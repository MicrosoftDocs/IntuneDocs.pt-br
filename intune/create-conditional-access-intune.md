---
title: Configurar o acesso condicional baseado em dispositivo usando o Intune
titlesuffix: Microsoft Intune
description: Saiba como criar uma política de acesso condicional baseada em dispositivo com base na conformidade de dispositivo do Microsoft Intune e no gerenciamento de aplicativo móvel.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 03ca9a65d5a62c75c45541b42c9b2aa5c4871a18
ms.sourcegitcommit: e0374b3ced83c8876a4f78b326869c10588a55e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56307780"
---
# <a name="create-a-device-based-conditional-access-policy"></a>Criar uma política de acesso condicional baseada em dispositivo

Com o Intune, você pode aprimorar o acesso condicional no Azure Active Directory adicionando conformidade de dispositivo móvel aos controles de acesso. Depois de criar uma política de conformidade do Intune que define os requisitos para conformidade dos dispositivos, use o status de conformidade do dispositivo para permitir ou bloquear o acesso aos seus aplicativos e serviços. Você pode fazer isso criando uma política de acesso condicional que usa a configuração **Exigir que o dispositivo seja marcado como em conformidade**. 

Uma política de acesso condicional especifica o aplicativo ou serviços que você quer proteger, as condições sob as quais os aplicativos ou serviços podem ser acessados e os usuários aos quais a política se aplica. Acesso condicional é um recurso premium do Azure AD que pode ser configurado no Azure Active Directory, mas você também pode configurar essas mesmas políticas de dentro do portal do Intune. 

> [!IMPORTANT]
> Antes de configurar o acesso condicional, você precisará configurar políticas de conformidade de dispositivo do Intune para avaliar dispositivos com base nos requisitos específicos. Confira [Introdução às políticas de conformidade do dispositivo no Intune](device-compliance-get-started.md).

## <a name="create-conditional-access-policy"></a>Criar política de acesso condicional

1.  No portal do Intune, selecione **Acesso condicional** > **Políticas** > **Nova Política**.
   
    ![Criar uma nova política de acesso condicional](media/create-conditional-access-intune/create-ca.png)
 
2.  Em **Atribuições**, selecione **Usuários e Grupos**. 
3.  Na guia **Incluir**, identifique os usuários ou grupos aos quais você deseja aplicar essa política de acesso condicional. Depois de escolher quem incluir, use a guia **Excluir** se houver usuários, funções ou grupos que você deseja excluir desta política.  
    - **Todos os usuários**: Selecione esta opção para aplicar a política a todos os usuários e grupos, incluindo usuários internos e convidados.
  
    - **Selecione usuários e grupos**: Selecione esta opção e especifique uma ou mais das seguintes opções:
  
      a. **Todos os usuários convidados**: Selecione esta opção para incluir ou excluir usuários convidados externos (por exemplo, parceiros, colaboradores externos)
       
      b. **Funções de diretório**: Selecione uma ou mais funções do Azure AD para incluir ou excluir os usuários que recebem essas funções.
      
      c. **Usuários e grupos**: Selecione esta opção para pesquisar e selecionar usuários individuais ou grupos que você quer incluir ou excluir.
     
       > [!TIP]  
       > Teste a política em um grupo menor de usuários para verificar se que ela funciona conforme o esperado.
4.  Selecione **Concluído**.
5.  Em **Atribuições**, selecione **Aplicativos de nuvem**. 
6.  Na guia **Incluir**, identifique os aplicativos e serviços que você deseja proteger com essa política de acesso condicional. Em seguida, use a guia **Excluir** se houver aplicativos ou serviços a serem excluídos dessa política.
    - **Todos os aplicativos em nuvem**: Selecione esta opção para aplicar a política a todos os aplicativos.
      > [!IMPORTANT]  
      > O aplicativo de Gerenciamento do Microsoft Azure para acessar o portal do Azure está incluído nessa lista. Use a guia **Excluir** aqui ou nas opções de **Usuários e grupos** para garantir que você (ou os usuários ou grupos designados) poderá entrar no portal do Azure. 

    - **Selecionar aplicativos**: Selecione essa opção, escolha **Selecionar** e use a lista de aplicativos para pesquisar e selecionar os aplicativos ou serviços que você deseja proteger.
    
      ![Criar uma nova política de acesso condicional](media/create-conditional-access-intune/create-ca-select-apps.png)

