---
title: Configurar a integração do Pradeo com o Intune
titleSuffix: Intune on Azure
description: Integração do conector do Pradeo com o Intune
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 82872ba6-80f8-4cc9-adf4-0ccd8ff26dd2
ms.openlocfilehash: 223161bd12f40b3539ce2502599eb3324c7458ca
ms.sourcegitcommit: f70d6aaea59b52cd0d7bd3008afd243868967fd6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37067416"
---
# <a name="integrate-pradeo-with-intune"></a>Integrar o Pradeo ao Intune

Conclua as etapas a seguir para integrar a solução de Defesa contra Ameaças Móveis do Pradeo ao Intune.

## <a name="before-you-begin"></a>Antes de começar

> [!NOTE]
> As etapas a seguir devem ser concluídas no [console de Segurança do Pradeo](https://www.apps-security.com).

Antes de iniciar o processo de integração do Pradeo ao Intune, verifique se você tem o seguinte:

-   Assinatura do Microsoft Intune

-   Credenciais de administrador do Azure Active Directory para conceder as seguintes permissões:

    -   Entrada e leitura de perfil do usuário

    -   Acessar diretório como o usuário conectado

    -   Ler dados do diretório

    -   Enviar informações do dispositivo para o Intune

-   Credenciais do administrador para acessar o console de Segurança do Pradeo.

### <a name="pradeo-app-authorization"></a>Autorização de aplicativo do Pradeo

O processo de autorização de aplicativo do Pradeo é o seguinte:

-   Permitir que o serviço do Pradeo comunique informações relacionadas ao estado de integridade do dispositivo novamente para o Intune.

-   Sincronizar o Pradeo com a associação ao Grupo de Registro do Azure AD para popular o banco de dados do dispositivo.

-   Permitir que o console de administrador do Pradeo use o SSO (Logon Único) do Azure AD.

-   Permitir que o aplicativo Pradeo se conecte usando o SSO do Azure AD.

## <a name="to-set-up-pradeo-integration"></a>Para configurar a integração do Pradeo

1.  Acesse o [console de Segurança do Pradeo](https://www.apps-security.com) e entre com suas credenciais.

2.  Escolha **Administração – Enterprise Mobility Management** no menu.

3.  Escolha o **logotipo do Intune**.

4.  Na janela **EMM (Enterprise Mobility Management) – Intune**, na **Etapa 1**, escolha o botão **Conector do Pradeo**. 

    ![Janela do EMM Intune no Pradeo](./media/pradeo_setup.png)

5. Na janela de conexão do Microsoft Intune, insira suas credenciais do Intune.

5.  A página da Web do Pradeo será reaberta. Na **Etapa 2**, escolha o botão **Integridade do Dispositivo do Pradeo**.

7. Na janela do Conector do Pradeo-Intune, selecione **Aceitar**. 

8. Na janela do conector de API de dispositivo do Pradeo, selecione **Aceitar**.

9. A página da Web do Pradeo será reaberta. Na **Etapa 3**, escolha o botão **Conectar-se à Microsoft**. 

10. Na janela de autenticação do Microsoft Intune, insira suas credenciais do Intune.

11. Quando a mensagem **Integração bem-sucedida** for exibida, a integração estará concluída.

## <a name="next-steps"></a>Próximas etapas

-   [Configurar aplicativos do Pradeo](mtd-apps-ios-app-configuration-policy-add-assign.md)