---
title: Gerenciar computadores com software cliente no Microsoft Intune – Azure | Microsoft Docs
description: Gerenciar computadores Windows instalando o software cliente do Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8f481c17e6cb1285147c7f6361bfff73801b2bba
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736124"
---
# <a name="manage-windows-pcs-as-computers-via-intune-software-client"></a>Gerenciar computadores Windows como computadores por meio do cliente de software do Intune

[!INCLUDE [classic-portal](../../intune-classic/includes/classic-portal.md)]

> [!NOTE]
> Use o Microsoft Intune para gerenciar computadores Windows como [dispositivos móveis com o MDM (gerenciamento de dispositivo móvel)](../enrollment/windows-enroll.md) ou como computadores com o cliente de software do Intune, conforme descrito abaixo. No entanto, a Microsoft recomenda que os clientes usem a [solução de gerenciamento MDM](../enrollment/windows-enroll.md) sempre que possível. Para obter mais informações, consulte [Comparar o gerenciamento de computadores Windows como computadores ou dispositivos móveis](pc-management-comparison.md) 

O Intune fornece às organizações uma solução abrangente para gerenciar dispositivos móveis. O Intune pode gerenciar computadores Windows como dispositivos móveis usando os recursos modernos de gerenciamento de dispositivo integrados ao sistema operacional Windows 10. Para atender às necessidades de gerenciamento de sua organização, o Intune também pode gerenciar computadores Windows como computadores com o cliente de software do Intune. Esse método de gerenciamento usa recursos tradicionais de gerenciamento de computador no sistema operacional Windows herdado.

O cliente de software do Intune é mais adequado para computadores Windows que executam sistemas operacionais herdados, como o Windows 7, que não podem ser gerenciados como dispositivos móveis. O cliente de software do Intune usa recursos de gerenciamento como a Política de Grupo para gerenciar computadores na nuvem.

O Intune dá suporte ao gerenciamento de computadores Windows como computadores usando o cliente de software para até 7.000 PCs. Para implantações maiores, gerencie computadores Windows 10 como dispositivos móveis. Cada versão do Intune e atualização do Windows 10 inclui recursos de gerenciamento baseados na arquitetura de gerenciamento de dispositivo móvel. É altamente recomendável que você mude sua organização para o Windows 10 gerenciado como dispositivo móvel.


> [!NOTE]
> É possível gerenciar dispositivos com Windows 8.1 ou posterior como computadores, usando o software cliente do Intune, ou como dispositivos móveis. Não é possível usar os dois métodos no mesmo dispositivo. Pense cuidadosamente antes de decidir gerenciar computadores com o cliente de software do Intune. Este tópico se aplica somente ao gerenciamento de dispositivos como PCs executando o software cliente do Intune.

## <a name="requirements-for-intune-pc-client-management"></a>Requisitos para o gerenciamento de cliente de computador do Intune

**Hardware**:  
Veja a seguir os requisitos mínimos de hardware para instalar o software cliente do Intune:

|Requisito|Mais informações|
|---------------|--------------------|
|Rede|O cliente requer que o PC tenha conectividade com a Internet.|
|Processador e memória|Consulte os requisitos de RAM e de processador para o sistema operacional do PC.|
|Espaço em disco|200 MB de espaço em disco disponível antes de instalar o software cliente.|

**Software**:  
Veja a seguir os requisitos de software para a instalação do software cliente:

