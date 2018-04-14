---
title: "Média de movimentos"
description: "A média de movimentos é um método de avaliação de custo perpétuo baseado no princípio da média, no qual os custos das saídas de estoque não são alterados quando os custos de compra mudam. A diferença é capitalizada e baseia-se em um cálculo proporcional. O valor restante é despesa."
author: AndersGirke
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c1f8a8cf4a58177d423709f245760a5ba9ca7e4e
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="moving-average"></a>Média de movimentos

[!INCLUDE [banner](../includes/banner.md)]

A média de movimentos é um método de avaliação de custo perpétuo baseado no princípio da média, no qual os custos das saídas de estoque não são alterados quando os custos de compra mudam. A diferença é capitalizada e baseia-se em um cálculo proporcional. O valor restante é despesa. 

Ao usar a média móvel, as liquidações de estoque e marcação do estoque não são suportados. O fechamento de estoque não afeta os produtos que têm a média móvel, como o grupo de modelos de estoque, e não gera nenhuma liquidação entre as transações.

Estes são pré-requisitos quando você usa custo da média móvel como um método de avaliação de custo.

1.  Na página **Grupos de modelos de item**, configure um grupo de modelos de item com a Média de movimentos selecionada no campo **Modelo de estoque**. **Observação:** Por padrão, quando a média móvel for selecionada, os campos **Lançar estoque físico** e **Lançar estoque financeiro** também são selecionados. 

2.  Na página **Lançamento**, atribua as contas às contas de **Diferença de preço da média de movimentos** e de **Reavaliação de custos da média de movimentos** na guia **Estoque**. Você usa a conta **Diferença de preço da média de movimentos** quando o custo for gasto proporcionalmente. Isso ocorre devido a uma diferença de custo entre o recebimento da compra e a fatura de compra, e por causa de uma diferença entre a quantidade de estoque original e a quantidade disponível atual. Use a conta **Reavaliação de custos da média de movimentos** quando você desejar ajustar o custo da média móvel para um produto para um novo preço unitário.
3.  Na página **Produtos liberados**, atribua o grupo de modelos de item da média móvel ao produto. **Observação:** O processo de fechamento de estoque fecha somente o período contábil. Ele não afeta os produtos que têm a média móvel atribuída a eles como um grupo de modelos do item.

## <a name="convert-to-the-moving-average-costing-method"></a>Converte para o método de avaliação de custo da média móvel
Os produtos podem ser convertidos para usar o método de avaliação de estoque de média móvel. Esse tipo de conversão é normalmente feita no final do ano, depois que o último mês do ano atual é fechado. Ela é feita usando o modelo de avaliação de custo atual do produto. Você pode alterar o método de avaliação de custo de estoque de um método de avaliação de custo que é baseado no custo médio para um método baseado na média móvel. 

Se você está alterando seu método de avaliação de custo de um método padrão para um de média móvel, você tem que realizar as seguintes tarefas:

1.  Faça ajustes para obter as quantidades em estoque e valores 0 (zero).
2.  Depois que o valor e a quantidade do estoque for 0 (zero), altere o grupo de modelos de item para a média móvel.
3.  Faça ajustes para obter a quantidade e o valor de volta ao estoque.

Você não pode alterar o método de avaliação de custo do estoque de um método de média móvel para o método Primeiro a entrar, primeiro a sair (PEPS), Último a entrar, Primeiro a sair (UEPS) ou de média ponderada.

**Observação:** A conversão de custo padrão para média ponderada móvel é um processo manual.

Os exemplos a seguir ilustram o impacto de usar o método de avaliação de custo de média móvel. Existem quatro configurações:
-   Diferença entre custo de ordem de compra e despesa proporcional
-   Produtos de média móvel e ajuste de estoque
-   Média móvel com produção
-   Média móvel com transação de datas anteriores

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>Diferença entre custo de ordem de compra e despesa proporcional
Com a média móvel, o custo do produto é determinado pelo recebimento da compra. Quando a fatura de compra é lançada, se houver uma diferença de custo entre o recebimento da compra e a fatura de compra, a diferença será ajustada proporcionalmente para os produtos em estoque no momento, e qualquer valor restante será despesa. 

Neste exemplo, uma ordem de compra é criada e recebida por um custo, e a fatura de compra é lançada com um custo diferente.

1.  Crie uma ordem de compra para uma quantidade de 2 e preço unitário de R$ 10,00.
2.  Crie um recebimento de compra do produto.
3.  Crie uma ordem de venda para uma quantidade de 1 e preço unitário de R$ 10,00.
4.  Crie uma fatura de compra para uma quantidade de 2 e preço unitário de R$ 12,00.

A diferença no preço unitário, R$ 2,00, será lançada na conta Diferença de preço da média de movimentos quando a fatura de compra for lançada. O motivo é que dois produto foram comprados a um custo de R$ 20,00. Um dos produtos foi vendido por um preço unitário de R$ 10,00. A fatura de compra foi lançada ao preço unitário de 12,00 com uma quantidade de 2. O preço unitário de produto não pode ser lançado em 14,00.

