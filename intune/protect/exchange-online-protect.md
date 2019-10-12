---
title: Exchange sem o gerenciamento de dispositivos
titleSuffix: Microsoft Intune
description: Use o Microsoft Intune para conceder aos funcionários acesso ao email do Office 365 Exchange Online deles sem precisar configurar um sistema de gerenciamento de dispositivos.
keywords: Acesso ao email do Office 365 Exchange
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/31/2017
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.topic: archived
ms.technology: ''
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 66e1d2df3d6aa3e5346104d6548df7dcb210c0f0
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732679"
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a>Proteger o Office 365 Exchange Online sem precisar de gerenciamento de dispositivo

Caso deseje, você pode conceder aos funcionários acesso a seus emails de trabalho sem a sobrecarga de configurar um sistema de gerenciamento de dispositivos. Você pode conceder acesso ao Office 365 Exchange Online por meio do Intune. Para concluir as etapas necessárias, confirme se você tem as licenças do Microsoft 365 ou do Azure Active Directory (premium) e do Intune. Os funcionários precisam ter um [dispositivo iOS ou Android com suporte](../fundamentals/supported-devices-browsers.md). 

Se você decidir configurar um sistema de gerenciamento de dispositivo, isso será possível. Esse tipo de proteção de aplicativo funciona independentemente do gerenciamento de dispositivo. 

## <a name="action-plan"></a>Plano de ação

1. [Saiba mais sobre Acesso Condicional](conditional-access.md). 
2. [Saiba mais sobre Acesso Condicional baseado em aplicativo](app-based-conditional-access-intune.md).
3. [Configurar políticas de Acesso Condicional baseado em aplicativo para o Exchange Online](app-based-conditional-access-intune-create.md).
4. [Bloquear aplicativos que não podem ser gerenciados](app-modern-authentication-block.md), especificamente os aplicativos que não usam a ADAL (Biblioteca de Autenticação do Azure Active Directory).
5. (Opcional) [Configurar políticas de Acesso Condicional baseado em aplicativo para o SharePoint Online](app-based-conditional-access-intune-create.md). Essas políticas bloqueiam o acesso aos dados da empresa de aplicativos que não podem ser gerenciados e protegidos. As políticas também limitam o acesso por meio do SharePoint móvel. 

## <a name="what-to-tell-employees-and-students"></a>O que dizer aos funcionários e alunos

* Solicite que os funcionários e alunos baixem e instalem o Microsoft Outlook ou o Microsoft SharePoint para iOS da Apple App Store ou para Android da Google Play Store. 
* Se você bloquear o acesso para aplicativos que não usam uma autenticação moderna, informe essa restrição aos funcionários e alunos. 

## <a name="next-steps"></a>Próximas etapas

Você usou o Acesso Condicional baseado em aplicativo para aumentar a segurança dos dados da empresa. Nas próximas etapas, você poderá aprender mais sobre outras maneiras de aumentar a proteção dos dados da empresa, incluindo: 

* Configurar o [Acesso Condicional baseado em conformidade de dispositivo, em risco de dispositivo, em localização e em atributos do usuário no Active Directory e no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).  
* Configurar políticas de proteção de aplicativo para ajudá-lo a proteger os dados da empresa contra perda de dados intencional ou não intencional. 
* Aproveitar a Proteção de Informações do Azure para proteger os dados da empresa que estão fora da sua rede. 

Deseja obter ajuda para habilitar este ou outros cenários do EMS ou do Office 365? Se você tiver, pelo menos, 150 licenças do Microsoft 365, do Enterprise Mobility + Security ou do Azure Active Directory Premium, use seus [Benefícios do FastTrack](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 