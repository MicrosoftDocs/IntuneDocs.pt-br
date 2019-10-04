---
title: Início Rápido – Política de conformidade de senha para dispositivos Android
titleSuffix: Microsoft Intune
description: Neste início rápido, você usará o Microsoft Intune para configurar um comprimento de senha obrigatório para dispositivos Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c2969c57a598acbc0239e07d4ed347739c9719c2
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726850"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Início Rápido: Criar uma política de conformidade de senha para dispositivos Android

Neste início rápido, você usará o Microsoft Intune para exigir que os usuários do Android da sua equipe de trabalho insiram uma senha de comprimento específico antes de conceder acesso às informações em seus dispositivos Android. 

Uma política de conformidade de dispositivos do Intune especifica as regras e configurações que dispositivos precisam cumprir para serem considerados em conformidade. Você pode usar as políticas de conformidade com Acesso Condicional para permitir ou bloquear o acesso aos recursos da empresa. Você também pode obter relatórios de dispositivo e realizar ações de não conformidade.

> [!IMPORTANT]
> Além das configurações de senha, você também deve considerar outras configurações de segurança do sistema para proteger sua força de trabalho. Saiba mais em [Configurações de segurança do sistema](compliance-policy-create-android-for-work.md).

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune. 

## <a name="create-a-device-compliance-policy"></a>Criar uma política de conformidade do dispositivo

Para este início rápido, você usará o Intune para exigir que os usuários do Android da sua equipe de trabalho insiram uma senha de comprimento específico antes de conceder acesso às informações em seus dispositivos Android.

1. No Intune, selecione **Conformidade do dispositivo** > **Políticas** > **Criar política**.
2. Adicione **Conformidade do Android** como o **Nome**. Além disso, adicione uma **Descrição**.
3. Para **Plataforma**, selecione **Android**. 
4. Selecione **Configurações** > **Segurança do Sistema** para exibir a folha **Segurança do Sistema** do Android.
5. Clique em **Exigir** ao lado de **Exigir uma senha para desbloquear dispositivos móveis**.
6. Selecione **Ao menos numérico** ao lado de **Tipo de senha obrigatório**.
7. Insira **6** ao lado de **Comprimento mínimo da senha**. 

    ![Captura de tela da criação de um grupo no Microsoft Intune](./media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. Quando terminar, clique em **Ok** > **Ok** > **Criar** para criar a política.

Após criar a política com êxito, ela aparecerá na sua lista de políticas de conformidade do dispositivo. 

## <a name="clean-up-resources"></a>Limpar os recursos

Quando ela não for mais necessária, exclua a política. Para fazer isso, selecione a política de conformidade e clique em **Excluir**.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você usou o Intune para criar uma política de conformidade para os dispositivos Android da sua força de trabalho para exigir uma senha com pelo menos seis caracteres de comprimento. Para obter mais informações sobre as políticas de conformidade de criação, confira [Introdução às políticas de conformidade do dispositivo no Intune](device-compliance-get-started.md).

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início rápido: Enviar notificações para dispositivos não compatíveis](../quickstart-send-notification.md)