---
title: Manter ordens planejadas
description: "Este artigo oferece informações sobre como gerenciar ordens planejadas. Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3d7afda9371b4d21e58f2e56de3d477b1c9950a1
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="maintain-planned-orders"></a><span data-ttu-id="f3b55-104">Manter ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="f3b55-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3b55-105">Este artigo oferece informações sobre como gerenciar ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="f3b55-105">This article provides information about how to manage planned orders.</span></span> <span data-ttu-id="f3b55-106">Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada.</span><span class="sxs-lookup"><span data-stu-id="f3b55-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="f3b55-107">Você pode gerenciar ordens planejados no espaço de trabalho **Planejamento mestre**, na lista **Ordem planejada** ou nas listas **Ordens de produção planejadas**, **Ordens de compra planejadas** e **Transferência planejada**.</span><span class="sxs-lookup"><span data-stu-id="f3b55-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="f3b55-108">Você pode usar o campo **Status** para ajudar a acompanhar seu progresso.</span><span class="sxs-lookup"><span data-stu-id="f3b55-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="f3b55-109">Os seguintes valores são usados:</span><span class="sxs-lookup"><span data-stu-id="f3b55-109">The following values are used:</span></span>

-   <span data-ttu-id="f3b55-110">Quando o planejamento mestre gerar ordens planejadas, elas terão o status **Não processado**.</span><span class="sxs-lookup"><span data-stu-id="f3b55-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="f3b55-111">Se você optar por não confirmar uma ordem planejada, poderá atribuir a ela o status **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="f3b55-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="f3b55-112">Quando você optar por confirmar uma ordem planejada, atribuirá a ela o status **Aprovado**.</span><span class="sxs-lookup"><span data-stu-id="f3b55-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="f3b55-113">Esse status indica que você aprova a confirmação da ordem planejada, mas que ela ainda não foi confirmada.</span><span class="sxs-lookup"><span data-stu-id="f3b55-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="f3b55-114">**Observação:** uma ordem planejada aprovada é transferida, no estado atual, para o próximo cálculo do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="f3b55-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="f3b55-115">É possível confirmar uma ordem planejada clicando em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f3b55-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="f3b55-116">As seguintes ordens planejadas podem ser confirmadas:</span><span class="sxs-lookup"><span data-stu-id="f3b55-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="f3b55-117">A ordem planejada selecionada.</span><span class="sxs-lookup"><span data-stu-id="f3b55-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="f3b55-118">Várias ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="f3b55-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="f3b55-119">Ordens planejadas geradas por um detalhamento da página **Detalhamento**.</span><span class="sxs-lookup"><span data-stu-id="f3b55-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="f3b55-120">Clique em **Ordens planejadas**, selecione a ordem planejada e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f3b55-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="f3b55-121">Ao ser confirmada, uma ordem planejada é movida para a seção de ordens do módulo relevante.</span><span class="sxs-lookup"><span data-stu-id="f3b55-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> <span data-ttu-id="f3b55-122">**Observação:** você pode clicar com o botão direito do mouse em uma ordem planejada que tenha um determinado status e filtrar outras ordens planejadas com o mesmo status.</span><span class="sxs-lookup"><span data-stu-id="f3b55-122">**Note:** You can right-click a planned order that has a particular status and filter for other planned orders that have the same status.</span></span> <span data-ttu-id="f3b55-123">Essa funcionalidade será útil se, por exemplo, você quiser filtrar todas as ordens planejadas cujo status seja **Aprovado**, para que possa então confirmá-las.</span><span class="sxs-lookup"><span data-stu-id="f3b55-123">This functionality is useful if, for example, you want to filter for all planned orders that have a status of **Approved**, so that you can then firm them.</span></span>

<a name="additional-resources"></a><span data-ttu-id="f3b55-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f3b55-124">Additional resources</span></span>
--------

[<span data-ttu-id="f3b55-125">Planos mestres</span><span class="sxs-lookup"><span data-stu-id="f3b55-125">Master plans</span></span>](master-plans.md)




