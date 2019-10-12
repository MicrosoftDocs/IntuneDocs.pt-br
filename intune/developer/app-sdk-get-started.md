---
title: Introdução ao SDK de Aplicativos do Microsoft Intune
description: Habilite rapidamente seu aplicativo móvel para MAM (gerenciamento de aplicativo móvel) com o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: bfe84b9bff41a8f715a9288ee93a2e78e52f7d34
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733836"
---
# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Introdução ao SDK de Aplicativos do Microsoft Intune

Este guia ajudará você a habilitar rapidamente seu aplicativo móvel dar suporte a políticas de Proteção de Aplicativo com o Microsoft Intune. Pode ser útil compreender primeiro os benefícios do SDK de Aplicativo do Intune enumerados na [Visão geral do SDK de Aplicativos do Intune](app-sdk.md).

O SDK do Aplicativo do Intune dá suporte a cenários semelhantes no iOS e Android e destina-se a criar uma experiência consistente em todas as plataformas para os administradores de TI. Porém, há pequenas diferenças no suporte a determinados recursos devido a diferenças e limitações da plataforma.

## <a name="register-your-store-app-with-microsoft"></a>Registrar seu aplicativo de uma loja de aplicativos no Microsoft

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a>Caso o aplicativo seja interno à sua organização e não esteja disponível publicamente:

