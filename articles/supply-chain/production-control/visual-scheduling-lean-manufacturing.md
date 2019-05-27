---
title: Agendamento visual para lean manufacturing
description: Este tópico fornece informações sobre o quadro de programação kanban, que o planejador de produção pode usar para controlar e otimizar o plano da produção de trabalhos kanban.
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fdfa78ba0ace5481305d2ab505ed5fc7538e29e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545021"
---
# <a name="visual-scheduling-for-lean-manufacturing"></a>Agendamento visual para lean manufacturing

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre o quadro de programação kanban, que o planejador de produção pode usar para controlar e otimizar o plano da produção de trabalhos kanban.

Este tópico fornece informações sobre o quadro de programação kanban, que o planejador de produção pode usar para controlar e otimizar o plano da produção de trabalhos kanban.

O quadro de programação kanban permite que o planejador de produção controle e otimize o plano da produção de trabalhos kanban. Ele torna o fluxo de trabalhos kanban transparente e fornece ao planejador de produção uma ferramenta que otimiza e ajusta o plano da produção da célula de trabalho de lean manufacturing.

## <a name="visual-scheduling-of-kanban-jobs"></a>Agendamento visual de trabalhos kanban
Um trabalho kanban pode consistir em um ou mais trabalhos kanban. Há dois tipos de trabalhos kanban:

-   Processar
-   Transferência

Só é possível agendar os trabalhos do tipo **Processo**. O trabalho kanban e suas propriedades, como o tempo de atividade, são definidos no fluxo kanban de produção. No fluxo kanban de produção, o trabalho kanban também é atribuído a uma célula de trabalho. A capacidade diária da célula de trabalho é calculada com base na capacidade da célula de trabalho definida no grupo de recursos. É ajustado pelo tempo de trabalho diário no calendário relacionado. Quando um trabalho kanban é agendado, o trabalho carrega a capacidade da célula de trabalho. O quadro de programação kanban fornece os seguintes principais recursos:

-   Uma visão geral gráfica do plano da produção em uma célula de trabalho de lean manufacturing. Essa visão geral mostra os trabalhos do processo kanban nos períodos definidos.
-   Uma ferramenta que permite agendar trabalhos kanban não planejados e reagendar trabalhos programados anteriormente.

## <a name="kanban-schedule-board"></a>Quadro de programação kanban
A página **Quadro de programação kanban** contém sete elementos principais, conforme mostrado na seguinte ilustração. 

![Quadro de programação kanban](./media/kanban-schedule-board-1024x554.png)
1.  Painel de Ação
2.  Filtrar campos
3.  Botão de trabalho não planejados
4.  Nó de período
5.  Trabalho kanban
6.  Barra de capacidade
7.  Escala de tempo

### <a name="view-the-time-scale"></a>Exibir a escala de tempo

O quadro é dividido em períodos, cada um sendo representado como um nó (4). Os nós de período são listados no eixo vertical, e o acesso horizontal representa uma escala de tempo (7) que mostra a duração do período. Um período tem duração de um dia ou uma semana. A duração do período é determinada pela configuração da célula de trabalho selecionada para o quadro de programação kanban (2). Para cada nó de período, o quadro de programação kanban indica quanto os trabalhos kanban agendados estão carregando em relação ao período. Há também uma indicação da produtividade máxima referente ao período. Se a produtividade planejada exceder a produtividade máxima, o período será considerado como sobrecarregado, e aparecerá um símbolo de aviso vermelho. Um trabalho Kanban agendado será mostrado em um período com hora inicial e hora final programadas (5). A duração do trabalho é igual ao tempo de atividade. Os trabalhos kanban aparecerão como sobreposição em um período se seu tempo de atividade exceder o takt time da célula de trabalho.

### <a name="view-job-status"></a>Exibir status do trabalho

