---
title: Perfis de provisionamento do aplicativo | Microsoft Docs
titleSuffix: Intune Azure preview
description: "Visualização do Intune Azure: o Intune fornece as ferramentas para atribuir proativamente um novo perfil provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 966c097280ebebac68749e71c20381ee816360da
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017

---

# <a name="use-ios-mobile-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Usar os perfis de provisionamento móvel do iOS para impedir que os aplicativos expirem

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="introduction"></a>Introdução

Os aplicativos de linha de negócios de iOS da Apple atribuídos em iPhones e iPads são criados com um perfil de provisionamento incluído e código assinado com um certificado. Quando o aplicativo é executado, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento. As validações a seguir ocorrem:

- **Integridade do arquivo de instalação** – o iOS compara os detalhes de aplicativos com a chave pública do certificado de assinatura de empresa. Se eles forem diferentes, o conteúdo dos aplicativos poderá ter sido alterado e ele não poderá ser executado.
- **Imposição de funcionalidades** – o iOS tenta aplicar as funcionalidades do aplicativo do perfil de provisionamento corporativo (não perfis de provisionamento de desenvolvedor individuais) contidas no arquivo de instalação (.ipa) do aplicativo.


A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos. No entanto, o perfil de provisionamento expira após um ano. Enquanto o certificado ainda for válido, o Intune fornecerá as ferramentas para atribuir proativamente um novo perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração.
Depois que o certificado expirar, você deverá assinar o aplicativo novamente com um novo certificado e inserir um novo perfil de provisionamento com a chave do novo certificado.


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Como criar um perfil de provisionamento de aplicativo móvel iOS

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1.  Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Perfis de provisionamento iOS**.
2.  Na folha da lista de perfis, escolha **Criar Perfil**.
3. Na folha **Criar perfil**, configure os valores a seguir:
    - **Nome** – forneça um nome para essa política de perfil de provisionamento móvel.
    - **Descrição** – de maneira opcional, forneça uma descrição para a política.
    - **Carregar arquivo de perfil** – escolha **Importar** e escolha um arquivo de Perfil de Configuração Móvel da Apple (com a extensão **.mobileprovision**) que você baixou do site do Desenvolvedor da Apple.
4. Ao terminar, escolha **Criar**.

## <a name="next-steps"></a>Próximas etapas

Atribua o perfil aos dispositivos iOS necessários. Para saber mais, use as etapas em [Como atribuir perfis de dispositivo](device-profile-assign.md).
