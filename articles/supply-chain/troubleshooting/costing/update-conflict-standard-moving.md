---
title: Há um conflito de atualização quando o método de avaliação de estoque é custo padrão ou média móvel
description: Um conflito de atualização ocorre quando o método de avaliação de estoque é Custo padrão ou Média móvel
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 920d20d19843ce0cac678c5426c00ec99aa61c61
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475610"
---
# <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Um conflito de atualização ocorre quando o método de avaliação de estoque é Custo padrão ou Média móvel

## <a name="symptoms"></a>Sintomas

Ao lançar documentos, como diários de estoque, faturas de ordens de compra ou faturas de ordens de venda em paralelo para escalabilidade e desempenho, você pode receber uma mensagem de erro sobre um conflito de atualização e alguns dos documentos podem não ser lançados. Esse problema pode ocorrer quando o método de avaliação de estoque é *Custo padrão* ou *Média móvel*. Esses dois métodos são métodos perpétuos de avaliação de custo. Em outras palavras, o custo final é determinado no momento do lançamento.

Se você estiver usando o método *Média móvel*, a mensagem de erro se assemelhará a este exemplo:

> O valor de estoque xx.xx não é esperado após o cálculo de despesas proporcionais

Se você estiver usando o método *Custo padrão*, a mensagem de erro se assemelhará a este exemplo:

> O custo padrão não corresponde ao valor do estoque financeiro após a atualização. Valor = xx.xx, Qtd. = yy.yy, Custo padrão = zz.zz

## <a name="workaround"></a>Solução alternativa

Até que a Microsoft lance uma solução para corrigir o problema, considere o uso das seguintes soluções alternativas para ajudar a evitar ou reduzir esses erros:

- Relance os documentos com falha.
- Crie documentos com menos linhas.
- Evite valores decimais no custo padrão. Tente definir o custo padrão para que o campo **Quantidade de preço** seja definido como *1*. Se for necessário especificar um valor **Quantidade de preço** maior do que *1*, tente minimizar o número de casas decimais no custo padrão da unidade. (O ideal é que haja menos de duas casas decimais). Por exemplo, evite definir configurações de custo padrão como **Preço** = *10* e **Quantidade de preço** = *3*, pois elas produzirão um custo padrão de unidade de 3,333333 (no qual o valor decimal se repete).
- Na maioria dos documentos, evite ter várias linhas que contenham a mesma combinação de dimensões de estoque financeiro e de produtos.
- Reduza o grau de paralelização. (Neste caso, o sistema pode ficar mais rápido, pois ocorrem menos conflitos de atualização e repetições).
