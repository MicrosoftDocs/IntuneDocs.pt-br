---
title: Logs de auditoria de atividades do Intune
description: Saiba como examinar os logs de auditoria que registram as atividades do Intune
keywords: 
author: dougeby
manager: dougeby
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: b2f6f6f4829e53d60cc259be220de89cf3f8d97d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="audit-logs-for-intune-activities"></a>Logs de auditoria de atividades do Intune
Os logs de auditoria fornecem um registro das atividades que geram uma alteração no Microsoft Intune. As ações Criar, Atualizar (editar), Excluir e Atribuir, ou as tarefas remotas, geram eventos de auditoria que você pode examinar. Você pode examinar os logs de auditoria da maioria das cargas de trabalho do Intune. 

## <a name="who-can-access-the-data"></a>Quem pode acessar os dados?
Os usuários com as seguintes permissões podem examinar os logs de auditoria:
- Administrador Global
- Administrador de Serviços do Intune
- Os administradores atribuídos a uma função do Intune com permissões de **Dados de auditoria** - **Leitura**

## <a name="audit-logs-for-intune-workloads"></a>Logs de auditoria de cargas de trabalho do Intune
Você pode examinar os logs de auditoria no grupo Monitoramento de cada carga de trabalho do Intune.  
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha a carga de trabalho da qual você deseja examinar os logs de auditoria.
4. No grupo **Monitoramento** da carga de trabalho, escolha **Logs de auditoria**.

## <a name="review-audit-events"></a>Examinar eventos de auditoria
![Logs de auditoria](./media/monitor-audit-logs.png "Logs de auditoria")

Um log de auditoria tem um modo de exibição de lista padrão que mostra os itens a seguir:    

- data e hora da ocorrência
- Iniciado por (Ator)
- Atividade
- Destino(s)
- Category
- Status

Ao clicar em um item no modo de exibição de lista, você obtém todos os detalhes disponíveis sobre ele.

![Logs de auditoria](./media/monitor-audit-log-detail.png "Logs de auditoria")

> [!Note]    
> A seção **Iniciado por (ator)** nos detalhes do log de auditoria fornece informações sobre quem executou a atividade e de onde ela foi executada. Por exemplo, se você executar a atividade no Intune no Portal do Azure, **Aplicativo** sempre listará a **extensão do Portal do Microsoft Intune** e **ID do Aplicativo** sempre usará o mesmo GUID. 
>    
> A seção **Destino(s)** pode listar vários destinos e as propriedades que foram alteradas.  


## <a name="filter-audit-events"></a>Filtrar eventos de auditoria
Cada carga de trabalho tem um item de menu que filtra previamente a categoria de eventos de auditoria associados a essa folha. Uma opção de filtro separada permite alterar categorias diferentes, e detalhes de ação do evento nessa categoria. Você pode pesquisar pelo UPN (por exemplo, o usuário que realizou a ação). Um filtro de intervalo de datas permite as opções de 24 horas, sete dias ou 30 dias. Por padrão, os últimos 30 dias dos eventos de auditoria são exibidos.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Usar a API do Graph para recuperar os eventos de auditoria
Para obter detalhes sobre como usar a API do Graph para recuperar até um ano de eventos de auditoria, consulte [List auditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list).