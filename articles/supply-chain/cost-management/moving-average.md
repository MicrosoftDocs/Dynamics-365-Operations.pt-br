---
title: Média móvel
description: A média móvel é um método de avaliação de custo perpétuo baseado no princípio da média, no qual os custos das saídas de estoque não são alterados quando os custos de compra mudam. A diferença é capitalizada e baseia-se em um cálculo proporcional. O valor restante é despesa.
author: AndersGirke
manager: tfehr
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0957fee111ec1fd5bb66951126869cf46d88b36e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967474"
---
# <a name="moving-average"></a>Média de movimentos

[!include [banner](../includes/banner.md)]

A média de movimentos é um método de avaliação de custo perpétuo baseado no princípio da média, no qual os custos das saídas de estoque não são alterados quando os custos de compra mudam. A diferença é capitalizada e baseia-se em um cálculo proporcional. O valor restante é despesa.

Ao usar a média móvel, as liquidações de estoque e marcação do estoque não são suportados. O fechamento de estoque não afeta os produtos que têm a média móvel, como o grupo de modelos de estoque, e não gera nenhuma liquidação entre as transações.

Estes são pré-requisitos quando você usa custo da média móvel como um método de avaliação de custo.

1. Na página **Grupos de modelos de item**, configure um grupo de modelos de item com a **Média móvel** selecionada no campo **Modelo de estoque**.

    > [!NOTE]
    > Por padrão, quando a **Média móvel** for selecionada, os campos **Lançar estoque físico** e **Lançar estoque financeiro** também serão selecionados.

1. Na página **Lançamento**, atribua contas à **Diferença de preço da média móvel**. Você usa a conta **Diferença de preço da média móvel** quando o custo precisa ser gasto proporcionalmente. Isso ocorre nestes dois cenários:
    - Há uma diferença de custo entre o recebimento da compra e a fatura de compra porque existe uma diferença entre a quantidade de estoque original e a quantidade disponível atual.
    - As transações passam o estoque de negativo a zero, e há uma diferença entre o custo da transação e o custo da média móvel atual.

1. Na página **Lançamento**, atribua contas às contas de **Reavaliação de custos da média móvel** na guia **Estoque**. Você usa a conta **Reavaliação de custos da média móvel** quando deseja ajustar o custo da média móvel de um produto a um novo preço unitário.

1. Na página **Produtos liberados**, atribua o grupo de modelos de item da média móvel ao produto.

    > [!NOTE]
    > O processo de fechamento de estoque fecha somente o período contábil. Ele não afeta os produtos que têm a média móvel atribuída a eles como um grupo de modelos do item.

## <a name="convert-to-the-moving-average-costing-method"></a>Converte para o método de avaliação de custo da média móvel

Os produtos podem ser convertidos para usar o método de avaliação de estoque de média móvel. Esse tipo de conversão é normalmente feita no final do ano, depois que o último mês do ano atual é fechado. Ela é feita usando o modelo de avaliação de custo atual do produto. Você pode alterar o método de avaliação de custo de estoque de um método de avaliação de custo que é baseado no custo médio para um método baseado na média móvel.

Se você está alterando seu método de avaliação de custo de um método padrão para um de média móvel, você tem que realizar as seguintes tarefas:

1. Faça ajustes para obter as quantidades em estoque e valores 0 (zero).
1. Depois que o valor e a quantidade do estoque for 0 (zero), altere o grupo de modelos de item para a média móvel.
1. Faça ajustes para obter a quantidade e o valor de volta ao estoque.

Você não pode alterar o método de avaliação de custo do estoque de um método de média móvel para o método Primeiro a entrar, primeiro a sair (PEPS), Último a entrar, Primeiro a sair (UEPS) ou de média ponderada.

> [!NOTE]
> A conversão de custo padrão para média ponderada móvel é um processo manual.

Os exemplos a seguir ilustram o impacto de usar o método de avaliação de custo de média móvel. Existem quatro configurações:

- Diferença entre custo de ordem de compra e despesa proporcional
- Produtos de média móvel e ajuste de estoque
- Média móvel com produção
- Média móvel com transação de datas anteriores

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>Diferença entre custo de ordem de compra e despesa proporcional

Com a média móvel, o custo do produto é determinado pelo recebimento da compra. Quando a fatura de compra é lançada, se houver uma diferença de custo entre o recebimento da compra e a fatura de compra, a diferença será ajustada proporcionalmente para os produtos em estoque no momento, e qualquer valor restante será despesa.

Neste exemplo, uma ordem de compra é criada e recebida por um custo, e a fatura de compra é lançada com um custo diferente.

1. Crie uma ordem de compra para uma quantidade de 2 e preço unitário de R$ 10,00.
1. Crie um recebimento de compra do produto.
1. Crie uma ordem de venda para uma quantidade de 1 e preço unitário de R$ 10,00.
1. Crie uma fatura de compra para uma quantidade de 2 e preço unitário de R$ 12,00.

A diferença no preço unitário, R$ 2,00, será lançada na conta Diferença de preço da média de movimentos quando a fatura de compra for lançada. O motivo é que dois produto foram comprados a um custo de R$ 20,00. Um dos produtos foi vendido por um preço unitário de R$ 10,00. A fatura de compra foi lançada ao preço unitário de 12,00 com uma quantidade de 2. O preço unitário de produto não pode ser lançado em 14,00.

## <a name="moving-average-product-and-inventory-adjustment"></a>Produtos de média móvel e ajuste de estoque

Se precisar ajustar o custo da média móvel de um produto, os ajustes de estoque são autorizados a partir da data de hoje. Não é possível realizar um ajuste de estoque de datas anteriores para corrigir o custo da média móvel de um produto. Você não pode propagar os custos em transações subsequentes.

