---
title: Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados
titleSuffix: Microsoft Intune
description: Saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo iOS quando ele é executado.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 542d9c7890f9484311ca8e6400d0a75a41e13d7c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725693"
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use políticas de configuração de aplicativo no Microsoft Intune para fornecer definições de configuração personalizadas para um aplicativo iOS. Essas definições de configuração permitem que um aplicativo seja personalizado com base na orientação dos fornecedores do aplicativo. É necessário obter essas definições de configuração (chaves e valores) do fornecedor do aplicativo. Para configurar o aplicativo, especifique as configurações como chaves e valores ou como um XML que contém as chaves e os valores.

Como administrador do Microsoft Intune, é possível controlar quais contas de usuário são adicionadas aos aplicativos do Microsoft Office em dispositivos gerenciados. É possível limitar o acesso apenas a contas permitidas de usuários corporativos e bloquear contas pessoais em dispositivos registrados. Os aplicativos de suporte processam a configuração do aplicativo, removem e bloqueiam contas não aprovadas. As definições da política de configuração são usadas quando o aplicativo verifica se elas existem, normalmente, na primeira vez em que ele é executado.

Depois de adicionar uma política de configuração de aplicativo, você pode definir as atribuições para política de configuração de aplicativo. Ao definir as atribuições para a política, você pode optar por incluir ou excluir os grupos de usuários para os quais a política se aplica. Ao optar por incluir um ou mais grupos, você pode optar por selecionar grupos específicos para incluir ou selecionar grupos internos. Os grupos internos incluem **Todos os Usuários**, **Todos os Dispositivos** e **Todos os Usuários + Todos os Dispositivos**. 

> [!NOTE]
> O Intune fornece os grupos **Todos os Usuários** e **Todos os Dispositivos** pré-criados no console, com otimizações internas para sua conveniência. É altamente recomendável usar esses grupos para destinar a todos os usuários e todos os dispositivos em vez de usar outros grupos "Todos os usuários" e "Todos os dispositivos" que você mesmo tenha criado.

Depois de selecionar os grupos incluídos para sua política de configuração de aplicativo, você também pode escolher os grupos específicos a serem excluídos. Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](apps-inc-exl-assignments.md).

> [!TIP]
> No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior. Ela dá suporte aos seguintes tipos de instalação de aplicativo:
>
> - **Aplicativo iOS gerenciado da loja de aplicativos**
> - **Pacote do aplicativo do iOS**
>
> Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md). Para saber mais sobre como incorporar a configuração de aplicativo ao pacote do aplicativo .ipa para dispositivos gerenciados, confira Configuração de Aplicativos Gerenciados na [documentação do desenvolvedor do iOS](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html).

## <a name="create-an-app-configuration-policy"></a>Criar uma política de configuração do aplicativo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecione a carga de trabalho **Aplicativos clientes**.
4. Escolha **Políticas de configuração do aplicativo** no grupo **Gerenciar** e escolha **Adicionar**.
5. Defina os seguintes detalhes:
    - **Nome** – o nome do perfil exibido no portal do Azure.
    - **Descrição** – a descrição do perfil que é exibida no portal do Azure.
    - **Tipo de registro de dispositivo**: escolha **Dispositivos gerenciados** para dispositivos que foram registrados no Intune.
