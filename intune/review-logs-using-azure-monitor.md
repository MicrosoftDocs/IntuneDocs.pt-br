---
title: Encaminhar logs de auditoria no Azure Monitor usando o Microsoft Intune – Azure | Microsoft Docs
description: Use as Configurações de Diagnóstico para enviar logs de auditoria e logs operacionais no Microsoft Intune para a conta de armazenamento do Azure, hubs de eventos ou análises de log. Escolha por quanto tempo deseja manter os dados e confira custos previstos para locatários de tamanhos diferentes.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f4f93ab1cd2c662cb97dafd19684b353268087f6
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842568"
---
# <a name="send-log-data-to-storage-event-hubs-or-log-analytics-in-intune-preview"></a>Enviar dados de log para o armazenamento, hubs de eventos ou análises de log no Intune (versão prévia)

O Microsoft Intune inclui logs internos que fornecem informações sobre seu ambiente. Os **Logs de Auditoria** mostram detalhes sobre eventos diferentes ou tarefas que ocorrem no Intune. Os **Logs Operacionais (versão prévia)** mostram detalhes sobre usuários e dispositivos que têm êxito (ou falham) no registro.

Esses logs também podem ser enviados aos serviços do Azure Monitor, incluindo contas de armazenamento, hubs de eventos e análises de log. Especificamente, você pode:

* Arquive logs do Intune em uma conta de armazenamento do Azure para manter os dados ou arquivá-los por um tempo definido.
* Transmita os logs do Intune para um hub de eventos do Azure para análise usando ferramentas conhecidas do SIEM (Gerenciamento de Eventos e Informações de Segurança), como Splunk e QRadar.
* Integre logs do Intune com suas próprias soluções de log personalizadas transmitindo-os para um hub de eventos.
* Envie logs do Intune para o Log Analytics para ativar visualizações, monitoramento e alertas avançados sobre os dados conectados.

Esses recursos fazem parte das **Configurações de Diagnóstico** no Intune. 

Este artigo mostra como usar as **Configurações de Diagnóstico** para enviar dados de log para diferentes serviços, oferece exemplos e estimativas de custos e responde a algumas perguntas comuns.

## <a name="prerequisites"></a>Pré-requisitos

Para usar esse recurso, você precisa de:

