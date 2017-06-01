---
title: "Implantar aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS | Microsoft Docs"
description: "Implante aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS no console clássico do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 19c8ca7bbfe19649585d63ce2c0c96a8f57b3739
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Implantar aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração de aplicativo iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Antes de começar

-   As etapas a seguir devem ser concluídas no [console clássico do Intune](https://manage.microsoft.com/).

-   Use a mesma conta do Azure AD previamente configurada no Console de gerenciamento do Skycure, que deve ser a mesma conta usada para fazer logon no console clássico do Intune.

-   Verifique se que você está familiarizado com o processo de:

    -   [Implantar um aplicativo com o Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Implantar a política de configuração de aplicativo do iOS](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Para implantar aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração de aplicativo do iOS

1.  No console clássico do Intune, escolha **Aplicativos** &gt; **Aplicativos** para exibir a lista de aplicativos que você pode gerenciar.

2.  Selecione os seguintes aplicativos:

    a.  Microsoft Authenticator

    b.  Aplicativo Skycure para Android

    c.  Aplicativo Skycure para iOS

       ![Todos os aplicativos do console clássico do Intune para implantar](../media/mtp/skycure-deploy-app-1.png)

3.  Escolha **Gerenciar Implantações**, selecione o grupo de segurança do Azure AD que tenha os usuários do Skycure, clique em **Avançar**.

4.  Na página **Ação de Implantação**, selecione a opção **Instalação Necessária** do menu suspenso **Aprovação**e clique em **Avançar**.

    ![Ação de implantação do console clássico do Intune](../media/mtp/skycure-deploy-app-2.png)

5.  Na página **Perfil de VPN**, selecione a opção **Nenhum** na lista suspensa **Política de VPN** e, em seguida, clique em **Avançar**.

6.  Na página **Configuração de Aplicativo Móvel**, selecione a Política de Configuração de Aplicativo do iOS criada anteriormente na lista suspensa **Política de Configuração do Aplicativo** e, em seguida, clique em **Concluir**.

    ![Configuração de aplicativo móvel do console clássico do Intune](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Próximas etapas

[Configurar a integração do Skycure com o Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)
