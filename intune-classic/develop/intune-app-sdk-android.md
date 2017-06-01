---
title: Guia do SDK de Aplicativo do Microsoft Intune para desenvolvedores do Android | Microsoft Docs
description: "O SDK de Aplicativo do Microsoft Intune para Android permite incorporar o MAM (gerenciamento de aplicativo móvel) do Intune em seu aplicativo Android."
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 973e97c7dc5f16df93d2c74546b9a4c6c05a0354
ms.contentlocale: pt-br
ms.lasthandoff: 05/31/2017


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Guia do SDK de Aplicativo do Microsoft Intune para desenvolvedores do Android

> [!NOTE]
> Leia primeiro a [Visão geral do SDK de Aplicativo do Intune](intune-app-sdk.md), que explica os recursos atuais do SDK e descreve como preparar a integração em cada plataforma com suporte.

O SDK do Aplicativo do Microsoft Intune para Android permite incorporar políticas de proteção do aplicativo do Intune (também conhecidas como políticas **APP** ou MAM) em seu aplicativo Android nativo. Um aplicativo orientado para Intune é aquele que está integrado ao SDK de Aplicativo do Intune. Os administradores do Intune podem facilmente implantar políticas de proteção do aplicativo em seu aplicativo orientado para Intune quando o Intune gerencia o aplicativo de forma ativa.


## <a name="whats-in-the-sdk"></a>O que está contido no SDK

O SDK do aplicativo do Intune é composto pelos seguintes arquivos:  

* **Microsoft.Intune.MAM.SDK.aar**: os componentes do SDK, com exceção dos arquivos JAR Support.V4 e Support.V7. Esse arquivo pode ser usado no lugar de componentes individuais se sua compilação do sistema der suporte a arquivos AAR.
* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v4. Os aplicativos que precisam desse suporte devem referenciar diretamente o arquivo JAR.
* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v7. Os aplicativos que precisam desse suporte devem referenciar diretamente o arquivo JAR.
* **proguard.txt**: contém regras do ProGuard que devem ser aplicadas se estiver desenvolvendo com o ProGuard.
* **CHANGELOG.txt**: fornece um registro das alterações feitas em cada versão do SDK.
* **THIRDPARTYNOTICES.TXT**: um aviso de atribuição que reconhece códigos de terceiros e/ou de OSS que serão compilados em seu aplicativo.

Se o sistema de compilação não der suporte a arquivos AAR, você poderá usar os seguintes arquivos em vez de Microsoft.Intune.MAM.SDK.aar.
* **Microsoft.Intune.MAM.SDK.jar**: as interfaces necessárias para habilitar o MAM e a interoperabilidade com o aplicativo de Portal da Empresa do Intune. Os aplicativos devem especificá-lo como uma referência de biblioteca Android.
* **O diretório de recursos**: os recursos (como cadeias de caracteres) dos quais o SDK depende.
* **AndroidManifest.xml**: os pontos de entrada e os requisitos da biblioteca.


## <a name="requirements"></a>Requisitos

O SDK de Aplicativos do Intune é um projeto Android compilado. Como resultado, ele não é afetado pela versão do Android que o aplicativo usa para suas versões de API mínima ou de destino. O SDK dá suporte à API 14 do Android (Android 4.0 +) por meio da API 25 do Android (Android 7.1).



### <a name="company-portal-app"></a>Aplicativo do Portal da Empresa
O SDK de Aplicativo do Intune para Android depende da presença do aplicativo do [Portal da Empresa](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) no dispositivo para habilitar as políticas de proteção do aplicativo. O Portal da Empresa recupera as políticas de proteção de aplicativo do serviço Intune. Quando o aplicativo é inicializado, ele carrega a política e o código para impor essa política do Portal da Empresa.

> [!NOTE]
> Quando o aplicativo do Portal da Empresa não está no dispositivo, um aplicativo orientado para Intune comporta-se como um aplicativo normal que não oferece suporte a políticas de proteção de aplicativo do Intune.

Para a proteção do aplicativo sem registro de dispositivo, o usuário _**não**_ precisa registrar o dispositivo usando o aplicativo do Portal da Empresa.

## <a name="sdk-integration"></a>Integração do SDK

### <a name="build-integration"></a>Integração de compilação

O SDK de Aplicativos do Intune é uma biblioteca Android padrão sem dependências externas. O **Microsoft.Intune.MAM.SDK.jar** contém ambas as interfaces necessárias para a habilitação da política de proteção de aplicativo e o código necessário para interoperar com o aplicativo do Portal da Empresa do Microsoft Intune.

O **Microsoft.Intune.MAM.SDK.jar** deve ser especificado como uma referência da biblioteca do Android. Para fazer isso, abra o projeto de aplicativo no Android Studio e vá para **Arquivo > Novo > Novo módulo** e selecione **Importar .JAR/Pacote .AAR**. Selecione nosso pacote de arquivamento do Android Microsoft.Intune.MAM.SDK.aar.

Além disso, o **Microsoft.Intune.MAM.SDK.Support.v4** e o **Microsoft.Intune.MAM.SDK.Support.v7** contêm variantes do Intune de `android.support.v4` e `android.support.v7` respectivamente. Eles não são criados no Microsoft.Intune.MAM.SDK.aar no caso de um aplicativo não querer incluir as bibliotecas de suporte. Eles são arquivos JAR padrão em vez de projetos de biblioteca do Android.

#### <a name="proguard"></a>ProGuard

Se o [ProGuard](http://proguard.sourceforge.net/) (ou qualquer outro mecanismo de redução/ofuscação) for usado como uma etapa de compilação, as classes de SDK do Intune deverão ser excluídas. Para o ProGuard, isso pode ser feito incluindo as regras do arquivo proguard.txt distribuído com o SDK.

As Bibliotecas de autenticação do Azure Active Directory (ADAL) podem ter suas próprias restrições de ProGuard. Se seu aplicativo se integrar com a ADAL, você deverá seguir a documentação do ADAL sobre estas restrições.

### <a name="entry-points"></a>Pontos de entrada
======= A Biblioteca de Autenticação do Azure Active Directory ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) exige essas permissões para realizar a autenticação agenciada. Se essas permissões não forem concedidas ao aplicativo ou revogadas pelo usuário, os fluxos de autenticação que exigem o agente (o aplicativo de Portal da Empresa) serão desabilitados.

O SDK de Aplicativo do Intune requer alterações no código-fonte do aplicativo para habilitar as políticas de proteção de aplicativo do Intune. Isso é feito por meio da substituição das classes base do Android por classes base do Intune equivalentes, cujos nomes têm o prefixo **MAM**. As classes do SDK estão entre a classe base do Android e a versão do próprio aplicativo derivada dessa classe. Usando uma atividade como exemplo, você acabará com uma hierarquia de herança que se parece com: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Por exemplo, quando `AppSpecificActivity` interage com seu pai (por exemplo, chamando `super.onCreate()`), `MAMActivity` é a superclasse.

