---
title: Lacunas funcionais entre relatórios de valor de estoque/classificação por vencimento e versões de armazenamento
description: Lacunas funcionais entre relatórios de valor de estoque/classificação por vencimento e versões de armazenamento
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f74389648034bf036ce48ac84b3421a8a340f105
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686643"
---
# <a name="functional-gaps-between-inventory-valueaging-reports-and-their-storage-versions"></a>Lacunas funcionais entre relatórios de valor de estoque/classificação por vencimento e versões de armazenamento

Os recursos [Armazenamento de relatório de classificação por vencimento do estoque](/dynamics365/supply-chain/cost-management/inventory-aging-report-storage) e [Relatório de armazenamento de valor de estoque](/dynamics365/supply-chain/cost-management/inventory-value-report-storage) permitem que o Supply Chain Management exiba grandes volumes de transações de estoque. Em cada caso, os resultados do relatório são salvos para navegação e exportação, diferentemente das versões sem armazenamento desses relatórios. Contudo, algumas funcionalidades presentes nas versões sem armazenamento desses relatórios não existem nas versões com armazenamento. As subseções a seguir resumem as diferenças e fornecem soluções alternativas.

## <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Os relatórios de armazenamento não incluem subtotais, mesmo se estiverem habilitados no layout do relatório

Os subtotais podem causar problemas quando o resultado é exportado, especialmente se os usuários alterarem a sequência de registro.

Para verificar os subtotais, você pode exportar o resultado para o Microsoft Excel. Como alternativa, se você quiser verificar os subtotais no Supply Chain Management, use o [Gerenciamento de recursos](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) para habilitar os recursos *Novo controle de grade* e *Agrupamento em grades*, que fornecem uma maneira muito mais flexível de ver o subtotal para qualquer grupo por coluna. Para obter mais informações, consulte [Recursos de grade](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities).

## <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>O relatório de armazenamento do valor do estoque não é compatível com informações da conta contábil

Você pode executar o balancete para obter o saldo das contas de estoque e compará-lo com o relatório **Armazenamento de valor de estoque**.
