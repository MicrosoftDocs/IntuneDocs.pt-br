---
title: "Configurações de restrição de dispositivo do Intune para Windows 10"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: conheça as configurações do Intune que você pode usar para controlar as configurações do dispositivo e as funcionalidades dos dispositivos Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 88910c6628bb356e4a757cbdb4cf63b0acf60040
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo do Windows 10 e posterior no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="general"></a>Geral
-     **Captura de tela (somente dispositivo móvel)** – permite que o usuário capture a tela do dispositivo como uma imagem.
-     **Copiar e colar (somente dispositivo móvel)** – Permitir utilizar ações de copiar e colar entre os aplicativos do dispositivo.
-     **Cancelamento de registro manual** – Permite que o usuário exclua manualmente a conta de trabalho do dispositivo.
-     **Instalação manual do certificado raiz (somente dispositivo móvel)** - impede que o usuário instale manualmente os certificados raiz e certificados CAP intermediários.
-     **Envio de dados de diagnóstico** – Os valores possíveis são:
    -         **Nenhum** Nenhum dado é enviado para a Microsoft
    -         **Básico** Informações limitadas são enviadas para a Microsoft
    -         **Avançado** Dados de diagnóstico avançados são enviados para a Microsoft
    -         **Completo** Envia os mesmos dados que Avançado, além de dados adicionais sobre o estado do dispositivo
-     **Câmera** – Permite ou bloqueia o uso da câmera do dispositivo.
-     **Sincronização de arquivos do OneDrive** - bloqueia a sincronização de arquivos do dispositivo com o OneDrive.
-     **Armazenamento removível** – Especifica se é possível usar dispositivos de armazenamento externo, como um cartão SD, no dispositivo.
-     **Geolocalização** – Especifica se o dispositivo pode usar informações de serviços de localização.
-     **Compartilhamento da Internet** – Permite o uso do compartilhamento de conexão com a Internet no dispositivo.
-     **Redefinição do telefone** – Controla se o usuário pode realizar uma redefinição de fábrica em seu dispositivo.
-     **Conexão USB (somente dispositivos móveis)** – controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB.
-     **Modo AntiTheft (somente dispositivos móveis)** – configure se o modo AntiTheft do Windows está habilitado.
-     **Notificações da central de ações (somente dispositivos móveis)** – habilita ou desabilita as notificações da central de ações na tela de bloqueio do dispositivo (somente Windows 10 Mobile).
-     **Cortana** – Habilitar ou desabilitar a assistente de voz Cortana.
-     **Gravação de voz (somente dispositivos móveis)** – permitir ou bloquear o uso do gravador de voz do dispositivo.
-     **Modificação das configurações de energia e suspensão (somente desktop)** - impede que o usuário final altere as configurações de energia e suspensão no dispositivo.
-     **Modificação das configurações de região (somente desktop)** - impede que o usuário final altere as configurações de região no dispositivo.
-     **Modificação das configurações de idioma (somente desktop)** - impede que o usuário altere as configurações de idioma no dispositivo.
-     **Modificação do horário do sistema** - impede que o usuário final altere a data e hora do dispositivo.
-     **Modificação do nome do dispositivo** - impede que o usuário final altere o nome do dispositivo.
-     **Adicionar pacotes de provisionamento** - bloqueia o agente de configuração de tempo de execução que instala os pacotes de provisionamento.
-     **Remover pacotes de provisionamento** - bloqueia o agente de configuração de tempo de execução que remove os pacotes de provisionamento.
-     **Descoberta de dispositivos** - bloqueia a descoberta de um dispositivo por outros dispositivos.
-     **Alternador de tarefas (somente dispositivos móveis)** - bloqueia o alternador de tarefas no dispositivo.
-     **Diálogo de erro do cartão SIM (somente dispositivos móveis)** - bloqueia a exibição de uma mensagem de erro no dispositivo se nenhum cartão SIM for detectado.


