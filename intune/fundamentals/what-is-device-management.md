---
title: Gerenciamento de dispositivos no Microsoft 365
description: O Microsoft 365 Enterprise inclui o Microsoft Intune. Veja como o Intune fornece gerenciamento de dispositivo móvel e gerenciamento de aplicativos móveis para a sua organização. Leia cenários comuns e use o Intune para implantar o Microsoft 365 em seu ambiente.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/14/2019
ms.topic: conceptual
audience: ITPro
ms.service: microsoft-intune
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 25a3aab5472c91cd53e0cffbec2c870f51f60c79
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71735474"
---
# <a name="what-is-device-management"></a>O que é o gerenciamento de dispositivo? 

Uma tarefa essencial de qualquer Administrador é proteger os recursos e os dados de uma organização. Essa tarefa é o *gerenciamento de dispositivo*. Os usuários têm muitos dispositivos nos quais eles abrem e compartilham arquivos pessoais, visitam sites e instalam aplicativos e jogos. Esses mesmos usuários também são funcionários e alunos. Eles querem usar seus dispositivos para acessar recursos de trabalho e estudantis, como o OneNote e o email. O Gerenciamento de dispositivo permite às organizações proteger os recursos e os dados. 

Usando um provedor de gerenciamento de dispositivo, as organizações podem garantir que somente pessoas e dispositivos autorizados tenham acesso às informações proprietárias. Da mesma forma, os usuários de dispositivos podem se sentir à vontade para acessar dados de trabalho de seu próprio smartphone, pois sabem que seus dispositivos atendem aos requisitos de segurança da organização. Como uma organização, você pode perguntar – **O que podemos usar para proteger nossos recursos?**

A resposta é o [Microsoft Intune](what-is-intune.md). O Intune oferece MDM (gerenciamento de dispositivo móvel) e MAM (gerenciamento de aplicativo móvel). Algumas das tarefas principais de qualquer solução de MDM ou MAM são:

- Dar suporte a um ambiente móvel diversificado e gerenciar dispositivos iOS, Android, Windows e macOS com segurança.
- Garantir que dispositivos e aplicativos estejam em conformidade com os requisitos de segurança da sua organização.
- Criar políticas que ajudam a proteger os dados da empresa em dispositivos pessoais e de propriedade da empresa.
- Usar uma solução móvel unificada para impor essas políticas e ajudar a gerenciar dispositivos, aplicativos, usuários e grupos.

O Intune está incluído no Microsoft 365, e se integra ao Microsoft Azure AD (Azure Active Directory). O Microsoft Azure AD ajuda a controlar quem tem acesso e o que pode ser acessado.

## <a name="hello-intune"></a>Olá, Intune!
Muitas organizações, como a Microsoft, usam o Intune para proteger os dados proprietários que os usuários acessam em seus dispositivos móveis pessoais e de propriedade da empresa. O Intune inclui políticas de configuração de aplicativos e dispositivos, políticas de atualização de software e status de instalação (gráficos, tabelas e relatórios) para ajudar você a proteger e monitorar o acesso a dados.

É comum que as pessoas tenham vários dispositivos que usam plataformas diferentes. Por exemplo, um funcionário pode usar o Surface Pro para o trabalho e um dispositivo móvel Android em sua vida pessoal. E é comum acessar recursos organizacionais, como o Microsoft Outlook e o SharePoint, desses vários dispositivos.

Com o Intune, é possível gerenciar vários dispositivos por pessoa e as diferentes plataformas que são executadas em cada um deles, incluindo iOS, macOS, Android e Windows. O Intune separa as políticas e configurações por plataforma de dispositivo. Portanto, é fácil de gerenciar e exibir os dispositivos de uma plataforma específica.

**[Cenários comuns](common-scenarios.md)** é um excelente recurso para ver como o Intune responde a perguntas comuns ao trabalhar com dispositivos móveis. Você encontrará cenários sobre:  
- Proteger o email com o Exchange no Local
- Acessar o Office 365 de forma segura
- Usar dispositivos pessoais para acessar recursos organizacionais

## <a name="integration-with-secure-and-protect-services"></a>Integração com serviços de segurança e proteção
Uma tarefa essencial de qualquer solução de gerenciamento de dispositivo é fornecer segurança e proteção. O Intune realiza um excelente trabalho de integração com outros serviços para realizar essa tarefa. Por exemplo:

- O **Microsoft 365** é um componente fundamental para simplificar tarefas comuns de TI. No centro de administração do Microsoft 365, você deve criar usuários e gerenciar grupos. Você também obtém acesso a outros serviços, como Intune, Azure AD e muito mais.

  Por exemplo, crie um grupo de dispositivos iOS no Microsoft 365. Em seguida, pode usar o Intune para efetuar push das políticas para o grupo de dispositivos iOS com foco nos recursos iOS, como o acesso à App Store, o uso do AirDrop, o backup para o iCloud, o uso do filtro de Web da Apple e muito mais.

