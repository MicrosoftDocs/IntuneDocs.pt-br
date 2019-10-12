---
title: O que há de novo m meses anteriores no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Veja comunicados mais antigos da página de novidades do Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/8/2019
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1af106227442e91121f6c8c653c261bd677f3a9f
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814188"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Novidades do Microsoft Intune – meses anteriores

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

<!-- ########################## -->
## <a name="december-2018"></a>Dezembro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="updates-for-application-transport-security----748318---"></a>Atualizações de Segurança do Transporte de Aplicativo <!-- 748318 -->

O Microsoft Intune dá suporte para o protocolo TLS 1.2 e versões posteriores para fornecer a melhor criptografia, garantir que o Intune esteja mais seguro por padrão e alinhar-se a outros serviços da Microsoft, como o Microsoft Office 365. Para atender a esse requisito, os portais da empresa para iOS e macOS imporão requisitos atualizados de ATS (Segurança do Transporte de Aplicativo) da Apple que também exigem TLS 1.2 e versões posteriores. O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS e macOS. Para saber mais, confira o [blog de suporte do Intune](https://aka.ms/compportalats).

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>O SDK de Aplicativo do Intune dará suporte a chaves de criptografia de 256 bits <!-- 1832174 -->
Agora o SDK do Aplicativo Intune para Android usa as chaves de criptografia de 256 bits quando a criptografia é habilitada por Políticas de Proteção de Aplicativo. O SDK continua a fornecer suporte a chaves de 128 bits para compatibilidade com o conteúdo e aplicativos que usam versões mais antigas do SDK.

#### <a name="microsoft-auto-update-version-450-required-for-macos-devices----3503442---"></a>É necessário ter a versão 4.5.0 da Atualização Automática da Microsoft para dispositivos macOS <!-- 3503442 -->
Para continuar recebendo atualizações para o Portal da Empresa e outros aplicativos do Office, os dispositivos macOS gerenciados pelo Intune devem atualizar para a Atualização Automática da Microsoft 4.5.0. Talvez os usuários já tenham essa versão para seus aplicativos do Office.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="intune-requires-macos-1012-or-later----2827778---"></a>O Intune exige o macOS 10.12 ou posterior <!-- 2827778 -->
Agora, o Intune exige o macOS 10.12 ou posterior. Dispositivos que usam versões anteriores do macOS não podem usar o Portal da Empresa para se inscrever no Intune. Para receber assistência do suporte e os novos recursos, os usuários precisarão atualizar seus dispositivos para o macOS 10.12 ou superior, e atualizar o aplicativo Portal da Empresa para a versão mais recente.

<!-- ########################## -->
## <a name="november-2018"></a>Novembro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Como desinstalar aplicativos em dispositivos iOS supervisionados corporativos <!-- 1281677 -->
Você pode remover qualquer aplicativo em dispositivos iOS corporativos supervisionados. Você pode remover qualquer aplicativo definindo como destino grupos de usuários ou dispositivos com um tipo de atribuição de **Desinstalação**. Para dispositivos iOS não supervisionados ou pessoais, você continuará podendo remover apenas os aplicativos instalados usando o Intune.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Como baixar conteúdo de aplicativos Win32 do Intune <!-- 2617320 -->
Os clientes com Windows 10 RS3 e superior baixarão o conteúdo do aplicativo Intune Win32 usando um componente de Otimização de Entrega no cliente do Windows 10. A otimização de entrega fornece o recurso de ponto a ponto ativada por padrão. Atualmente, a otimização de entrega pode ser configurada pela política de grupo. Para saber mais, consulte [Otimização de entrega para Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Dispositivo de usuário final e menu de conteúdo do aplicativo <!-- 2771453 -->
Os usuários finais agora podem usar o menu de contexto no dispositivo e nos aplicativos para acionar ações comuns, como renomear um dispositivo ou verificar a conformidade.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Definir a tela de fundo personalizada no aplicativo Tela Inicial Gerenciada  <!-- 3041945 -->
Vamos adicionar uma configuração que permite personalizar a aparência da tela de fundo do aplicativo Tela Inicial Gerenciada em dispositivos Android Enterprise de vários aplicativos em modo de quiosque.  Para configurar a **tela de fundo da URL Personalizada**, vá para o Intune no portal do Azure > Configuração do dispositivo. Selecione um perfil de configuração do dispositivo atual ou crie um novo para editar suas configurações de quiosque.
Para ver as configurações de quiosque, consulte [Restrições de dispositivo do Android Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Salvar e aplicar atribuição de política de proteção de aplicativo <!-- 3104570 -->
Agora, você tem mais controle sobre suas [atribuições de política de proteção de aplicativo](../apps/app-protection-policies.md#deploy-a-policy-to-users). Ao selecionar *Atribuições* para definir ou editar as atribuições de uma política, você deve **Salvar** sua configuração antes de aplicar a alteração. Use **Descartar** para limpar todas as alterações feitas sem salvá-las nas listas de inclusão ou exclusão.  Ao exigir Salvar ou Descartar, apenas os usuários desejados receberão uma política de proteção do aplicativo.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Novas configurações do navegador Microsoft Edge para Windows 10 e posterior <!-- 3174639 -->
Essa atualização inclui novas configurações para ajudar a controlar e gerenciar o navegador Microsoft Edge em seus dispositivos. Para obter uma lista dessas configurações, consulte [Restrição de dispositivo para Windows 10 (e mais recentes)](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Novo suporte a aplicativos com políticas de proteção de aplicativo <!-- 3330037 -->
Agora, você pode gerenciar os seguintes aplicativos com as [políticas de proteção de aplicativo do Intune](../apps/app-protection-policies.md):
- Stream (iOS)
- To DO (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Use as políticas de proteção de aplicativo para proteger dados corporativos e controlar a transferência de dados para esses aplicativos, como outros aplicativos gerenciados pela política do Intune. Observação: se o Flow ainda não estiver visível no console, adicione-o criando ou editando políticas de proteção do aplicativo. Para fazer isso, use a opção **+ Mais aplicativos** e especifique a *ID do Aplicativo* do Flow no campo de entrada. No Android, use *com.microsoft.flow* e para iOS use *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Suporte para OAuth do iOS 12 em perfis de email do iOS <!--2155106 -->
Perfis de email do iOS do Intune oferecem suporte ao OAuth (Open Authorization) do iOS 12. Para ver esse recurso, crie um novo perfil (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **iOS** para a plataforma > **Email** para tipo de perfil), ou atualize um perfil de email do iOS existente. Caso habilite o OAuth em um perfil que já esteja implantado para os usuários, os usuários serão solicitados a autenticar novamente e baixar seus emails de novo.

Os [perfis de email do iOS](../configuration/email-settings-ios.md) têm mais informações sobre como usar o OAuth em um perfil de email.

#### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>Suporte do NAC (Controle de Acesso à Rede) do Citrix SSO para iOS <!-- 3259404 -->
A Citrix lançou uma atualização para o Citrix Gateway para permitir o Controle de Acesso de Rede (NAC) do Citrix SSO para iOS no Intune. Você pode optar por incluir uma ID de dispositivo em um perfil da VPN no Intune e, em seguida, enviar esse perfil por push para dispositivos iOS. Você precisará instalar a atualização mais recente do Citrix Gateway para usar essa funcionalidade.

[Definir configurações da VPN em dispositivos iOS](../configuration/vpn-settings-ios.md#base-vpn-settings) fornece mais informações sobre como usar o NAC, incluindo alguns requisitos adicionais. 

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>Os números de build e de versão do iOS e do macOS são mostrados <!-- 1892471 -->
Em **Conformidade do dispositivo** > **Conformidade do dispositivo**, as versões do sistema operacional iOS e macOS são mostradas e estão disponíveis para uso em políticas de conformidade. Essa atualização inclui o número de build, configurável em ambas as plataformas.
Quando são lançadas atualizações de segurança, a Apple normalmente mantém o número de versão no estado em que se encontra, mas atualiza o número de build. Ao usar o número de build em uma política de conformidade, você pode verificar facilmente se uma atualização de vulnerabilidade está instalada.
Para usar esse recurso, consulte as políticas de conformidade para [iOS](../protect/compliance-policy-create-ios.md#device-health) e [macOS](../protect/compliance-policy-create-mac-os.md#device-properties).

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Os grupos de atualização estão sendo substituídos por configurações de Otimização de Entrega para o Windows 10 e posterior <!-- 2753807 -->
Otimização de entrega é um novo perfil de configuração para o Windows 10 e versões posteriores. Esse recurso fornece uma experiência mais simplificada para fornecer atualizações de software para dispositivos em sua organização. Essa atualização também ajuda você a fornecer as configurações em anéis de atualização novos e existentes usando um perfil de configuração.
Para configurar um perfil de configuração de otimização de entrega, consulte [Configurações de otimização de entrega do Windows 10 (e versões mais recentes)](../configuration/delivery-optimization-windows.md).

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices----2827760---"></a>Novas configurações de restrição de dispositivo adicionadas para dispositivos iOS e macOS <!-- 2827760 -->
Esta atualização inclui novas configurações para dispositivos iOS e macOS lançados com o iOS 12:

**Configurações do iOS**: 
- Geral: bloquear remoção de aplicativo (somente supervisionado)
- Geral: bloquear modo restrito de USB (somente supervisionado)
- Geral: forçar data e hora automáticas (somente supervisionado)
- Senha: bloquear o AutoPreenchimento de senha (somente supervisionado)
- Senha: bloquear solicitações de proximidade de senha (somente supervisionado)
- Senha: bloquear o compartilhamento de senha (somente supervisionado)

**Configurações do macOS**: 
- Senha: bloquear AutoPreenchimento de senha
- Senha: bloquear solicitações de proximidade de senha
- Senha: bloquear compartilhamento de senha

Para saber mais sobre essas configurações, consulte as configurações de restrição de dispositivos [iOS](../configuration/device-restrictions-ios.md) e [macOS](../configuration/device-restrictions-macos.md).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Suporte do Autopilot para dispositivos ingressados no Azure Active Directory híbrido (versão prévia) <!-- 1048100-->
Você agora pode configurar dispositivos ingressados no Azure Active Directory híbrido usando o Autopilot. Os dispositivos devem ser ingressados na rede da sua organização para usar o recurso Autopilot híbrido. Para obter mais informações, confira [Implantar dispositivos ingressados no Azure AD híbrido usando o Intune e o Windows Autopilot](../enrollment/windows-autopilot-hybrid.md).
Esse recurso será implantando em toda a base de usuários nos próximos dias. Portanto, você não poderá seguir estas etapas até que ela seja distribuída para a sua conta.

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Aplicativos selecionados acompanhados na Página de Status de Registro<!-- 2531007 -->
Você pode escolher quais aplicativos são rastreados na página de status de registro. Até que esses aplicativos sejam instalados, o usuário não pode usar o dispositivo. Para saber mais, consulte [Configurar uma página de status de registro](../enrollment/windows-enrollment-status.md).

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Pesquisar o dispositivo do Autopilot pelo número de série <!--2595788 -->
Agora, você pode pesquisar dispositivos do Autopilot pelo número de série. Para fazer isso, escolha **Registro de dispositivo** > **Registro do Windows** > **Dispositivos** > digite um número de série na caixa **Pesquisar por número de série** > pressione Enter.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Acompanhar a instalação do Office ProPlus <!--2620217 -->
Os usuários podem acompanhar o progresso da instalação do [Office ProPlus](../apps/apps-add-office365.md) usando a [Página de Status de Registro](../enrollment/windows-enrollment-status.md). Para saber mais, consulte [Configurar uma página de status de registro](../enrollment/windows-enrollment-status.md).

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alertas de expiração de token VPP ou de licença do Portal da Empresa <!-- 2237572 -->
Se você estiver usando o VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante o registro no DEP, o Intune o alertará quando o token VPP estiver prestes a expirar e quando as licenças para o Portal da Empresa estiverem acabando.

#### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>Suporte do Programa de registro de dispositivos do macOS para contas do Apple School Manager <!--3006133 -->
Agora o Intune oferece suporte ao uso do Programa de registro de dispositivos em dispositivos macOS para contas do Apple School Manager.  Para saber mais, consulte [Registrar automaticamente dispositivos macOS com o Apple School Manager ou o Programa de registro de dispositivos](../enrollment/device-enrollment-program-enroll-macos.md).

#### <a name="new-intune-device-subscription-sku---3312071--"></a>Novo SKU de assinatura de dispositivo do Intune <!--3312071-->
Para ajudar a reduzir o custo de dispositivos de gerenciamento nas empresas, um novo SKU de assinatura com base em dispositivo agora está disponível. Este SKU de dispositivo do Intune é licenciado por dispositivo mensalmente. O preço varia de acordo com o programa de licenciamento. Ele está disponível diretamente no Centro de administração do Microsoft 365 e pelo EA ([Contrato Enterprise](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2)), MPSA ([Contrato de Produtos e Serviços Microsoft](https://www.microsoft.com/licensing/mpsa/default)), [Contratos Microsoft Open](https://partner.microsoft.com/licensing/licensing-agreements) e CSP ([Provedor de Soluções na Nuvem](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453)).

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Pausar temporariamente o modo de quiosque em dispositivos Android para fazer alterações <!-- 3041935 -->
Ao usar dispositivos Android no modo de quiosque de vários aplicativos, um administrador de TI talvez precise fazer alterações ao dispositivo. Essa atualização inclui novas configurações de quiosque de vários aplicativos que possibilitam que um Administrador de TI pause temporariamente o modo de quiosque usando um PIN e obtenha acesso a todo o dispositivo.
Para ver as configurações de quiosque, consulte [Restrições de dispositivo do Android Enterprise](../configuration/device-restrictions-android-for-work.md).

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Habilitar o botão de página inicial virtual em dispositivos de quiosque Android Enterprise  <!-- 3042021 -->
Uma nova configuração permitirá que os usuários toquem em um botão de tecla no dispositivo para alternar entre o aplicativo Tela Inicial Gerenciada e outros aplicativos atribuídos no dispositivo de quiosque de vários aplicativos. Essa configuração é particularmente útil em cenários em que o aplicativo de quiosque do usuário não responde adequadamente ao botão "Voltar". Você poderá definir essa configuração para dispositivos Android de uso único e corporativos. Para habilitar ou desabilitar o **botão de Página inicial virtual**, vá para o Intune no portal do Azure > Configuração do dispositivo. Selecione um perfil de configuração do dispositivo atual ou crie um novo para editar suas configurações de quiosque.
Para ver as configurações de quiosque, consulte [Restrições de dispositivo do Android Enterprise](../configuration/device-restrictions-android-for-work.md).




<!-- ########################## -->
## <a name="october-2018"></a>Outubro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Acesso a propriedades-chave do perfil usando o aplicativo do portal da empresa <!-- 772203 -->
Os usuários finais já podem acessar as propriedades e ações da conta de chave de acesso, como redefinição de senha, do aplicativo Portal da Empresa. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Os teclados de terceiros podem ser bloqueados por configurações da APP no iOS <!-- 1248481 -->
Em dispositivos iOS, os administradores do Intune podem bloquear o uso do teclados de terceiros ao acessarem dados da organização em aplicativos protegidos por política. Quando a APP (Política de Proteção de Aplicativo) for definida para bloquear teclados de terceiros, o usuário do dispositivo receberá uma mensagem na primeira vez que interagir com os dados corporativos ao usar um teclado de terceiros. Todas as opções que são não o teclado nativo serão bloqueadas e não serão exibidas para os usuários do dispositivo. Os usuários do dispositivos somente verão a mensagem de caixa de diálogo uma vez. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Acesso à conta de usuário de aplicativos do Intune em dispositivos Android e iOS gerenciados <!-- 1248496 -->
Como administrador do Microsoft Intune, é possível controlar quais contas de usuário são adicionadas aos aplicativos do Microsoft Office em dispositivos gerenciados. É possível limitar o acesso apenas a contas permitidas de usuários corporativos e bloquear contas pessoais em dispositivos registrados. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>Política de configuração de aplicativos do Outlook para iOS e Android <!--1828527 -->
Agora você pode criar uma política de configuração de aplicativo do Outlook para iOS e Android para usuários locais que aproveitam a autenticação Básica com o protocolo ActiveSync. Outras configurações serão adicionadas à medida que forem habilitadas no Outlook para iOS e Android.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Pacotes de idiomas do Office 365 Pro Plus <!-- 1833450 -->
Como a administração do Intune, você poderá implantar idiomas adicionais para aplicativos do Office 365 Pro Plus gerenciados por meio do Intune. A lista de idiomas disponíveis inclui o **Tipo** de pacote de idiomas (núcleo, parcial e revisão de texto). No portal do Azure, selecione **Microsoft Intune** > **Aplicativos clientes** > **Aplicativos** > **Adicionar**. Na lista **Tipo de aplicativo** da folha **Adicionar aplicativo**, selecione **Windows 10** em **Pacote do Office 365**. Selecione **Idiomas** na folha **Configurações do Pacote de Aplicativos**.

#### <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Extensões de arquivo de aplicativos LOB (linha de negócios) do Windows <!-- 1884873 -->
As extensões de arquivo para aplicativos LOB do Windows agora incluirão *.msi*, *.appx*, *.appxbundle*, *.msix* e *.msixbundle*. Você pode adicionar um aplicativo no Microsoft Intune, selecionando **Aplicativos clientes** > **Aplicativos** > **Adicionar**. O painel **Adicionar aplicativo** é exibido permitindo que você selecione o **Tipo de aplicativo**. Para aplicativos de LOB do Windows, selecione aplicativo de **Linha de negócios** como o tipo de aplicativo, selecione o **Arquivo de pacote do aplicativo** e, em seguida, insira um arquivo de instalação com a extensão apropriada.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Implantação do aplicativo do Windows 10 usando o Intune <!-- 2309001 -->
Criado com base no suporte existente para aplicativos LOB (linha de negócios) e aplicativos Microsoft Store para Empresas, os administradores podem usar o Intune para implantar a maioria dos aplicativos existentes de sua organização nos usuários finais em dispositivos Windows 10. Os administradores podem adicionar, instalar e desinstalar aplicativos para usuários do Windows 10 em diversos formatos, como MSIs, Setup.exe ou MSP. O Intune avaliará as regras de requisitos antes de baixar e instalar, notificar os usuários finais do status ou dos requisitos de reinicialização usando a Central de Ações do Windows 10. Essa funcionalidade desbloqueará efetivamente organizações interessadas em deslocar essa carga de trabalho para o Intune e a nuvem. No momento, este recurso está em versão prévia pública e esperamos adicionar novas funcionalidades significativas a ele durante os próximos meses. 

#### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>Configurações da APP (Política de Proteção de Aplicativo) para dados da Web <!-- 2662995 -->
Configurações de política de aplicativo para conteúdo Web em dispositivos Android e iOS serão atualizadas para lidar melhor com links Web http e https, bem como transferência de dados por meio de Links Universais do iOS e Links de Aplicativo do Android. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Dispositivo de usuário final e menu de conteúdo do aplicativo <!-- 2771453 -->
Os usuários finais agora podem usar o menu de contexto no dispositivo e aplicativos para disparar ações comuns, como renomear um dispositivo ou verificar a conformidade. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Atalhos de teclado do Portal da Empresa do Windows <!-- 2771518 -->
Os usuários finais agora poderão disparar ações de aplicativo e do dispositivo no Portal da Empresa do Windows usando atalhos de teclado (aceleradores).

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Exigir PIN não biométrico após um tempo limite especificado <!-- 1506985 -->
Ao exigir um PIN não biométrico após o tempo limite especificado pelo administrador, o Intune oferecerá maior segurança para aplicativos habilitados para MAM (Gerenciamento de Aplicativo Móvel) restringindo o uso de identificação biométrica para acesso a dados corporativos. As configurações afetarão os usuários que contam com Touch ID (iOS), Face ID (iOS), Android Biometric ou outros métodos de autenticação biométrica futuros para acessar seus aplicativos habilitados para APP/MAM. Essas configurações permitirão que os administradores do Intune tenham controle mais granular sobre acesso de usuário, eliminando casos em que um dispositivo com várias impressões digitais ou outros métodos de acesso biométrico pode revelar dados corporativos para um usuário incorreto. No Portal do Azure, abra o **Microsoft Intune**. Selecione **Aplicativos clientes** > **Políticas de proteção de aplicativos** > **Adicionar uma política** > **Configurações**. Localize a seção **Acessar** para configurações específicas. Para obter informações sobre as configurações de acesso, confira [Configurações do iOS](../apps/app-protection-policy-settings-ios.md#access-requirements) e [Configurações do Android](../apps/app-protection-policy-settings-android.md#access-requirements).

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Configurações de transferência de dados da APP do Intune em dispositivos iOS registrados no MDM <!-- 2244713 -->
Você pode separar o controle de configurações de transferência de dados do Aplicativo do Intune em dispositivos registrados no MDM do iOS da especificação de identidade do usuário registrado, também conhecida como nome UPN. Os administradores que não estiverem usando o IntuneMAMUPN não observarão uma alteração de comportamento. Quando essa funcionalidade estiver disponível, os administradores que estiverem usando o IntuneMAMUPN para controlar o comportamento de transferência de dados em dispositivos registrados deverão revisar as novas configurações e atualizar as configurações de aplicativo conforme necessário.

#### <a name="windows-10-win32-apps----2617325---"></a>Aplicativos Win32 do Windows 10 <!-- 2617325 -->
Você pode configurar seus aplicativos do Win32 a serem instalados no contexto de usuário para usuários individuais, em vez de instalar o aplicativo para todos os usuários do dispositivo.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Aplicativos Win32 do Windows e scripts do PowerShell <!-- 2617330 -->
Os usuários finais não precisam mais fazer logon no dispositivo para instalar aplicativos do Win32 ou executar scripts do PowerShell. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Solução de problemas de instalação de aplicativos cliente <!-- 1363711 -->
Você pode solucionar problemas de sucesso da instalação de aplicativos cliente examinando a coluna rotulada **Instalação do aplicativo** na folha **Solucionar problemas**. Para exibir a folha **Solucionar problemas**, no portal do Intune, selecione **Solucionar problemas** em **Ajuda e suporte**.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>Criar sufixos DNS em perfis de configuração de VPN em dispositivos que executam o Windows 10<!-- 1333668 -->
Quando você cria um perfil de configuração do dispositivo VPN (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **plataforma Windows 10 ou posterior** > O tipo de perfil **VPN**), insere algumas configurações de DNS. Com essa atualização, também é possível inserir vários **sufixos DNS** no Intune. Ao usar sufixos DNS, você pode procurar um recurso de rede usando o nome curto dele em vez do nome de domínio totalmente qualificado (FQDN). Essa atualização também permite alterar a ordem dos sufixos DNS no Intune.
[Configurações de VPN do Windows 10](../configuration/vpn-settings-windows-10.md#dns-settings) lista as configurações DNS atuais.
Aplica-se a: dispositivos Windows 10

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Suporte para VPN Always On em perfis de trabalho do Android Enterprise <!-- 1333705 -->
Nesta atualização, é possível usar as conexões VPN Always On em dispositivos Android empresariais com perfis de trabalho gerenciados. As conexões VPN sempre ativadas permanecem conectadas ou são reconectadas imediatamente quando o usuário desbloqueia o dispositivo, quando o dispositivo é reiniciado ou quando a rede sem fio é alterada. Você também pode colocar a conexão em modo de "bloqueio", o que bloqueia todo o tráfego até que a conexão VPN seja ativada.
É possível habilitar a VPN Always On na **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Android enterprise** para configurações da plataforma > **Restrições de dispositivo** > **Conectividade**.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>Emitir certificados SCEP para dispositivos sem usuário <!-- 1744554 -->
Atualmente, os certificados são emitidos para usuários. Com essa atualização, os certificados SCEP podem ser emitidos para dispositivos, incluindo dispositivos sem usuário, como quiosques (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Certificado SCEP** para perfil). Outras atualizações incluem:
- A propriedade **Assunto** em um perfil SCEP agora é uma caixa de texto personalizada e pode incluir novas variáveis. 
- A propriedade **Nome alternativo da entidade (SAN)** em um perfil SCEP agora é um formato de tabela e pode incluir novas variáveis. Na tabela, um administrador pode adicionar um atributo e preencher o valor em uma caixa de texto personalizada. A SAN será compatível com os seguintes atributos: 
  - DNS
  - Endereço de email
  - UPN

  Essas novas variáveis podem ser adicionadas com texto estático em uma caixa de texto de valor personalizada. Por exemplo, o atributo DNS pode ser adicionado como `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Os símbolos de chaves, ponto e vírgula e barra vertical “ { } ; | ” não funcionarão no texto estático da SAN. Apenas uma das novas variáveis de certificado do dispositivo a serem aceitas para `Subject` ou `Subject alternative name` devem ser colocadas entre chaves. 

Novas variáveis de certificado do dispositivo:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
> - `{{FullyQualifiedDomainName}}` funciona somente para dispositivos Windows e unidos ao domínio. 
> - Ao especificar propriedades do dispositivo, como IMEI, número de série e nome de domínio totalmente qualificado no assunto ou SAN para um certificado de dispositivo, esteja ciente de que essas propriedades podem ser falsificadas por uma pessoa com acesso ao dispositivo. 

[Criar um perfil de certificado SCEP](../protect/certificates-profile-scep.md#create-a-scep-certificate-profile) lista as variáveis atuais ao criar um perfil de configuração de SCEP. 

Aplica-se a: Windows 10 e posterior e iOS, com suporte a Wi-Fi

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Bloquear remotamente dispositivos sem conformidade <!-- 2064495 -->
Quando um dispositivo não for compatível, será possível criar uma ação na política de conformidade que bloqueia o dispositivo remotamente. Em Intune > **Conformidade do dispositivo**, crie uma nova política ou selecione uma política de conformidade existente > **Propriedades**. Selecione **Ações em caso de não conformidade** > **Adicionar** e opte por bloquear remotamente o dispositivo.
Com suporte em: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 e posterior 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Melhorias no perfil de quiosque do Windows 10 e posterior no portal do Azure <!-- 2748224 -->
Essa atualização inclui as seguintes melhorias no perfil de configuração do dispositivo Windows 10 Kiosk (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** para plataforma > **Versão prévia do Quiosque** para o tipo de perfil): 
- Atualmente, você pode criar vários perfis de quiosque no mesmo dispositivo. Com essa atualização, o Intune dará suporte somente a um perfil de quiosque por dispositivo. Se você ainda precisar de vários perfis de quiosque em um único dispositivo, poderá usar um URI personalizado.
- Em um perfil de **Quiosque de vários aplicativos**, é possível selecionar o tamanho do bloco de aplicativos e a ordem do **layout do menu Iniciar** na grade de aplicativos. Se você preferir mais personalização, poderá fazer o upload de um arquivo XML.
- As configurações do navegador de quiosque serão movidas para as configurações de **Quiosque**. Atualmente, as configurações de **Navegador da Web de quiosque** têm sua categoria própria no Portal do Azure.
Aplica-se ao Windows 10 e posteriores

#### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Solicitação de PIN ao alterar impressões digitais ou identificação de rosto em um dispositivo iOS  <!-- 2637704  -->
Os usuários agora são solicitados a inserir um PIN após fazerem alterações biométricas em seu dispositivo iOS. Isso inclui alterações em impressões digitais ou Face ID registradas. O tempo da solicitação depende da configuração do tempo limite em *Verificar novamente os requisitos de acesso após (minutos)* .  Quando não há um PIN definido, o usuário é solicitado a definir um. 
 
Esse recurso está disponível apenas para iOS e requer a participação de aplicativos que integram o SDK do aplicativo Intune para iOS, versão 9.0.1 ou posterior. A integração do SDK é necessária para que o comportamento possa ser aplicado aos aplicativos de destino. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. Alguns aplicativos que participam incluem WXP, Outlook, Managed Browser e Yammer.

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>Suporte para controle de acesso à rede em clientes VPN do iOS <!-- 1333693 -->
Com essa atualização, há uma nova configuração para habilitar o NAC (Controle de Acesso à Rede) quando você cria um perfil de configuração de VPN para Cisco AnyConnect, F5 Access e Citrix SSO para iOS. Essa configuração permite que a ID de NAC do dispositivo seja incluída no perfil de VPN. Atualmente, não existe nenhum cliente VPN nem solução de parceiro NAC que dê suporte a essa nova ID de NAC, mas manteremos você informado por meio de nossa [postagem no blog de suporte](ttps://aka.ms/iOS12_and_vpn) quando houver.

Para usar o NAC, você precisará:
1. Optar por permitir que o Intune inclua as identificações de dispositivo em perfis de VPN
2. Atualizar o seu software/firmware de provedor NAC usando as diretrizes diretamente do seu provedor NAC

Para obter informações sobre essa configuração em um perfil VPN do iOS, confira [Adicionar configurações de VPN a dispositivos iOS no Microsoft Intune](../configuration/vpn-settings-ios.md). Para obter mais informações sobre o controle de acesso de rede, confira [Integração de NAC (controle de acesso à rede) com o Intune](../protect/network-access-control-integrate.md). 

Aplica-se a: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Remover um perfil de email de um dispositivo, mesmo quando há apenas um email perfil <!-- 1818139 -->
Anteriormente, não era possível remover um perfil de email de um dispositivo *quando* ele era o único perfil de email. Com essa atualização, esse comportamento foi alterado. Agora, você pode remover um perfil de email, mesmo que ele seja o único perfil de email no dispositivo. Confira [Adicionar configurações de email em dispositivos usando o Intune](../configuration/email-settings-configure.md) para obter detalhes.

#### <a name="powershell-scripts-and-aad----2309469---"></a>Scripts do PowerShell e AAD <!-- 2309469 -->
Scripts do PowerShell no Intune podem ser direcionados para grupos de segurança de dispositivo do AAD.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nova configuração padrão "Tipo de senha obrigatória" para Android, Android Enterprise<!-- 2649963 -->
Quando você cria uma nova política de conformidade (**Intune** > **Conformidade do dispositivo** > **Políticas** > **Criar política** > **Android** ou **Android Enterprise** para a Plataforma > Segurança do Sistema), o valor padrão para **Tipo de senha necessário** muda:

De: padrão do dispositivo Para: pelo menos numérico

Aplica-se a: Android, Android Enterprise

Para ver essas configurações, vá para [Android](../protect/compliance-policy-create-android.md) e [Android Enterprise](../protect/compliance-policy-create-android-for-work.md).

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Usar uma chave pré-compartilhada em um perfil de Wi-Fi do Windows 10 <!-- 2662938 -->
Com essa atualização, você pode usar uma chave pré-compartilhada (PSK) com o protocolo de segurança WPA/WPA2-Personal para autenticar um perfil de configuração de Wi-Fi no Windows 10. Você também pode especificar a configuração de custo para uma rede limitada para dispositivos com a atualização de outubro de 2018 do Windows 10.

No momento, é preciso importar um perfil de Wi-Fi ou criar um perfil personalizado para usar uma chave pré-compartilhada. [Configurações de Wi-Fi no Windows 10](../configuration/wi-fi-settings-windows.md) lista as configurações atuais. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>Remover certificados PKCS e SCEP de seus dispositivos <!-- 3218390 -->
Em alguns cenários, os certificados PKCS e SCEP permaneciam nos dispositivos, mesmo quando uma política era removida de um grupo, quando uma configuração ou implantação de conformidade era excluída ou quando um administrador atualizava um perfil de SCEP ou de PKCS existente. Essa atualização alterou esse comportamento. Há alguns cenários em que os certificados PKCS e SCEP são removidos dos dispositivos e alguns cenários em que eles permanecem no dispositivo. Confira [Remove SCEP and PKCS certificates in Microsoft Intune](../protect/remove-certificates.md) (Remover certificados SCEP e PKCS no Microsoft Intune) para conhecer esses cenários.

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Usar o Gatekeeper em dispositivos macOS para conformidade <!-- 2504381 -->
Esta atualização inclui o Gatekeeper para macOS avaliar dispositivos quanto à conformidade. Para definir a propriedade de Gatekeeper, escolha [Adicionar uma política de conformidade do dispositivo para dispositivos macOS](../protect/compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Aplicar perfil do Autopilot a dispositivos Windows 10 registrados que ainda não estão registrados no Autopilot <!-- 1558983 -->
É possível aplicar perfis do Autopilot a dispositivos Windows 10 registrados que ainda não estiverem registrados no Autopilot. No perfil do Autopilot, escolha a opção **Converter todos os dispositivos de destino em Autopilot** para registrar automaticamente dispositivos não Autopilot no serviço de implantação do Autopilot. Aguarde 48 horas para que o registro seja processado. Quando o registro do dispositivo é cancelado e redefinido, o Autopilot o provisiona.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Criar e atribuir vários perfis de Página de Status de Registro a grupos do Azure AD <!-- 2526564 -->
Agora é possível [criar e atribuir](../enrollment/windows-enrollment-status.md) vários perfis de Página de status de registro a grupos do Azure ADD.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migração do Programa de registro de dispositivos para o Apple Business Manager no Intune <!--2748613-->
O ABM (Apple Business Manager) funciona no Intune, e você pode atualizar sua conta do DEP (Programa de registro de dispositivos) para o ABM. O processo no Intune é o mesmo. Para atualizar sua conta da Apple do DEP para o ABM, vá para [https://support.apple.com/HT208817]( https://support.apple.com/HT208817).

#### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Guias de status de alerta e registro na página Visão geral do registro de dispositivos <!--2748656-->
Alertas e falhas de registro agora são exibidos em guias separadas na página de visão geral de registro do dispositivo.

#### <a name="enrollment-abandonment-report----1382924---"></a>Relatório de abandono de registro <!-- 1382924 -->
Um novo relatório que fornece detalhes sobre registros abandonados está disponível em **Registro de dispositivo** > **Monitorar**. Para obter mais informações, confira [Relatório de abandono do portal da empresa](../enrollment/enrollment-report-company-portal-abandon.md).

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Novo recurso de termos de uso do Azure Active Directory <!-- 2870393 -->
O Azure Active Directory tem um recurso de termos de uso que você pode usar em vez dos termos e condições existentes do Intune. O recurso de termos de uso do Azure AD oferece mais flexibilidade sobre quais termos mostrar e quando mostrá-los, melhor suporte à localização, mais controle em como os termos são renderizados e melhor geração de relatórios. O recurso de termos de uso do Azure AD requer o Azure Active Directory Premium P1, que também faz parte do pacote Enterprise Mobility + Security E3. Para obter mais informações, confira o [artigo Gerenciar seus termos e condições da sua empresa para acesso do usuário](../enrollment/terms-and-conditions-create.md).

#### <a name="android-device-owner-mode-support---3188762--"></a>Suporte ao modo de Proprietário do Dispositivo Android <!--3188762-->
Para o Registro Móvel do Samsung Knox, o Intune agora dá suporte ao registro de dispositivos para o modo de Proprietário de Dispositivo Android do gerenciamento. Os usuários em redes de celular ou Wi-Fi podem inscrever seus dispositivos com apenas alguns toques ao o ligarem pela primeira vez. Para saber mais, confira [Inscrever automaticamente os dispositivos Android usando o Knox Mobile Enrollment da Samsung](../enrollment/android-samsung-knox-mobile-enroll.md).

### <a name="device-management"></a>Gerenciamento de dispositivos
#### <a name="new-settings-for-software-updates------1907869---"></a>Novas configurações de atualizações de software   <!-- 1907869 -->  
- Agora, você pode configurar algumas notificações para alertar os usuários finais sobre reinicializações exigidas para concluir a instalação das atualizações de software mais recentes.   
- Agora, você pode configurar um prompt de aviso de reinicialização para reinicializações que ocorrem fora do horário de trabalho, o que dá suporte a cenários de BYOD.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Agrupar dispositivos registrados no Windows Autopilot por ID de correlação <!-- 2075110 -->
O Intune agora dá suporte ao agrupamento de dispositivos Windows por uma ID de correlação quando registrado usando o [Autopilot para dispositivos existentes](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) por meio do Configuration Manager. A ID de correlação é um parâmetro do arquivo de configuração do Autopilot. O Intune definirá automaticamente o [atributo do dispositivo do Azure AD enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) para que ele seja igual a "OfflineAutopilotprofile-<correlator ID>". Isso permite que os grupos dinâmicos arbitrários do Azure AD sejam criados com base na ID de correlação por meio do atributo enrollmentprofileName para registros offline do Autopilot. Para obter mais informações, confira [Windows Autopilot para dispositivos existentes](../enrollment/enrollment-autopilot.md#windows-autopilot-for-existing-devices).

#### <a name="intune-app-protection-policies----2984657---"></a>Políticas de proteção de aplicativo do Intune <!-- 2984657 -->
As políticas de Proteção de Aplicativo do Intune permitem que você defina várias configurações de proteção de dados para aplicativos protegidos do Intune, como Microsoft Word e Microsoft Outlook. Alteramos a aparência dessas configurações para [iOS](../apps/app-protection-policy-settings-ios.md) e [Android](../apps/app-protection-policy-settings-android.md) para tornar mais fácil encontrar as configurações individuais. Há três categorias de configurações de política:
- **Realocação de dados** – esse grupo inclui os controles DLP (prevenção de perda dados), como restrições de cortar, copiar, colar e salvar-como. Essas configurações determinam como os usuários interagem com os dados nos aplicativos.
- **Requisitos de acesso** – esse grupo contém as opções de PIN por aplicativo que determinam como o usuário final acessa os aplicativos em um contexto de trabalho.  
- **Inicialização condicional** – esse grupo contém configurações como configurações de sistema operacional mínimo, jailbreak e detecção de dispositivos com raiz e períodos de cortesia offline.  
  
A funcionalidade das configurações não muda, mas será mais fácil encontrá-la quando você trabalhar na política de fluxo de criação.

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Restringir aplicativos e bloquear o acesso a recursos da empresa em dispositivos Android <!-- 2451462  -->  
Na **Conformidade do dispositivo** > **Políticas** > **Criar política** > **Android**  >  **Segurança do sistema**, há uma nova configuração na seção *Segurança do dispositivo*, chamada **Aplicativos restritos**. A configuração **Aplicativos restritos** usará uma política de conformidade para bloquear o acesso a recursos corporativos se determinados aplicativos forem instalados no dispositivo. O dispositivo é considerado não compatível até que os aplicativos restritos sejam removidos dele.
Aplica-se a: 
- Android

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>O Intune dará suporte a um tamanho máximo de pacote de 8 GB para aplicativos LOB <!-- 1727158 -->
O Intune aumentou o tamanho máximo do pacote para 8 GB para aplicativos de LOB (linha de negócios). Para obter mais informações, confira [Adicionar aplicativos ao Microsoft Intune](../apps/apps-add.md).

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Adicionar imagem de marca personalizada ao aplicativo do Portal da Empresa <!-- 1916266 -->
Como administrador do Microsoft Intune, você poderá fazer upload de uma imagem de marca personalizada que será exibida como uma imagem de tela de fundo na página do perfil do usuário no aplicativo do Portal da Empresa iOS. Para obter mais informações sobre como configurar o aplicativo do Portal da Empresa, confira [Como configurar o aplicativo do Portal da Empresa do Microsoft Intune](../apps/company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>O Intune manterá o idioma localizado do Office ao atualizar o Office nos computadores dos usuários finais <!-- 2971030 -->
Quando o Intune instalar o Office nos computadores do seu usuário final, os usuários finais obterão automaticamente os mesmos pacotes de idioma que eles tinham com as instalações anteriores do .MSI Office. Para obter mais informações, confira [Atribuir aplicativos do Office 365 a dispositivos Windows 10 com o Microsoft Intune](../apps/apps-add-office365.md).

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Nova experiência de suporte do Intune no portal de Gerenciamento de Dispositivo do Microsoft 365 <!-- 3076965 -->
Estamos desenvolvendo uma nova experiência de Ajuda e Suporte para o Intune no [Portal de Gerenciamento de Dispositivo do Microsoft 365]( http://devicemanagement.microsoft.com). A nova experiência permite que você descreva seu problema em suas próprias palavras e receba informações de solução de problemas e conteúdo de correção baseado na Web. Essas soluções são oferecidas por meio de um algoritmo de aprendizado de máquina baseado em regras, orientado por consultas de usuário.  

Além das orientações específicas do problema, você também pode usar o novo fluxo de trabalho de criação do caso para abrir um caso de suporte por email ou telefone.  

Para clientes que fazem parte da implementação, essa nova experiência substitui a experiência de Ajuda e Suporte atual de um conjunto estático de opções pré-selecionadas com base na área do console em que você está quando você abre a Ajuda e Suporte.  

*Esta nova experiência de Ajuda e Suporte está sendo distribuída a alguns, mas não todos, os locatários e está disponível no Portal de Gerenciamento de Dispositivo. Os participantes dessa nova experiência são selecionados aleatoriamente entre os locatários do Intune disponíveis. Novos locatários serão adicionados à medida que expandirmos a distribuição.*  

Para obter mais informações, confira [Experiência de Ajuda e Suporte](get-support.md#help-and-support-experience) em Como obter suporte para o Microsoft Intune.  

#### <a name="powershell-module-for-intune--preview-available----951068---"></a>Módulo do PowerShell para Intune – Versão prévia disponível <!-- 951068 -->
Um novo módulo do PowerShell, que dá suporte para a API do Intune por meio do Microsoft Graph, agora está disponível em versão prévia no [GitHub](https://aka.ms/intunepowershell). Para obter detalhes de como usar esse módulo, confira o LEIAME nesse local.

<!-- ########################## -->
## <a name="september-2018"></a>Setembro de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Remover a duplicação dos blocos de status de proteção de aplicativo <!-- 3083391 -->
Os blocos **Status do usuário para iOS** e **Status do usuário para Android** existiam nas páginas **Aplicativos Cliente – Visão geral** e **Aplicativos Cliente – Status de proteção do aplicativo**. Os blocos de status foram removidos da página **Aplicativos Cliente – Visão geral** para evitar a duplicação. 

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Com suporte para mais ACs (autoridades de certificação) de terceiros <!-- 3093107 -->
Usando o protocolo SCEP, agora você poderá emitir novos certificados e renovar certificados em dispositivos móveis usando Windows, iOS, Android e macOS.

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="intune-moves-to-support-ios-10-and-later----2454656---"></a>O Intune muda para dar suporte ao iOS 10 e posterior <!-- 2454656 -->  
Agora o registro do Intune, o Portal da Empresa e o navegador gerenciado dão suporte a dispositivos iOS que executam o iOS 10 e posterior. Para verificar se há dispositivos ou usuários afetados em sua organização, vá para o Intune no portal do Azure > **Dispositivos** > **Todos os dispositivos**. Filtre por sistema operacional e clique em **Colunas** para exibir os detalhes da versão do sistema operacional. Solicite que os usuários atualizem seus dispositivos para uma versão do sistema operacional com suporte.  

Se você tiver algum dos dispositivos listados abaixo ou desejar registrar algum deles, esteja ciente de que eles são compatíveis somente com o iOS 9 e versões anteriores.  Para continuar acessando o Portal da Empresa do Intune, atualize esses dispositivos para dispositivos que dão suporte ao iOS 10 ou posteriores:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3ª geração) 
* iPad Mini (1ª geração)  

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Centro de Administração do Gerenciamento de Dispositivo do Microsoft 365 <!-- 3078424 -->
Uma das promessas do Microsoft 365 é a administração simplificada e, com o passar dos anos, nós integramos os serviços de back-end do Microsoft 365 para fornecer cenários de ponta a ponta, como Acesso Condicional do Azure AD e Intune. O novo [Centro de Administração do Microsoft 365](http://devicemanagement.microsoft.com) é o lugar para consolidar, simplificar e integrar a experiência de administração. O workspace do especialista para Gerenciamento de Dispositivos fornece acesso fácil a todos os dispositivos e informações de gerenciamento de aplicativos e as tarefas que sua organização precisa. Esperamos que ele se torne o workspace de nuvem primária para as equipes de computação do usuário final corporativo.


<!-- ########################## -->
## <a name="august-2018"></a>Agosto de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Suporte de túnel de pacote para perfis VPN por aplicativo iOS para tipos de conexão personalizados e do Pulse Secure <!-- 1520957 -->
Ao usar um perfil VPN para cada aplicativo iOS, você pode escolher usar o túnel de camada de aplicativo (proxy de aplicativo) ou o túnel no nível do pacote (túnel de pacote). Essas opções estão disponíveis com os seguintes tipos de conexão:
- VPN personalizado
- Pulse Secure. Se você não tiver certeza de qual valor usar, confira a documentação do seu provedor VPN.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Atraso quando as atualizações de software do iOS são mostradas no dispositivo <!-- 1949583 -->
Em Intune > **Atualizações de Software** > **Atualizar políticas do iOS**, você pode configurar os dias e horários em que não deseja que sejam instaladas atualizações nos dispositivos. Em uma atualização futura, você poderá atrasar quando uma atualização de software é mostrada visivelmente no dispositivo, de 1 a 90 dias. 
[Configurar políticas de atualização do iOS no Microsoft Intune](../protect/software-updates-ios.md) lista as configurações atuais.

#### <a name="office-365-proplus-version----2213968---"></a>Versão do Office 365 ProPlus <!-- 2213968 -->
Ao atribuir os aplicativos do Office 365 ProPlus a dispositivos Windows 10 usando o Intune, você poderá selecionar a versão do Office. No portal do Azure, selecione **Microsoft Intune** > **Aplicativos** > **Adicionar Aplicativo**. Em seguida, selecione **Office 365 ProPlus Suite (Windows 10)** na lista suspensa **Tipo**. Selecione **Configurações do Pacote de Aplicativos** para exibir a folha associada. Defina o **Canal de Atualização** para um valor, como **Mensal**. Opcionalmente, remova outras versões do Office (msi) dos dispositivos de usuário final, selecionando **Sim**. Selecione **Específico** para instalar uma versão específica do Office para o canal selecionado em dispositivos de usuário final. Neste ponto, você pode selecionar a **Versão específica** do Office a ser usada. As versões disponíveis serão alteradas ao longo do tempo. Portanto, quando você cria uma nova implantação, as versões disponíveis podem ser mais recentes, e determinadas versões mais antigas podem não estar disponíveis. As implantações atuais continuarão a implantar a versão mais antiga, mas a lista de versões será atualizada continuamente por canal. Para mais informações, confira [Visão geral dos canais de atualização do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Suporte para registrar configuração de DNS para VPN do Windows 10 <!-- 2282852 -->
Com essa atualização, você pode configurar perfis VPN do Windows 10 para registrar dinamicamente os endereços IP atribuídos à interface VPN com o DNS interno, sem precisar usar perfis personalizados.
Para obter informações sobre as configurações de perfil VPN disponíveis, confira [Configurações de VPN do Windows 10](../configuration/vpn-settings-windows-10.md).

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>O instalador do Portal da Empresa do macOS agora inclui o número de versão no nome do arquivo instalador <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759---"></a>Atualizações automáticas de aplicativo iOS <!-- 2729759 -->
As atualizações automáticas do aplicativo funcionam para aplicativos licenciados para o dispositivo e para o usuário no iOS versão 11.0 e posteriores.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>O Windows Hello será direcionado a usuários e dispositivos <!-- 1106609 -->
Quando você cria uma política do [Windows Hello para Empresas](../protect/windows-hello.md), ela se aplica a todos os usuários da organização (abrange o locatário). Com esta atualização, a política também pode ser aplicada a usuários ou dispositivos específicos usando uma política de configuração do dispositivo (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Proteção de Identidade** > **Windows Hello para Empresas**).
No Intune no portal do Azure, as configurações e definições do Windows Hello agora existem tanto em **Registro do dispositivo** quanto em **Configuração do dispositivo**. O **Registro de dispositivos** é direcionado a toda a organização (abrange o locatário) e dá suporte ao Windows Autopilot (OOBE). A **Configuração do dispositivo** é direcionada a usuários e dispositivos usando uma política que é aplicada durante o check-in.
Esse recurso aplica-se a:  
- Windows 10 e posterior
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858---"></a>Zscaler é uma conexão disponível para perfis VPN no iOS <!-- 1769858 -->
Quando você cria um perfil de configuração do dispositivo VPN no iOS (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **iOS** plataforma > Tipo de perfil **VPN**), há vários tipos de conexão, incluindo Cisco, Citrix e outros. Essa atualização adiciona o Zscaler como um tipo de conexão. 
[Configurações de VPN para dispositivos que executam o iOS](../configuration/vpn-settings-ios.md) lista os tipos de conexão disponíveis.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077---"></a>Modo FIPS para perfis de Wi-Fi da empresa para Windows 10 <!-- 1879077 -->
Agora você pode habilitar o modo FIPS (padrão FIPS) para perfis de Wi-Fi da empresa para Windows 10 no portal do Azure do Intune. Verifique se o modo FIPS está habilitado na sua infraestrutura de Wi-Fi ao habilitá-lo em seus perfis de Wi-Fi.
[Configurações de Wi-Fi para dispositivos Windows 10 e posteriores no Intune](../configuration/wi-fi-settings-windows.md) mostra como criar um perfil de Wi-Fi.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Controlar o modo S em dispositivos Windows 10 e posteriores – versão prévia pública <!-- 1958649 -->
Com essa atualização de recurso, você pode criar um perfil de configuração do dispositivo que tira um dispositivo Windows 10 do modo S ou impede que os usuários tirem o dispositivo do modo S. Esse recurso está no Intune > **Configuração do dispositivo** > **Perfis** >  **Windows 10 e posteriores** > **Atualização de edição e alternância de modo**.
[Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode) (Introdução ao Windows 10 no modo S) fornece mais informações sobre o modo S.
Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).

#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Pacote de configuração do Windows Defender ATP adicionado automaticamente ao perfil de configuração <!-- 2144658 -->
Ao usar a [Proteção Avançada contra Ameaças e integrar](../protect/advanced-threat-protection.md#onboard-devices-by-using-a-configuration-profile) dispositivos no Intune, você teve que baixar um pacote de configuração e adicioná-lo ao seu perfil de configuração. Com essa atualização, o Intune obtém automaticamente o pacote da Central de Segurança do Windows Defender e adiciona-o ao seu perfil.
Aplica-se ao Windows 10 e posteriores.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Exigir que os usuários se conectem durante a instalação do dispositivo <!--2311457-->
Agora você pode definir perfis de dispositivo para exigir que o dispositivo se conecte a uma rede antes de continuar, após a página Rede, durante a instalação do Windows 10. Embora esse recurso esteja na versão prévia, um Windows Insider build 1809 ou posterior é necessário para usar essa configuração.
Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).

#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>Restringir aplicativos e bloquear o acesso aos recursos da empresa em dispositivos iOS e Android Enterprise <!-- 2451462 -->
Em **Conformidade de dispositivos** > **Políticas** > **Criar política** > **iOS** > **Segurança do Sistema**, há uma nova configuração **Aplicativos restritos**. Essa nova configuração usa uma política de conformidade para bloquear o acesso aos recursos da empresa quando determinados aplicativos estão instalados no dispositivo. O dispositivo é considerado não compatível até que os aplicativos restritos sejam removidos dele.
Aplica-se a: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Atualizações modernas de suporte a VPN para iOS <!-- 2459928, 1819876, and 2650856 -->
Essa atualização adiciona suporte aos seguintes clientes VPN do iOS:
- F5 Access (versão 3.0.1 e posterior)
- SSO da Citrix
- GlobalProtect da Palo Alto Networks versão 5.0 e posterior Também nessa atualização:
- O tipo de conexão do **F5 Access** existente foi renomeado para **F5 Access Herdado** para iOS.
- O tipo de conexão **GlobalProtect da Palo Alto Networks** existente foi renomeado para **GlobalProtect da Palo Alto Networks (herdado)** para iOS.
Os perfis existentes com esses tipos de conexão continuam a funcionar com seus respectivos clientes VPN herdados. Se você estiver usando o Cisco AnyConnect Herdado, o F5 Access Herdado, a VPN da Citrix ou o GlobalProtect da Palo Alto Networks versão 4.1 e anteriores com o iOS, passe a usar os novos aplicativos. Faça isso assim que possível para garantir que o acesso VPN esteja disponível para dispositivos iOS após a atualização para o iOS 12.
Para obter mais informações sobre perfis VPN e o iOS 12, confira o [Microsoft Intune Support Team Blog](https://go.microsoft.com/fwlink/?linkid=2013806) (Blog da equipe de suporte do Microsoft Intune).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Exportar políticas de conformidade do Portal Clássico do Azure para recriar essas políticas no portal do Azure do Intune <!-- 2469637 -->
As políticas de conformidade criadas no Portal Clássico do Azure serão preteridas. Você pode examinar e excluir as políticas de conformidade existentes, no entanto, você não pode atualizá-las. Se você precisar migrar políticas de conformidade para o portal do Azure do Intune atual, exporte as políticas como um arquivo separado por vírgula (arquivo *.csv*). Em seguida, use os detalhes no arquivo para recriar essas políticas no portal do Azure do Intune.

> [!IMPORTANT]
> Quando o Portal Clássico do Azure for desativado, você não poderá mais acessar ou exibir suas políticas de conformidade. Portanto, exporte as políticas e recrie-as no portal do Azure antes que o Portal Clássico do Azure seja desativado.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Better Mobile – novo parceiro de Defesa contra Ameaças Móveis <!-- 22662717 -->
Você pode controlar o acesso de dispositivos móveis aos recursos corporativos usando o Acesso Condicional com base na avaliação de risco realizada pela Better Mobile, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Bloquear o Portal da Empresa no modo de aplicativo único até a conexão do usuário <!--1067692 --> 
Caso você autentique um usuário por meio do Portal da Empresa e não pelo Assistente de Configuração durante o registro no DEP, haverá a opção de executar o Portal da Empresa no modo de aplicativo único. Essa opção bloqueia o dispositivo imediatamente depois que o Assistente de Configuração é concluído para que o usuário precise entrar para acessar o dispositivo. Esse processo garante que a integração do dispositivo seja concluída e ele não fique órfão em um estado sem nenhum usuário vinculado.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Atribuir um usuário e nome amigável a um dispositivo do Autopilot <!--1346521 -->
Agora você pode [atribuir um usuário a um único dispositivo do Autopilot](../enrollment/enrollment-autopilot.md). Os administradores também poderão atribuir nomes amigáveis para saudar o usuário durante a configuração do dispositivo com o Autopilot.
Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>Usar licenças de dispositivo VPP para pré-provisionar o Portal da Empresa durante o registro no DEP <!-- 1608345 -->
Agora você pode usar licenças de dispositivo do VPP (Volume Purchase Program) para pré-provisionar o Portal da Empresa durante os registros no DEP (Programa de registro de dispositivos). Para fazer isso, quando você [criar ou editar um perfil de registro](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), especifique o token VPP que deseja usar para instalar o Portal da Empresa. Verifique se o token não expira e se você tem licenças suficientes para o aplicativo de Portal da Empresa. Caso o token for expirar ou for executado sem licenças, o Intune enviará por push o Portal da Empresa da App Store (uma ID da Apple será solicitada).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Confirmação necessária para excluir o token do VPP que está sendo usado para o pré-provisionamento do Portal da Empresa <!-- 2237634 -->
Agora será necessária uma confirmação para excluir um token do VPP (Volume Purchase Program) se ele estiver sendo usado para pré-provisionar o Portal da Empresa durante o registro no DEP.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Bloquear registros de dispositivos Windows pessoais <!-- 1849498 -->
Você pode [bloquear o registro de dispositivos pessoais do Windows](../enrollment/enrollment-restrictions-set.md) no [gerenciamento de dispositivo móvel](../enrollment/windows-enroll.md) no Intune. Os dispositivos registrados com o [agente Intune PC](../manage-windows-pcs-with-microsoft-intune.md) não podem ser bloqueados com esse recurso. Esse recurso será implantado nas próximas semanas, portanto, talvez você não o veja imediatamente na interface do usuário.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Especificar os padrões de nome de computador em um perfil do Autopilot <!--1849855-->
Você pode [especificar um modelo de nome do computador](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) para gerar e definir o [nome do computador](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) durante o registro do Autopilot. Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).

#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Ocultar as opções de alteração de conta na página de entrada e na página de erro de domínio da empresa para os perfis do Windows Autopilot <!--1901669 -->
Há [novas opções de perfil do Windows Autopilot](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) para os administradores ocultarem as opções de alteração de conta nas páginas de entrada e de erro de domínio da empresa. Para ocultar essas opções, é necessário configurar uma Identidade Visual da Empresa no Azure Active Directory. Aplica-se a: o build mais recente do [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (durante a versão prévia).

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Suporte do macOS para o Programa de Registro de Dispositivos da Apple <!-- 747651 -->
O Intune agora dá suporte ao registro de dispositivos macOS no DEP (Programa de Registro de Dispositivos) da Apple. Para obter mais informações, veja [Registrar automaticamente dispositivos macOS com o Programa de registro de dispositivos da Apple](../enrollment/device-enrollment-program-enroll-macos.md).

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="delete-jamf-devices----2653306--"></a>Excluir dispositivos do Jamf <!-- 2653306-->
Você pode excluir os dispositivos gerenciados pelo JAMF, acessando **Dispositivos** > escolha o dispositivo JAMF > **Excluir**.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Alterar a terminologia para "desativar" e "apagar" <!-- 2175759 -->
Para ficar consistente com a API do Graph, os termos a seguir foram alterados na documentação e na interface do usuário do Intune:
- **Remover dados da empresa** será alterado para "desativar"
- **Redefinição de fábrica** será alterado para **apagar**

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Caixa de diálogo de confirmação se administrador tentar excluir o MDM Push Certificate <!-- 297909500-->
Se alguém tentar excluir um Apple MDM Push Certificate, uma caixa de diálogo de confirmação exibirá o número de dispositivos iOS e macOS relacionados. Se o certificado for excluído, esses dispositivos precisarão ser registrados novamente.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Configurações de segurança adicionais do Windows Installer <!-- 2282430 -->
Você pode permitir que os usuários controlem as instalações de aplicativos. Se habilitadas, as instalações que, de outra forma, poderiam ser interrompidas devido a uma violação de segurança teriam permissão para continuar. Você pode direcionar o Windows Installer para usar permissões elevadas quando ele instalar algum programa em um sistema. Além disso, você pode habilitar itens de WIP (Proteção de Informações do Windows) a serem indexados e os metadados sobre eles armazenados em um local não criptografado. Quando a política é desabilitada, os itens protegidos pela WIP não são indexados e não aparecem nos resultados na Cortana ou no Explorador de Arquivos. A funcionalidade para essas opções está desabilitada por padrão. 

#### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nova atualização de experiência do usuário para o site do Portal da Empresa <!--2000968 -->
Nós adicionamos novos recursos ao site Portal da Empresa, com base nos comentários dos clientes. Você usufruirá de uma melhoria significativa nas funcionalidades existentes e na usabilidade dos seus dispositivos. As áreas do site, como detalhes do dispositivo, comentários e suporte e visão geral do dispositivo, receberam um design novo, moderno e responsivo. Você também verá:

- Fluxos de trabalho simplificados em todas as plataformas de dispositivo
- Fluxos de identificação e registro de dispositivo aprimorados
- Mensagens de erro mais úteis
- Linguagem mais amigável, menos jargão técnico
- Capacidade de compartilhar links diretos para aplicativos
- Melhor desempenho para grandes catálogos de aplicativos
- Maior acessibilidade para todos os usuários  

A [documentação do site Portal da Empresa do Intune](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) foi atualizada para refletir essas alterações. Para ver um exemplo das melhorias do aplicativo, confira [Atualizações da interface do usuário para aplicativos de usuário final do Intune](../whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Detecção avançada de jailbreak em relatórios de conformidade<!-- 2198738 -->
Os estados da configuração de detecção avançada de jailbreak agora aparecem em todos os relatórios de conformidade no console do administrador.

### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="scope-tags-for-policies---1081974---"></a>Marcas de escopo para políticas <!--1081974 -->
Você pode [criar marcas de escopo](scope-tags.md) para limitar o acesso aos recursos do Intune. Adicione uma marca de escopo a uma atribuição de função e, em seguida, adicione a marca de escopo a um perfil de configuração. A função só terá acesso a recursos com perfis de configuração que tenham marcas de escopo correspondentes (ou nenhuma marca de escopo).





<!-- ########################## -->
## <a name="july-2018"></a>Julho de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>Suporte para aplicativo de LOB (linha de negócios) do macOS <!-- 1895847 -->
O Microsoft Intune permite que aplicativos de LOB para macOS sejam implantados como **Obrigatório** ou **Disponível com registro**. Os usuários finais podem obter aplicativos implantados como **Disponível** usando o Portal da Empresa para macOS ou o [site do Portal da Empresa](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>Suporte de aplicativo nativo do iOS para o modo de quiosque <!-- 2051098 -->
Além dos Aplicativos da Loja e dos Aplicativos Gerenciados, agora você pode selecionar um Aplicativo Nativo (por exemplo, o Safari) que é executado no modo de quiosque em um dispositivo iOS.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Editar suas implantações de aplicativo do Office 365 Pro Plus <!-- 2150145 -->
Como administrador do Microsoft Intune, você tem maior capacidade para editar suas implantações de aplicativo do Office 365 Pro Plus. Além disso, não é mais necessário excluir as implantações para alterar uma das propriedades do pacote. No portal do Azure, selecione **Microsoft Intune** > **Aplicativos clientes** > **Aplicativos**. Na lista de aplicativos, selecione o Pacote Office 365 Pro Plus.  

#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>O SDK do Aplicativo Intune para Android atualizado está disponível <!-- 2744271-->
Uma versão atualizada do SDK do Aplicativo do Intune está disponível para fornecer suporte aos lançamentos da plataforma Android. Se você é um desenvolvedor de aplicativos e usa o SDK do Intune para Android, instale a versão atualizada do SDK do Aplicativo do Intune para garantir que a funcionalidade do Intune nos aplicativos Android continue viável, como esperado nos dispositivos da plataforma Android. Esta versão do SDK do Aplicativo do Intune fornece um plug-in interno que executa as atualizações do SDK. Não é necessário reescrever códigos existentes que estejam integrados. Para saber mais, confira [SDK do Intune para Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Se estiver usando o estilo de notificação anterior do Intune, recomendamos usar o ícone de porta-arquivos. Para saber mais sobre identidade visual, confira [este repositório do GitHub](https://github.com/msintuneappsdk/intune-app-partner-badge).

#### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Mais oportunidades de sincronização no aplicativo do Portal da Empresa para o Windows  
O aplicativo do Portal da Empresa para Windows agora permite que você inicie uma sincronização diretamente na barra de tarefas do Windows e no menu Iniciar. Esse recurso é especialmente útil se a única tarefa é sincronizar dispositivos e obter acesso a recursos corporativos. Para acessar o novo recurso, clique com o botão direito do mouse no ícone do Portal da Empresa fixado na barra de tarefas ou no menu Iniciar. Nas opções de menu (também conhecidas como lista de atalhos), selecione **Sincronizar este dispositivo**. O Portal da Empresa será aberto na página **Configurações** e iniciará a sincronização. Para ver a nova funcionalidade, confira [Novidades da interface do usuário](../whats-new-app-ui.md).   

#### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Novas experiências de navegação no aplicativo do Portal da Empresa para o Windows  
Agora, ao navegar ou pesquisar aplicativos no aplicativo do Portal da Empresa para o Windows, você pode alternar entre a exibição **Blocos** existente e a exibição **Detalhes** recém-adicionada. A nova exibição lista detalhes do aplicativo, como nome, fornecedor, data de publicação e status da instalação.  

A exibição **Instalados** da página **Aplicativos** permite que você veja detalhes sobre as instalações de aplicativos concluídas e em andamento. Para ver a aparência da nova exibição, confira [Novidades da interface do usuário](../whats-new-app-ui.md).  

#### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Melhoria na experiência do aplicativo do Portal da Empresa para os gerentes de registros de dispositivo  
Quando um DEM (gerenciador de registros de dispositivo) entrar no aplicativo do Portal da Empresa para Windows, agora o aplicativo listará apenas o dispositivo em execução atual do DEM. Essa melhoria reduzirá os tempos limite que ocorriam quando o aplicativo tentava mostrar todos os dispositivos registrados pelo DEM.  

#### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Bloquear acesso do aplicativo com base em modelos e fornecedores de dispositivos não aprovados  <!-- 1425689 ! -->
O administrador de TI do Intune pode impor uma lista especificada de fabricantes Android e/ou modelos de iOS por meio das Políticas de Proteção de Aplicativo do Intune. O administrador de TI pode fornecer uma lista separada por ponto e vírgula de fabricantes para políticas do Android e de modelos de dispositivos para políticas do iOS. As Políticas de Proteção de Aplicativo do Intune servem apenas para Android e iOS. Há duas ações separadas que podem ser executadas nessa lista especificada:
- Um bloqueio de acesso do aplicativo em dispositivos que não estão especificados.
- Ou uma limpeza seletiva de dados corporativos em dispositivos que não estão especificados. 

O usuário não conseguirá acessar o aplicativo direcionado se os requisitos por meio da política não forem atendidos. Com base nas configurações, o usuário pode ser bloqueado ou passar por uma limpeza seletiva dos dados corporativos no aplicativo. Em dispositivos iOS, esse recurso exige a participação de aplicativos (tais como WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de Aplicativo do Intune para que esse recurso seja imposto aos aplicativos de destino. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. No Android, esse recurso exige a versão mais recente do Portal da Empresa. 

Em dispositivos de usuário final, o cliente do Intune executará uma ação com base em uma correspondência simples das cadeias de caracteres especificadas na folha do Intune para Políticas de Proteção de Aplicativo. Isso depende totalmente do valor informado pelo dispositivo. Por isso, o administrador de TI é incentivado a garantir que o comportamento desejado seja preciso. Isso pode ser feito testando essa configuração com base em vários fabricantes e modelos de dispositivo direcionados a um grupo de usuários pequeno. No Microsoft Intune, selecione **Aplicativos clientes** > **Políticas de proteção de aplicativo** para exibir e adicionar as políticas de proteção de aplicativo. Para obter mais informações sobre as políticas de proteção de aplicativo, consulte [Quais são as políticas de proteção de aplicativo](../apps/app-protection-policy.md) e [Apagar dados seletivamente usando ações de acesso da política de Proteção de Aplicativo no Intune](../apps/app-protection-policies-access-actions.md).

#### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Acesso ao build de pré-lançamento do Portal da Empresa do macOS <!-- 1734766 -->
Usando o Microsoft AutoUpdate, você pode inscrever-se para receber os builds antecipadamente ao ingressar no Programa Insider. A inscrição permite que você use o Portal da Empresa atualizado antes que ele esteja disponível para seus usuários finais. Para obter mais informações, veja o [Blog do Microsoft Intune](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Criar política de conformidade do dispositivo usando as configurações do Firewall em dispositivos macOS <!-- 1497640 -->
Quando você cria uma política de conformidade do macOS (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Plataforma: macOS** > **Segurança do sistema**), há algumas novas configurações de **Firewall** disponíveis: 

- **Firewall**: configure como conexões de entrada são tratadas em seu ambiente.
- **Conexões de entrada**: **Bloquear** todas as conexões de entrada, exceto as conexões necessárias para serviços básicos da Internet, como DHCP, Bonjour e IPsec. Essa configuração também bloqueia todos os serviços de compartilhamento.
- **Modo Furtivo**: **Habilite** o modo furtivo para impedir que o dispositivo responda a solicitações de investigação. O dispositivo continua a responder a solicitações de entrada para aplicativos autorizados.

Aplica-se a: macOS 10.12 e posteriores

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Novo perfil de configuração de dispositivo de Wi-Fi para Windows 10 e posterior <!-- 1879077 -->
No momento, você pode importar e exportar perfis de Wi-Fi usando arquivos XML. Com essa atualização, você pode criar um perfil de configuração de dispositivo de Wi-Fi diretamente no Intune, como em algumas outras plataformas.

Para criar o perfil, abra **Configuração do dispositivo** > **Perfis** > **Criar Perfil** > **Windows 10 e posteriores** > **Wi-Fi**. 

Aplica-se ao Windows 10 e posteriores.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Quiosque – obsoleto, está esmaecido e não pode ser alterado <!-- 2149998 -->
O recurso (versão prévia) Quiosque (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10 e posterior** > **Restrições do dispositivo**) está obsoleto e foi substituído por [Configurações de quiosque para o Windows 10 e posterior](../configuration/kiosk-settings.md). Com essa atualização, o recurso **Quiosque – obsoleto** fica esmaecido e a interface do usuário não pode ser alterada nem atualizada. 

Para habilitar o modo de quiosque, confira [Configurações de quiosque para Windows 10 e posteriores](../configuration/kiosk-settings.md).

Aplica-se ao Windows 10 e posteriores, Windows Holographic for Business

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>APIs para usar autoridades de certificação de terceiros <!-- 2184013 -->
Nesta atualização, há uma API Java que permite a integração das autoridades de certificação de terceiros ao Intune e ao SCEP. Assim, os usuários poderão adicionar o certificado SCEP a um perfil e aplicá-lo aos dispositivos usando o MDM.

Atualmente, o Intune permite [Solicitações SCEP usando serviços de certificados do Active Directory](../protect/certificates-scep-configure.md).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Alternar para mostrar ou não mostrar o botão Encerrar Sessão em um navegador de quiosque <!-- 2455253 -->
Agora você pode configurar se os navegadores de Quiosque mostram ou não o botão Encerrar Sessão. Veja o controle em **Configuração do dispositivo** > **Quiosque (versão prévia)**  > **Navegador da Web de quiosque**. Se estiver habilitado, quando um usuário clicar no botão, o aplicativo solicitará uma confirmação para encerrar a sessão. Quando confirmado, o navegador limpa todos os dados de navegação e navega novamente para a URL padrão.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Criar um perfil de configuração de celular do eSIM <!-- 2564077 -->
Em **Configuração do dispositivo**, você pode criar um perfil de celular eSIM. É possível importar um arquivo contendo os códigos de ativação de celular fornecidos pela operadora do dispositivo móvel. Em seguida, você pode implantar esses perfis nos dispositivos Windows 10 habilitados para eSIM LTE, como o Surface Pro LTE e outros dispositivos compatíveis com eSIM.

Verifique se seus [dispositivos são compatíveis com perfis de eSIM](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Aplica-se ao Windows 10 e posteriores.

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Selecionar as categorias de dispositivo usando as configurações de Acessar Trabalho ou Escola <!-- 1058963 eenotready --> 
Se você tiver habilitado o [mapeamento do grupo de dispositivos](../enrollment/device-group-mapping.md), os usuários no Windows 10 passarão a receber uma solicitação para selecionar uma categoria de dispositivo após o registro por meio do botão **Conectar** em **Configurações** > **Contas** > **Acesso corporativo ou de estudante**. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Usar sAMAccountName como o nome de usuário da conta para perfis de email <!-- 1500307 -->
Você pode usar o **sAMAccountName** local como o nome de usuário da conta para perfis de email para Windows 10, iOS e Android. Você também pode obter o domínio do atributo `domain` ou `ntdomain` no Azure AD (Azure Active Directory). Ou insira um domínio estático personalizado.

Para usar esse recurso, você deve sincronizar o atributo `sAMAccountName` do seu ambiente do Active Directory local com o Azure AD.

Aplica-se ao: [Android](../configuration/email-settings-android.md), [iOS](../configuration/email-settings-ios.md), [Windows 10 e posteriores](../configuration/email-settings-windows-10.md)

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Ver perfis de configuração do dispositivo em conflito <!-- 1556983 -->
Em **Configuração do Dispositivo**, é mostrada uma lista dos perfis existentes. Com essa atualização, uma nova coluna foi adicionada para fornecer detalhes sobre os perfis que apresentam conflito. Você pode selecionar uma linha em conflito para ver a configuração e o perfil que apresenta o conflito. 

Mais detalhes sobre como [gerenciar perfis de configuração](../configuration/device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Novo status para dispositivos em conformidade do dispositivo <!-- 2308882 -->
Em **Conformidade do dispositivo** > **Políticas** > selecione uma política > **Visão geral**, os seguintes novos estados foram adicionados:
- bem-sucedido
- erro
- conflito
- pending
- não aplicável Uma imagem que mostra a contagem de dispositivos de uma plataforma diferente também é mostrada. Por exemplo, se você estiver procurando em um perfil do iOS, o novo bloco mostrará a contagem de dispositivos não iOS que também estão atribuídos a esse ele. Veja [Políticas de conformidade do dispositivo](../protect/compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>A conformidade do dispositivo é compatível com soluções de antivírus de terceiros <!-- 2325484 -->
Quando você cria uma política de conformidade do dispositivo (**Conformidade do dispositivo** > **Políticas** > **Criar política** > **Plataforma: Windows 10 e posteriores** > **Configurações** > **Segurança do sistema**), há novas opções de **[Segurança do Dispositivo](../protect/compliance-policy-create-windows.md)** : 
- **Antivírus**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções antivírus registradas com a Central de Segurança do Windows, como Symantec e Windows Defender. 
- **Software antispyware**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções de software antispyware registradas na Central de Segurança do Windows, como Symantec e Windows Defender. 

Aplica-se ao Windows 10 e posteriores 

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Marcar automaticamente os dispositivos Android registrados usando o Registro de Dispositivo Móvel do Samsung Knox como "corporativo". <!-- 2404851 -->
Por padrão, agora os dispositivos Android registrados usando o Registro de Dispositivo Móvel do Samsung Knox são marcados como **corporativos** em **Propriedade do Dispositivo**. Você não precisa identificar manualmente os dispositivos corporativos usando o IMEI nem os números de série antes de se registrar usando o Registro de Dispositivo Móvel do Knox.

#### <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Dispositivos sem a coluna de perfis na lista de tokens do programa de registro <!-- 1853904 -->
Na lista de tokens do programa de registro, há uma nova coluna que mostra o número de dispositivos sem um perfil atribuído. Isso ajuda os administradores a atribuir perfis a esses dispositivos antes de entregá-los aos usuários. Para ver a nova coluna, vá para **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Excluir em massa os dispositivos na folha de dispositivos <!-- 1793693 -->
Agora você pode excluir vários dispositivos ao mesmo tempo na folha Dispositivos. Escolha **Dispositivos** > **Todos os dispositivos** > selecione os dispositivos que deseja excluir > **Excluir**. Para dispositivos que não podem ser excluídos, um alerta será exibido.

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Alterações de nome do Google para Android for Work e Play for Work <!--842873 -->
O Intune atualizou a terminologia "Android for Work" para refletir as alterações de identidade visual do Google. Os termos "Android for Work" e "Play for Work" não são mais usados. É usada uma terminologia diferente, dependendo do contexto:
- "Empresarial Android" refere-se à pilha de gerenciamento Android moderna geral.
- "Perfil de Trabalho" ou "Proprietário de Perfil" refere-se a dispositivos BYOD gerenciados com perfis de trabalho.
- "Google Play gerenciado" refere-se à loja de aplicativos do Google.

#### <a name="rules-for-removing-devices----1609459---"></a>Regras para remover dispositivos <!-- 1609459 -->
Estão disponíveis novas regras que permitem remover automaticamente dispositivos que não fizeram check-in por um número de dias que você definir. Para ver a nova regra, vá para o painel **Intune**, selecione **Dispositivos** e selecione **Regras de limpeza do dispositivo**.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Suporte para uso único de propriedade corporativa para dispositivos Android <!-- 1630973 -->

Agora o Intune é compatível com dispositivos com Android altamente gerenciados e bloqueados no estilo quiosque. Isso permite que os administradores bloqueiem ainda mais o uso de um dispositivo para um único aplicativo ou um conjunto pequeno de aplicativos, e impede que os usuários habilitem outros aplicativos ou executem outras ações no dispositivo. Para configurar o quiosque do Android, vá o Intune > **Registro de dispositivo** > **Registro do Android** > **Registros de dispositivo de quiosque e tarefa**. Para obter mais informações, veja [Configurar o registro de dispositivos corporativos de quiosque do Android](../enrollment/android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Revisão por linha de identificadores de dispositivo corporativo duplicados carregados <!-- 2203794-->
Ao carregar IDs corporativas, agora o Intune fornece uma lista de todas as duplicatas e dá a opção de substituir ou manter as informações existentes. O relatório será exibido se houver duplicatas depois que você escolher **Registro de dispositivo** > **Identificadores de Dispositivo Corporativo** > **Adicionar Identificadores**. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Adicione manualmente identificadores de dispositivo corporativo <!-- 2203803 -->
Agora você pode adicionar manualmente IDs de dispositivo corporativo. Escolha **Registro de dispositivo** > **Identificadores de Dispositivo Corporativo** > **Adicionar**. 


<!-- ########################## -->
## <a name="june-2018"></a>Junho de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Suporte móvel do Microsoft Edge para políticas de Proteção de Aplicativo do Intune <!-- 1817882 -->
O navegador Microsoft Edge para dispositivos móveis agora dá suporte a políticas de proteção de aplicativo definidas no Intune.

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Recuperar a AUMID (ID de modelo de usuário do aplicativo associado) para aplicativos da Microsoft Store para Empresas no modo de quiosque <!-- 1560077 ! -->
O Intune agora pode recuperar as AUMIDs (IDs de modelo de usuário do aplicativo) para aplicativos WSfB (Microsoft Store para Empresas) para melhorar a configuração do perfil de quiosque.

Para saber mais sobre aplicativos da Microsoft Store para Empresas, confira [Gerenciar aplicativos da Microsoft Store para Empresas](../apps/windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Nova página da identidade visual do Portal da Empresa <!-- 1916370 -->
A página de identidade visual do Portal da Empresa tem um novo layout, mensagens e dicas de ferramenta.


### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo – novo parceiro de Defesa contra Ameaças Móveis <!-- 1169249 -->
É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pela Pradeo, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

#### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>Usar o modo FIPS com o conector do Certificado NDES <!-- 1333688 -->
Quando você instala o conector do Certificado NDES em um computador com o modo do padrão FIPS habilitado, a emissão e a revogação de certificados não funcionam conforme esperado. Com essa atualização, o suporte para o FIPS está incluído no conector do Certificado NDES. 

Essa atualização também inclui:

- O conector do Certificado NDES exige o .NET 4.5 Framework, que é automaticamente incluído no Windows Server 2016 e no Windows Server 2012 R2. Anteriormente, o .NET 3.5 Framework era a versão mínima necessária.
- O suporte ao TLS 1.2 é incluído no conector do Certificado NDES. Se o servidor com o conector do Certificado NDES instalado dá suporte ao TLS 1.2, o protocolo TLS 1.2 é usado. Se o servidor não dá suporte ao TLS 1.2, o TLS 1.1 é usado. Atualmente, o TLS 1.1 é usado para autenticação entre os dispositivos e o servidor.

Para obter mais informações, confira [Configurar e usar certificados SCEP](../protect/certificates-scep-configure.md) e [Configurar e usar certificados PKCS](../protect/certficates-pfx-configure.md).

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680----"></a>Suporte para perfis de VPN GlobalProtect da Palo Alto Networks <!-- 1333680 ! -->
Com essa atualização, você pode escolher o GlobalProtect da Palo Alto Networks como um tipo de conexão VPN para perfis VPN no Intune (**Configuração do dispositivo** > **Perfis**  >  **Criar perfil** > **Tipo de perfil** > **VPN**). Nesta versão, há suporte para as seguintes plataformas: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Adições às configurações das opções de segurança do dispositivo local <!-- 1403702 -->
Agora você pode definir as configurações adicionais de Opções de Segurança de Dispositivo Local para dispositivos Windows 10. Configurações adicionais estão disponíveis nas áreas de Cliente de Rede da Microsoft, Servidor de Rede Microsoft, Acesso e segurança de rede e Logon interativo. Encontre essas configurações na categoria Endpoint Protection quando você cria uma política de configuração de dispositivo com Windows 10.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Habilitar o modo de quiosque em dispositivos com Windows 10 <!-- 1560072 ! -->
Em dispositivos com Windows 10, você pode criar um perfil de configuração e habilitar o modo de quiosque (**Configuração do Dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** > **Restrições do Dispositivo** > **Quiosque**). Nesta atualização, a configuração **Quiosque (visualização)** é renomeada para **Quiosque (obsoleto)** . **Quiosque (obsoleto)** não é mais recomendado para uso, mas continuará a funcionar até a atualização de julho. **Quiosque (obsoleto)** é substituído pelo novo tipo de perfil **Quiosque** (**Criar perfil** > **Windows 10** > **Quiosque (versão prévia)** ), que conterá as configurações de quiosques no Windows 10 RS4 e versões posteriores.

Aplica-se ao Windows 10 e posteriores.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>O gráfico de perfil do dispositivo do usuário está de volta <!-- 2160133 -->
Durante o aprimoramento das contagens numéricas exibidas no gráfico de perfil do dispositivo (**Configuração do dispositivo** > **Perfis** > selecione um perfil existente > **Visão geral** ), o gráfico de usuário gráfico foi temporariamente removido.

Com essa atualização, o gráfico de usuário está de volta, e é exibido no Portal do Azure.

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118---"></a>Suporte para registro do Windows Autopilot sem autenticação de usuário <!-- 1165118 -->
O Intune agora é compatível com registro do Windows Autopilot sem autenticação de usuário. Essa é uma nova opção no perfil de implantação do Windows Autopilot, "Modo de Implantação do Autopilot" definido como "Autoimplantando".  O dispositivo precisa executar o Windows 10 Insider Preview Build 17672 ou posterior e ter um chip do TPM 2.0 para concluir com êxito esse tipo de registro. Como nenhuma autenticação de usuário é necessária, você só deve atribuir essa opção a dispositivos sobre os quais você tenha controle físico.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nova configuração de idioma/região ao configurar o OOBE para Autopilot <!-- 1821766 -->
Uma nova definição de configuração está disponível para definição do idioma e da região para perfis do Autopilot durante a Experiência de Configuração Inicial. Para ver a nova configuração, escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de implantação** > **Criar perfil** > **Modo de implantação** = **Autoimplantação** > **Padrões configurados**.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nova configuração para o teclado do dispositivo <!-- 1821768 -->
Uma nova configuração estará disponível para definição do teclado para perfis do Autopilot durante a configuração inicial pelo usuário. Para ver a nova configuração, escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de implantação** > **Criar perfil** > **Modo de implantação** = **Autoimplantação** > **Padrões configurados**.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Perfis do AutoPilot passando para direcionamento de grupo <!-- 1877935 -->
Os perfis de implantação do AutoPilot podem ser atribuídos a grupos do Azure AD que contém dispositivos do AutoPilot.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="set-compliance-by-device-location----851881----"></a>Definir a conformidade de acordo com a localização do dispositivo <!-- 851881 ! -->
Em algumas situações, convém restringir o acesso aos recursos corporativos a uma localização específica, definida por uma conexão de rede. Agora você pode criar uma política de conformidade (**Conformidade do dispositivo** > **Locais**) com base no endereço IP do dispositivo. Se o dispositivo sair do intervalo de IP, ele não poderá mais acessar os recursos corporativos.

Aplica-se a: dispositivos Android 6.0 e superiores, com o aplicativo Portal da Empresa atualizado

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Impedir aplicativos e experiências de consumidor em dispositivos Windows 10 Enterprise RS4 AutoPilot<!-- 1621980 -->
Você poderá impedir a instalação de aplicativos e experiências de consumidor nos seus dispositivos Windows 10 Enterprise RS4 AutoPilot. Para ver esse recurso, acesse **Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Plataforma** = **Windows 10 ou posterior** > **Tipo de perfil** = **Restrições do dispositivo** > **Configurar** > **Windows Spotlight** > **Recursos do consumidor**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948---"></a>Desinstale a versão mais recente das atualizações de software do Windows 10 <!-- 1732948 -->
Caso você descubra um problema de quebra em seus computadores Windows 10, poderá optar por desinstalar a atualização (reverter) a atualização de recurso mais recente ou a atualização de qualidade mais recente. Desinstalar uma atualização de recurso ou qualidade só está disponível para o canal de serviço que o dispositivo se encontra. Ao desinstalar, uma política é disparada para restaurar a atualização anterior em seus computadores Windows 10. Para atualizações de recursos, especificamente, você pode limitar o tempo entre 2 e 60 dias em que uma desinstalação da versão mais recente pode ser aplicada. Para definir opções de desinstalação de atualização de software, selecione **Atualizações de software** na folha do **Microsoft Intune** no portal do Azure. Em seguida, selecione **Anéis de Atualização do Windows 10** na folha **Atualizações de software**. Em seguida, você pode escolher a opção **Desinstalar** na seção **Visão Geral**.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>Pesquisar IMEI e número de série de todos os dispositivos <!-- 1793685 -->
Agora você pode pesquisar IMEI e números de série na folha Todos os dispositivos (email, UPN, nome do dispositivo e nome de gerenciamento ainda estão disponíveis). No Intune, escolha **Dispositivos** > **Todos os dispositivos** > Insira sua pesquisa na caixa de pesquisa.

#### <a name="management-name-field-will-be-editable----1875989---"></a>O campo Nome de gerenciamento poderá ser editado <!-- 1875989 -->
Você agora pode editar o campo de nome de gerenciamento na folha **Propriedades** de um dispositivo. Para editar esse campo, escolha **Dispositivos** > **Todos os dispositivos** > escolha o dispositivo > **Propriedades**. Use o campo de nome de gerenciamento para identificar exclusivamente um dispositivo.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Novo filtro Todos os dispositivos: categoria de dispositivo <!-- 1878520 -->
Agora você pode filtrar a lista **Todos os dispositivos** por categoria de dispositivo. Para fazer isso, escolha **Dispositivos** > **Todos os dispositivos** > **Filtrar** > **Categoria de dispositivo**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Use o TeamViewer para compartilhar a tela de dispositivos iOS e MacOS <!-- 1985547 -->
Os administradores agora podem se conectar ao [TeamViewer](../remote-actions/teamviewer-support.md) e iniciar uma sessão de compartilhamento de tela com dispositivos iOS e macOS. Usuários do iPhone, iPad e macOS podem compartilhar suas telas ao vivo com qualquer desktop ou dispositivo móvel. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Suporte ao Multiple Exchange Connector <!-- 2070451 -->
Você não fica mais limitado a um Microsoft Intune Exchange Connector por locatário. O Intune agora é compatível com vários Conectores do Exchange para que você possa configurar o Acesso Condicional do Intune com diversas organizações locais do Exchange.

Com um conector do Exchange local do Intune, você pode gerenciar o acesso ao dispositivo para suas caixas de entrada do Exchange local com base em se um dispositivo é registrado no Intune e está em conformidade com as políticas de conformidade de dispositivo do Intune. Para configurar um conector, baixe o conector do Exchange local do Portal do Azure no Intune e instale-o em um servidor na sua organização do Exchange. No painel do Microsoft Intune, escolha **Acesso local** e, em **Configuração**, selecione **Conector do Exchange ActiveSync**. Baixe o conector local do Exchange local e instale-o em um servidor na sua organização do Exchange. Agora que não há mais o limite de um conector do Exchange por locatário, se você tiver organizações do Exchange adicionais, siga este mesmo processo para baixar e instalar um conector para cada organização do Exchange adicional.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Detalhes do novo hardware do dispositivo: CCID <!-- 2156657 -->
As informações de CCID (Dispositivo de Interface de Cartão de Chip) agora estão incluídas para cada dispositivo. Para vê-las, selecione **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Hardware**> marque **Detalhes da rede**>

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Atribua todos os usuários e dispositivos como grupos de escopo <!-- 2196803 -->
Você agora pode atribuir todos os dispositivos e todos os usuários e todos os dispositivos aos grupos no escopo. Para fazer isso, escolha **Funções do Intune** > **Todas as funções** > **Gerenciador de política e perfil** > **Atribuições** > escolher uma atribuição > **Escopo (grupos)** .

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806---"></a>Informações de UDID agora estão incluídas para dispositivos iOS e macOS <!-- 2219806 -->
Para ver o UDID (Identificador Exclusivo de Dispositivo) para dispositivos iOS e macOS, acesse **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Hardware**. O UDID só está disponível para dispositivos corporativos (conforme definido em **Dispositivos** > **Todos os dispositivos** > escolher um dispositivo > **Propriedades** > **Propriedade do dispositivo**).

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Solução aprimorada de problemas de instalação do aplicativo <!-- 928990 -->
Em dispositivos gerenciados pelo MDM do Microsoft Intune, as instalações de aplicativos às vezes podem falhar. Quando a instalação desses aplicativos falha, pode ser um desafio entender o motivo da falha ou solucionar o problema. Estamos enviando uma Visualização Pública dos nossos recursos de Solução de Problemas de Aplicativo. Você observará um novo nó em cada dispositivo individual com o nome **Aplicativos Gerenciados**. Ele lista os aplicativos que foram entregues por meio do MDM do Intune. Dentro do nó, você verá uma lista dos estados de instalação do aplicativo. Se você selecionar um aplicativo individual, verá o modo de exibição de solução de problemas desse aplicativo específico. Na exibição de solução de problemas, você verá o ciclo de vida completo do aplicativo, por exemplo, quando o aplicativo foi criado, modificado, direcionado e entregue a um dispositivo. Além disso, se a instalação do aplicativo não for bem-sucedida, você receberá o código de erro e uma mensagem útil sobre a causa do erro. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Políticas de proteção de aplicativo do Intune e Microsoft Edge <!-- 1818968 -->
O navegador Microsoft Edge para dispositivos móveis (iOS e Android) agora é compatível com as políticas de proteção de aplicativo do Microsoft Intune. Os usuários de dispositivos iOS e Android que entrarem com suas contas corporativas do Azure AD no aplicativo Microsoft Edge estarão protegidos pelo Intune. Em dispositivos iOS, a política **Exigir navegador gerenciado para conteúdo da Web** permitirá aos usuários abrir links no Microsoft Edge quando for gerenciado.

<!-- ########################## -->
## <a name="may-2018"></a>Maio de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Configurar políticas de proteção do aplicativo <!-- 2144597 Part 2 -->

No portal do Azure, em vez de acessar a folha do serviço de Proteção de Aplicativo do Intune, vá apenas até o Intune. Agora, há apenas uma localização para políticas de proteção de aplicativo no Intune. Observe que todas as suas políticas de proteção de aplicativo estão na folha **Aplicativo móvel** no Intune em **Políticas de proteção de aplicativo**. Essa integração ajuda a simplificar a administração do gerenciamento de nuvem. Lembre-se de que todas as políticas de proteção do aplicativo já estão no Intune e você pode modificar qualquer uma das políticas configuradas anteriormente. As políticas de APP (Proteção de Política de Aplicativo) e de CA (Acesso Condicional) do Intune estão agora em **Acesso Condicional**, que pode ser encontrado na seção **Gerenciar** na folha **Microsoft Intune** ou na seção **Segurança** na folha **Azure Active Directory**. Para saber mais sobre como modificar políticas de Acesso Condicional, confira [Acesso Condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Para obter mais informações, consulte [Quais são as políticas de proteção do aplicativo?](../apps/app-protection-policy.md)

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Requer a instalação de perfis de políticas, aplicativos, certificado e rede <!-- 1553555 -->
Os administradores podem impedir que usuários finais acessem a área de trabalho do Windows 10 RS4 até que o Intune instale políticas, aplicativos e perfis de certificado e de rede durante o provisionamento de dispositivos AutoPilot. Para obter mais informações, consulte [Configurar uma página de status de registro](../enrollment/windows-enrollment-status.md).

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Suporte ao registro no Samsung Knox Mobile <!--1112863-->
Ao usar o Intune com a inscrição no Samsung Knox Mobile (KME), você pode inscrever vários dispositivos Android corporativos. Os usuários em redes de celular ou Wi-Fi podem inscrever seus dispositivos com apenas alguns toques ao o ligarem pela primeira vez. Ao usar o Aplicativo de Implantação do Knox, os dispositivos podem ser inscritos usando Bluetooth ou NFC. Para saber mais, confira [Inscrever automaticamente os dispositivos Android usando o Knox Mobile Enrollment da Samsung](../enrollment/android-samsung-knox-mobile-enroll.md).

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas 

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Solicitar ajuda no aplicativo Portal da Empresa para Windows 10 <!-- 1874137 -->
Agora, o Portal da Empresa para Windows 10 envia logs de aplicativo diretamente à Microsoft quando o usuário inicia o fluxo de trabalho para obter ajuda com um problema. Isso facilitará a solução de problemas enviados para a Microsoft.

<!-- ########################## -->
## <a name="april-2018"></a>Abril de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Suporte de senha para o PIN de MAM no Android<!-- 1438086 -->

Os administradores do Intune podem definir um requisito de inicialização do aplicativo para impor uma senha, em vez de um PIN numérico de MAM. Se configurado, o usuário precisa definir e usar uma senha quando solicitado antes de obter acesso a aplicativos habilitados para MAM. Uma senha é definida como um PIN numérico com pelo menos um caractere especial ou letras maiúsculas/minúsculas. O Intune é compatível com senha de maneira semelhante ao PIN numérico existente, sendo capaz de definir um tamanho mínimo, permitindo caracteres e sequências repetidos por meio do console do administrador. Este recurso requer a versão mais recente do Portal da Empresa no Android. Esse recurso já está disponível para iOS.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Suporte para aplicativo de LOB (linha de negócios) do macOS <!-- 1473977 -->
O Microsoft Intune oferecerá a capacidade de instalar aplicativos de LOB macOS do Portal do Azure. Você poderá adicionar um aplicativo de LOB macOS ao Intune depois de ele ter sido previamente processado pela ferramenta disponível no GitHub. No portal do Azure, escolha **Aplicativos clientes** na folha **Intune**. Na folha **Aplicativos clientes**, escolha **Aplicativos** > **Adicionar**. Na folha **Adicionar Aplicativo**, selecione **Aplicativo de linha de negócios**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment----1813073---"></a>Grupos Todos os Usuários e Todos os Dispositivos internos para atribuição de aplicativo de perfil de trabalho do Android Enterprise <!-- 1813073 -->
É possível aproveitar os grupos internos **Todos os Usuários** e **Todos os Dispositivos** para a atribuição de aplicativos de perfil de trabalho do Android Enterprise. Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](../apps/apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>O Intune reinstalará os aplicativos necessários que são desinstalados pelos usuários <!-- 1947010 -->
Se um usuário final desinstalar um aplicativo obrigatório, o Intune reinstalará automaticamente o aplicativo em até 24 horas, em vez de aguardar o ciclo de reavaliação de 7 dias.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Atualizar o local em que você configura as políticas de proteção do aplicativo <!-- 2144597 -->

No portal do Azure dentro do serviço do Microsoft Intune, você será temporariamente direcionado da folha de serviço da **Proteção de Aplicativo do Intune** para a folha **Aplicativo Móvel**. Observe que todas as suas políticas de proteção de aplicativo já estão na folha de **Aplicativo Móvel** do Intune, em configuração do aplicativo. Em vez de acessar a Proteção de Aplicativo do Intune, basta acessar o Intune. Em abril de 2018, interromperemos o redirecionamento e removeremos totalmente a folha de serviço da **Proteção de Aplicativo do Intune**, para que haja apenas um local para as políticas de proteção de aplicativos no Intune. 

**Como isso me afeta?**
Essa alteração afeta os clientes do Intune autônomo e os clientes do híbrido (Intune com o Configuration Manager). Essa integração ajudará a simplificar a administração do gerenciamento da nuvem.

**O que preciso fazer para me preparar para essa alteração?**
Marque o **Intune** como um favorito, em vez da folha de serviço da **Proteção de Aplicativo do Intune** e familiarize-se com o fluxo de trabalho da política de proteção de Aplicativo na folha de aplicativo **Móvel** no Intune. Você será redirecionado por um breve período e, em seguida, removeremos a folha **Proteção de Aplicativo**. Lembre-se de que todas as políticas de proteção de aplicativo já estão no Intune e você pode modificar qualquer uma das suas políticas de Acesso Condicional. Para saber mais sobre como modificar políticas de Acesso Condicional, confira [Acesso Condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Para obter mais informações, consulte [Quais são as políticas de proteção do aplicativo?](../apps/app-protection-policy.md) 

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153---"></a>A lista de status e gráfico de perfil do dispositivo mostra todos os dispositivos em um grupo <!-- 1449153 -->
Quando você configura um perfil de dispositivo (**Configuração do dispositivo** > **Perfis**), escolha o perfil do dispositivo, como iOS. Você pode atribuir esse perfil a um grupo que inclua dispositivos iOS e dispositivos não iOS. A contagem de gráfico mostra que o perfil é aplicado a dispositivos iOS *e* não iOS (**Configuração do dispositivo** > **Perfis** > selecione um perfil existente > **Visão geral**). Quando você seleciona o gráfico na guia **Visão geral**, o **Status do dispositivo** lista todos os dispositivos no grupo, em vez de apenas os dispositivos iOS. 

Com essa atualização, o gráfico (**Configuração do dispositivo** > **Perfis** > Selecione um perfil existente > **Visão geral**) mostrará apenas a contagem para o perfil de dispositivo específico. Por exemplo, se o perfil do dispositivo de configuração se aplicar a dispositivos iOS, o gráfico listará somente a contagem de dispositivos iOS. Selecionar o gráfico e abrir o **Status do dispositivo** lista apenas os dispositivos iOS.

Enquanto essa atualização está sendo feita, o gráfico do usuário é removido temporariamente. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>VPN Always On para Windows 10 <!--1333666 -->

No momento, [Always On](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) pode ser usado em dispositivos Windows 10 usando um perfil de VPN (rede virtual privada) personalizado criado usando o OMA-URI.

Com essa atualização, os administradores podem habilitar o Always On para perfis de VPN do Windows 10 diretamente no Intune no Portal do Azure. Perfis de VPN Always On conectam-se automaticamente quando:

- Os usuários fazem logon em seus dispositivos
- A rede no dispositivo muda
- A tela do dispositivo é ativada novamente depois de ser desligada

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Novas configurações de impressora para perfis de educação <!-- 1308900 -->

Para perfis de educação, novas configurações estão disponíveis na categoria **Impressoras**: **Impressoras**, **Impressora padrão**, **Adicionar novas impressoras**.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile---1098984---"></a>Mostrar as informações sobre a chamada no perfil pessoal – Perfil de trabalho do Android Enterprise <!--1098984 -->
Ao usar um perfil pessoal em um dispositivo, os usuários finais poderão não ver os detalhes das informações sobre a chamada de um contato de trabalho. 

Com essa atualização, há uma nova configuração em **Android Enterprise** > **Restrições de dispositivo** > **Configurações do perfil de trabalho**:
- Exibir a identificação do chamador do contato de trabalho no perfil pessoal

Quando esta opção está habilitada (não configurada), os detalhes de contato comercial do chamador são exibidos no perfil pessoal. Quando bloqueada, o número de contato comercial do chamador não é exibido no perfil pessoal. 

Aplicável a: dispositivos Android de perfil de trabalho no sistema operacional Android v6.0 e mais recentes

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Novas configurações do Windows Defender Credential Guard adicionadas às configurações do Endpoint Protection <!--1102252 --><!--from 1802 and 1804-->

Com essa atualização, o [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Configuração do dispositivo** > **Perfis** > **Proteção do ponto de extremidade**) inclui as seguintes configurações: 

- **Windows Defender Credential Guard**: ativa a proteção de credenciais com segurança baseada em virtualização. Habilitar este recurso ajuda a proteger as credenciais na próxima reinicialização quando as opções **Nível de segurança de plataforma com a inicialização segura** e **Segurança baseada em virtualização** estiverem habilitadas. As opções incluem:
  - **Desabilitada**: se o Credential Guard tiver sido ativado anteriormente com a opção **Habilitado sem bloqueio**, então, ele desativará o Credential Guard remotamente.

  - **Habilitada com o bloqueio UEFI**: garante que o Credential Guard não possa ser desabilitado com a chave do Registro ou usando a Política de Grupo. Para desabilitar a Proteção de Credenciais depois de usar essa configuração, você deve definir a Política de Grupo como "Desabilitada". Em seguida, remova a funcionalidade de segurança de cada computador, com um usuário fisicamente presente. Essas etapas limpam a configuração mantida no UEFI. Enquanto a configuração da UEFI for mantida, o Credential Guard estará habilitado.

  - **Habilitada sem bloqueio**: permite que o Credential Guard seja desabilitado remotamente usando a Política de Grupo. Os dispositivos que usam essa configuração devem estar executando, pelo menos, o Windows 10 (versão 1511).

As seguintes tecnologias dependentes são habilitadas automaticamente ao configurar o Credential Guard: 

- **Habilitar a VBS (segurança baseada em virtualização)** : ativa a VBS (segurança baseada em virtualização) na próxima reinicialização. A segurança baseada em virtualização usa o Hipervisor do Windows para fornecer suporte aos serviços de segurança e exige a Inicialização Segura.
- **Inicialização segura com DMS (Acesso direto à memória)** : ativa a VBS com inicialização segura e acesso direto à memória. A proteção de DMA exige suporte de hardware e é habilitada somente em dispositivos configurados corretamente. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Use um nome de entidade personalizado no certificado SCEP <!-- 2064190 -->
Você pode usar o nome comum **OnPremisesSamAccountName** em uma entidade personalizada em um perfil de certificado SCEP. Por exemplo, você pode usar `CN={OnPremisesSamAccountName})`.

#### <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles----1098977---"></a>Bloquear câmera e capturas de tela nos perfis de trabalho do Android Enterprise <!-- 1098977 -->
Duas novas propriedades estão disponíveis para bloqueio quando você configurar as restrições de dispositivo para dispositivos Android: 
- Câmera: bloqueia o acesso a todas as câmeras no dispositivo
- Captura de tela: bloqueia a captura de tela e também impede que o conteúdo seja mostrado em dispositivos de exibição que não tenham uma saída de vídeo segura

Se aplica a perfis de trabalho do Android Enterprise.

#### <a name="use-cisco-anyconnect-client-for-ios----1333708---"></a>Usar o cliente do Cisco AnyConnect para iOS <!-- 1333708 -->

Quando você cria um novo perfil de VPN para iOS, agora há duas opções: **Cisco AnyConnect** e **Cisco Legacy AnyConnect**. Os perfis do Cisco AnyConnect 4.0.7x são compatíveis com o 4.0.7x e versões mais recentes. Os perfis existentes de VPN do Cisco AnyConnect do iOS são rotulados como **Cisco Legacy AnyConnect** e continuarão a funcionar com o Cisco AnyConnect 4.0.5x e versões anteriores, como fazem atualmente.

> [!NOTE]
> Essa alteração se aplica apenas ao iOS. Continuará existindo apenas uma opção do Cisco AnyConnect para os perfis de trabalho do Android Enterprise, Android e plataformas do macOS.


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Novas etapas de registro para usuários em dispositivos com macOS High Sierra 10.13.2+ <!--1734567 -->
O macOS High Sierra 10.13.2 introduziu o conceito de registro do MDM "Aprovado pelo Usuário". As inscrições aprovadas permitem que o Intune gerencie algumas configurações sensíveis de segurança. Para obter mais informações, consulte a documentação de suporte da Apple aqui: https://support.apple.com/HT208019.

Dispositivos registrados usando o Portal da Empresa macOS são considerados "Não Aprovados pelo Usuário", a menos que o usuário final abra as Preferências do Sistema e dê manualmente sua aprovação. Para esse fim, o Portal da Empresa macOS agora direciona os usuários em macOS 10.13.2 e acima e aprovar manualmente o registro no final do processo de registro. O console do administrador do Intune relatará se um dispositivo registrado for aprovado pelo usuário.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Os dispositivos macOS registrados em Jamf já podem se registrar no Intune <!-- 2370684 -->
As versões 1.3 e 1.4 do portal da empresa do macOS não registraram com êxito os dispositivos Jamf no Intune. A versão 1.4.2 do portal do macOS corrige esse problema.

#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Experiência de ajuda atualizada no aplicativo Portal da Empresa para Android <!-- 1631531 -->
Nós atualizamos a experiência da ajuda no aplicativo Portal da Empresa para Android com base nas práticas recomendadas para a plataforma Android. Agora, quando os usuários encontram um problema no aplicativo, eles poderão tocar em **Menu** > **Ajuda** e:
- Faça o upload dos de diagnóstico para a Microsoft.
- Envie um email que descreva a ID do problema e do incidente para um profissional de suporte da empresa.  

Para conferir a experiência de ajuda atualizada, acesse [Enviar logs usando o email](/intune-user-help/send-logs-to-your-it-admin-by-email-android) e [Enviar erros à Microsoft](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Novo gráfico de tendência de falha de registro e tabela de motivos de falhas <!-- 1471783 -->
Na página Visão Geral do Registro, você poderá exibir a tendência de falhas de registro e as cinco principais causas de falhas. Ao clicar no gráfico ou na tabela, você poderá fazer uma busca detalhada nos detalhes para encontrar recomendações de solução de problemas e sugestões de correção.


### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----1629303---"></a>A ATP (Proteção Avançada contra Ameaças) e o Intune estão totalmente integrados <!-- 1629303 -->

[ATP (Proteção Avançada contra Ameaças)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) mostra o nível de risco de dispositivos Windows 10. Na Central de Segurança do Windows Defender (portal da ATP), você pode criar uma conexão ao Microsoft Intune. Depois de criada, uma política de conformidade do Intune é usada para determinar um nível de ameaça aceitável. Se o nível de ameaça for excedido, uma política de Acesso Condicional do AD (Azure Active Directory) poderá bloquear o acesso a aplicativos diferentes na organização.

Esse recurso permite que a ATP examine arquivos, detecte ameaças e relate qualquer risco em seus dispositivos Windows 10.

Confira [Habilitar a ATP com Acesso Condicional no Intune](../protect/advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Suporte para dispositivos sem usuário <!-- 1637553 -->
O Intune é compatível com a capacidade de avaliar a conformidade em um dispositivo sem usuário, como o Microsoft Surface Hub. A política de conformidade pode ter como destino dispositivos específicos. Assim, a conformidade (e a não conformidade) pode ser determinada para dispositivos que não tenham um usuário associado.

#### <a name="delete-autopilot-devices----1713650---"></a>Excluir dispositivos Autopilot <!-- 1713650 -->
Os administradores do Intune podem [excluir dispositivos do AutoPilot](../enrollment/enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Experiência de exclusão do dispositivo aprimorada <!--1832333 -->
Você não precisa mais remover dados da empresa, nem fazer uma redefinição de fábrica do dispositivo antes de [excluir um dispositivo do Intune](../remote-actions/devices-wipe.md#delete-devices-from-the-intune-portal).

Para ver a nova experiência, entre no Intune e selecione **Dispositivos** > **Todos os Dispositivos** > nome do dispositivo > **Excluir**.

Se você ainda quiser apagar/desativar a confirmação, poderá usar a rota de ciclo de vida do dispositivo padrão emitindo **Remover dados da empresa** e **Redefinição de Fábrica** antes de **Excluir**. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Tocar sons no iOS quando no modo Perdido <!-- 1947769 -->
Quando dispositivos iOS supervisionados estiverem no [modo Perdido](../remote-actions/device-lost-mode.md) do MDM (gerenciamento de dispositivo móvel), você poderá [tocar um som](../remote-actions/device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Dispositivos** > **Todos os dispositivos** > Selecione um dispositivo iOS > **Visão geral** > **Mais**). O som continua sendo reproduzido até o dispositivo ser removido do Modo perdido ou um usuário desabilitar o som no dispositivo. Aplica-se a dispositivos iOS 9.3 e mais recentes.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Bloquear ou permitir os resultados da Web em pesquisas feitas em um dispositivo do Intune <!--1972804-->

Os administradores agora podem bloquear os resultados da Web de pesquisas feitas em um dispositivo.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Mensagens de erro aprimoradas para falha no upload do Apple MDM Push Certificate <!-- 2172331 -->

A mensagem de erro explica que a mesma ID da Apple deve ser usada durante a renovação de um certificado existente do MDM.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Testar o Portal da Empresa para macOS em máquinas virtuais <!-- 2216679 -->

Publicamos as orientações para ajudar os administradores de TI a testar o aplicativo do Portal da Empresa para macOS em máquinas virtuais no Parallels Desktop e no VMware Fusion. Saiba mais em [Registrar máquinas macOS virtuais para teste](../enrollment/macos-enroll.md#enroll-virtual-macos-machines-for-testing).

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Atualização de experiência do usuário para o aplicativo Portal da Empresa para iOS <!--1412866 -->
Lançamos uma atualização principal da experiência do usuário para o aplicativo Portal da Empresa para iOS. A atualização apresenta um novo design visual completo que inclui uma aparência modernizada. Mantivemos a funcionalidade do aplicativo, mas aumentamos sua usabilidade e acessibilidade.  

Você também verá:
- Suporte para iPhone X.
- Mais rapidez na inicialização do aplicativo e no carregamento de respostas para economizar tempo para os usuários.
- Barras de progresso adicionais para fornecer aos usuários as informações de status mais atualizadas.
- Melhorias às maneiras como os usuários carregam logs, portanto, se algo der errado, será mais fácil relatar.  

Para ver a aparência atualizada, vá para [Novidades da interface do usuário do aplicativo](../whats-new-app-ui.md).

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Proteger dados do Exchange no Local usando a APP do Intune e o AC <!-- 1056954 -->
Agora você pode usar a APP (Proteção de Política do Aplicativo) do Intune e o AC (Acesso Condicional) para proteger o acesso a dados do Exchange no Local com o Outlook Mobile. Para adicionar ou modificar uma política de proteção de aplicativo no portal do Azure, selecione **Microsoft Intune** > **Aplicativos clientes** > **Políticas de proteção de aplicativo**. Antes de usar esse recurso, verifique se você atende aos [requisitos do Outlook para iOS e Android](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx).


### <a name="user-interface"></a>Interface do usuário

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Blocos de dispositivo aprimorados no Portal da Empresa do Windows 10 <!--2213364 -->

Os blocos foram atualizados para serem mais acessíveis aos usuários com visão subnormal e para apresentarem um desempenho melhorado nas ferramentas de leitura de tela.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Enviar relatórios de diagnóstico no aplicativo Portal da Empresa para macOS <!-- 2216677 -->
O aplicativo Portal da Empresa para dispositivos macOS foi atualizado para melhorar o modo como os usuários relatam erros relacionados ao Intune. No aplicativo Portal da Empresa, seus funcionários podem:

- Carrega relatórios de diagnóstico diretamente para a equipe de desenvolvedores Microsoft.
- Envie por email uma ID de incidente à equipe de suporte de TI da sua empresa.

Para obter mais informações, consulte [Enviar erros para o macOS](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010---"></a>O Intune se adapta ao Fluent Design System no aplicativo Portal da empresa para o Windows 10 <!-- 1195010 -->
O aplicativo do Portal da Empresa do Intune para Windows 10 foi atualizado com a [exibição de navegação do Fluent Design System](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics). No lado do aplicativo, você verá uma lista estática e vertical de todas as páginas de nível superior. Clique em qualquer link para exibir e alternar rapidamente entre as páginas. Esta é a primeira de várias atualizações que você verá como parte de nosso esforço contínuo de criar uma experiência mais adaptável, intuitiva e familiar no Intune. Para ver a aparência atualizada, vá para [Novidades da interface do usuário do aplicativo](../whats-new-app-ui.md).

<!-- ########################## -->
## <a name="march-2018"></a>Março de 2018

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Alertas para a expiração de aplicativos de LOB (linha de negócios) do iOS para Microsoft Intune <!-- 748789 -->

No Portal do Azure, o Intune o alertará sobre aplicativos de linha de negócios iOS que estão prestes a expirar. Após carregar uma nova versão do aplicativo de linha de negócios iOS, o Intune remove a notificação de expiração da lista de aplicativos. Esta notificação de expiração somente ficará ativa para aplicativos de linha de negócios iOS recém-carregados. Um aviso aparecerá 30 dias antes da expiração do perfil de provisionamento de aplicativo do iOS LOB. Quando expirar, o alerta mudará para Expirado.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Personalize os temas do Portal da Empresa com códigos hexadecimais <!--1049561 -->

Você pode personalizar a cor do tema nos aplicativos do Portal da Empresa usando códigos hexadecimais. Ao inserir o código hexadecimal, o Intune determina a cor do texto que oferece o maior nível de contraste entre a cor do texto e a cor da tela de fundo. É possível visualizar a cor do texto e o logotipo da empresa em relação à cor em **Aplicativos clientes** > **Portal da Empresa**.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos para Android Enterprise <!-- 1813081 -->

Android Enterprise (anteriormente conhecido como Android for Work) é compatível com a inclusão e a exclusão de grupos, mas não com grupos internos de **Todos os Usuários** e **Todos os Dispositivos** pré-criados. Para obter mais informações, consulte [Incluir e excluir atribuições de aplicativo no Microsoft Intune](../apps/apps-inc-exl-assignments.md).


### <a name="device-management"></a>Gerenciamento de dispositivos

### <a name="export-all-devices-into-csv-files-in-ie-microsoft-edge-or-chrome----2258071---"></a>Exportar todos os dispositivos para arquivos CSV no IE, no Microsoft Edge ou no Chrome <!-- 2258071 -->
Em **Dispositivos** > **Todos os Dispositivos**, você pode **Exportar** os dispositivos para uma lista formatada em CSV. Os usuários do IE (Internet Explorer) com >10.000 dispositivos podem exportar com êxito seus dispositivos para vários arquivos. Cada arquivo tem até 10.000 dispositivos.

Os usuários do Microsoft Edge e do Chrome com > 30 mil dispositivos podem exportar com êxito seus dispositivos para vários arquivos. Cada arquivo tem até 30.000 dispositivos.

[Gerenciar dispositivos](../remote-actions/device-management.md) fornece mais detalhes sobre o que você pode fazer com os dispositivos que gerencia.

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Novos aprimoramentos de segurança no serviço do Intune  <!-- 1637539 -->   

Apresentamos uma alternância do Intune no Azure que os clientes autônomos do Intune podem usar para tratar os dispositivos sem qualquer política atribuída como **Em conformidade** (recurso de segurança desligado) ou tratar esses dispositivos como **Não em conformidade** (recurso de segurança ligado). Isso garantirá acesso aos recursos somente após a avaliação de conformidade do dispositivo.

Esse recurso afeta você de maneira diferente dependendo se você já tem políticas de conformidade atribuídas ou não.

- Se você for uma conta nova ou existente e não tiver nenhuma política de conformidade atribuída aos seus dispositivos, a alternância será definida automaticamente como **Em conformidade**. O recurso está desligado como uma configuração padrão no console. Não há nenhum impacto ao usuário final.
- Se você for uma conta existente e tiver qualquer dispositivo com uma política de conformidade atribuída, a alternância será definida automaticamente como **Não em conformidade**. O recurso está ligado como uma configuração padrão conforme a atualização de março é implantada.

Se você usar políticas de conformidade com CA (Acesso Condicional) e o recurso estiver ativado, os dispositivos que não tiverem pelo menos uma política de conformidade atribuída agora serão bloqueados pelo CA. Os usuários finais associados a esses dispositivos, que anteriormente tinham permissão de acesso ao email, perderão o acesso, a menos que você atribua pelo menos uma política de conformidade a todos os dispositivos.   

Observe que, embora o status de alternância padrão seja exibido na interface do usuário imediatamente com as atualizações do serviço do Intune feitas em março, esse status de alternância não é imposto imediatamente. Alterações feitas à alternância não terá impacto sobre a conformidade do dispositivo até habilitarmos sua conta para ter uma alternância operando. Você será informado por meio do Centro de Mensagens quando terminamos de habilitar sua conta. Isso pode levar alguns dias depois que o serviço do Intune for atualizado para março.

**Informações adicionais**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Detecção avançada de jailbreak <!-- 846515 -->

A detecção de jailbreak avançada é uma nova configuração de conformidade que melhora a maneira como o Intune avalia os dispositivos desbloqueados por jailbreak. A configuração faz com que o dispositivo faça check-in no Intune com mais frequência, o que utiliza os serviços de localização do dispositivo e afeta o uso da bateria.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Redefina senhas de dispositivos Android O <!-- 1238299 -->
Você poderá redefinir senhas para dispositivos com Android 8.0 registrados com perfis de Trabalho. Quando você envia uma solicitação de "Redefinir senha" a um dispositivo Android 8.0, ele define uma nova senha de desbloqueio de dispositivo ou um desafio de perfil gerenciado para o usuário atual. A senha ou o desafio é enviado e entra em vigor imediatamente.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Direcionamento de políticas de conformidade para dispositivos em grupos de dispositivo <!--1307012 -->

Você pode direcionar políticas de conformidade para usuários em grupos de usuários. Com essa atualização, você pode direcionar políticas de conformidade para dispositivos em grupos de dispositivo. Dispositivos de destino como parte de grupos de dispositivos não receberão as ações de conformidade.

#### <a name="new-management-name-column----1333586---"></a>Coluna Novo nome de gerenciamento <!-- 1333586 -->
 Uma nova coluna chamada **Nome de gerenciamento** está disponível na folha de dispositivos. Este é um nome não editável gerado automaticamente atribuído por dispositivo, com base na seguinte fórmula:
- Nome padrão para todos os dispositivos: <username><em><devicetype></em><enrollmenttimestamp>
- Para dispositivos adicionados em massa: <PackageId/ProfileId><em><DeviceType></em><EnrollmentTime>

Esta é uma coluna opcional na folha de dispositivos. Ele não está disponível por padrão e você poderá acessá-lo apenas por meio do seletor de colunas. O nome do dispositivo não é afetado por essa nova coluna.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>Os dispositivos iOS solicitam um PIN a cada 15 minutos <!--1550837 -->
Depois que uma política de conformidade ou de configuração for aplicada a um dispositivo iOS, os usuários serão solicitados a definir um PIN a cada 15 minutos. Os usuários são notificados continuamente até que um PIN seja definido.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Agendar suas atualizações automáticas <!--1805514 -->
Com o Intune, você controla como instalar atualizações automáticas usando as [configurações do Grupo de Atualização do Windows](../protect/windows-update-for-business-configure.md). Com essa atualização, você pode agendar atualizações recorrentes, incluindo semana, dia e hora.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>Use o nome totalmente diferenciado como assunto para o certificado SCEP <!--2221763 -->
Quando você cria um perfil de certificado SCEP, você inserir o Nome do assunto. Com essa atualização, você pode usar o nome totalmente diferenciado como a entidade. Para **Nome do assunto**, selecione **Personalizado** e, em seguida, digite `CN={{OnPrem_Distinguished_Name}}`. Para usar a variável `{{OnPrem_Distinguished_Name}}`, sincronize o atributo de usuário `onpremisesdistingishedname` usando o [Azure AD (Active Directory) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) com seu Azure AD.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Habilitar compartilhamento de contatos por Bluetooth – Android for Work <!--1098983 -->
Por padrão, o Android impede que contatos no perfil de trabalho sejam sincronizados com dispositivos Bluetooth. Como resultado, os contatos do perfil de trabalho não são exibidos nas informações sobre a chamada para dispositivos Bluetooth.

Com essa atualização, há uma nova configuração em **Android for Work** > **Restrições de dispositivo** > **Configurações do perfil de trabalho**:
- Compartilhamento de contatos por Bluetooth

O administrador do Intune pode configurar essas configurações para habilitar o compartilhamento. Isso é útil ao emparelhar um dispositivo com um dispositivo Bluetooth baseado em carro que exibe as informações sobre a chamada para uso não assistido. Quando habilitados, os contatos de perfil de trabalho são exibidos. Quando não habilitados, os contatos de perfil de trabalho não serão exibidos.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Configurar o Gatekeeper para controlar a origem do download do aplicativo macOS <!-- 1690459 -->

Você pode configurar o Gatekeeper para proteger os dispositivos de aplicativos, controlando de que local os aplicativos podem ser baixados. Você pode configurar as seguintes fontes de download: **Mac App Store**, **Mac App Store e desenvolvedores identificados** ou **De qualquer lugar**. Você também pode configurar se os usuários podem instalar um aplicativo usando CTRL + clique para substituir esses controles do Gatekeeper.

Essas configurações podem ser encontradas em **Configuração do dispositivo** -> **Criar perfil** -> **macOS** -> **Endpoint Protection**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Configurar o firewall do aplicativo Mac <!-- 1690461 -->

Você pode configurar o firewall do aplicativo Mac. Você pode usar isso para controlar as conexões por aplicativo, em vez de por porta. Isso facilita obter os benefícios da proteção de firewall e ajuda a impedir que aplicativos indesejáveis assumam o controle de portas de rede abertas para aplicativos legítimos.

Esse recurso pode ser encontrado em **Configuração do dispositivo** -> **Criar perfil** -> **macOS** -> **Endpoint Protection**.

Depois de habilitar a configuração de Firewall, você pode configurar o firewall usando duas estratégias:

- Bloquear todas as conexões de entrada

   É possível bloquear todas as conexões de entrada para os dispositivos de destino. Se você optar por fazer isso, as conexões de entrada serão bloqueadas para todos os aplicativos.

- Permitir ou bloquear aplicativos específicos

   Você pode permitir ou bloquear que aplicativos específicos recebam conexões de entrada. Você também pode habilitar o modo furtivo para impedir respostas para as solicitações de sondagem.

#### <a name="detailed-error-codes-and-messages----1376342---"></a>Códigos de erro e mensagens detalhados <!-- 1376342 -->

Em Configuração do Dispositivo, há mensagens e códigos de erro mais detalhados disponíveis para visualização. Esse relatório aprimorado mostra as configurações, o estado dessas configurações e os detalhes sobre como solucionar problemas.

##### <a name="more-information"></a>Mais informações

- Bloquear todas as conexões de entrada

   Isso impede que todos os serviços de compartilhamento (como Compartilhamento de arquivos e Compartilhamento de tela) recebam conexões de entrada. Os serviços do sistema que ainda têm permissão para receber conexões de entrada são:
  - configd – implementa DHCP e outros serviços de configuração de rede
  - mDNSResponder – implementa o Bonjour
  - racoon – implementa IPSec

    Para usar os serviços de compartilhamento, verifique se **Conexões de entrada** está definido como **Não configurado** (não **Bloqueado**).

- Modo furtivo

   Habilite esta opção para impedir que o computador responda às solicitações de sondagem. O computador ainda responde a solicitações de entrada para aplicativos autorizados. Solicitações inesperadas, como o ICMP (ping), são ignoradas.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Desabilitar verificações na reinicialização do dispositivo <!--1805490 -->
Com o Intune, você tem controle para [gerenciar atualizações de software](../protect/windows-update-for-business-configure.md). Com essa atualização, a propriedade <strong>Reiniciar verificações</strong> está disponível e habilitada por padrão. Para ignorar as verificações típicas que ocorrem quando você reinicia um dispositivo (como usuários ativos, níveis de bateria e assim por diante), selecione <strong>Ignorar</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Novos canais do Windows 10 Insider Preview disponíveis para anéis de implantação <!-- 1746293 -->
Agora você tem a opção de selecionar os seguintes canais de serviço do Windows 10 Insider Preview ao criar um anel de implantação do Windows 10:
- Build do Windows Insider &#8208; rápido
- Build do Windows Insider &#8208; lento
- Liberar build do Windows Insider 

Para obter mais informações sobre esses canais, consulte [Gerenciar builds do Insider Preview](https://insider.windows.com/for-business-organization-admin/).   
Para obter mais informações sobre como criar canais de implantação no Intune, consulte [Gerenciar atualizações de software no Intune](../protect/windows-update-for-business-configure.md).

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Novas configurações do Windows Defender Exploit Guard <!-- 1631893 -->

Seis novas configurações de <strong>Redução da Superfície de Ataque</strong> e funcionalidades expandidas de <strong>Acesso controlado a pastas: proteção de pasta</strong> agora estão disponíveis. Essas configurações podem ser encontradas em: Configuração do dispositivo\Perfis\
Criar perfil\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Redução da superfície de ataque

|Nome da configuração  |Opções de configuração  |Descrição  |
|---------|---------|---------|
|Proteção avançada contra ransomware|Habilitado, Auditoria, Não configurado|Usar proteção agressiva contra ransomware.|
|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows|Habilitado, Auditoria, Não configurado|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows (lsass.exe).|
|Criação de processo de comandos WMI e PSExec|Bloquear, Auditoria, Não configurado|Bloquear criações de processo provenientes de comandos PSExec e WMI.|
|Processos não assinados e não confiáveis executados de um USB|Bloquear, Auditoria, Não configurado|Bloquear processos não assinados e não confiáveis executados de um USB.|
|Arquivos executáveis que não atendem um critério de prevalência, idade ou lista confiável|Bloquear, Auditoria, Não configurado|Bloquear a execução de arquivos executáveis a menos que eles atendam a um critério de prevalência, de idade ou de lista confiável.|

#### <a name="controlled-folder-access"></a>Acesso controlado à pasta

|              Nome da configuração               |                                                              Opções de configuração                                                              | Descrição |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Proteção de pasta (já implementada) | Não configurado, Habilitar, Somente auditoria (já implementado)<br><br> <strong>Novo</strong><br>Bloquear modificação de disco, Auditar modificação de disco |             |

Proteger arquivos e pastas contra alterações não autorizadas por aplicativos não amigáveis.<br><br>**Habilitar**: impedir que aplicativos não confiáveis modifiquem ou excluam arquivos em pastas protegidas e gravem em setores do disco.<br><br>
**Bloquear modificação de disco somente**:<br>Impedir que aplicativos não confiáveis gravem em setores do disco. Aplicativos não confiáveis ainda podem modificar ou excluir arquivos em pastas protegidas.|

### <a name="intune-apps"></a>Aplicativos do Intune

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Os sites da Web do Azure Active Directory podem exibir o aplicativo Intune Managed Browser e dar suporte ao Logon Único para o Managed Browser (Versão Prévia Pública) <!-- 710595 -->

Usando o Azure AD (Azure Active Directory), agora você pode restringir o acesso a sites em dispositivos móveis para o aplicativo Intune Managed Browser. No Managed Browser, os dados do site permanecerão seguros e separados dos dados pessoais do usuário final. Além disso, o Managed Browser oferecerá suporte a recursos de Logon Único para sites protegidos pelo Azure AD. Entrar no Managed Browser ou usar o Managed Browser em um dispositivo com outro aplicativo gerenciado pelo Intune, permite que o Managed Browser acesse sites corporativos protegidos pelo Azure AD sem que o usuário precise inserir suas credenciais. Essa funcionalidade se aplica a sites como o Outlook Web Access (OWA) e o SharePoint Online, bem como a outros sites corporativos, como os recursos da intranet acessados por meio do Proxy do Aplicativo Azure. Para saber mais, confira [Controles de acesso no Acesso Condicional do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Aplicativo Portal da Empresa para atualizações visuais do Android <!--976944 -->

Atualizamos o aplicativo Portal da Empresa para Android para seguir as diretrizes do [Design de Material](https://material.io/) do Android. É possível ver as imagens dos novos ícones no artigo [Novidades na interface do usuário do aplicativo](../whats-new-app-ui.md).

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Registro do Portal da Empresa melhorado <!-- 1874230 eeready-->
Os usuários que registrarem um dispositivo usando o Portal da Empresa no Windows 10 build 1703 e superior agora podem concluir a primeira etapa de registro sem sair do aplicativo.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>Agora o HoloLens e o Surface Hub são exibidos nas listas de dispositivos <!--1725868 -->
Adicionamos suporte para mostrar dispositivos HoloLens e Surface Hub registrados no Intune no aplicativo Portal da Empresa para Android.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Categorias personalizadas de livros para livros eletrônicos do VPP (Volume Purchase Program) <!-- 1488911 -->
Você pode criar categorias de livros eletrônicos personalizadas e atribuir livros eletrônicos do VPP a essas categorias personalizadas. Os usuários finais poderão ver as categorias de livro eletrônico recém-criadas e os livros atribuídos às categorias. Para obter mais informações, consulte [Gerenciar aplicativos e livros comprados por volume com o Microsoft Intune](../apps/vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Mudanças de suporte para a opção de comentários do aplicativo Portal da Empresa para Windows <!-- 2070166 -->
A partir de 30 de abril de 2018, a opção **Enviar Comentários** no aplicativo Portal da Empresa para Windows funcionará apenas em dispositivos que executam a Atualização de Aniversário do Windows 10 (1607) e posterior. Não há mais suporte para a opção de enviar comentários ao usar o aplicativo Portal da Empresa para Windows com:  
- Windows 10, versão 1507  
- Windows 10, versão 1511  
- Windows Phone 8.1 

Se o seu dispositivo estiver executando no Windows 10 RS1 ou posterior, baixe a versão mais recente do aplicativo Portal da Empresa do Windows na Store. Se você estiver executando uma versão sem suporte, continue a enviar comentários por meio destes canais: 
- Aplicativo Hub de Comentários no Windows 10
- Email WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Novas configurações do Windows Defender Application Guard <!-- 1631890 -->

- **Habilitar aceleração de elementos gráficos**: os administradores poderão habilitar um processador de gráficos virtual para o Windows Defender Application Guard. Essa configuração permite que a CPU descarregue a renderização de gráficos no vGPU. Isso pode melhorar o desempenho ao trabalhar com sites com uso intenso de gráficos ou ao assistir a vídeos dentro do contêiner.

- **SaveFilestoHost**: os administradores poderão permitir que arquivos sejam passados do Microsoft Edge em execução no contêiner para o sistema de arquivos do host. Ativar essa configuração permite que os usuários baixem arquivos do Microsoft Edge no contêiner para o sistema de arquivos do host.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Políticas de proteção MAM definidas como destino com base no estado de gerenciamento <!-- 1665993 -->
Você pode ter como destino políticas de MAM com base no estado de gerenciamento do dispositivo:
- **Dispositivos Android** – você poderá ter como destino dispositivos não gerenciados, dispositivos gerenciados pelo Intune e Perfis do Android Enterprise gerenciados pelo Intune (anteriormente Android for Work).
- **Dispositivos iOS** – você poderá ter como destino dispositivos não gerenciados (somente MAM) ou dispositivos gerenciados pelo Intune.

    > [!NOTE]
    > - O suporte do iOS para essa funcionalidade será implantado em abril de 2018.

Para obter mais informações, consulte [Políticas de proteção do aplicativo de destino com base no estado de gerenciamento de dispositivo](../apps/app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Melhorias à linguagem no aplicativo Portal da Empresa para Windows <!-- 1683758 -->
Melhoramos a linguagem no Portal da Empresa para Windows 10 para ser mais amigável e específica para sua empresa. Para ver algumas amostras de imagens do que já fizemos, consulte [novidades na interface do usuário do aplicativo](../whats-new-app-ui.md).

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Novas adições aos nossos documentos sobre privacidade do usuário <!-- 1440709 -->
Como parte dos nossos esforços para dar aos usuários finais mais controle sobre seus dados e privacidade, publicamos as atualizações aos documentos que explicam como exibir e remover dados armazenados localmente usando os aplicativos do Portal da Empresa. Você pode encontrar essas atualizações no:

- **Android**: [como cancelar o registro do dispositivo Android do Intune](/intune-user-help/unenroll-your-device-from-intune-android)
- **Android, se o usuário tiver recusado os termos de uso**: [remova seu gerenciamento de dispositivo se tiver recusado os "Termos de Uso"](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android)
- **iOS**: [remova seu dispositivo iOS do Intune](/intune-user-help/unenroll-your-device-from-intune-ios)
- **Windows**: [remova seu dispositivo Windows do Intune](/intune-user-help/unenroll-your-device-from-intune-windows)

<!-- ########################## -->
## <a name="february-2018"></a>Fevereiro de 2018

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Suporte do Intune para várias contas do Programa de registro de dispositivos da Apple/Apple School Manager <!-- 747685 -->

Agora o Intune é compatível com o registro de dispositivos de até 100 contas diferentes do [DEP (Programa de registro de dispositivos) da Apple](../enrollment/device-enrollment-program-enroll-ios.md) ou do [Apple School Manager](../enrollment/apple-school-manager-set-up-ios.md). Cada token carregado pode ser gerenciado separadamente para o registro de perfis e dispositivos. Um perfil de registro diferente pode ser atribuído automaticamente por token do DEP/School Manager carregado. Se vários tokens do School Manager forem carregados, será possível compartilhar apenas um por vez com o Microsoft School Data Sync.

Após a migração, as APIs do Graph beta e os scripts publicados para gerenciamento do DEP da Apple ou do ASM no Graph deixarão de funcionar. Há novas APIs do Graph beta em desenvolvimento que serão lançadas após a migração.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Consultar as restrições de registro por usuário <!-- 1634444 eeready wnready -->
Agora, na folha **Solucionar Problemas**, é possível ver as [restrições de registro](../enrollment/enrollment-restrictions-set.md) que estão em vigor para cada usuário ao selecionar **Restrições de registro** na lista **Atribuições**.

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nova opção de autenticação de usuário para registro em massa da Apple <!-- 747625 eeready -->

> [!NOTE]
> Os novos locatários veem essa opção imediatamente. Para locatários existentes, esse recurso será distribuído durante o mês de abril. Até essa implantação estar concluída, talvez você não tenha acesso aos novos recursos.

Agora o Intune oferece a opção para autenticar dispositivos usando o aplicativo Portal da Empresa para os seguintes métodos de registro:

- Programa de Registro do Dispositivo da Apple
- Apple School Manager
- Registro do Apple Configurator

Com a opção do Portal da Empresa, a autenticação multifator do Azure Active Directory pode ser imposta sem bloquear esses métodos de registro.

Com a opção do Portal da Empresa, o Intune ignora a autenticação do usuário no Assistente de Configuração do iOS para registro de afinidade de usuário. Isso significa que o dispositivo é registrado inicialmente como um dispositivo sem usuário e, portanto, não recebe as configurações ou políticas de grupos de usuários. Ele recebe apenas as configurações e políticas de grupos de dispositivos. No entanto, o Intune instalará automaticamente o aplicativo do Portal da Empresa no dispositivo. O primeiro usuário a iniciar e entrar no aplicativo do Portal da Empresa será associado ao dispositivo no Intune. Nesse momento, o usuário receberá as configurações e políticas de seus grupos de usuários. A associação do usuário não pode ser alterada sem um novo registro.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Suporte do Intune para várias contas do Programa de registro de dispositivos da Apple/Apple School Manager <!-- 747685 eeready -->

Agora o Intune é compatível com o registro de dispositivos de até 100 contas diferentes do DEP (Programa de registro de dispositivos) da Apple ou do Apple School Manager. Cada token carregado pode ser gerenciado separadamente para o registro de perfis e dispositivos. Um perfil de registro diferente pode ser atribuído automaticamente por token do DEP/School Manager carregado. Se vários tokens do School Manager forem carregados, será possível compartilhar apenas um por vez com o Microsoft School Data Sync.

Após a migração, as APIs do Graph beta e os scripts publicados para gerenciamento do DEP da Apple ou do ASM no Graph deixarão de funcionar. Há novas APIs do Graph beta em desenvolvimento que serão lançadas após a migração.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Impressão remota em uma rede segura <!-- 1709994  -->
As soluções de impressão móvel sem fio do PrinterOn permitirão aos usuários imprimir remotamente de qualquer lugar, e a qualquer momento, em uma rede segura. O PrinterOn será integrado ao SDK do Aplicativo do Intune para iOS e Android. Você poderá direcionar políticas de proteção de aplicativo para esse aplicativo por meio da folha **Políticas de proteção do aplicativo** do Intune no console do administrador. Os usuários finais poderão baixar o aplicativo "PrinterOn para Microsoft" através da Play Store ou iTunes para uso no ecossistema do Intune.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Suporte do Portal da Empresa para macOS para registros que usam o Gerenciador de Registros do Dispositivo <!-- 1352411 -->

Agora os usuários podem fazer registro no Portal da Empresa para macOS usando o Gerenciador de Registros do Dispositivo.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Relatórios de status de ameaça e status da integridade do Windows Defender <!--854704 -->

Compreender o status da integridade e das ameaças do Windows Defender é essencial para gerenciar computadores Windows.  Com essa atualização, o Intune adiciona novos relatórios e ações ao status e à integridade do agente do Windows Defender. Usando um relatório de acúmulo de status na [carga de trabalho de Conformidade do Dispositivo](../protect/compliance-policy-monitor.md), você pode ver os dispositivos que precisam do seguinte:
- atualização de assinatura
- Reiniciar
- intervenção manual
- verificação completa
- outros estados de agente que requerem intervenção

Um relatório de análise para cada categoria de status lista os computadores individuais que precisam de atenção ou aqueles cujo estado relatado é **Limpo**.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Novas configurações de privacidade para restrições de dispositivo <!--1308926 -->
Agora [duas novas configurações de privacidade](../configuration/device-restrictions-windows-10.md#privacy) estão disponíveis para dispositivos:
- **Publicar as atividades do usuário**: defina como **Bloquear** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas.
- **Apenas atividades locais**: defina como **Bloquear** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas com base somente em atividades locais.

#### <a name="new-settings-for-the-microsoft-edge-browser---1469166---"></a>Novas configurações para o navegador Microsoft Edge <!--1469166 -->
Agora há [duas novas configurações](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser) disponíveis para dispositivos com o navegador Microsoft Edge: **Caminho para o arquivo de favoritos** e **Alterações aos Favoritos**.

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="protocol-exceptions-for-applications---1035509---"></a>Exceções de protocolo para aplicativos <!--1035509 -->

Agora você pode criar exceções para a política de transferência de dados de MAM (gerenciamento de aplicativo móvel) do Intune para abrir aplicativos não gerenciados específicos. Esses aplicativos devem ser confiáveis para a TI. Exceto pelas exceções que você cria, a transferência de dados ainda fica restrita a aplicativos gerenciados pelo Intune quando sua política de transferência de dados estiver definida como **somente aplicativos gerenciados**. É possível criar as restrições usando protocolos (iOS) ou pacotes (Android).

Por exemplo, é possível adicionar o pacote do Webex como uma exceção à política de transferência de dados de MAM. Isso permitirá que links do Webex em uma mensagem de email gerenciada do Outlook sejam abertos diretamente no aplicativo Webex. A transferência de dados permanecerá restrita em outros aplicativos não gerenciados. Para obter mais informações, consulte [Exceções à política transferência de dados para aplicativos](../apps/app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Dados criptografados de WIP (Proteção de Informações do Windows) nos resultados da pesquisa do Windows <!-- 1469193 -->
Uma configuração na política de WIP (Proteção de Informações do Windows) agora permite que você controle se os dados criptografados por WIP são incluídos nos resultados da pesquisa do Windows. Defina essa opção da política de proteção de aplicativo por meio da seleção de **Permitir que o indexador do Windows Search pesquise itens criptografados** nas **Configurações avançadas** da política de Proteção de Informações do Windows. A política de proteção do aplicativo deve ser definida para a plataforma *Windows 10* e a política de aplicativo **Estado do registro** deve ser definida como **Com registro**. Para obter mais informações, consulte [Permitir que o indexador do Windows Search pesquise itens criptografados](../apps/windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Configurando um aplicativo móvel do MSI com autoatualização <!-- 1740840 -->
Você pode configurar um aplicativo móvel do MSI com atualização automática conhecido para ignorar o processo de verificação de versão. Essa funcionalidade é útil para evitar entrar em uma condição de corrida. Por exemplo, esse tipo de condição de corrida poderá ocorrer se o aplicativo que está sendo automaticamente atualizado pelo desenvolvedor também for atualizado pelo Intune. As duas atualizações podem tentar impor uma versão do aplicativo em um cliente do Windows, o que poderia criar um conflito. Para esses aplicativos do MSI atualizados automaticamente, você pode configurar a opção **Ignorar a versão do aplicativo** na folha **Informações do aplicativo**. Quando essa configuração é definida como **Sim**, Microsoft Intune ignora a versão do aplicativo instalada no cliente do Windows.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Conjuntos relacionados de licenças de aplicativo compatíveis com o Intune <!-- 1864117 -->
Agora o Intune no Portal do Azure é compatível com conjuntos relacionados de licenças de aplicativo como um único item de aplicativo na interface do usuário. Além disso, qualquer aplicativo licenciado offline sincronizado da Microsoft Store para Empresas será consolidado em uma única entrada de aplicativo e qualquer detalhe de implantação dos pacotes individuais será migrado para essa única entrada. Para exibir conjuntos de licenças de aplicativo relacionados no portal do Azure, selecione **Licenças de aplicativo** na folha **Aplicativos clientes**.

### <a name="device-configuration"></a>Configuração do dispositivo
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Extensões de arquivo da WIP (Proteção de Informações do Windows) para criptografia automática <!-- 1463582 -->
Uma configuração na política da WIP (Proteção de Informações do Windows) agora permite que você especifique quais extensões de arquivo são criptografadas automaticamente ao copiar de um compartilhamento de SMB (protocolo SMB) dentro do limite corporativo, como definido na política da WIP.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Definir as configurações de conta do recurso para Surface Hubs

Você já pode definir remotamente configurações de conta do recurso para Surface Hubs.

A conta do recurso é usada por um Surface Hub para autenticar no Skype/Exchange a fim de ingressar em uma reunião.
Você poderá criar uma conta do recurso exclusiva para que o Surface Hub possa aparecer na reunião como aparece na sala de conferência.
Por exemplo, uma conta do recurso como **Sala de conferência B41/6233**.

> [!NOTE]
> - Se deixar os campos em branco, você substituirá os atributos configurados anteriormente no dispositivo.
>
> - As propriedades de conta do recurso podem ser alteradas dinamicamente no Surface Hub. Por exemplo, se a rotação de senha estiver ativada. Portanto, é possível que os valores no console do Azure levem algum tempo para refletir a realidade do dispositivo.
>
>   Para entender o que está configurado atualmente no Surface Hub, os dados da conta do recurso podem ser incluídas no inventário de hardware (que já tem um intervalo de sete dias) ou como propriedades somente leitura. Para aumentar a precisão após a ação remota ter ocorrido, você pode obter o estado dos parâmetros imediatamente após a execução da ação para atualizar a conta/parâmetros no Surface Hub.

##### <a name="attack-surface-reduction"></a>Redução da superfície de ataque

|Nome da configuração  |Opções de configuração  |Descrição  |
|---------|---------|---------|
|Execução de conteúdo executável protegido por senha no email|Bloquear, Auditoria, Não configurado|Impedir que arquivos executáveis protegidos por senha baixados por email sejam executados.|
|Proteção avançada contra ransomware|Habilitado, Auditoria, Não configurado|Usar proteção agressiva contra ransomware.|
|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows|Habilitado, Auditoria, Não configurado|Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows (lsass.exe).|
|Criação de processo de comandos WMI e PSExec|Bloquear, Auditoria, Não configurado|Bloquear criações de processo provenientes de comandos PSExec e WMI.|
|Processos não assinados e não confiáveis executados de um USB|Bloquear, Auditoria, Não configurado|Bloquear processos não assinados e não confiáveis executados de um USB.|
|Arquivos executáveis que não atendem um critério de prevalência, idade ou lista confiável|Bloquear, Auditoria, Não configurado|Bloquear a execução de arquivos executáveis a menos que eles atendam a um critério de prevalência, de idade ou de lista confiável.|

##### <a name="controlled-folder-access"></a>Acesso controlado à pasta

|              Nome da configuração               |                                                              Opções de configuração                                                              | Descrição |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Proteção de pasta (já implementada) | Não configurado, Habilitar, Somente auditoria (já implementado)<br><br> <strong>Novo</strong><br>Bloquear modificação de disco, Auditar modificação de disco |             |

Proteger arquivos e pastas contra alterações não autorizadas por aplicativos não amigáveis.<br><br>**Habilitar**: impedir que aplicativos não confiáveis modifiquem ou excluam arquivos em pastas protegidas e gravem em setores do disco.<br><br>
**Bloquear modificação de disco somente**:<br>Impedir que aplicativos não confiáveis gravem em setores do disco. Aplicativos não confiáveis ainda podem modificar ou excluir arquivos em pastas protegidas.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Acréscimos às configurações de Segurança do sistema para políticas de conformidade do Windows 10 e posteriores <!--1704133-->

Acréscimos às configurações de conformidade do Windows 10 já estão disponíveis, incluindo a necessidade de um Firewall e do Windows Defender Antivírus.

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Suporte para aplicativos offline da Microsoft Store para Empresas <!--1222672-->
Aplicativos offline comprados na Microsoft Store para Empresas agora estão sincronizados com o Portal do Azure. Você pode implantar esses aplicativos em grupos de dispositivos ou de usuários. Os aplicativos offline são instalados pelo Intune e não pela loja.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Impedir que os usuários finais adicionem ou removam contas manualmente no perfil de trabalho <!-- 1728700 -->

Agora, ao implantar o aplicativo Gmail em um perfil Android for Work, você pode impedir que usuários finais adicionem ou removam contas manualmente no perfil de trabalho, usando a configuração **Adicionar e remover contas** no perfil de restrições de dispositivo do Android for Work.

<!-- ########################## -->
## <a name="january-2018"></a>Janeiro de 2018

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alertas para tokens expirados e tokens que expirarão em breve <!-- 1639263 -->
A página de visão geral agora mostra alertas para tokens expirados e tokens que expirarão em breve. Ao clicar em um alerta de um único token, você será levado até a página de detalhes do token.  Se você clicar no alerta com vários tokens, será levado até uma lista com todos os tokens e seu status. Os administradores devem renovar seus tokens antes da data de expiração.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Suporte ao comando "Erase" remoto para dispositivos macOS <!-- 1438084 -->

Os administradores podem emitir um comando Erase remotamente para dispositivos macOS.

> [!IMPORTANT]
> O comando erase não pode ser revertido e deve ser usado com cuidado.

O comando erase remove todos os dados, incluindo o sistema operacional, de um dispositivo. Também remove o dispositivo do gerenciamento do Intune. Nenhum aviso é emitido para o usuário, e a remoção ocorre imediatamente após a emissão do comando.

Você deve configurar um PIN de recuperação de seis dígitos. Este PIN pode ser usado para desbloquear o dispositivo apagado e, nesse momento, a reinstalação do sistema operacional começará. Após o início da remoção, o PIN aparecerá em uma barra de status na folha de visão geral do dispositivo no Intune. O PIN permanecerá enquanto a remoção estiver em andamento. Após a conclusão da remoção, o dispositivo desaparecerá totalmente do gerenciamento do Intune. Anote o PIN de recuperação para que a pessoa que estiver restaurando o dispositivo possa usá-lo.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Revogar licenças para um token de Programa de Compra por Volume do iOS <!-- 820870 -->
Você pode revogar a licença de todos os aplicativos do VPP (Apple Volume Purchase Program) do iOS para um determinado Token de VPP.

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Revogação de aplicativos do Volume Purchase Program do iOS  <!-- 820863 -->
Para um determinado dispositivo que tem um ou mais aplicativos do VPP (Apple Volume Purchase Program) do iOS, você pode revogar a licença do aplicativo com base no dispositivo associada ao dispositivo. A revogação de uma licença de aplicativo não desinstala o aplicativo VPP relacionado do dispositivo. Para desinstalar um aplicativo VPP, altere a ação de atribuição para **Desinstalar**. Para saber mais, confira [Como gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune](../apps/vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Atribuir aplicativos móveis do Office 365 a dispositivos iOS e Android usando o tipo de aplicativo integrado <!-- 1332318 -->
O tipo de aplicativo **Interno** facilita a criação e atribuição de aplicativos do Office 365 aos dispositivos iOS e Android que você gerencia. Esses aplicativos incluem aplicativos 0365 como Word, Excel, PowerPoint e OneDrive. Você pode atribuir aplicativos específicos ao tipo de aplicativo e editar a configuração de informações do aplicativo.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Inclusão e exclusão da atribuição de aplicativo com base em grupos <!-- 1406920 -->

Durante a atribuição de aplicativo e após a seleção de um tipo de atribuição, você pode selecionar os grupos a serem incluídos e os grupos a serem excluídos.

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Você pode atribuir uma política de configuração de aplicativo para grupos por meio da inclusão e exclusão de atribuições  <!-- 1480316 -->

Você pode atribuir uma política de configuração de aplicativo a um grupo de usuários e dispositivos usando uma combinação de atribuições de inclusão e exclusão. As atribuições de podem ser escolhidas como uma seleção personalizada de grupos ou como um grupo virtual. Um grupo virtual pode incluir **Todos os usuários**, **Todos os dispositivos** ou **Todos os Usuários + Todos os Dispositivos**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Suporte para política de atualização de edição do Windows 10   <!-- 903672(archived), 1119689 -->  
Você pode criar uma política de atualização de edição do Windows 10 que atualiza dispositivos Windows 10 para Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education e Windows 10 Professional Education N. Para obter detalhes sobre atualizações de edição do Windows 10, veja [Como configurar atualizações de edição do Windows 10](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>As Políticas de Acesso Condicional para o Intune só estão disponíveis no portal do Azure  <!-- 1737088 1634311 -->

Começando por esta versão, você deve configurar e gerenciar suas políticas de Acesso Condicional no [Portal do Azure](https://portal.azure.com), em **Azure Active Directory** > **Acesso Condicional** . Para sua conveniência, você também pode acessar essa folha do Intune no portal do Azure em **Intune** > **Acesso Condicional**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Atualizações nos emails de conformidade <!--1637547 -->

Quando um email é enviado para informar sobre um dispositivo não compatível, os detalhes sobre esse dispositivo são incluídos.

### <a name="intune-apps"></a>Aplicativos do Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nova funcionalidade para a ação "Resolver" para dispositivos Android <!--1583480-->

O aplicativo Portal da Empresa para Android está expandindo a ação "Resolver" para **Atualizar configurações do dispositivo** a fim de resolver [problemas de criptografia de dispositivo](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Bloqueio remoto disponível no aplicativo de Portal da Empresa para Windows 10 <!--676506-->
Agora, os usuários finais podem bloquear remotamente seus dispositivos do aplicativo do Portal da Empresa para Windows 10. Isso não será exibido para o dispositivo local que ele estiver usando ativamente.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Resolução facilitada de problemas de conformidade para o aplicativo do Portal da Empresa para Windows 10 <!--676546-->
Os usuários finais com dispositivos Windows poderão tocar no motivo da não conformidade no aplicativo Portal da Empresa. Quando possível, isso os levará diretamente para o local correto no aplicativo de configurações para corrigir o problema.

<!-- ########################## -->
## <a name="december-2017"></a>Dezembro de 2017

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nova configuração automática de reimplantação <!-- 1469168 -->
Essa configuração de **Reimplantação automática** permite que usuários com direitos administrativos excluam todos os dados e configurações de usuário usando **Ctrl+Win+R** na tela de bloqueio do dispositivo. O dispositivo é reconfigurado automaticamente e registrado novamente no gerenciamento. Essa configuração pode ser encontrada em Windows 10 > Restrições de dispositivo > Geral > Reimplantação automática. Para obter mais detalhes, confira [Configurações de restrição de dispositivo do Intune para Windows 10](../configuration/device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Suporte para as edições de origem adicionais na política de atualização de edição do Windows 10  <!-- 903672,  1119689 -->
Agora você pode usar a política de atualização de edição do Windows 10 para atualizar de edições adicionais do Windows 10 (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud etc.). Antes desta versão, os caminhos de atualização de edição com suporte eram mais limitados. Para obter detalhes, confira [Como configurar atualizações de edição do Windows 10](../configuration/edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Novas definições do perfil de configuração de dispositivo da WDSC (Central de Segurança do Windows Defender) <!-- 1335507 -->

O Intune adiciona uma nova seção de configurações de perfil de configuração de dispositivo sob a Proteção de ponto de extremidade chamada **Central de Segurança do Windows Defender**. Os administradores de TI podem configurar quais pilares do aplicativo Central de Segurança do Windows Defender os usuários finais podem acessar. Se um administrador de TI ocultar um pilar no aplicativo Central de Segurança do Windows Defender, todas as notificações relacionadas ao pilar oculto não serão exibidas no dispositivo do usuário.

Estes são os pilares que os administradores podem ocultar nas configurações do perfil de configuração de dispositivo da Central de Segurança do Windows Defender:
- Proteção contra vírus e ameaças
- Desempenho e integridade do dispositivo
- Proteções de firewall e rede
- Controle de aplicativo e navegador
- Opções da família

Os administradores de TI também podem personalizar quais notificações os usuários recebem. Por exemplo, você pode configurar se os usuários recebem todas as notificações geradas por pilares visíveis na WDSC, ou apenas as notificações críticas. As notificações não críticas incluem resumos periódicos de atividades do Windows Defender Antivírus e notificações após a conclusão das verificações. Todas as outras notificações são consideradas críticas. Além disso, você também pode personalizar o conteúdo da própria notificação, por exemplo, você pode fornecer informações de contato da TI para incorporar as notificações que aparecem nos dispositivos dos usuários.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Suporte a vários conectores para manipulação de certificado SCEP e PFX <!-- 1361755 -->

Agora, os clientes que usam o conector NDES local para fornecer certificados para dispositivos podem configurar vários conectores em um único locatário.

Essa nova capacidade dá suporte ao seguinte cenário:

- **Alta disponibilidade**

Cada conector NDES efetua o pull de solicitações de certificado do Intune.  Se um conector NDES ficar offline, o outro conector poderá continuar processando solicitações.

#### <a name="customer-subject-name-can-use-aad_device_id-variable-----1468599---"></a>Nome da entidade do cliente pode usar a variável AAD_DEVICE_ID  <!-- 1468599 -->

Agora, ao criar um perfil de certificado SCEP no Intune, você pode usar a variável AAD_DEVICE_ID ao compilar o nome de entidade personalizado.   Quando o certificado é solicitado usando esse perfil SCEP, a variável é substituída pela ID do dispositivo AAD do dispositivo que está fazendo a solicitação de certificado.


### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Gerenciar dispositivos macOS inscritos em Jamf com o mecanismo de conformidade do dispositivo do Intune <!-- 1592747 -->
Agora, você pode usar Jamf para enviar informações de estado do dispositivo macOS ao Intune, que, em seguida, avaliará a conformidade com as políticas definidas no console do Intune. Com base no estado de conformidade do dispositivo, bem como em outras condições (como local, risco de usuário etc.), o Acesso Condicional impõe a conformidade para dispositivos macOS que estão acessando aplicativos de nuvem e locais conectados com o Azure AD, incluindo o Office 365. Saiba mais sobre [como configurar a integração com Jamf](../protect/conditional-access-integrate-jamf.md) e [impor a conformidade para dispositivos gerenciados por Jamf](../protect/conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nova ação do dispositivo iOS   <!-- 1424701 -->

Agora, você pode desligar os dispositivos supervisionados com o iOS 10.3. Essa ação desliga o dispositivo imediatamente sem avisar o usuário final. A ação **Desligar (somente supervisionado)** pode ser encontrada nas propriedades do dispositivo quando você seleciona um dispositivo na carga de trabalho **Dispositivo**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Não permitir alterações de data/hora para dispositivos Samsung Knox <!-- 1468103 -->

Adicionamos um novo recurso que permite o bloqueio de alterações de data e hora em dispositivos Samsung Knox. Encontre isso nos **Perfis de configuração do dispositivo** > **Restrições de dispositivo (Android)**  > **Geral**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Conta do recurso do Surface Hub compatível <!-- 1566442  -->

Uma nova ação de dispositivo foi adicionada para que os administradores possam definir e atualizar a conta do recurso associada a um Surface Hub.

A conta do recurso é usada por um Surface Hub para autenticar com o Skype/Exchange a fim de ingressar em uma reunião. Você pode criar uma conta de recurso exclusiva para que o Surface Hub apareça na reunião como aparece na sala de conferência. Por exemplo, a conta do recurso pode aparecer como *Sala de conferência B41/6233*. A conta do recurso (conhecida como conta de dispositivo) para o Surface Hub normalmente precisa ser configurada para o local da sala de conferência, e quando outros parâmetros de conta de recurso precisam ser alterados.

Quando os administradores querem atualizar a conta do recurso em um dispositivo, eles devem fornecer as credenciais atuais do Active Directory/Azure Active Directory associadas ao dispositivo. Se a rotação de senha estiver ativada para o dispositivo, os administradores deverão acessar o Azure Active Directory para localizar a senha.

> [!NOTE]
> Todos os campos são enviados em um pacote, e substituem todos os campos que foram previamente configurados. Os campos vazios também são substituídos pelos campos existentes.

Veja a seguir as configurações que os administradores podem definir:

- **Conta de recurso**
  - **Usuário do Active Directory**

    Nomededomínio\nomedeusuário ou Nome UPN (UPN): user@domainname.com

  - **Senha**

- **Parâmetros opcionais da conta de recurso** (devem ser definidos usando a conta de recurso especificada)

  - **Período de rotação de senha**

    Certifique-se de que a senha da conta seja atualizada automaticamente pelo Surface Hub toda semana por motivos de segurança. Para configurar os parâmetros após essa habilitação, a conta no Azure Active Directory deve ter a senha redefinida primeiro.

  - **Endereço SIP (protocolo de iniciação de sessão)**

    Usado somente quando a descoberta automática falha.

  - **Email**

    Endereço de email da conta de recurso/do dispositivo.

  - **Exchange Server**

    Exigido somente quando a descoberta automática falha.

  - **Sincronização do calendário**

    Especifica se a sincronização de calendário, e outros serviços de servidor do Exchange, está habilitada. Por exemplo: sincronização de reunião.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Instalar aplicativos do Office em dispositivos macOS <!-- 1494311 -->
Agora, você pode instalar aplicativos do Office em dispositivos macOS. Esse novo tipo de aplicativo permitirá que você instale o Word, Excel, PowerPoint, Outlook e OneNote. Esses aplicativos também são fornecidos com o MAU (Microsoft AutoUpdate), para ajudar a manter seus aplicativos seguros e atualizados.

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Excluir um token de Programa de Compra por Volume do iOS <!-- 820879 -->
Você pode excluir o token do VPP (Programa de Compra por Volume) do iOS usando o console. Isso pode ser necessário quando houver instâncias duplicadas de um token VPP.

### <a name="intune-apps"></a>Aplicativos do Intune


### <a name="role-based-access-control"></a>Controle de acesso baseado em função

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Uma nova coleção de entidade chamada Usuário Atual é limitada a usuários ativos no momento <!-- 1667026 -->

A coleção de entidades **Usuários** contém todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa. Por exemplo, um usuário pode ter sido adicionado ao Intune e, em seguida, removido durante o último mês. Embora esse usuário não esteja presente no momento do relatório, o usuário e o estado estão presentes nos dados. Você pode criar um relatório que mostra a duração da presença histórica do usuário em seus dados.

Em contraste, a nova coleção de entidade **Usuário Atual** contém apenas os usuários que não foram removidos. A coleção de entidade **Usuário Atual** contém apenas usuários ativos no momento. Para saber mais sobre a coleção de entidade **usuário atual**, veja [Referência para a entidade de usuário atual](../developer/reports-ref-data-model.md).

### <a name="updated-graph-apis----1736360---"></a>APIs do Graph atualizadas <!-- 1736360 -->

Nesta versão, atualizamos algumas das APIs do Graph para Intune que estão na versão beta. Confira o [log de alterações mensal da API do Graph](https://developer.microsoft.com/graph/docs/concepts/changelog) para saber mais.

### <a name="monitor-and-troubleshoot"></a>Monitorar e solucionar problemas

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>O Intune é compatível com aplicativos negados pela WIP (Proteção de Informações da Windows) <!-- 1479103 -->
Você pode especificar aplicativos negados no Intune. Se um aplicativo for negado, ele será impedida de acessar informações corporativas, efetivamente o oposto da lista de aplicativos permitidos. Para obter mais informações, consulte [Lista de negações recomendados para a Proteção de Informações do Windows](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).

<!-- ########################## -->
## <a name="november-2017"></a>Novembro de 2017

### <a name="troubleshoot-enrollment-issues-----746324---"></a>Solucionar problemas de registro  <!-- 746324 -->

Agora o workspace **Solução de problemas** mostra problemas de registro do usuário. Os detalhes sobre o problema e as etapas de correção sugeridas podem ajudar os administradores e os operadores de suporte técnico a solucionar problemas. Determinados problemas de registro não são capturados e alguns erros podem não ter as sugestões de correção.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Restrições de registro atribuídas pelo grupo <!-- 747598 -->

Como administrador do Intune, agora é possível [criar restrições personalizadas de registro de Tipo de dispositivo e de Limite de dispositivos para grupos de usuários](../enrollment/enrollment-restrictions-set.md).

O Portal do Azure do Intune permite criar até 25 instâncias de cada tipo de restrição que podem ser atribuídas a grupos de usuários. Restrições atribuídas a grupos substituem as restrições padrão.

Todas as instâncias de um tipo de restrição são mantidas em uma lista estritamente ordenada. Essa ordem define um valor de prioridade para resolução de conflitos. Um usuário afetado por mais de uma instância de restrição é restringido apenas pela instância com o valor de prioridade mais elevado. Você pode alterar a prioridade de uma determinada instância arrastando-a para uma posição diferente na lista.

Essa funcionalidade será lançada com a migração das configurações de Android for Work no menu de registro do Android for Work para o menu de Restrições de Registro. Como esta migração pode levar vários dias, sua conta pode ser atualizada para outras partes do lançamento de novembro antes que você veja uma atribuição de grupo habilitada para Restrições de Registro.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Suporte para vários conectores do Serviço de Registro de Dispositivo de Rede (NDES) <!-- 1528104 -->

O NDES permite a execução de dispositivos móveis sem credenciais de domínio para obter certificados baseados no protocolo SCEP.
Nesta atualização, há suporte a vários conectores NDES.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Gerenciar dispositivos Android for Work independentemente dos dispositivos Android <!-- 1490731 EEready-->

O Intune é compatível com gerenciamento de registro de dispositivos Android for Work independentemente da plataforma Android. Essas configurações são gerenciadas em **Registro de Dispositivo** > **Restrições de registro** > **Restrições de Tipo de Dispositivo**. (Anteriormente, elas estavam localizadas em **Registro de Dispositivo** > **Registro de Android for Work** > **Configurações de Registro de Android for Work**.)

Por padrão, as configurações de dispositivos Android for Work são as mesmas que as configurações para dispositivos Android. No entanto, depois de alterar as configurações de Android for Work, esse não será mais o caso.

Se você bloquear o registro pessoal de Android for Work, somente dispositivos Android corporativos poderão se registrar como Android for Work.

Ao trabalhar com as novas configurações, considere os seguintes pontos:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Se você nunca integrou o registro de Android for Work antes

A plataforma Android for Work está bloqueada nas restrições de Tipo de Dispositivo padrão. Após integrar o recurso, você poderá permitir que dispositivos se registrem com Android for Work. Para fazer isso, altere o padrão ou crie uma nova restrição de Tipo de Dispositivo para substituir a restrição padrão de Tipo de Dispositivo.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Se você tiver integrado o registro de Android for Work

Se você já tiver integrado antes, sua situação dependerá da configuração que escolher:

| Setting | Status de Android for Work na Restrição de Tipo de Dispositivo padrão | Anotações |
| --- | --- | --- |
| **Gerenciar todos os dispositivos como Android** | Bloqueado | Todos os dispositivos Android devem se registrar sem o Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work** | Permitido | Todos os dispositivos que oferecem suporte ao Android for Work devem ser registrados com Android for Work. |
| **Gerenciar dispositivos com suporte como Android for Work somente para os usuários nestes grupos** | Bloqueado | Uma política de Restrição de Tipo de Dispositivo separada foi criada para substituir o padrão. Essa política define os grupos que você selecionou anteriormente para permitir o registro Android for Work. Usuários dentro dos grupos selecionados ainda poderão registrar seus dispositivos Android for Work. Todos os outros usuários são impedidos de se registrar com o Android for Work. |

Em todos os casos, a norma pretendida é preservada. Nenhuma ação é necessária de sua parte para manter a permissão global ou por grupo do Android for Work em seu ambiente.

### <a name="google-play-protect-support-on-android----908720---"></a>Suporte para Google Play Protect no Android <!-- 908720 -->

Com o lançamento do Android Oreo, o Google apresenta um conjunto de recursos de segurança chamado Google Play Protect, que permitem aos usuários e organizações a execução de aplicativos seguros e a proteção de imagens do Android. Agora o Intune é compatível com os recursos do Google Play Protect, incluindo atestado remoto do SafetyNet. Os administradores podem definir requisitos de política de conformidade que exigem que o Google Play Protect esteja configurado e íntegro.
A configuração **Atestado do dispositivo SafetyNet** exige que o dispositivo se conecte a um serviço do Google para verificar se o dispositivo está íntegro e não comprometido. Os administradores também podem definir um perfil de configuração para o Android for Work a fim de exigir que os aplicativos instalados sejam verificados pelos serviços do Google Play. Se um dispositivo não for compatível com os requisitos do Google Play Protect, o Acesso Condicional poderá impedir que os usuários acessem recursos corporativos.

- Saiba [Como criar uma política de conformidade do dispositivo para habilitar o Google Play Protect](../protect/compliance-policy-create-android.md).

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protocolo de texto permitido em Aplicativos gerenciados <!-- 1414050  -->

Aplicativos gerenciados pelo SDK do Aplicativo do Intune podem enviar mensagens SMS.


### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Relatório de instalação de aplicativos atualizado para incluir o status de Instalação pendente <!-- 1249446 -->  

O relatório **Status de instalação do aplicativo**, acessível para cada aplicativo por meio da lista **Aplicativo** na carga de trabalho **Aplicativos clientes**, agora contém uma contagem de **Instalação pendente** para Usuários e Dispositivos.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API do inventário de aplicativos iOS 11 para detecção de ameaças móveis <!-- 1391759 -->

O Intune coleta informações do inventário de aplicativos de dispositivos pessoais e corporativos e as disponibiliza para provedores de MTD (Detecção de Ameaça Móvel) para efetuar fetch, como Lookout for Work. É possível coletar um inventário de aplicativos dos usuários de dispositivos iOS 11+.

**Inventário de aplicativos**  
Inventários de dispositivos pessoais e corporativos iOS 11+ são enviados para o provedor de serviços de MTD. Os dados de inventário de aplicativos incluem:

- ID do aplicativo
- Versão de Aplicativo
- Versão Curta do Aplicativo
- Nome do Aplicativo
- Tamanho do Pacote do Aplicativo
- Tamanho Dinâmico do Aplicativo
- O Aplicativo é validado ou não
- O Aplicativo é gerenciado ou não

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrar usuários e dispositivos do MDM híbrido para o Intune autônomo <!-- 1463747 wnready -->
Novos processos e ferramentas já estão disponíveis para mover os usuários e seus dispositivos do MDM híbrido para o Intune no Portal do Azure, permitindo que você realize as seguintes tarefas:
- Copiar perfis e políticas do console do Configuration Manager para o Intune no portal do Azure
- Mover um subconjunto de usuários ao Intune no portal do Azure enquanto mantém o restante no MDM híbrido
- Migrar os dispositivos para o Intune no portal do Azure sem necessidade de registrá-los novamente

Consulte os detalhes em [Migrar usuários e dispositivos do MDM híbrido para o Intune autônomo](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Suporte de alta disponibilidade do Exchange Connector local  <!-- 676614 -->
Após o Exchange Connector criar uma conexão com o Exchange usando o CAS (Servidor de Acesso ao Cliente) especificado, o conector terá a capacidade de descobrir outros CASs. Se o CAS primário ficar não disponível, o conector realizará o failover em outro CAS, se houver um disponível, até que o CAS primário fique disponível. Para obter detalhes, confira [Suporte de alta disponibilidade do Exchange Connector local](../protect/exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support).

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Reiniciar remotamente o dispositivo iOS (somente supervisionado) <!-- 1424595 -->

Agora é possível disparar um dispositivo iOS 10.3+ supervisionado para reiniciar usando uma ação do dispositivo. Para obter mais informações sobre como usar a ação de reinício de dispositivo, consulte [Reiniciar remotamente dispositivos com o Intune](../remote-actions/device-restart.md).

> [!Note]
> Este comando requer um dispositivo supervisionado e o direito de acesso de **Bloqueio de Dispositivo**. O dispositivo é reiniciado imediatamente. Dispositivos iOS protegidos por senha não serão reconectados a uma rede Wi-Fi após a reinicialização; Após a reinicialização, é possível que eles não se comuniquem com o servidor.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Suporte para logon único para iOS <!-- 1333645 -->  

Você pode usar o Logon Único para usuários do iOS. Os aplicativos iOS que são codificados para exigir credenciais do usuário no conteúdo do Logon Único são compatíveis com essa atualização de configuração de conteúdo. Você também pode usar o UPN e a ID de Dispositivo do Intune para configurar o Nome da entidade e o Realm. Para obter detalhes, consulte [Configurar o Intune para logon único de dispositivo iOS](../configuration/ios-device-features-settings.md#single-sign-on).

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Adicionar "Encontrar meu iPhone" para dispositivos pessoais <!--1427287-->
Agora você pode exibir se os dispositivos iOS têm o Bloqueio de Ativação ligado. Esse recurso podia ser encontrado anteriormente no portal clássico do Intune.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Bloquear dispositivos macOS gerenciados remotamente com o Intune <!-- 1437691 -->

É possível bloquear um dispositivo macOS perdido e definir um PIN de recuperação de 6 dígitos. Quando bloqueados, a folha de **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.

Para obter mais informações, consulte [Bloquear dispositivos gerenciados remotamente com o Intune](../remote-actions/device-remote-lock.md).

### <a name="new-scep-profile-details-supported----1559808---"></a>Novos detalhes do perfil de SCEP com suporte <!-- 1559808 -->

Agora os administradores podem definir configurações adicionais ao criar um perfil SCEP em plataformas Windows, iOS, macOS e Android.  Os administradores podem definir o IMEI, o número ou o nome comum incluindo email no formato de nome do assunto.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset----1588489---"></a>Manter dados durante uma redefinição de fábrica  <!--1588489 -->
Ao restaurar o Windows 10 versão 1709 e posterior para as configurações de fábrica, uma nova funcionalidade estará disponível. Os administradores poderão especificar se o registro de dispositivo e outros dados provisionados serão mantidos em um dispositivo por meio de uma redefinição de fábrica.

Os seguintes dados são mantidos após a redefinição de fábrica:
- Contas do usuário associadas ao dispositivo
- Estado do computador (ingresso no domínio, ingressado no Azure Active Directory)
- Registro do MDM
- Aplicativos instalados pelo OEM (aplicativos do Win32 e da loja)
- Perfil de usuário
- Dados do usuário de fora do perfil do usuário
- Logon automático do usuário

Os dados a seguir não são mantidos:
- Arquivos do usuário
- Aplicativos instalados pelo usuário (aplicativos do Win32 e da loja)
- Configurações do dispositivo não padrão


### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>As atribuições de anel de atualização do Windows 10 são exibidas <!-- 1621837 -->
Quando estiver **solucionando problemas** para o usuário que estiver sendo exibido, será possível ver as atribuições de anéis de atualização do Windows 10.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Configurações de frequência do relatório da Proteção Avançada contra Ameaças do Windows Defender  <!-- 1455974  -->
O serviço de Proteção Avançada contra Ameaças (WDATP) do Windows Defender permite que os administradores gerenciem a frequência dos relatórios para dispositivos gerenciados. Com a nova opção de **Agilizar a frequência de relatórios de telemetria**, o WDATP coleta dados e avalia os riscos com mais frequência. O padrão para relatórios otimiza a velocidade e o desempenho. Aumentar a frequência de emissão de relatórios pode ser importante para dispositivos de alto risco. Essa configuração pode ser encontrada no perfil **Windows Defender ATP** nas **Configurações do dispositivo**.

### <a name="audit-updates----1412961---"></a>Atualizações de auditoria <!-- 1412961 -->  
A auditoria do Intune fornece um registro das operações de alteração relacionadas ao Intune.  Todas as operações de criação, atualização, exclusão e de tarefa remota são capturadas e mantidas por um ano.  O portal do Azure fornece uma exibição dos últimos 30 dias de dados de auditoria em cada carga de trabalho e pode ser filtrado.  Uma API do Graph correspondente permite a recuperação dos dados de auditoria armazenados para o último ano.

A auditoria é encontrada no grupo **MONITOR**. Há um item de menu de **Logs de Auditoria** para cada carga de trabalho.

### <a name="company-portal-app-for-macos-is-available---1541700--"></a>O aplicativo Portal da Empresa para macOS está disponível <!--1541700-->
O Portal da Empresa do Intune no macOS tem uma experiência atualizada, que foi otimizada para exibir corretamente todas as informações e notificações de conformidade que seus usuários precisam para todos os dispositivos inscritos. E, após a implantação do Portal da Empresa do Intune em um dispositivo, o Microsoft AutoUpdate para macOS fornecerá as atualizações. Baixe o novo Portal da Empresa do Intune para macOS fazendo logon no site do Portal da Empresa do Intune em um dispositivo macOS.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Agora, o Microsoft Planner faz parte da lista MAM (gerenciamento de aplicativo móvel) de aplicativos aprovados  <!-- 1248473 -->
O aplicativo Microsoft Planner para iOS e Android agora faz parte dos aplicativos aprovados para MAM (gerenciamento de aplicativo móvel). O aplicativo pode ser configurado por meio da folha Proteção de Aplicativo do Intune no Portal do Azure para todos os locatários.
- Saiba mais sobre a [lista MAM de aplicativos aprovados](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Frequência de atualização de requisito por VPN por aplicativo em dispositivos iOS   <!-- 1547061 -->  
Agora, os administradores podem remover os requisitos de acordo com a VPN do aplicativo para aplicativos em dispositivos iOS; os dispositivos afetados serão após o próximo check-in no Intune, o que geralmente ocorre em 15 minutos.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Suporte para o pacote de gerenciamento do System Center Operations Manager para o conector do Exchange <!-- 885457 -->
O pacote de gerenciamento do System Center Operations Manager para o conector do Exchange está disponível para ajudar você a analisar os logs do conector do Exchange. Com esse recurso, você terá diferentes maneiras de monitorar o serviço quando houver necessidade de solucionar problemas.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Cogerenciamento para dispositivos Windows 10  <!-- 1243445 -->
O cogerenciamento é uma solução que fornece uma ponte do gerenciamento tradicional para o moderno e um caminho para fazer a transição usando uma abordagem em fases. Na sua base, o cogerenciamento é uma solução na qual os dispositivos Windows 10 são gerenciados simultaneamente pelo Configuration Manager e pelo Microsoft Intune, e também podem ser ingressados no AD (Active Directory) e no Azure AD (Azure Active Directory).  Essa configuração lhe fornece um caminho para modernizar ao longo do tempo, no ritmo que seja adequado para sua organização se você não puder mover tudo de uma só vez.  

### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Restringir o registro do Windows por versão do sistema operacional <!-- 245498 -->
Como administrador do Intune, agora é possível especificar uma versão mínima e uma máxima do Windows 10 para registros de dispositivo. É possível definir essas restrições na folha **Configurações de Plataforma**.

Agora o Intune continuará dando suporte ao registro de computadores e telefones Windows 8.1. Contudo, apenas versões do Windows 10 podem ser definidas com limites mínimo e máximo. Para permitir o registro de dispositivos 8.1, deixe o limite mínimo vazio.

### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alertas para dispositivos não atribuídos do Windows AutoPilot  <!-- 1631236 -->
Um novo alerta está disponível para dispositivos não atribuídos do Windows AutoPilot na página **Microsoft Intune** > **Registro de Dispositivo** > **Visão geral**. Este alerta mostra quantos dispositivos do programa AutoPilot não têm perfis de implantação do AutoPilot atribuídos. Use as informações no alerta para criar perfis e atribuí-los aos dispositivos não atribuídos. Quando você clica no alerta, vê uma lista completa de dispositivos Windows AutoPilot e informações detalhadas sobre eles. Para obter mais informações, consulte [Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment](../enrollment/enrollment-autopilot.md).


### <a name="refresh-button-for-devices-list-------1333581---"></a>Botão Atualizar para a Lista de dispositivos    <!-- 1333581 -->
Como a Lista de dispositivos não é atualizada automaticamente, é possível usar o novo botão Atualizar para atualizar os dispositivos exibidos na lista.

### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Suporte para AC (Autoridade de Certificação) da Nuvem Symantec  <!-- 1333638 -->    
O Intune agora é compatível com a AC da Nuvem Symantec, que permite que o Conector de Certificado do Intune emita certificados PKCS da AC da Nuvem Symantec para dispositivos gerenciados pelo Intune. Se você já está usando o Conector de Certificado do Intune com a AC (Autoridade de Certificação) da Microsoft, é possível usar a configuração do Conector de Certificado do Intune existente para adicionar a compatibilidade com a AC da Symantec.

### <a name="new-items-added-to-device-inventory-----1404455---"></a>Novos itens adicionados ao inventário de aplicativos   <!--1404455 -->
Os novos itens a seguir já estão disponíveis para o [inventário realizado por dispositivos registrados](../remote-actions/device-inventory.md):

- Endereço MAC Wi-Fi
- Espaço de armazenamento total
- Espaço livre total
- MEID
- Operadora do assinante

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Definir o acesso para aplicativos pelo patch de segurança do Android mínimo no dispositivo<!-- 1278463 -->   
Um administrador pode definir o patch mínimo de segurança do Android que deve ser instalado no dispositivo para obter acesso a um aplicativo gerenciado em uma conta gerenciada.

> [!Note]  
> Este recurso só restringe os patches de segurança lançados pela Google no Android 6.0 + dispositivos.

### <a name="app-conditional-launch-support----1193313---"></a>Suporte de inicialização condicional do aplicativo <!-- 1193313 -->
Os administradores de TI agora poderão definir um requisito por meio do portal de administração do Azure para impor uma senha em vez de um PIN numérico por meio do gerenciamento de aplicativo móvel (MAM) quando o aplicativo iniciar. Se configurado, o usuário precisa definir e usar uma senha quando solicitado antes de obter acesso a aplicativos habilitados para MAM. Uma senha é definida como um PIN numérico com pelo menos um caractere especial ou letras maiúsculas/minúsculas. Esta versão do Intune permitirá esse recurso **somente no iOS**. O Intune dá suporte à senha de uma maneira semelhante ao PIN numérico, ele define um comprimento mínimo, permitindo caracteres e sequências repetidas. Esse recurso exige a participação de aplicativos (ou seja, WXP, Outlook, Managed Browser, Yammer) para integrar o SDK de Aplicativo do Intune ao código desse recurso em vigor para as configurações de senha a serem impostas aos aplicativos de destino.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>O número de versão do aplicativo de linha de negócios no relatório de instalação de dispositivo <!-- 1233999 -->
Com esta versão, o relatório de status de instalação do dispositivo exibe o número de versão do aplicativo para aplicativos de linha de negócios para iOS e Android. Você pode usar essas informações para solucionar problemas de seus aplicativos ou para localizar dispositivos que executam versões desatualizadas do aplicativo.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Os administradores agora podem definir as configurações de Firewall em um dispositivo usando um perfil de configuração do dispositivo <!-- 951708 -->   
Os administradores podem ativar o firewall para dispositivos e também configurar vários protocolos para redes públicas, privadas e de domínio.  Essas configurações de firewall podem ser encontradas no perfil "Endpoint Protection".

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>O Windows Defender Application Guard ajuda a proteger dispositivos contra sites não confiáveis, conforme definido pela sua organização <!-- 958257 -->   
Os administradores podem definir sites como "confiáveis" ou "corporativos" usando um fluxo de trabalho da Proteção de Informações do Windows ou o novo perfil "Limite de rede" nas configurações do dispositivo. Caso sejam exibidos com o Microsoft Edge, os sites que não estão listados no limite de rede confiável de um dispositivo Windows 10 de 64 bits serão abertos em um navegador de um computador virtual do Hyper-V.

O Application Guard pode ser encontrado nos perfis de configuração do dispositivo, no perfil "Endpoint Protection". A partir daí, os administradores podem configurar a interação entre o navegador virtualizado e o computador host, sites não confiáveis e sites confiáveis e dados de armazenamento gerados no navegador virtualizado. Para usar o Application Guard em um dispositivo, um limite de rede deve estar configurado primeiro. É importante definir somente um limite de rede para um dispositivo.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>O Windows Defender Application Control no Windows 10 Enterprise fornece modo para confiar somente em aplicativos autorizados <!-- 1031096 -->    
Com milhares de novos arquivos mal-intencionados criados diariamente, usar a detecção baseada em assinatura de antivírus para combater o malware poderá deixar de fornecer uma defesa adequada contra novos ataques. Ao usar o Windows Defender Application Control no Windows 10 Enterprise, é possível alterar a configuração do dispositivo de um modo no qual os aplicativos sejam confiáveis, a menos que sejam bloqueados por um antivírus ou outra solução de segurança, para um modo no qual o sistema operacional confie somente em aplicativos autorizados por sua empresa. Atribua confiança a aplicativos no Windows Defender Application Control.

Com o Intune, é possível configurar políticas de controle de aplicativo no modo "somente auditoria" ou no modo de imposição. Os aplicativos não são bloqueados durante a execução no modo “somente auditoria”. O modo "somente auditoria" registra todos os eventos em logs do cliente local. Também é possível configurar se somente componentes do Windows e aplicativos da Microsoft Store podem ser executados ou se aplicativos adicionais com boa reputação, conforme definido pelo Intelligent Security Graph, podem ser executados.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>O Windows Defender Exploit Guard é um novo conjunto de recursos de prevenção contra intrusões para o Windows 10 <!-- 1063615 -->   
O Windows Defender Exploit Guard inclui regras personalizadas para reduzir a capacidade de exploração de aplicativos, impede ameaças à macro e ao script, bloqueia automaticamente conexões de rede para endereços IP de baixa reputação e pode proteger dados do ransomware e ameaças desconhecidas. O Windows Defender Exploit Guard consiste nos seguintes componentes:

- A **Redução da Superfície de Ataque** fornece regras que permitem impedir ameaças a email, macro e script.
- O **acesso controlado a pastas** bloqueia automaticamente o acesso ao conteúdo de pastas protegidas.
- O **Filtro de Rede** bloqueia a conexão de saída de qualquer aplicativo para IP/domínio de baixa reputação
- O **Exploit Protection** fornece memória, fluxo de controle e restrições de políticas que podem ser usados para proteger um aplicativo contra explorações.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10 <!-- 790537 -->

A extensão de gerenciamento do Intune permite que você carregue scripts do PowerShell no Intune para serem executados em dispositivos Windows 10. A extensão complementa as funcionalidades MDM (Gerenciamento de Dispositivo Móvel) do Windows 10 e torna fácil para você passar para um gerenciamento moderno. Para obter detalhes, consulte [Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10](../apps/intune-management-extension.md).

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Novas configurações de restrição de dispositivo para Windows 10      <!-- 1308850 -->
- Mensagens (somente celular) – Desabilite testes ou mensagens MMS
- Senha – As configurações para habilitar o FIPS e o uso dos dispositivos secundários Windows Hello para autenticação 
- Tela – Configurações para ativar ou desativar o dimensionamento do GDI para aplicativos herdados

### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Restrições de dispositivo do modo de quiosque do Windows 10 <!-- 1308872 -->   
É possível restringir os usuários do dispositivo Windows 10 ao modo de quiosque, que limita os usuários a um conjunto de aplicativos predefinidos.  Para fazer isso, crie um perfil de restrição de dispositivo Windows 10 e defina as configurações de Quiosque.

O modo de quiosque dá suporte a dois modos: **único aplicativo** (permite que um usuário execute apenas um aplicativo) ou **multiaplicativo** (permite o acesso a um conjunto de aplicativos).  Você define o nome do dispositivo e da conta de usuário, o que determina os aplicativos com suporte).  Quando o usuário está conectado, ele estará limitado aos aplicativos definidos.  Para obter mais informações, consulte [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

O modo de quiosque requer:

- O Intune deve ser a autoridade MDM.
- Os aplicativos já devem estar instalados no dispositivo de destino.
- O dispositivo deve ser [adequadamente provisionado](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Novo perfil de configuração do dispositivo para criar limites de rede <!-- 1311967 -->   
Um novo perfil de configuração de dispositivo chamado **Limite de rede** pode ser encontrado com seus outros perfis de configuração de dispositivo. Use esse perfil para definir os recursos online que você deseja que sejam considerados corporativos e confiáveis. Você deve definir um limite de rede para um dispositivo *antes* que os recursos, como o Windows Defender Application Guard e a Proteção de Informações do Windows, possam ser usados no dispositivo. É importante definir somente um limite de rede para cada dispositivo.

Você pode definir recursos de nuvem da empresa, intervalos de endereços IP e servidores proxy internos que você deseja que sejam considerados confiáveis. Depois de definido, um limite de rede pode ser consumido por outros recursos, como o Windows Defender Application Guard e a Proteção de Informações do Windows.

### <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Duas configurações adicionais para o Windows Defender Antivírus <!-- 1338409 -->  
**Nível de bloqueio de arquivo**

| | |
|---|---|
| Não configurado | **Não Configurado** usa o nível de bloqueio padrão do Windows Defender Antivírus e fornece detecção de alta segurança sem aumentar o risco de detectar arquivos legítimos. |
| Alta | **Alto** se aplica um alto nível de detecção.
| Alta +  | **Alto +** fornece um alto nível com medidas de proteção adicional que podem afetar o desempenho do cliente.
| Tolerância zero  | A **Tolerância zero** bloqueia todos os executáveis desconhecidos. |

Embora seja pouco provável, configurar como **Alto** pode fazer com que alguns arquivos legítimos sejam detectados.
É recomendável definir o nível de bloqueio do Arquivo para padrão, **Não configurado**.

**Extensão de tempo limite para verificação de arquivo pela nuvem**  

| | |
|--|--|
| Número de segundos (0-50) | Especifique o máximo de tempo para o Windows Defender Antivírus bloquear um arquivo enquanto aguarda um resultado da nuvem. O tempo padrão é de 10 segundos: qualquer tempo adicional especificado aqui (até 50 segundos) será adicionado a esses 10 segundos. Na maioria dos casos, a verificação leva muito menos tempo do que o máximo. Estender o tempo permite que a nuvem investigue completamente os arquivos suspeitos. É recomendável que você habilite essa configuração e especifique pelo menos 20 segundos adicionais. |

### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix VPN adicionado a dispositivos Windows 10 <!-- 1512457 -->  
É possível configurar uma VPN Citrix para seus dispositivos Windows 10. É possível escolher a VPN do Citrix na lista *Selecione um tipo de conexão* na folha **VPN da Base** ao configurar a VPN para Windows 10 e posterior.

> [!Note]
> A configuração do Citrix existia para iOS e Android.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>As conexões Wi-Fi são compatíveis com chaves pré-compartilhadas no iOS <!-- 1550823 -->
Os clientes podem configurar perfis Wi-Fi para usar PSK (chaves pré-compartilhadas) para conexões WPA/WPA2 Personal em dispositivos iOS. Esses perfis são enviados por push para o dispositivo do usuário quando o dispositivo é registrado no Intune.

Quando o perfil tiver sido enviado por push para o dispositivo, a próxima etapa dependerá da configuração do perfil.  Se estiver configurado para se conectar automaticamente, ele se conectará quando a rede for a próxima necessária.  Quando o perfil se conecta manualmente, o usuário deve ativar a conexão manualmente.  

### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Acesso aos logs de aplicativos gerenciados para iOS <!-- 1469920 -->
Agora os usuários finais com o Browser gerenciado instalado podem exibir o status de gerenciamento de todos os aplicativos publicados da Microsoft e enviar logs para solucionar problemas dos seus aplicativos iOS gerenciados.

Saiba como habilitar o modo de solução de problemas no Managed Browser em um dispositivo iOS, consulte [How to access to managed app logs using the Managed Browser on iOS](../apps/app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) (Como acessar logs de aplicativos gerenciados usando o Managed Browser no iOS).

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Aprimoramentos no fluxo de trabalho de configuração de dispositivo no Portal da Empresa para iOS na versão 2.9.0 <!-- 1417174 -->

O fluxo de trabalho de configuração de dispositivo foi melhorado no aplicativo Portal da Empresa para iOS. A linguagem é mais fácil de usar e combinamos as telas sempre que possível. A linguagem é mais específica à sua empresa ao usar o nome da empresa em todo o texto de configuração. Veja esse fluxo de trabalho atualizado na  [página de novidades da interface do usuário do aplicativo](../whats-new-app-ui.md).


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Entidade de usuário contém dados mais recentes do usuário no modelo de dados do Data Warehouse <!-- 1544273 -->
A primeira versão do modelo de dados do Intune Data Warehouse continha somente dados históricos recentes do Intune. Os criadores de relatório não podiam capturar o estado atual de um usuário. Nesta atualização, a **Entidade do usuário** é preenchida com os dados mais recentes do usuário.

<!-- ########################## -->
## <a name="october-2017"></a>Outubro de 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>O número de versão do aplicativo de linha de negócios Android e iOS é visível <!-- 1380712 -->

Aplicativos no Intune agora exibem o número de versão para aplicativos de linha de negócios iOS e Android. O número é exibido no portal do Azure na lista de aplicativos e na folha de visão geral do aplicativo. Os usuários finais podem ver o número do aplicativo no aplicativo do Portal da Empresa e no portal da web.

__Número de versão completo__ O número de versão completo identifica uma versão específica do aplicativo. O número é exibido como _Versão_(_Build_). Por exemplo, 2.2(2.2.17560800)

O número de versão completa tem dois componentes:

- **Versão**  
  O número de versão é o número de versão legível do aplicativo. Isso é usado pelos usuários finais para identificar versões diferentes do aplicativo.

- **Número de build**  
  O número de build é um número interno que pode ser usado na detecção do aplicativo e para gerenciar o aplicativo de forma programática. O número de build se refere a uma iteração do aplicativo que referencia alterações no código.

Saiba mais sobre os números de versão e desenvolvimento de aplicativos de linha de negócios em [Introdução ao SDK de Aplicativo do Microsoft Intune](../developer/app-sdk-get-started.md#line-of-business-app-version-numbers).

### <a name="device-and-app-management-integration----677972---"></a>Integração do gerenciamento de dispositivos e aplicativos <!-- 677972 -->   
Agora que o gerenciamento de dispositivo móvel do Intune (MDM) e o gerenciamento de aplicativo móvel (MAM) são ambos acessíveis do portal do Azure, o Intune começou integrar a experiência de administração de TI em torno do gerenciamento de aplicativo e dispositivo. Essas alterações têm o objetivo de simplificar seu dispositivo e a experiência de gerenciamento de aplicativo.

Saiba mais sobre as alterações de MDM e MAM anunciadas no [blog da equipe de suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Novos alertas de registro para dispositivos Apple <!-- 1471790 -->
A página de visão geral de registro mostrará alertas úteis para administradores de TI sobre o gerenciamento de dispositivos Apple. Os alertas serão exibido na página Visão geral de quando o certificado de push de MDM da Apple estiver expirando ou já tiver expirado; quando o token do Programa de Registro de Dispositivos estiver expirando ou já tiver expirado; e quando houver dispositivos não atribuídos no Programa de Registro de Dispositivo.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Substituição do token de suporte para a configuração de aplicativos sem registro de dispositivo <!-- 1080364 -->

Você pode usar tokens de valores dinâmicos nas configurações de aplicativo para aplicativos em dispositivos que não estão registrados. Para obter mais informações, consulte [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](../apps/app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Atualizações para o aplicativo Portal da Empresa para Windows 10 <!--1299474-->
A página Configurações no aplicativo Portal da Empresa para Windows 10 foi atualizada para tornar as configurações e as ações de usuário pretendidas mais consistentes em todas as configurações. Ela também foi atualizada para corresponder ao layout de outros aplicativos do Windows. Encontre imagens de antes/depois na página [Novidades da interface do usuário do aplicativo](../whats-new-app-ui.md).

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para dispositivos com Windows 10 <!--1337920-->
Adicionamos o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para Windows 10. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela **Sobre**.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Solicitações de comentários para o aplicativo Portal da Empresa para Android <!--1165249-->
O aplicativo Portal da Empresa para Android agora solicita comentários do usuário final. Estes comentários são enviados diretamente para a Microsoft e fornecem aos usuários finais uma oportunidade de avaliar o aplicativo na loja pública do Google Play. Os comentários não são obrigatórios, e podem ser ignorados facilmente para que os usuários possam continuar usando o aplicativo.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Ajudando seus usuários com o aplicativo de Portal da Empresa para Android <!-- 1573324, 1573150, 1558616, 1564878 -->

O aplicativo de Portal da Empresa para Android adicionou instruções para os usuários finais a fim de ajudá-los a compreender e, quando possível, resolver automaticamente novos casos de uso.
- Os usuários finais serão direcionados para o [Portal do Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) para remover um dispositivo se tiverem atingido o número máximo de dispositivos que eles têm permissão para adicionar.
- Os usuários finais recebem etapas a serem seguidas para ajudá-los a [corrigir erros de ativação em dispositivos Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) ou a [desligar o modo de economia de energia](/intune-user-help/power-saving-mode-android). Se nenhuma dessas soluções resolver o problema, fornecemos uma explicação de como [enviar logs para a Microsoft](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nova ação “Resolver” disponível para dispositivos Android <!-- 1583480 -->

O aplicativo do Portal da Empresa para Android está apresentando uma ação de “Resolver” na página _Atualizar configurações do dispositivo_. Selecionar essa opção levará o usuário final diretamente para a configuração que está causando a não conformidade do seu dispositivo. O aplicativo do Portal da Empresa para Android atualmente dá suporte a essa ação para as configurações de [senha do dispositivo](/intune-user-help/set-your-pin-or-password-android), [depuração de USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) e [Fontes Desconhecidas](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Indicador de progresso de configuração do dispositivo no Portal da Empresa para Android <!-- 1565657 -->
O aplicativo Portal da Empresa para Android mostra um indicador de progresso de configuração do dispositivo quando o usuário estiver inscrevendo seu dispositivo. O indicador mostra novos status, começando com "Configurando seu dispositivo...", depois "Registrando seu dispositivo..." e "Concluindo o registro de seu dispositivo...", em seguida, "Concluindo a configuração de seu dispositivo...".

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Suporte à autenticação baseada em certificado no Portal da Empresa para iOS <!--1029830-->
Adicionamos suporte para autenticação baseada em certificado (CBA) no aplicativo do Portal da Empresa para iOS. Os usuários com CBA inserem seus nomes de usuário, em seguida, tocam no link "Entrar com um certificado". O CBA já é compatível com os aplicativos do Portal da Empresa para Android e Windows. Você pode obter mais informações na página [entrar no aplicativo do Portal da Empresa](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Os aplicativos disponíveis com ou sem inscrição podem ser instalados sem receber uma solicitação de inscrição. <!-- 1334712 -->

Os aplicativos da empresa que foram disponibilizados com ou sem o registro no aplicativo do Portal da Empresa Android agora podem ser instalados sem um aviso de registro.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Suporte do Programa Windows AutoPilot Deployment no Microsoft Intune  <!-- 747617  -->
Agora você pode usar o Microsoft Intune com o programa Windows AutoPilot Deployment para capacitar os usuários a provisionarem dispositivos corporativos sem envolver TI. Você pode personalizar a OOBE (configuração inicial pelo usuário) e orientar os usuários a ingressarem seus dispositivos no Azure AD e a se registrarem no Intune. Trabalhando juntos, o Microsoft Intune e o Windows AutoPilot eliminam a necessidade de implantar, manter e gerenciar imagens do sistema operacional. Para obter detalhes, consulte [Enroll Windows devices using Windows AutoPilot Deployment Program](../enrollment/enrollment-autopilot.md) (Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment).

### <a name="quickstart-for-device-enrollment-----1425655---"></a>Início Rápido para o registro de dispositivo  <!-- 1425655 --> 
O Início Rápido agora está disponível para o **Registro de dispositivo** e fornece uma tabela de referências para gerenciamento de plataformas e a configuração do processo de registro. Uma breve descrição de cada item e links para a documentação com instruções passo a passo fornece uma documentação útil para simplificar a introdução.

### <a name="device-categorization----1427491---"></a>Categorização de dispositivo <!-- 1427491 -->
O gráfico de plataforma de dispositivos registrados da folha **Dispositivos > Visão geral** organiza os dispositivos pela plataforma, incluindo Windows Mobile, Windows, macOS, iOS e Android.  Os dispositivos que executam outros sistemas operacionais são agrupados em "Outros".  Isso inclui dispositivos fabricados pela Blackberry, NOKIA e outras.  

Para saber quais dispositivos são afetados em seu locatário, escolha **Gerenciar > Todos os dispositivos** e, em seguida, use **Filtrar** para limitar o campo **SO**.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium – Novo parceiro de Defesa contra Ameaças Móveis   <!-- 954681 -->  
Você pode controlar o acesso de dispositivos móveis aos recursos corporativos usando o Acesso Condicional com base na avaliação de risco realizada pela Zimperium, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Como funciona a integração com o Intune
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Zimperium. Você pode configurar políticas de Acesso Condicional de EMS com base na avaliação de risco da Zimperium habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos sem conformidade a recursos corporativos com base em ameaças detectadas.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10  <!--- 978575, 1308849, -->  
Estamos adicionando novas configurações ao perfil de restrição de dispositivo Windows 10 na categoria Windows Defender SmartScreen.

Para obter detalhes sobre o perfil de restrição de dispositivo Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior](../configuration/device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Suporte remoto para dispositivos Windows e Windows Mobile   <!-- 1070473 -->  
O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, que permite dar assistência remota a usuários que executam dispositivos Windows e Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Verificar dispositivos com o Windows Defender <!-- 1280988  1280990   -->
Agora você pode executar uma **Verificação rápida**, uma **Verificação completa** e **Atualizar assinaturas** com o Windows Defender Antivírus em dispositivos Windows 10 gerenciados. Na folha de visão geral do dispositivo, escolha a ação a ser executada no dispositivo. Você precisará confirmar a ação antes de o comando ser enviado ao dispositivo. 

**Verificação rápida**: uma verificação rápida examina os locais onde o malware registra-se para começar, como as chaves do Registro e pastas de inicialização conhecidas do Windows. Uma verificação rápida demora cerca de cinco minutos. Combinada com a configuração **Proteção sempre em tempo real**, que examina os arquivos quando eles são abertos, fechados e sempre que um usuário navega até uma pasta, uma verificação rápida ajuda a fornecer proteção contra malware que pode estar no sistema ou no kernel. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Verificação completa**: uma verificação completa pode ser útil em dispositivos que encontraram uma ameaça de malware para identificar se há componentes inativos que exigem uma limpeza mais completa, e é útil para executar verificações sob demanda. A verificação completa pode demorar uma hora. Os usuários veem os resultados da varredura em seus dispositivos após a conclusão. 

**Atualizar assinaturas**: o comando para atualizar assinatura atualiza as definições e assinaturas de malware do Windows Defender. Isso ajuda a garantir o que Windows Defender Antivírus seja eficaz na detecção de malware. Esse recurso destina-se somente a dispositivos com Windows 10, com conectividade de internet pendente no dispositivo. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>O botão Habilitar/Desabilitar foi removido da página Autoridade de Certificação do Intune do portal do Azure do Intune  <!-- 1400455 -->
 Estamos eliminando uma etapa extra da configuração do Certificate Connector no Intune. No momento, você pode baixar o Certificate Connector e habilitá-lo no console do Intune. No entanto, se você desabilitar o conector no console do Intune, o conector continuará a emitir certificados.

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
A partir de outubro, o botão Habilitar/Desabilitar não aparecerá mais na página Autoridade de certificação no Portal do Azure. A funcionalidade do conector permanece a mesma. Os certificados ainda são implantados nos dispositivos registrados no Intune. Você ainda pode baixar e instalar o Certificate Connector. Para interromper a emissão de certificados, agora você pode desinstalar o Certificate Connector em vez de desabilitá-lo.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?
Se o Certificate Connector já estiver desabilitado, você deverá desinstalá-lo.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Novas configurações do perfil de restrição de dispositivo do Windows 10 Team   <!--- 1308838 -->
Nesta versão, foram adicionadas várias novas configurações ao perfil de restrição de dispositivo do Windows 10 Team para ajudar a controlar dispositivos do Surface Hub.

Para saber mais sobre esse perfil, veja [Configurações de restrição de dispositivo do Windows 10 Team](../configuration/device-restrictions-windows-10-teams.md).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Impedir que os usuários de dispositivos com Android alterem a data e a hora de seus dispositivos  <!-- 1333292 -->
Use uma [política de dispositivo personalizada do Android](../configuration/custom-settings-android.md) para impedir que os usuários de dispositivos com Android alterem a data e a hora do dispositivo.

Para fazer isso, configure uma política personalizada do Android com o URI de configuração ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Defina isso como **TRUE** e, em seguida, atribua-o aos grupos necessários.

### <a name="bitlocker-device-configuration----1397398---"></a>Configuração de dispositivo do BitLocker <!-- 1397398 -->
A seção **Criptografia do Windows > Configurações Base** inclui uma nova configuração **Aviso para criptografia de outro disco** que permite que você desabilite o [prompt de aviso](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowwarningforotherdiskencryption) para a criptografia de outro disco que possa estar em uso no dispositivo do usuário.  A mensagem de aviso exige o consentimento do usuário final antes de instalar o BitLocker no dispositivo e bloqueia a instalação do BitLocker até receber a confirmação do usuário final.  A nova configuração desabilita o aviso ao usuário final.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Os aplicativos do Volume Purchase Program for Business agora serão sincronizadas ao seu locatário do Intune <!-- 800882 -->  
Os desenvolvedores de terceiros podem distribuir aplicativos de forma privada para membros autorizados do VPP (Volume Purchase Program) for Business especificados no iTunes Connect. Esses membros do VPP for Business podem entrar na App Store do Volume Purchase Programa e adquirir seus aplicativos.

Com esta versão, os aplicativos do VPP for Business comprados pelo usuário final passarão a ser sincronizados com seus locatários do Intune.

### <a name="select-apple-countryregion-store-to-sync-vpp-apps-----1332311---"></a>Selecione o país/região da loja da Apple para sincronização de aplicativos VPP  <!-- 1332311 -->  
Você pode configurar o país/região da loja do VPP (Programa de Compra por Volume) ao carregar seu token de VPP. O Intune sincroniza aplicativos do VPP para todas as localidades da loja VPP especificada de um país/região.

> [!NOTE]  
> Atualmente, o Intune sincroniza apenas aplicativos do VPP da loja do país/região do VPP que correspondem à localidade do Intune na qual o locatário do Intune foi criado.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Bloquear a ação de copiar e colar entre perfis de trabalho e pessoais no Android for Work <!-- 1098994 -->
Com esta versão, é possível configurar o perfil de trabalho para Android for Work para bloquear a ação de copiar e colar entre aplicativos pessoais e de trabalho. Encontre essa nova configuração no perfil **Restrições de dispositivo** para a plataforma **Android for Work** em **Configurações de perfil de trabalho**.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Criar aplicativos iOS limitados a Apple App Stores regionais específicas <!-- 1281692 -->
Você poderá especificar a localidade do país/região durante a criação de um aplicativo gerenciado da Apple App Store.

> [!Note]  
> No momento, você só pode criar aplicativos gerenciados da Apple App Store que estão presentes na loja dos Estados Unidos.

### <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Atualizar usuário VPP do iOS e os aplicativos de dispositivo licenciados  <!-- 1305564 -->  
Você poderá configurar o token de VPP do iOS para atualizar todos os aplicativos comprados para esse token por meio do serviço Intune. O Intune detectará as atualizações do aplicativo VPP dentro da loja de aplicativos e as enviará automaticamente ao dispositivo quando o dispositivo fizer check-in.

Para obter as etapas para definir um token do VPP e habilitar as atualizações automáticas, consulte [Como gerenciar aplicativos iOS comprados por meio de um Volume Purchase Program com o Microsoft Intune] (/intune/vpp-aplicativos-ios).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Coleção de entidades de associação de dispositivo do usuário adicionada ao modelo de dados do Intune Data Warehouse <!-- 1187917 -->
Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo. O modelo de dados pode ser acessado por meio do arquivo do Power BI (PBIX) recuperado da página do Intune Data Warehouse, por meio do ponto de extremidade OData ou desenvolvendo um cliente personalizado.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Examinar a conformidade da política para anéis de atualização do Windows 10 <!-- 1067886 -->
Você poderá examinar um relatório da política de seus grupos de atualização do Windows 10 em Atualizações de software > Por estado de implantação do grupo de atualização. O relatório da política inclui o status da implantação para os anéis de atualização que você configurou. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Novo relatório que lista os dispositivos iOS com versões anteriores do iOS   <!-- 1352223 -->
O relatório **Dispositivos iOS desatualizados** está disponível no workspace **Atualizações de software**. No relatório, você pode exibir uma lista de dispositivos iOS supervisionados que foram direcionados por uma política de atualização de iOS e têm as atualizações disponíveis. Para cada dispositivo, você pode exibir um status de por que o dispositivo não foi atualizado automaticamente. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Exibir as atribuições de política de proteção do aplicativo para solução de problemas <!--  1475003 -->
Nesta versão futura, a opção de **Política de proteção do aplicativo** será adicionada à lista suspensa **Atribuições** disponível na folha de solução de problemas. Agora você pode selecionar as políticas de proteção do aplicativo para ver as políticas de proteção de aplicativo atribuídas aos usuários selecionados.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Melhorias no fluxo de trabalho de configuração de dispositivo no Portal da Empresa <!--1490692-->
Melhoramos o fluxo de trabalho de configuração de dispositivo no aplicativo do Portal da Empresa para Android. A linguagem é mais fácil de usar e mais específica para sua empresa e combinamos as telas sempre que possível. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md#week-of-october-2-2017).

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Melhor orientação sobre a solicitação de acesso aos contatos em dispositivos Android <!--1484985-->

O aplicativo de Portal da Empresa para Android normalmente exige que o usuário final aceite a permissão de Contatos. Se um usuário final recusar esse acesso, ele verá uma notificação no aplicativo que o alerta para conceder a permissão para Acesso Condicional. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Correção de inicialização segura para Android <!--1490712-->

Os usuários finais com dispositivos Android poderão tocar no motivo da não conformidade no aplicativo do Portal da Empresa. Quando possível, isso os levará diretamente para o local correto no aplicativo de configurações para corrigir o problema. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Notificações por push adicionais para usuários finais no aplicativo Portal da Empresa para Android Oreo <!--1475932-->

Os usuários finais verão notificações adicionais para indicar a eles quando o aplicativo Portal da Empresa para Android Oreo estiver executando tarefas em segundo plano, como recuperação de políticas do serviço Intune. Isso aumenta a transparência para os usuários finais sobre quando o Portal da Empresa está executando tarefas administrativas em seu dispositivo. Isso faz parte da [otimização geral da interface do usuário do Portal da Empresa](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) para o aplicativo Portal da Empresa para Android Oreo. 

Há mais otimizações para novos elementos de interface do usuário que estão habilitados no Android Oreo.  Os usuários finais verão notificações adicionais que indicarão a eles quando o Portal da Empresa estiver executando tarefas em segundo plano, tais como recuperação das políticas do serviço Intune.  Isso aumenta a transparência para os usuários finais sobre quando o Portal da Empresa está executando tarefas administrativas no dispositivo deles.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Novos comportamentos para o aplicativo Portal da Empresa para Android com perfis de trabalho <!-- 1485783 -->

Quando você inscreve um dispositivo do Android for Work com um perfil de trabalho, é o aplicativo de Portal da Empresa no perfil de trabalho que executa as tarefas de gerenciamento no dispositivo. 

Se você estiver usando um aplicativo habilitado para MAM no perfil particular, o aplicativo Portal da Empresa para Android não servirá para mais nada. Para melhorar a experiência de perfil de trabalho, o Intune ocultará automaticamente o aplicativo Portal da Empresa pessoal após uma inscrição bem-sucedida do perfil de trabalho.

O aplicativo Portal da Empresa para Android pode ser habilitado a qualquer momento no perfil pessoal procurando por [Portal da Empresa na Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e tocando em **Habilitar**.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudando para o modo de manutenção <!--1428681-->

A partir de outubro de 2017, os aplicativos de Portal da Empresa para Windows 8.1 e Windows Phone 8.1 mudará para o modo de manutenção. Isso significa que os aplicativos e cenários existentes, como inscrição e conformidade, continuarão a ter suporte para essas plataformas. Esses aplicativos continuarão disponíveis para download por meio dos canais de lançamento existente, como na Microsoft Store. 

Uma vez no modo de manutenção, esses aplicativos receberão apenas atualizações de segurança críticas. Nenhuma atualização ou recurso adicional será lançado para esses aplicativos. Para os novos recursos, recomendamos que você atualize os dispositivos para Windows 10 ou Windows 10 Mobile. 


### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Bloquear o registro de dispositivo Samsung Knox sem suporte  <!-- 1490695 -->

O aplicativo Portal da Empresa tenta registrar apenas os dispositivos Samsung Knox com suporte. Para evitar erros de ativação de Knox que impedem o registro do MDM, o registro do dispositivo será tentado somente se ele aparecer na [lista de dispositivos publicada pela Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Os dispositivos Samsung podem ter números de modelo que oferecem suporte a Knox, enquanto outros não. Verifique a compatibilidade com KNOX com o revendedor do dispositivo antes de adquirir e implantar. Você pode encontrar a lista completa de dispositivos verificados nas [configurações de política do Android e Samsung Knox Standard](supported-devices-browsers.md#intune-supported-web-browsers).

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Fim do suporte para Android 4.3 e inferior <!-- 1171126, 1326920 -->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Até dezembro, todos os dispositivos inscritos serão desativados, resultando na perda do acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e reduzirão a qualidade da sua experiência ao longo do tempo.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Informar aos usuários finais quais informações de dispositivo podem ser vistas em dispositivos registrados <!--1165314-->
Estamos adicionando o **Tipo de Propriedade** à tela Detalhes do Dispositivo em todos os aplicativos Portal da Empresa. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente do artigo [Quais informações sua empresa pode ver?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Isso será distribuído em todos os aplicativos de Portal da Empresa em um futuro próximo. Anunciamos isso para iOS em [setembro](#september-2017).

<!-- ########################## -->
## <a name="september-2017"></a>Setembro de 2017

### <a name="intune-supports-ios-11---1428975--"></a>O Intune dá suporte ao iOS 11 <!--1428975-->
O Intune dá suporte ao iOS 11. Isso foi anunciado anteriormente no [blog de Suporte do Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Fim do suporte para iOS 8.0 <!-- 1164477 -->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para iOS exigirão o iOS 9.0 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes de setembro não poderão acessar o Portal da Empresa ou esses aplicativos. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Ação de atualização adicionada ao aplicativo Portal da Empresa para Windows 10 <!--1132468-->
O aplicativo Portal da Empresa para Windows 10 permite que os usuários atualizem os dados no aplicativo efetuando o pull para atualizar ou, em desktops, pressionando F5.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Informar aos usuários finais que informações de dispositivo podem ser vistas para iOS <!--739894-->

Adicionamos o **Tipo de Propriedade** à tela Detalhes do Dispositivo no aplicativo Portal da Empresa para iOS. Isso permitirá aos usuários obter mais informações sobre privacidade diretamente desta página nos documentos do usuário final do Intune. Eles também poderão localizar essas informações na tela Sobre.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Permitir que os usuários finais acessem o aplicativo de Portal da Empresa para Android sem registro <!---1169910--->

Em breve, os usuários finais não precisarão registrar seu dispositivo para acessar o aplicativo de Portal da Empresa para Android. Os usuários finais em organizações que estão usando as Políticas de Proteção de Aplicativo deixarão de receber solicitações para registrar seu dispositivo quando abrirem o aplicativo de Portal da Empresa. Os usuários finais também poderão instalar aplicativos do Portal da Empresa sem registrar o dispositivo. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Frases mais fáceis de entender para o aplicativo Portal da Empresa para Android <!---1396349--->  

O processo de inscrição para o aplicativo Portal da Empresa para Android foi simplificado com o novo texto a fim de facilitar a inscrição dos usuários. Se você tiver a documentação de inscrição personalizada, atualize-o para refletir as novas telas. Você pode encontrar as imagens de amostra na nossa página [Atualizações da interface do usuário para aplicativos de usuário final do Intune](whats-new-app-ui.md#week-of-september-11-2017).

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Aplicativo Portal da Empresa do Windows 10 adicionado à política de permissão da Proteção de Informações do Windows <!-- 677129 -->

O aplicativo Portal da Empresa do Windows 10 foi atualizado para dar suporte à WIP (Proteção de Informações do Windows). O aplicativo pode ser adicionado à política de permissão do WIP. Com essa alteração, o aplicativo não precisa mais ser adicionado à lista **Isento**.


<!-- ########################## -->
## <a name="august-2017"></a>Agosto de 2017

### <a name="improvements-to-device-overview----1404453---"></a>Melhorias na visão geral de dispositivos <!-- 1404453 -->  
Com as melhorias, agora a visão geral de dispositivos exibe os dispositivos registrados, mas exclui os dispositivos gerenciados pelo Exchange ActiveSync. Os dispositivos do Exchange ActiveSync não têm as mesmas opções de gerenciamento que os dispositivos registrados. Para exibir o número de dispositivos registrados e o número de dispositivos registrados por plataforma no Intune, no portal do Azure, acesse **Dispositivos** > **Visão geral**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Melhorias no inventário de dispositivos coletado pelo Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
Nesta versão, fizemos as seguintes melhorias nas informações de inventário coletadas para cada um dos dispositivos que você gerencia:
 
- Para dispositivos Android, agora você pode adicionar uma coluna no inventário de dispositivos que mostra o nível de patch mais recente para cada dispositivo. Adicione a coluna **Nível de patch de segurança** à sua lista de dispositivos para ver essa informação.
- Ao filtrar a exibição de dispositivos, agora você pode filtrar os dispositivos pela data de registro. Por exemplo, você pode exibir somente os dispositivos que foram registrados após uma data especificada.
- Fizemos melhorias no filtro usado pelo item **Última data de check-in**.
- Na lista de dispositivos, agora você pode exibir o número de telefone dos dispositivos corporativos.
Além disso, você pode usar o painel de filtro para pesquisar dispositivos por número de telefone.

Para obter mais detalhes sobre o inventário de dispositivos, consulte [Como exibir o inventário de dispositivo do Intune](../remote-actions/device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>Suporte a Acesso Condicional para dispositivos macOS 
<!-- 720172 -->
Agora você pode definir uma política de acesso condicional que exige que os dispositivos Mac sejam registrados no Intune e estejam em conformidade com as políticas de conformidade do dispositivo. Por exemplo, os usuários podem baixar o aplicativo de Portal da Empresa Intune para macOS e registrar seus dispositivos Mac no Intune. O Intune avaliar se o dispositivo Mac está em conformidade ou não com requisitos como PIN, criptografia, versão do sistema operacional e integridade do sistema.

- Saiba mais sobre o [Suporte a Acesso Condicional para dispositivos macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>O aplicativo Portal da Empresa para macOS está em versão prévia pública <!---1484796--->
O aplicativo Portal da Empresa para macOS agora está disponível como parte da visualização pública para Acesso Condicional no Enterprise Mobility + Security. Essa versão é compatível com macOS 10.11 e superior. Obtenha-a em [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Novas configurações de restrição de dispositivo para Windows 10    
<!--1063965, 1308850  -->
Nesta versão, adicionamos novas configurações no [perfil de restrição de dispositivo Windows 10](/intune/device-restrictions-windows-10) nas seguintes categorias:

- Windows Defender SmartScreen
- Loja de aplicativos

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Atualizações no perfil de dispositivo de Endpoint Protection do Windows 10 para configurações do BitLocker
<!--1459533 -->    
Nesta versão, fizemos as seguintes melhorias no modo de funcionamento das configurações do BitLocker em um perfil de dispositivo de Endpoint Protection do Windows 10:
 
- Em **Configurações de unidade do sistema operacional do Bitlocker**, na configuração **BitLocker com chip do TPM não compatível**, anteriormente, quando você selecionava **Bloquear**, o BitLocker era permitido. Agora isso foi corrigido para bloquear o BitLocker quando essa opção está selecionada.
- Em **Configurações da unidade do sistema operacional do Bitlocker**, na configuração **Agente de recuperação de dados com base em certificado**, agora você pode bloquear explicitamente o agente de recuperação de dados com base em certificado. No entanto, por padrão, o agente é permitido.
- Em **Configurações de unidade de dados fixa do BitLocker**, na configuração **Agente de recuperação de dados**, agora você pode bloquear explicitamente o agente de recuperação de dados.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](../protect/endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nova experiência conectada para usuários do Portal da Empresa para Android e para usuários da Política de Proteção de Aplicativo <!-- 621669 -->
Agora, os usuários finais podem procurar aplicativos, gerenciar dispositivos e exibir informações de contato de TI usando o aplicativo Portal da Empresa para Android sem registrar seus dispositivos Android. Além disso, se um usuário final já usa um aplicativo protegido pelas Políticas de Proteção de Aplicativo do Intune, ele não recebe mais uma solicitação para registrar o dispositivo ao iniciar o Portal da Empresa para Android.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nova configuração no aplicativo Portal da Empresa para Android para ativar/desativar a otimização de bateria <!--1405990-->
A página **Configurações** no aplicativo Portal da Empresa para Android tem uma nova configuração que permite que os usuários desliguem facilmente a otimização da bateria para os aplicativos Portal da Empresa e Microsoft Authenticator. O nome do aplicativo mostrado na configuração variará dependendo de qual aplicativo gerencia a conta de trabalho. É recomendável que os usuários desliguem a otimização da bateria para melhorar o desempenho dos aplicativos de trabalho que sincronizam dados e emails. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Suporte a várias identidades do OneNote para iOS      <!-- 1234281 -->
Os usuários finais agora podem usar contas diferentes (trabalho e pessoal) com o Microsoft OneNote para iOS. As políticas de proteção de aplicativo podem ser aplicadas aos dados corporativos em blocos de anotações de trabalho sem afetar os blocos de anotações pessoais. Por exemplo, uma política pode permitir que um usuário localize informações em blocos de anotações de trabalho, mas impedirá que o usuário copie e cole dados corporativos do bloco de anotações de trabalho para um bloco de anotações pessoal.
 
- Saiba mais sobre os aplicativos que dão suporte à [proteção de aplicativo e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Novas configurações para permitir e bloquear aplicativos em dispositivos Samsung Knox Standard
<!-- 1305423 822899-->  
Nessa versão, estamos adicionando novas [configurações de restrições de dispositivo](../configuration/device-restrictions-android.md) que permitem especificar as seguintes listas de aplicativo:
 
- Aplicativos que os usuários têm permissão para instalar
- Aplicativos que os usuários são impedidos de executar
- Aplicativos que ficam ocultados do usuário no dispositivo
 
Você pode especificar o aplicativo por URL, nome de pacote ou na lista de aplicativos gerenciados.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Link da nova interface do usuário da política de Acesso Condicional com base no aplicativo do Azure AD no Intune
<!-- 1016201 -->
Agora os administradores de TI podem definir políticas condicionais baseadas no aplicativo por meio da nova interface do usuário de política de Acesso Condicional na carga de trabalho do Azure AD. O Acesso Condicional com base no aplicativo na seção Proteção de Aplicativo do Intune no Portal do Azure por enquanto continuará lá, e a implementação será feita em conjunto. Também há um link de conveniência para a nova interface do usuário da política de Acesso Condicional na carga de trabalho do Intune.

- Saiba mais sobre o [Acesso Condicional com base no aplicativo no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).

<!-- ########################## -->
## <a name="july-2017"></a>Julho de 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Restringir a restrição de registro de dispositivo Android e iOS por versão do sistema operacional  <!--- 1333256,  1245463 --->
O Intune agora dá suporte à restrição do registro de iOS e Android por número de versão do sistema operacional. Agora, em **Restrição de Tipo de Dispositivo**, o administrador de TI pode definir uma configuração de plataforma para restringir o registro entre os valores mínimo e máximo do sistema operacional. As versões do sistema operacional Android devem ser especificadas como Major.Minor.Build.Rev, em que Minor, Build e Rev são opcionais. Versões do iOS devem ser especificadas como Major.Minor.Build, em que Minor e Build são opcionais. Saiba mais sobre as [restrições de registro de dispositivo](../enrollment/enrollment-restrictions-set.md).

>[!NOTE]
>Não restringe o registro por meio dos programas de registro da Apple ou do Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Restringir o registro de dispositivos de propriedade pessoal Android, iOS e macOS  <!--- 1333272,  1333275, 1245709 --->
O Intune pode restringir o registro de dispositivos pessoais colocando em uma lista de permissões os números IMEI dos dispositivos corporativos. Agora, o Intune expandiu essa funcionalidade para iOS, Android e macOS usando os números de série do dispositivo. Ao carregar os números de série para o Intune, você pode pré-declarar os dispositivos como corporativos. Usando as restrições de registro, você pode bloquear dispositivos pessoais (BYOD), permitindo somente o registro de dispositivos corporativos. Saiba mais sobre as [restrições de registro de dispositivo](../enrollment/enrollment-restrictions-set.md).

Para importar os números de série, acesse **Registro de dispositivo** > **Identificadores de dispositivo corporativo**, clique em **Adicionar** e, em seguida, carregue um arquivo .CSV (sem cabeçalho, duas colunas de número de série e detalhes como números IMEI). Para restringir os dispositivos pessoais, acesse **Registro de dispositivo** > **Restrições de registro**. Em **Restrições de tipo de dispositivo**, selecione o **Padrão** e, em seguida, escolha **Configurações da Plataforma**. Você pode **Permitir** ou **Bloquear** dispositivos pessoais para iOS, Android e macOS.


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nova ação de dispositivo para forçar os dispositivos a sincronizarem com o Intune <!-- 711369 -->
Nessa versão, adicionamos uma nova ação de dispositivo que força o dispositivo selecionado a fazer check-in no Intune imediatamente. Quando um dispositivo faz check-in, ele recebe imediatamente as ações pendentes ou políticas que foram atribuídas a ele.  Esta ação pode ajudá-lo a validar imediatamente e solucionar problemas das políticas que você atribuiu, sem aguardar o próximo check-in agendado.
Para ver mais detalhes, consulte [Sincronizar o dispositivo](../remote-actions/device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível <!-- 777100 -->
Uma nova política está disponível no workspace de Atualizações de software, em que você pode forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível. Para obter detalhes, consulte [Configurar políticas de atualização do iOS](/intune/software-updates-ios)

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile – novo parceiro de Defesa contra Ameaças Móveis  <!-- 954651, 1172027 -->
É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o Acesso Condicional baseado na avaliação de risco realizada pelo Checkpoint SandBlast Mobile, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Como a integração com o Intune funciona?
O risco é avaliado com base na telemetria coletada dos dispositivos que executam o Checkpoint SandBlast Mobile. É possível configurar políticas de Acesso Condicional do EMS com base na avaliação de risco do Checkpoint SandBlast Mobile habilitada por meio das políticas de conformidade de dispositivo do Intune. Você pode permitir ou bloquear o acesso de dispositivos não compatíveis aos recursos corporativos com base nas ameaças detectadas.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Implantar um aplicativo como ele está disponível na Microsoft Store para Empresas <!-- 748101 -->
Com essa versão, os administradores agora podem atribuir o Microsoft Store para Empresas como ele está disponível. Quando definido como disponível, os usuários finais podem instalar o aplicativo do site ou do aplicativo do Portal da Empresa sem serem redirecionados para a Microsoft Store.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Atualizações da interface do usuário do site do Portal da Empresa <!--1313244 part 1-->
Fizemos várias atualizações na interface do usuário do [site Portal da Empresa](https://portal.manage.microsoft.com) para aprimorar a experiência do usuário final.

- __Aprimoramentos para blocos de aplicativos__: os ícones de aplicativo agora serão exibidos com uma tela de fundo gerada automaticamente com base na cor dominante do ícone (caso seja possível detectá-la). Quando aplicável, essa tela de fundo substituirá a borda cinza que era visível anteriormente em blocos de aplicativos.

    O site do Portal da Empresa exibe ícones grandes sempre que possível em uma versão futura. É recomendável que os administradores de TI publiquem aplicativos usando ícones de alta resolução com um tamanho mínimo de 120x120 pixels. 

- __Alterações de navegação__: os itens da barra de navegação foram movidos para o menu hambúrguer na parte superior esquerda. A página Categorias foi removida. Os usuários agora podem filtrar o conteúdo por categoria durante a navegação.

- __Atualizações para os Aplicativos em Destaque__: adicionamos uma página dedicada ao site em que os usuários podem procurar os aplicativos que você optou por destacar e fizemos algumas alterações na interface do usuário da seção Em destaque da página inicial.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Suporte para iBooks no site do Portal da Empresa <!--1231841-->
Adicionamos uma página dedicada ao site do Portal da Empresa que permite aos usuários procurar e baixar iBooks. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>Detalhes adicionais da solução de problemas de suporte técnico <!---  Applies to 1263399, 1326964, 1341642 --->
O Intune atualizou a exibição de solução de problemas e aprimorou as informações que ele fornece aos administradores e à equipe de suporte técnico. Agora, é exibida uma tabela **Atribuições** que resume todas as atribuições do usuário com base em associação a um grupo. Essa lista inclui:
- Aplicativos móveis
- Políticas de conformidade
- Perfis de configuração

Além disso, a tabela **Dispositivos** agora inclui as colunas **Tipo de ingresso no Azure AD** e **Em conformidade com o Azure AD**. Para obter mais informações, consulte [ajudar os usuários a solucionar problemas](../help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Intune Data Warehouse (Visualização Pública)
O Intune Data Warehouse coleta amostras de dados diariamente para fornecer uma exibição histórica do locatário. É possível acessar os dados usando um arquivo do Power BI (PBIX), um link OData compatível com várias ferramentas de análise ou interagindo com a API REST. Para obter mais informações, consulte [Usar o Intune Data Warehouse](../developer/reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Modos claro e escuros disponíveis para o aplicativo de Portal da Empresa para Windows 10 <!---676547--->
Os usuários finais poderão personalizar o modo de cores para o aplicativo de Portal da Empresa para Windows 10. O usuário poderá fazer a alteração na seção Configurações do aplicativo de Portal da Empresa. A alteração será exibida depois que o usuário reiniciar o aplicativo. Para Windows 10 versão 1607 e posteriores, o modo de aplicativo padrão será o da configuração do sistema. Para Windows 10 versão 1511 e anteriores, o modo de aplicativo padrão será o da configuração do sistema.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Habilitar que os usuários finais marquem seu grupo de dispositivos no aplicativo de Portal da Empresa para Windows 10 <!---807046-->
Os usuários finais agora podem selecionar a grupo seu dispositivo pertence marcando-o diretamente de no aplicativo de Portal da Empresa para Windows 10.

<!-- ########################## -->
## <a name="june-2017"></a>Junho de 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Novo acesso de administração baseada em funções para administradores do Intune   <!-- 1099990 -->  
Uma nova função de administrador de Acesso Condicional está sendo adicionada para exibir, criar, modificar e excluir políticas de Acesso Condicional do Azure AD. Anteriormente, somente os administradores globais e os administradores de segurança tinham essa permissão. Os administradores do Intune podem receber essa permissão de função para ter acesso às políticas de Acesso Condicional.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Marcar dispositivos de propriedade corporativa com o número de série <!-- 1215070 -->  
O Intune agora dá suporte ao upload dos números de série de iOS, macOS e Android como Identificadores de Dispositivo Corporativo. No momento, não é possível usar números de série para bloquear o registro de dispositivos pessoais, pois os números de série não são verificados durante o registro. O bloqueio de dispositivos pessoais pelo número de série será liberado em breve.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Novas ações remotas para dispositivos iOS <!-- 854689 -->
Neste lançamento, adicionamos duas novas ações remotas para dispositivos iPad compartilhados, que gerenciam o aplicativo Classroom da Apple:

- [Fazer logoff do usuário atual](../remote-actions/device-logout-user.md) – realiza a saída do usuário atual de um dispositivo iOS escolhido.
- [Remover usuário](../remote-actions/device-remove-user.md) – Exclui um usuário escolhido do cache local de um dispositivo iOS.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Suporte para iPads compartilhados com o aplicativo Sala de aula do iOS <!-- 1044681 -->
Nessa versão, expandimos o suporte do gerenciamento do aplicativo Classroom iOS para incluir os alunos que fazem logon em iPads compartilhados usando suas IDs da Apple gerenciadas.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Alterações para aplicativos internos do Microsoft Intune <!-- 1332306 -->
Antes, o Intune incluía vários aplicativos internos que você podia atribuir rapidamente. Com base em seus comentários, removemos esta lista e você não precisa mais conferir os aplicativos internos.
No entanto, se você já atribuiu aplicativos internos, eles ainda estarão visíveis na lista de aplicativos. Você pode continuar a atribuir esses aplicativos conforme necessário.
Planejamos adicionar em um lançamento posterior, um método mais fácil para selecionar e atribuir aplicativos internos no Portal do Azure.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Instalação mais fácil de aplicativos do Office 365 <!--- 1121362 --->
O novo tipo de aplicativo do **Office 365 ProPlus** facilitará a atribuição de aplicativos do Office 365 ProPlus 2016 aos dispositivos gerenciados que executam a versão mais recente do Windows 10. Além disso, você também poderá instalar o Microsoft Project e o Microsoft Visio se tiver licenças para eles. Os aplicativos que você desejar serão agrupados e aparecerão como um aplicativo na lista de aplicativos no console do Intune.
Para obter mais informações, consulte [Como adicionar aplicativos do Office 365 para Windows 10](../apps/apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Suporte para aplicativos offline da Microsoft Store para Empresas <!--- 777044 --->
Aplicativos offline comprados na Microsoft Store para Empresas agora serão sincronizados com o Portal do Azure. Você poderá implantar esses aplicativos em grupos de dispositivos ou de usuários. Os aplicativos offline são instalados pelo Intune e não pela loja.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>O Microsoft Teams agora faz parte da lista de AC baseada em aplicativos de aplicativos aprovados   <!-- 1257019 -->
O aplicativo Microsoft Teams para iOS e Android fará parte dos aplicativos aprovados para as políticas de Acesso Condicional baseado em aplicativos do Exchange e do SharePoint Online. O aplicativo pode ser configurado por meio da folha Proteção de Aplicativo do Intune no Portal do Azure para todos os locatários que usam o Acesso Condicional baseado em aplicativo.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Navegador gerenciado e integração de proxy de aplicativo <!-- 1287310 -->
O Navegador Gerenciado do Intune agora pode ser integrado ao serviço de Proxy de aplicativo do Azure AD para permitir que os usuários acessem os sites da Web internos, mesmo quando estão trabalhando remotamente. Os usuários do navegador simplesmente inserem a URL normalmente e o Managed Browser encaminha a solicitação através do gateway Web do proxy de aplicativo. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](../apps/app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Novas definições de configuração de aplicativos para o Intune Managed Browser <!-- 682951 -->
Nesta versão, adicionamos configurações adicionais para o aplicativo Intune Managed Browser para iOS e Android. Agora você pode usar uma política de configuração de aplicativo para configurar a página inicial padrão e os indicadores do navegador.
Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](../apps/app-configuration-managed-browser.md)

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Configurações do BitLocker para Windows 10  <!-- 951707 -->
Agora você pode definir as configurações do BitLocker para dispositivos Windows 10 usando um novo perfil de dispositivo do Intune. Por exemplo, você pode exigir que os dispositivos sejam criptografados e também definir outras configurações que são aplicadas quando o BitLocker é ativado.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](../protect/endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
Nesta versão, adicionamos novas configurações para o perfil de restrição de dispositivo do Windows 10 nas seguintes categorias:

- Windows Defender
- Celular e conectividade
- Experiência na tela bloqueada
- Privacidade
- Pesquisar
- Destaque do Windows
- Navegador Microsoft Edge

Para obter mais informações sobre as configurações do Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior](../configuration/device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Agora o aplicativo Portal da Empresa para Android tem uma nova experiência de usuário final para as Políticas de Proteção do Aplicativo <!--1305217-->
Com base nos comentários dos clientes, modificamos o aplicativo de Portal da Empresa para Android mostrar um botão **Acessar Conteúdo da Empresa**. A intenção é impedir que os usuários finais passem desnecessariamente pelo processo de inscrição quando eles só precisam acessar os aplicativos que dão suporte a Políticas de Proteção do Aplicativo, um recurso de gerenciamento de aplicativo móvel do Intune. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nova ação de menu para remover o Portal da Empresa com facilidade <!--1164569-->
De acordo com os comentários dos usuários, o aplicativo do Portal da Empresa para Android adicionou uma nova ação de menu para iniciar a remoção do Portal da Empresa por meio do dispositivo. Esta ação remove o dispositivo do gerenciamento do Intune para que o aplicativo possa ser removido do dispositivo pelo usuário. Veja essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md) e na [documentação do usuário final do Android](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Aprimoramentos à sincronização de aplicativo com a Atualização do Windows 10 para Criadores <!--676505-->
O aplicativo do Portal da Empresa para Windows 10 agora iniciará automaticamente uma sincronização para solicitações de instalação de aplicativo em dispositivos com a Atualização do Windows 10 para Criadores (versão 1703). Isso reduzirá o problema de atraso das instalações de aplicativos durante o estado de "Sincronização Pendente". Além disso, os usuários poderão iniciar manualmente uma sincronização de dentro do aplicativo. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nova experiência orientada para o Portal da Empresa do Windows 10 <!---1058938--->
O aplicativo do Portal da Empresa para o Windows 10 incluirá uma experiência de passo a passo guiado do Intune para dispositivos que não foram identificados nem registrados. A nova experiência fornece instruções passo a passo que guiam o usuário pelo processo de inscrição no Azure Active Directory (exigido para recursos de Acesso Condicional) e inscrição de MDM (exigido para os recursos de gerenciamento de dispositivo). A experiência guiada estará acessível na home page do Portal da Empresa. Os usuários podem continuar a usar o aplicativo se não concluírem o registro e inscrição, mas enfrentarão uma funcionalidade limitada.

Esta atualização só fica visível em dispositivos que executam a Atualização de Aniversário do Windows 10 (build 1607) ou superior. Veja essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Os consoles de administrador do Microsoft Intune e do Acesso Condicional estão disponíveis
Anunciamos a disponibilidade geral do novo Intune nos consoles de administrador do Portal do Azure e do Acesso Condicional. Por meio do Intune no Portal do Azure, agora você pode gerenciar todas as funcionalidades MAM e MDM do Intune em uma única experiência de administrador consolidada e aproveitar o agrupamento e direcionamento do Azure AD. O Acesso Condicional no Azure reúne funcionalidades avançadas no Azure AD e no Intune em um único console unificado. Além disso, de uma experiência administrativa, a migração para a plataforma Azure permite o uso de navegadores modernos.

O Intune agora está visível sem o rótulo **versão prévia** no Portal do Azure em portal.azure.com.

No momento, nenhuma ação é necessária para os clientes existentes, a menos que você tenha recebido uma de uma série de mensagens no centro de mensagens solicitando uma ação de sua parte para que possamos migrar seus grupos. Talvez você também tenha recebido um aviso do centro de mensagens informando que a migração está levando mais tempo devido a bugs no nosso lado. Continuaremos trabalhando incessantemente para migrar os clientes afetados.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Melhorias nos blocos do aplicativo no aplicativo do Portal da Empresa para iOS
Atualizamos o design dos blocos do aplicativo na home page para refletir a cor da identidade visual definida para o Portal da Empresa. Para obter mais informações, consulte [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Seletor de conta agora disponível para o aplicativo do Portal da Empresa para iOS
Os usuários de dispositivos iOS poderão ver nosso novo seletor de conta ao entrarem no Portal da Empresa, caso usem suas contas corporativas ou de estudante para entrar em outros aplicativos da Microsoft. Para saber mais, veja [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

<!-- ########################## -->
## <a name="may-2017"></a>Maio de 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Alterar sua autoridade MDM sem cancelar o registro de dispositivos gerenciados <!--1103950-->
Agora você pode alterar a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. No console do Configuration Manager, [altere a autoridade de MDM](/sccm/mdm/deploy-use/change-mdm-authority) em Definir como Configuration Manager (híbrido), como Microsoft Intune (autônomo) ou vice-versa.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Notificação aprimorada para PINs de inicialização do Samsung Knox <!--1087143-->
Quando os usuários finais precisarem definir um PIN de inicialização em dispositivos Samsung Knox para ficarem em conformidade com a criptografia, a notificação exibida para eles os levará para o local exato no aplicativo de Configurações quando a notificação for tocada.  Anteriormente, a notificação levava o usuário final para a tela de alteração de senha.

### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Suporte para o ASM (Apple School Manager) com iPad compartilhado <!-- 748864, 770395-->

O Intune agora dá suporte ao uso do ASM (Apple School Manager) no lugar do Programa de registro de dispositivos da Apple para fornecer o registro pronto para uso de dispositivos iOS. A integração do ASM é necessária para usar o aplicativo de sala de aula para iPads compartilhados e é necessário para habilitar a sincronização de dados do ASM para o Azure Active Directory por meio da sincronização do Microsoft School Data (SDS). Para obter mais informações, consulte [Habilitar o registro de dispositivo iOS com o Apple School Manager](../enrollment/apple-school-manager-set-up-ios.md).

> [!NOTE]
> A configuração de iPads Compartilhados para trabalhar com o aplicativo Sala de aula exige configurações de Educação do iOS no Azure que ainda não estão disponíveis.  Essa funcionalidade será adicionada em breve.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Fornecer assistência remota para dispositivos Android usando o TeamViewer <!-- 675418 -->

O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, para que você possa fornecer assistência remota aos usuários que executam dispositivos Android. Para obter mais informações, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](../remote-actions/teamviewer-support.md).

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Novas condições de políticas de proteção de aplicativo para MAM <!-- 679864 -->

Agora você pode definir um requisito para o MAM sem os usuários do registro, que impõe as seguintes políticas:

- Versão mínima do aplicativo
- Versão mínima do sistema operacional
- Versão mínima do SDK do aplicativo do Intune do aplicativo de destino (somente iOS)

Esse recurso está disponível no Android e no iOS. O Intune dá suporte à imposição de versão mínima para versões de plataforma do sistema operacional, versões de aplicativos e SDK do aplicativo do Intune. No iOS, os aplicativos que têm o SDK integrado também podem definir uma imposição de versão mínima no nível do SDK. O usuário não poderá acessar o aplicativo direcionado se os requisitos mínimos por meio da política de proteção de aplicativo não forem atendidos nos três diferentes níveis mencionados acima. Neste ponto, o usuário poderá remover sua conta (para aplicativos de várias identidades), fechar o aplicativo ou atualizar a versão do sistema operacional ou do aplicativo.

Defina também outras configurações para fornecer uma notificação sem bloqueio que recomenda uma atualização do sistema operacional ou do aplicativo. Essa notificação pode ser fechada e o aplicativo pode ser usado normalmente.

Para obter mais informações, consulte [Configurações da política de proteção de aplicativo do iOS](../apps/app-protection-policy-settings-ios.md) e [Configurações da política de proteção de aplicativo do Android](../apps/app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Definir as configurações de aplicativo para o Android for Work <!-- 621621 -->
Alguns aplicativos Android da loja dão suporte a opções de configuração gerenciada que permitem a um administrador de TI controlar como um aplicativo é executado no perfil de trabalho. Com o Intune, agora você pode exibir as configurações com suporte em um aplicativo e defini-las no Portal do azure com um designer de configuração ou um editor de JSON. Para obter mais informações, consulte [Usar configurações de aplicativo para o Android for Work](../apps/app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nova funcionalidade de configuração de aplicativos para MAM sem registro <!-- 677969 -->
Agora você pode criar políticas de configuração de aplicativo por meio do MAM sem um canal de registro. Esse recurso é equivalente às políticas de configuração de aplicativo disponíveis na configuração de aplicativo do MDM (gerenciamento de dispositivo móvel). Para obter um exemplo de configuração de aplicativo que usa o MAM sem registro, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](../apps/app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Configurar listas de permissões e bloqueios de URLs para o Managed Browser <!-- 682960 -->
Agora você pode configurar uma lista de permissões e bloqueios de domínios e URLs para o Intune Managed Browser usando definições de configuração de aplicativo no portal do Azure. Essas configurações podem ser definidas independentemente de estarem sendo usadas em um dispositivo gerenciado ou não gerenciado. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](../apps/app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Exibição de assistência técnica da política de proteção de aplicativo <!-- 1069473 -->
Os usuários da assistência técnica de TI agora podem verificar o status da licença do usuário e o status dos aplicativos da política de proteção de aplicativo atribuídos aos usuários na folha Solução de Problemas. Para obter detalhes, consulte [Solução de problemas](./help-desk-operators.md).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Controlar visitas ao site em dispositivos iOS <!-- 723832 -->
Agora você pode controlar quais sites os usuários de dispositivos iOS podem visitar usando um dos dois seguintes métodos:

- Adicione URLs permitidas e bloqueadas usando o filtro de conteúdo da web interno da Apple.

- Permita que apenas sites especificado sejam acessados pelo navegador Safari. Para cada site que você especificar são criados indicadores no Safari.

Para obter mais informações, consulte [Configurações de filtro de conteúdo da Web para dispositivos iOS](../configuration/ios-device-features-settings.md#web-content-filter).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Pré-configurar permissões de dispositivo para os aplicativos do Android for Work <!-- 621614 -->
Para aplicativos implantados em perfis de trabalho de dispositivos Android for Work, agora é possível configurar o estado de permissões em aplicativos individuais.  Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso ao local ou a câmera do dispositivo perguntarão se os usuários aceitam ou recusam as permissões.  Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final será solicitado a conceder a permissão de aplicativo para usar o microfone. Esse recurso permite definir permissões em nome do usuário final.  É possível configurar permissões para a) negar automaticamente sem notificar o usuário; b) aprovar automaticamente sem notificar o usuário ou c) solicitar que o usuário aceite ou recuse. Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](../configuration/device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Definir PIN específico do aplicativo para dispositivos Android for Work <!-- 728976, 1102534 -->
Dispositivos Android 7.0 e superior com um perfil de trabalho gerenciados como um dispositivo Android for Work possibilitam ao administrador definir uma política de senha que se aplica somente aos aplicativos no perfil de trabalho.  As opções incluem:

- Definir apenas uma política de senha em todo o dispositivo – essa é a senha que o usuário deve usar para desbloquear seu dispositivo inteiro.
- Definir apenas uma política de senha de perfil de trabalho – os usuários deverão inserir uma senha sempre que um aplicativo for aberto no perfil de trabalho.
- Definir uma política de dispositivo e de perfil de trabalho – o administrador de TI tem a opção de definir uma política de senha de dispositivo e uma política de senha de perfil de trabalho em diferentes níveis (por exemplo, um PIN de quatro dígitos para desbloquear o dispositivo, mas um PIN de seis dígitos para abrir um aplicativo de trabalho).

Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](../configuration/device-restrictions-android-for-work.md).

> [!NOTE]
> Isso está disponível somente no Android 7.0 e superior.  Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou optar por combinar os dois PINs definidos no mais forte dos dois.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Novas configurações para dispositivos Windows 10 <!-- 978585 -->
Adicionamos novas [configurações de restrição de dispositivos Windows](../configuration/device-restrictions-windows-10.md) que controlam recursos como vídeos sem fio, descoberta de dispositivo, alternância de tarefas e mensagens de erro do cartão SIM.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Atualizações da configuração de certificado <!-- 918991 and 823198 -->
Ao criar um perfil de certificado SCEP, em <strong>Formato do nome da entidade</strong>, a opção <strong>Personalizado</strong> está disponível para dispositivos iOS, Android e Windows. Antes dessa atualização, o campo <strong>Personalizado</strong> estava disponível apenas para dispositivos iOS. Para obter mais informações, consulte [Criar perfil de certificado SCEP](../protect/certificates-profile-scep.md).

Ao criar um perfil de certificado PKCS, em **Nome alternativo da entidade**, o **Atributo personalizado do Azure AD** está disponível. A opção **Departamento** fica disponível quando você seleciona **Atributo personalizado do Azure AD**. Para obter mais informações, confira [Criar um perfil de certificado PKCS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Configurar vários aplicativos que podem ser executados quando um dispositivo Android está no modo de quiosque <!-- 662059 -->
Anteriormente, quando um dispositivo Android estava no modo de quiosque, era possível configurar apenas um aplicativo que tinha permissão para ser executado. Agora é possível configurar vários aplicativos usando a ID do aplicativo, a URL da loja ou selecionando um aplicativo Android já gerenciado. Para obter mais informações, consulte [Configurações do modo de quiosque](../configuration/device-restrictions-android.md#kiosk).

<!-- ########################## -->
## <a name="april-2017"></a>Abril de 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Suporte para gerenciamento do aplicativo Sala de Aula da Apple
Agora você pode gerenciar o aplicativo Sala de Aula de iOS em iPads. Configure o aplicativo Sala de Aula no iPad dos professores com os dados corretos de sala e de aluno, e configure os iPads do aluno registrados para uma sala, para que você possa controlá-los usando o aplicativo.
Para obter detalhes, confira [Definir as configurações de educação do iOS](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Suporte para opções de configuração gerenciada para aplicativos Android <!-- 621621 -->
Agora, os aplicativos Android na Play Store, que são compatíveis com opções de configuração gerenciada, podem ser configurados pelo Intune.  Esse recurso permite que a TI exiba a lista de valores de configuração que têm suporte por um aplicativo e fornece uma interface do usuário interativa, de primeira classe para permitir que esses valores sejam configurados.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nova política de Android para PINs complexos <!-- 722069 -->
Agora, você pode definir um tipo de [senha](../configuration/device-restrictions-android.md#password) obrigatória como Numérico complexo em um perfil de dispositivo Android para dispositivos que executam o Android 5.0 e posterior.  Use essa configuração para impedir que os usuários dos dispositivos criem um PIN que contenha números consecutivos ou repetições, como 1111 ou 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Suporte adicional para dispositivos Android for Work
- **Gerencie as configurações de perfil de trabalho e senha** <!-- 612808 -->

  Agora, essa nova política de restrição para dispositivo Android for Work lhe permite gerenciar as configurações de perfil de trabalho e senha nos dispositivos Android for Work que você gerencia.

- **Permitir o compartilhamento de dados entre perfis pessoais e de trabalho** <!-- 1045102 -->

Agora, essa política de restrição de dispositivo do Android for Work possui novas opções para ajudar você a configurar o compartilhamento de dados entre perfis pessoais e de trabalho.

- **Restrinja “copiar e colar” entre perfis de trabalho e pessoais** <!-- 1046094 -->

  Agora, um novo perfil de dispositivo personalizado para dispositivos Android for Work lhe permite restringir se são permitidas ações de copiar e colar entre aplicativos pessoais e de trabalho.

Para saber mais, confira [Restrições de dispositivo para Android for Work](../configuration/device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Atribua aplicativos LOB a dispositivos iOS e Android <!-- 1057568 -->
Agora, você pode atribuir aplicativos LOB (linha de negócios) para [iOS](../apps/lob-apps-ios.md) (arquivos .ipa) e [Android](../apps/lob-apps-android.md) (arquivos .apk) a usuários ou dispositivos.


### <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Novas políticas de dispositivos para iOS <!-- 723774, 723815, 723826, 723830 -->
- **Aplicativos na Tela inicial** – controla quais aplicativos os usuários veem na [Tela inicial de seus dispositivos iOS](../configuration/ios-device-features-settings.md#home-screen-layout). Essa política altera o layout da Tela inicial, mas não implanta nenhum aplicativo.

- **Conexões com dispositivos AirPrint** – controla a quais [dispositivos AirPrint](../configuration/ios-device-features-settings.md#airprint) (impressoras de rede) os usuários finais do dispositivo iOS podem se conectar.

- **Conexões com dispositivos AirPlay** – controla a quais [dispositivos AirPlay](../configuration/ios-device-features-settings.md) (como a Apple TV) os usuários finais do dispositivo iOS podem se conectar.

- **Mensagem de tela de bloqueio personalizado** – configura uma mensagem personalizada que os usuários verão na tela de bloqueio de seu dispositivo iOS, que substitui a mensagem de tela de bloqueio padrão. Para obter mais informações, consulte [Ativar o modo perdido em dispositivos iOS](../remote-actions/device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Restrinja as notificações por push para aplicativos iOS <!-- 723767 -->
Agora, em um perfil de restrição de dispositivo do Intune, você pode configurar os seguintes [ajustes de notificação](../configuration/ios-device-features-settings.md#app-notifications) para dispositivos iOS:

- Ative ou desative completamente a notificação de um aplicativo especificado.
- Ative ou desative a notificação no centro de notificações para um aplicativo especificado.
- Especifique o tipo de alerta, **nenhum**, **faixa** ou **alerta modal**.
- Especifique se são permitidos selos para esse aplicativo.
- Especifique se são permitidos sons de notificação.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Configure aplicativos iOS para serem executados de forma independente no modo de aplicativo único <!-- 737837 -->
Agora você pode usar um perfil de dispositivo do Intune para configurar dispositivos iOS para executar aplicativos especificados no [modo autônomo de aplicativo único](../configuration/device-restrictions-ios.md#autonomous-single-app-mode). Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo. Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Configure domínios confiáveis para email e navegação em dispositivos iOS <!-- 723765 -->
Agora, em um perfil de restrição de dispositivo iOS, você pode configurar os seguintes [ajustes de domínio](../configuration/device-restrictions-ios.md#domains):

- **Domínios de email desmarcados** – Emails que o usuário envia ou recebe que não coincidam com os domínios que você especificar aqui serão marcados como não confiáveis.

- **Domínios da web gerenciados** – Documentos baixados de URLs que você especificar aqui serão considerados gerenciados (somente Safari).  

- **Domínios de preenchimento automático de senha do Safari** – Os usuários podem salvar senhas no Safari somente de URLs que correspondam aos padrões que você especificar aqui. Para usar essa configuração, o dispositivo deve estar no modo supervisionado e não configurado para vários usuários. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Aplicativos VPP disponíveis no Portal da Empresa iOS <!-- 748782 -->
Agora você pode atribuir aplicativos iOS adquiridos com base em volume (VPP) como instalações **Disponíveis** para usuários finais. Os usuários finais precisarão de uma conta na Apple Store para instalar o aplicativo.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Sincronize livros eletrônicos da Apple VPP Store <!-- 800878 -->
Agora você pode [sincronizar os livros](../apps/vpp-apps-ios.md) adquiridos na loja de programa adquirido por volume da Apple com o Intune e atribuí-los aos usuários.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Gerenciamento de vários usuários para dispositivos Samsung Knox Standard <!-- 971988 -->
Agora há suporte para dispositivos que executam o Samsung Knox Standard para o [gerenciamento de vários usuários](../enrollment/android-enroll.md) pelo Intune. Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure Active Directory e o dispositivo é gerenciado centralmente independentemente de estar ou não em uso.  Quando os usuários finais entram, eles têm acesso a aplicativos e obtêm as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Configurações adicionais de restrição de dispositivos no Windows <!-- 818566 -->
Adicionamos suporte para outras [configurações de restrição de dispositivos no Windows](../configuration/device-restrictions-windows-10.md), como suporte adicional ao navegador Microsoft Edge, personalização da tela de bloqueio de dispositivo, personalizações do menu Iniciar, papel de parede definido por pesquisa do Destaque do Windows e configuração do proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Suporte a vários usuários para atualização do Windows 10 para criadores <!-- 822547 -->
Adicionamos suporte para o [gerenciamento de vários usuários](../enrollment/windows-enroll.md) para dispositivos que executam a atualização do Windows 10 para criadores e estão ingressados no domínio do Azure Active Directory. Isso significa que, quando usuários padrão diferentes fizerem logon no dispositivo com suas credenciais do Azure AD, eles receberão quaisquer aplicativos e políticas que foram atribuídos ao seu nome de usuário. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Novo Início para PCs com Windows 10<!-- 1004830 -->
Agora há uma [nova ação de dispositivo para começar do zero](../remote-actions/device-fresh-start.md) disponível em PCs com Windows 10.  Quando você executa esta ação, quaisquer aplicativos que foram instalados no computador são removidos e o PC é atualizado automaticamente para a versão mais recente do Windows. Isso pode ser usado para ajudar a remover aplicativos de OEM pré-instalados que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Caminhos de atualização adicionais do Windows 10 <!-- 903672 -->
Agora você pode criar uma [política de atualização de edição para atualizar os dispositivos](../configuration/edition-upgrade-configure-windows-10.md) para as seguintes edições adicionais do Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Registro em massa de dispositivos com Windows 10 <!-- 747607 -->
Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer). Para habilitar o [registro em massa do MDM](../enrollment/windows-bulk-enroll.md) para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa. Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para a entrada de seus usuários do Azure AD.  Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários. Não há suporte para cenários de autoatendimento e de Portal da Empresa no momento.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Novas configurações de MAM para PIN e locais de armazenamento gerenciado <!-- 581122, 736644 -->
Agora, duas novas configurações do aplicativo estão disponíveis para ajudá-lo com cenários de gerenciamento do aplicativo móvel (MAM):

- **Desabilite o PIN do aplicativo quando o PIN do dispositivo é gerenciado** – Detecta se um PIN do dispositivo está presente no dispositivo registrado e, nesse caso, ignora o PIN do aplicativo disparado pelas políticas de proteção de aplicativo. Essa configuração permitirá uma redução no número de vezes que uma solicitação de PIN é exibida para os usuários que abrem um aplicativo habilitado para MAM em um dispositivo registrado. Esse recurso está disponível para Android e iOS.

- **Selecione quais dados corporativos de serviços de armazenamento pode ser salvos em** – Permite-lhe especificar em quais locais de armazenamento deseja salvar os dados corporativos. Os usuários podem salvar nos serviços de localização de armazenamento selecionados, o que significa que todos os outros serviços de localização de armazenamento não listados serão bloqueados.

  Lista de serviços de localização de armazenamento com suporte:

  - OneDrive
  - Business SharePoint Online
  - Armazenamento local

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portal de solução de problemas de suporte técnico <!-- 907448 -->
O novo [portal de solução de problemas](../help-desk-operators.md) permite que operadores de suporte técnico e administradores do Intune vejam usuários e seus dispositivos e executem tarefas para resolver problemas técnicos do Intune.

<!-- ########################## -->
## <a name="march-2017"></a>Março de 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Suporte para o Modo Perdido do iOS <!--431695-->
Para o iOS 9.3 e dispositivos posteriores, o Intune adicionou suporte para o **Modo Perdido**. Agora, você pode bloquear um dispositivo para impedir o uso e exibir uma mensagem e número de telefone de contato da tela de bloqueio do dispositivo.

O usuário final não conseguirá desbloquear o dispositivo até que um administrador desative o Modo Perdido. Quando o Modo Perdido é habilitado, você pode usar a ação **Localizar dispositivo** para exibir a localização geográfica do dispositivo em um mapa no console do Intune.

O dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.

Para obter mais informações, consulte [O que é gerenciamento de dispositivos do Microsoft Intune](../remote-actions/device-management.md)?

### <a name="improvements-to-device-actions-report---677150--"></a>Aprimoramentos para o relatório de Ações de Dispositivo <!--677150-->
Fizemos aprimoramentos no relatório de Ações de Dispositivo para melhorar o desempenho. Além disso, agora você pode filtrar o relatório por estado. Por exemplo, você pode filtrar o relatório para mostrar somente as ações do dispositivo que foram concluídas.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](../apps/apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Atribuir aplicativos LOB para usuários com dispositivos não registrados <!--748823-->
Agora você pode atribuir aplicativos de linhas de negócios da loja para os usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo do usuário não estiver registrado no Intune, ele deverá ir para o site Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.

### <a name="new-compliance-reports---846671--"></a>Novos relatórios de conformidade <!--846671-->
Agora você tem relatórios de conformidade que dão a postura de conformidade de dispositivos na sua empresa e permitem que você solucione rapidamente problemas relacionados à conformidade encontrados pelos usuários. Você pode exibir informações sobre

- Estado de conformidade geral de dispositivos
- Estado de conformidade para uma configuração individual
- Estado de conformidade para uma política individual

Você também pode usar esses relatórios para uma busca detalhada em um dispositivo individual para exibir as configurações específicas e as políticas que afetam esse dispositivo.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->
Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no Portal do Azure. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.


<!-- ########################## -->
## <a name="february-2017"></a>Fevereiro de 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Capacidade de restringir o registro de dispositivos móveis <!--747600, 795782-->
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.

- Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.  
- Apenas para iOS e Android, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](../enrollment/device-enrollment.md).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Exibir todas as ações em dispositivos gerenciados <!--677150-->
Um novo relatório __Ações de Dispositivo__ mostra quem realizou ações remotas como redefinição de fábrica em dispositivos e, além disso, mostra o status dessas ações. Consulte [O que é o gerenciamento de dispositivos?](../remote-actions/device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->
Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

### <a name="custom-app-categories---748805--"></a>Categorias de aplicativo personalizadas <!--748805-->
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](../apps/apps-add.md).

### <a name="display-device-categories---814654--"></a>Exibir categorias de dispositivos <!--814654-->
Agora você pode exibir a categoria de dispositivo como uma coluna na lista de dispositivos. Você também pode editar a categoria da seção de propriedades da folha de propriedades do dispositivo. Consulte [como adicionar um aplicativo ao Intune](../apps/apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Definir as configurações do Windows Update para Empresas <!--776716-->

O Windows como um Serviço é a nova maneira de fornecer atualizações para o Windows 10. Começando no Windows 10, quaisquer novas Atualizações de Recursos e Atualizações de Qualidade terão o conteúdo de todas as atualizações anteriores. Isso significa que contanto que você tenha instalado a atualização mais recente, sabe que seus dispositivos do Windows 10 estão completamente atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Usando o Windows Update para Empresas, você pode simplificar a experiência de gerenciamento da atualização para que não precise aprovar as atualizações individuais para os grupos de dispositivos. Você ainda pode gerenciar os riscos em seus ambientes configurando uma estratégia de distribuição de atualização e o Windows Update irá assegurar que as atualizações sejam instaladas no momento certo. O Microsoft Intune fornece a capacidade de definir as configurações da atualização nos dispositivos e oferece a capacidade de adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam o Windows Update diretamente para as atualizações. Use o Intune para configurar e gerenciar os **anéis de atualização do Windows 10**. Um anel de atualização contém um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas. Para obter detalhes, consulte [Definir as configurações do Windows Update para Empresas](../protect/windows-update-for-business-configure.md).