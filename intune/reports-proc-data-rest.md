---
title: Obter dados da API do Data Warehouse com um cliente REST
description: Recupere dados do Data Warehouse do Intune usando uma API RESTful.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1bbb0e8ba84e221df3a434da79c513939267648b
ms.sourcegitcommit: b8ef9d8387b4d9b2ea4e6ce937635304771e6532
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2017
---
# <a name="get-data-from-the-intune-data-warehouse-api-with-a-rest-client"></a>Obter dados da API do Data Warehouse do Intune com um cliente REST

Você pode acessar o modelo de dados do Data Warehouse do Intune por meio de pontos de extremidade RESTful. Para obter acesso aos seus dados, seu cliente deve ser autorizado no Microsoft Azure Active Directory (Azure AD) usando OAuth 2.0. Para habilitar o acesso, primeiro configure um aplicativo nativo no Azure e conceda permissões para a API do Microsoft Intune. O cliente local é autorizado e, em seguida, ele pode se comunicar com os pontos de extremidade do Data Warehouse por meio do aplicativo nativo.

As etapas para configurar um cliente para obter dados da API do Data Warehouse requerem:

1. Criar um aplicativo cliente como um aplicativo nativo no Azure
3. Conceder ao cliente o acesso de aplicativo à API do Microsoft Intune
3. Criar um cliente REST local para obter os dados