Neste exemplo, o custo da média móvel será ajustado para um produto.

1. Selecione o produto para o qual você deseja ajustar o custo de média móvel. 

 > [!NOTE]
 > A página **Reavaliação da média móvel** examina o estoque disponível de um produto. O produto selecionado tem uma quantidade lançada de 1, um valor lançado de R$ 12,00, um custo unitário lançado de R$ 12,00 e um custo unitário de R$ 12,00.
    
1. Atualize o campo **Custo unitário** para 16,00. O sistema calcula os campos restantes.
1. O ajuste é lançado.

> [!NOTE]
> Você só pode ajustar o custo da média móvel a partir da data de hoje.

Na página **Liquidações do comprovante**, você pode ver um ajuste de R$ 4,00 lançado na conta Reavaliação de custos da média móvel.

## <a name="moving-average-with-production"></a>Média móvel com produção

A média móvel suporta itens produzidos. Se você pretende usar a média móvel em um ambiente de produção, selecione **Usar preço de custo previsto** na página **Parâmetros de controle de produção**. Isso significa que o preço de custo que é calculado durante a previsão é usado, em vez do preço de custo real de cálculo de BOM.

## <a name="moving-average-with-a-backdated-transaction"></a>Média móvel com transação de datas anteriores

Os custos da média móveis atuais são atribuídos às transações de datas anteriores e a quantidade física do produto é atualizada, mas o custo da média móvel do produto não é afetado. Neste exemplo de média móvel, uma transação de data antiga para um produto de média móvel é lançada.

1. Crie um ajuste de estoque para o produto de média móvel para uma quantidade de 1 e um custo de R$ 20,00.
1. O histórico de transações de estoque para o produto assemelha-se ao seguinte:
    - Uma transação de estoque de 1, um custo de R$ 16,00, uma data de lançamento de 15 de janeiro e uma data de transação de 15 de janeiro.
    - Um ajuste de estoque de 1, um custo de R$ 20,00, uma data de lançamento de 1º de janeiro e uma data de transação de 15 de janeiro.
1. Lance o ajuste.

Na página **Transações de estoque** você verá que R$ 4,00 foram gastos, já que a média móvel atual do produto é de R$ 16,00. Você poderá lançar no passado, mas a diferença de custo é despesa, para que o custo da média móvel não seja afetado.

## <a name="negative-inventory-balances"></a>Saldos de estoque negativos

As transações são tratadas de forma diferente dependendo se a nova quantidade disponível após a transação é negativa, zero ou positiva.

### <a name="new-balance-is-negative-or-zero"></a>Novo saldo é negativo ou zero

Se a nova quantidade disponível for negativa ou zero, a transação terá os custos médios atuais. Se houver uma diferença entre o preço de compra e os custos médios atuais, ele será lançado na **Diferença de preço para a média móvel**.

### <a name="new-balance-is-positive"></a>O novo saldo é positivo

Se a nova quantidade disponível for positiva após a transação, a transação será dividida em duas partes e com custo diferente, conforme resumido na tabela a seguir.

| Parte | Descrição |
|---|---|
| Quantidade de negativo a zero | O estoque usa o custo médio móvel atual do item, em vez do custo da transação para essa parte da quantidade de recebimento que aumenta o saldo disponível de negativo para zero. A diferença entre o custo da transação e o custo da média móvel atual é lançada em **Diferença de preço para a média móvel**. |
| Quantidade de zero a positivo | O estoque usa o custo da transação para essa parte da quantidade de recebimentos que aumenta o saldo disponível de zero para positivo.                                                  |

## <a name="inventory-value-report"></a>Relatório de valor de estoque

Neste exemplo de média móvel, o relatório de valor de estoque é impresso para oferecer suporte ao cálculo atual da média móvel para um produto. O relatório Valor do estoque pode imprimir as transações em ordem cronológica, junto com o custo para oferecer suporte ao cálculo do custo de média móvel de um produto. O relatório exibe o custo de média móvel para o produto. Na caixa de diálogo **Relatórios de valor de estoque**, um Intervalo de datas permite que você selecione a **Hora da transação** ou a **Data de lançamento** no qual o relatório será classificado. A opção **Data de lançamento** é como o relatório é impresso tradicionalmente. A opção **Hora da transação** é a data real em que a transação é relatada e o custo de média móvel do produto é atualizado. É possível imprimir o relatório Valor do estoque usando a opção **Classificação de tempo da transação** se quiser ver o cálculo de custo de média móvel ao longo do tempo. A tabela a seguir exibe as transações do produto para o qual o relatório é impresso quando a opção **Classificação de tempo da transação** for usada.

| Hora da transação | Data         | Tipo de transação           | A quantidade | Valor | Custo médio da unidade |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 1 de outubro    | Saldo inicial          | 0        | 0,00   | 0,00              |
| 8 de outubro        | 28 de setembro | Recebimento em data anterior          | 1        | 16,00  | 16,00             |
| 3 de outubro        | 3 de outubro    | Recebimento de compra           | 2        | 20,00  | 12:00             |
| 5 de outubro        | 5 de outubro    | ordem de venda                | -1       | -10,00 | 13,00             |
| 7 de outubro        | 7 de outubro    | Fatura de compra           |          | 2,00   | 14,00             |
| 8 de outubro        | 8 de outubro    | Reavaliação da média de movimentos |          | 4.00   | 16.00             |
|                  | 31 de outubro   | Total                      | 2        | 32.00  | 16.00             |

> [!NOTE]
> Não é possível reconciliar a contabilidade com o estoque usando a opção **Classificação de tempo da transação**. O relatório deve ser impresso usando a opção **Data de lançamento**.
