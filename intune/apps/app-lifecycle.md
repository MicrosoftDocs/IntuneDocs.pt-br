---
title: Visão geral do ciclo de vida do aplicativo para Microsoft Intune
description: Saiba mais sobre o ciclo de vida de aplicativos gerenciados no Microsoft Intune. O ciclo de vida do aplicativo inclui adicionar, implantar, configurar, proteger e desativar aplicativos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: apps; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3c351c1bef09d559ee6fb07b2c5135b25ca69d9d
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725706"
---
# <a name="overview-of-the-app-lifecycle-in-microsoft-intune"></a>Visão geral do ciclo de vida do aplicativo no Microsoft Intune

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

O ciclo de vida de aplicativo do Microsoft Intune começa quando um aplicativo é adicionado e passa por outras fases até ele ser removido. Ao compreender essas fases, você terá os detalhes necessários para iniciar o gerenciamento de aplicativos no Intune.

![O ciclo de vida do aplicativo - Adicionar, implantar, configurar, proteger e desativar. ](./media/app-lifecycle/app-lifecycle.png "O ciclo de vida de aplicativo do Intune")

## <a name="add"></a>Add

A primeira etapa na implantação do aplicativo é adicionar ao Intune os aplicativos que você deseja gerenciar e atribuir. Embora você possa trabalhar com vários tipos de aplicativos diferentes, os procedimentos básicos são os mesmos. Com o Intune, é possível adicionar tipos de aplicativos diferentes, incluindo aplicativos escritos internamente (linha de negócios), aplicativos da Store, aplicativos nativos e aplicativos na Web. Para obter mais informações sobre os tipos de aplicativos, consulte [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md). 

## <a name="deploy"></a>Implantar

Depois de adicionar o aplicativo ao Intune, será possível [atribuí-lo aos usuários e dispositivos gerenciados](apps-deploy.md). O Intune facilita esse processo e, após a implantação do aplicativo, é possível [monitorar o êxito](apps-monitor.md) da implantação pelo Intune no Portal do Azure. Além disso, em algumas lojas de aplicativos, como as da [Apple](vpp-apps-ios.md) e do [Windows](windows-store-for-business.md), é possível comprar licenças de aplicativo em massa para sua empresa. O Intune pode sincronizar dados com essas lojas, para que você possa implantar e acompanhar o uso da licença para esses tipos de aplicativos, diretamente no console de administração do Intune.

## <a name="configure"></a>Configurar

Como parte do ciclo de vida do aplicativo, são lançadas novas versões de aplicativos regularmente. O Intune fornece ferramentas para [atualizar aplicativos](apps-add.md) implantados para uma versão mais recente com facilidade. Além disso, é possível configurar funcionalidade extra em alguns aplicativos, por exemplo:
- As [políticas de configuração de aplicativo iOS](app-configuration-policies-use-ios.md) fornecem configurações para aplicativos iOS compatíveis que são usadas quando o aplicativo é executado. Por exemplo, um aplicativo pode exigir configurações de identidade visual específicas ou o nome de um servidor com o qual ele precisa se conectar.
- As [políticas de navegador gerenciado](app-configuration-managed-browser.md) ajudam a definir as configurações para o navegador gerenciado do Intune, que substitui o navegador padrão do dispositivo e permite restringir os sites que os usuários podem visitar.

## <a name="protect"></a>Proteger

O Intune oferece várias maneiras para ajudar a proteger os dados em seus aplicativos. Os principais métodos são:
- [Acesso condicional](../protect/conditional-access.md), que controla o acesso ao email e outros serviços com base nas condições que você especificar. As condições incluem tipos de dispositivo ou conformidade com uma [política de conformidade do dispositivo](../protect/device-compliance-get-started.md) implantada.
- As [políticas de proteção de aplicativo](app-protection-policy.md) funcionam com aplicativos individuais para ajudar a proteger os dados da empresa usados por eles. Por exemplo, você pode restringir a cópia de dados entre os aplicativos gerenciados e não gerenciados, ou impedir que aplicativos sejam executados em dispositivos com jailbreak ou raiz.

## <a name="retire"></a>Desativar

Por fim, é provável que os aplicativos implantados fiquem desatualizados e precisem ser removidos. O Intune facilita [desativar aplicativos de serviço](../remote-actions/device-management.md).

## <a name="next-steps"></a>Próximas etapas

- Saiba mais sobre o [gerenciamento de aplicativos no Microsoft Intune](app-management.md)