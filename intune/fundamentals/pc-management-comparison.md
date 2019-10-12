---
title: Comparar as opções de gerenciamento de computadores Windows
titleSuffix: Microsoft Intune
description: Registro de dispositivos iOS corporativos usando o DEP (Programa de registro de dispositivos) da Apple ou o Apple Configurator.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 217b93fcd78010428ce427a755e6c0c20f4372df
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736267"
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Comparar o gerenciamento de computadores Windows como computadores ou dispositivos móveis

[!INCLUDE [classic-portal](../../intune-classic/includes/classic-portal.md)]

As organizações podem usar o Microsoft Intune para gerenciar computadores Windows como dispositivos móveis com o MDM (gerenciamento de dispositivo móvel) ou como computadores com o cliente de software do Intune.  A Microsoft recomenda que os clientes usem a solução de gerenciamento MDM sempre que possível. No entanto, para ajudá-lo a compreender melhor as diferenças entre essas opções, o gráfico a seguir compara as duas opções de gerenciamento.

|**Funcionalidade/Cenário** |**Windows como Computador**<br>Cliente de software do Intune | **Windows como dispositivos móveis**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Sistemas operacionais** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Suporte do Portal do Intune** |[Console do Silverlight](https://manage.microsoft.com)|[Portal do Azure](https://portal.azure.com) |
|**Acesso condicional**|Não disponível|Disponível <br>[O que é o Acesso Condicional?](../protect/conditional-access.md)|
|**Registro em massa**|Não disponível|Disponível <br>[Registro em massa para dispositivos Windows](../enrollment/windows-bulk-enroll.md)|
|**Perfis de dispositivo**|Não disponível|Disponível <br>[O que são perfis de dispositivo do Microsoft Intune?](../configuration/device-profiles.md)|
|**Registro sem agente**|Não disponível |Disponível<br>[Registrar dispositivos Windows](../enrollment/windows-enroll.md)|
|**Gerenciamento de atualizações de software**| Windows Updates e atualizações de aplicativos da Microsoft<br>[Manter computadores Windows atualizados com as atualizações de software](../keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)|Microsoft Store para Empresas para atualizações do Windows 10 e de aplicativos da Microsoft<br> [Definir as configurações do Windows Update for Business](../protect/windows-update-for-business-configure.md) |
|**Gerenciamento de licenças de software**|Disponível <br>[Gerenciar contratos de licença para software de computadores Windows](../manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)|Microsoft Store para Empresas (somente aplicativos .appx)<br>[Gerenciar aplicativos comprados na Microsoft Store para Empresas](../apps/windows-store-for-business.md)|
|**Inventário**|Disponível <br>[Exibir o inventário de software e hardware de computadores Windows](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md)|Disponível <br>[Como monitorar as informações do aplicativo](../apps/apps-monitor.md)<br>[O que é o gerenciamento de dispositivo](../remote-actions/device-management.md)|
|**Política de Firewall do Windows**|Disponível <br>[Ajude a proteger Computadores Windows usando políticas de Firewall do Windows](../help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) |Disponível <br>[Windows Defender Firewall](../protect/endpoint-protection-windows-10.md#windows-defender-firewall)|
|**Proteção antimalware**|Endpoint Protection<br>[Ajudar a proteger computadores Windows com o Endpoint Protection](../help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)|Windows Defender<br>[Habilitar o Windows Defender](../protect/advanced-threat-protection.md)|
|**Assistência remota** |TeamViewer<br>[Solicitar e fornecer assistência remota para computadores Windows](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md)|TeamViewer<br> [Usar o TeamViewer para administrar remotamente os dispositivos do Intune](../remote-actions/teamviewer-support.md) |
|**Implantação de aplicativo** | Não disponível para a Microsoft Store para Empresas,<br>somente .exe, .appx e .msi de vários arquivos<br>[Adicionar aplicativos a computadores Windows que executam o cliente de software do Intune](add-apps-for-windows-pcs-in-microsoft-intune.md)|Disponível para aplicativos da Microsoft Store e aplicativos de linha de negócios<br>[Como adicionar aplicativos da Windows Store](../apps/store-apps-windows.md)<br>[Como adicionar aplicativos LOB (aplicativos de linha de negócios) do Windows](../apps/lob-apps-windows.md)|
|**Proteção de aplicativo**|Não disponível|Disponível <br>[O que são políticas de proteção do aplicativo?](../apps/app-protection-policy.md)|
|**Atestado de integridade**|Não disponível|Disponível|


## <a name="advantages-of-mdm-windows-pc-management"></a>Vantagens do gerenciamento MDM de computadores Windows
O gerenciamento de computadores Windows com o moderno gerenciamento de dispositivo móvel apresenta as seguintes vantagens:
- **Escalabilidade** – o gerenciamento MDM é dimensionado com gerenciamento de nuvem do Intune. O cliente de software do Intune é limitado a 7.000 computadores.
- **Simplicidade** – usa funcionalidades de gerenciamento modernas incluídas no sistema operacional sem depender do download de um cliente de software
- **Consistência** – os computadores Windows são gerenciados como todos os outros dispositivos móveis em sua organização
<!-- - **Cloud optimization** - -->