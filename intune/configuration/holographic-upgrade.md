---
title: Atualizar para Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Saiba como atualizar dispositivos que executam o Windows Holographic para o Windows Holographic for Business
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8005912cdb4a5898eccf7c95500ff7bbdbe34b3c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734564"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Atualizar dispositivos que executam o Windows Holographic para o Windows Holographic for Business

O Microsoft Intune inclui muitas configurações para ajudar a proteger seus dispositivos. Este artigo lista e descreve as configurações para atualizar dispositivos com Windows Holographic para Windows Holographic for Business. Essas configurações são criadas em um perfil de configuração de atualização no Intune que são enviadas por push ou implantadas em dispositivos.

Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para atualizar seus dispositivos com Windows Holographic. Para o Microsoft HoloLens, você pode adquirir o Commercial Suite para obter a licença necessária para a atualização. Para obter mais informações, consulte [Desbloquear recursos do Windows Holographic for Business](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise).

Para saber mais sobre esse recurso, consulte [Atualizar edições Windows 10 ou habilitar o modo S](../edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Atualização de edição

- **Edição para a qual atualizar**: selecione **Windows 10 Holographic for Business**.
- **Arquivo de Licença**: navegue e selecione o arquivo de licença XML que foi fornecido para você.

  ![Insira o nome do arquivo XML que inclui as informações de licença do Holographic for Business](./media/holographic-upgrade/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas talvez ainda não esteja fazendo nada. [Atribua o perfil](device-profile-assign.md) e [monitore seu status](../device-profile-monitor.md).

Você também pode criar perfis de atualização de edição para dispositivos com [Windows 10 e posterior](edition-upgrade-windows-settings.md).