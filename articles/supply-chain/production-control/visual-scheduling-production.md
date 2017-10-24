---
title: "Gráfico de Gantt para agendamento de trabalho"
description: "Os planejadores de produção podem controlar e otimizar planejamentos de produção usando gráficos de Gantt."
author: johanhoffmann
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgShopSupervisorWorkspace, ProdTable, ProdTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: cc7543305ac634dfed3779bb83806ee4fd97d7fa
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="gantt-chart-for-job-scheduling"></a>Gráfico de Gantt para agendamento de trabalho

[!include[banner](../includes/banner.md)]

O gráfico de Gantt foi criado para permitir que os planejadores de produção controlem e otimizem o plano da produção. O gráfico de Gantt torna o fluxo de operações transparente e facilita o ajuste da agenda de produção considerando a escassez de materiais ou de recursos. Com isso, os planejadores podem fazer o melhor uso dos recursos disponíveis, minimizar o trabalho em andamento e otimizar as horas de produtividade de ordens de produção.

O gráfico de Gantt é uma representação visual de atividades programadas em um intervalo de tempo definido. As atividades são programadas em recursos com a capacidade definida por um calendário de capacidade. Os seguintes tipos de atividades podem ser exibidos no gráfico de Gantt.

-   Trabalhos de ordens de produção que são trabalhos programados.
-   Trabalhos de ordens de produção planejadas.
-   Atividades de projetos programados de trabalhos do tipo Previsões de horas.