## <a name="password"></a>Senha
-     **Senha** – Exige que o usuário final insira uma senha para acessar o dispositivo.
    -     **Tipo de senha exigida** – Especifica se a senha deve ser apenas numérica ou alfanumérica.
    -     **Tamanho mínimo da senha** – Aplicável somente a Windows 10 Mobile.
    -     **Número de falhas conexão antes de limpar o dispositivo** – Para dispositivos que executam o Windows 10: se o dispositivo tiver o BitLocker habilitado, ele será colocado no modo de recuperação do BitLocker depois que a conexão falhar o número de vezes especificado. Se o dispositivo não tiver o BitLocker habilitado, essa configuração não será aplicada.
Para dispositivos que executam o Windows Mobile 10: depois que a entrada falhar o número de vezes que você especificar, o dispositivo será apagado.
    -     **Máximo de minutos de inatividade para o bloqueio de tela** – Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada.
    -     **Expiração de senha (dias)** – Especifica o período após o qual a senha do dispositivo deve ser alterada.
    -     **Impedir a reutilização de senhas anteriores** – Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.
    -     **Exigir senha quando o dispositivo retorna do estado inativo** – Especifica que o usuário deverá inserir uma senha para desbloquear o dispositivo (somente Windows 10 Mobile).
-     **Criptografia** – Habilitar a criptografia em dispositivos de destino (somente Windows 10 Mobile).

## <a name="personalization"></a>Personalização

-     **URL de imagem de plano de fundo da área de trabalho (somente desktop)** - especifique a URL para uma imagem no formato PNG, JPG ou JPEG que será usada como o papel de parede da área de trabalho do Windows. Os usuários não poderão alterar isso.

## <a name="locked-screen-experience"></a>Experiência na tela bloqueada

-     **URL de imagem da tela bloqueada (somente desktop)** - especifique a URL para uma imagem no formato PNG, JPG ou JPEG que será usada como o papel de parede de tela bloqueada do Windows. Os usuários não poderão alterar isso.


## <a name="app-store"></a>Loja de aplicativos

-     **Loja de aplicativos (somente dispositivo móvel)** – Habilitar ou bloquear o uso da loja de aplicativos em dispositivos Windows 10 Mobile.
-     **Atualizar aplicativos automaticamente a partir da Store** - permite que os aplicativos instalados a partir da Windows Store sejam atualizados automaticamente.
-     **Instalação de aplicativo confiável** - permite que os aplicativos assinados com um certificado de confiança sejam carregados por sideload.
-     **Desbloqueio do desenvolvedor** - permite que configurações de desenvolvedor do Windows, como a permissão de sideload de aplicativos, sejam modificadas pelo usuário final.
-     **Dados de aplicativo do usuário compartilhados** - permite que os aplicativos compartilhem dados entre usuários diferentes no mesmo dispositivo.
-     **Usar somente armazenamento privado** - habilite esta opção para permitir que somente os usuários finais possam baixar aplicativos de seu armazenamento privado.
-     **Inicialização de aplicativo originado na Store** - usada para desabilitar todos os aplicativos que foram previamente instalados no dispositivo ou baixados da Windows Store.
-     **Instalar dados do aplicativo no volume do sistema** - impede que os aplicativos armazenem dados no volume do sistema do dispositivo.
-     **Instalar aplicativos na unidade do sistema** - impede que os aplicativos armazenem dados na unidade do sistema do dispositivo.
-     **DVR de Jogos (somente desktop)** - Define se é permitido registrar e transmitir jogos.