- O **Windows Defender** inclui muitos recursos de segurança para ajudar a proteger dispositivos Windows 10. Por exemplo, usando o Intune e o Windows Defender juntos, você pode: 

  - Habilite o [Windows Defender SmartScreen](../protect/endpoint-protection-windows-10.md) para procurar atividades suspeitas nos arquivos e aplicativos nos dispositivos móveis. 
  - Use [ATP (Proteção Avançada contra Ameaças) do Microsoft Defender](../protect/advanced-threat-protection.md) para ajudar a evitar violações de segurança em dispositivos móveis. E ajude a limitar o impacto de uma violação de segurança ao bloquear o acesso de um usuário a recursos corporativos.

- O **Acesso condicional** é um recurso do Azure Active Directory e se integra perfeitamente com o Intune. Usando o [Acesso condicional](../protect/conditional-access.md), garanta que somente dispositivos em conformidade tenham permissão para acessar o email, o SharePoint e outros aplicativos. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Escolha a solução de gerenciamento de dispositivo ideal para você

Há duas maneiras de abordar o gerenciamento de dispositivo. Primeiro, você pode gerenciar diferentes aspectos de dispositivos usando os recursos integrados do Intune. Essa abordagem é chamada de **MDM (gerenciamento de dispositivo móvel)** . Os usuários "registram" seus dispositivos e usam certificados para se comunicar com o Intune. Como um administrador de TI, você efetua push de aplicativos para dispositivos, restringe os dispositivos a um sistema operacional específico, bloqueia dispositivos pessoais e muito mais. Se um dispositivo for perdido ou roubado, você também poderá remover todos os dados do dispositivo. 

Na segunda abordagem, é possível gerenciar os aplicativos nos dispositivos. Essa abordagem é chamada de **MAM (gerenciamento de aplicativos móveis)** . Os usuários podem usar seus dispositivos pessoais para acessar recursos organizacionais. Ao abrir um aplicativo, como o email ou o SharePoint, é solicitado que os usuários realizem autenticação adicional. Se um dispositivo for perdido ou roubado, você poderá remover todos os dados da organização do dispositivo. 

Você também pode usar uma combinação de [MDM e MAM](byod-technology-decisions.md) juntos.

Ao configurar o Intune, você também pode optar por trabalhar exclusivamente no portal do Azure para gerenciar dispositivos ou usar o Intune e o Microsoft 365 juntos para gerenciar dispositivos. [Migrar o gerenciamento de dispositivo móvel para o Intune no portal do Azure](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) é um estudo de caso de TI da Microsoft. Neste estudo de caso, veja como a TI da Microsoft escolheu uma abordagem de gerenciamento de dispositivo moderna e leia as lições aprendidas.

## <a name="simplify-it-tasks-using-the-device-management-admin-center"></a>Simplificar as tarefas de TI usando o centro de administração do Gerenciamento de Dispositivo

O [centro de administração do Gerenciamento de Dispositivo](https://devicemanagement.microsoft.com/) é um ponto único centralizado para gerenciar e concluir as tarefas em seus dispositivos móveis. Este espaço de trabalho inclui os serviços usados para gerenciamento de dispositivos, incluindo o Intune e o Azure Active Directory, e também para gerenciar aplicativos de cliente. 

No centro de administração do gerenciamento de dispositivos, você pode:

- [Registrar dispositivos](../enrollment/device-enrollment.md)
- [Configurar a conformidade do dispositivo](../protect/device-compliance-get-started.md)
- [Gerenciar dispositivos](../remote-actions/device-management.md)
- [Gerenciar aplicativos](../apps/app-management.md)  
- [Livros eletrônicos do iOS](../apps/vpp-ebooks-ios.md)  
- [Instalar o conector local do Exchange](../protect/exchange-connector-install.md)  
- [Gerenciar funções](role-based-access-control.md)  
- Gerenciar atualizações de software
  - [Gerenciar as atualizações do Windows 10](../protect/windows-update-for-business-configure.md)  
  - [Gerenciar as atualizações do iOS](../protect/software-updates-ios.md)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Gerenciar usuários](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Gerenciar grupos e membros](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Solucionar problemas](help-desk-operators.md)

## <a name="next-step"></a>Próxima etapa

Quando estiver pronto para começar a usar uma solução de MDM ou MAM, percorra as diferentes etapas para configurar o Intune, registrar dispositivos e iniciar a criação de políticas. [Gerenciamento de dispositivo móvel para o Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) também é um excelente recurso.