## <a name="moving-average-product-and-inventory-adjustment"></a>Produtos de média móvel e ajuste de estoque
Se precisar ajustar o custo da média móvel de um produto, os ajustes de estoque são autorizados a partir da data de hoje. Não é possível realizar um ajuste de estoque de datas anteriores para corrigir o custo da média móvel de um produto. Você não pode propagar os custos em transações subsequentes. 

Neste exemplo, o custo da média móvel será ajustado para um produto.

1.  Selecione o produto para o qual você deseja ajustar o custo de média móvel. **Observação:** A página **Reavaliação da média de movimentos** examina o estoque disponível de um produto. O produto selecionado tem uma quantidade lançada de 1, um valor lançado de R$ 12,00, um custo unitário lançado de R$ 12,00 e um custo unitário de R$ 12,00.
2.  Atualize o campo **Custo unitário** para 16,00. O sistema calcula os campos restantes.
3.  O ajuste é lançado.

**Observação:** Você só pode ajustar o custo da média móvel a partir da data de hoje.

Na página **Liquidações do comprovante**, você pode ver um ajuste de 4.00 lançado na conta Reavaliação de custos da média de movimentos.

## <a name="moving-average-with-production"></a>Média móvel com produção
A média móvel suporta itens produzidos. Se você pretende usar a média móvel em um ambiente de produção, o controle deslizante **Usar preço de custo previsto** na página **Parâmetros de controle de produção** deve ser selecionado. Isso significa que o preço de custo que é calculado durante a previsão é usado, em vez do preço de custo real de cálculo de BOM.

## <a name="moving-average-with-a-backdated-transaction"></a>Média móvel com transação de datas anteriores
Os custos da média móveis atuais são atribuídos às transações de datas anteriores e a quantidade física do produto é atualizada, mas o custo da média móvel do produto não é afetado. Neste exemplo de média móvel, uma transação de data antiga para um produto de média móvel é lançada.

1.  Crie um ajuste de estoque para o produto de média móvel para uma quantidade de 1 e um custo de R$ 20,00.
2.  O histórico de transações de estoque para o produto assemelha-se ao seguinte:
    -   Uma transação de estoque de 1, um custo de R$ 16,00, uma data de lançamento de 15 de janeiro e uma data de transação de 15 de janeiro.
    -   Um ajuste de estoque de 1, um custo de R$ 20,00, uma data de lançamento de 1º de janeiro e uma data de transação de 15 de janeiro.
3.  Lance o ajuste.

Na página **Transações de estoque** você verá que R$ 4,00 foram gastos, já que a média móvel atual do produto é R$ 16,00. Você poderá lançar no passado, mas a diferença de custo é despesa, para que o custo da média móvel não seja afetado.

## <a name="inventory-value-report"></a>Relatório de valor de estoque
Neste exemplo de média móvel, o relatório de valor de estoque é impresso para oferecer suporte ao cálculo atual da média móvel para um produto. O relatório Valor do estoque pode imprimir as transações em ordem cronológica, junto com o custo para oferecer suporte ao cálculo do custo de média móvel de um produto. O relatório exibe o custo de média móvel para o produto. Na caixa de diálogo **Relatórios de valor de estoque**, um Intervalo de dados permite que você selecione a **Hora da transação** ou a **Data de lançamento** no qual o relatório será classificado. A opção **Data de lançamento** é como o relatório é impresso tradicionalmente. A opção **Hora da transação** é a data real em que a transação é relatada e o custo de média móvel do produto é atualizado. É possível imprimir o relatório Valor do estoque usando a opção**Classificação de tempo da transação** se quiser ver o cálculo de custo de média móvel ao longo do tempo. A tabela a seguir exibe as transações do produto para o qual o relatório é impresso quando a opção **Classificação de tempo da transação** for usada.

| Hora da transação | Data         | Tipo de transação           | A quantidade | Valor | Custo médio da unidade |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 1 de outubro    | Saldo inicial          | 0        | 0,00   | 0,00              |
| 8 de outubro        | 28 de setembro | Recebimento em data anterior          | 1        | 16,00  | 16,00             |
| 3 de outubro        | 3 de outubro    | Recebimento de compra           | 2        | 20,00  | 12:00             |
| 5 de outubro        | 5 de outubro    | ordem de venda                | -1       | -10,00 | 13,00             |
| 7 de outubro        | 7 de outubro    | Fatura de compra           |          | 2,00   | 14,00             |
| 8 de outubro        | 8 de outubro    | Reavaliação da média de movimentos |          | 4,00   | 16,00             |
|                  | 31 de outubro   | Total                      | 2        | 32,00  | 16,00             |

 **Observação:** Não é possível reconciliar a contabilidade com o estoque usando a opção **Classificação de tempo da transação**. O relatório deve ser impresso usando a opção **Data de lançamento**.