7.  Selecione **Concluído**.
8.  Em **Atribuições**, selecione **Condições**.
    - **Risco de entrada**: Escolha Sim para usar a detecção de risco de entrada do Azure AD Identity Protection com essa política e, em seguida, escolha os níveis de risco de entrada aos quais a política deve ser aplicada.
    - **Plataformas de dispositivo**: Na guia **Incluir**, identifique as plataformas de dispositivo aos quais essa política de acesso condicional se aplica. Use a guia **Excluir** para excluir plataformas dessa política.
    - **Locais**: Na guia **Incluir**, especifique se a política se aplica a qualquer local, os locais de rede confiáveis que estão sob o controle do seu departamento de TI ou locais de rede específicos. Use a guia **Excluir** para excluir locais de rede dessa política. 
    - **Aplicativos cliente**: Escolha **Sim** para especificar se a política deve ser aplicada a aplicativos de navegador, aplicativos móveis e clientes de desktop. Você também pode selecionar **Clientes de autenticação moderna** (como o Outlook para iOS ou o Outlook para Android) e **clientes do Exchange ActiveSync**.
    - **Estado do dispositivo**: A política de acesso condicional será aplicada a todos os estados de dispositivo, a menos que você escolha Sim e exclua especificamente os estados Dispositivo ingressado no Azure AD Híbrido ou Dispositivo marcado como em conformidade (ou ambos).
    
      ![Criar uma nova política de acesso condicional](media/create-conditional-access-intune/create-ca-device-platforms.png)

      > [!TIP]  
      > Se você quiser proteger os clientes de **Autenticação moderna** e **clientes do Exchange ActiveSync**, crie duas políticas de acesso condicional separadas, um para cada tipo de cliente. Embora o Exchange ActiveSync ofereça suporte à autenticação moderna, a única condição compatível com o Exchange ActiveSync é a plataforma. Outras condições, incluindo a autenticação multifator, não têm suporte. Para proteger com eficiência o acesso ao Exchange Online pelo Exchange ActiveSync, crie uma política de acesso condicional que especifica o aplicativo de nuvem do Office 365 Exchange Online e o aplicativo cliente do Exchange ActiveSync com a opção Aplicar política somente em plataformas selecionada.

9.  Selecione **Concluído**.
10. Em **Controles de acesso**, selecione **Conceder**. Configure o que acontece com base nas condições configuradas.  Selecione entre as opções a seguir:
    - **Bloquear o acesso**: Os usuários especificados nesta política não terão acesso aos aplicativos sob as condições que você especificou.
    - **Conceder acesso**: Os usuários especificados nesta política receberão acesso, mas você pode exigir qualquer uma das ações adicionais a seguir:
      - **Exigir autenticação multifator**: O usuário precisará cumprir requisitos de segurança adicionais, como uma chamada telefônica ou SMS.
      - **Exigir que o dispositivo seja marcado como em conformidade**: O dispositivo deve estar em conformidade com o Intune. Se o dispositivo não estiver em conformidade, o usuário terá a opção de registrar o dispositivo no Intune. 
      - **Exigir um dispositivo ingressado no Azure AD Híbrido**: Os dispositivos devem ser ingressados no Azure AD Híbrido.
      - **Exigir o aplicativo cliente aprovado**: O dispositivo deve usar aplicativos cliente aprovados. 
      - **Para vários controles**: Selecione **Exigir todos os controles selecionados** para que todos os requisitos acima sejam aplicados quando um dispositivo tentar acessar o aplicativo.
    
      ![Configurações de Concessão dos controles de acesso](media/create-conditional-access-intune/create-ca-grant-access-settings.png)
 
11. Em **Habilitar política**, selecione **Ativado**.
     
     ![Habilitar a política](media/create-conditional-access-intune/enable-policy.png)

12. Selecione **Criar**.

## <a name="see-also"></a>Consulte também
[Acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md)