Aplicativos Android típicos têm um modo único e têm acesso ao sistema por meio de seu objeto de [**Contexto**](https://developer.android.com/reference/android/content/Context.html). Aplicativos que integraram o SDK de Aplicativo do Intune, por outro lado, têm modo dual. Esses aplicativos continuam a acessar o sistema por meio do objeto `Context`. Dependendo da base de `Activity` utilizada, o objeto `Context` será fornecido pelo Android ou será inteligentemente multiplexado entre uma exibição restrita do sistema e a fornecida pelo Android `Context`.


## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent"></a>Substitua classes, métodos e atividades por seus equivalentes com MAM

As classes base do Android devem ser substituídas por seus equivalentes com MAM. Para fazer isso, localize todas as instâncias das classes listadas na tabela a seguir e as substitua pelo SDK de Aplicativo do Intune equivalente.

| Classe base do Android | Substituição do SDK de Aplicativo do Intune |
|--|--|
| android.app.Activity | MAMActivity |
| android.app.ActivityGroup | MAMActivityGroup |
| android.app.AliasActivity | MAMAliasActivity |
| android.app.Application | MAMApplication |
| android.app.DialogFragment | MAMDialogFragment |
| android.app.ExpandableListActivity | MAMExpandableListActivity |
| android.app.Fragment | MAMFragment |
| android.app.IntentService | MAMIntentService |
| android.app.LauncherActivity | MAMLauncherActivity |
| android.app.ListActivity | MAMListActivity |
| android.app.NativeActivity | MAMNativeActivity |
| android.app.PendingIntent | MAMPendingIntent (veja as observações abaixo) |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (necessário apenas se o Associador não for gerado de uma interface da AIDL (linguagem IDL do Android)) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft.Intune.MAM.SDK.Suppout.v4.jar:

| MAM do Intune da classe do Android | Substituição do SDK de Aplicativo do Intune |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| Android.support.v4.App.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft.Intune.MAM.SDK.Suppout.v7.jar:

|Classe do Android | Substituição do SDK de Aplicativo do Intune |
|--|--|
|Android.support.v7.App.ActionBarActivity | MAMActionBarActivity |


### <a name="renamed-methods"></a>Métodos renomeados
Após derivar de um dos pontos de entrada com MAM, é seguro usar `Context` normalmente – por exemplo, iniciando as classes `Activity` e usando `PackageManager`.

Em muitos casos, um método disponível na classe Android foi marcado como final na classe de MAM de substituição. Nesse caso, a classe de MAM de substituição fornece um método nomeado da mesma forma (em geral, com o sufixo `MAM`), que deve ser substituído em vez disso. Por exemplo, ao derivar de `MAMActivity`, em vez de substituir `onCreate()` e chamar `super.onCreate()`, `Activity` deve substituir `onMAMCreate()` e chamar `super.onMAMCreate()`. O compilador Java deve impor as restrições finais para evitar a substituição acidental do método original em vez do MAM equivalente.

### <a name="pendingintent"></a>PendingIntent
Em vez de `PendingIntent.get*`, você deve usar o método `MAMPendingIntent.get*`. Depois disso, você pode usar o `PendingIntent` resultante, como de costume.

### <a name="manifest-replacements"></a>Substituições de manifesto
Observe que talvez seja necessário executar algumas das substituições de classe acima no manifesto, bem como no código Java. Nota especial:
* As referências do manifesto a `android.support.v4.content.FileProvider` devem ser substituídas por `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.


## <a name="sdk-permissions"></a>Permissões do SDK

O SDK de Aplicativo do Intune exige três [permissões de sistema do Android](https://developer.android.com/guide/topics/security/permissions.html) em aplicativos que o integram:

* `android.permission.GET_ACCOUNTS`  (solicitada em tempo de execução se necessário)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

A Biblioteca de Autenticação do Azure Active Directory ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) exige essas permissões para realizar a autenticação agenciada. Se essas permissões não forem concedidas ao aplicativo ou revogadas pelo usuário, os fluxos de autenticação que exigem o agente (o aplicativo de Portal da Empresa) serão desabilitados.

## <a name="logging"></a>Logging

O registro em log deve ser inicializado no início para obter o máximo dos dados registrados. O `Application.onMAMCreate()` normalmente é o melhor lugar para inicializar o registro em log.

Para receber logs do MAM em seu aplicativo, crie um [manipulador Java](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) e adicione-o ao `MAMLogHandlerWrapper`. Isso irá chamar o `publish()` no manipulador de aplicativo para cada mensagem de log.

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```



## <a name="enable-features-that-require-app-participation"></a>Habilitar recursos que exigem a participação do aplicativo

Há várias políticas de proteção de aplicativo que o SDK não pode implementar por conta própria. O aplicativo pode controlar seu comportamento para conquistar esses recursos usando várias APIs que podem ser encontradas na interface `AppPolicy` a seguir.

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}

```

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)` sempre retornará uma política de aplicativo não nula, mesmo que o dispositivo ou aplicativo não esteja sob uma política de gerenciamento do Intune.

### <a name="example-determine-if-pin-is-required-for-the-app"></a>Exemplo: determinar se o PIN é necessário para o aplicativo

Se o aplicativo tem sua própria experiência de usuário de PIN, convém desabilitá-lo se o administrador de TI tiver configurado o SDK para solicitar um PIN do aplicativo. Para determinar se o administrador de TI implantou a política PIN de aplicativo para esse aplicativo, para o usuário final atual, chame o método a seguir:

```java
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a>Exemplo: determinar o usuário principal do Intune

Além das APIs expostas na AppPolicy, o nome principal do usuário (**UPN**) também é exposto pela API `getPrimaryUser()` definida dentro da interface do `MAMUserInfo`. Para obter o UPN, chame o seguinte:

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

A definição completa da interface MAMUserInfo está disponível abaixo:

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a>Exemplo: determinar se é permitido salvar em dispositivo ou armazenamento em nuvem

Muitos aplicativos implementam recursos que permitem que o usuário final salve arquivos localmente ou em um serviço de armazenamento em nuvem. O SDK de Aplicativo do Azure permite que os administradores de TI protejam contra vazamento de dados aplicando as restrições de política da forma que considerarem adequada para sua organização.  Uma das políticas que o setor de TI pode controlar é se o usuário final pode salvar em um armazenamento de dados "pessoal" não gerenciado. Isso inclui salvar localmente, em cartões SD ou em serviços de backup de terceiros.

**A participação do aplicativo é necessária para habilitar o recurso.** Se o seu aplicativo permitir o salvamento em locais na nuvem ou pessoais diretamente do aplicativo, você deve implementar esse recurso para garantir que o administrador de TI possa controlar se é permitido salvar em um local. A API abaixo permite que o aplicativo saiba se é permitido salvar em um armazenamento pessoal de acordo com a atual política do administrador. O aplicativo pode, então, aplicar a política, pois ele está ciente de que o armazenamento pessoal de dados está disponível para o usuário final por meio do aplicativo.  

Para determinar se a política é aplicada, faça a chamada a seguir:

```java
MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

... onde `service` é um dos seguintes SaveLocations:


    * SaveLocation.ONEDRIVE_FOR_BUSINESS
    * SaveLocation.SHAREPOINT
    * SaveLocation.BOX
    * SaveLocation.DROPBOX
    * SaveLocation.GOOGLE_DRIVE
    * SaveLocation.LOCAL
    * SaveLocation.OTHER

O método anterior para determinar se a política de um usuário permitia que eles salvassem dados em vários locais era `getIsSaveToPersonalAllowed()` dentro da mesma classe **AppPolicy**. Essa função está agora **preterida** e não deve ser usada, a chamada a seguir é equivalente a `getIsSaveToPersonalAllowed()`:

```java

MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> Use `SaveLocation.OTHER` se o local em questão não estiver listado na enum **SaveLocations**.


## <a name="register-for-notifications-from-the-sdk"></a>Registrar-se para notificações do SDK

### <a name="overview"></a>Visão geral
O SDK de Aplicativo do Intune permite que seu aplicativo controle o comportamento de algumas políticas, como um apagamento remoto, quando elas são implantadas pelo administrador de TI. Quando um administrador de TI implanta tal política, o serviço do Intune envia uma notificação para o SDK.

O aplicativo deve ser registrado para receber notificações do SDK, criando uma `MAMNotificationReceiver` e registrando-a com `MAMNotificationReceiverRegistry`. Isso é feito fornecendo o receptor e o tipo de notificação desejada em `App.onCreate`, como mostra o exemplo a seguir:

```java
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
        .registerReceiver(
            new ToastNotificationReceiver(),
            MAMNotificationType.WIPE_USER_DATA);
    }
