---
title: Avaliar todas as ações para diretivas de localização de várias SKUs
description: Um novo recurso foi adicionado para avaliar todas as ações de diretivas de local de várias SKUs. Esta página orienta sobre você sobre a ativação.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 45995ed6f051cdf6be2b2985ff0e2cb1decf4cf0
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475563"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>A opção Várias SKU não avalia as ações da diretiva de vários locais

## <a name="symptoms"></a>Sintomas

As diretivas de local do tipo de ordem de trabalho *Ordens de venda* e do tipo de trabalho *Colocar* não avaliam várias ações da diretiva de local quando a opção **Várias SKUs** é selecionada. Somente a primeira ação da diretiva de local é avaliada.

## <a name="resolution"></a>Resolução

Um novo recurso, *Avaliar todas as ações para diretivas de local Várias SKUs*, foi adicionado na versão 10.0.15 (consulte [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Esse recurso avalia todas as ações para diretivas de local Várias SKUs. Se você precisar desse recurso, use o [Gerenciamento de recursos](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) para ativá-lo.
