---
title: Aplicar filtros a um plano
description: Este artigo explica como usar filtros em um plano quando a funcionalidade Otimização de Planejamento for usada.
author: t-benebo
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: c2df379be0876225bc7b0301d21f4e6660b04eb6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875294"
---
# <a name="apply-filters-to-a-plan"></a>Aplicar filtros a um plano

[!include [banner](../../includes/banner.md)]

Quando a funcionalidade Otimização de Planejamento for usada, você poderá aplicar um filtro a um plano. O **Filtro do plano** sempre será aplicado durante uma execução de planejamento mestre. Um **Filtro do plano** é útil quando você deseja limitar um plano a um grupo de itens específico e garantir que nenhum outro item seja incluído como parte do planejamento mestre resultante.

Se um **Filtro do plano** for aplicado, e um filtro de runtime também for aplicado durante a execução do planejamento mestre, somente a interseção dos dois filtros será incluída na execução do planejamento.

O **Filtro do plano** pode ser acessado dos **Planos mestre** quando a Otimização de Planejamento for usada.

## <a name="example-scenario"></a>Cenário de exemplo

Um filtro de plano é configurado para incluir os itens A, B e C. Em seguida, são feitas execuções do planejamento mestre para o mesmo plano, mas filtros de runtime diferentes são aplicados:

- **Filtro de runtime que inclui o item D:** nenhum item é planejado, já que não há interseção entre o filtro de plano e filtro de runtime.
- **Filtro de runtime que inclui os itens A e D:** somente o item A é incluído na execução do planejamento, já que o item D não faz parte do filtro de plano.
- **Filtro de runtime que inclui o item B:** somente o item B é incluído na execução do planejamento, e a saída de planejamento anterior para o item A é mantida.
- **Filtro de runtime que inclui todos os itens (filtros em branco):** os itens A, B e C são incluídos na execução do planejamento, e a saída do planejamento anterior para os itens A e B é substituída.

> [!NOTE]
> Se você definir um filtro de plano no plano selecionado como o **Plano mestre dinâmico atual** na página **Parâmetros de planejamento mestre**, a funcionalidade do plano mestre dinâmico ficará limitada aos itens filtrados. Por exemplo, se os requisitos líquidos forem atualizados para um item e não fizerem parte do filtro de plano, nenhum resultado será gerado.

## <a name="related-resources"></a>Recursos relacionados

[Visão geral da Otimização de Planejamento](planning-optimization-overview.md)

[Introdução à Otimização de Planejamento](get-started.md)

[Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)

[Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)

[Cancelar um trabalho de planejamento](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
