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
# <a name="approve-planned-orders"></a><span data-ttu-id="384bb-103">Aprovar ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="384bb-103">Approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="384bb-104">Este tópico fornece informações sobre como atualizar o status de ordens planejadas na Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="384bb-104">This topic provides information about how to update the status of planned orders in Planning Optimization.</span></span>

<span data-ttu-id="384bb-105">Observe que a aprovação de ordens planejadas é uma etapa opcional no caminho de criação de uma ordem confirmada com base em uma ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="384bb-105">Note that approval of planned orders is an optional step, on the way to create a firmed order from a planned order.</span></span> <span data-ttu-id="384bb-106">É recomendável aprovar ordens planejadas modificadas, caso contrário, as edições serão ignoradas e substituídas pela próxima execução de planejamento.</span><span class="sxs-lookup"><span data-stu-id="384bb-106">It is recommended to approve modified planned orders, otherwise the edits will be ignored and overwritten by the next planning run.</span></span>

![Fluxo de ordem planejada](media/approved-planned-orders-1.png)

<span data-ttu-id="384bb-108">O campo **Status** ajuda você a acompanhar seu progresso usando os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="384bb-108">The **Status** field helps you tack your progress using the following values:</span></span>

- <span data-ttu-id="384bb-109">**Não processado:** quando o planejamento mestre gerar ordens planejadas, elas terão o status *Não processado*.</span><span class="sxs-lookup"><span data-stu-id="384bb-109">**Unprocessed:** When master planning generates planned orders, the planned orders have a status of *Unprocessed*.</span></span> <span data-ttu-id="384bb-110">As ordens planejadas com esse status serão excluídas durante a próxima execução de planejamento.</span><span class="sxs-lookup"><span data-stu-id="384bb-110">Planned orders with this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="384bb-111">**Concluído:** se você decidir não confirmar uma ordem planejada, poderá alterar o status para *Concluído* a fim de indicar que concluiu a avaliação dessa ordem.</span><span class="sxs-lookup"><span data-stu-id="384bb-111">**Completed:** If you decide not to firm a planned order, you can change the status to *Completed* to indicate that you completed evaluating this planned order.</span></span> <span data-ttu-id="384bb-112">Observe que os status *Não processado* e *Concluído* são tratados da mesma forma pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="384bb-112">Note that a status of *Unprocessed* and *Completed* are treated the same by the system.</span></span>
- <span data-ttu-id="384bb-113">**Aprovado:** se você quiser manter as edições ou estiver planejando confirmar uma ordem planejada, altere o status para *Aprovado*.</span><span class="sxs-lookup"><span data-stu-id="384bb-113">**Approved:** If you want to keep edits or are planning to firm a planned order, change the status to *Approved*.</span></span> <span data-ttu-id="384bb-114">As ordens planejadas com o status *Aprovado* são consideradas como fornecimento fixo e esperado pelo planejamento mestre, portanto, não são modificadas nem excluídas durante execuções posteriores dele.</span><span class="sxs-lookup"><span data-stu-id="384bb-114">Planned orders with *Approved* status are considered as fixed and expected supply by master planning, so they are not modified or deleted during later master planning runs.</span></span> <span data-ttu-id="384bb-115">Para fazer isso, a lógica de planejamento copia as ordens planejadas *Aprovadas* da versão anterior do plano para a nova versão do plano durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="384bb-115">To achieve this, the planning logic copies the *Approved* planned orders from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="384bb-116">Observe que as ordens planejadas com o status *Aprovado* só são consideradas fornecimento no plano mestre específico.</span><span class="sxs-lookup"><span data-stu-id="384bb-116">Note that *Approved* planned orders are only considered supply within the specific master plan.</span></span>

<span data-ttu-id="384bb-117">Você pode gerenciar ordens planejadas no espaço de trabalho **Planejamento mestre**, na lista **Ordem planejada** ou nas listas **Ordens de produção planejadas**, **Ordens de compra planejadas** e **Transferência planejada**.</span><span class="sxs-lookup"><span data-stu-id="384bb-117">You can manage planned orders from the  **Master planning**  workspace, the  **Planned order**  list, or the  **Planned production orders**,  **Planned purchase orders**, and  **Planned transfer**  lists.</span></span>
