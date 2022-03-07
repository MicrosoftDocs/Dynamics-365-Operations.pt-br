---
title: Preço de custo médio
description: O processo de fechamento de estoque liquida transações de saída para transações de recebimento com base no método de avaliação do estoque selecionado no grupo de modelos do item. Entretanto, antes que o fechamento de estoque seja executado, o sistema calcula um preço de custo médio que normalmente é usado quando as transações de saída são lançadas.
author: AndersGirke
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventModelGroup, InventOnhandItem, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79003
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 871b3ffce45848f95d132eff3fd327295bc5084c
ms.sourcegitcommit: fefe93f3f44d8aa0b7e6d54cc4a3e5eca6e64feb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092180"
---
# <a name="running-average-cost-price"></a>Preço de custo médio

[!include [banner](../includes/banner.md)]

O processo de fechamento de estoque liquida transações de saída para transações de recebimento com base no método de avaliação do estoque selecionado no grupo de modelos do item. Entretanto, antes que o fechamento de estoque seja executado, o sistema calcula um preço de custo médio que normalmente é usado quando as transações de saída são lançadas.

O sistema estima esse preço de custo médio de um item usando esta fórmula:

Preço estimado = (valor físico + valor financeiro) ÷ (quantidade física + quantidade financeira)

## <a name="default-item-cost"></a>Custo padrão do item

O custo padrão do item para um produto liberado pode ser configurado em uma das duas maneiras na página **Detalhes do produto liberado**:

- Crie um custo padrão selecionando **Preço de item** no grupo **Configurar** na guia **Gerenciar custos** do Painel de Ações. Se você usar esse método, deverá usar uma versão de custo padrão e o custo deverá ser ativado.
- Defina um preço de custo de item padrão para um produto liberado inserindo um valor no campo **Preço** na FastTab **Gerenciar custos**.

Além de inserir ou criar um preço, você pode marcar a caixa de seleção **Usar preço de custo mais recente** na FastTab **Gerenciar custos** da página **Detalhes do produto liberado**. Nesse caso, o sistema atualizará automaticamente o campo **Preço** quando você lançar uma atualização financeira. Por exemplo, se você lançar uma fatura da ordem de compra, o campo será definido como o preço de compra a partir dessa fatura.

Se você tiver um preço de custo em uma versão de avaliação de custo ativa e inserir um preço na FastTab **Gerenciar custos**, o sistema usará o preço da versão de avaliação de custo ativa antes que ela use o preço definido na FastTab **Gerenciar custos**.

## <a name="using-the-running-average-cost-price"></a>Uso do preço de custo médio

A tabela a seguir mostra quando o sistema lança transações de estoque usando o preço de custo médio e quando ele usa o preço de custo definido no registro mestre do item.

| Condição | O sistema usa o preço de custo médio estimado | O sistema usa o preço de custo do item padrão |
| --- | --- | --- |
| O numerador\* e o denominador\*\* são positivos. | Sim | Número |
| O numerador\*, denominador\*\*, ou ambos são negativos. | Não | Sim |
| O denominador\*\* é 0 (zero). | Não | Sim |

\* Numerador = (Valor físico + Valor financeiro)  
\*\* Denominador = (Quantidade física + Quantidade financeira)

> [!NOTE]
> Se a opção **Incluir valor físico** não estiver selecionada para um item, o sistema usará 0 (zero) para o valor físico e a quantidade física. Para obter informações sobre essa opção, consulte [Incluir valor físico](include-physical-value.md).

## <a name="avoiding-pricing-amplification"></a>Evite a amplificação de preços

Em raras ocasiões, o sistema precifica várias saídas antes de ter recebimentos suficientes para basear o preço. Esse cenário pode fazer com que as estimativas do preço de custo médio fique excessivamente inflacionado. No entanto, há etapas que você pode executar para evitar a amplificação de preços ou para reduzir seu impacto quando ela acontecer.

**Cenário:** As transações a seguir ocorrem para um item para o qual você selecionou a opção **Incluir valor físico**:

1. Você recebe financeiramente uma quantidade 100 a BRL 100,00.
2. Você emite financeiramente uma quantidade 200.
3. Você recebe fisicamente uma quantidade 101 a BRL 202,00.

Quando você examina o preço de custo médio estimado para o item, espera um preço de custo de BRL 1,51. Em vez disso, você encontra uma média operacional estimada de BRL 102,00, baseada na seguinte fórmula:

