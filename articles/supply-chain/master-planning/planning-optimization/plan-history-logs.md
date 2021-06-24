---
title: Exibir logs de histórico de plano e de planejamento
description: Este tópico explica como exibir o histórico de trabalhos de planejamento disparados pela funcionalidade Otimização de Planejamento.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187238"
---
# <a name="view-plan-history-and-planning-logs"></a>Exibir logs de histórico de plano e de planejamento

[!include [banner](../../includes/banner.md)]

Este tópico explica como exibir o histórico de trabalhos de planejamento disparados pela funcionalidade Otimização de Planejamento no Microsoft Dynamics 365 Supply Chain Management.

Para exibir o histórico de um plano, abra o plano em **Planejamento mestre** \> **Configuração** \> **Planos** \> **Planos mestres** e selecione **Histórico**. O histórico lista todos os trabalhos do plano selecionado. A lista inclui os trabalhos concluídos e ativos.

O histórico dos trabalhos para execuções de planejamento mestre da Otimização de Planejamento mantém apenas até 60 registros por plano mestre. Sempre que você executa um novo cálculo de planejamento mestre, o registro histórico mais antigo desse plano é excluído.

Além de verificar a hora inicial e o status de trabalhos, você pode exibir o log para um determinado trabalho. O log inclui informações e avisos adicionais. Nem todos os trabalhos têm um log. Para exibir o log para um trabalho, selecione **Log**. As entradas de registro só são armazenadas por 30 dias após a data de término do trabalho, depois disso, são automaticamente excluídas.

## <a name="related-resources"></a>Recursos relacionados

- [Visão geral da Otimização do Planejamento](planning-optimization-overview.md)
- [Introdução à Otimização do Planejamento](get-started.md)
- [Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)
- [Aplicar filtros a um plano](plan-filters.md)
- [Cancelar um trabalho de planejamento](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]