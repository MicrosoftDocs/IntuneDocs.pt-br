---
# required metadata

title: Ser notificado pelos alertas | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 396ea714-0433-4bd5-a934-8d0b477f28e4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ser notificado pelos alertas do Microsoft Intune
Os alertas mantém você em contato com o que está acontecendo no Microsoft Intune.

Por exemplo, alertas podem notificá-lo sobre os eventos a seguir:

-   Um problema com o Exchange Connector que afeta o gerenciamento de dispositivos móveis

-   Foi encontrado malware em um computador

-   Um conflito entre duas políticas do Intune foi detectado


## Como os alertas funcionam
Alertas são gerados com base em **tipos de alertas**, um conjunto de regras pré-configuradas internas ao Intune. Por exemplo, o tipo de alerta **O armazenamento em nuvem tem 10% ou menos de espaço livre** alerta você quando há pouco espaço para armazenar seus aplicativos na nuvem. Você pode habilitar ou desabilitar e configurar as propriedades de cada tipo de alerta. Por exemplo, ao usar o tipo de alerta acima, você pode configurar:

-   **Estado:** Se o tipo de alerta está habilitado ou desabilitado

-   **Gravidade:** A gravidade do alerta


|Severidade|Detalhes|
|--------|-------|
    |![Alerta crítico](../media/Critical-Alert.jpg)|Indica um problema sério que você deve investigar assim que possível, por exemplo, se o malware foi detectado em um computador.|
    |![Alerta de aviso](../media/Warning-Alert.jpg)|Indica um problema que não é grave no momento, mas pode se tornar sério se você não der a devida atenção, por exemplo, atualizações de segurança estão aguardando para serem instaladas.|
    |![Alerta informativo](../media/Informational-Alert.jpg)|Indica informações que não são críticas para suas operações, por exemplo, uma nova versão do Exchange Connector está disponível.|

Outros tipos de alerta podem conter itens diferentes que você pode configurar, como o percentual de dispositivos que deve ser afetado por um problema antes que um alerta seja gerado.

**Quando os critérios de um tipo de alerta são atendidos, um alerta é gerado e exibido no console de administração do Intune.**

Além disso, você pode configurar o Intune para ser notificado por email quando um alerta é gerado.

## Configurando alertas
No [console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Administrador** &gt; **Alertas e Notificações** e, em seguida, escolha uma das seguintes tarefas de configuração:

|Tarefa|Descrição|
|--------|---------------|
|**Tipos de alerta**|Escolha o tipo de alerta que você deseja configurar e siga um destes procedimentos:<br /><br />Escolha **Configurar**. Na caixa de diálogo **Configurar Tipo de Alerta**, defina as configurações desejadas e, em seguida, clique em **OK**.<br /><br />**Habilite** ou **Desabilite** o alerta.<br /><br />Expanda o nó **Tipos de Alertas** e escolha uma categoria para exibir somente os tipos de alertas nesta categoria.|
|**Destinatários**|Escolha **Adicionar** para adicionar um novo endereço de email que receberá as notificações de email que você configurar.<br /><br />Você também pode **Editar** ou **Excluir** os destinatários existentes.<br /><br />Para receber notificações, você também deve adicionar esse endereço de email como um destinatário em **Regras de Notificação**.|
|**Regras de Notificação**|Configura as regras que definem a quem um alerta de email será enviado. Você pode:<br /><br />**Escolher uma regra existente** - Escolha uma regra e clique em **Selecionar Destinatários**. Você pode selecionar todos os destinatários que receberão um email quando um alerta que atenda a essa regra é gerado.<br /><br />**Criar uma nova regra** - insira um nome para a regra, selecione a severidade do alerta e as categorias de alerta que se aplicam às regras, selecione os grupos de dispositivos aos quais a regra se aplica e selecione os usuários que receberão um email quando um alerta é gerado.<br /><br />Você também pode **Habilitar**, **Desabilitar**, **Editar**ou **Excluir** uma regra existente.|

## Trabalhando com alertas
Use as opções a seguir para ajudá-lo a trabalhar com alertas no console de administração do Intune.

|Opção|Descrição|
|----------|---------------|
|**Exibir alertas ativos**|Escolha uma destas:<br /><br />**Exibir um resumo do alerta** - no espaço de trabalho **Painel**, os principais erros são exibidos no painel Alertas. Escolha o painel para ver informações mais detalhadas.<br /><br />Além disso, você pode exibir um resumo do alerta a página **Visão Geral** do espaço de trabalho **Alertas** .<br /><br />**Exibir todos os alertas** - No espaço de trabalho **Alertas**, escolha **Todos os Alertas**.|
|**Exibir avisos**|Escolha uma destas:<br /><br />No espaço de trabalho **Painel**, escolha **Avisos**.<br /><br />No espaço de trabalho **Alertas**, clique em **Todos os Alertas** &gt; **Avisos**.|
|**Fechar um alerta**|Na lista de alertas, escolha o alerta para fechar e, em seguida, clique em **Fechar Alerta**.<br /><br />Alertas fechados são excluídos permanentemente após 90 dias.|
|**Reativar um alerta fechado**|Na lista de alertas, defina o menu suspenso **Filtros** para **Fechado**.<br /><br />Na lista de alertas fechados, selecione o alerta que você deseja reativar e, em seguida, escolha **Reativar Alerta**.|
Os alertas do Intune permanecem ativos até que:

-   O problema que causou o alerta seja resolvido

-   Você feche o alerta manualmente

-   45 dias passaram desde que o alerta foi gerado

> [!TIP] Se o mesmo alerta for gerado por dispositivos em execução em sistemas operacionais diferentes, você poderá ver várias versões do mesmo alerta na lista de alertas.

### Consulte também
[Monitoramento e relatórios com o Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)


<!--HONumber=May16_HO5-->