6. Selecione **iOS** para **Plataforma**.
7. Escolha **Aplicativo associado**. Em seguida, no painel **Aplicativo associado**, escolha o aplicativo gerenciado para o qual você deseja aplicar a configuração e selecione **OK**.
8. No painel **Adicionar política de configuração**, escolha **Definições de configuração**.
9. Selecione **Formato de definições de configuração**. Escolha um dos seguintes métodos para adicionar informações de configuração:
    - **Usar o designer de configuração**
    - **Inserir dados XML**<br><br>
    Para obter detalhes sobre como usar o designer de configuração, confira [Usar o designer de configuração](#use-configuration-designer). Para obter detalhes sobre como inserir dados XML, confira [Inserir dados XML](#enter-xml-data). 
10. Após adicionar suas informações de configuração, escolha **OK** e, em seguida, escolha **Adicionar** para adicionar a política de configuração. O painel de visão geral da política de configuração é exibido.
11. Selecione **Atribuições** para exibir as opções de inclusão e exclusão. 

    ![Captura de tela da guia Incluir de Atribuições de política](./media/app-configuration-policies-use-ios/app-config-policy01.png)
12. Selecione **Todos os Usuários** na guia **Inclusão**.

    ![Captura de tela de Atribuições de política – opção de lista suspensa Todos os usuários](./media/app-configuration-policies-use-ios/app-config-policy02.png)
13. Selecione a guia **Excluir**. 
14. Clique em **Selecionar grupos para excluir** para exibir o painel relacionado.

    ![Captura de tela Atribuições de política – folha Selecionar grupos para excluir](./media/app-configuration-policies-use-ios/app-config-policy03.png)
15. Escolha os grupos que você deseja excluir e, em seguida, clique em **Selecionar**.

    >[!NOTE]
    >Ao adicionar um grupo, se nenhum outro grupo ainda tiver sido incluído para um determinado tipo de atribuição, ele será pré-selecionado e ficará inalterável para outros tipos de atribuição de inclusão. Assim, esse grupo que foi usado, não poderá ser usado como um grupo excluído.
16. Clique em **Salvar**.

## <a name="use-configuration-designer"></a>Usar o designer de configuração

O Microsoft Intune fornece definições de configuração exclusivas a um aplicativo. Use o designer de configuração para aplicativos em dispositivos que estão registrados ou não no Microsoft Intune. O designer permite que você defina chaves de configuração e valores específicos que ajudam você a criar o XML subjacente. Você também deve especificar o tipo de dados para cada valor. Essas configurações são fornecidas para os aplicativos automaticamente quando os aplicativos são instalados.

### <a name="add-a-setting"></a>Adicionar uma configuração

1. Para cada chave e valor na configuração, defina:
   - **Chave de configuração** – a chave que identifica exclusivamente a configuração específica.
   - **Tipo de valor** – o tipo de dados do valor de configuração. Os tipos incluem Inteiro, Real, Cadeia de caracteres ou Booliano.
   - **Valor de configuração** – o valor da configuração.
2. Escolha **OK** para definir as configurações.

### <a name="delete-a-setting"></a>Excluir uma configuração

1. Escolha as reticências ( **...** ) ao lado da configuração.
2. Selecione **Excluir**.

Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.

### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Permitir somente contas da organização configuradas em aplicativos de várias identidades 

Para dispositivos iOS, use os seguintes pares de chave/valor:

| **Key** | IntuneMAMAllowedAccountsOnly |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Valores** | <ul><li>**Habilitado**: A única conta permitida é a conta de usuário gerenciado definida pela chave [IntuneMAMUPN](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm).</li><li>**Desabilitado** (ou qualquer valor que não seja uma correspondência que diferencia maiúsculas e minúsculas para **Habilitado**): Qualquer conta é permitida.</li></ul> |.

   > [!NOTE]
   > Você deve usar o OneDrive para iOS 10.34 ou posterior e o Outlook para iOS 2.99.0 ou posterior, e o aplicativo deve ser direcionado com as [políticas de proteção de aplicativo do Intune](app-protection-policy.md) ao permitir apenas contas da organização configuradas com várias identidades.

## <a name="enter-xml-data"></a>Inserir dados XML

É possível digitar ou colar uma lista de propriedades XML que contém as definições de configuração do aplicativo para dispositivos registrados no Intune. O formato da lista de propriedades XML varia dependendo do aplicativo que você está configurando. Para obter detalhes sobre o formato exato a ser usado, contate o fornecedor do aplicativo.

O Intune valida o formato XML. No entanto, o Intune não verifica se a PList (lista de propriedades) XML funciona com o aplicativo de destino.

Para saber mais sobre listas de propriedades XML:

- Consulte [Understand XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) (Compreender Listas de propriedades XML) na Biblioteca do Desenvolvedor iOS.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Exemplo de formato de arquivo XML de configuração de aplicativo

Quando você cria um arquivo de configuração de aplicativo, você pode especificar um ou mais dos seguintes valores usando este formato:

```xml
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
  <key>aaddeviceid</key>
  <string>{{aaddeviceid}}</string>
</dict>
```

### <a name="supported-xml-plist-data-types"></a>Tipos de dados XML PList com suporte

O Intune dá suporte para os seguintes tipos de dados em uma lista de propriedades:

- &lt;inteiro&gt;
- &lt;real&gt;
- &lt;cadeia de caracteres&gt;
- &lt;matriz&gt;
- &lt;dict&gt;
- &lt;true /&gt; ou &lt;false /&gt;

### <a name="tokens-used-in-the-property-list"></a>Tokens usados na lista de propriedades

Além disso, o Intune dá suporte aos seguintes tipos de token na lista de propriedades:
- \{\{userprincipalname\}\}—por exemplo, **John@contoso.com**
- \{\{mail\}\}—por exemplo, **John@contoso.com**
- \{\{partialupn\}\}—por exemplo, **João**
- \{\{accountid\}\}—por exemplo, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\}—por exemplo, **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\}—por exemplo, **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}—por exemplo, **João Silva**
- \{\{serialnumber\}\}—por exemplo, **F4KN99ZUG5V2** (para dispositivos iOS)
- \{\{serialnumberlast4digits\}\}— por exemplo, **G5V2** (para dispositivos iOS)
- \{\{aaddeviceid\}\} – por exemplo, **ab0dc123-45d6-7e89-aabb-cde0a1234b56**

