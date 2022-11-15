---
title: Cancelar um trabalho de planejamento
description: Este artigo explica como cancelar um trabalho de planejamento ativo que usa a funcionalidade Otimização do planejamento.
author: t-benebo
ms.date: 02/18/2020
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
ms.openlocfilehash: f5f1f2c8e3e43e36d837ebf989422b0dca7819d6
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741167"
---
# <a name="cancel-a-planning-job"></a>Cancelar um trabalho de planejamento

[!include [banner](../../includes/banner.md)]

No Microsoft Dynamics 365 Supply Chain Management, você cancela um trabalho de planejamento ativo que usa a funcionalidade de otimização do planejamento. Ao selecionar **Cancelar** na caixa de diálogo quando um trabalho de otimização de planejamento é acionado diretamente da interface do usuário (não em segundo plano), isso não cancelará o trabalho de otimização de planejamento. Mesmo se você receber um aviso como “Operação cancelada”, ainda será necessário seguir as etapas abaixo para cancelar um trabalho de planejamento com a otimização de planejamento.

Para cancelar um trabalho de planejamento ativo, siga estas etapas.

> [!NOTE]
> Somente é possível cancelar trabalhos ativos.

1. Acesse **Planejamento mestre \> Configuração \> Planos**.
2. Selecione um plano apropriado para a execução do planejamento.
3. Selecione **Histórico**.
4. Selecione o trabalho de planejamento a ser cancelado.
5. Selecione **Cancelar**.

O status do trabalho será **Cancelando** até o serviço de otimização do planejamento confirmar que o trabalho foi cancelado. O status mudará para **Cancelado**.

> [!NOTE]
> Para ver as alterações de status, atualize a página selecionando o botão **Atualizar**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]