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
ms.openlocfilehash: a59724ff698b6ad0e84b0642240da5f8953ab3d1
ms.sourcegitcommit: 9642494da87c0d237f9fcbe15df14315d9e88fa2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2021
ms.locfileid: "7385714"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Falha no lançamento do diário devido ao desequilíbrio

[!include [banner](../includes/banner.md)]

Este tópico explica por que débitos e créditos podem não ser equilibrados em transações de comprovante, de forma que as transações não podem ser iniciadas. O tópico também inclui etapas para corrigir o problema.

## <a name="symptom"></a>Sintoma

Em alguns casos, um diário não pode ser lançado, e a seguinte mensagem é mostrada: "As transações em um comprovante específico não são equilibradas em uma determinada data (moeda contábil: 0,01 — moeda de relatório: 0,06)". Por que o diário não pode ser lançado?

## <a name="resolution"></a>Resolução

Durante o lançamento em Contabilidade, cada comprovante deve ser equilibrado na moeda da transação, moeda contábil e moeda de relatório, se essas moedas forem definidas na página **Configuração do razão**. (Os comprovantes são equilibrados quando o total de débitos é igual ao total de créditos.)

Na parte inferior da página de linhas do diário, os totais são mostrados na moeda da contabilidade e na moeda do relatório. Eles **não** são mostrados na moeda de transação para transações em moeda estrangeira. Além disso, a mensagem de erro que os usuários recebem durante a simulação ou lançamento mostra as diferenças apenas na moeda contábil e na moeda do relatório. Ela não as mostra na moeda da transação, porque um único comprovante pode ter mais de uma moeda de transação e o diário pode incluir comprovantes em diferentes moedas de transação. Portanto, é importante que você verifique se os valores da moeda da transação para cada comprovante estão equilibrados.

### <a name="transaction-currency"></a>Moeda da transação

Durante a simulação e o lançamento, o sistema verifica se todos os comprovantes estão equilibrados na moeda da transação. Para cada comprovante inserido, pode haver uma ou mais moedas para a moeda da transação. Por exemplo, um comprovante que é inserido no diário geral pode ter duas moedas de transação quando dinheiro é transferido de uma conta bancária que usa euros (EUR) para uma conta bancária que usa dólares canadenses (CAD).

Se um comprovante tiver apenas uma moeda de transação, o total de débitos deverá ser igual ao total de créditos para aquele comprovante. Os clientes encontraram os seguintes cenários em que o lançamento falhou corretamente porque os valores da moeda da transação não foram equilibrados:

- Os débitos totais e os créditos totais **não** foram equilibrados na moeda da transação, mas foram equilibrados na moeda contábil e na moeda de relatório. Um cliente presumiu que o comprovante ainda seria lançado. No entanto, essa suposição estava incorreta. **Os valores da moeda da transação em um comprovante devem sempre ser equilibrados quando todas as linhas do comprovante têm a mesma moeda.**
- O comprovante foi importado por meio do Microsoft Excel, e o usuário pensou que os valores da moeda da transação estavam equilibrados. Na pasta de trabalho do Excel, os valores importados foram definidos como valores **Numéricos**, não valores de **Moeda**. Nesse cenário, os valores numéricos da pasta de trabalho tinham mais de duas casas decimais, e mais de duas casas decimais foram incluídas quando os valores foram importados. Portanto, os débitos não eram iguais aos créditos, porque estavam incorretos por uma fração de centavo. O diário não refletiu essa diferença nas linhas do comprovante, pois os valores mostrados têm apenas duas casas decimais.
- O comprovante foi importado por meio do Excel, e o usuário pensou que os valores da moeda da transação estavam equilibrados. Embora o comprovante estivesse equilibrado, algumas linhas do comprovante tinham datas de transação diferentes. Se você adicionou o total de débitos e créditos por comprovante e data da transação, eles não foram equilibrados. O sistema agora evita esse cenário. Um comprovante pode ter apenas uma data de transação. Este requisito é imposto quando você insere um comprovante por meio do diário geral no sistema. No entanto, ele não foi originalmente aplicado quando um comprovante foi importado por meio do Excel.

Em um cenário com suporte, um comprovante pode ter mais de uma moeda de transação. Nesse caso, o sistema **não** verifica se os débitos são iguais aos créditos na moeda da transação, pois as moedas não coincidem. Em vez disso, o sistema verifica se os valores monetários contábeis estão equilibrados.

### <a name="accounting-currency"></a>Moeda contábil

Se todas as linhas de um comprovante tiverem a mesma moeda de transação e se os valores da moeda da transação estiverem equilibrados, o sistema verificará se os valores da moeda contábil estão equilibrados. Se o comprovante for inserido em uma moeda estrangeira, a taxa de câmbio nas linhas do comprovante será usada para converter os valores da moeda da transação para a moeda contábil. Primeiro, cada linha do comprovante é traduzida. Em seguida, as linhas são somadas para determinar os débitos totais e os créditos totais. Como cada linha é traduzida, os débitos totais e os créditos totais podem não ser equilibrados. No entanto, se a diferença estiver dentro do valor de **Diferença de centavos máxima** definido na página **Parâmetros da contabilidade**, o comprovante será lançado, e a diferença será lançada automaticamente na conta de Diferença de centavos.

Se o comprovante tiver mais de uma moeda de transação, cada linha do comprovante será convertida para a moeda contábil, e as linhas serão somadas para determinar o total de débitos e créditos. Para serem considerados equilibrados, os débitos e os créditos devem estar equilibrados, e não deve haver nenhuma diferença de arredondamento de centavos.

### <a name="reporting-currency"></a>Moeda de relatório

Se todas as linhas de um comprovante tiverem a mesma moeda de transação e se os valores da moeda da transação estiverem equilibrados, o sistema verificará se os valores da moeda de relatório estão equilibrados. Se o comprovante for inserido em uma moeda estrangeira, a taxa de câmbio nas linhas do comprovante será usada para converter os valores da moeda da transação para a moeda de relatório. Primeiro, cada linha do comprovante é traduzida. Em seguida, as linhas são somadas para determinar os débitos totais e os créditos totais. Como cada linha é traduzida, os débitos totais e os créditos totais podem não ser equilibrados. No entanto, se a diferença estiver dentro do valor de **Arredondamento máximo de centavos na moeda de relatório** definido na página **Parâmetros da contabilidade**, o comprovante será lançado, e a diferença será lançada automaticamente na conta de Diferença de centavos.

Se o comprovante tiver mais de uma moeda de transação, cada linha do comprovante será convertida para a moeda de relatório, e as linhas serão somadas para determinar o total de débitos e créditos. Para serem considerados equilibrados, os débitos e os créditos devem estar equilibrados, e não deve haver nenhuma diferença de arredondamento de centavos.
