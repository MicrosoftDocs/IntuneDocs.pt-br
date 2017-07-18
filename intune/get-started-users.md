---
title: "Introdução aos usuários"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fc1c4f6d18fd78f455be8e333bb765080184c908
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# Introdução aos usuários
<a id="get-started-with-users" class="xliff"></a>

![Um usuário genérico no Azure](/intune/media/generic-intune-user.png)

O Azure AD gerencia os grupos de objetos – como dispositivos e aplicativos – da sua organização. Você pode agrupar usuários ou dispositivos em vez de precisar gerenciar cada dispositivo individualmente. Isso permite atribuir facilmente aplicativos e configurações para um grande número de usuários e dispositivos.

## Como eu crio um usuário?
<a id="how-do-i-create-a-user" class="xliff"></a>

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Usando **Pesquisar recursos**, pesquise **Usuários e grupos**.
3. Depois de abrir a folha **Usuários e grupos**, selecione **Todos os usuários** e **+ Novo usuário**.
4. Insira os detalhes do usuário, como **Nome** e **Nome de usuário**. A parte do nome de domínio do nome de usuário deve ser o nome de domínio inicial padrão “contoso.onmicrosoft.com” ou um nome de domínio não federado verificado como “contoso.com”.
5. Em **Grupos**, escolha o grupo de teste ao qual o usuário será adicionado.
6. Salve a senha do usuário gerada automaticamente para que você possa usá-la para fazer logon em um dispositivo de teste. Você deve fornecer essa senha para usuários para que eles podem alterá-la para uma senha normal que pode ser lembrada.
7. Na folha **Usuário**, selecione **Criar**.

## Atribuir licenças a usuários
<a id="assigning-licenses-to-users" class="xliff"></a>

Depois de criar um usuário, será necessário usar o [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para atribuir uma licença do Intune a esse usuário. Sem atribuir uma licença, não será possível registrar seus dispositivos no gerenciamento.

1. Entre no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) com as mesmas credenciais que você usou para entrar no Intune.
2. Selecione **Usuários** > **Usuários Ativos** e selecione o usuário que você criou anteriormente.
3. Pode ser necessário aguardar um pouco para que todas as informações do usuário sejam carregadas. Depois de carregadas, selecione **Editar** nas **Licenças de produto** do usuário.
4. Atribua um **Local** ao usuário e mude o Intune para **ativado**.

 > [!NOTE]
 > Isso usa uma das suas licenças para este usuário. Se você estiver usando o ambiente em tempo real, poderá desligar o uso dessa licença mais tarde para reatribuí-la a um usuário real.

5. Selecione **Salvar**.