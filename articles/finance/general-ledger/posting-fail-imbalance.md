---
title: Falha no lançamento do diário devido ao desequilíbrio
description: Este tópico explica por que débitos e créditos podem não ser equilibrados em transações de comprovante, de forma que as transações não podem ser iniciadas. O tópico também inclui etapas para corrigir o problema.
author: kweekley
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-8-03
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fc413f8230849653aef8c2951f1749823edded6e
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605420"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Falha no lançamento do diário devido ao desequilíbrio

[!include [banner](../includes/banner.md)]

Este tópico explica por que débitos e créditos podem não ser equilibrados em transações de comprovante, de forma que as transações não podem ser iniciadas. O tópico também inclui etapas para corrigir o problema.

## <a name="symptom"></a>Sintoma

Em alguns casos, um diário não pode ser lançado, e a seguinte mensagem é mostrada: "As transações em um comprovante específico não são equilibradas em uma determinada data (moeda contábil: 0,01 — moeda de relatório: 0,06)". Por que o diário não pode ser lançado?

## <a name="resolution"></a>Resolução

Durante o lançamento em Contabilidade, cada comprovante deve ser equilibrado na moeda da transação, moeda contábil e moeda de relatório, se essas moedas forem definidas na página **Configuração do razão**. (Os comprovantes são equilibrados quando o total de débitos é igual ao total de créditos.)

Na parte inferior da página de linhas do diário, os totais são mostrados na moeda da contabilidade e na moeda do relatório. Eles **não** são mostrados na moeda de transação para transações em moeda estrangeira. Além disso, a mensagem de erro que os usuários recebem durante a simulação ou lançamento mostra as diferenças apenas na moeda contábil e na moeda do relatório. Ela não as mostra na moeda da transação, porque um único comprovante pode ter mais de uma moeda de transação e o diário pode incluir comprovantes em diferentes moedas de transação. Portanto, é importante que você verifique manualmente se os valores de moeda da transação para cada comprovante que tem apenas uma moeda da transação estão equilibrados.

### <a name="transaction-currency"></a>Moeda da transação

Durante a simulação e o lançamento, o sistema verifica se todos os comprovantes que têm somente uma moeda de transação estão equilibrados na moeda da transação. Para cada comprovante inserido, pode haver uma ou mais moedas para a moeda da transação. Por exemplo, um comprovante que é inserido no diário geral pode ter duas moedas de transação quando dinheiro é transferido de uma conta bancária que usa euros (EUR) para uma conta bancária que usa dólares canadenses (CAD).

Se um comprovante tiver apenas uma moeda de transação, o total de débitos deverá ser igual ao total de créditos na moeda da transação para aquele comprovante. Os clientes encontraram os seguintes cenários em que o lançamento falhou corretamente porque os valores da moeda da transação não foram equilibrados:

- Os débitos totais e os créditos totais **não** foram equilibrados na moeda da transação, mas foram equilibrados na moeda contábil e na moeda de relatório. Um cliente presumiu que o comprovante ainda seria lançado. No entanto, essa suposição estava incorreta. **Os valores da moeda da transação em um comprovante devem sempre ser equilibrados quando todas as linhas do comprovante têm a mesma moeda da transação.**
- O comprovante foi importado com uma entidade de dados por meio da DMF (estrutura de gerenciamento de dados) e o usuário pensou que os valores de moeda da transação estivessem equilibrados. No arquivo de importação, alguns dos valores numéricos tinham mais de duas casas decimais, e mais de duas casas decimais foram incluídas quando os valores foram importados. Portanto, os débitos não eram iguais aos créditos, porque estavam incorretos por uma fração de centavo. O diário não refletiu essa diferença nas linhas do comprovante, pois os valores mostrados têm apenas duas casas decimais.
- O comprovante foi importado com uma entidade de dados por meio do DMF, e o usuário pensou que os valores da moeda da transação estivessem equilibrados. Embora o **comprovante** estivesse equilibrado, algumas linhas do comprovante tinham datas de transação diferentes. Se você tiver adicionado o total de débitos e na moeda da transação atual créditos por **comprovante e data da transação**, eles não foram equilibrados. Este requisito é imposto quando você insere um comprovante por meio do diário geral no sistema. No entanto, isso não é aplicado quando um comprovante é importado com uma entidade de dados por meio do DMF.