Mais informações sobre um trabalho kanban estarão disponíveis na dica de ferramenta que aparece quando você coloca o ponteiro sobre o trabalho. Um símbolo fornece informações sobre o status do trabalho. Por exemplo, um símbolo de relógio indica que o trabalho kanban está vencido.

### <a name="use-colors-to-view-the-kanban-schedule-board"></a>Usar cores para exibir o quadro de programação kanban

Para melhorar a visão geral que o quadro de programação kanban fornece, é possível usar cores para distinguir trabalhos kanban. A cor de um trabalho kanban é configurada no grupo de agendamento de lean manufacturing, no qual é possível agregar os produtos que devem ser produzidos na mesma sequência. O botão **Usar cores do tema** na guia **Quadro** do Painel de Ação permite que você alterne entre as cores do tema do aplicativo e as cores que são configuradas no grupo de agendamento de lean manufacturing. Para cada período, uma barra de capacidade (6) indica quantas horas disponíveis referentes ao período foram carregadas com trabalhos kanban. Se o período estiver sobrecarregado, a barra de capacidade aparecerá mais espessa e em vermelho. Todas essas funções estarão disponíveis na guia **Quadro** do Painel de Ação (1) na parte superior da página **Quadro de programação kanban**.

## <a name="plan-unplanned-jobs"></a>Planejar trabalhos não planejados
É possível agendar trabalhos kanban não planejados na caixa de diálogo **Planejar trabalhos não planejados**. Para abrir essa caixa de diálogo, clique no botão **Trabalhos não planejados** que mostra o número atual de trabalhos não planejados. Como alternativa, clique em **Planejar trabalhos não planejados** na guia **Quadro** do Painel de Ação. A caixa de diálogo mostra uma lista dos trabalhos kanban não planejados da célula de trabalho. É possível usar o campo **Filtrar** para filtrar todos os campos na grade. Por exemplo, você pode filtrar trabalhos kanban de um produto específico. Após ter uma lista filtrada dos trabalhos que deseja agendar, selecione-os na lista e depois clique em **OK**. Para usar o planejamento automático para agendar os trabalhos, defina a opção **Planejamento automático** como **Sim**. Nesse caso, os trabalhos são agendados em um período de acordo com sua data de vencimento. Também é possível agendar os trabalhos por período. Basta selecionar um período no campo **Período**. A seguinte ilustração mostra um exemplo da caixa de diálogo **Planejar trabalhos não planejados**. 

![Caixa de diálogo Planejar trabalhos não planejados](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a>Sequenciar trabalhos kanban no mesmo período
É possível alterar a sequência de um ou mais trabalhos selecionados em um período. Essa capacidade pode ser útil para priorizar alguns trabalhos no período. Como alternativa, pode ser que você queira sequenciar trabalhos com os mesmos atributos de produto, para otimizar a execução do trabalho. Você pode alterar a sequência usando uma operação arrastar e soltar ou usando os itens de menu **Recuar** e **Avançar** na guia **Quadro** do Painel de Ação.

## <a name="reassign-kanban-jobs-across-periods"></a>Reatribuir trabalhos kanban em períodos
Trabalhos podem ser reatribuídos de um período a outro. Esse recurso pode ser útil se um período estiver sobrecarregado e você quiser nivelar a carga para períodos com capacidade sobressalente. Você pode reatribuir trabalhos usando uma operação arrastar e soltar ou usando os itens de menu **Próximo período** e **Período anterior** na guia **Quadro** do Painel de Ação.

## <a name="open-the-kanban-schedule-board"></a>Abrir o quadro de agenda kanban
É possível abrir o quadro de agenda kanban usando o item de menu nas seguintes páginas:

-   Página **Área de produção**
-   Página **Agendamento de trabalhos kanban**
-   Página **Visualização do fluxo de produção**


<a name="additional-resources"></a>Recursos adicionais
--------

[Lean manufacturing – agendamento de trabalhos kanban](lean-manufacturing-kanban-job-scheduling.md)

