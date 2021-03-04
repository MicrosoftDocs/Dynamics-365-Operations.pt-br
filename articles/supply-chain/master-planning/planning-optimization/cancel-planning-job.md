---
title: Cancelar um trabalho de planejamento
description: Este tópico explica como cancelar um trabalho de planejamento ativo que usa a funcionalidade de otimização do planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 4b65d344cd764740cc1485969c2fc4c2052e55e2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422155"
---
# <a name="cancel-a-planning-job"></a>Cancelar um trabalho de planejamento

[!include [banner](../../includes/banner.md)]

No Microsoft Dynamics 365 Supply Chain Management, você cancela um trabalho de planejamento ativo que usa a funcionalidade de otimização do planejamento. Ao selecionar **Cancelar** na caixa de diálogo quando um trabalho de otimização de planejamento é acionado diretamente da interface do usuário (não em segundo plano), isso não cancelará o trabalho de otimização de planejamento. Mesmo se você receber um aviso como “Operação cancelada”, ainda será necessário seguir as etapas abaixo para cancelar um trabalho de planejamento com a otimização de planejamento.


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

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Otimização do Planejamento](planning-optimization-overview.md)

[Introdução à Otimização de Planejamento](get-started.md)

[Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)

[Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)

[Aplicar filtros a um plano](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]