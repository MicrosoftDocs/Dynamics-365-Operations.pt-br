---
title: "Preço de custo médio"
description: "Os acordos de processo de fechamento de estoque para transações emitem passe recebimento de transações, com base no método de avaliação de estoque selecionado no grupo modelo do item. Contudo, antes que fechamento de estoque seja executado, o sistema calcula um preço de custo médio estimado em execução usado normalmente quando as transações de saída são lançadas."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-04-07 15 - 11 - 47
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79003
ms.assetid: adc3f245-dc9d-4327-88fb-6a579194a5fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 685dfaa877699db3c36cc1ea77d956461f8e68ec
ms.lasthandoff: 03/29/2017


---

# <a name="running-average-cost-price"></a>Preço de custo médio

Os acordos de processo de fechamento de estoque para transações emitem passe recebimento de transações, com base no método de avaliação de estoque selecionado no grupo modelo do item. Contudo, antes que fechamento de estoque seja executado, o sistema calcula um preço de custo médio estimado em execução usado normalmente quando as transações de saída são lançadas.

O sistema estima esse preço de custo médio estimado em execução para um item usando esta fórmula: Preço estimado = (valor físico + valor financeiro) ÷ (quantidade física + quantidade financeira)

## <a name="using-the-running-average-cost-price"></a>Uso do preço de custo médio
A tabela a seguir mostra aos lançamentos do sistema inventariarem transações usando o preço de custo médio estimado em execução, e quando usar o preço de custo estimado que foi definido no registro mestre do item.

| Condição                                               | O sistema usará o preço de custo estimado em execução médio estimado | O sistema usará o preço de custo estimado definido no item mestre |
|---------------------------------------------------------|----------------------------------------------------------|-------------------------------------------------------------------|
| \* o numerador e o denominador são positivos\*\* .  | Sim                                                      | Não                                                                |
| O numerador, o denominador\*\*\*, ou ambos são negativos. | Não                                                       | Sim                                                               |
| \*\* o denominador é 0 (zero).                        | Não                                                       | Sim                                                               |

\* numerador = (valor físico + valor financeiro) \*\* denominador = (quantidade física + quantidade financeira) ** observação: ** ** Se incluir valor físico ** a opção não estiver selecionada para um item, o process 0 do sistema (zero) para exibir o valor e a quantidade físicos. Para obter informações sobre essa opção, consulte [Incluir valor físico](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Evite a amplificação de preços
Em raras ocasiões, o sistema precifica vários problemas antes de ter recibos suficientes para basear o preço. Esse cenário pode fazer com que as estimativas do preço de custo médio fique excessivamente inflacionado. No entanto, há etapas que você pode executar para evitar a amplificação de preços ou para reduzir seu impacto quando ela acontecer. **Cenário** As transações a seguir ocorrem para um item para o qual você selecionou a opção **Incluir valor físico**:

1.  Você recebe financeiramente uma quantidade 100 a BRL 100,00.
2.  Você emite financeiramente uma quantidade 200.
3.  Você recebe fisicamente uma quantidade 101 a BRL 202,00.

Quando você examina o preço de custo médio estimado para o item, espera um preço de custo de BRL 1,51. Em vez disso, você descobre uma média estimada de execução de r$ 102.00, que é baseado no seguinte fórmula: Preço estimado = \[202 + (100) - \[÷ 101 +\] (- 100) =\] 102 ÷ 1 = 102 da amplificação de preços, ocorre porque quando 200 itens foram emitidas financeiramente na etapa 2, o sistema deve pelo preço de 100 dos itens antes que tenha todos recebimentos correspondentes. Essa situação faz o estoque fique negativo. O sistema então estima um preço unitário de BRL 1.00, como nós pudemos esperar. No entanto, quando os 100 recebimentos correspondentes chegam, estão a um preço unitário de BRL 2,00 cada. **Observação:** embora as saídas gerem estoque negativo, o estoque é positivo quando o preço de saída é calculado. Portanto, o preço de custo médio é usado em vez do preço no item mestre. Nesse ponto, o sistema tiver uma compensação de valor de estoque de BRL 100.00. Embora essa compensação tenha sido criada com mais de 100 peças, onde havia uma compensação unitária de BRL 1,00 cada, agora temos apenas parte do estoque. Dessa forma, a compensação de BRL 100,00 será alocada a essa única peça. O resultado é o preço de custo estimado inflacionado em excesso. **Observação:** para comparação, observe que se as etapas 2 e 3 forem revertidas no cenário 200 itens serão lançados a um preço unitário de BRL 1,51, e uma peça permanecerá ao preço unitário de BRL 1,51. Como esse cenário de amplificação de preço pode ocorrer quando o estoque negativo está envolvido, é difícil evitá-lo nestes casos:

-   Você deve estimar preços de saída sobre o valor disponível e a quantidade.
-   Você deve ajustar o valor disponível e a quantidade com relação a saídas e recebimentos.
-   Seu modelo de negócios permite o envio ou a precificação de mais peças do que você tem.
-   Você deve aceitar qualquer quantidade e valor de recebimento enviados para você.

No entanto, se o modelo de negócios permitir, as práticas a seguir podem ajudar você a evitar as quantidades negativas que tornam o cenário de amplificação de preços possível:

-   Se você selecionar a opção **Incluir valor físico** para um item, desmarque a caixa de seleção **Estoque negativo físico** na página **Grupos de modelos de item**.
-   Se você *não* selecionar a opção **Incluir valor físico** para um item, desmarque a caixa de seleção **Estoque negativo físico** na página **Grupos de modelos de item**.

Adicionalmente, considere que a compensação máxima no valor de estoque físico está limitada pelo número de transações físicas e pela diferença entre preços físicos e financeiros. Desde que todas as transações físicas sejam atualizadas financeiramente, o valor físico não poderá aumentar até níveis extremos. Por fim, observe que o efeito de amplificação diminui significativamente quando a compensação acumulada for dividida por várias peças disponíveis em vez de apenas uma.


