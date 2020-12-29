---
title: Solucionar problemas de gerenciamento de custos
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com gerenciamento de custos.
author: riluan
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: e84bb167395c06295b0e8ef8b9fd98aa4bc0cc14
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4422628"
---
# <a name="troubleshoot-cost-management"></a>Solucionar problemas de gerenciamento de custos

Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com gerenciamento de custos.

## <a name="functional-gaps-between-the-inventory-valueaging-reports-and-their-storage-versions"></a>Lacunas funcionais entre os relatórios de valor de estoque/classificação por vencimento e suas versões de armazenamento

Os recursos [Armazenamento de relatório de classificação por vencimento do estoque](inventory-aging-report-storage.md) e [Relatório de armazenamento de valor de estoque](inventory-value-report-storage.md) permitem que o Supply Chain Management exiba grandes volumes de transações de estoque. Em cada caso, os resultados do relatório são salvos para navegação e exportação, diferentemente das versões sem armazenamento desses relatórios. Contudo, algumas funcionalidades presentes nas versões sem armazenamento desses relatórios não existem nas versões com armazenamento. As subseções a seguir resumem as diferenças e fornecem soluções alternativas.

### <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Os relatórios de armazenamento não incluem subtotais, mesmo se estiverem habilitados no layout do relatório

Os subtotais podem causar problemas quando o resultado é exportado, especialmente se os usuários alterarem a sequência de registro.

Para verificar os subtotais, você pode exportar o resultado para o Microsoft Excel. Como alternativa, se você deseja verificar os subtotais no Supply Chain Management, use [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitar os recursos *Novo controle de grade* e *Agrupamento (versão prévia) em grades*, que fornecem uma maneira muito mais flexível de ver o subtotal para qualquer grupo por coluna. Para obter mais informações, consulte [Recursos de grade](../../fin-ops-core/fin-ops/get-started/grid-capabilities.md).

### <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>O relatório de armazenamento do valor do estoque não é compatível com informações da conta contábil

Você pode executar o balancete para obter o saldo das contas de estoque e compará-lo com o relatório **Armazenamento de valor de estoque**.

## <a name="warnings-or-errors-are-shown-when-changing-a-ledger-period-status-without-closing-inventory"></a>Avisos ou erros são mostrados durante a alteração do status de um período contábil sem fechar o estoque

A Microsoft introduziu as seguintes validações para evitar problemas causados por um processo incorreto de final de período em relação aos custos. Se você encontrar qualquer uma das seguintes mensagens de erro, consulte [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) para obter mais informações sobre como resolver esses problemas.

- Você está prestes a executar um recálculo com uma data %1 (10-02-2019). O último recálculo registrado foi executado em um período anterior com uma data %2 (20-01-2019). Nenhuma execução de fechamento de estoque com uma data %3 (31-01-2019) que corresponde ao final de período foi registrada. Lembre-se de executar um fechamento de estoque a partir da data %3 (31-01-2019) que corresponde ao final do período. A avaliação de estoques, custo dos produtos vendidos e variações podem não estar corretos no razão auxiliar ou na contabilidade até que seja executado.

- Você está prestes a alterar o status do período contábil %1 para %2. Nenhuma execução de fechamento de estoque com uma data %3 que corresponde ao final do período foi registrada. Execute um fechamento de estoque a partir de %3 que corresponde ao final do período antes de alterar o status. A avaliação de estoques, custo dos produtos vendidos e variações podem não estar corretos no razão auxiliar ou na contabilidade até que seja executado. Relatado por entidade legal %4. Por enquanto, é informativo, mas será necessário executar essa ação no futuro.

- A estrutura da conta %1 foi alterada. Uma ou mais contas principais %2 não existem mais. Essas contas principais são exigidas por %3 com uma data %4. Adicione essas contas principais à estrutura de contas %1 antes de retomar o trabalho %3. Por enquanto, é informativo, mas será necessário executar essa ação no futuro.

- Você está prestes a executar um fechamento de estoque com uma data %1 (31-01-2019). Nenhuma execução de custos de fluxo inverso com uma data %2 (31-01-2019) que corresponde ao fim do período foi registrada. Lembre-se de executar um cálculo de custos de fluxo inverso com uma data de %3 (31-01-2019) que corresponda ao final do período. A avaliação de estoques, custo dos produtos vendidos e variações podem não estar corretos no razão auxiliar ou na contabilidade até que seja executado.

- Você está prestes a executar um cálculo de custos de fluxo inverso com uma data %1 (28-02-2019). O último cálculo de custos de fluxo inverso registrado foi executado em um período anterior com uma data %2 (31-01-2019). Nenhuma execução de fechamento de estoque com uma data %3 (31-01-2019) que corresponde ao final de um período foi registrada.
Lembre-se de executar um fechamento de estoque a partir da data %3 (31-01-2019) que corresponde ao final de um período. A avaliação de estoques, custo dos produtos vendidos e variações podem não estar corretos no razão auxiliar ou na contabilidade até que o fechamento do estoque seja executado.

## <a name="inventory-aging-report-discrepancies"></a>Discrepâncias no relatório de classificação por vencimento do estoque

O **Relatório de classificação por vencimento do estoque** mostra diferentes valores quando exibidos em diferentes dimensões de armazenamento (como local ou depósito). Para obter mais informações sobre a lógica de relatório, consulte [Exemplos de relatório de classificação por vencimento do estoque e lógica](inventory-aging-report.md).
