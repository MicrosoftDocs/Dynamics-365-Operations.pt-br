---
title: Avisos ou erros ao alterar o status de um período contábil sem fechar o estoque
description: Avisos ou erros ao alterar o status de um período contábil sem fechar o estoque
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
ms.openlocfilehash: 05851753e29da75f014d2cc77e2b8df259620eee
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475566"
---
# <a name="warnings-or-errors-on-changing-ledger-period-status-without-closing-inventory"></a>Avisos ou erros ao alterar o status de um período contábil sem fechar o estoque

A Microsoft introduziu as seguintes validações para evitar problemas causados por um processo incorreto de final de período em relação aos custos. Se você encontrar qualquer uma das seguintes mensagens de erro, consulte [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) para obter mais informações sobre como resolver esses problemas.

- Você está prestes a executar um recálculo com uma data %1 (10-02-2019). O último recálculo registrado foi executado em um período anterior com uma data %2 (20-01-2019). Nenhuma execução de fechamento de estoque com uma data %3 (31-01-2019) que corresponde ao final de período foi registrada. Lembre-se de executar um fechamento de estoque a partir da data %3 (31-01-2019) que corresponde ao final do período. A avaliação de estoques, custo dos produtos vendidos e variações pode não estar correta no razão auxiliar ou na contabilidade até que isso seja executado.

- Você está prestes a alterar o status do período contábil %1 para %2. Nenhuma execução de fechamento de estoque com uma data %3 que corresponde ao final do período foi registrada. Execute um fechamento de estoque a partir de %3 que corresponde ao final do período antes de alterar o status. A avaliação de estoques, custo dos produtos vendidos e variações pode não estar correta no razão auxiliar ou na contabilidade até que isso seja executado. Relatado por entidade legal %4. Por enquanto, é informativo, mas será necessário executar essa ação no futuro.

- A estrutura da conta %1 foi alterada. Uma ou mais contas principais %2 não existem mais. Essas contas principais são exigidas por %3 com uma data %4. Adicione essas contas principais à estrutura de contas %1 antes de retomar o trabalho %3. Por enquanto, é informativo, mas será necessário executar essa ação no futuro.

- Você está prestes a executar um fechamento de estoque com uma data %1 (31-01-2019). Nenhuma execução de custos de fluxo inverso com uma data %2 (31-01-2019) que corresponde ao fim do período foi registrada. Lembre-se de executar um cálculo de custos de fluxo inverso com uma data de %3 (31-01-2019) que corresponda ao final do período. A avaliação de estoques, custo dos produtos vendidos e variações pode não estar correta no razão auxiliar ou na contabilidade até que isso seja executado.

- Você está prestes a executar um cálculo de custos de fluxo inverso com uma data %1 (28-02-2019). O último cálculo de custos de fluxo inverso registrado foi executado em um período anterior com uma data %2 (31-01-2019). Nenhuma execução de fechamento de estoque com uma data %3 (31-01-2019) que corresponde ao final de um período foi registrada.

Lembre-se de executar um fechamento de estoque a partir da data %3 (31-01-2019) que corresponde ao final de um período. A avaliação de estoques, custo dos produtos vendidos e variações podem não estar corretos no razão auxiliar ou na contabilidade até que o fechamento do estoque seja executado.