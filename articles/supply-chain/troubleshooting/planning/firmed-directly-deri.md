---
title: Os pedidos firmados derivados diretamente são processados por um fluxo de trabalho em análise
description: Os pedidos firmados derivados diretamente são processados por um fluxo de trabalho que tem o status Em análise.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d54985707d82df2b947a7cb615fc25f90aa31702
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026277"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a><span data-ttu-id="220a2-103">Os pedidos firmados derivados diretamente são processados por um fluxo de trabalho em análise</span><span class="sxs-lookup"><span data-stu-id="220a2-103">Directly derived firmed orders are processed by an in-review workflow</span></span>

<span data-ttu-id="220a2-104">Número da base de dados de conhecimento: 4612450</span><span class="sxs-lookup"><span data-stu-id="220a2-104">KB number: 4612450</span></span>

## <a name="symptoms"></a><span data-ttu-id="220a2-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="220a2-105">Symptoms</span></span>

<span data-ttu-id="220a2-106">Os pedidos firmados derivados diretamente são processados por um fluxo de trabalho que tem o status *Em análise*.</span><span class="sxs-lookup"><span data-stu-id="220a2-106">Directly derived firmed orders are processed by a workflow that has a status of *In-review*.</span></span>

## <a name="resolution"></a><span data-ttu-id="220a2-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="220a2-107">Resolution</span></span>

<span data-ttu-id="220a2-108">Quando o Controle de Alterações está habilitado, o status de *Em análise* é atribuído aos pedidos derivados firmados (pedidos de compra do subcontrato).</span><span class="sxs-lookup"><span data-stu-id="220a2-108">When change tracking is enabled, a status of *In-review* is assigned to firmed derived orders (subcontract purchase orders).</span></span> <span data-ttu-id="220a2-109">Portanto, se um pedido de compra for derivado (um pedido de compras do subcontrato), ele é enviado somente a um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="220a2-109">Therefore, if a purchase order is derived (a subcontract purchase order), it's only submitted to a workflow.</span></span> <span data-ttu-id="220a2-110">Se um pedido de compra for um pedido de compra planejado firmado, ele é automaticamente aprovado para garantir que o mecanismo de planejamento não crie novos pedidos planejados enquanto o pedido de compra ainda estiver no status *Rascunho*.</span><span class="sxs-lookup"><span data-stu-id="220a2-110">If a purchase order is a firmed planned purchase order, it's automatically approved to ensure that the planning engine doesn't create new planned orders while the purchase order is still in *Draft* status.</span></span>
