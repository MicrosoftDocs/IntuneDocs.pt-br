---
title: Solucionar problemas do Exchange Connector | Microsoft Docs
description: Solucione problemas relacionados ao Intune Exchange Connector.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dc
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ad0519145b6cc7c837490892089c18bf20e08d57
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="troubleshoot-the-exchange-connector"></a>Solução de problemas com o Exchange Connector

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico descreve como solucionar problemas que podem estar relacionados com o Intune Exchange Connector.

## <a name="steps-for-checking-the-connector-configuration"></a>Etapas para verificar a configuração do Connector 

Verifique a configuração do Exchange Connector e veja se o problema foi resolvido.

- Certifique-se de especificar uma conta de notificação na instalação inicial do Exchange Connector.
- A Conta de serviço do Exchange Connector deve ter as permissões apropriadas para executar os cmdlets do PowerShell usados pelo Exchange Connector.
- Ao configurar o Exchange Connector, especifique um CAS (Servidor de Acesso para Cliente) que seja o mais próximo possível do servidor que hospeda o Exchange Connector. A latência de comunicação entre o CAS e o Exchange Connector pode resultar em atrasos de descoberta de dispositivo, especialmente ao usar o O365 dedicado.
- Lembre-se de que há uma latência de tempo entre as sincronizações do Exchange Connector com o CAS do Exchange. Uma sincronização completa ocorre uma vez por dia e uma sincronização de delta (rápida) ocorre a cada duas horas. Há a probabilidade que usuários com um dispositivo registrado recentemente sofram atraso na obtenção de acesso.
- 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>O dispositivo do Exchange ActiveSync não é descoberto no Exchange
Verifique se o Exchange Connector está sincronizando com o Exchange Server. Para fazer isso, localize os logs para uma sincronização completa ou delta. Consulte Logs do Exchange Connector. Se uma sincronização completa ou delta tiver sido concluída com êxito desde que o dispositivo foi associado, você eliminou isso como origem do problema. Se nenhuma sincronização tiver sido feita, colete os logs de sincronização e anexe-os a sua solicitação de suporte.

- Se um usuário não tiver uma licença do Intune, o Exchange Connector não descobrirá seus dispositivos.
- Se o endereço SMTP primário de um usuário for diferente de seus UPN no AAD, o Exchange Connector não descobrirá os dispositivos desse usuário do Intune/AAD. Corrija o endereço SMTP primário.
- Se o CAS com que o Exchange Connector se comunica durante um ciclo de descoberta for um CAS do Exchange 2010 e você tiver as caixas de correio do Exchange 2010 e 2013, o Exchange Connector não descobrirá os dispositivos de nenhum usuário do Exchange 2013. Para resolver esse problema, configure o Exchange Connector para apontar para um CAS do Exchange 2013.  Embora esse problema esteja relacionado principalmente a topologias do O365 dedicado, ainda é recomendável apontar para um CAS do Exchange 2013 em outras topologias como uma prática recomendada.
- Para ambientes do Exchange dedicado (O365 dedicado), você deve apontar o Exchange Connector para um CAS do Exchange 2013 (não 2010) no ambiente dedicado durante a configuração inicial, uma vez que ele se comunicará com este CAS somente ao executar cmdlets do Powershell.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Usando o Powershell para obter mais dados sobre problemas do Exchange Connector
- Para obter uma lista de todos os dispositivos móveis para uma caixa de correio, use Get-ActiveSyncDeviceStatistics -mailbox mbx
- Para obter uma lista de endereços SMTP para uma caixa de correio, use Get-Mailbox -Identity user | select emailaddresses | fl.
- Para obter informações detalhadas sobre o estado de acesso a um dispositivo, use Get-CASMailbox <upn> | fl

### <a name="next-steps"></a>Próximas etapas
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).
