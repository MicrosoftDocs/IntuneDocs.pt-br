---
title: "Apagamento de dispositivos móveis gerenciados pelo Exchange | Microsoft Docs"
description: "O Microsoft Intune permite apagar ou redefinir dispositivos móveis que são gerenciados usando o EAS (Exchange ActiveSync) com o Intune Exchange Connector"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4b0914ab12456fd3ad5f957d68a59df9de539176
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---


# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Exchange-managed mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune permite apagar ou redefinir dispositivos móveis que são gerenciados usando o EAS (Exchange ActiveSync) com o Intune Exchange Connector. A tabela a seguir descreve os recursos de apagamento disponíveis por meio do Exchange ActiveSync:

|Tipo de apagamento|Windows 8.1 e Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Apagamento completo|Remove a conta de email e os emails armazenados em cache.|Redefinição XFactory.|Redefinição de fábrica.|
|Apagamento seletivo/email|Remove conta de email.|Não há suporte.|Não há suporte.|
|Apagamento seletivo/políticas|Aplicação de políticas é removida, mas as configurações não são alteradas|Aplicação XFactory é removida, mas as configurações não são alteradas.|A aplicação da política é removida, mas as configurações não são alteradas.|
