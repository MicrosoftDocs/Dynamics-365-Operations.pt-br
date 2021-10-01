---
title: Plano de fornecimento
description: Este tópico fornece informações sobre a página Plano de fornecimento e seus recursos.
author: crytt
ms.date: 9/3/2021
ms.topic: article
ms.search.form: ReqSupplyDemandSchedule, ReqSupplyDemandScheduleFilters, ReqSupplyDemandItemDetails, ReqTransFuturesActionsPart, ReqSupplyDemandOverviewLegendPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0760fcd5408d3960dcc55f773b4e09efc3c9f81c
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505548"
---
# <a name="supply-schedule"></a>Plano de fornecimento

[!include [banner](../includes/banner.md)]

A página **Plano de fornecimento** mostra uma visão geral abrangente de fornecimento e demanda de um produto ou família de produtos. As informações são filtradas por localização, plano mestre e períodos. Você também pode usar a página para criar novas ordens, modificar as ordens planejadas existentes e executar o planejamento mestre.

## <a name="open-the-supply-schedule-page"></a>Abrir a página Plano de fornecimento

Você pode abrir a página **Plano de fornecimento** de uma das seguintes maneiras:

- Acesse **Planejamento mestre \> Planejamento mestre \> Plano de fornecimento**. Na caixa de diálogo **Modificar filtro**, especifique o plano e o produto que você está procurando inserindo valores de filtro nos campos fornecidos. (No restante deste tópico, a coleção de valores de filtro que você insere é conhecida como "o filtro" ou "o filtro atual"). Quando terminar, selecione **OK**.
- Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**. Selecione ou abra um produto. Depois, no Painel de Ações, na guia **Plano**, no grupo **Exibir**, selecione **Plano de fornecimento**.
- Acesse **Planejamento mestre \> Configuração \> Previsão de demanda \> Chaves de alocação de itens**. Selecione uma chave de alocação de itens usada como uma família de produtos. Depois, no Painel de Ações, selecione **Plano de fornecimento**.
- Acesse **Planejamento mestre \> Planejamento mestre \> Ordens planejadas**. Selecione ou abra uma ordem planejada. Depois, no Painel de Ações, na guia **Exibir**, no grupo **Exibir**, selecione **Plano de fornecimento**.

> [!NOTE]
> Ao abrir a página **Plano de fornecimento** de um produto, uma família de produtos ou uma ordem planejada, você não precisa inserir valores de filtro. O sistema usará o modelo de período padrão.

## <a name="use-the-supply-schedule-page"></a>Usar a página Plano de fornecimento

A página **Plano de fornecimento** consiste em uma seção superior, a Guia Rápida **Estoque de final do período**, uma Guia Rápida adicional que se torna visível, com base na linha selecionada na seção superior e no painel Quadro de Fatos. (Para abrir o painel Quadro de Fatos e exibir um Quadro de Fatos, selecione **Informações relacionadas** na borda direita da página.)

### <a name="upper-section"></a>Seção superior

A seção superior da página **Plano de fornecimento** contém uma grade que mostra os dados a seguir para um produto ou família de produtos. Esses dados são divididos por períodos definidos pelo valor **Modelo de período** do filtro.

- **Estoque inicial do período** – esta linha mostrará o saldo de estoque esperado no início do período se todas as ordens do sistema ocorrerem.
- **Estoque final do período** – esta linha mostrará o saldo de estoque esperado no final do período se todas as ordens do sistema ocorrerem.
- **Estoque vinculado de final de período** – esta linha mostra o valor do estoque no final do período que está vinculado à demanda futura.
- **Fornecimento líquido de período** – esta linha mostra a diferença entre o fornecimento e a demanda no período.
- **Estoque mínimo** – este nó mostra o estoque de segurança de um produto ou família de produtos. Para expandir ou recolher este nó, selecione-o e, depois, **Expandir** ou **Recolher** na barra de ferramentas. Este nó é mostrado somente quando há estoque de segurança para o produto ou a família de produtos.
- **Demanda** – este nó mostra a demanda por um produto ou família de produtos. A demanda é agrupada por tipo de transação. Para expandir ou recolher este nó, selecione-o e, depois, **Expandir** ou **Recolher** na barra de ferramentas. Os tipos de transação de demanda incluem vendas, transferências e diários de estoque. Este nó é mostrado somente quando há demanda pelo produto ou família de produtos.
- **Fornecimento** – este nó mostra o fornecimento de um produto ou família de produtos. O fornecimento é agrupado por tipo de transação. Para expandir ou recolher este nó, selecione-o e, depois, **Expandir** ou **Recolher** na barra de ferramentas. Os tipos de transação de fornecimento incluem produção, compra e transferências. Este nó é mostrado somente quando há fornecimento do produto ou família de produtos.

