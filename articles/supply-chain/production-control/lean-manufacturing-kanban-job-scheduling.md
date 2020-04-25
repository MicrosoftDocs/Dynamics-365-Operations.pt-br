---
title: Agendamento do trabalho kanban para lean manufacturing
description: Este artigo fornece informações sobre o controle visual sobre a programação de trabalhos kanban e várias formas agendar trabalhos kanban.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18326fdc931faf1aecd4b8b69fefed8b90c191ab
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211459"
---
# <a name="kanban-job-scheduling-for-lean-manufacturing"></a>Agendamento do trabalho kanban para lean manufacturing

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre o controle visual sobre a programação de trabalhos kanban e várias formas agendar trabalhos kanban.  

A página **Agendamento de trabalhos kanban** fornece controle visual das agendas de células de trabalho de lean manufacturing. Ela oferece uma visão geral de todos os trabalhos kanban e fornece vários recursos de filtragem. Nesta página, você pode mover para todas as outras páginas relacionadas à configuração e execução do kanban.

## <a name="automatic-scheduling-of-kanban-jobs"></a>Agendamento automático de trabalhos kanban
O planejamento pode ser disparado automaticamente se você definir o parâmetro **Quantidade planejamento automático** na regra kanban. Se você definir **Quantidade de planejamento automático** como **1**, cada trabalho kanban será planejado imediatamente quando for criado. O resultado é uma série de operações por ordem de chegada. Se você definir **Quantidade de planejamento automático** com um valor maior que 1, os trabalhos kanban serão agrupados antes de serem planejados. 

Este conceito permite a redução de tamanhos do kanban abaixo dos tamanhos reais do lote econômico. Por exemplo, o tamanho de lote econômico para um item específico (ou a família de itens) é 30. Em vez de criar os kanbans que usam a quantidade de produto 30, você pode configurar a regra kanban, de forma que ela tenha uma quantidade de produtos igual a 10 e um valor de **3** para **Quantidade de planejamento automático**. Embora o planejamento automático agende os trabalhos kanban para a célula de trabalho somente quando existem três trabalhos não planejados, é totalmente transparente para o planejador e o supervisor de chão de fábrica que dois trabalhos não planejados podem estar aguardando execução. O planejador ou gerente de chão de fábrica pode executar esses dois trabalhos na produção, planejando-os manualmente ou criando kanbans adicionais.

## <a name="manual-scheduling"></a>Agendamento manual
Para agendamento manual, o Microsoft Dynamics AX 2012 apresentou o quadro de agendamento kanban. O agendamento manual pode ser combinado com o agendamento automático. O quadro de agendamento kanban permite que você planeje e cancele o planejamento de trabalhos, mova-os em sequência ou mova-os de período para período. Os trabalhos se baseiam em uma regra kanban onde o valor de **Planejamento automático** é maior que **0** e pode ser definido manualmente como não planejado. No entanto, esses trabalhos serão replanejados quando o próximo evento de planejamento automático ocorrer (isto é, quando um novo kanban for criado). As seguintes opções estão disponíveis para o agendamento manual:

-   **Agenda** agenda os trabalhos selecionados de acordo com a data de vencimento. (Esta opção é semelhante ao planejamento automático.)
-   **Agendar a partir da data** tenta agendar os trabalhos selecionados de acordo com a data de vencimento, mas restringe o resultado usando a data de início mais próxima especificada.
-   **Voltar** retorna os trabalhos agendados selecionados para a sequência no período.
-   **Avançar** avança os trabalhos agendados selecionados na sequência com o período.
-   **Período anterior** move os trabalhos agendados selecionados para o início ou final do período anterior.
-   **Próximo período** move os trabalhos agendados selecionados para o início ou final do próximo período.
-   **Plano** &gt; **Reverter status de trabalho** permite que você cancele o agendamento de um trabalho agendado.

## <a name="lean-scheduling-groups"></a>Grupos de agendamento de lean manufacturing
Cada cor representa um grupo de agendamento de lean manufacturing Os grupos de agendamento de lean manufacturing podem ser definidos livremente como grupos genéricos ou grupos que pertencem a uma única célula de trabalho. Os itens e dimensões podem ser atribuídos livremente aos grupos de agendamento. Por exemplo, em uma célula Pintura, um grupo de agendamento pode representar uma cor do produto. No trabalho que é controlado por requisitos de ferramentas específicos, os itens podem ser agrupadas pelo requisito da ferramenta, e uma célula de trabalho de embalagem pode agrupar itens por modelo de embalagem. O uso de cores em grupos de agendamento de lean manufacturing é opcional, mas recomendável. Melhora a visibilidade no status do plano. Por exemplo, é muito fácil ver o dia em que as cores são geradas, e você consegue identificar rapidamente como esse trabalho pode ser otimizado.

## <a name="work-cell-capacity-and-period-capacity"></a>Capacidade da célula de trabalho e capacidade de período
A capacidade de uma célula de trabalho de lean manufacturing é sempre uma capacidade simultânea. Ou seja, vários trabalhos podem estar ativos em uma célula de trabalho ao mesmo tempo. A capacidade pode ser rastreada de duas maneiras: produtividade e horas.

### <a name="throughput"></a>Produtividade

A capacidade de uma célula de trabalho é definida pela quantidade média de produtividade de um período de referência (dia útil padrão, semana ou mês). A capacidade real por dia ou semana é calculada com base nos horários de trabalho do calendário atribuído à célula de trabalho. A capacidade que é carregada por trabalho é a quantidade do trabalho, ajustada pelo índice de produtividade na célula de trabalho.

### <a name="hours"></a>Horas

A capacidade disponível por dia ou semana é definida pelo calendário atribuído à célula de trabalho. A capacidade que é carregada por trabalho é o tempo de ciclo da atividade, ajustado pela quantidade (quantidade de atividade padrão versus quantidade de trabalho real) e pelo índice de produtividade na célula de trabalho.

#### <a name="period-capacity-factbox"></a>Quadro de Fatos de capacidade do período

A página de listagem **Agendamento do trabalho kanban** contém um Quadro de Fatos que mostra a capacidade de período disponível e reservado para a célula de trabalho selecionada. Dependendo dos períodos de agendamento selecionados no modelo do fluxo de produção, os períodos mostram dias ou semanas.

<a name="additional-resources"></a>Recursos adicionais
--------



