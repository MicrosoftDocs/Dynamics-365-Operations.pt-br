---
title: Aprovar ordens planejadas
description: Este tópico descreve a aprovação de ordens planejadas com suporte na Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 08/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c29ede7ad8916a97b4a04b68f41961f79810e0c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983560"
---
# <a name="approve-planned-orders"></a>Aprovar ordens planejadas

[!include [banner](../../includes/banner.md)]

Este tópico fornece informações sobre como atualizar o status de ordens planejadas na Otimização de Planejamento.

Observe que a aprovação de ordens planejadas é uma etapa opcional no caminho de criação de uma ordem confirmada com base em uma ordem planejada. É recomendável aprovar ordens planejadas modificadas, caso contrário, as edições serão ignoradas e substituídas pela próxima execução de planejamento.

![Fluxo de ordem planejada](media/approved-planned-orders-1.png)

O campo **Status** ajuda você a acompanhar seu progresso usando os seguintes valores:

- **Não processado:** quando o planejamento mestre gerar ordens planejadas, elas terão o status *Não processado*. As ordens planejadas com esse status serão excluídas durante a próxima execução de planejamento.
- **Concluído:** se você decidir não confirmar uma ordem planejada, poderá alterar o status para *Concluído* a fim de indicar que concluiu a avaliação dessa ordem. Observe que os status *Não processado* e *Concluído* são tratados da mesma forma pelo sistema.
- **Aprovado:** se você quiser manter as edições ou estiver planejando confirmar uma ordem planejada, altere o status para *Aprovado*. As ordens planejadas com o status *Aprovado* são consideradas como fornecimento fixo e esperado pelo planejamento mestre, portanto, não são modificadas nem excluídas durante execuções posteriores dele. Para fazer isso, a lógica de planejamento copia as ordens planejadas *Aprovadas* da versão anterior do plano para a nova versão do plano durante o planejamento mestre. Observe que as ordens planejadas com o status *Aprovado* só são consideradas fornecimento no plano mestre específico.

Você pode gerenciar ordens planejadas no espaço de trabalho **Planejamento mestre**, na lista **Ordem planejada** ou nas listas **Ordens de produção planejadas**, **Ordens de compra planejadas** e **Transferência planejada**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]