Muitos dos botões disponíveis da barra de ferramentas, de exibições do Quadro de Fatos e de exibições de Guia Rápida dependem das suas seleções na seção superior. Em geral, você escolhe um tipo de transação selecionando uma das linhas no nó **Fornecimento** ou **Demanda**. Escolha um período selecionando uma coluna específica para a linha selecionada.

A barra de ferramentas acima da grade na seção superior da página **Plano de fornecimento** fornece os seguintes botões:

- **Expandir/recolher** – expanda ou recolha um nó selecionado, como o nó **Demanda**, o nó **Fornecimento** e seus subnós. (Os nós mostram um prefixo **\[+\]** ou **\[-\]** para indicar se estão recolhidos ou expandidos no momento.)
- **Novo** – abre um menu em que cada comando, por sua vez, abre uma caixa de diálogo ou página que permite adicionar um tipo específico de item para a seleção. Os comandos disponíveis incluem **Fornecimento de previsão**, **Ordem planejada**, **Kanban planejado**, **Nova ordem de produção**, **Ordem de compra** e **Ordem de transferência**.
- **Planejamento mestre** – executar o planejamento mestre. Uma caixa de diálogo é exibida, na qual você pode especificar o plano a ser executado. Por padrão, o campo **Plano mestre** é definido para corresponder ao filtro atual.
- **Relatório de conclusão máx.** – abra a página **Relatório de conclusão máx.** do produto definido no filtro atual.
- **Atualizar ordens planejadas** – abra a página **Ordens planejadas**, que mostra ordens planejadas para o produto ou família de produtos definida no filtro atual.
- **Nível** – propague as ordens planejadas de acordo com as configurações da caixa de diálogo exibida.
- **Política de plano de material por localização** – abra a página **Cobertura de item** para o produto definido no filtro atual.
- **Regra Kanban** – abra a página **Regras Kanban** para o produto definido no filtro atual.

### <a name="fasttabs"></a>Guia Rápidas

A página **Plano de fornecimento** pode conter as seguintes Guia Rápidas:

- **Estoque de final de período** – essa Guia Rápida mostra os dados de estoque final de período em um formato gráfico.
- **Perfil de fornecimento** – esta Guia Rápida mostra os dados de fornecimento em formato gráfico. Ela fica visível quando você seleciona um nó **Fornecimento** ou uma linha abaixo dele na seção superior.
- **Resumo** – esta Guia Rápida mostra detalhes de resumo relacionados ao tipo de transação selecionado na seção superior. Por exemplo, se você selecionar **Vendas** no nó **Demanda**, esta Guia Rápida mostrará os campos relacionados a ordens de venda, como **Linhas de ordem de venda solicitadas** ou **Valor total**. Se você selecionar **Ordens de produção** no subnó **Produção** do nó **Fornecimento**, esta Guia Rápida mostrará os campos relacionados a ordens de produção, como **Ordens de produção agendadas** ou **Totais agendados**. Os valores de campo dependem do período selecionado na seção superior. 
- **\[Tipo de transação\] - \[Período\]** – esta Guia Rápida mostra ordens para o tipo de transação e o período que você selecionou na seção superior. O nome da Guia Rápida reflete essas seleções. Por exemplo, ele pode ter o nome **Ordens de venda - reserva** ou **Ordens de produção - semana 37**.

### <a name="action-pane"></a>Painel de Ação

Os seguintes botões estão disponíveis no Painel de Ações:

- **Modificar filtro** – abre a caixa de diálogo **Modificar filtro**, em que você pode atualizar valores de filtro e reabra a página **Plano de fornecimento**, que reflete as configurações de filtro atualizadas.
- **Mostrar atrasos** – realce as linhas relevantes na seção superior se houver uma ordem atrasada desse tipo de transação.

### <a name="factbox-pane"></a>Painel Quadro de Fatos

Para abrir o painel Quadro de Fatos e exibir um Quadro de Fatos, selecione **Informações relacionadas** na borda direita da página. Os seguintes Quadros de Fatos estão disponíveis na página **Plano de fornecimento**:

- **Detalhes do item** – este Quadro de Fatos mostra informações básicas sobre o produto definido no filtro atual. Ele estará em branco se você tiver definido uma família de produtos no filtro.
- **Ações** – este Quadro de Fatos mostra ações das ordens do tipo de transação selecionado na seção superior.
- **Atrasos** – este Quadro de Fatos mostra atrasos das ordens do tipo de transação selecionado na seção superior.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
