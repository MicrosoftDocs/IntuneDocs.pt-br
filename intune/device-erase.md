---
title: Apagar um dispositivo macOS
titleSuffix: Microsoft Intune
description: Saiba como apagar todos os dados, incluindo o sistema operacional, de um dispositivo macOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d6ae04abda7f026bcbc02e325274712a386147b8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2018
---
# <a name="erase-all-data-from-a-macos-device"></a>Apagar todos os dados de um dispositivo macOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Você pode apagar todos os dados de um dispositivo macOS, incluindo o sistema operacional. O dispositivo também será removido do gerenciamento do Intune. Nenhum aviso será dado ao usuário final.

1. No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Dispositivos** > **Todos os dispositivos** > escolha o dispositivo que deseja apagar.
![Captura de tela](./media/device-erase/choosedevice.png)
2. Clique em **Mais** > **Apagar** > forneça um número de 6 dígitos para o **PIN de recuperação**. Este é o PIN que você deve fornecer ao usuário para que ele possa reinstalar o sistema operacional no dispositivo. Certifique-se de anotar esse PIN porque ele não ficará visível após a conclusão da ação de apagar.
![Captura de tela](./media/device-erase/providepin.png)
3. Clique em **OK** apagar o dispositivo.