## <a name="edge-browser"></a>Navegador Edge
-     **Navegador Microsoft Edge (somente dispositivo móvel)** – Permitir o uso do navegador da Web Edge no dispositivo.
-     **SmartScreen** – Habilita ou desabilita o SmartScreen, que bloqueia sites fraudulentos.
-     **Enviar cabeçalhos Do Not Track** – Configura o navegador Edge para enviar cabeçalhos Do Not Track para sites visitados pelos usuários.
-     **Cookies** – Permite que o navegador salve cookies da Internet no dispositivo.
-     **JavaScript** – Permite que scripts, como JavaScript, sejam executados no navegador Edge.
-     **Pop-ups** - bloqueia janelas pop-up no navegador (aplica-se a somente a desktops com Windows 10).
-     **Sugestões de Pesquisa** – Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa.
-     **Enviar tráfego da intranet para o Internet Explorer** – permite aos usuários abrir sites de intranet no Internet Explorer (somente para desktops com Windows 10).
-     **Preenchimento automático** – permite que os usuários alterem completamente as configurações de preenchimento automático no navegador (somente para desktop com Windows 10).
-     **Gerenciador de Senhas** – Habilitar ou desabilitar o recurso de Gerenciador de Senhas do Edge.
-     **Local da lista de sites do modo Empresarial** – Especifica onde encontrar a lista de sites que serão abertos no modo Empresarial. Os usuários não podem editar essa lista.<br>(Somente Windows 10 Desktop).
-     **Ferramentas de desenvolvedor** - impede que o usuário final abra as ferramentas de desenvolvedor do Edge.
-     **Extensões** - permite ao usuário final instalar extensões do Edge no dispositivo.
-     **Navegação inPrivate** - impede que o usuário final abra sessões de navegação InPrivate.
-     **Url da primeira execução** - insira a URL que o navegador Edge abrirá na primeira vez que for executado (somente dispositivos móveis).
-     **Home pages** - adicione uma lista de sites que serão usados como home pages no navegador Edge (somente desktop).
-     **Bloquear acesso aos about:flags** - impede que o usuário final acesse a página about:flags no Edge que contém configurações experimentais e de desenvolvedor.
-     **Substituição do prompt de SmartScreen** - permite ao usuário final ignorar os avisos do filtro do SmartScreen sobre sites possivelmente mal-intencionados.
-     **Substituição do prompt de SmartScreen para arquivos** - permite ao usuário final ignorar os avisos do filtro do SmartScreen sobre o download de arquivos possivelmente mal-intencionados.
-     **Endereço IP do localhost WebRtc** - bloqueia a exibição do endereço IP do localhost de usuários ao fazer chamadas telefônicas usando a protocolo RTC da web.
-     **Mecanismo de pesquisa padrão** - especifica o mecanismo de pesquisa padrão a ser usado. Os usuários finais podem alterar esse valor a qualquer momento.

## <a name="search"></a>Pesquisar
- **Pesquisa segura (somente dispositivos móveis)** - controla como o Cortana filtra o conteúdo adulto nos resultados da pesquisa. Você pode selecionar **Estrito**, **Moderado** ou permitir que o usuário final escolha suas próprias configurações.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento
-     **Conta da Microsoft** – Permite que o usuário associe uma conta da Microsoft ao dispositivo.
-     **Conta não Microsoft** – Permite que o usuário adicione contas de email ao dispositivo que não estão associadas a uma conta da Microsoft.
-     **Sincronização de configurações para conta da Microsoft** – Permitir configurações de dispositivo e aplicativos associadas a uma conta da Microsoft para sincronização entre dispositivos.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade
-     **Roaming de dados** – Permitir roaming entre redes ao acessar os dados.
-     **VPN em rede celular** – Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular.
-     **Roaming VPN em rede celular** – Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular em roaming.
-     **Bluetooth** – Controla se o usuário pode habilitar e configurar o Bluetooth no dispositivo.
-     **Descoberta de Bluetooth** – Permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.
-     **Anúncios por Bluetooth** – Permite que o dispositivo receba anúncios via Bluetooth.
-     **Nome do Bluetooth do dispositivo** - permite que você especifique o nome do Bluetooth para o dispositivo.
-     **NFC** – Permite que o usuário habilite e configure recursos de comunicação a curta distância no dispositivo.
-     **Wi-Fi** – Permite que o usuário habilite e configure o Wi-Fi no dispositivo (somente Windows 10 Mobile).
-     **Conectar automaticamente a hotspots Wi-Fi** – Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente.
-     **Configuração manual de Wi-Fi** – Controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se pode usar somente as conexões configuradas por um perfil Wi-Fi (somente Windows 10 Mobile).
-     **Intervalo de verificação de Wi-Fi** - especifique com que frequência os dispositivos procuram redes Wi-Fi.

