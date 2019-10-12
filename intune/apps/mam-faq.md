---
title: Perguntas frequentes sobre o MAM e a proteção do aplicativo
description: Este artigo fornece respostas para algumas perguntas frequentes sobre o Intune MAM (gerenciamento de aplicativo móvel) e a proteção do aplicativo do Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: erikre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1e77d303b3f9100c688b64feae6ca330d515df1b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724679"
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Perguntas frequentes sobre o MAM e a proteção do aplicativo

Este artigo fornece respostas para algumas perguntas frequentes sobre o Intune MAM (gerenciamento de aplicativo móvel) e a proteção do aplicativo do Intune.

## <a name="mam-basics"></a>Noções básicas sobre o MAM

**O que é o MAM?**<br></br>
[Gerenciamento de aplicativo móvel do Intune](app-lifecycle.md) refere-se ao pacote de recursos de gerenciamento do Intune que permite publicar, enviar por push, configurar, proteger, monitorar e atualizar aplicativos móveis para os usuários.

**Quais são os benefícios da proteção do aplicativo do MAM?**<br></br>
O MAM protege os dados de uma organização em um aplicativo. Com o MAM sem registro (MAM-WE), um aplicativo relacionado ao trabalho ou à escola que contém dados confidenciais pode ser gerenciado em quase todos os dispositivos, incluindo dispositivos pessoais em cenários de BYOD (traga seu próprio dispositivo). Vários aplicativos de produtividade, como os aplicativos do Microsoft Office, podem ser gerenciados pelo Intune MAM. Consulte a lista oficial de [aplicativos gerenciados pelo Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) disponíveis para uso público.

**Quais configurações de dispositivo têm suporte no MAM?**<br></br>
O Intune MAM dá suporte a duas configurações:
- **Intune MDM + MAM**: Os administradores de TI apenas podem gerenciar aplicativos usando o MAM e políticas de proteção do aplicativo em dispositivos registrados no Intune MDM (gerenciamento de dispositivo móvel). Para gerenciar aplicativos usando o MDM + MAM, os clientes devem usar o console do Intune no portal do Azure em https://portal.azure.com.

