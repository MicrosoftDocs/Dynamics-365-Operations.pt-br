---
title: Cancelar um trabalho de planejamento
description: Este tópico explica como cancelar um trabalho de planejamento ativo que usa a funcionalidade de otimização do planejamento.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
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
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773904"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a>Cancelar um trabalho de planejamento

No Microsoft Dynamics 365 Supply Chain Management, você cancela um trabalho de planejamento ativo que usa a funcionalidade de otimização do planejamento.

Para cancelar um trabalho de planejamento ativo, siga estas etapas.

> [!NOTE]
> Somente é possível cancelar trabalhos ativos.

1. Vá para **Planejamento mestre \> Configuração \> Planos**.
2. Selecione um plano apropriado para a execução do planejamento.
3. Selecione **Histórico**.
4. Selecione o trabalho de planejamento a ser cancelado.
5. Selecione **Cancelar**.

O status do trabalho será **Cancelando** até o serviço de otimização do planejamento confirmar que o trabalho foi cancelado. O status mudará para **Cancelado**.

> [!NOTE]
> Para ver as alterações de status, atualize a página selecionando o botão **Atualizar**.

## <a name="related-resources"></a>Recursos relacionados

[Visão geral da otimização do planejamento](planning-optimization-overview.md)

[Introdução à Otimização de Planejamento](get-started.md)

[Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)

[Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)

[Aplicar filtros a um plano](plan-filters.md)