O gráfico de Gantt pode ser aberto em duas diferentes exibições, **Modo de exibição de ordem** e **Modo de exibição de recurso**[.](https://authoring.help.dynamics.com/en/?post_type=incsub_wiki&p=1665154&preview=true)No **Modo de exibição de ordem**, as atividades são agrupadas em ordens de produção. Isso pode ser útil, por exemplo, se você quiser manter uma visão geral de todos os trabalhos pertencentes às mesmas ordens. No **Modo de exibição de recurso**, todos os trabalhos são agrupados em recursos individuais. Essa exibição pode ser útil na otimização do plano em nível de recurso, como uma máquina ou um grupo de máquinas. O gráfico de Gantt exibido nas ilustrações abaixo mostra **Modo de exibição de ordem** e **Modo de exibição de recurso** com estes principais elementos:

1.  Atividade de gráfico de Gantt
2.  Ícone de escassez de material
3.  Ícone de disponibilidade de material
4.  Ícone de data de entrega da ordem
5.  Barra de capacidade

## <a name="order-view"></a>Modo de exibição de ordem

[![Modo de exibição de ordem](./media/orderview.png)](./media/orderview.png)

## <a name="resource-view"></a>Modo de exibição de recurso
[![Modo de exibição de recurso](./media/resview.png)](./media/resview.png)

## <a name="activities"></a>Atividades
As atividades aparecem como barras e são organizadas em uma grade de escala de tempo com horas inicial e final programadas, tornando a extensão das barras proporcional ao tempo necessário para concluir a atividade. As atividades são exibidas de acordo com uma escala de tempo. É possível ajustar a escala de tempo no menu ao selecionar uma data inicial e final e uma unidade de tempo, como horas ou dias. Ajustando a escala de tempo, você pode definir o foco em um intervalo de tempo no qual deseja gerenciar as atividades. 

Para obter uma melhor visão geral, há diferentes opções para controlar a cor das atividades. Você pode configurar uma cor individual para as atividades, usar a cor de tema que é o tema de cor geral usado no aplicativo ou configurar a cor para que ela seja controlada pelo código de cor das ordens de produção. 

O intervalo de tempo das atividades tem uma sombra em segundo plano. Períodos com uma sombra branca indicam um intervalo de tempo com capacidade definida no recurso da atividade, enquanto períodos com uma sombra cinza indicam intervalos de tempo sem capacidade definida. 

No lado esquerdo do gráfico, há informações adicionais sobre a atividade, como o recurso no qual a atividade está programada e o número de ordem de produção. A conexão entre trabalhos pertencentes à mesma ordem é mostrada com uma seta. 

Você pode obter mais informações sobre uma atividade na caixa de diálogo de atividades. Para abrir a caixa de diálogo, clique duas vezes na atividade ou selecione o menu **informações**. Na caixa de diálogo de atividades, é possível ver a data inicial e final programada e as informações de tempo sobre quais materiais a atividade está programada para consumir. 

As atividades podem ser agrupadas em níveis de agrupamento. Os níveis de agrupamento são hierárquicos e podem ser usados para fazer um agrupamento lógico das atividades. Por exemplo, se houver um layout no qual as atividades de fabricação são agrupadas por local, unidades de produção, grupos de recurso e recursos, é possível usar os níveis de agrupamento para agrupar as atividades de acordo com esse layout. Os níveis de agrupamento podem ser expandidos e recolhidos no nível de agrupamento individual ou em todos os níveis do gráfico usando os botões **Expandir tudo** e **Recolher tudo** no menu. Você também pode configurar os níveis de agrupamento para que eles sejam expandidos ou recolhidos quando o gráfico estiver aberto.

### <a name="material-availability"></a>Disponibilidade de materiais

O gráfico de Gantt pode ser configurado para fornecer ao planejador informações detalhadas sobre o status do material em relação às atividades individuais. Por exemplo, isso pode ser útil se o material for exibido e estiver afetando o plano de produção. Nesse caso, os problemas com material serão destacados no gráfico de Gantt para ajudar o planejador a entender as consequências e fazer os ajustes necessários. 

Um trabalho aparecerá com ícone de escassez de material se a data inicial programada do trabalho for posterior à data de disponibilidade do material consumido pelo trabalho. A data de disponibilidade do material é calculada com base nas informações de vinculação no plano mestre dinâmico. O ícone de escassez de material aparecerá, por exemplo, em um trabalho que está consumindo um material vinculado a uma ordem de compra com um recibo posterior à data inicial planejada do trabalho.

### <a name="indicator-of-material-availability-date"></a>Indicador de data de disponibilidade do material

Ao configurar o gráfico para que ele exiba trabalhos com escassez de material, um ícone para mostrar a data de disponibilidade do material também pode ser exibido. O ícone será mostrado apenas se a data de disponibilidade do material estiver dentro do intervalo de tempo definido do gráfico. Se a data de disponibilidade do material estiver fora do intervalo de tempo definido, informações mais detalhadas sobre disponibilidade de material poderão ser recuperadas da lista de materiais na caixa de diálogo do trabalho. Na lista, também há um ícone mostrando materiais em atraso do trabalho. Você pode programar um trabalho usando a data de disponibilidade do material como data inicial.

### <a name="indicator-of-order-delivery-date"></a>Indicador da data de entrega da ordem

Esse ícone indica a data de entrega de uma ordem de produção. O ícone só é visível no Modo de exibição de ordem.

### <a name="capacity-bar"></a>Barra de capacidade

Você pode configurar o gráfico para que ele mostre uma barra de capacidade de recurso. Essa barra fornece uma visão geral da capacidade de recurso de uma atividade no intervalo de tempo definido do gráfico. A barra de capacidade não é mostrada em relação a períodos de tempo nos quais o recurso não está reservado. Em períodos nos quais o recurso está reservado para capacidade, a barra de capacidade é exibida como uma barra sólida. Em períodos nos quais o recurso está excessivamente reservado, a barra aparecerá mais espessa e em vermelho. Por exemplo, se dois trabalhos se sobrepuserem, a barra de capacidade indicará reserva excessiva no intervalo de tempo onde há sobreposição. A barra de capacidade é atualizada dinamicamente quando você agenda um trabalho. Habilite a barra de capacidade no menu **Mostrar barra de capacidade**. Só é exibida no **Modo de exibição de recurso**. Para obter uma visão mais detalhada da capacidade máxima em um recurso, use o gráfico **Capacidade máxima**, que pode ser aberto no menu ou no menu de contexto de uma atividade selecionada.

## <a name="job-scheduling-in-the-gantt-chart"></a>Agendamento de trabalho no gráfico de Gantt
O gráfico de Gantt oferece diferentes opções para fazer ajustes no plano de produção. No gráfico de Gantt, você pode reagendar atividades com uma interação de arrastar e soltar ou em um menu de agenda. No processo de planejamento, é possível considerar capacidade de recurso, capacidades do recurso e restrições de material.

### <a name="schedule-a-job-as-a-drag-and-drop-interaction"></a>Agendar um trabalho como interação de arrastar e soltar

Você pode reagendar um trabalho no intervalo de tempo definido como uma interação de arrastar e soltar. Só é possível reagendar o trabalho no mesmo recurso e só é possível agendar um trabalho de cada vez.

### <a name="schedule-a-job-from-the-menu"></a>Agendar um trabalho no menu

No menu **Agendar trabalhos**, você pode agendar um ou mais trabalhos selecionados no gráfico com base em uma direção de agendamento e uma data e hora de agendamento. Há três direções de agendamento disponíveis.

-   Avançar a partir da data do plano
-   Voltar a partir da data do plano
-   A partir da data de disponibilidade do material

Não é possível agendar um trabalho fora do intervalo de tempo definido do gráfico de Gantt. Se fizer isso, o trabalho ficará não programado e você receberá a mensagem de erro "Não foi possível agendar o trabalho no período carregado".

### <a name="schedule-previous-jobs"></a>Agendar trabalhos anteriores

Em uma rede de atividades, como trabalhos pertencentes à mesma ordem de produção, é possível usar a função **Agendar trabalhos anteriores** para agendar os trabalhos anteriores relativos a um trabalho selecionado na rede. No seguinte exemplo, a atividade em destaque é o trabalho selecionado. O diagrama mostra antes um trabalho anterior que é programado e depois o trabalho anterior que é programado. 

[![Agendar trabalho anterior](./media/schprevjob3.png)](./media/schprevjob3.png)

### <a name="schedule-next-jobs"></a>Agendar próximos trabalhos

É possível usar a função **Agendar próximos trabalhos** para agendar os próximos trabalhos relacionados a um trabalho selecionado em uma rede de atividades. No seguinte exemplo, a atividade em destaque é o trabalho selecionado. O diagrama mostra antes o próximo trabalho que é programado e depois o próximo trabalho que é programado. 

[![Agendar próximo trabalho](./media/schnxtjob.png)](./media/schnxtjob.png)

### <a name="schedule-around-job"></a>Agenda em torno de trabalho

É possível usar a função **Agenda em torno de trabalho** para agendar o próximo trabalho e o trabalho anterior relacionados a um trabalho selecionado em uma rede de atividades. No seguinte exemplo, a atividade em destaque é o trabalho selecionado. O diagrama mostra antes um trabalho anterior que é programado e depois o trabalho anterior que é programado. 

[![Agenda em torno de trabalho](./media/scharoundjob1.png)](./media/scharoundjob1.png)

### <a name="arrange-jobs"></a>Organizar trabalhos

É possível usar a função **Organizar** para organizar as atividades selecionadas no mesmo recurso. Essas atividades podem estar na mesma rede de atividades, mas também podem pertencer a diferentes redes. Quando você usa a função de organização, os intervalos de tempo entre as atividades selecionadas serão eliminados. Você pode usar essa função para otimizar a utilização de capacidade dos recursos. O diagrama mostra antes um trabalho anterior que é programado e depois o trabalho anterior que é programado. 

[![Organizar trabalho](./media/arrangejobs1.png)](./media/arrangejobs1.png)

### <a name="reassign-activities-from-one-resource-to-another"></a>Reatribuir atividades de um recurso para outro

Você pode reatribuir um trabalho de um recurso para outro. Isso pode ser útil em situações nas quais uma máquina está fora de serviço ou excessivamente reservada e você precisa encontrar outro recurso disponível que possa fazer o trabalho.

### <a name="reassigning-an-activity-as-a-drag-and-drop-interaction"></a>Reatribuindo uma atividade como uma interação de arrastar e soltar

Na exibição **Recurso**, é possível reatribuir uma atividade a um recurso diferente no gráfico de Gantt como uma interação de arrastar e soltar. Para fazer isso, selecione a linha na qual a atividade está agendada. Após a seleção da linha, você pode arrastá-la até o recurso no gráfico agrupado em um nível de agrupamento de recursos diferente.

### <a name="reassigning-an-activity-from-the-schedule-jobs-menu"></a>Reatribuindo uma atividade no menu Agendar trabalhos

Você pode reatribuir um trabalho na caixa de diálogo **Agendar trabalho** aberta no menu **Agendar trabalho**. Nesse menu, só é possível reatribuir um trabalho a um recurso que já está carregado no gráfico de Gantt. Se apenas um trabalho for selecionado, a lista suspensa do recurso será classificada por recursos aplicáveis. Se mais trabalhos forem selecionados, não haverá mais informações sobre recursos aplicáveis na lista de recursos.

## <a name="load-additional-resources-to-the-gantt-chart"></a>Carregar recursos adicionais no gráfico de Gantt
No **Modo de exibição de recurso**, há uma opção de carregar recursos adicionais no gráfico de Gantt. Isso pode ser útil para encontrar um recurso alternativo para um trabalho que está agendado em uma máquina excessivamente reservada ou quebrada. Na página **Carregar recursos adicionais**, você obterá uma lista de recursos que são eficientes quanto a data como a data em que a lista é aberta. Recursos aplicáveis, relacionados a um trabalho selecionado no gráfico de Gantt, serão listados primeiro. Se houver vários trabalhos selecionados, antes de abrir a lista, nenhuma indicação de recursos aplicáveis será mostrada. Na página **Carregar recursos adicionais**, você pode selecionar um ou mais recursos, que serão carregados no gráfico de Gantt quando você confirmar sua seleção. Se não houver trabalhos agendados no recurso selecionado no intervalo de tempo do gráfico de Gantt, o recurso será colocado em um nível de agrupamento de recursos na parte inferior da lista de atividades no gráfico de Gantt.

### <a name="access-the-gantt-chart"></a>Acessar o gráfico de Gantt

O gráfico de Gantt pode ser aberto nas seguintes páginas.

| **Página**                                                                                     | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Lista e detalhe de ordem de produção**                                                         | Na página **Lista e detalhe de ordem de produção**, você pode abrir o gráfico de Gantt de uma ou mais ordens selecionadas. Abrir o gráfico no item de menu **Gráfico de Gantt** carregará não só todos os trabalhos relacionados às ordens de produção selecionadas, mas também os trabalhos de outras ordens de produção que são agendadas nos mesmos recursos. Abrir o gráfico no item de menu **Gráfico de Gantt - Exibição rápida** só carregará trabalhos relacionados às ordens de produção selecionada. Nessa exibição, não é possível agendar trabalhos. |
| **Recurso**                                                                                 | Na página **Recurso**, é possível abrir o gráfico de Gantt no item de menu **Gráfico de Gantt**. Quando selecionados, todos os trabalhos agendados no recurso em um intervalo de tempo selecionado serão carregados no gráfico.                                                                                                                                                                                                                                                                                                   |
| **Grupo de recursos**                                                                           | Na página **Grupo de recursos**, é possível abrir o gráfico de Gantt no item de menu **Gráfico de Gantt**. Quando selecionados, todos os trabalhos agendados nos recursos no grupo de recursos serão mostrados em um intervalo de tempo selecionado.                                                                                                                                                                                                                                                                                    |
| **Gráficos de Gantt**                                                                             | Na página **Gráficos de Gantt**, você pode configurar gráficos de Gantt por recursos e grupos de recursos. Por exemplo, para controlar atividades de produção de conjuntos específicos de recursos ou grupos de recursos, é possível fazer configurações individuais destes na página **Gráficos de Gantt**. Você pode abrir o gráfico de Gantt em cada configuração.                                                                                                                                                    |
| **Previsões de horas** (projeto)                                                                 | Atividades de projeto do tipo **Previsão de horas** podem ser trabalhos agendados em recursos. Na página **Previsão de horas** no menu **Agendamento**, você pode abrir o gráfico de Gantt em uma ordem para ver as atividades de projeto agendadas de trabalho de tipo previsão de horas.                                                                                                                                                                                                                                                             |
| **Trabalho a ser concluído** (Lista no espaço de trabalho **Gerenciamento de piso de produção**)                      | O espaço de trabalho **Lista de trabalhos a serem concluídos no Gerenciamento de piso de produção** mostra os trabalhos de ordens de produção e lote que estão em progresso nos recursos selecionados do espeço de trabalho. No item de menu **Gráfico de Gantt**, você pode abrir o gráfico de Gantt, no qual todos os trabalhos selecionados na lista serão carregados no gráfico.                                                                                                                                                                                |
| **Ordens de produção a liberar** (Aberta no espaço de trabalho **Gerenciamento de piso de produção**) | A página Ordens de produção a liberar é aberta no espaço de trabalho **Gerenciamento de piso de produção**. Essa página mostra a liberação pendente de ordens de produção e lote agendadas. Nessa página, você pode abrir o gráfico de Gantt das ordens de produção selecionadas.                                                                                                                                                                                                                                                        |
## <a name="see-also"></a>Consulte também  
[Agendamento visual com gráfico de Gantt para ordens de produção e de lote (Vídeo)](https://youtu.be/BtbuShkGj4I)


