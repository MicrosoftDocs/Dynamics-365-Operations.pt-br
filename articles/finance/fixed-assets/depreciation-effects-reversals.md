---
title: Efeitos de depreciação em reversões
description: Este artigo discute implicações potenciais para reverter uma transação de ativo fixo.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: kfend
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f0eeaafe7538b6aeeadfc804096ecee11e714da
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714191"
---
# <a name="depreciation-effects-with-reversals"></a>Efeitos de depreciação em reversões

[!include [banner](../includes/banner.md)]

Este artigo discute implicações potenciais para reverter uma transação de ativo fixo. 

Você pode reverter transações de ativo fixo e transações associadas a um ativo fixo. Você também pode revogar uma transação revertida. 

Você pode reverter ou revogar uma transação que não seja a transação lançada mais recentemente nas depreciações para o ativo. Determine primeiro se alguma transação de depreciação foi lançada após a transação que está sendo revertida. Essa etapa é necessária porque a depreciação não é recalculada durante a reversão de uma transação. Portanto, a depreciação normalmente é superestimada ou subestimada após a reversão, como mostram os exemplos. 

Para garantir que a depreciação está correta ao reverter uma transação, não continue com a reversão se receber uma mensagem durante esse processo indicando que a depreciação não será recalculada. Em vez disso, primeiro estorne a transação de depreciação lançada após a transação que tentou reverter e, depois, continue com a devolução. Você não será avisado sobre recálculos da depreciação e poderá continuar com a reversão. 

Os exemplos a seguir mostram os cálculos feitos se você continuar após a mensagem de aviso, sem primeiro reverter as transações de depreciação.

## <a name="example-1-depreciation-is-overstated"></a>Exemplo 1: a depreciação é superestimada
Um ativo é configurado com uma vida útil de cinco anos e uma depreciação linear (60 períodos de depreciação). Neste exemplo, a depreciação é superestimada.
#### <a name="asset-transaction-history"></a>Histórico de transações de ativo

| Data       | Tipo de transação                                                          | Valor                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| 1º de janeiro  | Aquisição                                                               | 59.000,00                                 |
| 1º de janeiro  | Ajuste de aquisição                                                    | 1.000,00                                  |
| 31 de janeiro | Depreciação (criada usando uma proposta para um período de depreciação) | Cálculo de 1.000,00: Valor contábil (59.000 + 1.000)/Número de períodos de depreciação restantes (60) |

#### <a name="reversal-action"></a>Ação de reversão

| Data      | Tipo de transação                | Valor    |
|-----------|---------------------------------|-----------|
| 1º de janeiro | Reversão do ajuste de aquisição | –1.000,00 |

#### <a name="depreciation-effect"></a>Efeito da depreciação

| Data        | Tipo de transação        | Valor                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| 28 de fevereiro | Depreciação (proposta) | Cálculo de 983,05: Valor contábil (59.000 - 1.000 de depreciação)/Número de períodos de depreciação restantes (59) |

A depreciação é superestimada em 16,95 (1000 - 983,05).

## <a name="example-2-depreciation-is-understated"></a>Exemplo 2: a depreciação é subestimada
Um ativo é configurado com uma vida útil de cinco anos e uma depreciação linear (60 períodos de depreciação). Neste exemplo, a depreciação é subestimada.
#### <a name="asset-transaction-history"></a>Histórico de transações de ativo

| Data       | Tipo de transação                                                          | Valor                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| 1º de janeiro  | Aquisição                                                               | 59.000,00                                   |
| 1º de janeiro  | Ajuste de desvalorização                                                     | 1.000,00                                    |
| 31 de janeiro | Depreciação (criada usando uma proposta para um período de depreciação) | Cálculo de 966,67: Valor contábil (59.000 - 1.000)/Número de períodos de depreciação restantes (60) |

#### <a name="reversal-action"></a>Ação de reversão

| Data      | Tipo de transação               | Valor    |
|-----------|--------------------------------|-----------|
| 1º de janeiro | Reversão do ajuste de desvalorização | –1.000,00 |

#### <a name="depreciation-effect"></a>Efeito da depreciação

| Data        | Tipo de transação        | Valor                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| 28 de fevereiro | Depreciação (proposta) | Cálculo de 983,62: Valor contábil (59.000 - 966,67 de depreciação)/Número de períodos de depreciação restantes (59) |

A depreciação é subestimada em 16,95 (983,62 - 966,67).



## <a name="additional-resources"></a>Recursos adicionais

[Depreciação de ativo fixo](fixed-asset-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
