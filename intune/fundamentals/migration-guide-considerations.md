---
title: Considerações especiais sobre a migração
titleSuffix: Microsoft Intune
description: Este artigo fornece considerações especiais de migração antes de iniciar uma campanha de migração para o Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 45e2985bcf01d635e964ee8785938c0d5df4e4af
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727604"
---
# <a name="special-migration-considerations"></a>Considerações especiais sobre a migração

Algumas considerações especiais de migração podem ser aplicáveis dependendo do seu ambiente de provedor de MDM existente.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Apagamento para o DEP (Programa de registro de dispositivos) da Apple

O programa DEP (Programa de Registro de Dispositivo) da Apple define configurações de dispositivos que não podem ser removidas pelo usuário final. Para manter os recursos de gerenciamento avançados do DEP, o dispositivo precisa ser retornado ao estado de configuração inicial (novo) por meio de um apagamento para ser registrado no Intune.

Para continuar usando o DEP para gerenciar os dispositivos no Intune, [configure o registro de dispositivo iOS com o Programa de registro de dispositivos](../enrollment/device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Próximas etapas

[Fase 2: Campanha de migração](../migration-guide-campaign.md)