Em um cenário com suporte, um comprovante pode ter mais de uma moeda de transação. Nesse caso, o sistema **não** verifica se os débitos são iguais aos créditos na moeda da transação, pois as moedas não coincidem. Em vez disso, o sistema verifica se os valores monetários contábeis e a moeda de relatório estão equilibrados.

### <a name="accounting-currency"></a>Moeda contábil

Se todas as linhas de um comprovante tiverem a mesma moeda de transação e se os valores da moeda da transação estiverem equilibrados, o sistema verificará se os valores da moeda contábil estão equilibrados. Se o comprovante for inserido em uma moeda estrangeira, a taxa de câmbio nas linhas do comprovante será usada para converter os valores da moeda da transação para a moeda contábil. Primeiro, cada linha do comprovante é traduzida e arredondada para duas casas decimais. Em seguida, as linhas são somadas para determinar os débitos totais e os créditos totais. Como cada linha é traduzida, os débitos totais e os créditos totais podem não ser equilibrados. No entanto, se o valor absoluto da diferença estiver dentro do valor de **Diferença de centavos máxima** definido na página **Parâmetros da contabilidade**, o comprovante será lançado, e a diferença será lançada automaticamente na conta de Diferença de centavos.

Se o comprovante tiver mais de uma moeda de transação, cada linha do comprovante será convertida para a moeda contábil e arredondado para duas casas decimais, e as linhas serão somadas para determinar o total de débitos e créditos. Para serem considerados equilibrados, os débitos e os créditos devem ser equilibrados, seja como traduzidos ou quando a diferença de arredondamento da moeda contábil é incluída.

### <a name="reporting-currency"></a>Moeda de relatório

Se todas as linhas de um comprovante tiverem a mesma moeda de transação e se os valores da moeda da transação estiverem equilibrados, o sistema verificará se os valores da moeda de relatório estão equilibrados. Se o comprovante for inserido em uma moeda estrangeira, a taxa de câmbio nas linhas do comprovante será usada para converter os valores da moeda da transação para a moeda de relatório. Primeiro, cada linha do comprovante é traduzida e arredondada para duas casas decimais. Em seguida, as linhas são somadas para determinar os débitos totais e os créditos totais. Como cada linha é traduzida, os débitos totais e os créditos totais podem não ser equilibrados. No entanto, se a diferença estiver dentro do valor de **Arredondamento máximo de centavos na moeda de relatório** definido na página **Parâmetros da contabilidade**, o comprovante será lançado, e a diferença será lançada automaticamente na conta de Diferença de centavos.

Se o comprovante tiver mais de uma moeda de transação, cada linha do comprovante será convertida para a moeda de relatório e arredondado para duas casas decimais, e as linhas serão somadas para determinar o total de débitos e créditos. Para serem considerados equilibrados, os débitos e os créditos devem ser equilibrados, seja como traduzidos ou quando a diferença de arredondamento da moeda de relatório é incluída.

### <a name="example-for-an-accounting-currency-imbalance"></a>Exemplo de desequilíbrio de moeda contábil

> [!NOTE]
> O valor da moeda de relatório é calculado com base no valor da moeda da transação, da mesma forma que o valor da moeda contábil.

Taxa de câmbio: 1,5

| Linha | Comprovante | Conta | Moeda | Débito (transação) | Crédito (transação) | Débito (contabilidade) | Crédito (contabilidade) |
|---|---|---|---|---|---|---|---|
| 1 | 001 | 1101-01 | EUR | 3.33 | | 5,00 (4,995) | |
| 2 | 001 | 1101-02 | EUR | 3.33 | | 5,00 (4,995) | |
| 3 | 001 | 1101-03 | EUR | 3.34 | | 5.01 | |
| 4 | 001 | 4101- | EUR | | 10,00 | | 15.00 |
| **Total** | | | | **10.00** | **10.00** | **15.01** | **15.00** |

A moeda contábil está fora do saldo em 0,01. No entanto, desde que o arredondamento mínimo máximo na moeda contábil seja no mínimo 0,01, a diferença será lançada automaticamente na conta de diferença de centavos e o comprovante será lançado com êxito.