Preço estimado = \[202 + (-100)\] ÷ \[101 + (-100)\] = 102 ÷ 1 = 102

Essa amplificação de preços ocorre porque quando 200 itens têm saída financeira na etapa 2, o sistema deve precificar 100 dos itens antes de ter os recibos correspondentes. Essa situação faz o estoque fique negativo. O sistema estima um preço unitário de BRL 1,00, como você pode esperar. No entanto, quando os 100 recebimentos correspondentes chegam, estão a um preço unitário de BRL 2,00 cada.

> [!NOTE]
> Embora as saídas gerem estoque negativo, o estoque é positivo quando o preço de saída é calculado. Portanto, o preço de custo médio é usado em vez do preço no item mestre. Nesse ponto, o sistema tem uma compensação de valor de estoque de BRL 100,00. Embora essa compensação tenha sido criada com mais de 100 peças, onde havia uma compensação unitária de BRL 1,00 cada, você agora tem apenas parte do estoque. Dessa forma, a compensação de BRL 100,00 será alocada a essa única peça. O resultado é o preço de custo estimado inflacionado em excesso.
>
> Para comparação, observe que se as etapas 2 e 3 forem revertidas no cenário, 200 itens serão lançados a um preço unitário de BRL 1,51, e uma peça permanecerá ao preço unitário de BRL 1,51. Como esse cenário de amplificação de preço pode ocorrer quando o estoque negativo está envolvido, é difícil evitá-lo nestes casos:
>
> - Você deve estimar preços de saída sobre o valor disponível e a quantidade.
> - Você deve ajustar o valor disponível e a quantidade com relação a saídas e recebimentos.
> - Seu modelo de negócios permite o envio ou a precificação de mais peças do que você tem.
> - Você deve aceitar qualquer quantidade e valor de recebimento enviados para você.

No entanto, se o modelo de negócios permitir, as práticas a seguir podem ajudar você a evitar as quantidades negativas que tornam o cenário de amplificação de preços possível:

- Se você selecionar a opção **Incluir valor físico** para um item, desmarque a caixa de seleção **Estoque negativo físico** na página **Grupos de modelos de item**.
- Se você **não** selecionar a opção **Incluir valor físico** para um item, desmarque a caixa de seleção **Estoque negativo físico** na página **Grupos de modelos de item**.

Adicionalmente, considere que a compensação máxima no valor de estoque físico está limitada pelo número de transações físicas e pela diferença entre preços físicos e financeiros. Desde que todas as transações físicas sejam atualizadas financeiramente, o valor físico não poderá aumentar até níveis extremos. Por fim, observe que o efeito de amplificação diminui significativamente quando a compensação acumulada for dividida por várias peças disponíveis em vez de apenas uma.

## <a name="avoid-a-zero-cost-price-on-issues"></a>Evitar um preço de custo zero nos lançamentos

Quando a opção **Incluir valor físico** não estiver selecionada na página **Grupo de modelo do item**, uma saída do estoque pode ter um preço de custo zero, se não houver recebimentos atualizados financeiramente no estoque. Para ajudar a evitar este cenário, considere as seguintes opções:

- Selecione a opção **Incluir valor físico** na página **Grupo de modelos do item**. Esta opção impedirá um preço de custo zero em uma saída, desde que o recebimento seja fisicamente atualizado. Se você não permitir um estoque físico negativo, as saídas calcularão a média da execução a partir das transações atualizadas fisicamente.
- Crie um preço de custo de item padrão ativando uma versão de custo que tenha um custo padrão ou insira o preço na FastTab **Gerenciar custos** da página **Detalhes do produto liberado**. Esta opção é melhor quando a opção **Incluir valor físico** não está selecionada na página **Grupo de modelos do item** porque o sistema sempre terá o preço de fallback a ser usado.
- Marque a opção **Usar último preço de custo** na FastTab **Gerenciar custos** da página **Detalhes do produto liberado**. Esta opção manterá o campo **Preço** atualizado toda vez que você atualizar financeiramente um recibo. Se você selecionar esta opção, mas não inserir um preço padrão ou ativar um custo em uma versão de custo padrão, ainda poderá ter um custo zero em uma saída.

Se você tiver transações de saída com custo zero, o processo *Fechamento e ajuste de estoque* corrigirá o preço de custo criando um ajuste depois que os recebimentos forem atualizados financeiramente. Lembre-se de que o período financeiro quando essa atualização ocorre pode ser diferente do período financeiro quando os itens foram recebidos ou emitidos fisicamente.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
