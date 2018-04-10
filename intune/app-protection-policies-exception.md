---
title: "Exceções da política de transferência de dados para aplicativos"
titleSuffix: Microsoft Intune
description: "Crie exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f9015e3a-c22c-42eb-90e6-ba48dee3a41d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1e37e78f7272b0f53f974eccb20c7e02574a9a9
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2018
---
# <a name="how-to-create-exceptions-to-the-intune-mobile-application-management-mam-data-transfer-policy"></a>Como criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como um administrador, você pode criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune. Uma exceção permite que você escolha especificamente quais aplicativos não gerenciados podem transferir dados entre aplicativos gerenciados. Os aplicativos não gerenciados que são incluídos na lista de exceções devem ser considerados confiáveis pelo TI. 

>[!WARNING] 
> Você é responsável por fazer alterações na política de exceção de transferência de dados. As adições a essa política permitem que aplicativos não gerenciados (aplicativos que não são gerenciados pelo Intune) acessem dados protegidos por aplicativos gerenciados. Esse acesso aos dados protegidos pode resultar em vazamentos de segurança de dados. Adicione exceções de transferência de dados somente a aplicativos que sua organização deve usar, mas que não sejam compatíveis com as APPs (políticas de proteção do aplicativo) do Intune. Além disso, adicione exceções somente para aplicativos que não representam riscos de vazamento de dados.

Esse recurso se aplica quando você cria uma política de proteção de aplicativos do Intune com a transferência de dados definida como **Somente aplicativos gerenciados**. A não ser pelas exceções que você criar, quando a política de transferência de dados estiver definida como **Somente aplicativos gerenciados**, a transferência de dados permanecerá restrita a aplicativos que são gerenciados pelo Intune. É possível criar as restrições usando protocolos (iOS) ou pacotes (Android).

Você pode configurar esse recurso para permitir exceções à política de proteção de aplicativo **restringir transferência de dados** de MAM do Intune. Essa política é necessária somente se você deseja permitir a transferência de dados para um aplicativo que não é compatível com a APP do Intune. Essa política permite que os aplicativos gerenciados pelo Intune, com configurações de transferência de dados definidas como **Somente aplicativos gerenciados**, invoquem aplicativos não gerenciados com base no protocolo de URL (iOS) ou no nome do pacote (Android). O Intune adiciona aplicativos vitais nativos à lista padrão de exceções. 

## <a name="ios-data-transfer-exceptions"></a>Exceções de transferência de dados do iOS
Para uma política destinada ao iOS, você pode configurar as exceções de transferência de dados por protocolo de URL. Para adicionar uma exceção, consulte a documentação fornecida pelo desenvolvedor do aplicativo para encontrar informações sobre os protocolos de URL compatíveis. Para obter mais informações sobre exceções de transferência de dados do iOS, consulte [Configurações de política de proteção de aplicativo iOS – Isenções de transferência de dados](app-protection-policy-settings-ios.md#data-transfer-exemptions).

## <a name="android-data-transfer-exceptions"></a>Exceções de transferência de dados de Android
Para uma política destinada ao Android, você pode configurar as exceções de transferência de dados por nome de pacote do aplicativo. Verifique a página **Google Play** Store do aplicativo ao qual você deseja adicionar uma exceção, a fim de localizar o nome do pacote do aplicativo. Para obter informações adicionais sobre exceções de transferência de dados do Android, consulte [Configurações de política de proteção de aplicativo Android – Isenções de transferência de dados](app-protection-policy-settings-android.md#data-transfer-exemptions).

### <a name="example"></a>Exemplo
Ao adicionar o pacote **Webex** como uma exceção à política de transferência de dados de MAM, os links do Webex, em uma mensagem de email do Outlook gerenciada, terão permissão para abrir diretamente no aplicativo Webex. A transferência de dados permanecerá restrita em outros aplicativos não gerenciados.

- Exemplo do **Webex** do iOS: para isentar o aplicativo **Webex** e permitir que ele seja invocado por aplicativos gerenciados do Intune, você deve adicionar uma exceção de transferência de dados à cadeia de caracteres a seguir: <code>wbx</code>.

- Exemplo do **Webex** do Android: para isentar o aplicativo **Webex** e permitir que ele seja invocado por aplicativos gerenciados do Intune, você deve adicionar uma exceção de transferência de dados à cadeia de caracteres a seguir: <code>com.cisco.webex.meetings</code>. 

## <a name="next-steps"></a>Próximas etapas

- [Criar e implantar as políticas de proteção do aplicativo](app-protection-policies.md)
- [Configurações de política de proteção de aplicativo iOS – Isenções de transferência de dados](app-protection-policy-settings-ios.md#data-transfer-exemptions)
- [Configurações de política de proteção de aplicativo Android – Isenções de transferência de dados](app-protection-policy-settings-android.md#data-transfer-exemptions)