```

### <a name="mamnotificationreceiver"></a>MAMNotificationReceiver

A interface `MAMNotificationReceiver` apenas recebe notificações do serviço do Intune. Algumas notificações são manipuladas pelo SDK diretamente, enquanto outras exigem a participação do aplicativo. Um aplicativo **deve** retornar true ou false de uma notificação. Ele deve sempre retornar true, a menos que alguma ação que ele tentou executar como resultado da notificação falhe.

* Essa falha pode ser relatada ao serviço do Intune. Um exemplo de cenário a ser relatado é se o aplicativo falhar ao apagar dados do usuário após o administrador de TI iniciar um apagamento.

>[!NOTE]
> É seguro bloquear em `MAMNotificationReceiver.onReceive` porque seu retorno de chamada não está em execução no thread da interface do usuário.

A interface do `MAMNotificationReceiver` conforme definida no SDK está incluída abaixo:

```java
/**
 * The SDK is signaling that a MAM event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

### <a name="types-of-notifications"></a>Tipos de notificações

As seguintes notificações são enviadas para o aplicativo e algumas delas podem exigir a participação do aplicativo:

* **WIPE_USER_DATA**: essa notificação é enviada em uma classe `MAMUserNotification`. Quando a notificação é recebida, o aplicativo deve excluir todos os dados associados à identidade "corporativa" passada com o `MAMUserNotification`. Atualmente, essa notificação é enviada durante o cancelamento do registro do serviço do APP-WE. O nome principal do usuário geralmente é especificado durante o processo de registro. Se você se registrar para essa notificação, seu aplicativo deve garantir que todos os dados do usuário tenham sido excluídos. Se você não se registrar para ela, o comportamento de apagamento seletivo padrão será executado.

* **WIPE_USER_AUXILIARY_DATA**: os aplicativos podem se registrar para essa notificação se quiserem que o SDK de Aplicativo do Intune execute o comportamento de apagamento seletivo padrão, mas ainda desejarem remover alguns dados auxiliares quando o apagamento ocorrer.

* **REFRESH_POLICY**: essa notificação é enviada em uma `MAMUserNotification`. Quando a notificação é recebida, qualquer política do Intune armazenada em cache deve ser invalidada e atualizada. Normalmente, isso é tratado pelo SDK, porém deve ser tratado pelo aplicativo se a política for usada de qualquer maneira persistente.

* **MANAGEMENT_REMOVED**: essa notificação é enviada um `MAMUserNotification` e informa ao aplicativo que ele está prestes a não ser mais gerenciado. Depois de não ser gerenciado, ele não será mais capaz de ler arquivos criptografados, ler os dados criptografados com MAMDataProtectionManager, interagir com a área de transferência criptografada ou de outra forma participar do ecossistema de aplicativos gerenciados.


> [!NOTE]
> Um aplicativo nunca deve se registrar para as notificações `WIPE_USER_DATA` e `WIPE_USER_AUXILIARY_DATA` simultaneamente.


## <a name="configure-azure-active-directory-authentication-library-adal"></a>Configurar a ADAL (Biblioteca de Autenticação do Azure Active Directory)

Primeiro, leia as diretrizes de integração ADAL encontradas no [repositório ADAL no GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-android).

O SDK depende da [ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/) para [autenticação](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-scenarios/) e cenários de inicialização condicional, o que exige que os aplicativos sejam configurados com o [Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-whatis/). Os valores de configuração são comunicados para o SDK por meio dos metadados AndroidManifest.

Para configurar seu aplicativo e habilitar a autenticação adequada, adicione o seguinte ao nó de aplicativo no AndroidManifest.xml. Algumas dessas configurações somente são necessárias se seu aplicativo usar o ADAL para autenticação em geral. Nesse caso, você precisará dos valores específicos que seu aplicativo usa para se registrar com o AAD. Isso é feito para garantir que não seja solicitada a autenticação do usuário final duas vezes devido ao AAD reconhecer dois valores de registro separados: um do aplicativo e um do SDK.

```xml
<meta-data
    android:name="com.microsoft.intune.mam.aad.Authority"
    android:value="https://AAD authority/" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.ClientID"
    android:value="your-client-ID-GUID" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
    android:value="your-redirect-URI" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.SkipBroker"
    android:value="[true | false]" />
```

### <a name="adal-metadata"></a>Metadados de ADAL

* **Autoridade** é a autoridade AAD atual em uso. Se houver, será necessário usar seu próprio ambiente no qual as contas do AAD foram configuradas. Se esse valor estiver ausente, um padrão do Intune será usado.

* **ClientID** é a ClientID do AAD a ser usada. Você deve usar o ClientID do seu próprio aplicativo se ele estiver registrado com o AD do Azure. Se esse valor estiver ausente, um padrão do Intune será usado.

* **NonBrokerRedirectURI** é URI de redirecionamento do AAD para usar em casos sem agente. Se nenhum for especificado, um valor padrão `urn:ietf:wg:oauth:2.0:oob` será usado. Esse padrão é adequado para a maioria dos aplicativos.

* **SkipBroker** é usado no caso do ClientID não ter sido configurado para usar o URI de redirecionamento do agente. O valor padrão é "false".
    * Para aplicativos que **não integram o ADAL** e **não desejam participar de autenticação/SSO orientada para todo o dispositivo**, ele deve ser definido como "true". Quando esse valor for "true", o único URI de redirecionamento que será usado é NonBrokerRedirectURI.

    * Para aplicativos que dão suporte a agenciamento de SSO em todo o dispositivo, ele deve ser "false". Quando o valor for "false", o SDK selecionará um agente entre o resultado de [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) e NonBrokerRedirectURI, com base na disponibilidade do agente no sistema. Em geral, o agente estará disponível no aplicativo do Portal da Empresa ou aplicativo do Autenticador do Azure.

### <a name="common-adal-configurations"></a>Configurações comuns do ADAL

Veja seguir as maneiras comuns de um aplicativo ser configurado com a ADAL. Localize a configuração do aplicativo e defina os parâmetros de metadados do ADAL (explicados acima) para os valores necessários.

1. **O aplicativo não se integra ao ADAL:**

    | Parâmetro do ADAL necessário | Valor |
    |--|--|
    | Autoridade | Ambiente desejado no qual as contas do AAD foram configuradas |
    | SkipBroker | verdadeiro |

2. **O aplicativo integra o ADAL:**

    |Parâmetro do ADAL necessário| Valor |
    |--|--|
    | Autoridade | Ambiente desejado no qual as contas do AAD foram configuradas |
    | ClientID | O ClientID do aplicativo (gerado pelo AD do Azure, quando o aplicativo é registrado) |
    | NonBrokerRedirectURI | Um URI de redirecionamento válido para o aplicativo ou `urn:ietf:wg:oauth:2.0:oob` por padrão. <br><br> Configure o valor como um URI de redirecionamento aceitável para o ClientID do seu aplicativo.
    | SkipBroker | Falso |


3. **O aplicativo integra-se ao ADAL, mas não oferece suporte a autenticação/SSO orientada para todo o dispositivo:**

    |Parâmetro do ADAL necessário| Valor |
    |--|--|
    | Autoridade | Ambiente desejado no qual as contas do AAD foram configuradas |
    | ClientID | O ClientID do aplicativo (gerado pelo AD do Azure, quando o aplicativo é registrado) |
    | NonBrokerRedirectURI | Um URI de redirecionamento válido para o aplicativo ou `urn:ietf:wg:oauth:2.0:oob` por padrão. <br><br> Configure o valor como um URI de redirecionamento aceitável para o ClientID do seu aplicativo.
    | SkipBroker | **True** |

## <a name="app-protection-policy-without-device-enrollment"></a>Política de proteção do aplicativo sem registro de dispositivo

### <a name="overview"></a>Visão geral
Política de proteção de aplicativo do Intune sem registro do dispositivo, também conhecido como APP-WE ou MAM-WE, permite que os aplicativos sejam gerenciados pelo Intune sem a necessidade de o dispositivo ser registrado no MDM do Intune. O aplicativo-funciona com ou sem registro do dispositivo. O Portal da Empresa ainda é necessário para ser instalado no dispositivo, mas o usuário não precisa entrar no Portal da Empresa e registrar o dispositivo.

> [!NOTE]
> Todos os aplicativos são necessários para dar suporte à política de proteção do aplicativo sem registro de dispositivo.

### <a name="workflow"></a>Fluxo de trabalho

Quando um aplicativo cria uma nova conta de usuário, ele deve registrar a conta para gerenciamento com o SDK de aplicativo do Intune. O SDK tratará os detalhes do registro do aplicativo no serviço APP-WE; se necessário, ele tentará novamente outros registros em intervalos de tempo apropriados, se houver falhas.

O aplicativo também pode consultar o SDK de aplicativo do Intune para o status de um usuário registrado para determinar se o usuário deve ser impedido de acessar o conteúdo corporativo. Várias contas podem ser registradas para gerenciamento, mas, no momento, apenas uma conta pode ser registrada ativamente com o serviço APP-WE de cada vez. Isso significa que apenas uma conta no aplicativo pode receber a política de proteção do aplicativo de cada vez.

O aplicativo deve fornecer um retorno de chamada para adquirir o token de acesso apropriado do Azure Active Directory Authentication Library (ADAL) em nome do SDK. Supõe-se que o aplicativo já use ADAL para autenticação do usuário e para adquirir os seus próprios tokens de acesso.

Quando o aplicativo remove completamente uma conta, ele deverá cancelar o registro dessa conta para indicar que o aplicativo não deve mais aplicar a política para esse usuário. Se o usuário tiver sido inscrito no serviço de MAM, o usuário terá o registro cancelado e o aplicativo será apagado.


### <a name="overview-of-app-requirements"></a>Visão geral dos requisitos de aplicativo

Para implementar a integração APP-WE, seu aplicativo deverá registrar a conta de usuário com o SDK do MAM:

1. O aplicativo _deve_ implementar e registrar uma instância da interface do `MAMServiceAuthenticationCallback`. A instância de retorno de chamada deve ser registrada o mais cedo possível no ciclo de vida do aplicativo (normalmente no método `onMAMCreate()` da classe de aplicativo).

2. Quando uma conta de usuário é criada e o usuário entra com êxito com o ADAL, o aplicativo _deve_ chamar o `registerAccountForMAM()`.

3. Quando uma conta de usuário tiver sido completamente removida, o aplicativo deverá chamar o `unregisterAccountForMAM()` para remover a conta do gerenciamento do Intune.

    > [!NOTE]
    > Se um usuário sair do aplicativo temporariamente, o aplicativo não precisará chamar o `unregisterAccountForMAM()`. A chamada pode iniciar um apagamento para remover completamente os dados corporativos para o usuário.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager

Todas as APIs de registro e autenticação necessárias podem ser encontradas na interface do `MAMEnrollmentManager`. Uma referência ao `MAMEnrollmentManager` pode ser obtida da seguinte maneira:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr

```

A instância do `MAMEnrollmentManager` retornada tem a garantia de não ser nula. Os métodos de API enquadram-se em duas categorias: **autenticação** e **registro de conta**.

> [!NOTE]
> O `MAMEnrollmentManager` contém alguns métodos de API que serão preteridos em breve. Para maior clareza, somente os métodos relevantes e os códigos de resultado são mostrados no bloco de código abaixo.

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a>Autenticação de conta

Esta seção descreve os métodos de API de autenticação no `MAMEnrollmentManager` e como usá-los.

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. O aplicativo deve implementar a interface do `MAMServiceAuthenticationCallback` para permitir que o SDK solicite um token do ADAL para o usuário e a ID de recurso determinados. A instância de retorno de chamada deve ser fornecida para o `MAMEnrollmentManager` chamando seu método `registerAuthenticationCallback()`. Um token pode ser necessário muito cedo no ciclo de vida do aplicativo para as tentativas de registro ou check-ins de atualização periódica da política de proteção de aplicativo; portanto, é o lugar ideal para registrar o retorno de chamada no método `onMAMCreate()` da subclasse `MAMApplication` do aplicativo.

2. O método `acquireToken()` deve adquirir o token de acesso para a ID de recurso solicitada para o usuário especificado. Se ele não puder adquirir o token solicitado, deverá retornar nulo.

3. Caso o aplicativo seja capaz de fornecer um token quando o SDK chamar o `acquireToken()` – por exemplo, se houver falha de autenticação silenciosa e for um momento inconveniente para mostrar uma interface do usuário – o aplicativo poderá fornecer um token em um momento posterior chamando o método `updateToken()`. O mesmo UPN, ID do AAD e ID de recursos que foram solicitados pela chamada anterior a `acquireToken()` devem ser passadas para o `updateToken()`, juntamente com o token que finalmente foi adquirido. O aplicativo deverá chamar esse método o mais rápido possível após retornar nulo do retorno de chamada fornecido.

> [!NOTE]
> O SDK chamará `acquireToken()` periodicamente para obter o token, de modo que chamar `updateToken()` não seja estritamente necessário. No entanto, isso é recomendável porque pode ajudar as inscrições e os check-ins de política de proteção de aplicativo serem concluídos de maneira oportuna.


### <a name="account-registration"></a>Registro de conta

Esta seção descreve os métodos de API de registro de conta no `MAMEnrollmentManager` e como usá-los.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. Para registrar uma conta para gerenciamento, o aplicativo deverá chamar `registerAccountForMAM()`. Uma conta de usuário é identificada por seu UPN e sua ID de usuário do AAD. A ID do locatário também é necessária para associar os dados de registro ao locatário do AAD do usuário. O SDK pode tentar registrar o aplicativo para o usuário especificado no serviço do MAM; se o registro falhar, ele tentará registrar de novo periodicamente até que a conta tenha o registro cancelado. Normalmente, o período de repetição será de 12-24 horas. O SDK fornece o status de tentativas de registro de forma assíncrona por meio de notificações.

2. Como a autenticação do AAD é necessária, o melhor momento para registrar a conta do usuário é depois que o usuário tiver entrado no aplicativo e tiver sido autenticado com êxito usando o ADAL.
    * A ID do AAD do usuário e a ID do locatário são retornadas da chamada de autenticação do ADAL como parte do objeto [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android). A ID do locatário é proveniente do método `AuthenticationResult.getTenantID()`.
    * As informações sobre o usuário encontram-se em um subobjeto do tipo `UserInfo` que vem do `AuthenticationResult.getUserInfo()` e a ID do usuário do AAD é recuperada do objeto chamando `UserInfo.getUserId()`.

3. Para cancelar o registro de uma conta do gerenciamento do Intune, o aplicativo deverá chamar `unregisterAccountForMAM()`. Se a conta tiver sido registrada com êxito e for gerenciada, o SDK cancelará o registro da conta e apagará seus dados. As tentativas periódicas de registro para a conta serão interrompidas. O SDK fornece o status da solicitação de cancelamento de registro de forma assíncrona por meio de notificações.

### <a name="important-implementation-notes"></a>Notas importantes da implementação

#### <a name="authentication"></a>Autenticação

* Quando o aplicativo chamar `registerAccountForMAM()`, ele poderá receber um retorno de chamada em sua interface do `MAMServiceAuthenticationCallback` logo em seguida em um thread diferente. Idealmente, o aplicativo adquiriu seu próprio token do ADAL antes de registrar a conta para agilizar a aquisição do **token MAMService**. Se o aplicativo retornar um token válido do retorno de chamada, o registro continuará e o aplicativo obterá o resultado final por meio de uma notificação.

* Se o aplicativo não retornar um token válido do AAD, o resultado final da tentativa de registro será `AUTHENTICATION_NEEDED`. Se o aplicativo recebe esse resultado por meio de notificação, ele poderá agilizar o processo de registro adquirindo o **token MAMService** e chamar o método `updateToken()` para iniciar o processo de registro novamente. Isso _não_ é um requisito sólido; no entanto, como o SDK tenta realizar o registro periodicamente, ele invoca o retorno de chamada para adquirir o token.

* O `MAMServiceAuthenticationCallback` registrado do aplicativo também será chamado para adquirir um token para check-ins de atualização periódica da política de proteção de aplicativo. Se o aplicativo não for capaz de fornecer um token quando solicitado, ele não receberá uma notificação, mas deverá tentar adquirir um token e chamar o `updateToken()` no próximo horário conveniente para agilizar o processo de check-in. Se não for fornecido um token, o retorno de chamada ainda será chamado na próxima tentativa de check-in.

#### <a name="registration"></a>Registro

* Para sua conveniência, os métodos de registro são imutáveis; por exemplo, `registerAccountForMAM()` registrará somente uma conta e tentará registrar o aplicativo se a conta não estiver registrada, e `unregisterAccountForMAM()` apenas cancelará uma conta se ela estiver registrada. As chamadas subsequentes são não operacionais; portanto, não há prejuízo em chamar esses métodos mais de uma vez. Além disso, a correspondência entre chamadas para esses métodos e as notificações de resultados não são garantidas: por exemplo, se `registerAccountForMAM` for chamado para uma identidade que já esteja registrada, a notificação poderá não ser enviada novamente para essa identidade. É possível que as notificações sejam enviadas sem corresponderem a todas as chamadas para esses métodos, porque o SDK pode periodicamente tentar inscrições em segundo plano e os cancelamentos de registro podem ser disparados por solicitações de apagamento recebidas do serviço Intune.

* Os métodos de registro podem ser chamados para qualquer número de identidades diferentes, mas atualmente apenas uma conta de usuário pode ser registrada com êxito. Se várias contas de usuário que são licenciadas para o Intune e afetadas pela política de proteção do aplicativo forem registradas ao mesmo tempo ou quase simultaneamente, não há nenhuma garantia de qual ganhará a corrida.

* Por fim, você pode consultar o `MAMEnrollmentManager` para ver se uma conta específica está registrada e para obter seu status atual usando o método `getRegisteredAccountStatus`. Se a conta fornecida não estiver registrada, esse método retornará **nulo**. Se a conta estiver registrada, esse método retornará o status da conta como um dos membros da enumeração `MAMEnrollmentManager.Result`.

### <a name="result-and-status-codes"></a>Resultado e códigos de status

Quando uma conta é registrada pela primeira vez, ela começa no estado `PENDING`, indicando que a tentativa inicial de registro de serviço do MAM está incompleta. Após a tentativa de registro terminar, uma notificação será enviada com um dos códigos de resultado na tabela a seguir. Além disso, o método `getRegisteredAccountStatus()` retornará o status da conta para que o aplicativo sempre possa determinar se o acesso ao conteúdo corporativo é bloqueado para esse usuário. Se a tentativa de registro falhar, o status da conta poderá mudar ao longo do tempo como o registro de novas tentativas do SDK no plano de fundo.

|Código de Resultado | Explicação |
| -- | -- |
|AUTHORIZATION_NEEDED | Esse resultado indica que um token não foi fornecido pela instância `MAMServiceAuthenticationCallback` registrada do aplicativo ou o token fornecido era inválido.  O aplicativo deve adquirir um token válido e chamar `updateToken()` se for possível. |
| NOT_LICENSED | O usuário não está licenciado para o Intune ou a tentativa de contatar o serviço MAM do Intune falhou.  O aplicativo deve continuar em um estado não gerenciado (normal) e o usuário não deve estar bloqueado.  Os registros serão repetidos periodicamente caso o usuário se torne licenciado no futuro. |
| ENROLLMENT_SUCCEEDED | A tentativa de registro teve êxito ou o usuário já está registrado.  No caso de um registro bem-sucedido, uma notificação de atualização de política será enviada antes dessa notificação.  O acesso a dados corporativos deve ser permitido. |
| ENROLLMENT_FAILED | Falha na tentativa de registro.  Detalhes adicionais podem ser encontrados nos logs do dispositivo.  O aplicativo não deve permitir o acesso corporativo nesse estado, porque anteriormente foi determinado que o usuário estava licenciado para o Intune.|
| WRONG_USER | Somente um usuário por dispositivo pode registrar um aplicativo com o serviço do MAM.  Para registrar com êxito como um usuário diferente, todos os aplicativos registrados deverão ter o registro cancelado primeiro.  Caso contrário, esse aplicativo deverá ser registrado como o usuário principal.  Essa verificação ocorre após a verificação da licença, então o usuário deve ser impedido de acessar dados corporativos até que o aplicativo seja registrado com êxito.|
| UNENROLLMENT_SUCCEEDED | O cancelamento do registro foi realizado com sucesso.|
| UNENROLLMENT_FAILED | Houve falha na solicitação de cancelamento do registro.  Detalhes adicionais podem ser encontrados nos logs do dispositivo. |
| PENDING | A tentativa de registro inicial para o usuário está em andamento.  O aplicativo pode bloquear o acesso a dados corporativos até que o resultado do registro seja conhecido, mas não é obrigado a fazê-lo. |
| COMPANY_PORTAL_REQUIRED | O usuário é licenciado para o Intune, mas o aplicativo não pode ser registrado até que o aplicativo do Portal da Empresa esteja instalado no dispositivo. O SDK do aplicativo do Intune tenta bloquear o acesso ao aplicativo para determinado usuário e o direciona para instalar o aplicativo do Portal da Empresa (veja abaixo para obter detalhes). |


### <a name="company-portal-requirement-prompt-override-optional"></a>Substituição do prompt de requisito do Portal da Empresa (opcional)

Se o resultado de `COMPANY_PORTAL_REQUIRED` for recebido, o SDK bloqueará o uso de atividades que usam a identidade para a qual o registro foi solicitado. Em vez disso, o SDK fará essas atividades exibirem um prompt para baixar o Portal da Empresa. Se você quiser impedir esse comportamento em seu aplicativo, as atividades poderão implementar o `MAMActivity.onMAMCompanyPortalRequired`.

Esse método é chamado antes que o SDK exiba sua interface de usuário de bloqueio padrão. Se o aplicativo alterar a identidade da atividade ou cancelar o registro do usuário que tentou registrar, o SDK não bloqueará a atividade. Nessa situação, depende do aplicativo evitar o vazamento de dados corporativos.

### <a name="notifications"></a>Notificações

Um novo tipo de `MAMNotification` foi adicionado para informar ao aplicativo que a solicitação de registro foi concluída.  O `MAMEnrollmentNotification` será recebido por meio da interface do `MAMNotificationReceiver` conforme descrito na seção [Registrar-se para notificações do SDK](#register-for-notifications-from-the-sdk).

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}

```

O método `getEnrollmentResult()` retorna o resultado da solicitação de registro.  Como o `MAMEnrollmentNotification` estende o `MAMUserNotification`, a identidade do usuário para o qual o registro foi tentado também está disponível. O aplicativo deve implementar a interface do `MAMNotificationReceiver` para receber essas notificações que estão detalhadas na seção [Registrar-se para notificações do SDK](#Register-for-notifications-from-the-SDK).

O status da conta de usuário registrado poderá ser alterado quando um registro de notificação for recebido, mas não será alterada em alguns casos (por exemplo, se a notificação do `AUTHORIZATION_NEEDED` for recebida após um resultado mais informativo como `WRONG_USER`, o resultado mais informativo será mantido como o status da conta)


## <a name="protecting-backup-data"></a>Proteção de dados de backup

A partir do Android Marshmallow (API 23), o Android tem duas formas para um aplicativo fazer backup de seus dados. Cada opção está disponível para seu aplicativo e requer etapas diferentes para garantir que a proteção de dados do Intune seja implementada corretamente. Examine a tabela abaixo para ver as ações correspondentes necessárias para o comportamento correto de proteção de dados.  Leia mais sobre os métodos de backup no [Guia da API do Android](http://developer.android.com/guide/topics/data/backup.html).

### <a name="auto-backup-for-apps"></a>Backup automático de aplicativos

O Android começou a oferecer [backups completos automáticos](https://developer.android.com/guide/topics/data/autobackup.html) para o Google Drive para aplicativos em dispositivos Android Marshmallow, independentemente da API de destino do aplicativo. Em seu AndroidManifest.xml, se você definir explicitamente `android:allowBackup` como **false**, seu aplicativo nunca será enfileirado para backups pelo Android e os dados "corporativos" permanecerão no aplicativo. Nesse caso, nenhuma ação adicional é necessária.

No entanto, por padrão, o atributo `android:allowBackup` é definido como true, mesmo que `android:allowBackup` não esteja especificado no arquivo de manifesto. Isso significa que todos os dados do aplicativo são copiados automaticamente para a conta do Google Drive do usuário, um comportamento padrão que representa um **risco de vazamento de dados**. Portanto, o SDK requer as alterações descritas na tabela a seguir para garantir que a proteção de dados seja aplicada.  É importante seguir as diretrizes abaixo para proteger os dados do cliente corretamente se você quiser que seu aplicativo seja executado em dispositivos Android Marshmallow.  

O Intune permite que você utilize todos os [recursos de Backup Automático](https://developer.android.com/guide/topics/data/autobackup.html) disponíveis no Android, incluindo a capacidade de definir regras personalizadas no XML, mas você precisa seguir as etapas abaixo para proteger seus dados:

1. Se seu aplicativo **não** usar seu próprio BackupAgent, use o MAMBackupAgent padrão para permitir backups completos automáticos que estejam em conformidade com a política do Intune. Se você fizer isso, poderá ignorar o atributo do manifesto `android:fullBackupOnly`, pois ele não será aplicável para nosso agente de backup. Coloque o seguinte no manifesto do aplicativo:

    ```xml
android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```

2. **[Opcional]**  Se você tiver implementado um BackupAgent personalizado opcional, precisará usar MAMBackupAgent ou MAMBackupAgentHelper. Confira as seções a seguir. Use o **MAMDefaultFullBackupAgent** do Intune (descrito na etapa 1), que fornece backup fácil no Android M e superior.

3. Quando decidir qual tipo de backup completo seu aplicativo deve receber (filtrado, não filtrado ou nenhum), você precisará definir o atributo `android:fullBackupContent` como true, false ou um recurso XML em seu aplicativo.

4. Em seguida, você _**deve**_ copiar tudo o que colocar no `android:fullBackupContent` em uma marca de metadados chamada `com.microsoft.intune.mam.FullBackupContent` no manifesto.

    **Exemplo 1**: se você quiser que seu aplicativo tenha backups completos sem exclusões, defina o atributo `android:fullBackupContent` e a marca de metadados `com.microsoft.intune.mam.FullBackupContent` como **true**:

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    **Exemplo 2**: se você quiser que seu aplicativo use seu BackupAgent personalizado e recuse backups automáticos completos compatíveis com a política do Intune, defina o atributo e a marca de metadados como **false**:

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    **Exemplos 3**: se você quiser que seu aplicativo tenha backups completos de acordo com suas regras personalizadas definidas em um arquivo XML, defina o atributo e a marca de metadados como o mesmo recurso de XML:

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <a name="keyvalue-backup"></a>Backups de chave/valor

A opção [Backup de chave/valor](https://developer.android.com/guide/topics/data/keyvaluebackup.html) está disponível para todas as APIs acima de 8 e carrega dados do aplicativo para o [Serviço de Backup do Android](https://developer.android.com/google/backup/index.html). A quantidade de dados por usuário de seu aplicativo é limitada a 5MB. Se você usar o Backup de chave/valor, deverá usar um **BackupAgentHelper** ou **BackupAgent**.

### <a name="backupagenthelper"></a>BackupAgentHelper

O BackupAgentHelper é mais simples de implementar do que o BackupAgent em termos de funcionalidade nativa do Android e integração de MAM do Intune. O BackupAgentHelper permite que o desenvolvedor registre arquivos inteiros e preferências compartilhadas com um **FileBackupHelper** e **SharedPreferencesBackupHelper** (respectivamente), que são adicionados ao BackupAgentHelper no momento da criação. Siga as etapas abaixo para usar um BackupAgentHelper com o MAM do Intune:

1. Para utilizar o backup de várias identidades com um BackupAgentHelper, siga o guia do Android para [Estendendo o BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper).

2. Faça a sua classe estender o equivalente do MAM a BackupAgentHelper, FileBackupHelper e SharedPreferencesBackupHelper.

|Classe do Android | Equivalente do MAM |
|--|--|
|BackupAgentHelper |MAMBackupAgentHelper |
|FileBackupHelper | MAMFileBackupHelper
|SharedPreferencesBackupHelper| MAMSharedPreferencesBackupHelper|

As diretrizes a seguir levam a um backup e uma restauração bem-sucedidos de várias identidades.

### <a name="backupagent"></a>BackupAgent

O BackupAgent permite que você seja muito mais explícito sobre de quais dados é feito backup. Como o desenvolvedor é bastante responsável pela implementação, há mais etapas necessárias para garantir a proteção de dados apropriada do Intune. Uma vez que a maioria do trabalho é passado para você, o desenvolvedor, integração do Intune é um pouco mais envolvida.

**Integrar o MAM:**

1. Leia atentamente o guia do Android para [Backup de chave/valor](https://developer.android.com/guide/topics/data/keyvaluebackup.html) e especificamente [Estendendo o BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) para garantir que a sua implementação do BackupAgent siga as diretrizes do Android.

2. Faça sua classe estender o `MAMBackupAgent`.

**Backup de várias identidades:**

1. Antes de iniciar o backup, verifique se os arquivos ou buffers de dados dos quais você planeja fazer backup estão realmente **permitidos pelo administrador de TI para terem o backup feito** em cenários de várias identidades. Nós fornecemos a função `isBackupAllowed` em `MAMFileProtectionManager` e `MAMDataProtectionManager` para determinar isso. Se o buffer de dados ou arquivo não tiver permissão para backup, você não deverá continuar incluindo-o em seu backup.

2. Em algum momento durante o backup, se desejar que as identidades dos arquivos verificados na etapa 1 façam backup, você deverá chamar `backupMAMFileIdentity(BackupDataOutput data, File … files)` com os arquivos dos quais planeja extrair dados. Isso criará automaticamente novas entidades de backup e as gravará em `BackupDataOutput` para você. Essas entidades serão consumidas automaticamente após a restauração.

**Restauração de várias identidades:**

O guia de Backup de dados especifica um algoritmo geral para restaurar os dados do aplicativo e fornece um exemplo de código na seção [Estendendo o BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent). Para ter uma restauração bem-sucedida de várias identidades, você deverá seguir a estrutura geral fornecida neste exemplo de código com atenção especial para o seguinte:

1.    Você deve utilizar um loop `while(data.readNextHeader())`* para percorrer as entidades de backup.

2.    Você deve chamar `data.skipEntityData()`* se `data.getKey()`* não coincidir com a chave que você escreveu em `onBackup`. Sem realizar esta etapa, suas restaurações poderão não obter êxito.

3.    Evite retornar enquanto estiver consumindo entidades de backup na construção `while(data.readNextHeader())`*, porque as entidades que escrevemos automaticamente serão perdidas.

* Onde `data` é o nome da variável local para o **BackupDataInput** que é passado para o seu aplicativo após a restauração.

## <a name="multi-identity-optional"></a>Várias identidades (opcional)

### <a name="overview"></a>Visão geral
Por padrão, o SDK de Aplicativo do Intune aplicará a política ao aplicativo como um todo. Várias identidades é um recurso de proteção opcional do aplicativo do Intune que pode ser habilitado para permitir que a política seja aplicada por identidade. Ele requer uma participação significativamente maior do aplicativo do que outros recursos de proteção do aplicativo.

O aplicativo _precisa_ informar o SDK quando pretender alterar a identidade ativa. O SDK também notificará o aplicativo quando uma alteração de identidade for necessária. Depois que o usuário registrar o dispositivo ou o aplicativo, o SDK registrará essa identidade e a considerará a identidade gerenciada primária do Intune. Outros usuários no aplicativo serão tratados como não gerenciados, com configurações de política irrestritas.

> [!NOTE]
> Atualmente, há suporte para apenas uma identidade gerenciada do Intune por dispositivo.

Observe que uma identidade é definida simplesmente como uma cadeia de caracteres. As identidades **não diferenciam maiúsculas de minúsculas** e as solicitações de identidade ao SDK podem não retornar o mesmo esquema de maiúsculas e minúsculas usado originalmente ao definir a identidade.


### <a name="enabling-multi-identity"></a>Habilitando várias identidades

Por padrão, considera-se que todos os aplicativos são aplicativos de identidade única. Você pode declarar um aplicativo para reconhecer várias identidades colocando os seguintes metadados no arquivo AndroidManifest.xml.

```xml
  <meta-data
      android:name="com.microsoft.intune.mam.MAMMultiIdentity"
      android:value="true" />
```

### <a name="setting-the-identity"></a>Definindo a identidade

Os desenvolvedores podem definir a identidade do usuário aplicativo nos níveis a seguir em ordem de prioridade descendente:

  1. Nível de thread
  2. Nível de contexto (geralmente, a Atividade)
  3. Nível de processo

Uma identidade definida no nível do thread substitui uma identidade definida no nível do Contexto, que substitui uma identidade definida no nível do processo. Uma identidade definida em um contexto é usada apenas em operações de E/S de arquivo de cenários associados apropriados, por exemplo, não tem um contexto associado. Os seguintes métodos no `MAMPolicyManager` podem ser usados para definir a identidade e recuperar os valores de identidade definidos anteriormente.

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

  /**
   * Get the currently applicable app policy. Same as
   * MAMComponents.get(AppPolicy.class). This method does
   * not take the context identity into account.
   */
  public static AppPolicy getPolicy();

  /**
   * Get the currently applicable app policy, taking the context
   * identity into account.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);

  ```

>[!NOTE]
> Você pode limpar a identidade do aplicativo definido-a como nula.
>
> A cadeia de caracteres vazia pode ser usada como uma identidade que nunca terá política de proteção de aplicativo.

#### <a name="results"></a>Resultados
Todos os métodos usados para definir a identidade relatam os valores de resultado via `MAMIdentitySwitchResult`. Há quatro valores que podem ser retornados:

| Retornar valor | Cenário |
|--|--|
| SUCCEEDED | A alteração de identidade foi bem-sucedida. |
| NOT_ALLOWED | Não é permitido alterar a identidade. <br><br>Isso ocorrerá se for feita uma tentativa de mudar para outro usuário gerenciado que pertence à mesma organização que o usuário registrado. Ocorrerá também se for feita uma tentativa de definir a identidade da interface do usuário (Contexto) quando uma identidade diferente estiver definida no thread atual. |
| CANCELLED | O usuário cancelou a alteração de identidade, normalmente pressionando o botão Voltar em um PIN ou prompt de autenticação. |
| FAILED | Ocorreu uma falha na alteração da identidade por um motivo não especificado.|


No caso da definição de uma identidade de Contexto, o resultado é relatado de forma assíncrona. Se o Contexto for uma Atividade, o SDK não saberá se a alteração de identidade foi bem-sucedida até que a inicialização condicional seja realizada, o que pode exigir que o usuário insira um PIN ou suas credenciais corporativas. Espera-se que o aplicativo implemente um `MAMSetUIIdentityCallback` para receber esse resultado, você pode passar null para esse parâmetro.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

Também é possível definir a identidade de uma atividade diretamente por meio de um método em `MAMActivity`, em vez de chamar `MAMPolicyManager.setUIPolicyIdentity`. Use o seguinte método para fazer isso:

```java
     public final void switchMAMIdentity(final String newIdentity);
```

Você também pode substituir um método no `MAMActivity` se quiser que o aplicativo seja notificado do resultado das tentativas de alterar a identidade da atividade.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

>[!NOTE]
> Alterar a identidade pode exigir a recriação da atividade. Nesse caso, o retorno de chamada `onSwitchMAMIdentityComplete` será entregue para a nova instância da atividade.


### <a name="implicit-identity-changes"></a>Alterações de identidade implícitas

Além da capacidade do aplicativo de definir a identidade, um thread ou a identidade de um contexto pode mudar com base na entrada de dados de outro aplicativo orientado para Intune que tenha política de proteção de aplicativo.

#### <a name="examples"></a>Exemplos

  1. Se uma atividade for iniciada de uma `Intent` enviada por outro aplicativo com MAM, a identidade da atividade será definida com base na identidade em vigor no outro aplicativo no momento em que a `Intent` foi enviada.

  2.  Para serviços, a identidade do thread será definida da mesma forma pela duração de uma chamada `onStart` ou `onBind`. Chamadas para `Binder` retornadas de `onBind` também definirão temporariamente a identidade do thread.

  3. De forma semelhante, chamadas para um `ContentProvider` definirão a identidade do thread no período de sua duração.


  Além disso, a interação do usuário com uma atividade pode causar uma mudança de identidade implícita.

  **Exemplo:** se um usuário cancelar após um prompt de autorização durante o `Resume`, ocorrerá uma mudança implícita para uma identidade vazia.

  O aplicativo tem uma oportunidade de ser informado dessas alterações e, se precisar, pode proibi-las. `MAMService` e `MAMContentProvider` expõem o seguinte método que as subclasses podem substituir:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
      final AppIdentitySwitchResultCallback callback);
  ```

  Na classe `MAMActivity`, um parâmetro adicional está presente no método:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
      final AppIdentitySwitchReason reason,
      final AppIdentitySwitchResultCallback callback);
  ```

  * O `AppIdentitySwitchReason` captura a fonte da mudança implícita e pode aceitar os valores `CREATE`, `RESUME_CANCELLED` e `NEW_INTENT`.  O motivo `RESUME_CANCELLED` é usado quando a atividade é retomada e faz com que o PIN, a autenticação ou outra interface do usuário de conformidade seja exibida; o usuário tenta cancelar para sair dessa interface do usuário, normalmente usando o uso do botão Voltar.


  * `AppIdentitySwitchResultCallback` é o seguinte:

      ```java
      public interface AppIdentitySwitchResultCallback {
          /**
           * @param result
           *            whether the identity switch can proceed.
           */
          void reportIdentitySwitchResult(AppIdentitySwitchResult result);
      }
      ```

      Onde ```AppIdentitySwitchResult``` é ÊXITO ou FALHA.

O método `onMAMIdentitySwitchRequired` é chamado para todas as mudanças de identidade implícitas, exceto por aquelas feitas por meio de um Associador retornado de `MAMService.onMAMBind`. As implementações padrão do `onMAMIdentitySwitchRequired` imediatamente chamam:

*  `reportIdentitySwitchResult(FAILURE)` quando o motivo é RESUME_CANCELLED.

*  `reportIdentitySwitchResult(SUCCESS)` em todos os outros casos.

  Não é esperado que a maioria dos aplicativos precisem bloquear ou adiar uma mudança de identidade de maneira diferente, mas se um aplicativo precisar fazer isso, os seguintes pontos devem ser considerados:

  * Se uma mudança de identidade estiver bloqueada, o resultado será o mesmo, como se as configurações de compartilhamento de `Receive` tivessem proibido a entrada de dados.

  * Se um serviço estiver em execução no thread principal, `reportIdentitySwitchResult` **deve** ser chamado de forma síncrona ou o thread da interface do usuário falhará.

  * Para criação de **Atividade**, `onMAMIdentitySwitchRequired` será chamado antes de `onMAMCreate`. Se o aplicativo precisar mostrar a interface do usuário para determinar se deve permitir a mudança de identidade, a interface do usuário deverá ser exibida usando uma atividade *diferente*.

  * Em uma **Atividade**, quando for solicitada uma mudança para a identidade vazia com o motivo igual a RESUME_CANCELLED, o aplicativo deverá modificar a atividade retomada para exibir dados consistentes com essa mudança de identidade.  Se isso não for possível, o aplicativo deverá recusar a mudança e o usuário será solicitado novamente a obedecer a política para retomar a identidade (por exemplo, recebendo a tela de entrada de PIN do aplicativo).

    > [!NOTE]
    > Um aplicativo com várias identidades sempre receberá dados de entrada de aplicativos gerenciados e não gerenciados. É responsabilidade do aplicativo tratar dados de identidades gerenciadas de maneira gerenciada.

  Se uma identidade solicitada for gerenciada (use `MAMPolicyManager.getIsIdentityManaged` para verificar), mas o aplicativo não puder usar a conta (por exemplo, porque contas, como contas de email, devem ser configuradas no aplicativo primeiro), a chave de identidade deverá ser recusada.



  ### <a name="file-protection"></a>Proteção de arquivo

  Cada arquivo tem uma identidade associada no momento da criação, com base na identidade do thread e do processo. Essa identidade será usada para a criptografia de arquivos e o apagamento seletivo. Somente arquivos cuja identidade é gerenciada e tem uma política que exige criptografia serão criptografados. A funcionalidade de apagamento seletivo padrão do SDK apagará apenas arquivos associados à identidade gerenciada para a qual um apagamento foi solicitado. O aplicativo pode consultar ou alterar a identidade de um arquivo usando a classe `MAMFileProtectionManager`.

  ```java
    public final class MAMFileProtectionManager {

        /**
         * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
         * future protection changes.
         *
         * @param identity
         *            Identity to set.
         * @param file
         *            File to protect.
         * @throws IOException
         *             If the file cannot be changed.
         */
        public static void protect(final File file, final String identity) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File or directory to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

    }

    public interface MAMFileProtectionInfo {
        String getIdentity();
    }

  ```

A marcação de identidade do arquivo é sensível ao modo offline. Os aspectos a seguir devem ser levados em conta:

  * Se o Portal da Empresa não estiver instalado, os arquivos não poderão ser marcados segundo a identidade.

  * Se o Portal da Empresa estiver instalado, mas o aplicativo não tiver a política do MAM do Intune, os arquivos não poderão ser marcados segundo a identidade de forma confiável.

  * Quando a marcação de identidade do arquivo se torna disponível, todos os arquivos criados anteriormente são tratados como pessoais/não gerenciados (pertencentes à identidade de cadeia de caracteres vazia), a menos que o aplicativo tenha sido instalado anteriormente como um aplicativo gerenciado de identidade única. Nesse caso, eles serão tratados como pertencentes ao usuário registrado.

### <a name="directory-protection"></a>Proteção de diretório

Os diretórios podem ser protegidos com o mesmo método `protect` usado para proteger os arquivos. Observe que a proteção de diretório é aplicada recursivamente para todos os arquivos e subdiretórios contidos no diretório e para novos arquivos criados dentro do diretório. Como a proteção de diretório é aplicada recursivamente, a chamada do `protect` pode levar algum tempo para ser concluída em diretórios muito grandes. Por esse motivo, os aplicativos que aplicam proteção a um diretório que contém um grande número de arquivos podem desejar executar o `protect` de maneira assíncrona em um thread em segundo plano.

### <a name="data-protection"></a>Proteção de dados

Não é possível marcar um arquivo como pertencente a várias identidades. Aplicativos que precisam armazenar dados pertencentes a diferentes usuários no mesmo arquivo podem fazer isso manualmente usando os recursos fornecidos pelo `MAMDataProtectionManager`. Isso permite que o aplicativo criptografe dados e os vincule a um usuário específico. Os dados criptografados são adequados para armazenamento em disco em um arquivo. Você pode consultar os dados associados à identidade e os dados podem ser descriptografados mais tarde.

Os aplicativos que usam o `MAMDataProtectionManager` devem implementar um receptor para a notificação `MANAGEMENT_REMOVED`. Após essa notificação ser concluída, os buffers que foram protegidos por meio dessa classe não serão mais legíveis se a criptografia de arquivo tiver sido habilitada quando os buffers estavam protegidos. Um aplicativo pode corrigir essa situação chamando MAMDataProtectionManager.unprotect em todos os buffers durante essa notificação. Observe que também é seguro chamar a proteção durante essa notificação se for necessário preservar as informações de identidade: a criptografia tem garantia de ser desativada durante a notificação.

```java

