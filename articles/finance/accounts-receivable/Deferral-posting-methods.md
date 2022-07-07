---
title: Métodos de lançamento de adiamento
description: Este artigo descreve as diferenças entre os métodos de lançamento de adiamento dos adiamentos de receita e despesa na cobrança de assinatura.
author: JodiChristiansen
ms.date: 6/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: c66ed1c38251140dd798c39797873ceb5f7121a4
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9019088"
---
# <a name="deferral-posting-methods"></a>Métodos de lançamento de adiamento

Este artigo descreve as diferenças entre os métodos de lançamento de adiamento dos adiamentos de receita e despesa na cobrança de assinatura.

Na página **Parâmetros de adiamento de receita e despesa**, as opções para métodos de lançamento de adiamento são **Balanço** e **Lucros e perdas**. O exemplo neste artigo ajudará a explicar as diferenças entre os dois métodos e os motivos pelos quais você pode usar um método ou o outro.

O método **Balanço** usa somente duas contas. Portanto, há menos configuração envolvida. O método **Lucros e perdas** tem duas contas adicionais, **Reconhecimento inicial** e **Contrapartida de reconhecimento**, para receita, descontos e custos, dependendo do tipo de transação. Essas contas são configuradas na página **Padrões de adiamento** (**Cobrança de assinatura \> Adiamentos de receita e despesa \> Configuração**). Embora o exemplo se concentre na receita adiada, o mesmo conceito pode ser aplicado a descontos adiados e a custos adiados.

## <a name="example"></a>Exemplo

A fatura de venda 1 tem um total de US$ 3.000 e tem receita adiada. As tabelas a seguir mostram as distribuições quando essa fatura de venda é lançada.

**Método balanço**

| Tipo | Conta | Débito | Crédito|
|---|---|---|---|
| Débito | Contas a Receber | 3,000.00 | |
| Crédito | Receita adiada | | 3,000.00 |

**Método lucros e perdas**

| Tipo | Conta | Débito | Crédito |
|---|---|---|---|
| Débito | Contas a Receber | 3,000.00 | |
| Débito | Contrapartida do reconhecimento de receita | 3,000.00 | |
| Crédito | Receita adiada | | 3,000.00 |
| Crédito | Reconhecimento da receita inicial | | 3,000.00 |

A fatura de venda 2 tem um total de US$ 2.000 e não tem receita adiada.

| Tipo | Conta | Valor |
|---|---|---|
| Débito | Contas a Receber | 3,000.00 |
| Crédito | Renda | 3,000.00 |

**Total do método balanço para a fatura de venda 1 e 2 combinadas**

| Conta | Débito | Crédito |
|---|---|---|
| Contas a Receber | 5.000,00 | |
| Renda | | 2,000.00 |
| Receita adiada | | 3,000.00 |

Quando o método **Balanço** é usado, não é tão fácil ver a receita bruta de um período. Alguma receita é lançada na conta de **Receita adiada**. Lembre-se de que, como a receita é reconhecida a cada período, há vários débitos e créditos na conta de **Receita adiada**. A receita bruta para um determinado período será misturada com as entradas/saídas do reconhecimento de receita.

**Totais do método Lucros e perdas para a fatura de venda 1 e 2 combinadas**

| Conta | Débito | Crédito |
|---|---|---|
| Contas a Receber | 5.000,00 | |
| Renda | | 5.000,00 |
| Contrapartida de receita | 3,000.00 | |
| Receita adiada | | 3,000.00 |

Toda a receita vai para a conta de **Receita** de lucros e perdas. Em seguida, a receita adiada é movida do demonstrativo de lucros e perdas para o balanço. Você pode ver facilmente a receita bruta, pois tudo é lançado na conta de **Receita**. No entanto, parte da receita bruta é adiada. Portanto, ela é movida para a conta de **Receita adiada** e reconhecida posteriormente.

No método **Lucros e perdas**, você pode verificar a conta de **Receita** e a conta de **Contrapartida de receita** para ver a receita bruta de US$ 5.000 e a receita líquida (líquida da adiada) de US$ 2.000. Embora o método **Lucros e perdas** possa tornar o relatório mais fácil, há mais contas a serem configuradas.
