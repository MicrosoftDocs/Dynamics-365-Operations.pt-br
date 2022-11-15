---
title: Execução visual e colaborativa
description: Este artigo descreve como monitorar pontos de separação, zonas de buffer, ordens planejadas e histórico do seu DDMRP (Planejamento de Requisitos de Material Orientado por Demanda).
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqDDMRPWorkspace, ReqDecouplingPointsStatusByNetFlow, ReqDecouplingPointStatusByOnHand, ReqPlannedOrderForm, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: ce32a4449da8e85f958f212f2c2dfd2841ca6887
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740814"
---
# <a name="visual-and-collaborative-execution"></a>Execução visual e colaborativa

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Este artigo descreve como monitorar pontos de separação, zonas de buffer, ordens planejadas e histórico do seu DDMRP (Planejamento de Requisitos de Material Orientado por Demanda).

## <a name="visually-track-buffers-and-quantities-for-a-selected-item"></a>Rastrear visualmente os buffers e as quantidades de um item selecionado

No Microsoft Dynamics 365 Supply Chain Management, você pode rastrear visualmente como os buffers, as quantidades disponíveis e os níveis de fluxo líquido mudam ao longo do tempo para qualquer produto liberado selecionado. Siga estas etapas para abrir e revisar os gráficos.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione um item liberado que seja configurado como um ponto de separação. (Para obter mais informações, consulte [Posicionamento de estoque](ddmrp-inventory-positioning.md).)
1. No Painel de Ações, na guia **Plano**, selecione **Cobertura do item**.
1. Na página **Cobertura do item**, selecione um registro de cobertura de item que crie um ponto de separação. (Esse registro mostrará o nome de um grupo de cobertura configurado para criar pontos de separação.)
1. Selecione a guia **Disponível**. Essa guia inclui um gráfico que mostra como as quantidades disponíveis são alteradas ao longo do tempo, juntamente com o valor do nível disponível que foi registrado para um período específico, toda vez que o planejamento mestre foi executado. A guia também inclui uma tabela que mostra em qual das seguintes categorias cada nível disponível registrado se enquadra:

    - **Criticamente baixo** – menos da metade do mínimo para o período.
    - **Baixo** – entre a metade do mínimo e o mínimo.
    - **Média disponível** – entre o mínimo e o mínimo mais a zona verde.
    - **Acima da média** – mais que a média.

    ![Histórico de níveis disponíveis na guia Disponível.](media/ddmrp-on-hand-graph.png "Histórico de níveis disponíveis na guia Disponível")

    > [!NOTE]
    > As cores usadas na guia **Disponível** representam intervalos diferentes das cores semelhantes usadas na guia **Valores do buffer**.

1. Para exibir como os valores de buffer foram alterados ao longo do tempo e como eles se comparam aos níveis disponível e de fluxo líquido, selecione a guia **Valores do buffer**.

    ![Histórico de níveis de fluxo líquido e disponível na guia Valores do buffer.](media/ddmrp-buffer-values-graph.png "Histórico de níveis de fluxo líquido e disponível na guia Valores do buffer")

## <a name="track-the-status-and-planned-orders-for-all-decoupling-points"></a>Rastrear o status e as ordens planejadas para todos os pontos de separação

O espaço de trabalho **MRP baseado na demanda** fornece várias ferramentas, com KPIs (indicadores chave de desempenho) e visões gerais do status dos itens do ponto de separação e das ordens planejadas relacionadas. Para abri-lo, vá para **Planejamento mestre \> Espaços de trabalho \> MRP baseado na demanda**.

![Espaço de trabalho MRP baseado na demanda.](media/ddmrp-workspace.png "Espaço de trabalho MRP baseado na demanda")

## <a name="get-overviews-of-decoupling-points-and-planned-orders"></a>Obter visões gerais de pontos de separação e ordens planejadas

Além do espaço de trabalho **MRP baseado na demanda**, o Supply Chain Management fornece várias páginas nas quais é possível exibir informações sobre a configuração do DDMRP, pontos de separação e ordens planejadas. Algumas dessas páginas também fornecem botões convenientes no Painel de Ações que permitem o gerenciamento de buffers, a execução do planejamento mestre e a abertura de outros modos de exibição relacionados.

- Para exibir o status do ponto de separação por nível de fluxo líquido, vá para **Planejamento mestre \> Planejamento mestre \> DDMRP \> Status dos pontos de separação por fluxo líquido**.
- Para exibir o status do ponto de separação por nível de estoque disponível, vá para **Planejamento mestre \> Planejamento mestre \> DDMRP \> Status dos pontos de separação por disponibilidade**.
- Para exibir ordens planejadas dos pontos de separação, vá para **Planejamento mestre \> Planejamento mestre \> DDMRP \> Ordens planejadas para pontos de separação**.
- Para exibir os prazos de entrega separados, vá para **Planejamento mestre \> Planejamento mestre \> DDMRP \> Prazo de entrega separado**.

## <a name="clean-up-decoupling-point-buffer-values"></a>Limpar valores de buffer do ponto de separação

Com o tempo, o sistema criará uma grande quantidade de dados históricos relacionados a cálculos de buffer em andamento. Esses dados históricos farão com que seu volume de dados aumente e possa futuramente afetar o desempenho do sistema. Portanto, é recomendável, ocasionalmente, limpar os valores antigos do buffer de ponto de separação.

> [!WARNING]
> O trabalho de limpeza removerá as configurações de valor de buffer históricas e as informações de fluxo líquido/disponível históricas. Ele não é reversível.

Siga estas etapas para limpar os valores de buffer do ponto de separação.

1. Vá para **Planejamento mestre \> Planejamento mestre \> DDMRP \> Limpar valores de buffer do ponto de separação**.
1. Na caixa de diálogo **Limpar valores de buffer do ponto de separação**, defina os seguintes campos:

    - **Excluir registros anteriores a (dias)** – especifique a idade dos registros mais jovens a serem mantidos, em dias. Todos os registros de valor de buffer do ponto de separação que forem mais antigos do que esse valor serão excluídos.
    - **Plano mestre** – selecione um plano mestre que inclua itens que devem ser afetados por essas limpeza. A limpeza será aplicada a todos os itens no plano depois que as configurações de **Filtro** especificadas nessa caixa de diálogo forem aplicadas.

1. Para limitar o conjunto de registros em que o trabalho em lote deve ser executado, na FastTab **Registros a serem incluídos**, selecione **Filtro** para abrir a caixa de diálogo **Consulta**. Essa caixa de diálogo funciona do mesmo jeito que para outros tipos de [trabalho em segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Na FastTab **Executar em segundo plano**, especifique como, quando e com que frequência a limpeza deve ser feita. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Selecione **OK** para adicionar o novo trabalho a uma fila de lote para execução.
