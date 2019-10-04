---
title: Exceções da política de transferência de dados para aplicativos
titleSuffix: Microsoft Intune
description: Crie exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ada0f7fc7ed21750adf20a63d229f9a188cf34f
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725524"
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Como criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune

Como um administrador, você pode criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune. Uma exceção permite que você escolha especificamente quais aplicativos não gerenciados podem transferir dados entre aplicativos gerenciados. O departamento de TI precisa confiar nos aplicativos não gerenciados incluídos na lista de exceções. 

>[!WARNING] 
> Você é responsável por fazer alterações na política de exceção de transferência de dados. As adições a essa política permitem que aplicativos não gerenciados (aplicativos que não são gerenciados pelo Intune) acessem dados protegidos por aplicativos gerenciados. Esse acesso aos dados protegidos pode resultar em vazamentos de segurança de dados. Adicione exceções de transferência de dados somente a aplicativos que sua organização deve usar, mas que não sejam compatíveis com as APPs (políticas de proteção do aplicativo) do Intune. Além disso, adicione exceções somente para aplicativos que não representam riscos de vazamento de dados.

Em uma Política de Proteção de Aplicativo do Intune, a definição de **Permitir que o aplicativo transfira dados para outros aplicativos** como **Aplicativos gerenciados por política** significa que o aplicativo pode transferir dados somente para aplicativos gerenciados pelo Intune. Caso precise permitir a transferência de dados para aplicativos específicos que não dão suporte ao Aplicativo do Intune, crie exceções a essa política usando **Selecionar aplicativos para isenção**. As isenções permitem que os aplicativos gerenciados pelo Intune invoquem aplicativos não gerenciados com base no protocolo de URL (iOS) ou o nome do pacote (Android). Por padrão, o Intune adiciona aplicativos vitais nativos à lista de exceções. 

> [!NOTE]
> Modificar ou adicionar às exceções da política de transferência de dados não afeta outras Políticas de Proteção do Aplicativo, como restrições a cortar, copiar e colar. 

## <a name="ios-data-transfer-exceptions"></a>Exceções de transferência de dados do iOS
Para uma política destinada ao iOS, você pode configurar as exceções de transferência de dados por protocolo de URL. Para adicionar uma exceção, consulte a documentação fornecida pelo desenvolvedor do aplicativo para encontrar informações sobre os protocolos de URL compatíveis. Para obter mais informações sobre exceções de transferência de dados do iOS, confira [Configurações da política de proteção de aplicativo do iOS – Isenções de transferência de dados](app-protection-policy-settings-ios.md#data-transfer-exemptions).

> [!NOTE]
> A Microsoft não tem um método para localizar manualmente o protocolo de URL para a criação de exceções de aplicativo para aplicativos de terceiros. 

## <a name="android-data-transfer-exceptions"></a>Exceções de transferência de dados de Android
Para uma política destinada ao Android, você pode configurar as exceções de transferência de dados por nome de pacote do aplicativo. Verifique a página **Google Play** Store do aplicativo ao qual você deseja adicionar uma exceção, a fim de localizar o nome do pacote do aplicativo. Para obter mais informações sobre exceções de transferência de dados do Android, confira [Configurações da política de proteção de aplicativo do Android – Isenções de transferência de dados](app-protection-policy-settings-android.md#data-transfer-exemptions).


>[!TIP]
> Você pode encontrar a ID do pacote de um aplicativo navegando até o aplicativo na loja do Google Play. A ID do pacote está contida na URL da página do aplicativo. Por exemplo, a ID do pacote do aplicativo Microsoft Word é **com.microsoft.office.word**.

### <a name="example"></a>Exemplo
Ao adicionar o pacote **Webex** como uma exceção à política de transferência de dados de MAM, os links do Webex, em uma mensagem de email do Outlook gerenciada, terão permissão para abrir diretamente no aplicativo Webex. A transferência de dados permanecerá restrita em outros aplicativos não gerenciados.

- Exemplo do **Webex** do iOS:   Para isentar o aplicativo **Webex**, de modo que ele possa ser invocado por aplicativos gerenciados do Intune, adicione uma exceção de transferência de dados à seguinte cadeia de caracteres: <code>wbx</code>
    
- Exemplo do **Mapas** do iOS:   Para isentar o aplicativo nativo **Mapas**, de modo que ele possa ser invocado por aplicativos gerenciados do Intune, adicione uma exceção de transferência de dados à seguinte cadeia de caracteres: <code>maps</code>

- Exemplo do **Webex** do Android:   Para isentar o aplicativo **Webex**, de modo que ele possa ser invocado por aplicativos gerenciados do Intune, adicione uma exceção de transferência de dados à seguinte cadeia de caracteres: <code>com.cisco.webex.meetings</code>
    
- Exemplo do **SMS** do Android:   Para isentar o aplicativo nativo **SMS**, de modo que ele possa ser invocado por aplicativos gerenciados do Intune em diferentes aplicativos de mensagens e dispositivos Android, adicione exceções de transferência de dados às seguintes cadeias de caracteres: 
    <code>com.google.android.apps.messaging</code>
    
    <code>com.android.mms</code>
    
    <code>com.samsung.android.messaging</code>

## <a name="next-steps"></a>Próximas etapas

- [Criar e implantar as políticas de proteção do aplicativo](app-protection-policies.md)
- [Configurações de política de proteção de aplicativo iOS – Isenções de transferência de dados](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Configurações de política de proteção de aplicativo Android – Isenções de transferência de dados](app-protection-policy-settings-android.md#data-transfer-exemptions)