public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
     * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
     *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
     *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
     *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
     *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
     * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
     *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
     *            Otherwise it will be impossible to get protection info
     *            without advancing the stream position. The stream must be
     *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
     *            returned by a previous call to protect() or a copy of
     *            such bytes.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}

```

### <a name="content-providers"></a>Provedores de conteúdo

Se o aplicativo fornece dados corporativos além de um **ParcelFileDescriptor** por meio de um **ContentProvider**, o aplicativo deve chamar o método `isProvideContentAllowed(String)` no `MAMContentProvider`, passando um UPN da identidade do proprietário (nome principal do usuário) para o conteúdo. Se essa função retornar false, o conteúdo *não pode* ser retornado ao chamador. Descritores de arquivo retornados por meio de um provedor de conteúdo são manipulados automaticamente com base na identidade do arquivo.

### <a name="selective-wipe"></a>Apagamento seletivo

Se um aplicativo se registrar para notificação do `WIPE_USER_DATA`, ele não receberá o benefício do comportamento de apagamento seletivo do SDK padrão. Para aplicativos com reconhecimento de várias identidades, essa perda pode ser mais significativo, uma vez que o apagamento seletivo padrão do MAM apagará apenas os arquivos cujas identidades são direcionadas por um apagamento.

Se um aplicativo com reconhecimento de várias identidade deseja que o apagamento seletivo padrão do MAM seja feito _**e**_ deseja realizar suas próprias ações de apagamento, ele deve se registrar para as notificações do `WIPE_USER_AUXILIARY_DATA`. Essa notificação será enviada imediatamente pelo SDK antes de executar o apagamento seletivo padrão do MAM. Um aplicativo nunca deve se registrar para WIPE_USER_DATA e WIPE_USER_AUXILIARY_DATA.


## <a name="style-customization-optional"></a>Personalização de estilo (opcional)

Os modos de exibição gerados pelo SDK do MAM visualmente podem ser personalizados para atender melhor ao aplicativo no qual ele está integrado. Você pode personalizar as cores primárias, secundárias e de plano de fundo, além do tamanho do logotipo do aplicativo. Essa personalização de estilo é opcional e o padrão será usado se nenhum estilo personalizado estiver configurado.


### <a name="how-to-customize"></a>Como personalizar
Para que as alterações de estilo se apliquem às exibições do MAM do Intune, crie primeiro um arquivo XML de substituição de estilo. Esse arquivo deve ser colocado no diretório "/res/xml" do seu aplicativo e você pode renomeá-lo como quiser. Veja abaixo um exemplo do formato que esse arquivo deve seguir.

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>

```

