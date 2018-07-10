---
title: Edição antecipada
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0500194f5afaba11f37b84bbdf606e6167632a71
ms.sourcegitcommit: afa2e84d5cadf5542ecabc26e61dc71919992a22
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37340168"
---
# <a name="the-early-edition-for-microsoft-intune---july-2018"></a>A edição antecipada do Microsoft Intune – julho de 2018

> [!Note]
> Notificação do NDA: as seguintes alterações estão em desenvolvimento para o Intune. Essas informações são compartilhadas sob NDA de modo muito limitado. Não poste nenhuma dessas informações em mídia social nem em sites públicos, como Twitter, UserVoice, Reddit e assim por diante. 

A **edição antecipada** fornece uma lista de recursos, compartilhados sob NDA, que estarão disponíveis em versões futuras do Microsoft Intune. Essas informações são fornecidas de forma limitada e estão sujeitas a alterações. Não tweet, poste no UserVoice, nem compartilhe de nenhuma outra forma essas informações fora de sua empresa. Alguns recursos listados aqui correm o risco de não estarem prontos na data de fechamento e serem atrasados até uma versão futura. Outros recursos estão sendo testados em um piloto (liberação de versões de pré-lançamento) para garantir que fiquem prontos para o cliente. Fale com seu contato do grupo de produtos da Microsoft em caso de perguntas ou dúvidas.

Esta página é atualizada periodicamente. Volte a ela para verificar se há atualizações adicionais.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure

<!-- 1807 start -->

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Redefinir senhas de dispositivo por meio do Portal da Empresa para Windows 10 <!-- 2101282 --> 
Em breve seus funcionários poderão redefinir o PIN ou a senha do dispositivo usando diretamente o aplicativo Portal da Empresa para Windows 10. Essa funcionalidade estará disponível em dispositivos locais e remotos gerenciados pelo Intune compatíveis com redefinições de senha. Dependendo do tipo de dispositivo, uma solicitação feita para um dispositivo remoto removerá a senha atual do dispositivo ou criará uma senha temporária. Os usuários que solicitam uma redefinição de um dispositivo local serão redirecionados ao aplicativo de Configurações do dispositivo.

### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>Usar S/MIME para criptografar e assinar vários dispositivos de um usuário  <!-- 1333642 -->
Uma atualização futura incluirá uma criptografia de email S/MIME usando um novo perfil de certificado importado (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > selecione a plataforma > tipo de perfil **Certificado PKCS importado**). No Intune, você pode importar certificados no formato PFX. Em seguida, o Intune pode fornecer os mesmos certificados para vários dispositivos registrados por um único usuário. Isso também inclui:

- O perfil de email do iOS nativo permite habilitar a criptografia S/MIME usando certificados importados no formato PFX.
- O aplicativo de email nativo em dispositivos Windows Phone 10 usam automaticamente o certificado S/MIME.
- Os certificados privados podem ser entregues em várias plataformas. Porém, nem todos os aplicativos de email são compatíveis com S/MIME.
- Em outras plataformas, talvez você precise configurar manualmente o aplicativo de email para habilitar o S/MIME.  
- Os aplicativos de email compatíveis com a criptografia S/MIME podem manipular a recuperação de certificados para criptografia de email S/MIME de uma maneira com a qual o MDM não é compatível, como a leitura do repositório de certificados do editor.

Compatível com: Windows, Windows Phone 10, macOS, iOS, Android

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Usar licenças de dispositivo VPP para pré-provisionar o Portal da Empresa durante o registro no DEP <!-- 1608345 -->
Você poderá usar licenças de dispositivo do VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante os registros no DEP (Programa de registro de dispositivos). Para fazer isso, quando você criar ou editar um perfil de registro, especifique o token VPP que deseja usar para instalar o Portal da Empresa. Verifique se o token não expira e se você tem licenças suficientes para o aplicativo de Portal da Empresa. Caso o token for expirar ou for executado sem licenças, o Intune enviará por push o Portal da Empresa da App Store (uma ID da Apple será solicitada).

### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Excluir em massa os dispositivos na folha de dispositivos <!-- 1793693 -->
Você poderá excluir vários dispositivos ao mesmo tempo na folha Dispositivos. Escolha **Dispositivos** > **Todos os dispositivos** > selecione os dispositivos que deseja excluir > **Excluir**. Para dispositivos que não podem ser excluídos, um alerta será exibido.

### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Novo perfil de configuração de dispositivo de Wi-Fi para Windows 10 e posterior <!-- 1879077 -->
No momento, você pode importar e exportar perfis de Wi-Fi usando arquivos XML. Você poderá criar um perfil de configuração de dispositivo de Wi-Fi diretamente no Intune, como em algumas outras plataformas.

Para criar o perfil, abra **Configuração do dispositivo** > **Perfis** > **Criar Perfil** > **Windows 10 e posteriores** > **Wi-Fi**. 

Aplica-se ao Windows 10 e posteriores.

###  <a name="windows-line-of-business-lob-apps-file-extension-rename----1884873---"></a>Renomeação de extensão de arquivo de aplicativos de LOB (linha de negócios) do Windows <!-- 1884873 -->
As extensões de arquivo para aplicativos de LOB do Windows serão renomeadas de *.appx* e *.appxbundle* para *.msix* e *.msixbundle*. Você pode adicionar um aplicativo no Microsoft Intune selecionando **Aplicativos móveis** > **Aplicativos** > **Adicionar**. O painel **Adicionar aplicativo** é exibido permitindo que você selecione o **Tipo de aplicativo**. Para aplicativos de LOB do Windows, selecione aplicativo de **Linha de negócios** como o tipo de aplicativo, selecione o **Arquivo de pacote do aplicativo** e, em seguida, insira um arquivo de instalação com a extensão apropriada.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Pacote de configuração do Windows Defender ATP adicionado automaticamente ao perfil de configuração <!-- 2144658 -->
Ao usar dispositivos de [Proteção Avançada contra Ameaças e integração](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) no Intune, no momento, você baixa um pacote de configuração e adiciona-o ao perfil de configuração. Em uma atualização futura, o Intune obterá automaticamente o pacote da Central de Segurança do Windows Defender e o adicionará ao seu perfil.

Aplica-se ao Windows 10 e posteriores.

### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Quiosque – obsoleto, está esmaecido e não pode ser alterado <!-- 2149998 -->
O [Recurso de quiosque](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posteriores** > **Restrições do dispositivo**) ficará obsoleto e será substituído por [Configurações de quiosque para Windows 10 e posteriores](kiosk-settings.md). O recurso **Quiosque – obsoleto** estará esmaecido, e a interface do usuário não poderá ser alterada ou atualizada. 

Para habilitar o modo de quiosque, confira [Configurações de quiosque para Windows 10 e posteriores](kiosk-settings.md).

Aplica-se ao Windows 10 e posteriores, Windows Holographic for Business

### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>APIs para usar autoridades de certificação de terceiros <!-- 2184013 -->
Haverá uma API Java para permitir que autoridades de certificação de terceiros sejam integradas ao Intune e ao SCEP. Assim, os usuários poderão adicionar o certificado SCEP a um perfil e aplicá-lo aos dispositivos usando o MDM.

Atualmente, o Intune permite [Solicitações SCEP usando serviços de certificados do Active Directory](certificates-scep-configure.md).

### <a name="check-for-sccm-compliance----2192052---"></a>Verificar a conformidade com o SCCM <!-- 2192052 -->
Uma atualização futura incluirá uma nova configuração de conformidade com o SCCM (System Center Configuration Manager) (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Windows 10**). O SCCM envia sinais para a conformidade do Intune. Usando a configuração do Intune, você pode exigir que todos os sinais do SCCM retornem "compatível".

Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No SCCM, esse requisito tem o estado "Instalar". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.

Aplica-se ao Windows 10 e posteriores

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alertas de expiração de token do VPP ou de licença do Portal da Empresa quase acabando <!-- 2237572 -->
Se você usar o VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante o registro no DEP, o Intune o alertará quando o token VPP estiver prestes a expirar e quando as licenças para o Portal da Empresa estiverem quase acabando.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Confirmação necessária para excluir o token do VPP que está sendo usado para o pré-provisionamento do Portal da Empresa <!-- 2237634 -->
Será necessária uma confirmação para excluir um token do VPP (Volume Purchase Program) se ele estiver sendo usado para pré-provisionar o Portal da Empresa durante o registro no DEP.

### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Marcar automaticamente os dispositivos Android registrados usando o registro de dispositivo móvel do Samsung Knox como "corporativo" <!-- 2404851 -->
Por padrão, os dispositivos Android registrados usando o registro de dispositivo móvel do Samsung Knox serão marcados como **corporativos** em **Propriedade do Dispositivo**. Você não precisará identificar manualmente os dispositivos corporativos usando o IMEI ou números de série antes de registrar usando o registro de dispositivo móvel do Knox.

### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Alternar para mostrar ou não mostrar o botão Encerrar Sessão em um navegador de quiosque <!-- 2455253 -->
Você poderá configurar se os navegadores de quiosque mostram o botão Encerrar Sessão. Veja o controle em **Configuração do dispositivo** > **Quiosque (versão prévia)** > **Navegador da Web de quiosque**. Se estiver habilitado, quando um usuário clicar no botão, o aplicativo solicitará uma confirmação para encerrar a sessão. Quando confirmado, o navegador limpa todos os dados de navegação e navega novamente para a URL padrão.

### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Criar um perfil de configuração de celular do eSIM <!-- 2564077 -->
Em **Configuração do dispositivo**, você poderá criar um perfil de celular eSIM. É possível importar um arquivo contendo os códigos de ativação de celular fornecidos pela operadora do dispositivo móvel. Em seguida, você pode implantar esses perfis nos dispositivos Windows 10 habilitados para eSIM LTE, como o Surface Pro LTE e outros dispositivos compatíveis com eSIM.

Verifique se seus [dispositivos são compatíveis com perfis de eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Aplica-se ao Windows 10 e posteriores. 




<!-- 1806 start -->

### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Ver perfis de configuração do dispositivo em conflito <!-- 1556983 -->
Em **Configuração do Dispositivo**, é mostrada uma lista dos perfis existentes. Com essa atualização, uma nova coluna foi adicionada para fornecer detalhes sobre os perfis que apresentam conflito. Você pode selecionar uma linha em conflito para ver a configuração e o perfil que apresenta o conflito. 

Mais detalhes sobre [Perfis de configuração do dispositivo](device-profiles.md).

### <a name="corporate-owned-single-use-cosu-support-for-android-devices----1630973---"></a>Suporte para COSU (uso único de propriedade corporativa) para dispositivos Android <!-- 1630973 -->

O Intune oferecerá suporte a dispositivos com Android altamente gerenciados e bloqueados no estilo quiosque. Isso permite que os administradores bloqueiem ainda mais o uso de um dispositivo para um único aplicativo ou um conjunto pequeno de aplicativos, e impede que os usuários habilitem outros aplicativos ou executem outras ações no dispositivo.

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>suporte do macOS para o Programa de Registro de Dispositivo da Apple <!-- 747651 -->

O Intune oferecerá suporte ao registro de dispositivos macOS no DEP (Programa de Registro de Dispositivos) da Apple. Para fazer isso:

1. Em deploy.apple.com, atribua números de série macOS a um servidor do MDM.
2. Importe os números de série para o Intune.
3. Crie um perfil do programa de registro específico para dispositivos macOS.

### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Alterações de nome do Google para Android for Work e Play for Work <!--842873 -->
O Intune atualizará a terminologia "Android for Work" para refletir as alterações de identidade visual do Google.  Os termos "Android for Work" e "Play for Work" não serão mais usados. Será usada uma terminologia diferente, dependendo do contexto:

- "Empresarial Android" refere-se à pilha de gerenciamento Android moderna geral.
- "Perfil de Trabalho" ou "Proprietário de Perfil" refere-se a dispositivos BYOD gerenciados com perfis de trabalho.
- "Google Play gerenciado" refere-se à loja de aplicativos do Google.

### <a name="monitor-ios--app-configuration-status-per-device----880037-eeready-eestaged---"></a>Monitorar o status de configuração de aplicativo do iOS por dispositivo <!-- 880037 eeready eestaged -->

Como o administrador do Microsoft Intune, você poderá monitorar o status de configuração de aplicativo do iOS para cada dispositivo gerenciado. No **Microsoft Intune**, no portal do Azure, selecione **Dispositivos** > **Todos os dispositivos**. Na lista de dispositivos gerenciados, selecione um dispositivo específico para exibir uma folha para o dispositivo. Na folha do dispositivo, selecione **Configuração de aplicativo**.  

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Teclados de terceiros podem ser bloqueados por configurações de APP no iOS <!-- 1248481 -->
Em dispositivos iOS, os administradores do Intune poderão bloquear o uso do teclados de terceiros ao acessarem dados da organização em aplicativos protegidos por política. Quando a APP (Política de Proteção de Aplicativo) for definida para bloquear teclados de terceiros, o usuário do dispositivo receberá uma mensagem na primeira vez que interagir com os dados corporativos ao usar um teclado de terceiros. Todas as opções que são não o teclado nativo serão bloqueadas e não serão exibidas para os usuários do dispositivos. Os usuários do dispositivos somente verão a mensagem de caixa de diálogo uma vez. 

### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Criar política de conformidade do dispositivo usando as configurações do Firewall em dispositivos macOS <!-- 1497640 -->
Quando você cria uma nova política de conformidade macOS (**Conformidade do dispositivo** > **Políticas** > **Criar política**  >  **Plataforma: macOS** > **Segurança do sistema**), haverá algumas novas configurações de **Firewall** disponíveis: 
- **Firewall**: configure como conexões de entrada são tratadas em seu ambiente.
- **Conexões de entrada**: **Bloquear** todas as conexões de entrada, exceto as conexões necessárias para serviços básicos da Internet, como DHCP, Bonjour e IPsec. Essa configuração também bloqueia todos os serviços de compartilhamento.
- **Modo Furtivo**: **Habilite** o modo furtivo para impedir que o dispositivo responda a solicitações de investigação. O dispositivo continua a responder a solicitações de entrada para aplicativos autorizados.

Aplica-se a: macOS 10.12 e posteriores

### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Usar sAMAccountName como o nome de usuário da conta para perfis de email <!-- 1500307 -->

Você poderá usar o **sAMAccountName** local como o nome de usuário da conta para perfis de email para Windows 10, iOS e Android. Você também será capaz de obter o domínio do atributo `domain` ou `ntdomain` no Azure AD (Azure Active Directory). Ou insira um domínio estático personalizado.

Para usar esse recurso, você deve sincronizar o atributo `sAMAccountName` do seu ambiente do Active Directory local com o Azure AD.

Aplica-se a: Android, iOS, Windows 10 e posteriores

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Exigir senha não biométrica na inicialização do aplicativo e tempo limite <!-- 1506985 -->

Ao exigir uma senha não biométrica na inicialização do aplicativo e após o tempo limite especificado pelo administrador, o Intune oferecerá maior segurança para aplicativos habilitados para MAM (Gerenciamento de Aplicativo Móvel) restringindo o uso de identificação biométrica para acesso a dados corporativos. As configurações afetarão os usuários que contam com Touch ID (iOS), Face ID (iOS), Android Biometric ou outros métodos de autenticação biométrica futuros para acessar seus aplicativos habilitados para APP/MAM. Essas configurações permitirão que os administradores do Intune tenham controle mais granular sobre acesso de usuário, eliminando casos em que um dispositivo com várias impressões digitais ou outros métodos de acesso biométrico pode revelar dados corporativos para um usuário incorreto. No Portal do Azure, abra o **Microsoft Intune**. Selecione **Aplicativos móveis** > **Políticas de proteção de aplicativo** > **Adicionar uma política** > **Configurações**. Localize a seção **Acessar** para configurações específicas.

### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Apagamento seletivo de dados de aplicativo da organização <!-- 1507030 -->
Os administradores poderão configurar um apagamento seletivo de dados da organização como uma nova ação quando as condições de configurações de Acesso APP (Políticas de Proteção do Aplicativo) não forem atendidas.  Esse recurso ajuda os administradores a proteger e remover automaticamente dados confidenciais de empresa de aplicativos com base em critérios previamente configurados.

### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Revogar um aplicativo iOS adquirido por meio do VPP <!-- 1777384 -->
Como o administrador do Microsoft Intune, você poderá revogar a licença para um aplicativo iOS selecionado adquirido por meio do VPP (programa de compra de volume). Você poderá notificar os usuários quando um aplicativo não estiver mais atribuído a eles. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. A contagem de licenças recuperadas será refletida no nó **Aplicativos Licenciados** na carga de trabalho de **Aplicativo** do Intune. Para obter mais informações relacionadas a aplicativos VPP iOS, veja [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](vpp-apps-ios.md).

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pacotes de idiomas do Office 365 Pro Plus <!-- 1833450 -->
Como a administração do Intune, você poderá implantar idiomas adicionais para aplicativos do Office 365 Pro Plus gerenciados por meio do Intune. A lista de idiomas disponíveis inclui o **Tipo** de pacote de idiomas (núcleo, parcial e revisão de texto). No portal do Azure, selecione **Microsoft Intune** > **Aplicativos móveis** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo** da folha **Adicionar aplicativo**, selecione **Windows 10** em **Pacote do Office 365**. Selecione **Idiomas** na folha **Configurações do Pacote de Aplicativos**.

### <a name="revoke-ios-vpp-app-license----1863797---"></a>Revogar a licença de aplicativo VPP iOS <!-- 1863797 -->
Como administrador, você poderá recuperar uma licença de aplicativo de VPP iOS atribuída a um usuário ou dispositivo. Desinstalar um aplicativo VPP iOS também permitirá que você recupere a licença do aplicativo. Em seguida, você pode optar por atribuir a licença do aplicativo a outro usuário ou dispositivo. Para obter mais informações sobre licenças de aplicativo VPP iOS, consulte [Gerenciar aplicativos adquiridos por volume do iOS no Microsoft Intune](vpp-apps-ios.md).

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Visualizar uma nova atualização de experiência do usuário para o site do Portal da Empresa <!--2000968 -->
Estamos adicionando novos recursos, com base nos comentários dos clientes, ao site Portal da Empresa e ao catálogo de aplicativos iOS. Você fará uma melhoria significativa na funcionalidade existente e na usabilidade dos seus dispositivos Android, iOS e Windows. Áreas do site, como detalhes do dispositivo, comentários e suporte e visão geral do dispositivo, receberão um design novo, moderno e responsivo. Você também verá:

- Fluxos de trabalho simplificados em todas as plataformas de dispositivo
- Fluxos de identificação e registro de dispositivo aprimorados
- Mensagens de erro mais úteis
- Linguagem mais amigável, menos jargão técnico
- Capacidade de compartilhar links diretos para aplicativos
- Melhor desempenho para grandes catálogos de aplicativos
- Maior acessibilidade para todos os usuários

A atualização está atualmente na versão prévia. Registre-se para ingressar na versão prévia em http://aka.ms/webcpflighting

### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Atualizações das mensagens de falta de conformidade no aplicativo Portal da Empresa <!-- 1832222 -->
Estamos revisando as mensagens que são exibidas para os usuários de dispositivos quando um dispositivo não está em conformidade. As mensagens manterão seus significados originais, mas serão atualizadas com uma linguagem mais amigável e menos técnica. Também estamos atualizando os links para etapas de correção e documentação para mantê-los atualizados.  

Os textos “antes” e “depois” a seguir são um exemplo das melhorias no sistema de mensagens que você verá:  

Antes: *Este dispositivo não contatou o serviço do Intune no período de tempo especificado exigido pelo administrador de TI. Para resolver esse problema, abra o aplicativo Portal da Empresa em seu dispositivo e clique no botão Verificar Conformidade.*  

Depois: *Há um tempo que seu dispositivo não faz check-in na organização. Para restabelecer a conexão, abra o aplicativo Portal da Empresa no dispositivo e toque em Verificar Configurações no dispositivo*.  

### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Editar suas implantações de aplicativo do Office 365 Pro Plus <!-- 2150145 -->
Como o administrador do Microsoft Intune, você terá maior capacidade de editar suas implantações de aplicativo do Office 365 Pro Plus. No portal do Azure, selecione **Microsoft Intune** > **Aplicativos móveis** > **Aplicativos**. Na lista de aplicativos, selecione o Pacote Office 365 Pro Plus.  

### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794---"></a>Revisão por linha de identificadores de dispositivo corporativo duplicados carregados <!-- 2203794 -->
Ao carregar IDs corporativas, o Intune fornece uma lista de todas as duplicatas e dá a opção de substituir ou manter as informações existentes. O relatório será exibido se houver duplicatas depois que você escolher **Registro de dispositivo** > **Identificadores de Dispositivo Corporativo** > **Adicionar Identificadores**. 

### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Adicione manualmente identificadores de dispositivo corporativo <!-- 2203803 -->
Você poderá adicionar manualmente as IDs de dispositivo corporativo. Escolha **Registro de dispositivo** > **Identificadores de Dispositivo Corporativo** > **Adicionar**.

### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Novo status para dispositivos em conformidade do dispositivo <!-- 2308882 -->
Em **Conformidade do dispositivo** > **Políticas** > selecione uma política > **Visão geral**, serão adicionados os seguintes novos estados:
- bem-sucedido
- erro
- conflito
- pendente
- não aplicável

Uma imagem que mostra a contagem de dispositivos de uma plataforma diferente também é mostrada. Por exemplo, se você estiver procurando em um perfil do iOS, o novo bloco mostrará a contagem de dispositivos não iOS que também estão atribuídos a esse ele. 

### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>A conformidade do dispositivo é compatível com soluções de antivírus de terceiros <!-- 2325484 -->
Quando você cria uma política de conformidade do dispositivo (**Conformidade do dispositivo** > **Políticas** > **Criar política**  >  **Plataforma: Windows 10 e posteriores** > **Configurações** > **Segurança do sistema**), haverá novas opções de **Segurança do Dispositivo**: 
- **Antivírus**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções antivírus registradas com a Central de Segurança do Windows, como Symantec. 
- **AntiSpyware**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções antispyware registradas com a Central de Segurança do Windows, como Symantec. 

Aplica-se ao Windows 10 e posteriores 

<!-- 1805 start -->

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Solução aprimorada de problemas de instalação do aplicativo <!-- 928990 -->
Em dispositivos gerenciados pelo MDM do Microsoft Intune, as instalações de aplicativos às vezes podem falhar. Quando a instalação desses aplicativos falha, pode ser um desafio entender o motivo da falha ou solucionar o problema. Estamos enviando uma Visualização Pública dos nossos recursos de Solução de Problemas de Aplicativo. Você observará um novo nó em cada dispositivo individual com o nome **Aplicativos Gerenciados**. Ele lista os aplicativos que foram entregues por meio do MDM do Intune. Dentro do nó, você verá uma lista dos estados de instalação do aplicativo. Se você selecionar um aplicativo individual, verá o modo de exibição de solução de problemas desse aplicativo específico. Na exibição de solução de problemas, você verá o ciclo de vida completo do aplicativo, por exemplo, quando o aplicativo foi criado, modificado, direcionado e entregue a um dispositivo. Além disso, se a instalação do aplicativo não for bem-sucedida, você receberá o código de erro e uma mensagem útil sobre a causa do erro.

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Exigir senha não biométrica na inicialização a frio do aplicativo e tempo limite <!-- 1506985 --> 

Ao exigir uma senha não biométrica na inicialização a frio do aplicativo e após o tempo limite especificado pelo administrador, o Intune oferecerá maior segurança para aplicativos habilitados para MAM (Gerenciamento de Aplicativo Móvel) restringindo o uso de identificação biométrica para acesso a dados corporativos. As configurações afetarão os usuários que contam com Touch ID (iOS), Face ID (iOS), Android Biometric ou outros métodos de autenticação biométrica futuros para acessar seus aplicativos habilitados para APP/MAM. Essas configurações permitirão que os administradores do Intune tenham controle mais granular sobre acesso de usuário, eliminando casos em que um dispositivo com várias impressões digitais ou outros métodos de acesso biométrico pode revelar dados corporativos para um usuário incorreto. No Portal do Azure, abra o **Microsoft Intune**. Selecione **Aplicativos móveis** > **Políticas de proteção de aplicativo** > **Adicionar uma política** > **Configurações**. Localize a seção **Acessar** para configurações específicas.

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Bloquear acesso do aplicativo com base em modelos e fornecedores de dispositivos não aprovados <!-- 1425689 ! -->
O administrador de TI do Intune será capaz de impor uma lista especificada de fabricantes Android e/ou modelos de iOS por meio das Políticas de Proteção de Aplicativo do Intune. O administrador de TI pode fornecer uma lista separada por ponto e vírgula de fabricantes para políticas do Android e de modelos de dispositivos para políticas do iOS. As Políticas de Proteção de Aplicativo do Intune servem apenas para Android e iOS. Haverá duas ações diferentes que podem ser executadas nessa lista especificada:
- Um bloqueio de acesso do aplicativo em dispositivos que não estão especificados.
- Ou uma limpeza seletiva de dados corporativos em dispositivos que não estão especificados. 

O usuário não conseguirá acessar o aplicativo direcionado se os requisitos por meio da política não forem atendidos. Com base nas configurações, o usuário pode ser bloqueado ou passar por uma limpeza seletiva dos dados corporativos no aplicativo. Em dispositivos iOS, esse recurso exige a participação de aplicativos (por exemplo, WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de Aplicativo do Intune para as configurações de versão mínima serem impostas aos aplicativos direcionados. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. No Android, esse recurso exige a versão mais recente do Portal da Empresa. 

Em dispositivos de usuário final, o cliente do Intune executaria uma ação com base em uma correspondência simples das cadeias de caracteres especificadas na folha do Intune para Políticas de Proteção de Aplicativo. Isso depende totalmente do valor informado pelo dispositivo. Por isso, o administrador de TI é incentivado a garantir que o comportamento desejado seja preciso. Isso pode ser feito testando essa configuração com base em vários fabricantes e modelos de dispositivo direcionados a um grupo de usuários pequeno. No Microsoft Intune, selecione **Aplicativos Móveis** > **Políticas de proteção de aplicativo** para exibir e adicionar as políticas de proteção de aplicativo. Para saber mais sobre políticas de proteção de aplicativo, confira [O que são políticas de proteção de aplicativo?](app-protection-policy.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Ações de acesso para políticas de proteção de aplicativo <!-- 1483510 EEready -->
Logo, você poderá configurar políticas de proteção de aplicativo para apagar, bloquear ou avisar explicitamente os dispositivos não compatíveis. A ação mais recente, *apagar*, remove os dados corporativos de um dispositivo. Se ocorrer uma limpeza, o usuário do dispositivo receberá uma notificação sobre o motivo da limpeza e etapas de remediação. Para algumas configurações, como a versão mínima do sistema operacional, você poderá aplicar várias ações, como bloquear e apagar. Essas ações são disparadas quando o aplicativo é iniciado.

<!-- 1804 start -->

### <a name="rules-for-removing-devices----1609459---"></a>Regras para remover dispositivos <!-- 1609459 -->
Estarão disponíveis novas regras que permitem remover automaticamente dispositivos que não fizeram check-in por um número de dias que você definir. Para ver a nova regra, vá para o painel **Intune**, selecione **Dispositivos** e selecione **Regras de remoção de dispositivo**.

<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Capacidade de implantar aplicativos LOB (aplicativo de linha de negócios) necessários para Todos os usuários em dispositivos do Windows 10 Desktop <!-- 1627835 RS4 -->
Os clientes poderão implantar os aplicativos de linha de negócios do Windows 10 necessários que deverão ser instalados em contextos de dispositivo. Isso permitirá que esses aplicativos estejam disponíveis para todos os usuários no dispositivo. Isso se aplica somente a dispositivos Windows 10 Desktop.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Atualizando a experiência de Ajuda e Comentários no aplicativo Portal da Empresa para Android <!--1631531 -->

Atualizaremos as experiências de Ajuda e Comentários no aplicativo Portal da Empresa para Android para alinhá-las às práticas recomendadas para aplicativos Android. Atualizaremos o aplicativo Portal da Empresa para Android nos próximos meses para dividir o item de menu **Ajuda e Comentários** nos itens **Ajuda** e **Enviar Comentário** separados. A página **Ajuda** conterá com uma seção de **Perguntas Frequentes** e um botão **Suporte por Email** para instruir os usuários finais a carregar logs para a Microsoft e enviar email para o suporte da empresa descrevendo o problema. **Enviar Comentários** guiará o usuário por um envio de comentários padrão da Microsoft, que solicitará ao usuário escolher entre “Gosto de algo”, “ Não gosto de algo” ou “Tenho uma ideia”.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Políticas de Proteção de Aplicativo <!-- 679615 -->
As Políticas de Proteção de Aplicativo do Intune oferecem a capacidade de criar políticas globais e padrão para habilitar rapidamente a proteção em todos os usuários no locatário inteiro.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Avisos

Não há nenhum avisos ativo no momento.

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.