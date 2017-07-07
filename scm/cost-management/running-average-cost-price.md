---
title: "Preço de custo médio"
description: "O processo de fechamento de estoque liquida transações de saída para transações de recebimento com base no método de avaliação do estoque selecionado no grupo de modelos do item. Entretanto, antes que o fechamento de estoque seja executado, o sistema calcula um preço de custo médio que normalmente é usado quando as transações de saída são lançadas."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a73ce12f1064c44b2af0fa4f33c63f1a6bddab89
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="running-average-cost-price"></a>Preço de custo médio

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


O processo de fechamento de estoque liquida transações de saída para transações de recebimento com base no método de avaliação do estoque selecionado no grupo de modelos do item. Entretanto, antes que o fechamento de estoque seja executado, o sistema calcula um preço de custo médio que normalmente é usado quando as transações de saída são lançadas.

O sistema estima esse preço de custo médio de um item usando esta fórmula: 

Preço estimado = (valor físico + valor financeiro) ÷ (quantidade física + quantidade financeira)

## <a name="using-the-running-average-cost-price"></a>Uso do preço de custo médio
A tabela a seguir mostra quando o sistema lança transações de estoque usando o preço de custo médio e quando ele usa o preço de custo definido no registro mestre do item.

| Condição                                               | O sistema usa o preço de custo médio estimado | O sistema usa o preço de custo definido no item mestre |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| O numerador\* e o denominador\*\* são positivos.  | Sim                                                      | Não                                                                |
| O numerador\*, denominador\*\*, ou ambos são negativos. | Não                                                       | Sim                                                               |
| O denominador\*\* é 0 (zero).                        | Não                                                       | Sim                                                               |

\* Numerador = (valor físico + valor financeiro) \*\* denominador = (quantidade física + quantidade financeira) 

**Observação:** Se a opção **Incluir valor físico** não estiver selecionada para um item, o sistema usará 0 (zero) para o valor físico e a quantidade física. Para obter informações sobre essa opção, consulte [Incluir valor físico](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Evite a amplificação de preços
Em raras ocasiões, o sistema precifica várias saídas antes de ter recebimentos suficientes para basear o preço. Esse cenário pode fazer com que as estimativas do preço de custo médio fique excessivamente inflacionado. No entanto, há etapas que você pode executar para evitar a amplificação de preços ou para reduzir seu impacto quando ela acontecer. **Cenário** As transações a seguir ocorrem para um item para o qual você selecionou a opção **Incluir valor físico**:

1.  Você recebe financeiramente uma quantidade 100 a BRL 100,00.
2.  Você emite financeiramente uma quantidade 200.
3.  Você recebe fisicamente uma quantidade 101 a BRL 202,00.

Quando você examina o preço de custo médio estimado para o item, espera um preço de custo de BRL 1,51. Em vez disso, você descobre uma média estimada de BRL 102,00, que se baseia nesta fórmula: Preço estimado = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102 Essa amplificação de preços ocorre porque, quando 200 itens são emitidos financeiramente na etapa 2, o sistema deve precificar 100 dos itens antes de ter os recebimentos correspondentes. Essa situação faz o estoque fique negativo. O sistema estima um preço unitário de BRL 1,00, como podemos esperar. No entanto, quando os 100 recebimentos correspondentes chegam, estão a um preço unitário de BRL 2,00 cada. 

**Observação:** embora as saídas gerem estoque negativo, o estoque é positivo quando o preço de saída é calculado. Portanto, o preço de custo médio é usado em vez do preço no item mestre. Nesse ponto, o sistema tem uma compensação de valor de estoque de BRL 100,00. Embora essa compensação tenha sido criada com mais de 100 peças, onde havia uma compensação unitária de BRL 1,00 cada, agora temos apenas parte do estoque. Dessa forma, a compensação de BRL 100,00 será alocada a essa única peça. O resultado é o preço de custo estimado inflacionado em excesso. 

**Observação:** para comparação, observe que se as etapas 2 e 3 forem revertidas no cenário 200 itens serão lançados a um preço unitário de BRL 1,51, e uma peça permanecerá ao preço unitário de BRL 1,51. Como esse cenário de amplificação de preço pode ocorrer quando o estoque negativo está envolvido, é difícil evitá-lo nestes casos:

-   Você deve estimar preços de saída sobre o valor disponível e a quantidade.
-   Você deve ajustar o valor disponível e a quantidade com relação a saídas e recebimentos.
-   Seu modelo de negócios permite o envio ou a precificação de mais peças do que você tem.
-   Você deve aceitar qualquer quantidade e valor de recebimento enviados para você.

No entanto, se o modelo de negócios permitir, as práticas a seguir podem ajudar você a evitar as quantidades negativas que tornam o cenário de amplificação de preços possível:

-   Se você selecionar a opção **Incluir valor físico** para um item, desmarque a caixa de seleção **Estoque negativo físico** na página **Grupos de modelos de item**.
-   Se você *não* selecionar a opção **Incluir valor físico** para um item, desmarque a caixa de seleção **Estoque negativo físico** na página **Grupos de modelos de item**.

Adicionalmente, considere que a compensação máxima no valor de estoque físico está limitada pelo número de transações físicas e pela diferença entre preços físicos e financeiros. Desde que todas as transações físicas sejam atualizadas financeiramente, o valor físico não poderá aumentar até níveis extremos. Por fim, observe que o efeito de amplificação diminui significativamente quando a compensação acumulada for dividida por várias peças disponíveis em vez de apenas uma.