## <a name="control-panel-and-settings"></a>Painel de controle e configurações

-     **Configurações de aplicativo** - bloqueia o acesso ao aplicativo de configurações do Windows.
    -     **Sistema** - bloqueia o acesso à área de sistema do aplicativo de configurações.
    -     **Dispositivos** - bloqueia o acesso à área de dispositivos do aplicativo de configurações.
    -     **Rede e Internet** - bloqueia o acesso à área de rede e internet do aplicativo de configurações.
    -     **Personalização** - bloqueia o acesso à área de personalização do aplicativo de configurações.
    -     **Contas** - bloqueia o acesso à área de contas do aplicativo de configurações.
    -     **Hora e Idioma** - bloqueia o acesso à área de hora e idioma do aplicativo de configurações.
    -     **Facilidade de Acesso** - bloqueia o acesso à área de facilidade de acesso do aplicativo de configurações.
    -     **Privacidade** - bloqueia o acesso à área de privacidade do aplicativo de configurações.
    -     **Atualização de Segurança** - bloqueia o acesso à área de atualizações e segurança do aplicativo de configurações.

## <a name="defender"></a>Defender

-     **Monitoramento em tempo real** – Habilita a verificação em tempo real de malware, de spyware e de outros tipos de software indesejados.
-     **Monitoramento de comportamento** – Permite que o Defender verifique se há certos padrões conhecidos de atividade suspeita nos dispositivos.
-     **Sistema de Inspeção de Rede (NIS)** – O Sistema de Inspeção de Rede (NIS) ajuda a proteger os dispositivos contra explorações baseadas em rede usando as assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear tráfego mal-intencionado.
-     **Examinar todos os downloads** – Controla se o Defender examina todos os arquivos baixados da Internet.
-     **Examinar scripts carregados nos navegadores da Web da Microsoft** – Permite que o Defender verifique os scripts que são usados no Internet Explorer.
-     **Acesso do usuário final ao Defender** – Controla se a interface do usuário do Windows Defender está oculta para usuários finais.
Quando essa configuração é alterada, ela entrará em vigor na próxima vez em que o computador do usuário final for reiniciado.
-     **Intervalo de atualização de assinatura (em horas)** – Especifique o intervalo no qual o Defender verificará novos arquivos de assinatura.
-     **Monitorar a atividade de arquivos e programas** – Permite que o Defender monitore a atividade de arquivos e programas nos dispositivos.
-     **Dias de espera antes de excluir malware em quarentena** – Permite que o Defender continue a rastrear o malware resolvido pelo número de dias que especificado para que você possa examinar manualmente os dispositivos infectados anteriormente. Se você definir o número de dias para **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente.
-     **Limite de uso de CPU durante uma verificação** – Permite limitar a quantidade de CPU que as verificações têm permissão para usar (de **1** a **100**).
-     **Verificar arquivos mortos** – Permite que o Defender examine arquivos mortos, como os arquivos Zip ou Cab.
-     **Verificar mensagens de email recebidas** – Permite que o Defender verifique mensagens de email assim que elas chegarem ao dispositivo.
-     **Examinar unidades removíveis durante uma verificação completa** – Permite que o Defender examine unidades removíveis como pen drives.
-     **Examinar unidades de rede mapeadas durante uma verificação completa** – Permite que o Defender examine arquivos em unidades de rede mapeadas.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.
-     **Examinar arquivos abertos de pastas de rede** – Permite que o Defender examine arquivos em unidades de rede compartilhadas (por exemplo, aqueles acessados de um caminho UNC).
Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.
-     **Proteção de nuvem** – Permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.
-     **Perguntar aos usuários antes de enviar amostras** – Controla se os arquivos que podem exigir mais análise pela Microsoft para determinar se são mal-intencionados são enviados automaticamente para a Microsoft.
-     **Hora para realizar uma verificação rápida diária** – Permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar.
-     **Tipo de verificação do sistema a ser executada** – Permite que você especifique o nível de verificação que será executado ao agendar uma verificação do sistema.

## <a name="defender-exclusions"></a>Exclusões do Defender