- **MAM sem registro de dispositivo**: o MAM sem registro de dispositivo, ou MAM-WE, permite que os administradores de TI gerenciem aplicativos usando o MAM e políticas de proteção do aplicativo em dispositivos não registrados no Intune MDM. Isso significa que os aplicativos podem ser gerenciados pelo Intune em dispositivos registrados em provedores de EMM de terceiros. Para gerenciar aplicativos usando o MAM-WE, os clientes deverão usar o console do Intune no portal do Azure em [https://portal.azure.com](https://portal.azure.com). Além disso, os aplicativos podem ser gerenciados pelo Intune em dispositivos registrados com provedores de Gerenciamento de Mobilidade Empresarial (EMM) de terceiros ou não registrados com um MDM.


## <a name="app-protection-policies"></a>Políticas de proteção do aplicativo

**O que são políticas de proteção do aplicativo?**<br></br>
Políticas de proteção do aplicativo são regras que garantem que os dados de uma organização permanecem seguros ou contidos em um aplicativo gerenciado. Uma política pode ser uma regra imposta quando o usuário tenta acessar ou mover dados “corporativos” ou um conjunto de ações proibidas ou monitoradas quando o usuário está no aplicativo.

**Quais são exemplos de políticas de proteção do aplicativo?**<br></br>
Consulte [Android app protection policy settings](app-protection-policy-settings-android.md) (Configurações da política de proteção de aplicativo Android) e [iOS app protection policy settings](app-protection-policy-settings-ios.md) (Configurações da política de proteção de aplicativo iOS) para obter informações detalhadas sobre cada configuração da política de proteção do aplicativo.

**É possível ter políticas MDM e MAM aplicadas ao mesmo usuário ao mesmo tempo em diferentes dispositivos? Por exemplo, se um usuário puder acessar seus recursos de trabalho em sua própria máquina habilitada para MAM, mas também trabalhar e usar um dispositivo gerenciado pelo MDM do Intune. Há alguma restrição a essa ideia?**<br></br>
Se você aplicar uma política de MAM ao usuário sem definir o estado do dispositivo, o usuário receberá a política de MAM em seu próprio dispositivo e no dispositivo gerenciado pelo Intune. Você também pode aplicar uma política de MAM com base no estado gerenciado. Portanto, ao criar uma política de proteção de aplicativo, ao lado de Destino para todos os tipos de aplicativo, selecione Não. Depois, siga um destes procedimentos:
- Aplique uma política de MAM menos rígida a dispositivos gerenciados pelo Intune e uma política de MAM mais restritiva a dispositivos não registrados no MDM.
- Aplique uma política de MAM apenas a dispositivos não registrados.

Saiba mais em [Como monitorar políticas de proteção de aplicativo](app-protection-policies-monitor.md).

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Aplicativos que podem ser gerenciados com políticas de proteção do aplicativo

**Quais aplicativos podem ser gerenciados por políticas de proteção do aplicativo?**<br></br>
Qualquer aplicativo que tenha sido integrado com o [SDK do Aplicativo do Intune](../developer/app-sdk.md) ou encapsulado pela [Ferramenta de Disposição do Aplicativo do Intune](../developer/apps-prepare-mobile-application-management.md) pode ser gerenciado por políticas de proteção do aplicativo do Intune. Consulte a lista oficial de [aplicativos gerenciados pelo Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) disponíveis para uso público.

**Quais são os requisitos de linha de base para usar políticas de proteção do aplicativo em um aplicativo gerenciado pelo Intune?**

- O usuário final deve ter uma conta do AAD (Azure Active Directory). Consulte [Adicionar usuários e conceder permissão administrativa para o Intune](../fundamentals/users-add.md) para saber como criar usuários do Intune no Azure Active Directory.

- O usuário final deve ter uma licença do Microsoft Intune atribuída à sua conta do Azure Active Directory. Confira [Gerenciar licenças do Intune](../fundamentals/licenses-assign.md) para saber como atribuir licenças do Intune aos usuários finais.

- O usuário final deve pertencer a um grupo de segurança destinado a uma política de proteção do aplicativo. A mesma política de proteção do aplicativo deve ter como destino o aplicativo específico utilizado. Políticas de proteção do aplicativo podem ser criadas e implantadas no console do Intune no [portal do Azure](https://portal.azure.com). No momento, grupos de segurança podem ser criados no [centro de administração do Microsoft 365](https://admin.microsoft.com).

- O usuário final deve se conectar ao aplicativo usando sua conta do AAD.

**E se eu quiser habilitar um aplicativo com a Proteção de Aplicativo do Intune, mas ele não está usando uma plataforma compatível de desenvolvimento de aplicativos?**

A equipe de desenvolvimento do SDK do Intune testa ativamente e mantém o suporte para aplicativos criados com as plataformas nativas do Android, iOS (Obj-C, Swift), Xamarin, Xamarin.Forms e Cordova. Embora alguns clientes tiveram sucesso na integração do SDK do Intune com outras plataformas, como React Native e NativeScript, não fornecemos orientação explícita ou plug-ins para desenvolvedores de aplicativos que usem algo diferente de nossas plataformas que têm suporte.

**O SDK da APP do Intune dá suporte à MSAL (Biblioteca de Autenticação da Microsoft) ou a contas sociais?**<br></br>
O SDK da APP do Intune usa algumas funcionalidades avançadas de ADAL para as versões internas e de terceiros do SDK. Assim, o MSAL não funciona bem com muitos de nossos principais cenários, como autenticação no serviço Proteção de Aplicativo do Intune e inicialização condicional. Considerando que a diretriz geral da equipe de identidade da Microsoft é mudar para o MSAL para todos os aplicativos do Microsoft Office, em algum momento o SDK do Intune precisará ser compatível com ele, mas não há planos agora para isso.

**Quais são os requisitos adicionais para usar o [aplicativo móvel do Outlook](https://products.office.com/outlook)?**

- O usuário final deve ter o aplicativo móvel do Outlook instalado em seu dispositivo.

- O usuário final deve ter uma caixa de correio do [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) e uma licença vinculada à sua conta do Azure Active Directory.

  >[!NOTE]
  > O aplicativo móvel do Outlook atualmente é compatível apenas para a Proteção de Aplicativo do Intune para o Microsoft Exchange Online e [Exchange Server com autenticação moderna híbrida](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx), e não dá suporte ao Exchange no Office 365 Dedicado.

**Quais são os requisitos adicionais para usar os [aplicativos Word, Excel e PowerPoint](https://products.office.com/business/office)?**

- O usuário final deve ter uma licença do [Office 365 Business ou Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) vinculada à sua conta do Azure Active Directory. A assinatura deve incluir os aplicativos do Office em dispositivos móveis e pode incluir uma conta de armazenamento em nuvem com o [OneDrive for Business](https://onedrive.live.com/about/business/). As licenças do Office 365 podem ser atribuídas na [centro de administração do Microsoft 365](https://admin.microsoft.com) seguindo estas [instruções](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

- O usuário final deve configurar um local gerenciado usando o salvamento granular como funcionalidade, na configuração "Impedir Salvar como" da política de proteção do aplicativo. Por exemplo, se o local gerenciado for o OneDrive, será necessário configurar o aplicativo [OneDrive](https://onedrive.live.com/about/) no aplicativo Word, Excel ou PowerPoint do usuário final.

- Se o local gerenciado for o OneDrive, será necessário direcionar o aplicativo de acordo com a política de proteção do aplicativo implantada para o usuário final.

  >[!NOTE]
  > No momento, os aplicativos móveis do Office dão suporte apenas ao SharePoint Online e não ao SharePoint local.

**Por que o local gerenciado (ou seja, o OneDrive) é necessário para o Office?**<br></br>
O Intune marca todos os dados no aplicativo como “corporativos” ou “pessoais”. Os dados são considerados “corporativos” quando tem como origem um local da empresa. Para os aplicativos do Office, o Intune considera o seguinte como locais da empresa: email (Exchange) ou armazenamento em nuvem (aplicativo OneDrive com uma conta do OneDrive para Empresas).

**Quais são os requisitos adicionais para usar o Skype for Business?**<br></br>
Consulte os requisitos de licença do [Skype for Business](https://products.office.com/skype-for-business/it-pros). Para configurações híbridas e locais do SfB (Skype for Business), confira [A autenticação moderna híbrida para SfB e Exchange torna-se GA](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) e [Autenticação moderna para SfB local com o AAD](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910), respectivamente.

## <a name="app-protection-features"></a>Recursos de proteção do aplicativo

**O que é o suporte a várias identidades?**<br></br>
Suporte a várias identidades é a capacidade do SDK do Aplicativo do Intune de aplicar políticas de proteção do aplicativo apenas à conta corporativa ou de estudante conectada ao aplicativo. Se uma conta pessoal estiver conectada ao aplicativo, os dados permanecerão inalterados.

**Qual é a finalidade do suporte a várias identidades?**<br></br>
O suporte a várias identidades permite que aplicativos com público "corporativo" e de consumidor (ou seja, os aplicativos do Office) sejam liberados publicamente com as funcionalidades de proteção do aplicativo do Intune para as contas "corporativas".

**E o Outlook e as várias identidades?**<br></br>
Como o Outlook tem uma exibição de email combinada de emails pessoal e “corporativo”, o aplicativo Outlook solicita o PIN do Intune na inicialização.

**O que é o PIN do aplicativo do Intune?**<br></br>
O PIN (Número de Identificação Pessoal) é uma senha usada para verificar se o usuário correto está acessando os dados da organização em um aplicativo.

- **Quando o usuário deverá inserir seu PIN?**<br></br> O Intune solicitará o PIN do aplicativo do usuário quando o usuário estiver prestes a acessar dados "corporativos". Em aplicativos de várias identidades, como o Word/Excel/PowerPoint, o usuário é solicitado a inserir seu PIN ao tentar abrir um arquivo ou documento “corporativo”. Em aplicativos de identidade única, como aplicativos de linha de negócios gerenciados com a Ferramenta de Disposição do Aplicativo do Intune, o PIN é solicitado na inicialização, pois o SDK do Aplicativo do Intune sabe que a experiência do usuário no aplicativo é sempre "corporativa".

- **Com que frequência o PIN do Intune será solicitado ao usuário?**<br></br> O administrador de TI pode definir a política de proteção do aplicativo Intune configurando "Verificar novamente os requisitos de acesso após (minutos)" no console de administrador do Intune. Essa configuração especifica a quantidade de tempo até os requisitos de acesso serem verificados no dispositivo e a tela PIN do aplicativo ser exibida novamente. No entanto, detalhes importantes sobre o PIN que afetam a frequência com que o usuário será consultado são: 

  - **O PIN é compartilhado entre aplicativos do mesmo editor para melhorar a usabilidade:** No iOS, um PIN de aplicativo é compartilhado entre todos os aplicativos **do mesmo editor de aplicativo**. No Android, o PIN de um aplicativo é compartilhado com todos os aplicativos.
  - **O comportamento "Verificar novamente os requisitos de acesso após (minutos)" após uma reinicialização do dispositivo:** Um "temporizador do PIN" rastreia o número de minutos de inatividade que determinam quando mostrar o PIN do aplicativo Intune. No iOS, o temporizador do PIN não é afetado pela reinicialização do dispositivo. Portanto, a reinicialização do dispositivo não tem nenhum efeito sobre o número de minutos que o usuário esteve inativo em um aplicativo iOS com a política de PIN do Intune. No Android, o temporizador do PIN é redefinido na reinicialização do dispositivo. Portanto, os aplicativos Android com a política de PIN do Intune provavelmente solicitarão um PIN do aplicativo, seja qual for o valor da configuração 'Verificar novamente os requisitos de acesso após (minutos)' **após uma reinicialização do dispositivo**.  
  - **A natureza em constante movimento do temporizador associada ao PIN:** Uma vez que um PIN é inserido para acessar um aplicativo (aplicativo A) e o aplicativo deixa o segundo plano (foco de entrada principal) no dispositivo, o temporizador do PIN é redefinido para esse PIN. Qualquer aplicativo (aplicativo B) que compartilhe esse PIN não solicitará ao usuário para inserir o PIN porque o temporizador foi redefinido. A solicitação será exibida novamente quando o valor "Verificar novamente os requisitos de acesso após (minutos)" for atendido novamente.

Para dispositivos iOS, mesmo se o PIN for compartilhado entre aplicativos de diferentes fornecedores, a solicitação será exibida novamente quando o valor **Verificar novamente os requisitos de acesso após (minutos)** for atendido novamente para o aplicativo que não é o foco principal da entrada. Por exemplo, um usuário tem o aplicativo _A_ do fornecedor _X_ e o aplicativo _B_ do fornecedor _Y_, e esses dois aplicativos compartilham o mesmo PIN. O usuário está concentrado no aplicativo _A_ (primeiro plano), e o aplicativo _B_ está minimizado. Depois que o valor **Verificar novamente os requisitos de acesso após (minutos)** for atendido e o usuário alternar para o aplicativo _B_, o PIN será necessário.

  >[!NOTE] 
  > Para verificar os requisitos de acesso do usuário com mais frequência (ou seja, solicitação do PIN), especialmente para um aplicativo usado com frequência, é recomendável reduzir o valor da configuração "Verificar novamente os requisitos de acesso após (minutos)". 
      
- **Como o PIN do Intune funciona com os PINs de aplicativo internos para o Outlook e o OneDrive?**<br></br>
O PIN do Intune funciona de acordo com um temporizador baseado em inatividade (ou seja, o valor de “Verificar novamente os requisitos de acesso após (minutos)”). Portanto, os prompts do PIN do Intune são mostrados independentemente dos prompts do PIN do aplicativo interno do Outlook e do OneDrive, que geralmente são vinculados à inicialização do aplicativo por padrão. Se o usuário recebe ambos os prompts de PIN ao mesmo tempo, o comportamento esperado é que o PIN do Intune tenha precedência. 

- **O PIN é seguro?**<br></br> O PIN serve para permitir que somente o usuário correto acesse os dados de sua organização no aplicativo. Portanto, um usuário final deve entrar com sua conta corporativa ou de estudante antes de definir ou redefinir o PIN do aplicativo do Intune. Essa autenticação é manipulada pelo Azure Active Directory por meio da troca de tokens seguros e não é transparente para o SDK do Aplicativo do Intune. Sob a perspectiva de segurança, a melhor maneira de proteger dados corporativos ou de estudante é criptografá-los. A criptografia não está relacionada ao PIN do aplicativo, mas à sua própria política de proteção de aplicativo.

- **Como o Intune protege o PIN contra ataques de força bruta?**<br></br> Como parte da política de PIN do aplicativo, o administrador de TI pode definir o número máximo de vezes que um usuário pode tentar autenticar seu PIN antes do bloqueio do aplicativo. Depois que o número de tentativas for atingido, o SDK do Aplicativo do Intune poderá apagar os dados “corporativos” no aplicativo.
  
- **Por que é necessário definir um PIN duas vezes em aplicativos do mesmo editor?**<br></br> Atualmente, o MAM (no iOS) permite o PIN no nível de aplicativo com caracteres alfanuméricos e especiais (chamados de ''senha''), que exige a participação de aplicativos (ou seja, WXP, Outlook, Managed Browser, Yammer) a fim de integrar o SDK do Aplicativo Intune para iOS. Sem isso, as configurações de senha não são aplicadas corretamente nos aplicativos de destino. Esse era um recurso lançado no SDK do Intune para iOS v. 7.1.12. <br><br> Para dar suporte a esse recurso e garantir a compatibilidade com versões anteriores do SDK do Intune para iOS, todos os PINs (numéricos ou de senha) na versão 7.1.12+ são tratados separadamente do PIN numérico das versões anteriores do SDK. Portanto, se um dispositivo tiver aplicativos com o SDK do Intune para versões do iOS anteriores a 7.1.12 E posteriores a 7.1.12 do mesmo editor, será necessário configurar dois PINs. <br><br> Dito isso, os dois PINs (para cada aplicativo) não estão relacionados de alguma forma, ou seja, devem aderir à política de proteção do aplicativo aplicada ao aplicativo. Como tal, *somente* se os aplicativos A e B tiverem as mesmas políticas aplicadas (com relação ao PIN), o usuário poderá configurar o mesmo PIN duas vezes. <br><br> Esse comportamento é específico ao PIN em aplicativos do iOS habilitados com o Gerenciamento de Aplicativo Móvel do Intune. Ao longo do tempo, à medida que os aplicativos adotam versões posteriores do SDK do Intune para iOS, a necessidade de definir um PIN duas vezes em aplicativos do mesmo editor se torna um problema menos significativo. Consulte a observação abaixo para obter um exemplo.

  >[!NOTE]
  > Por exemplo, se o aplicativo A for compilado com uma versão anterior à 7.1.12, e o aplicativo B for compilado com uma versão superior ou igual à 7.1.12 do mesmo editor, o usuário final precisará configurar PINs separadamente para A e B, se ambos forem instalados em um dispositivo iOS. <br><br> Se um aplicativo C que tenha o SDK versão 7.1.9 estiver instalado no dispositivo, ele compartilhará o mesmo PIN que o aplicativo A. <br><br> Um aplicativo D compilado com 7.1.14 compartilhará o mesmo PIN que o aplicativo B. <br><br> Se apenas os aplicativos A e C estiverem instalados em um dispositivo, será necessário definir um PIN. O mesmo se aplica se apenas os aplicativos B e D estiverem instalados em um dispositivo.

**E a criptografia?**<br></br>
Os administradores de TI podem implantar uma política de proteção do aplicativo que exige a criptografia dos dados do aplicativo. Como parte da política, o administrador de TI também pode especificar quando o conteúdo é criptografado.

- **Como o Intune criptografa os dados?**<br></br> Consulte [Android app protection policy settings (Configurações da política de proteção do aplicativo Android)](app-protection-policy-settings-android.md) e [iOS app protection policy settings (Configurações da política de proteção do aplicativo iOS)](app-protection-policy-settings-ios.md) para obter informações detalhadas sobre a configuração da política de proteção do aplicativo para criptografia.

- **O que é criptografado?**<br></br> Somente os dados marcados como “corporativos” são criptografados, de acordo com a política de proteção do aplicativo do administrador de TI. Os dados são considerados “corporativos” quando tem como origem um local da empresa. Para os aplicativos do Office, o Intune considera o seguinte como locais da empresa: email (Exchange) ou armazenamento em nuvem (aplicativo OneDrive com uma conta do OneDrive para Empresas). Para aplicativos de linha de negócios gerenciados pela Ferramenta de Disposição do Aplicativo do Intune, todos os dados do aplicativo são considerados "corporativos".

**Como o Intune apaga os dados remotamente?**<br></br>
O Intune pode apagar os dados do aplicativo de três maneiras diferentes: apagamento completo do dispositivo, apagamento seletivo para MDM e apagamento seletivo de MAM. Para obter mais informações sobre o apagamento remoto para MDM, consulte [Remover dispositivos usando o apagamento ou a desativação](../remote-actions/devices-wipe.md). Para obter mais informações sobre o apagamento seletivo usando MAM, confira [A ação Desativar](../remote-actions/devices-wipe.md#retire) e [Como apagar apenas dados corporativos dos aplicativos](apps-selective-wipe.md).

- **O que é o apagamento?**<br></br> O [apagamento](../remote-actions/devices-wipe.md) remove todos os dados e as configurações do usuário do **dispositivo** restaurando-o para as configurações padrão de fábrica. O dispositivo é removido do Intune.
  >[!NOTE]
  > O apagamento pode ser realizado apenas em dispositivos registrados no MDM (gerenciamento de dispositivo móvel) do Intune.

- **O que é o apagamento seletivo para MDM?**<br></br> Confira [Remover dispositivos – desativar](../remote-actions/devices-wipe.md#retire) para saber mais sobre a remoção de dados da empresa.

- **O que é o apagamento seletivo para MAM?**<br></br> O apagamento seletivo para MAM simplesmente remove dados de aplicativo da empresa de um aplicativo. A solicitação é iniciada usando o portal do Azure no Intune. Para saber como iniciar uma solicitação de apagamento, confira [Como remover apenas dados corporativos dos aplicativos](apps-selective-wipe.md).

- **Com que rapidez o apagamento seletivo para MAM ocorre?**<br></br> Se o usuário estiver usando o aplicativo quando o apagamento seletivo for iniciado, o SDK do Aplicativo do Intune verificará a cada 30 minutos uma solicitação de apagamento seletivo do serviço Intune MAM. Ele também verifica o apagamento seletivo quando o usuário inicia o aplicativo pela primeira vez e se conecta com sua conta corporativa ou de estudante.

**Por que os serviços Locais não funcionam com os aplicativos protegidos do Intune?**<br></br>
A proteção do aplicativo do Intune depende da consistência da identidade do usuário entre o aplicativo e o SDK do Aplicativo do Intune. A única maneira de assegurar isso é por meio da autenticação moderna. Existem cenários nos quais os aplicativos podem funcionar com uma configuração local, mas eles não são consistentes nem têm garantia.

**Existe uma maneira segura de abrir links da Web em aplicativos gerenciados?**<br></br>
Sim. O administrador de TI pode implantar e definir uma política de proteção do aplicativo para o [aplicativo Intune Managed Browser](../apps/app-configuration-managed-browser.md), um navegador da Web desenvolvido pelo Microsoft Intune que pode ser gerenciado facilmente com o Intune. O administrador de TI pode exigir que todos os links da Web em aplicativos gerenciados pelo Intune sejam abertos usando o aplicativo Managed Browser.

## <a name="app-experience-on-android"></a>Experiência do aplicativo no Android

**Por que o aplicativo Portal da Empresa é necessário para o funcionamento da proteção do aplicativo do Intune em dispositivos Android?**<br></br>
Grande parte da funcionalidade de proteção do aplicativo é interna ao aplicativo Portal da Empresa. O registro de dispositivo _não é necessário_, embora o aplicativo Portal da Empresa seja sempre obrigatório. Para o MAM-WE, o usuário final precisa apenas ter o aplicativo Portal da Empresa instalado no dispositivo.

**Como várias configurações de acesso de Proteção de Aplicativo do Intune definidas no mesmo conjunto de aplicativos e usuários funcionam no Android?**<br></br>
As políticas de Proteção de Aplicativo do Intune para acesso serão aplicadas em uma ordem específica nos dispositivos do usuário final à medida que eles tentarem acessar um aplicativo de destino da sua conta corporativa. Em geral, um bloqueio teria precedência e, em seguida, um aviso ignorável. Por exemplo, se aplicável ao usuário/aplicativo em questão, uma configuração de versão de patch mínima do Android que avisa o usuário para fazer uma atualização de patch, que será aplicada após a configuração da versão de patch mínima do Android que bloqueia o acesso do usuário. Portanto, o cenário em que o administrador de TI configura a versão de patch de Android mínima 2018-03-01 e a versão de patch de Android mínima (somente Aviso) 2018-02-01, enquanto o dispositivo tentar acessar o aplicativo estava em uma versão de patch 2018-01-01, o usuário final seria bloqueado com base a configuração mais restritiva para a versão de patch de Android mínima que resulta em acesso bloqueado. 

Ao lidar com diferentes tipos de configurações, um requisito de versão do aplicativo teria precedência, seguido por um requisito de versão do sistema operacional de versão de patch do Android. Em seguida, os avisos para todos os tipos de configurações na mesma ordem são verificados.

**As Políticas de Proteção de Aplicativo do Intune fornecem a funcionalidade para exigir que os dispositivos de usuário final sejam aprovados no Atestado SafetyNet do Google para dispositivos Android. Com que frequência um novo resultado do Atestado SafetyNet é enviado para o dispositivo?** <br><br> Uma nova determinação de serviço do Google Play será relatada ao administrador de TI em um intervalo determinado pelo serviço do Intune. A frequência com que a chamada de serviço é feita é limitada devido à carga; portanto, esse valor é mantido internamente e não é configurável. Qualquer ação configurada pelo administrador de TI para a configuração do Atestado SafetyNet do Google será usada com base no último resultado relatado ao serviço do Intune no momento da inicialização condicional. Se não houver dados, o acesso será permitido sem depender de nenhuma outra falha nas verificações de inicialização condicional e a “viagem de ida e volta” do Serviço do Google Play para determinar os resultados do atestado começará no back-end e avisará o usuário de maneira assíncrona se o dispositivo tiver falhado. Se houver dados obsoletos, o acesso será bloqueado ou permitido dependendo do último resultado relatado e, de maneira semelhante, a “viagem de ida e volta” do Serviço do Google Play para determinar os resultados do atestado começará e avisará o usuário de maneira assíncrona se o dispositivo tiver falhado.

**As Políticas de Proteção de Aplicativo do Intune fornecem a funcionalidade para que os administradores exijam que os dispositivos de usuário final enviem sinais por meio da API Verificar Aplicativos do Google para dispositivos Android. Como um usuário final pode ativar o exame de aplicativos para que ele não tenha o acesso bloqueado devido a isso?**<br><br> As instruções sobre como fazer isso variam um pouco por dispositivo. O processo geral envolve acessar a Google Play Store, clicar em **Meus aplicativos e jogos** e clicar no resultado do último exame de aplicativo que o levará até o menu do Play Protect. Verifique se **Examinar no dispositivo se há ameaças à segurança** está ativado.

**O que a API do Atestado SafetyNet do Google realmente verifica em dispositivos Android? Qual é a diferença entre os valores configuráveis de “Verificar integridade básica” e “Verificar integridade básica e dispositivos certificados”?** <br><br>
O Intune usa as APIs SafetyNet do Google Play Protect a serem adicionadas às nossas verificações de detecção raiz para dispositivos não registrados. O Google desenvolveu e manteve esse conjunto de APIs para os aplicativos Android adotarem se eles não desejarem que os aplicativos sejam executados em dispositivos desbloqueados por rooting. O aplicativo Android Pay incorporou isso, por exemplo. Embora o Google não compartilhe publicamente todas as verificações de detecção raiz que ocorrem, esperamos que essas APIs detectem usuários que bloquearam seus dispositivos por rooting. Esses usuários podem ter o acesso bloqueado ou suas contas corporativas podem ser apagadas dos aplicativos habilitados por política. “Verificar integridade básica” informa sobre a integridade geral do dispositivo. Dispositivos desbloqueados por rooting, emuladores, dispositivos virtuais e dispositivos com sinais de falsificação apresentam falha na integridade básica. “Verificar integridade básica e dispositivos certificados” informa sobre a compatibilidade do dispositivo com os serviços do Google. Somente dispositivos não modificados que foram certificados pelo Google podem ser aprovados nessa verificação. Dispositivos que falharão incluem o seguinte:

- dispositivos que apresentam falha na integridade básica
- dispositivos com um carregador de inicialização desbloqueado
- dispositivos com uma imagem/ROM do sistema personalizada
- dispositivos que o fabricante não inscreveu na certificação do Google ou que não foram aprovados por ela 
- dispositivos com uma imagem do sistema criada diretamente de arquivos de origem do Programa de Software Livre do Android
- dispositivos com uma imagem do sistema de versão prévia beta/do desenvolvedor

Confira a [documentação do Google sobre o Atestado SafetyNet](https://developer.android.com/training/safetynet/attestation) para obter detalhes técnicos.

**Há duas verificações semelhantes na seção Inicialização condicional ao criar uma Política de Proteção de Aplicativo do Intune para dispositivos Android. Devo exigir a configuração “atestado de dispositivo SafetyNet” ou “dispositivos bloqueados por rooting/jailbreak”?** <br><br>
As verificações da API SafetyNet do Google Play Protect exigem que o usuário final esteja online, pelo menos durante o período de execução da “viagem de ida e volta” para determinar os resultados do atestado. Se o usuário final estiver offline, o administrador de TI ainda poderá esperar que um resultado seja imposto da configuração “dispositivos bloqueados por rooting/com jailbreak”. Dito isso, se o usuário final tiver ficado offline por muito tempo, o valor “Período de carência offline” entrará em jogo e todo o acesso a dados corporativos ou de estudante será bloqueado depois que esse valor de temporizador for atingido até que o acesso à rede esteja disponível. Ativar as duas configurações permite que uma abordagem em camadas mantenha os dispositivos de usuário final íntegros, o que é importante quando os usuários finais acessam dados corporativos ou de estudante em dispositivos móveis. 

**As configurações da política de proteção de aplicativo que usam as APIs do Google Play Protect exigem que o Google Play Services funcione. E se o Google Play Services não tiver permissão no local em que o usuário final possa estar?**<br><br>
As duas configurações “atestado de dispositivo SafetyNet” e “Verificação de ameaças em aplicativos” exigem que a versão determinada pelo Google do Google Play Services funcione corretamente. Como essas configurações se enquadram na área de segurança, o usuário final será bloqueado se for direcionado com essas configurações e não atender à versão adequada do Google Play Services ou não tiver acesso ao Google Play Services. 

## <a name="app-experience-on-ios"></a>Experiência do aplicativo no iOS
**O que acontece se eu adicionar ou remover uma impressão digital ou detecção facial ao meu dispositivo?**<br></br>
As políticas de Proteção de Aplicativo do Intune permitem controlar o acesso do aplicativo somente para o usuário licenciado do Intune. Uma das maneiras de controlar o acesso ao aplicativo é exigir uma Touch ID ou a Face ID da Apple em dispositivos com suporte. O Intune implementa um comportamento no qual, se houver qualquer alteração ao banco de dados biométrico do dispositivo, solicitará ao usuário um PIN quando o próximo valor de tempo limite de inatividade for atendido. As alterações aos dados biométricos incluem a adição ou a remoção de uma impressão digital ou detecção facial. Se o usuário do Intune não tiver um PIN definido, ele será conduzido a configurar um PIN do Intune.

A intenção disso é continuar mantendo os dados da sua organização, dentro do aplicativo, seguros e protegidos no nível do aplicativo. Esse recurso está disponível apenas para iOS e requer a participação de aplicativos que integram o SDK do aplicativo Intune para iOS, versão 9.0.1 ou posterior. A integração do SDK é necessária para que o comportamento possa ser aplicado aos aplicativos de destino. Essa integração ocorre sem interrupção, e depende de equipes do aplicativo específico. Alguns aplicativos que participam incluem WXP, Outlook, Managed Browser e Yammer.
  
**Consigo usar a extensão de compartilhamento do iOS para abrir dados corporativos ou de estudante em aplicativos não gerenciados, mesmo com a política de transferência de dados definida como “apenas aplicativos gerenciados” ou “nenhum aplicativo”. Isso não causa a perda de dados?**<br></br>
A política de proteção do aplicativo do Intune não pode controlar a extensão de compartilhamento do iOS sem gerenciar o dispositivo. Portanto, o _**Intune criptografa os dados “corporativos” antes que eles sejam compartilhados fora do aplicativo**_ . É possível validar isso ao tentar abrir o arquivo “corporativo” fora do aplicativo gerenciado. O arquivo deve ser criptografado e não pode ser aberto fora do aplicativo gerenciado.

**Como várias configurações de acesso de Proteção de Aplicativo do Intune definidas no mesmo conjunto de aplicativos e usuários funcionam no iOS?**<br></br>
As políticas de Proteção de Aplicativo do Intune para acesso serão aplicadas em uma ordem específica nos dispositivos do usuário final à medida que eles tentarem acessar um aplicativo de destino da sua conta corporativa. Em geral, um apagamento teria precedência, seguido por um bloqueio e então um aviso ignorável. Por exemplo, se aplicável ao usuário/aplicativo em questão, uma configuração de sistema operacional mínima do iOS que avisa o usuário para atualizar a versão de iOS, que será aplicada após a configuração de sistema operacional mínima do iOS que bloqueia o acesso do usuário. Portanto, no cenário em que o administrador de TI configura a versão de sistema operacional iOS mínima para 11.0.0.0 e do sistema operacional iOS mínima para 11.1.0.0, enquanto o dispositivo que tenta acessar o aplicativo estava em uma versão de iOS 10, o usuário final seria bloqueado com base a configuração mais restritiva para a versão de sistema operacional iOS mínima que resulta em acesso bloqueado.

Ao lidar com diferentes tipos de configurações, um requisito de versão do SDK do Aplicativo Intune teria precedência, depois um requisito de versão do aplicativo, seguido pelo requisito de versão do sistema operacional iOS. Em seguida, os avisos para todos os tipos de configurações na mesma ordem são verificados. É recomendável que o requisito de versão do SDK do Aplicativo Intune seja configurado somente após a orientação da equipe de produto do Intune para cenários de bloqueio essenciais.


## <a name="see-also"></a>Consulte também
- [Implementar seu plano do Intune](../fundamentals/planning-guide-onboarding.md)
- [Teste e validação do Intune](../fundamentals/planning-guide-test-validation.md)
- [Configurações de política de gerenciamento de aplicativo móvel do Android no Microsoft Intune](../apps/app-protection-policy-settings-android.md)
- [Configurações de política de gerenciamento de aplicativo móvel iOS](../apps/app-protection-policy-settings-ios.md)
- [Atualização da política de proteção de aplicativo](../apps/app-protection-policy-delivery.md)
- [Validar políticas de proteção do aplicativo](../apps/app-protection-policy-delivery.md)
- [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](../apps/app-configuration-policies-managed-app.md)
- [Como obter suporte para o Microsoft Intune](../fundamentals/get-support.md)