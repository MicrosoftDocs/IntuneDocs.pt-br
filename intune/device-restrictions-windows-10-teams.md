---
title: "Restrições de dispositivo do Intune para Windows 10 Team"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba mais sobre as restrições de dispositivo disponíveis para dispositivos Windows 10 Team."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: afbbe6b7649e1ffc3f84ada64396d9033a2db200
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo Windows 10 Team no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

- **Ativar tela quando alguém estiver no recinto** – Permite que o dispositivo seja ativado automaticamente quando o sensor detectar a alguém na sala.
- **PIN para projeção sem fio** – Especifica se você deve inserir um PIN antes de poder usar os recursos de projeção sem fio do dispositivo.
- **Projeção sem fio Miracast** – Habilite esta opção se você quiser permitir que o dispositivo Windows 10 Team use dispositivos habilitados do Miracast para o projeto.
- **Informações de reunião exibidas na tela de Boas-Vindas** – Habilite essa opção para escolher as informações que serão exibidas no bloco Reuniões da tela de Boas-Vindas. Você pode:
    - **Mostrar somente organizador e hora**
    - **Mostrar organizador, hora e assunto (o assunto é oculto para reuniões privadas)**
- **URL da imagem de fundo da tela de Boas-Vindas** – Habilite essa configuração para exibir uma tela de fundo personalizada na tela de **Boas-Vindas** dos dispositivos com Windows 10 Team da URL especificada.<br>A imagem deve estar no formato PNG e a URL deve começar com **https://**.
- **Janela de manutenção para atualizações** – Configura a o intervalo em que atualizações podem ocorrer no dispositivo. Você pode configurar a hora de início do intervalo e sua duração (de 1 a 5 horas).
- **Insights Operacionais do Azure** – O Insights Operacionais do Azure, que faz parte do pacote do Microsoft Operations Manager, coleta, armazena e analisa os dados de arquivo de log de dispositivos Windows 10 Team.<br>Para se conectar aos Insights Operacionais do Azure, você deve especificar uma **ID do Espaço de Trabalho** e uma **Chave do Espaço de Trabalho**.
