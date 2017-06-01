---
title: "Visão geral do ciclo de vida do aplicativo | Microsoft Docs"
description: "Saiba mais sobre o ciclo de vida de aplicativos gerenciados pelo Intune, desde sua adição até sua eventual aposentadoria."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2c1b4876e92e64912f237560b346aedceb0771c5
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="overview-of-the-app-lifecycle"></a>Visão geral do ciclo de vida do aplicativo

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O ciclo de vida de aplicativo do Intune começa quando um aplicativo é adicionado e passa por outras fases até você removê-lo.

![O ciclo de vida do aplicativo](./media/app-lifecycle.png "o ciclo de vida do aplicativo do Intune")

## <a name="add"></a>Adicionar

A primeira etapa na implantação do aplicativo é adicionar os aplicativos que você deseja gerenciar e implantar no Intune. Embora você possa trabalhar com vários tipos de aplicativos diferentes, os procedimentos básicos são os mesmos. Com o Intune, é possível adicionar aplicativos a [dispositivos registrados](add-apps-for-mobile-devices-in-microsoft-intune.md) ou a [computadores Windows gerenciados com o software cliente do Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

## <a name="deploy"></a>Implantar

Depois de adicionar o aplicativo ao Intune, você poderá [implantá-lo nos dispositivos gerenciados](deploy-apps.md). O Intune facilita esse processo e, após a implantação do aplicativo, você pode [monitorar o êxito](monitor-apps-in-microsoft-intune.md) da implantação por meio do console de administração do Intune. Além disso, em algumas lojas de aplicativos, como as da [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) e do [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md), é possível comprar licenças de aplicativo em massa para sua empresa. O Intune pode sincronizar dados com essas lojas, para que você possa implantar e acompanhar o uso da licença para esses tipos de aplicativos, diretamente no console de administração do Intune.

## <a name="configure"></a>Configurar

Como parte do ciclo de vida do aplicativo, são lançadas novas versões de aplicativos regularmente. O Intune fornece ferramentas para [atualizar aplicativos](update-apps-using-microsoft-intune.md) implantados para uma versão mais recente com facilidade. Além disso, é possível configurar funcionalidade extra em alguns aplicativos, por exemplo:
- As [políticas de configuração de aplicativo iOS](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) fornecem configurações para aplicativos iOS compatíveis que são usadas quando o aplicativo é executado. Por exemplo, um aplicativo pode exigir configurações de identidade visual específicas ou o nome de um servidor para se conectar.
- As [políticas de navegador gerenciado](manage-internet-access-using-managed-browser-policies.md) ajudam a definir as configurações para o navegador gerenciado do Intune, que substitui o navegador padrão do dispositivo e permite restringir os sites que os usuários podem visitar.

## <a name="protect"></a>Proteger

O Intune oferece várias maneiras para ajudar a proteger os dados em seus aplicativos. Os principais métodos são:
- O [acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) controla o acesso ao email e outros serviços com base nas condições que você especificar. As condições incluem tipos de dispositivo ou conformidade com uma [política de conformidade do dispositivo](introduction-to-device-compliance-policies-in-microsoft-intune.md) implantada.
- O [MAM (gerenciamento de aplicativo móvel)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) funciona com aplicativos individuais para ajudar a proteger os dados da empresa utilizados por eles. Por exemplo, você pode restringir a cópia de dados entre os aplicativos gerenciados e não gerenciados, ou impedir que aplicativos sejam executados em dispositivos com jailbreak ou raiz.

## <a name="retire"></a>Desativar

Por fim, é provável que os aplicativos implantados fiquem desatualizados e precisem ser removidos. O Intune facilita [desativar aplicativos de serviço](retire-apps-using-microsoft-intune.md).