-     **Arquivos e pastas a serem excluídas da verificação e proteção em tempo real** – Adiciona um ou mais arquivos e pastas como **C:\Path** ou **%ProgramFiles%\Path\filename.exe** à lista de exclusões. Esses arquivos e pastas não serão incluídos em verificações em tempo real ou programadas.
-     **Extensões de arquivos a serem excluídas de verificações e proteção em tempo real** – Adicione uma ou mais extensões de arquivo como **jpg** ou **txt** à lista de exclusões. Qualquer arquivo com essas extensões não serão incluídos em verificações em tempo real ou programadas.
-     **Processos a serem excluídos de verificações e proteção em tempo real** – Adicionar um ou mais processos do tipo **.exe**, **.com** ou **.scr** à lista de exclusões. Esses processos não serão incluídos em verificações em tempo real ou programadas.


## <a name="network-proxy"></a>Proxy de rede

-     **Detectar automaticamente as configurações de proxy** - quando essa opção estiver habilitada, o dispositivo tentará localizar o caminho até um script PAC.
-     **Usar script de proxy** - selecione esta opção se você quiser especificar um caminho até um script PAC para configurar o servidor proxy.
    -     **Configurar URL de endereço do script** - insira a URL de um script PAC que você deseja usar para configurar o servidor proxy.
-     **Usar servidor proxy manual** - selecione esta opção se você quiser fornecer manualmente as informações do servidor proxy.
    -     **Endereço** - insira o nome ou o endereço IP do servidor proxy.
    -     **Número da porta** – insira o número de porta de seu servidor proxy.
    -     **Exceções de proxy** - insira todas as URLs que não devem usar o servidor proxy. Use um ponto e vírgula para separar cada item.
    -     **Ignorar servidor proxy para endereços locais** - habilite esta opção se você não quiser usar o servidor proxy para endereços locais na intranet.


## <a name="windows-spotlight"></a>Destaque do Windows

-     **Destaque do Windows** - permita ou bloqueie o Destaque do Windows, que fornece recursos como dicas e truques, mensagens sobre a Tela de Bloqueio do Windows e muito mais.
    -     **Dicas do Windows** - permite o bloqueio de exibição de dicas pop-up no Windows.
    -     **Recursos de Consumidor** - permite o bloqueio de recursos do consumidor, como sugestões do menu Iniciar e notificações de associação.

## <a name="display"></a>Vídeo

- **Entrada do usuário de receptores de vídeo sem fio** - bloqueia a entrada do usuário de receptores de vídeo sem fio.
- **Projeção neste PC** - impede que outros dispositivos descubram o PC para projeção.
- **Exigir PIN para emparelhamento** - exige um PIN durante a conexão com um dispositivo de projeção.

## <a name="start"></a>Inicie o

- **Desafixar aplicativos da barra de tarefas** - impede o usuário de desafixar aplicativos no menu Iniciar.
- **Documentos em Iniciar** - oculta ou mostra a pasta Documentos no menu Iniciar do Windows.
- **Downloads em Iniciar** - oculta ou mostra a pasta Downloads no menu Iniciar do Windows.
- **Explorador de Arquivos em Iniciar** - oculta ou mostra o aplicativo Explorador de Arquivos no menu Iniciar do Windows.
- **Grupo Doméstico em Iniciar** - oculta ou mostra a pasta Grupo Doméstico no menu Iniciar do Windows.
- **Música em Iniciar** - oculta ou mostra a pasta Música no menu Iniciar do Windows.
- **Rede em Iniciar** - oculta ou mostra a pasta Rede no menu Iniciar do Windows.
- **Pasta Pessoal em Iniciar** - oculta ou mostra a pasta Pessoal no menu Iniciar do Windows.
- **Imagens em Iniciar** - oculta ou mostra a pasta de imagens no menu Iniciar do Windows.
- **Configurações em Iniciar** - oculta ou mostra o aplicativo Configurações no menu Iniciar do Windows.
- **Vídeos em Iniciar** - oculta ou mostra a pasta de vídeos no menu Iniciar do Windows.