* Uma assinatura do Azure: Se você não tiver uma assinatura do Azure, você pode [se inscrever para uma avaliação gratuita](https://azure.microsoft.com/free/).
* Um ambiente do Microsoft Intune (locatário) no Azure
* Um usuário que seja **Administrador Global** ou **Administrador de Serviços do Intune** no locatário do Intune.

Dependendo de onde você deseja rotear os dados de log de auditoria, serão necessários um dos serviços a seguir:

* Uma [conta de armazenamento do Azure](https://docs.microsoft.com/azure/storage/common/storage-account-overview) com permissões *ListKeys*. É recomendável que você use uma conta de armazenamento geral e não uma conta de armazenamento de blobs. Para saber mais sobre preços do armazenamento, confira a [Calculadora de preços do armazenamento do Azure](https://azure.microsoft.com/pricing/calculator/?service=storage). 
* Um [namespace de hubs de eventos do Azure](https://docs.microsoft.com/azure/event-hubs/event-hubs-create#create-an-event-hubs-namespace) para se integrar com soluções de terceiros.
* Um [espaço de trabalho de análise de logs do Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) para enviar logs ao Log Analytics.

## <a name="send-logs-to-azure-monitor"></a>Enviar logs ao Azure Monitor

1. No [portal do Azure](https://portal.azure.com/), selecione **Todos os serviços** > filtre por **Intune** > selecione **Intune**.
2. Em **Monitoramento**, escolha **Configurações de diagnóstico**. Ative-a quando abri-la pela primeira vez:

    ![Ativar as configurações de diagnóstico no Intune para enviar logs ao Azure Monitor](media/diagnostics-settings-turn-on.png)

3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome para as configurações de diagnóstico. Essa configuração inclui todas as propriedades que você inserir. Por exemplo, insira `Route audit logs to storage account`.
    - **Arquivar em uma conta de armazenamento**: Salva os dados de log em uma conta de armazenamento do Azure. Use esta opção se quiser salvar ou arquivar os dados.

        1. Escolha esta opção > **Configurar**. 
        2. Escolha uma conta de armazenamento existente na lista > **OK**.

    - **Transmitir para um hub de eventos**: Transmite os logs para um hub de eventos do Azure. Se você quiser que seus dados de log sejam analisados usando ferramentas SIEM, como Splunk e QRadar, escolha essa opção.

        1. Escolha esta opção > **Configurar**. 
        2. Escolha um namespace de hub de eventos existente e a política na lista > **OK**.

    - **Enviar para o Log Analytics**: Envia os dados ao Azure Log Analytics. Se você quiser usar as visualizações, monitoramento e alertas nos logs, escolha esta opção.

        1. Escolha esta opção > **Configurar**. 
        2. Crie um novo espaço de trabalho e insira os detalhes do espaço de trabalho. Ou escolha um espaço de trabalho existente na lista > **OK**.

            O [espaço de trabalho do Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) fornece mais detalhes sobre essas configurações.

    - **LOG** > **AuditLogs**: Escolha esta opção para enviar os [logs de auditoria da Intune](monitor-audit-logs.md) para sua conta de armazenamento, hub de eventos ou análise de logs. Os logs de auditoria mostram o histórico de todas as tarefas que gera uma alteração no Intune, incluindo quem realizou a tarefa e quando.

      Se você optar por usar uma conta de armazenamento, insira também quantos dias deseja manter os dados (retenção). Para manter os dados permanentemente, defina a **Retenção (dias)** como `0` (zero).

    - **LOG** > **OperationalLogs**: Os logs operacionais (versão prévia) mostram o êxito ou falha de usuários e dispositivos que são registrados no Intune. Escolha esta opção para enviar os logs de registro para sua conta de armazenamento, hub de eventos ou log analytics.

      Se você optar por usar uma conta de armazenamento, insira também quantos dias deseja manter os dados (retenção). Para manter os dados permanentemente, defina a **Retenção (dias)** como `0` (zero).

      > [!NOTE]
      > Os logs operacionais estão em versão prévia. Para fornecer comentários, incluindo as informações incluídas nos logs operacionais, vá para [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/suggestions/36613948-diagnostics-settings-feedback) (um novo site é aberto).

    Quando terminar, suas configurações serão semelhantes às seguintes configurações: 

    ![A imagem de exemplo que envia logs de auditoria do Intune para uma conta de armazenamento do Azure](media/diagnostics-settings-example.png)

4. **Salve** suas alterações. A configuração é mostrada na lista. Depois de criadas, é possível alterá-las escolhendo **Editar configuração** > **salvar**.

## <a name="cost-considerations"></a>Considerações de custo

Se você já tiver uma licença do Microsoft Intune, precisará de uma assinatura do Azure para configurar a conta de armazenamento e o hub de eventos. Geralmente, a assinatura do Azure é gratuita. No entanto, você paga para usar os recursos do Azure, incluindo a conta de armazenamento para arquivamento e o hub de eventos para streaming. A quantidade de dados e os custos variam dependendo do tamanho do locatário.

### <a name="storage-size-for-activity-logs"></a>Tamanho do armazenamento para logs de atividade

Cada evento de log de auditoria usa cerca de 2 KB de armazenamento de dados. Para um locatário com 100.000 usuários, você pode ter cerca de 1,5 milhão de eventos por dia. É provável que você precise de cerca de 3 GB de armazenamento de dados por dia. Como as gravações normalmente ocorrem em lotes de cinco minutos, você pode esperar aproximadamente 9.000 operações de gravação por mês.

As tabelas a seguir mostram uma previsão de custo, dependendo do tamanho do locatário. Ele também inclui uma conta de armazenamento v2 de uso geral no oeste dos EUA por pelo menos um ano de retenção de dados. Para obter uma previsão do volume de dados que você espera para seus logs, use a [Calculadora de preços de armazenamento do Azure](https://azure.microsoft.com/pricing/details/storage/blobs/).

**Log de auditoria com 100.000 usuários**

| | |
|---|---|
|Eventos por dia| 1,5 milhão|
|Volume estimado de dados por mês| 90 GB|
|Custo previsto por mês (USD)| US$ 1,93|
|Custo previsto por ano (USD)| US$ 23,12|

**Log de auditoria com 1.000 usuários**

| | |
|---|---|
|Eventos por dia| 15.000|
|Volume estimado de dados por mês| 900 MB|
|Custo previsto por mês (USD)| US$ 0,02|
|Custo previsto por ano (USD)| US$ 0,24|

### <a name="event-hub-messages-for-activity-logs"></a>Mensagens do hub de eventos para os logs de atividade

Os eventos são normalmente agrupados em intervalos de cinco minutos e enviados como uma única mensagem com todos os eventos desse período. Uma mensagem no hub de eventos tem um tamanho máximo de 256 KB. Se o tamanho total de todas as mensagens no período de tempo exceder esse volume, várias mensagens serão enviadas.

Por exemplo, cerca de 18 eventos por segundo geralmente ocorrem em um locatário de grande porte com mais de 100.000 usuários. Isso equivale a 5.400 eventos a cada cinco minutos (300 segundos x 18 eventos). Os logs de auditoria têm cerca de 2 KB por evento. Isso equivale a 10,8 MB de dados. Portanto, 43 mensagens são enviadas ao hub de eventos naquele intervalo de cinco minutos.

A tabela a seguir contém os custos previstos por mês para um hub de eventos básico no oeste dos EUA, dependendo do volume de dados do evento. Para obter uma previsão do volume de dados que você espera para seus logs, use a [Calculadora de preços dos Hubs de Eventos](https://azure.microsoft.com/pricing/details/event-hubs/).

**Log de auditoria com 100.000 usuários**

| | |
|---|---|
|Eventos por segundo| 18|
|Eventos por intervalo de cinco minutos| 5.400|
|Volume por intervalo| 10,8 MB|
|Mensagens por intervalo| 43|
|Mensagens por mês| 371.520|
|Custo previsto por mês (USD)| US$ 10,83|

**Log de auditoria com 1.000 usuários**

| | |
|---|---|
|Eventos por segundo|0,1 |
|Eventos por intervalo de cinco minutos| 52|
|Volume por intervalo|104 KB |
|Mensagens por intervalo|1 |
|Mensagens por mês|8.640 |
|Custo previsto por mês (USD)|US$ 10,80 |

### <a name="log-analytics-cost-considerations"></a>Considerações de custo do Log Analytics

Para revisar os custos relacionados ao gerenciamento do espaço de trabalho do Log Analytics, confira [Gerenciar o custo controlando o volume de dados e a retenção no Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-manage-cost-storage).

## <a name="frequently-asked-questions"></a>Perguntas frequentes

Obtenha respostas para perguntas frequentes e leia sobre problemas conhecidos com logs do Intune no Azure Monitor.

#### <a name="which-logs-are-included"></a>Quais logs são incluídos?

Os logs de auditoria e operacionais (versão prévia) estão disponíveis para roteamento com esse recurso.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-event-hub"></a>Depois de uma ação, quando os logs correspondentes são exibidos no hub de eventos?

Os logs geralmente aparecem no hub de eventos dentro de alguns minutos após a execução da ação. [O que é o Hubs de Eventos do Azure?](https://docs.microsoft.com/azure/event-hubs/) fornece mais informações.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-storage-account"></a>Depois de uma ação, quando os logs correspondentes são exibidos na conta de armazenamento?

Nas contas de armazenamento do Azure, a latência fica entre 5 a 15 minutos após a execução da ação.

#### <a name="what-happens-if-an-administrator-changes-the-retention-period-of-a-diagnostic-setting"></a>O que acontece se um administrador alterar o período de retenção de uma configuração de diagnóstico?

A nova política de retenção será aplicada aos logs coletados após a alteração. Os logs coletados antes da alteração da política não serão afetados.

#### <a name="how-much-does-it-cost-to-store-my-data"></a>Quanto custa armazenar meus dados?

Os custos de armazenamento dependem do tamanho dos logs e do período de retenção que você escolher. Para obter uma lista dos custos previstos para locatários, que dependem do volume de log gerado, confira o [Tamanho do armazenamento para logs de atividade](#storage-size-for-activity-logs) (neste artigo).

#### <a name="how-much-does-it-cost-to-stream-my-data-to-an-event-hub"></a>Quanto custa a transmissão dos meus dados para um hub de eventos?

Os custos de streaming dependem do número de mensagens recebidas por minuto. Para obter detalhes sobre como os custos são calculados e os custos previstos com base no número de mensagens, confira [Mensagens do hub de eventos para os logs de atividade](#event-hub-messages-for-activity-logs) (neste artigo).

#### <a name="how-do-i-integrate-intune-audit-logs-with-my-siem-system"></a>Como faço para integrar os logs de auditoria do Intune com meu sistema SIEM?

Use o Azure Monitor com os Hubs de Eventos para transmitir logs para seu sistema SIEM. Primeiro, [transmita os logs para um hub de eventos](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub). Em seguida, [configure sua ferramenta SIEM](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub#access-data-from-your-event-hub) com o hub de eventos configurado. 

#### <a name="what-siem-tools-are-currently-supported"></a>Atualmente, quais ferramentas SIEM têm suporte?

Atualmente, o Azure Monitor tem suporte no [Splunk](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-integrate-activity-logs-with-splunk), QRadar e [Sumo Logic](https://help.sumologic.com/Send-Data/Applications-and-Other-Data-Sources/Azure_Active_Directory) (abre um novo site). Para saber mais sobre o funcionamento dos conectores, confira [Transmitir dados de monitoramento do Azure para um hub de eventos para consumo por uma ferramenta externa](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs).

#### <a name="can-i-access-the-data-from-an-event-hub-without-using-an-external-siem-tool"></a>Posso acessar os dados de um hub de eventos sem usar uma ferramenta SIEM externa?

Sim. Para acessar os logs a partir de um aplicativo personalizado, você pode usar a [API dos Hubs de Eventos](https://docs.microsoft.com/azure/event-hubs/event-hubs-dotnet-standard-getstarted-receive-eph).

#### <a name="what-data-is-stored"></a>Quais dados são armazenados?

O Intune não armazena todos os dados enviados pelo pipeline. O Intune roteia os dados para o pipeline do Azure Monitor, na autoridade do locatário. Para saber mais, confira [Visão geral do Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview).

## <a name="next-steps"></a>Próximas etapas

* [Arquivar logs de atividade em uma conta de armazenamento](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-azure-monitor-route-logs-to-storage-account)
* [Rotear logs de atividades para um hub de eventos](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub)
* [Integrar os logs de atividade com o Log Analytics](https://docs.microsoft.com/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics)