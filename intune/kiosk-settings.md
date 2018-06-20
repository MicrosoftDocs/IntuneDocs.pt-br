---
title: Configurações de quiosque para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Conheça as configurações do Microsoft Intune que você pode usar para controlar as configurações e as funcionalidades de dispositivos que executam o Windows 10.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 897ff48253961d6e1aa83bf36113c362d4548fbf
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745106"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Configurações de quiosque para Windows 10 (e posteriores) no Intune

Perfis de quiosque podem ser usados para configurar dispositivos Windows 10 para executarem um ou vários aplicativos. Quando você configura um perfil de quiosque, também escolhe se é mostrado um menu de início, se um navegador da Web está instalado e mais opções.

## <a name="kiosk-settings"></a>Configurações do quiosque

1. Selecione **Adicionar** para criar um ambiente de quiosque.
2. Insira um **Nome de configuração de quiosque** para o seu quiosque. Esse nome identifica um grupo de aplicativos, o layout desses aplicativos no menu inicial e os usuários atribuídos a essa configuração de quiosque.
3. Selecione o **Modo de quiosque**. **Modo de quiosque** Identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

  - **Não Configurado** (padrão): a política não habilita um modo de quiosque.
  - **Quiosque de aplicativo único de tela inteira**: o perfil permite que o dispositivo seja executado como uma conta de usuário única e bloqueia-a para um único aplicativo UWP (Plataforma Universal do Windows). Assim, quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.
  - **Quiosque multiaplicativo**: o perfil permite que o dispositivo execute vários aplicativos UWP (Plataforma Universal do Windows) ou aplicativos Win32. Você também pode atribuir diferentes aplicativos para diferentes contas de usuário. Somente os aplicativos que você adiciona estão disponíveis ao usuário. O benefício de um quiosque de vários aplicativos ou de um dispositivo com finalidade fixa é proporcionar uma experiência fácil para os usuários ao possibilitar acesso somente aos aplicativos de que eles precisam. E também removendo da exibição os aplicativos de que eles não precisam.

#### <a name="single-full-screen-app-kiosks"></a>Quiosques aplicativo de tela inteira único
Insira as seguintes configurações:

- **Identificador de aplicativo UWP (Plataforma Universal do Windows)**: insira o **AUMID (ID do modelo de usuário do aplicativo)** do aplicativo de quiosque. Ou selecione um aplicativo gerenciado existente que você tenha adicionado usando [Aplicativos Móveis](apps-add.md).

    Consulte [Encontrar a ID do modelo de usuário do aplicativo de um aplicativo instalado](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

- **Tipo de conta de usuário**: suas opções:

  - **Logon automático**: para quiosques em ambientes voltados para o público com logon automático habilitado, um usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Para configurar uma conta do Azure AD (Active Directory) para o modo de quiosque, use o formato `AzureAD\user@contoso.com`.
  - **Conta de usuário local**: insira a conta de usuário local (para o dispositivo) ou o logon da conta do Azure AD associado ao aplicativo de quiosque. Para contas ingressadas em domínios do Azure AD, especifique a conta usando o formato `domain\username@tenant.org`.

#### <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos
Os aplicativos nesse modo estão disponíveis no menu Iniciar. Esses aplicativos são os únicos aplicativos que o usuário pode abrir. 

[Quiosques de vários aplicativos](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) usam uma configuração de quiosque que lista os aplicativos permitidos e outras configurações.

Insira as seguintes configurações:

- **Adicionar Aplicativo Win32**: um aplicativo Win32 é um aplicativo da área de trabalho tradicional. Insira o **Nome do aplicativo** e o **Identificador**. O **Identificador** é o nome do caminho totalmente qualificado do executável com relação ao dispositivo.
- **Adicionar aplicativos gerenciados**: selecione um aplicativo gerenciado existente que você adicionou usando [Aplicativos Móveis no Intune](apps-add.md).
- **Adicionar aplicativo por AUMID**: insira o [AUMID do aplicativo](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplicativos da UWP).
- **Barra de tarefas**: escolha **Habilitar** (mostrar) na barra de tarefas ou mantenha-a como **Não configurada** (oculta) no quiosque.
- **Layout do menu Iniciar**: insira um arquivo XML que descreve como os aplicativos são exibidos no menu Iniciar, incluindo a ordem dos aplicativos. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) fornece algumas diretrizes e XML de exemplo.

  [Criar um quiosque Windows 10 que executa vários aplicativos](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) fornece mais detalhes sobre como usar e criar arquivos XML.

- **Tipo de conta de usuário**: adicione uma ou mais contas de usuário que podem usar os aplicativos que você adicionar. Quando a conta se conecta, apenas os aplicativos definidos na configuração estão disponíveis. A conta pode ser local para o dispositivo ou um logon de conta do Azure AD associado ao aplicativo de quiosque.

    Para quiosques em ambientes de público com logon automático habilitado, um tipo de usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Para configurar uma conta do Azure AD (Active Directory) para o modo de quiosque, use o formato `domain\user@tenant.com`.

## <a name="kiosk-web-browser-settings"></a>Configurações do navegador da Web de quiosque

Essas configurações controlam um aplicativo de navegador da Web no quiosque. Você deve ter implantado um aplicativo de navegador da Web para os dispositivos de quiosque usando [Aplicativos Móveis](apps-add.md).

1. Insira as seguintes configurações:

  - **URL da página inicial padrão**: insira a URL padrão que o navegador de quiosque abre quando o navegador é aberto ou reiniciado.

  - **Mostrar botão página inicial**: Mostrar (**Obrigatório**) ou ocultar (**Não configurado**) o botão de página inicial do navegador de quiosque. Por padrão, o botão Não está configurado.

  - **Mostrar botão de navegação**: Mostrar (**Obrigatório**) ou ocultar (**Não configurado**) os botões de avançar e voltar. Por padrão, os botões de navegação Não estão configurados.

  - **Atualizar o navegador quando o usuário exceder o limite de tempo ocioso**: insira a quantidade de tempo ocioso da sessão em minutos até que o navegador de quiosque reinicie em um estado novo. O valor é um inteiro de 1 a 1.440 minutos. Por padrão, o valor está vazio ou em branco, que significa que não há nenhum tempo limite de ociosidade.

  - **Sites bloqueados**: lista de URLs de sites bloqueados (com suporte a caracteres curinga). Use essa configuração para impedir que o navegador abra sites específicos. Você também pode **Importar** um arquivo .csv que contenha uma lista. Ou criar um arquivo .csv (**Exportar**) que contenha os sites que você adicionar.

  - **Exceções de site**: lista de exceções para URLs do site bloqueado (com suporte a caracteres curinga). Use essa configuração para permitir que o navegador abra sites específicos. Essas exceções são um subconjunto das URLs bloqueadas. Se uma URL estiver na lista de sites bloqueados e na lista de exceção do site, a exceção entrará em vigor.

    Você também pode **Importar** um arquivo .csv que contenha uma lista. Ou criar um arquivo .csv (**Exportar**) que contenha os sites que você adicionar.

2. Selecione **OK** para salvar suas alterações.

## <a name="next-steps"></a>Próximas etapas
[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).