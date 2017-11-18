---
title: Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10
titlesuffix: Azure portal
description: Aprenda a carregar scripts do PowerShell no Intune para executar em dispositivos Windows 10.
keywords: 
author: dougeby
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 237d6d090d0aae7f9a0853839b72d55618f4607e
ms.sourcegitcommit: af958afce3070a3044aafea490c8afc55301d9df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2017
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10
A extensão de gerenciamento do Intune permite que você carregue scripts do PowerShell no Intune para serem executados em dispositivos Windows 10. A extensão de gerenciamento complementa os recursos de gerenciamento de dispositivo móvel (MDM) do Windows 10 e facilita a mudança para o gerenciamento moderno.

## <a name="moving-to-modern-management"></a>Mover para o gerenciamento moderno
O computador do usuário final está passando por uma transformação digital. A TI clássica tradicional concentra-se em uma plataforma de dispositivo único, em dispositivos de negócios, em usuários que trabalham no escritório e em uma variedade de processos de TI manuais e reativos. No entanto, o local de trabalho moderno habilita diversas plataformas de dispositivos que são de propriedade do usuário e dos negócios, permite que usuários trabalhem de qualquer lugar e fornece processos de TI automatizados e proativos. 

Serviços de MDM, como o Microsoft Intune, podem gerenciar dispositivos Windows 10 usando o protocolo MDM. O cliente de gerenciamento interno do Windows 10 pode se comunicar com o Intune para executar tarefas de gerenciamento da empresa. Ele o ajuda a migrar para o gerenciamento moderno em dispositivos Windows 10. No entanto, há determinados recursos que talvez sejam necessários, como configuração avançada de dispositivo, solução de problemas e gerenciamento de aplicativo Win32 herdado que atualmente não estão disponíveis no Windows 10 MDM. Para esses recursos, você pode executar o cliente de software do Intune em seus dispositivos Windows 10. Como resultado, você não pode usar os novos recursos que o Windows 10 fornece. [Compare as diferenças entre o cliente de software do Intune e o MDM do Windows 10](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).

A extensão de gerenciamento do Intune complementa os recursos de MDM internos do Windows 10. Você pode criar scripts do PowerShell para executar nos dispositivos Windows 10 que fornecem os recursos necessários. Por exemplo, você pode criar um script do PowerShell que instala um aplicativo Win32 herdado em seus dispositivos Windows 10, carregar o script no Intune, atribuir o script a um grupo do Azure AD (Active Directory) e executar o script em dispositivos Windows 10. Em seguida, você pode monitorar o status de execução do script em dispositivos Windows 10 do início ao fim.

## <a name="prerequisites"></a>Pré-requisitos
A extensão de gerenciamento do Intune tem os seguintes pré-requisitos:
- Os dispositivos devem ser associados ao Azure AD
- Os dispositivos devem executar o Windows 10 versão 1607 ou posterior

## <a name="create-a-powershell-script-policy"></a>Criar uma política de script do PowerShell 
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
4. Na folha **Configuração do Dispositivo**, escolha **Gerenciar** > **scripts do PowerShell**.
5. Na folha **scripts do PowerShell**, escolha **Adicionar script**.
6. Na folha **Adicionar Script do PowerShell**, insira um **Nome** e **Descrição** para o script do PowerShell.
7. Para **Local do script**, procure pelo script do PowerShell. O script deve ter menos de 10 KB (ASCII) ou 5 KB (Unicode).
8. Escolha **Configurar** e, em seguida, escolha se deseja executar o script com as credenciais do usuário no dispositivo (**Sim**) ou com o contexto de sistema (**Não**). Por padrão, o script é executado no contexto do sistema. Selecione **Sim**, a menos que seja necessário executar o script no contexto do sistema. 
  ![Folha Adicionar script do PowerShell](./media/mgmt-extension-add-script.png)
9. Escolha se o script deve ser assinado por um distribuidor confiável (**Sim**). Por padrão, não há nenhum requisito para o script ser assinado. 
10. Clique em **OK** e, em seguida, clique em **Criar** para salvar o script.

## <a name="assign-a-powershell-script-policy"></a>Atribuir uma política de script do PowerShell
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
4. Na folha **Configuração do Dispositivo**, escolha **Gerenciar** > **scripts do PowerShell**.
5. Na folha **Scripts do PowerShell**, selecione o script para atribuir e, em seguida, selecione **Gerenciar** > **Atribuições**.
  ![Folha Adicionar script do PowerShell](./media/mgmt-extension-assignments.png)
 
6. Escolha **Selecionar Grupos** para listar os grupos disponíveis do Azure AD. 
7. Selecione os grupos e, em seguida, clique em **Selecionar** para atribuir a política aos grupos selecionados.

A extensão de gerenciamento do Intune é sincronizada com o Intune uma vez a cada hora. Depois de atribuir a política aos grupos do Azure AD, o script do PowerShell é executado e os resultados da execução são relatados. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>Monitorar status de execução para scripts do PowerShell
Você pode monitorar o status de execução de scripts do PowerShell para usuários e dispositivos no portal do Azure.
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
4. Na folha **Configuração do Dispositivo**, escolha **Gerenciar** > **scripts do PowerShell**.
5. Na folha **Scripts do PowerShell**, selecione o script a ser monitorado, escolha **Monitorar** e, em seguida, um dos seguintes relatórios:
   - **Status do dispositivo**
   - **Status do usuário**