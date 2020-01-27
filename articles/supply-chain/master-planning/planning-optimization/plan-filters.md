---
title: Aplicar filtros a um plano
description: Este tópico explica como usar filtros em um plano quando a funcionalidade Otimização de Planejamento for usada.
author: ChristianRytt
manager: AnnBe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 9d1431cc8db6fb28d1f1ec73ee07dd15e78f82e8
ms.sourcegitcommit: 65f4b8a751670a7fe9ef4cb8b218213f792d57a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945410"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="apply-filters-to-a-plan"></a>Aplicar filtros a um plano

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
> Você deve evitar definir um filtro de plano no plano selecionado como **Plano mestre dinâmico atual** na página **Parâmetros de planejamento mestre**. Caso contrário, a funcionalidade de plano mestre dinâmico ficará limitada aos itens filtrados. Por exemplo, se os requisitos líquidos forem atualizados para um item e não fizerem parte do filtro de plano, nenhum resultado será gerado.

## <a name="related-resources"></a>Recursos relacionados

[Visão geral da Otimização de Planejamento](planning-optimization-overview.md)

[Introdução à Otimização de Planejamento](get-started.md)

[Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)

[Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)

[Cancelar um trabalho de planejamento](cancel-planning-job.md)