Você deve reutilizar os recursos que já existem dentro de seu aplicativo. Por exemplo, você deve definir a cor verde no arquivo colors.xml e referenciá-la aqui. Você não pode usar o código de cor hexadecimal “#0000ff". O tamanho máximo para o logotipo do aplicativo é 110 dip (dp). Você pode usar uma imagem de logotipo menor, mas seguir o tamanho máximo produzirá resultados melhores visualmente. Se você exceder o limite de 110 dip, a imagem será reduzida e possivelmente ficará desfocada.

Veja abaixo uma lista completa de atributos de estilo permitidos, os elementos de interface do usuário que eles controlam, seus nomes de item de atributo de XML e o tipo de recurso esperado para cada.

|Atributo de estilo | Elementos de interface do usuário afetados | Nome do item de atributo | Tipo de recurso esperado |
| -- | -- | -- | -- |
| Cor da tela de fundo | Cor de fundo da tela de PIN <Br>Cor de preenchimento da caixa de PIN | background_color | Cor |
| Cor da tela de primeiro plano | Cor de texto da tela de primeiro plano <br> Borda da caixa se PIN no estado padrão <br> Caracteres (incluindo caracteres ofuscados) na caixa PIN quando o usuário digita um PIN| foreground_color | Cor|
| Cor de ênfase | Borda da caixa de PIN quando realçada <br> Hiperlinks |accent_color | Cor |
| Logotipo do aplicativo | Ícone grande que aparece na tela de PIN do aplicativo do Intune | logo_image | Desenhável |

