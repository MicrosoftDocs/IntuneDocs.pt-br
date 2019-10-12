---
title: Adicionar ou definir configurações de educação no Microsoft Intune – Azure | Microsoft Docs
description: Use o aplicativo Take a Test em um perfil de configuração de dispositivo no Windows 10 e dispositivos posteriores no Microsoft Intune. Crie um perfil de configuração usando as configurações de Educação e insira uma URL do aplicativo de provas, escolha como os usuários fazem login, monitore a tela durante as provas e permita ou impeça sugestões de texto durante as provas.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3fc42193b461b8a0364e4ef2a2c34fe3e446ada3
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724003"
---
# <a name="use-the-take-a-test-app-on-windows-10-devices-in-microsoft-intune"></a>Usar o aplicativo Take a Test em dispositivos com Windows 10 no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Os perfis de Educação no Intune são projetados para os alunos realizarem um teste ou exame em dispositivos. Esse recurso inclui o aplicativo **Take a Test** e configurações para adicionar uma URL de teste, escolher como os usuários finais entrarão no teste e muito mais. Esse recurso dá suporte à seguinte plataforma:

- Windows 10 e posterior

Quando o usuário entra, o aplicativo Take a Test é aberto automaticamente com o teste que você inseriu. Nenhum outro aplicativo pode ser executado no dispositivo enquanto o teste estiver em andamento. [Realizar testes no Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) fornece mais detalhes sobre o aplicativo Take a Test.

Este artigo lista as etapas para criar um perfil de configuração de dispositivo no Microsoft Intune. Também inclui informações para saber mais sobre as configurações de educação disponíveis para seus dispositivos com Windows 10.

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: escolha **Windows 10 e posterior**.
    - **Perfil**: Escolha **Perfil de educação**.

4. Insira as configurações que você deseja definir:

    - [Windows 10 e posterior](education-settings-windows.md)

5. Selecione **OK** > **Criar** para salvar suas alterações.

Depois de você inserir suas configurações e criar o perfil, seu perfil será mostrado na lista de perfis. Em seguida, [atribua esse perfil a alguns grupos](device-profile-assign.md).

## <a name="next-steps"></a>Próximas etapas

Veja uma lista das [configurações de educação do Windows 10](education-settings-windows.md) e suas descrições.

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).