Você _**não precisa**_ registrar seu aplicativo. Para [aplicativos de LOB (linha de negócios)](../apps/apps-add.md#app-types-in-microsoft-intune) interno escritos por ou para sua empresa, o administrador de TI implantará o aplicativo internamente. O Intune detectará que o aplicativo foi criado com o SDK e permitirá que o administrador de TI aplique as políticas de Proteção de Aplicativo a ele. É possível ignorar a seção [Habilitar o aplicativo iOS ou Android para a política de proteção do aplicativo](#enable-your-ios-or-android-app-for-app-protection-policy).

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a>Se o aplicativo for liberado para uma loja pública de aplicativos, como a Apple App Store ou o Google Play:

Primeiro, você _**deve**_ registrar o aplicativo no Microsoft Intune e concordar com os termos de registro. Em seguida, os administradores de TI poderão aplicar uma política de Proteção de Aplicativo ao aplicativo gerenciado, que será listado como um [aplicativo de parceiro protegido do Intune](../apps/apps-supported-intune-apps.md#partner-apps).

Somente depois que o registro for concluído e confirmado pela equipe do Microsoft Intune os administradores do Intune terão a opção de aplicar a política de proteção do aplicativo ao link profundo do aplicativo. A Microsoft também adicionará seu aplicativo à [página Parceiros do Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps). Nessa página, o ícone do aplicativo será exibido para mostrar que ele dá suporte às políticas de proteção do aplicativo do Intune.

### <a name="the-registration-process"></a>O processo de registro
Para iniciar o processo de registro e, se você ainda não estiver trabalhando com um contato da Microsoft, preencha o [Questionário de Parceiro de Aplicativo do Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR80SNPjnVA1KsGiZ89UxSdVUMEpZNUFEUzdENENOVEdRMjM5UEpWWjJFVi4u).

Usaremos os endereços de email listados em suas respostas ao questionário para contatá-lo e continuar o processo de registro. Além disso, usamos o seu endereço de email de registro para entrar em contato com você caso tenhamos quaisquer dúvidas.

> [!NOTE]
> Todas as informações coletadas no questionários e por email com a equipe do Microsoft Intune serão tratadas de acordo com a [Política de Privacidade da Microsoft](https://www.microsoft.com/privacystatement/default.aspx).

**O que esperar no processo de registro**:

1. Após enviar o questionário, nós contataremos você pelo endereço de email registrado para confirmar o recebimento ou para solicitar informações adicionais para concluir o registro.

2. Após recebermos de você todas as informações necessárias, enviaremos o Contrato de Parceiro do Aplicativo do Microsoft Intune para você assinar. Este contrato descreve os termos que sua empresa deve aceitar antes de se tornar um parceiro de aplicativo do Microsoft Intune.

3. Você também será notificado quando seu aplicativo for registrado com êxito no serviço do Microsoft Intune e quando ele estiver em destaque no site de [parceiros do Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

4. Por fim, o link profundo de seu aplicativo será adicionado à próxima atualização mensal do Serviço do Intune. Por exemplo, se as informações o registro forem concluídas em julho, o link profundo terá suporte em meados de agosto.

Se o link profundo do aplicativo for alterado no futuro, você precisará registrar novamente o aplicativo.

> [!NOTE]
> Além disso, informe se você atualizou o aplicativo com uma nova versão do SDK do Aplicativo do Intune.

## <a name="download-the-sdk-files"></a>Baixar os arquivos do SDK

Os SDKs do Aplicativo do Intune para iOS e Android nativo são hospedados em uma conta do GitHub da Microsoft. Esses repositórios públicos têm os arquivos do SDK para o iOS e Android nativo, respectivamente:

* [SDK de Aplicativo do Intune para iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [SDK de Aplicativo do Intune para Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Caso o aplicativo seja um aplicativo Xamarin, use essa variante do SDK:

* [Associações do Xamarin do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)

Convém criar uma conta do GitHub que você possa usar para bifurcar e efetuar pull de nosso repositórios. O GitHub permite que os desenvolvedores se comuniquem com nossa equipe de produto, abram questões e recebam respostas rápidas, exibam notas de versão e forneçam comentários à Microsoft. Em caso de dúvidas sobre o GitHub do SDK do Aplicativo do Intune, contate msintuneappsdk@microsoft.com.

## <a name="enable-your-ios-or-android-app-for-app-protection-policy"></a>Habilitar o aplicativo iOS ou Android para a política de proteção do aplicativo

Você precisará de um dos seguintes guias do desenvolvedor para ajudá-lo a integrar o SDK do Aplicativo do Intune em seu aplicativo:

* **[Guia do Desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md)** : esse documento fornece um passo a passo para a habilitação do aplicativo iOS nativo com o SDK do Aplicativo do Intune.

* **[Guia do Desenvolvedor do SDK do Aplicativo do Intune para Android](app-sdk-android.md)** : esse documento fornece um passo a passo para a habilitação do aplicativo Android nativo com o SDK do Aplicativo do Intune.

* **[Guia de Associações do Xamarin de SDK do Aplicativo do Intune](app-sdk-xamarin.md)** : esse documento ajudará você a criar aplicativos iOS e Android usando o Xamarin para as políticas de Proteção de Aplicativo do Intune.



## <a name="enable-your-ios-or-android-app-for-app-based-conditional-access"></a>Habilitar o aplicativo iOS ou Android para Acesso Condicional baseado em aplicativo

Além de habilitar o aplicativo com a política de proteção do aplicativo, para que ele funcione corretamente com o Acesso Condicional baseado em aplicativo AAD (Azure ActiveDirectory), é necessário o seguinte:

* Criar o aplicativo com a [Biblioteca de Autenticação do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) e habilitá-lo para autenticação com o Agente do AAD.

* A [ID do Cliente do AAD](https://docs.microsoft.com/azure/app-service/app-service-mobile-how-to-configure-active-directory-authentication#configure-a-native-client-application) deve ser exclusiva para o aplicativo em todas as plataformas Android e iOS.

## <a name="configure-telemetry-for-your-app"></a>Configurando a Telemetria para seu aplicativo

O Microsoft Intune coleta dados sobre estatísticas de uso para seu aplicativo.

* **SDK de Aplicativo Intune para iOS**: o SDK registra dados de telemetria do SDK sobre eventos de uso por padrão. Esses dados são enviados para o Microsoft Intune.

  * Se optar por não enviar dados de telemetria do SDK para o Microsoft Intune do seu aplicativo, você deverá desabilitar a transmissão de telemetria definindo a propriedade `MAMTelemetryDisabled` como ”YES” no dicionário IntuneMAMSettings.

* **SDK de Aplicativo do Intune para Android**: o SDK de Aplicativo do Intune para Android não controla a coleta de dados do aplicativo. Por padrão, o aplicativo Portal da Empresa registra em log os dados de telemetria. Esses dados são enviados para o Microsoft Intune. De acordo com a Microsoft Policy, nós não coletamos PII (informações de identificação pessoal). 

  * Se os usuários finais optarem por não enviar esses dados, eles deverão desligar a telemetria em Configurações no aplicativo Portal da Empresa. Para obter mais informações, consulte [Como desligar a coleta de dados de uso da Microsoft](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android). 

## <a name="line-of-business-app-version-numbers"></a>Números de versão de aplicativo de linha de negócios

Aplicativos de linha de negócios no Intune agora exibem o número de versão para aplicativos iOS e Android. O número é exibido no portal do Azure na lista de aplicativos e na folha de visão geral do aplicativo. Os usuários finais podem ver o número do aplicativo no aplicativo do Portal da Empresa e no portal da web.

### <a name="full-version-number"></a>Número de versão completo

O número de versão completo identifica uma versão específica do aplicativo. O número é exibido como _Versão_(_Build_). Por exemplo, 2.2(2.2.17560800). 

O número de versão completa tem dois componentes:

- **Versão**  
  O número de versão é o número de versão legível do aplicativo. Isso é usado pelos usuários finais para identificar versões diferentes do aplicativo.

- **Número de build**  
  O número de build é um número interno que pode ser usado na detecção do aplicativo e para gerenciar o aplicativo de forma programática. O número de build se refere a uma iteração do aplicativo que referencia alterações no código.

### <a name="version-and-build-number-in-android-and-ios"></a>Número de versão e de build no Android e iOS

Tanto Android quanto iOS usam números de versão e de build em referência a aplicativos. No entanto, os dois sistemas operacionais têm significados que são específicos de cada um. A tabela a seguir explica como esses termos estão relacionados.

Se você estiver desenvolvendo um aplicativo de linha de negócios para uso no Intune, lembre-se de usar o número de versão e de build. Recursos de gerenciamento de Aplicativo do Intune usam um **CFBundleVersion** (para iOS) e **PackageVersionCode** (para Android) significativos. Esses números são incluídos no manifesto do aplicativo. 

Intune|iOS|Android|Descrição|
|---|---|---|---|
Número de versão|CFBundleShortVersionString|PackageVersionName |Esse número indica uma versão específica do aplicativo para usuários finais.|
Número da versão|CFBundleVersion|PackageVersionCode |Esse número é usado para indicar uma iteração no código do aplicativo.|

#### <a name="ios"></a>iOS

- **CFBundleShortVersionString**  
  Especifica o número de versão do evento do pacote. Esse número identifica uma versão lançada do aplicativo. O número é usado pelos usuários finais para referenciar o aplicativo.
- **CFBundleVersion**  
  A versão de build do pacote, que identifica uma iteração do pacote. O número pode identificar um pacote lançado ou não lançado. O número é usado para detecção de aplicativo.

#### <a name="android"></a>Android

- **PackageVersionName**  
  O número de versão mostrado aos usuários. Esse atributo pode ser definido como uma cadeia de caracteres bruta ou como uma referência a um recurso de cadeia de caracteres. A cadeia de caracteres não tem nenhuma outra finalidade que não seja ser exibida para os usuários.
- **PackageVersionCode**  
  Um número de versão interno. Esse número é usado apenas para determinar se uma versão é mais recente do que a outra, com os números mais altos indicando as versões mais recentes. Essa não é a versão 

## <a name="next-steps-after-integration"></a>Próximas etapas após integração

### <a name="test-your-app"></a>Teste seu aplicativo
Depois de concluir as etapas necessárias para integrar seu aplicativo iOS ou Android com o SDK do Aplicativo do Intune, você precisará garantir que todas as políticas de proteção do aplicativo estão habilitadas e funcionando para o usuário e o administrador de TI. Para testar seu aplicativo integrado, você precisará do seguinte:

* **Conta de teste do Microsoft Intune**: para testar seu aplicativo gerenciado pelo Intune em relação aos recursos de proteção de aplicativo do Intune, você precisará de uma conta do Microsoft Intune.

  * Se você for um ISV que habilita aplicativos da loja do iOS ou do Android para a política de proteção do aplicativo do Intune, receberá um código promocional após a conclusão do registro no Microsoft Intune, conforme descrito na etapa de registro. O código de promoção permitirá que você se inscreva para uma avaliação de um ano de uso estendido do Microsoft Intune.

  * Se estiver desenvolvendo um aplicativo de linha de negócios que não será enviado para a loja, você deverá ter acesso ao Microsoft Intune por meio de sua organização. Você também pode se inscrever para uma avaliação gratuita de uma mês no [Microsoft Intune](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).

  * Se estiver testando seu aplicativo em um dispositivo móvel usando uma conta de usuário final, verifique se você concedeu a essa conta uma licença do Intune pelo site da Central de administração do Microsoft 365. Depois de fazer logon com uma conta do administrador, confira [Atribuir uma licença do Microsoft Intune](../fundamentals/licenses-assign.md).

* **Políticas de proteção do aplicativo do Intune**: para testar seu aplicativo em todas as políticas de proteção do aplicativo do Intune, é necessário saber qual é o comportamento esperado para cada configuração da política. Consulte as descrições de [políticas de proteção do aplicativo do iOS](../apps/app-protection-policy-settings-ios.md) e [políticas de proteção do aplicativo do Android](../apps/app-protection-policy-settings-android.md). Se seu aplicativo integrou o SDK do Intune, mas ainda não está listado no portal do Azure como um aplicativo de destino, você poderá direcioná-lo com uma política selecionando a opção "+ Mais Aplicativos" e fornecendo a ID do pacote (iOS) ou o nome do pacote (Android) na caixa de texto.

* **Solução de problemas**: se você encontrar algum problema ao testar manualmente a experiência do usuário durante a instalação do seu aplicativo, confira [Solucionar problemas de instalação do aplicativo](../apps/troubleshoot-app-install.md). 

### <a name="give-your-app-access-to-the-intune-app-protection-service-optional"></a>Fornecer ao aplicativo o acesso ao serviço de proteção de aplicativo do Intune (opcional)

Se o aplicativo estiver usando suas próprias configurações personalizadas do Azure Active Directory (AAD) para autenticação, então será necessário executar as etapas a seguir para os aplicativos de repositório público, bem como os aplicativos LOB internos. Não é necessário executar as etapas **se o seu aplicativo estiver usando a ID padrão do cliente do SDK do Intune**. 

Depois que você registrar seu aplicativo no locatário do Azure e ele estiver aparecendo em **Todos os Aplicativos**, você deverá fornecer ao aplicativo o acesso ao serviço de proteção de aplicativo do Intune (anteriormente conhecido como serviço MAM). No portal do Azure:

1. Acesse a folha **Azure Active Directory**.
2. Em **Registros de aplicativo**, vá para a listagem configurada para o aplicativo.
3. Clique em **+ Adicionar uma permissão**.
4. Clique em **APIs que minha organização usa**. 
5. Na caixa de pesquisa, insira **Gerenciamento de Aplicativo Móvel da Microsoft**.
6. Em **Permissões Delegadas**, marque a caixa de seleção **DeviceManagementManagedApps.ReadWrite: Ler e Gravar Dados de Gerenciamento de Aplicativo do Usuário***.
7. Clique em **Adicionar permissões**.

### <a name="badge-your-app-optional"></a>Marcar com uma notificação no aplicativo (opcional)

Depois de validar que as políticas de proteção do aplicativo do Intune funcionam no aplicativo, é possível marcar o ícone do aplicativo com uma notificação do logotipo de proteção do aplicativo do Intune.

Essa notificação indica aos administradores de TI, usuários finais e clientes potenciais do Intune que seu aplicativo funciona com as políticas de proteção do aplicativo do Intune. Ela incentiva o uso e a adoção de seu aplicativo pelos clientes do Intune.

A notificação é um ícone de porta-arquivos e pode ser vista nos exemplos abaixo:

![Políticas de proteção de aplicativo do Intune – Exemplo de notificação 1](./media/app-sdk-get-started/badge-example-1.png) ![Políticas de proteção de aplicativo do Intune – Exemplo de notificação 2](./media/app-sdk-get-started/badge-example-2.png)

**O que será necessário para marcar o aplicativo com uma notificação**:

* Um aplicativo de manipulação de imagem que pode ler arquivos **.eps** ou um aplicativo Adobe que pode ler arquivos **.ai**.

* Encontre os [ativos de notificação de aplicativo do Intune e as diretrizes](https://github.com/msintuneappsdk/intune-app-partner-badge) no GitHub do Microsoft Intune.