## <a name="limitations"></a>Limitações

### <a name="file-size-limitations"></a>Limitações de tamanho do arquivo

Para grandes bases de código que são executadas sem o [ProGuard](http://proguard.sourceforge.net/), as limitações do formato de arquivo executável Dalvik podem se tornar um problema. Especificamente, as limitações a seguir podem ocorrer:

1.    O limite de 65 mil para campos.
2.    O limite de 65 mil para métodos.



### <a name="policy-enforcement-limitations"></a>Limitações de imposição de política

* **Captura de tela**: o SDK não impõe um novo valor de configuração de captura de tela Atividades que já passaram por Activity.onCreate. Isso pode resultar em um período de tempo em que o aplicativo foi configurado para desabilitar as capturas de tela, mas capturas de tela ainda podem ser feitas.

* **Usando resolvedores de conteúdo**: a política de transferência ou de recebimento do Intune pode bloquear ou bloquear parcialmente o uso de um resolvedor de conteúdo para acessar o provedor de conteúdo em outro aplicativo. Isso fará com que os métodos de ContentResolver retornem null ou gerem um valor de falha (por exemplo, `openOutputStream` lançará `FileNotFoundException` se bloqueado). O aplicativo pode determinar se uma falha de gravação de dados por meio de um resolvedor de conteúdo foi causada pela política (ou seria causada pela política), fazendo a chamada:

    ```java
    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI);
    ```

### <a name="exported-services"></a>Serviços exportados

 O arquivo AndroidManifest.xml incluído no SDK de Aplicativos do Intune contém **MAMNotificationReceiverService**, que deve ser um serviço exportado para permitir que o Portal da Empresa envie notificações para um aplicativo esclarecido. O serviço verifica o chamador para garantir que apenas o Portal da Empresa tenha permissão para enviar notificações.



## <a name="expectations-of-the-sdk-consumer"></a>Expectativas do cliente do SDK

O SDK do Intune mantém o contrato fornecido pela API do Android, embora condições de falha possam ser disparadas com mais frequência como resultado da aplicação de políticas. Essas práticas recomendadas do Android reduzirão a probabilidade de falha:

* Funções do SDK do Android que podem retornar valores nulos agora têm maior alta probabilidade de ser nulas.  Para minimizar problemas, certifique-se de que verificações nulas estejam nos lugares certos.

* Recursos que podem ser verificados devem ser verificados por meio de suas APIs de substituição do MAM.

* Quaisquer funções derivadas devem chamar por meio de suas versões de superclasse.

* Evite o uso de qualquer API de forma ambígua. Por exemplo, usar `Activity.startActivityForResult` sem verificar o requestCode causará um comportamento estranho.

## <a name="recommended-android-best-practices"></a>Práticas recomendadas de Android

* Todos os projetos de biblioteca devem compartilhar o mesmo android:package sempre que possível. Isso não falhará esporadicamente em tempo de execução; este é essencialmente um problema de tempo de compilação. As versões mais recentes do SDK do aplicativo do Intune removerão parte da redundância.

* Use das ferramentas de compilação do SDK do Android mais recentes.

* Remova todas as bibliotecas desnecessárias e não utilizadas (por exemplo, android.support.v4)
