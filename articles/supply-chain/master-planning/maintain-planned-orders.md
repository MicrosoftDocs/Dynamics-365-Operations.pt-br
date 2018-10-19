---
title: Manter ordens planejadas
description: "Este tópico fornece informações sobre como gerenciar ordens planejadas. Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada."
author: roxanadiaconu
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 657c19896b20a514dc5308bf7fb086085b482fec
ms.openlocfilehash: bf578d98abc4825c5607ec031da6ab6737c3183a
ms.contentlocale: pt-br
ms.lasthandoff: 10/08/2018

---

# <a name="maintain-planned-orders"></a><span data-ttu-id="15589-104">Manter ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="15589-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15589-105">Este tópico fornece informações sobre como gerenciar ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="15589-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="15589-106">Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada.</span><span class="sxs-lookup"><span data-stu-id="15589-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="15589-107">Você pode gerenciar ordens planejados no espaço de trabalho **Planejamento mestre**, na lista **Ordem planejada** ou nas listas **Ordens de produção planejadas**, **Ordens de compra planejadas** e **Transferência planejada**.</span><span class="sxs-lookup"><span data-stu-id="15589-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="15589-108">Você pode usar o campo **Status** para ajudar a acompanhar seu progresso.</span><span class="sxs-lookup"><span data-stu-id="15589-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="15589-109">Os seguintes valores são usados:</span><span class="sxs-lookup"><span data-stu-id="15589-109">The following values are used:</span></span>

-   <span data-ttu-id="15589-110">Quando o planejamento mestre gerar ordens planejadas, elas terão o status **Não processado**.</span><span class="sxs-lookup"><span data-stu-id="15589-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="15589-111">Se você optar por não confirmar uma ordem planejada, poderá atribuir a ela o status **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="15589-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="15589-112">Quando você optar por confirmar uma ordem planejada, atribuirá a ela o status **Aprovado**.</span><span class="sxs-lookup"><span data-stu-id="15589-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="15589-113">Esse status indica que você aprova a confirmação da ordem planejada, mas que ela ainda não foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="15589-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="15589-114">**Observação:** uma ordem planejada aprovada é transferida, no estado atual, para o próximo cálculo do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="15589-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="15589-115">É possível confirmar uma ordem planejada clicando em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="15589-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="15589-116">As seguintes ordens planejadas podem ser confirmadas:</span><span class="sxs-lookup"><span data-stu-id="15589-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="15589-117">A ordem planejada selecionada.</span><span class="sxs-lookup"><span data-stu-id="15589-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="15589-118">Várias ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="15589-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="15589-119">Ordens planejadas geradas por um detalhamento da página **Detalhamento**.</span><span class="sxs-lookup"><span data-stu-id="15589-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="15589-120">Clique em **Ordens planejadas**, selecione a ordem planejada e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="15589-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="15589-121">Ao ser confirmada, uma ordem planejada é movida para a seção de ordens do módulo relevante.</span><span class="sxs-lookup"><span data-stu-id="15589-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> 

<a name="additional-resources"></a><span data-ttu-id="15589-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="15589-122">Additional resources</span></span>
--------

[<span data-ttu-id="15589-123">Planos mestres</span><span class="sxs-lookup"><span data-stu-id="15589-123">Master plans</span></span>](master-plans.md)