|Requisito|Mais informações|
|---------------|--------------------|
|Sistema operacional | Dispositivo Windows executando o Windows 7 SP1 e o Windows 8.1 ou posterior. </br></br>**Não há suporte para versões Home Edition.**|
|Permissões administrativas|A conta que instala o software cliente deve ter permissões de administrador local nesse dispositivo.|
|Windows Installer 3.1|O PC deve ter, no mínimo, o Windows Installer 3.1.<br /><br />Para exibir a versão do Windows Installer em um PC cliente:<br /><br />  No computador, clique com o botão direito do mouse em **%windir%\System32\msiexec.exe** e clique em **Propriedades**.<br /><br />Você pode baixar a versão mais recente do Windows Installer em [Windows Installer Redistributables](http://go.microsoft.com/fwlink/?LinkID=234258) no site do Microsoft Developer Network.|
|Remover o software cliente incompatível|Antes de instalar o software cliente do Intune, desinstale qualquer software cliente do Configuration Manager, do Operations Manager e do Service Manager do computador.|

> [!WARNING]
> A Microsoft anunciou que o [suporte ao Windows 7 termina no dia 14 de janeiro de 2020](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020). Nessa data, o Intune também desativa o suporte para dispositivos que executam o Windows 7. A Microsoft recomenda enfaticamente que você passe para o Windows 10 para impedir interrupções de serviço ou de suporte. 

## <a name="deploying-the-intune-software-client"></a>Implantar o cliente de software do Intune
Como administrador do Intune, você pode disponibilizar o cliente de software do Intune aos usuários de diversas formas. Para obter orientação, confira [Instalar o cliente de software do Intune em computadores Windows](../install-the-windows-pc-client-with-microsoft-intune.md).

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Recursos de gerenciamento do computador com o software cliente do Intune
Na maioria dos cenários, você registrará os dispositivos no Microsoft Intune, que fornece um maior conjunto de recursos. No entanto, você também pode gerenciar computadores usando o cliente de software Intune, que fornece os seguintes recursos:

- **[Gerenciamento de atualizações de software](../keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)** – você pode manter os computadores atualizados e decidir quando as atualizações são aplicadas.

- **[Política de Firewall do Windows](../help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md)** – ajuda a garantir que nenhum computador usado pela sua empresa tenha um Firewall do Windows inativo ou configurado incorretamente.

- **[Proteção antimalware](../help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)** – o Intune conta com o Endpoint Protection, que ajuda a proteger seus computadores contra malware.

- **[Assistência remota](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)** – o Intune permite que os usuários entrem em contato com a equipe de suporte de TI, que poderá fornecer assistência usando um recurso de área de trabalho remota que está incluído no Intune (requer o software TeamViewer).

- **[Gerenciamento de licenças de software](../manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)** – controle quantas licenças de software estão disponíveis e quantas licenças disponíveis estão sendo usadas.
- **[Implantação de aplicativo](add-apps-for-windows-pcs-in-microsoft-intune.md)** – implante software nos computadores que você gerencia. Alguns recursos de gerenciamento de aplicativos não estão disponíveis quando você gerencia computadores com o cliente de software.

<!-- - **Compliance settings reporting** -->

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Políticas e implantações de aplicativo do software cliente do Intune

Embora o software cliente do Intune dê suporte a [funcionalidades de gerenciamento que ajudam a proteger computadores](policies-to-protect-windows-pcs-in-microsoft-intune.md) gerenciando atualizações de software, o Firewall do Windows e o Endpoint Protection, computadores gerenciados com o software cliente do Intune não podem ser afetados por outras políticas do Intune, incluindo as configurações de política do **Windows** específicas ao gerenciamento de dispositivo móvel.

Ao usar o software cliente do Intune para gerenciar computadores Windows, você pode usar apenas as políticas mostradas na seção **Gerenciamento de Computador**.

O Intune gerencia computadores Windows usando as políticas de modo semelhante ao usado pelos GPOs (objetos de política de grupo) do AD DS (Active Directory Domain Services) do Windows Server. Se você gerenciar computadores ingressados no domínio do Active Directory com o Intune, [verifique se as políticas do Intune não entram em conflito com outros GPOs](resolve-gpo-and-microsoft-intune-policy-conflicts.md) usados em sua organização. Para ler mais, confira [Política de Grupo para iniciantes](https://technet.microsoft.com/library/hh147307.aspx).

  ![Selecione o modelo para a nova política de computador Windows](./media/manage-windows-pcs-with-microsoft-intune/select-template-for-pc-policy.png)

Ao implantar aplicativos, você pode usar apenas o Windows Installer (.exe, .msi).

  ![Selecione a plataforma e um local para os arquivos de software cliente do computador](./media/manage-windows-pcs-with-microsoft-intune/select-platform-of-software-files-for-pc-agent.png)

## <a name="common-tasks-for-windows-pcs"></a>Tarefas comuns para computadores Windows

Você pode usar o console de administração do Intune para realizar outras tarefas comuns de gerenciamento de computador em computadores Windows que têm o cliente instalado:
- [Usar políticas para simplificar o gerenciamento de computador](use-policies-to-simplify-windows-pc-management.md) - descreve as políticas do **Gerenciamento do Computador** do Intune e lista as configurações para o Microsoft Intune Center.

- [Exibir inventário de hardware e software para computadores Windows](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md) - explica como criar um relatório que lista informações sobre os recursos de hardware de computadores e o software instalado neles. Também explica como atualizar o inventário de computador para garantir que ele seja atual.
- [Desativar um computador Windows](retire-a-windows-pc-with-microsoft-intune.md) - lista as etapas para desativar um computador Windows e descreve o que acontece quando você desativa um computador.
- [Gerenciar a vinculação de usuário e dispositivo para computadores Windows](../manage-user-device-linking-for-windows-pcs-with-microsoft-intune.md) – explica quando e como você precisa vincular um usuário a um computador antes de implantar o software no usuário.
- [Solicitar e fornecer assistência remota para computadores Windows](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md) - explica como os usuários de computadores Intune obtêm Ajuda da assistência remota e descreve os pré-requisitos e a instalação do TeamViewer.

Para obter mais informações sobre as tarefas acima, consulte [tarefas comuns de gerenciamento do computador](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

## <a name="management-limitations-of-the-intune-client-software"></a>Limitações de gerenciamento do software cliente do Intune

Algumas opções de gerenciamento, que podem ser usadas para gerenciar computadores como dispositivos móveis, não podem ser usadas para computadores gerenciados com o software cliente do Intune:

- Apagamento completo (o apagamento seletivo está disponível)
- Acesso condicional

Além disso, observe que no console de administração do Intune, determinadas seções, como **Atualizações**, **Proteção** e **Licenças** serão exibidas somente se os dispositivos tiverem sido registrados com o cliente de software do Intune.

  ![Itens do console de administração que aparecem somente para clientes de computadores](./media/manage-windows-pcs-with-microsoft-intune/admin-console-settings-only-for-pc-agent.png)

## <a name="help-with-troubleshooting"></a>Ajuda com solução de problemas

O software cliente do Intune geralmente é executado silenciosamente, em segundo plano, sem necessidade de muita interação do usuário ou solução de problemas. Se você precisar solucionar problemas de gerenciamento de computador, verifique os logs. O software cliente do Intune e seus logs correspondentes são instalados no diretório %Program Files%\Microsoft\OnlineManagement.

Examine também o [registro de dispositivos](../enrollment/device-enrollment.md) para obter mais informações sobre como registrar dispositivos no Microsoft Intune.