## <a name="configure-the-company-portal-app-to-support-ios-dep-devices"></a>Configurar o aplicativo Portal da Empresa para dar suporte a dispositivos DEP com iOS

Os registros de DEP (Programa de Registro de Dispositivos da Apple) não são compatíveis com a versão da loja de aplicativos do aplicativo Portal da Empresa. No entanto, você pode configurar o aplicativo Portal da Empresa para dar suporte a dispositivos DEP com iOS usando as etapas a seguir.

1. No Intune, no portal do Azure:
    - Se necessário, adicione o Portal da Empresa do Intune em **Intune** > **Aplicativos cliente** > **Aplicativos** > **Adicionar**.
    - Acesse **Aplicativos cliente** > **Políticas de configuração de aplicativos** para criar uma política de configuração de aplicativo para o aplicativo Portal da Empresa.
2. Crie uma política de configuração de aplicativo com o XML abaixo. Para saber mais sobre como criar uma política de configuração de aplicativos e inserir dados XML, confira [Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados](app-configuration-policies-use-ios.md) ou, para MDM híbrido, consulte [Aplicar configurações aos aplicativos iOS com políticas de configuração de aplicativos no System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-ios-apps-with-app-configuration-policies).

    ``` xml
    <dict>
        <key>IntuneCompanyPortalEnrollmentAfterUDA</key>
        <dict>
            <key>IntuneDeviceId</key>
            <string>{{deviceid}}</string>
            <key>UserId</key>
            <string>{{userid}}</string>
        </dict>
    </dict>
    ```

3. Implante o Portal da Empresa em dispositivos com a política de configuração de aplicativos direcionada aos grupos desejados. Certifique-se de implantar a política somente em grupos de dispositivos que já foram registrados pelo DEP.
4. Avise os usuários para entrarem no aplicativo Portal da Empresa quando ele for automaticamente instalado.

## <a name="monitor-ios--app-configuration-status-per-device"></a>Monitorar o status da configuração do aplicativo iOS por dispositivo 
Depois que uma política de configuração for atribuída, você poderá monitorar o status de configuração do aplicativo iOS de cada dispositivo gerenciado. No **Microsoft Intune**, no portal do Azure, selecione **Dispositivos** > **Todos os dispositivos**. Na lista de dispositivos gerenciados, selecione um dispositivo específico para exibir uma folha para o dispositivo. Na folha do dispositivo, selecione **Configuração de aplicativo**.  

## <a name="additional-information"></a>Informações adicionais

- [Implantar definições de configuração de aplicativos no Outlook para iOS e Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune)

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo.