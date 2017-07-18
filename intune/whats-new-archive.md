---
title: Novidades do Microsoft Intune nos meses anteriores
titleSuffix: Intune on Azure
description: "Veja comunicados mais antigos da página de novidades do Intune"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 06/08/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cf2322a4009310e5dd561693ea6b3cdb97ab6e28
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Novidades do Microsoft Intune – meses anteriores
<a id="whats-new-in-the-microsoft-intune---previous-months" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## Abril de 2017
<a id="april-2017" class="xliff"></a>

### Suporte para gerenciamento do aplicativo Sala de Aula da Apple
<a id="support-for-managing-the-apple-classroom-app" class="xliff"></a>

Agora você pode gerenciar o aplicativo Sala de Aula de iOS em iPads. Configure o aplicativo Sala de Aula no iPad dos professores com os dados corretos de sala e de aluno, e configure os iPads do aluno registrados para uma sala, para que você possa controlá-los usando o aplicativo.
Para obter detalhes, confira [Definir as configurações de educação do iOS](education-settings-configure-ios.md).

### Suporte para opções de configuração gerenciada para aplicativos Android <!-- 621621 -->
<a id="support-for-managed-configuration-options-for-android-apps----621621---" class="xliff"></a>

Agora, os aplicativos Android na Play Store que oferecem suporte a opções de configuração gerenciada podem ser configurados pelo Intune.  Esse recurso permite que a TI exiba a lista de valores de configuração que têm suporte por um aplicativo e fornece uma interface do usuário interativa, de primeira classe para permitir que esses valores sejam configurados.

### Nova política de Android para PINs complexos <!-- 722069 -->
<a id="new-android-policy-for-complex-pins----722069---" class="xliff"></a>

Agora, você pode definir um tipo de [senha](device-restrictions-android.md#password) obrigatória como Numérico complexo em um perfil de dispositivo Android para dispositivos que executam o Android 5.0 e posterior.  Use essa configuração para impedir que os usuários dos dispositivos criem um PIN que contenha números consecutivos ou repetições, como 1111 ou 1234.

### Suporte adicional para dispositivos Android for Work
<a id="additional-support-for-android-for-work-devices" class="xliff"></a>

- **Gerencie as configurações de perfil de trabalho e senha**<!-- 612808 -->

  Agora, essa nova política de restrição para dispositivo Android for Work lhe permite gerenciar as configurações de perfil de trabalho e senha nos dispositivos Android for Work que você gerencia.

- **Permita o compartilhamento de dados entre perfis pessoais e de trabalho** <!-- 1045102 -->

Agora, essa política de restrição de dispositivo do Android for Work possui novas opções para ajudar você a configurar o compartilhamento de dados entre perfis pessoais e de trabalho.

- **Restrinja “copiar e colar” entre perfis de trabalho e pessoais**<!-- 1046094 -->

  Agora, um novo perfil de dispositivo personalizado para dispositivos Android for Work lhe permite restringir se são permitidas ações de copiar e colar entre aplicativos pessoais e de trabalho.

Para saber mais, confira [Restrições de dispositivo para Android for Work](device-restrictions-android-for-work.md).

### Atribua aplicativos LOB a dispositivos iOS e Android <!-- 1057568 -->
<a id="assign-lob-apps-to-ios-and-android-devices----1057568---" class="xliff"></a>

Agora, você pode atribuir aplicativos LOB (linha de negócios) para [iOS](lob-apps-ios.md) (arquivos .ipa) e [Android](lob-apps-android.md) (arquivos .apk) a usuários ou dispositivos.

###  Novas políticas de dispositivos para iOS <!-- 723774, 723815, 723826, 723830 -->
<a id="new-device-policies-for-ios----723774-723815-723826-723830---" class="xliff"></a>

- **Aplicativos na Tela inicial** – controla quais aplicativos os usuários veem na [Tela inicial de seus dispositivos iOS](home-screen-settings-ios.md). Essa política altera o layout da Tela inicial, mas não implanta nenhum aplicativo.

- **Conexões com dispositivos AirPrint** – controla a quais [dispositivos AirPrint](air-print-settings-ios-macos.md) (impressoras de rede) os usuários finais do dispositivo iOS podem se conectar.

- **Conexões com dispositivos AirPlay** – controla a quais [dispositivos AirPlay](airplay-settings-ios.md) (como a Apple TV) os usuários finais do dispositivo iOS podem se conectar.

- **Mensagem de tela de bloqueio personalizado** – configura uma mensagem personalizada que os usuários verão na tela de bloqueio de seu dispositivo iOS, que substitui a mensagem de tela de bloqueio padrão. Para obter mais informações, consulte [Ativar o modo perdido em dispositivos iOS](device-lost-mode.md)

### Restrinja as notificações por push para aplicativos iOS <!-- 723767 -->
<a id="restrict-push-notifications-for-ios-apps----723767---" class="xliff"></a>

Agora, em um perfil de restrição de dispositivo do Intune, você pode configurar os seguintes [ajustes de notificação](app-notification-settings-ios.md) para dispositivos iOS:

- Ative ou desative completamente a notificação de um aplicativo especificado.
- Ative ou desative a notificação no centro de notificações para um aplicativo especificado.
- Especifique o tipo de alerta, **nenhum**, **faixa** ou **alerta modal**.
- Especifique se são permitidos selos para esse aplicativo.
- Especifique se são permitidos sons de notificação.

### Configure aplicativos iOS para serem executados de forma independente no modo de aplicativo único <!-- 737837 -->
<a id="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---" class="xliff"></a>

Agora você pode usar um perfil de dispositivo do Intune para configurar dispositivos iOS para executar aplicativos especificados no [modo autônomo de aplicativo único](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo. Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### Configure domínios confiáveis para email e navegação em dispositivos iOS <!-- 723765 -->
<a id="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---" class="xliff"></a>

Agora, em um perfil de restrição de dispositivo iOS, você pode configurar os seguintes [ajustes de domínio](device-restrictions-ios.md#domains):

- **Domínios de email desmarcados** – Emails que o usuário envia ou recebe que não coincidam com os domínios que você especificar aqui serão marcados como não confiáveis.

- **Domínios da web gerenciados** – Documentos baixados de URLs que você especificar aqui serão considerados gerenciados (somente Safari).  

- **Domínios de preenchimento automático de senha do Safari** – Os usuários podem salvar senhas no Safari somente de URLs que correspondam aos padrões que você especificar aqui. Para usar essa configuração, o dispositivo deve estar no modo supervisionado e não configurado para vários usuários. (iOS 9.3+)


### Aplicativos VPP disponíveis no Portal da empresa iOS <!-- 748782 -->
<a id="vpp-apps-available-in-ios-company-portal----748782---" class="xliff"></a>

Agora você pode atribuir aplicativos iOS adquiridos com base em volume (VPP) como instalações **Disponíveis** para usuários finais. Os usuários finais precisarão de uma conta na Apple Store para instalar o aplicativo.

### Sincronize livros eletrônicos da Apple VPP Store <!-- 800878 -->
<a id="synchronize-ebooks-from-apple-vpp-store----800878---" class="xliff"></a>

Agora você pode [sincronizar os livros](vpp-apps-ios.md) adquiridos na loja de programa adquirido por volume da Apple com o Intune e atribuí-los aos usuários.

### Gerenciamento de vários usuários para dispositivos Samsung KNOX Standard <!-- 971988 -->
<a id="multi-user-management-for-samsung-knox-standard-devices----971988---" class="xliff"></a>

Agora há suporte para dispositivos que executam o Samsung KNOX Standard para o [gerenciamento de vários usuários](android-enroll.md) pelo Intune. Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure Active Directory e o dispositivo é gerenciado centralmente independentemente de estar ou não em uso.  Quando os usuários finais entram, eles têm acesso a aplicativos e obtêm as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

### Configurações adicionais de restrição de dispositivos no Windows <!-- 818566 -->
<a id="additional-windows-device-restriction-settings----818566---" class="xliff"></a>

Adicionamos suporte para outras [configurações de restrição de dispositivos no Windows](device-restrictions-windows-10.md), como suporte adicional ao navegador Edge, personalização da tela de bloqueio de dispositivo, personalizações do menu Iniciar, papel de parede definido por pesquisa do Windows Spotlight e configuração do proxy.

### Suporte a vários usuários para atualização do Windows 10 para criadores <!-- 822547 -->
<a id="multi-user-support-for-windows-10-creators-update----822547---" class="xliff"></a>

Adicionamos suporte para o [gerenciamento de vários usuários](windows-enroll.md) para dispositivos que executam a atualização do Windows 10 para criadores e estão ingressados no domínio do Azure Active Directory. Isso significa que, quando usuários padrão diferentes fizerem logon no dispositivo com suas credenciais do Azure AD, eles receberão quaisquer aplicativos e políticas que foram atribuídos ao seu nome de usuário. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.

### Começar do zero para PCs com Windows 10<!-- 1004830 -->
<a id="fresh-start-for-windows-10-pcs---1004830---" class="xliff"></a>

Agora há uma [nova ação de dispositivo para começar do zero](device-fresh-start.md) disponível em PCs com Windows 10.  Quando você executa esta ação, quaisquer aplicativos que foram instalados no computador são removidos e o PC é atualizado automaticamente para a versão mais recente do Windows. Isso pode ser usado para ajudar a remover aplicativos de OEM pré-instalados que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada.

### Caminhos de atualização adicionais do Windows 10 <!-- 903672 -->
<a id="additional-windows-10-upgrade-paths----903672---" class="xliff"></a>

Agora você pode criar uma [política de atualização de edição para atualizar os dispositivos](edition-upgrade-configure-windows-10.md) para as seguintes edições adicionais do Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### Registro em massa de dispositivos com Windows 10 <!-- 747607 -->
<a id="bulk-enroll-windows-10-devices----747607---" class="xliff"></a>

Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer). Para habilitar o [registro em massa do MDM](windows-bulk-enroll.md) para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa. Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para logon de seus usuários do Azure AD.  Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários. Não há suporte para cenários de autoatendimento e de Portal da Empresa no momento.

### Novas configurações de MAM para PIN e locais de armazenamento gerenciado <!-- 581122, 736644 -->
<a id="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---" class="xliff"></a>

Agora, duas novas configurações do aplicativo estão disponíveis para ajudá-lo com cenários de gerenciamento do aplicativo móvel (MAM):

- **Desabilite o PIN do aplicativo quando o PIN do dispositivo é gerenciado** – Detecta se um PIN do dispositivo está presente no dispositivo registrado e, nesse caso, ignora o PIN do aplicativo disparado pelas políticas de proteção de aplicativo. Essa configuração permitirá uma redução no número de vezes que uma solicitação de PIN é exibida para os usuários que abrem um aplicativo habilitado para MAM em um dispositivo registrado. Esse recurso está disponível para Android e iOS.

- **Selecione quais dados corporativos de serviços de armazenamento pode ser salvos em** – Permite-lhe especificar em quais locais de armazenamento deseja salvar os dados corporativos. Os usuários podem salvar nos serviços de localização de armazenamento selecionados, o que significa que todos os outros serviços de localização de armazenamento não listados serão bloqueados.

  Lista de serviços de localização de armazenamento com suporte:

  - OneDrive
  - Business SharePoint Online
  - Armazenamento local

### Portal de solução de problemas de suporte técnico <!-- 907448 -->
<a id="help-desk-troubleshooting-portal----907448---" class="xliff"></a>

O novo [portal de solução de problemas](help-desk-operators.md) permite que operadores de suporte técnico e administradores do Intune vejam usuários e seus dispositivos e executem tarefas para resolver problemas técnicos do Intune.

## Março de 2017
<a id="march-2017" class="xliff"></a>

### Suporte para o Modo Perdido do iOS<!--431695-->
<a id="support-for-ios-lost-mode---431695--" class="xliff"></a>

Para o iOS 9.3 e dispositivos posteriores, o Intune adicionou suporte para o **Modo Perdido**. Agora, você pode bloquear um dispositivo para impedir o uso e exibir uma mensagem e número de telefone de contato da tela de bloqueio do dispositivo.

O usuário final não conseguirá desbloquear o dispositivo até que um administrador desative o Modo Perdido. Quando o Modo Perdido é habilitado, você pode usar a ação **Localizar dispositivo** para exibir a localização geográfica do dispositivo em um mapa no console do Intune.

O dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.

Para obter mais informações, consulte [O que é gerenciamento de dispositivos do Microsoft Intune](device-management.md)?

### Aprimoramentos para o relatório de Ações de Dispositivo <!--677150-->
<a id="improvements-to-device-actions-report---677150--" class="xliff"></a>

Fizemos aprimoramentos no relatório de Ações de Dispositivo para melhorar o desempenho. Além disso, agora você pode filtrar o relatório por estado. Por exemplo, você pode filtrar o relatório para mostrar somente as ações do dispositivo que foram concluídas.

### Categorias de aplicativo personalizadas <!--748805-->
<a id="custom-app-categories---748805--" class="xliff"></a>

Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### Atribuir aplicativos LOB para usuários com dispositivos não registrados <!--748823-->
<a id="assign-lob-apps-to-users-with-unenrolled-devices---748823--" class="xliff"></a>

Agora você pode atribuir aplicativos de linhas de negócios da loja para os usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo do usuário não estiver registrado no Intune, ele deverá ir para o site Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.

### Novos relatórios de conformidade <!--846671-->
<a id="new-compliance-reports---846671--" class="xliff"></a>

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

### Acesso direto aos cenários de registro da Apple <!--951869-->
<a id="direct-access-to-apple-enrollment-scenarios---951869--" class="xliff"></a>

Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.


## Fevereiro de 2017
<a id="february-2017" class="xliff"></a>

### Capacidade de restringir o registro de dispositivos móveis <!--747600, 795782-->
<a id="ability-to-restrict-mobile-device-enrollment---747600-795782--" class="xliff"></a>
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.

* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.  
* Apenas para iOS e Android, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).

### Exibir todas as ações em dispositivos gerenciados <!--677150-->
<a id="view-all-actions-on-managed-devices---677150--" class="xliff"></a>
Um novo relatório __Ações de Dispositivo__ mostra quem realizou ações remotas como redefinição de fábrica em dispositivos e, além disso, mostra o status dessas ações. Consulte [O que é o gerenciamento de dispositivos?](device-management.md).

### Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->
<a id="non-managed-devices-can-access-assigned-apps---664691--" class="xliff"></a>
Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

### Categorias de aplicativo personalizadas <!--748805-->
<a id="custom-app-categories---748805--" class="xliff"></a>
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### Exibir categorias de dispositivos <!--814654-->
<a id="display-device-categories---814654--" class="xliff"></a>
Agora você pode exibir a categoria de dispositivo como uma coluna na lista de dispositivos. Você também pode editar a categoria da seção de propriedades da folha de propriedades do dispositivo. Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### Definir as configurações do Windows Update para Empresas <!--776716-->
<a id="configure-windows-update-for-business-settings---776716--" class="xliff"></a>

O Windows como um Serviço é a nova maneira de fornecer atualizações para o Windows 10. Começando no Windows 10, quaisquer novas Atualizações de Recursos e Atualizações de Qualidade terão o conteúdo de todas as atualizações anteriores. Isso significa que contanto que você tenha instalado a atualização mais recente, sabe que seus dispositivos do Windows 10 estão completamente atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Usando o Windows Update para Empresas, você pode simplificar a experiência de gerenciamento da atualização para que não precise aprovar as atualizações individuais para os grupos de dispositivos. Você ainda pode gerenciar os riscos em seus ambientes configurando uma estratégia de distribuição de atualização e o Windows Update irá assegurar que as atualizações sejam instaladas no momento certo. O Microsoft Intune fornece a capacidade de definir as configurações da atualização nos dispositivos e oferece a capacidade de adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam o Windows Update diretamente para as atualizações. Use o Intune para configurar e gerenciar os **anéis de atualização do Windows 10**. Um anel de atualização contém um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas. Para obter detalhes, consulte [Definir as configurações do Windows Update para Empresas](windows-update-for-business-configure.md).

## Janeiro de 2017
<a id="january-2017" class="xliff"></a>

### Atribuir aplicativos de linha de negócios independentemente de os dispositivos estarem registrados ou não <!--748823-->
<a id="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--" class="xliff"></a>
Agora você pode atribuir aplicativos de linhas de negócios e aplicativos da loja aos usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo dos usuários não estiver registrado no Intune, eles deverão acessar o site do Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa. Consulte [O que é o gerenciamento de aplicativo](app-management.md).

### Resolva o problema em que os dispositivos iOS estão inativos ou o console de administração não pode se comunicar com eles
<a id="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them" class="xliff"></a>
Quando os dispositivos dos usuários perdem contato com o Intune, você pode fornecer novas etapas de solução de problemas para ajudá-los a recuperar o acesso aos recursos da empresa. Consulte [Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles](enrollment-troubleshoot.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## Dezembro de 2016 (versão inicial)
<a id="december-2016-initial-release" class="xliff"></a>

### Integração do gerenciamento de despesas de telecomunicações no portal do Azure<!--747605-->
<a id="telecom-expense-management-integration-in-azure-portal--747605--" class="xliff"></a>
Agora estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com). Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).

- Implantar e gerenciar aplicativos de um repositório para dispositivos iOS, Android e Windows
- Implantar e gerenciar aplicativos LOB (linha de negócios) para dispositivos iOS, Android e Windows
- Implantar e gerenciar aplicativos adquiridos de volume para dispositivos iOS e Windows
- Implantar e gerenciar aplicativos Web para dispositivos Android, iOS e Windows
- Perfis de configuração do aplicativo gerenciado por iOS
- Configurar políticas de proteção de aplicativo e implantar aplicativos de linha de negócios em dispositivos que não são registrados com o Intune
- Perfis VPN, VPN por aplicativo, Wi-Fi, email e perfis de certificado
- Políticas de conformidade
- Acesso condicional para Azure AD
- Acesso condicional para Exchange Local
- Registro de dispositivo
- Controle de acesso baseado em função

## Recursos preteridos no Portal do Azure
<a id="deprecated-features-in-the-azure-portal" class="xliff"></a>

### Suporte para examinar de linha por linha dos identificadores de hardware
<a id="support-for-row-by-row-review-of-hardware-identifiers" class="xliff"></a>
O Portal do Azure não dá suporte à analise de linha por linha de identificadores de hardware para números IMEI e números de série da Apple. No console do Intune clássico, você pode importar detalhes de um arquivo valores separados por vírgulas (.csv) e substituir os detalhes existentes pelos identificadores de hardware individuais. O Portal do Azure apresenta uma única opção simplificada que automaticamente substitui detalhes para todos os identificadores de hardware ou ignora detalhes novos para identificadores existentes.

#### Como isso afeta você
<a id="how-this-affects-you" class="xliff"></a>
No Portal do Azure, você não poderá decidir, linha por linha, os dispositivos de identidade de equipamentos de móveis internacional (IMEI) para atualizar. O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.

#### Como se preparar para essa alteração
<a id="how-to-get-ready-for-this-change" class="xliff"></a>
Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração. Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.


### Suporte para o padrão perfis de registro de dispositivo corporativo em Apple DEP
<a id="support-for-default-corporate-device-enrollment-profiles-in-apple-dep" class="xliff"></a>
O Portal do Azure não dá suporte para o perfil de registro de dispositivo corporativo "padrão" para números de série do dispositivo do DEP (Programa de registro de dispositivos) da Apple. Essa funcionalidade, disponível no console do Intune clássico, está sendo descontinuada para impedir que os perfis atribuídos acidentalmente. No Portal do Azure, os números de série sincronizados com base em uma conta de DEP da Apple inicialmente não terá nenhum perfil de registro de dispositivo corporativo atribuído.

#### Como isso afeta você
<a id="how-this-affects-you" class="xliff"></a>
No Portal do Azure, você não poderá definir uma política de perfil padrão em todos os dispositivos da Apple. O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.

#### Como se preparar para essa alteração
<a id="how-to-get-ready-for-this-change" class="xliff"></a>
Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração. Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.

### Consulte também
<a id="see-also" class="xliff"></a>
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.