Siga as etapas a seguir para saber como autorizar e usar o Postman como um cliente. O Postman é uma ferramenta bastante usada para solucionar problemas e desenvolver clientes REST para trabalhar com APIs. Para obter mais informações sobre o Postman, consulte o site [Postman](https://www.getpostman.com). Este tópico também inclui um exemplo de código C#. O exemplo fornece uma amostra de como autorizar um cliente e obter dados da API.

## <a name="create-a-native-app-in-azure"></a>Criar um aplicativo nativo no Azure

Crie um aplicativo nativo no Azure. Este aplicativo nativo é o aplicativo cliente. O cliente em execução no seu computador local referencia a API do Data Warehouse do Intune quando o cliente local solicita credenciais. 

1. Entre no portal do Azure do seu locatário. Escolha **Azure Active Directory** > **Registros de aplicativo** para abrir a folha **Registros de aplicativo**.
2. Clique em **Novo registro de aplicativo**.
3. Digite os detalhes do aplicativo.
    1.  Digite um nome amigável, como Cliente do Data Warehouse do Intune, em **Nome**.
    2.  Selecione **Nativo** para o **Tipo de aplicativo**.
    3.  Digite uma URL em **URL de logon**. A URL de logon dependerá do cenário específico, no entanto, se você planeja usar o Postman, digite `https://www.getpostman.com/oauth2/callback`. Você usará o retorno de chamada para a etapa de autenticação do cliente ao autenticar no Azure AD.
4.  Clique em **Criar**.

     ![API Intune Data Warehouse](media\reports-get_rest_data_client_overview.png)

5. Anote a **ID do aplicativo** desse aplicativo. Você usará a ID na próxima seção.
6. Se você planeja usar o Postman, adicione uma chave. A chave é usada como o segredo do cliente com autenticação para o Azure AD. Para adicionar uma chave:
    1.  Clique em **Chaves** em **Acesso à API** na folha Configurações do aplicativo.
    2.  Digite um nome para sua chave, como Segredo do cliente, em **Descrição**.
    3.  Selecione **1 ano** para a Duração.
    4.  Clique em **Salvar**. 
    5.  Copie o valor da chave. Você não poderá recuperar a chave depois de fechar a folha **Configurações** das Chaves.

## <a name="grant-the-native-app-access-to-the-microsoft-intune-api"></a>Conceder ao aplicativo nativo o acesso à API do Microsoft Intune

Agora você tem um aplicativo definido no Azure. Conceda acesso do aplicativo nativo à API do Microsoft Intune.

1.  Clique no aplicativo nativo. Você nomeou o aplicativo como algo semelhante a Cliente do Data Warehouse do Intune.
2.  Clique em **Permissões necessárias** na folha **Configurações**
3.  Clique em **Adicionar** na folha **Permissões necessárias**.
4.  Clique em **Selecionar uma API**.
5.  Pesquise o nome do aplicativo Web. Seu nome é **API do Microsoft Intune**.
6.  Clique no aplicativo na lista.
7.  Clique em **Selecionar**.
8.  Marque a caixa **Permissões Delegadas** para adicionar **Obter informações do data warehouse do Microsoft Intune**.

    ![Habilitar acesso](media\reports-get_rest_data_client_access.png)

9.  Clique em **Selecionar**.
10.  Clique em **Concluído**.
11.  Opcionalmente, clique em **Conceder Permissões** na folha Permissões necessárias. Essa opção concede acesso a todas as contas no diretório atual. Isso impedirá que a caixa de diálogo de consentimento apareça para cada usuário no locatário. Para obter mais informações, consulte [Integrando aplicativos com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications).
12.  Clique em **Sim**.

## <a name="get-data-from-the-microsoft-intune-api-with-postman"></a>Obter dados da API do Microsoft Intune com o Postman

Você pode trabalhar com a API do Data Warehouse do Intune com um cliente REST genérico como o Postman. O Postman pode fornecer informações sobre os recursos da API, o modelo de dados OData subjacente e solucionar problemas de conexão para os recursos da API. Nesta seção, você pode encontrar informações de como gerar um token Auth2.0 para seu cliente local. O cliente precisará do token para autenticar-se no Azure AD e acessar os recursos da API.

### <a name="information-you-will-need-to-make-the-call"></a>Informações necessárias para fazer a chamada

Você precisa das seguintes informações para fazer uma chamada à REST usando o Postman:

| Atributo        | Descrição                                                                                                                                                                          | Exemplo                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| URL de Retorno de Chamada     | Defina como a URL de retorno de chamada na página de configurações do aplicativo.                                                                                                                              | https://www.getpostman.com/oauth2/callback                                                    |
| Nome do Token       | Uma cadeia de caracteres usada para passar as credenciais para o aplicativo do Azure. O processo gera o token que permite fazer uma chamada à API do Data Warehouse.                          | Portador                                                                                        |
| URL de Autenticação         | Esta é a URL usada para a autenticação. | https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com |
| URL do Token de Acesso | Esta é a URL usada para conceder o token.                                                                                                                                              | https://login.microsoftonline.com/common/oauth2/token |
| ID do Cliente        | Você criou e anotou essa ID quando criou o aplicativo nativo no Azure.                                                                                               | 4184c61a-e324-4f51-83d7-022b6a81b991                                                          |
| Segredo de Cliente    | Você criou e anotou esse segredo quando criou o aplicativo nativo no Azure.                                                                                              | JZoRZGPmN9xwsUnfX9UW877dkV5Fn/qQClhr7SuyMUQ=                                                  |
| Escopo (opcional) | Em Branco                                                                                                                                                                               | Você pode deixar o campo em branco.                                                                     |
| Tipo de Concessão       | O token é um código de autorização.                                                                                                                                                  | Código de Autorização                                                                            |

Você precisa do ponto de extremidade. Neste exemplo, vamos recuperar dados da entidade **datas**. A entidade **datas** tem o seguinte formato: `https://fef.{aus}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`. Você usará a URL de gerenciamento do locatário. Você usou a URL de gerenciamento do locatário quando criou o aplicativo Web.

### <a name="make-the-rest-call"></a>Fazer a chamada à REST

Para obter um novo token de acesso do Postman, você deve adicionar a URL de autorização do Azure AD, adicionar a ID do cliente e o Segredo do cliente. O Postman carregará a página de autorização na qual você poderá digitar suas credenciais.

#### <a name="add-the-information-used-to-request-the-token"></a>Adicionar as informações usadas para solicitar o token

1.  Baixe o Postman se ele ainda não estiver instalado. Para baixar o Postman, acesse [www.getpostman](https://www.getpostman.com).
2.  Abra o Postman. Escolha a operação HTTP **GET**.
3.  Cole a URL do ponto de extremidade no endereço. Deverá ser semelhante a:  

    `https://fef.msua06.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4.  Escolha a guia **Autorização** e selecione **OAuth 2.0** na lista **Tipo**.
5.  Clique em **Obter Novo Token de Acesso**.
6.  Verifique se você já adicionou a URL de retorno de chamada em seu aplicativo no Azure. A URL de retorno de chamada é `https://www.getpostman.com/oauth2/callback`.
7.  Digite Portador para o **Nome do Token**.
8.  Adicione a **URL do Auth**. Deverá ser semelhante a:  

    `https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com`
9.  Adicione a **URL do Token de Acesso**. Deverá ser semelhante a:  

     `https://login.microsoftonline.com/common/oauth2/token`

10. Adicione a **ID do Cliente** do aplicativo nativo que você criou no Azure e nomeou como `Intune Data Warehouse Client`. Deverá ser semelhante a:  

     `4184c61a-e324-4f51-83d7-022b6a81b991`

11. Adicione o **Segredo do Cliente** que você definiu como uma chave quando criou seu aplicativo nativo no Azure. Deverá ser semelhante a: 

     `F360R69M0MS72OB6YAqTyXO9MsXZx/OJTgAE2HB4k2k=`

12. Selecione o **Código de Autorização** e Solicitar token de acesso localmente.

13. Clique em **Solicitar Token**.

    ![Informações para o token](media\reports-postman_getnewtoken.png)

14. Digite as credenciais na página de autorização do AD ativo. A lista de Tokens Existentes no Postman agora contém o token chamado `Bearer`.
16. Escolha o token. Selecione **Cabeçalho** no qual o token será adicionado.
17. Clique em **Usar Token**. A lista de cabeçalhos contém o novo valor da chave de Autorização e o valor `Bearer <your-authorization-token>`.

#### <a name="send-the-call-to-the-endpoint-using-postman"></a>Enviar a chamada para o ponto de extremidade usando o Postman

1.  Clique em **Enviar**.
2.  Os dados de retorno são exibidos no corpo da resposta do Postman.

    ![Postman 200OK](media\reports-postman_200OK.png)

## <a name="create-a-rest-client-c-to-get-data-from-the-intune-data-warehouse"></a>Criar um cliente REST (C#) para obter dados do Data Warehouse do Intune

O exemplo a seguir contém um cliente REST simples. O código usa a classe **httpClient** da biblioteca do .Net. Depois de obter as credenciais para o Azure AD, o cliente cria uma chamada GET REST para recuperar a entidade de datas da API do Data Warehouse.

> [!Note]  
> Você pode acessar o exemplo de código a seguir [no GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs). Consulte o repositório do GitHub para obter as alterações e atualizações mais recentes para o exemplo.

1.  Abra o **Microsoft Visual Studio**.
2.  Escolha **Arquivo** > **Novo Projeto**. Expanda **Visual C#** e escolha **Aplicativo de Console (.Net Framework)**. 
3.  Nomeie o projeto como ` IntuneDataWarehouseSamples`, navegue até onde deseja salvar o projeto e, em seguida, clique em **OK**.
3.  Clique com o botão direito do mouse no nomes da solução no Gerenciador de Soluções e, em seguida, selecione **Gerenciar Pacotes NuGet para a Solução**. Clique em **Procurar** e, em seguida, digite 'Microsoft.IdentityModel.Clients.ActiveDirectory' na caixa de pesquisa.
4. Escolha o pacote, selecione o projeto **IntuneDataWarehouseSamples** em Gerenciar Pacotes da Sua Solução e, em seguida, clique em **Instalar**. 
5. Clique em **Eu Aceito** para aceitar a licença do pacote NuGet.
6. Abra `Program.cs` no Gerenciador de Soluções.

    ![Projeto no Visual Studio](media\reports-get_rest_data_in.png)

7.  Substitua o código em Program.cs pelo código a seguir:  
    ```csharp
namespace IntuneDataWarehouseSamples
{
    using System;
    using System.Net.Http;
    using System.Net.Http.Headers;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    class Program
    {
     static void Main(string[] args)
  {
   /**
    * TODO: Replace the below values with your own.
    * emailAddress - The email address of the user that you will authenticate as.
    *
    * password  - The password for the above email address.
    *    This is inline only for simplicity in this sample. We do not 
    *    recommend storing passwords in plaintext.
    *
    * applicationId - The application ID of the native app that was created in AAD.
    *
    * warehouseUrl   - The data warehouse URL for your tenant. This can be found in 
    *      the Azure portal.
    * 
    * collectionName - The name of the warehouse entity collection you would like to 
    *      access.
    */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "<Application ID>";
   var warehouseUrl = "https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
    resource: "https://api.manage.microsoft.com/",
    clientId: applicationId,
    userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
  }
    }
    ```

8.  Atualize os `TODO`s no exemplo de código.
9.  Pressione **Ctrl + F5** para compilar e executar o cliente Intune.DataWarehouseAPIClient no modo de depuração.

    ![Entidade de data recuperada no formato JSON.](media\reports-get_rest_data_output.png)

10.  Examine a saída do console. A saída contém dados no formato JSON extraídos da entidade **datas** em seu locatário do Intune.

## <a name="next-steps"></a>Próximas etapas

Você pode encontrar detalhes sobre a autorização, a estrutura da URL da API e os pontos de extremidade do OData em [Usar a API do Data Warehouse do Intune](reports-api-url.md). 

Você também pode consultar o modelo de dados do Data Warehouse do Intune para localizar as entidades de dados contidas na API. Para obter mais informações, consulte [Modelo de dados da API do Data Warehouse do Intune](reports-ref-data-model.md)