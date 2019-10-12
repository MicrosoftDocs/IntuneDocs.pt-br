---
title: Desativar um computador Windows
titleSuffix: Microsoft Intune
description: Como desativar um computador Windows gerenciado pelo Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: f41194f7a0f8de9fd1a0d6803ad63a2f253b89bf
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732939"
---
# <a name="retire-a-windows-pc"></a>Desativar um computador Windows

[!INCLUDE [classic-portal](../../intune-classic/includes/classic-portal.md)]

Use as etapas a seguir para desativar áreas de trabalho gerenciadas como computadores executando o cliente de software do Intune nelas. Ao desativar um computador, ele é removido do gerenciamento do Intune. Você não pode apagar um computador do Intune para defini-lo novamente para as configurações originais de fábrica.

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contém o computador que você deseja desativar).

2. Selecione os dispositivos que deseja desativar e escolha **Desativar/Apagar**.

Para registrar um computador novamente no Intune, reinstale o cliente de software no computador usando as diretrizes em [Instalar o cliente de computador Windows com o Microsoft Intune](../install-the-windows-pc-client-with-microsoft-intune.md).

Se um computador não conseguir se conectar ao Intune, será exibida uma mensagem no workspace **Painel**.

Ao desativar um computador:

- Ele é removido do inventário e gerenciamento do Intune e a licença associada ao computador é disponibilizada para reutilização. O recurso Desativar/Apagar remove o cliente de software do Intune, mas não remove aplicativos nem dados do computador. Essa desativação não executa um apagamento completo no computador.

- Seu status não é mais exibido no console do Intune.

- O Intune remove o cliente de software do computador. Se o computador não estiver conectado ao serviço Intune, o cliente de software será removido na próxima conexão.

- O Microsoft Intune Endpoint Protection é removido do computador. Se o computador tiver outro aplicativo de ponto de extremidade instalado e ele estiver desabilitado, o aplicativo poderá ser habilitado novamente depois que o Microsoft Intune Endpoint Protection for removido, a fim de garantir que o computador está protegido.

- Todas as políticas são removidas do computador e os valores definidos pela política serão alterados.

- O computador não receberá mais atualizações de software nem atualizações de definições de malware do serviço Intune.

- Dependendo de como estiverem configurados, os computadores desativados poderão continuar recebendo atualizações usando o Windows Server Update Services, Windows Update ou Microsoft Update.

    > [!IMPORTANT]
    > Se o software cliente tiver sido instalado com o uso de um GPO (Objeto de Política de Grupo), antes de remover o software cliente você deve remover o GPO para evitar que o software seja reinstalado.

    Se a desinstalação do cliente Endpoint Protection falhar, leia [Troubleshoot Endpoint Protection in Microsoft Intune](/intune/troubleshoot-endpoint-protection-in-microsoft-intune) (Solucionar problemas do Endpoint Protection no Intune) para obter mais ajuda.

## <a name="see-also"></a>Consulte também

[Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)