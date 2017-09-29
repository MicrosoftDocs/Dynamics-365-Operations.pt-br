---
title: "Planejamento mestre para cobertura de site e depósito, depósito não obrigatório"
description: "Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado. A dimensão do depósito não é obrigatória."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 9c7b13a7a018ce584c877fed6212abc3c2913903
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="7a8e3-104">Planejamento mestre para cobertura de site e depósito, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="7a8e3-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7a8e3-105">Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="7a8e3-106">A dimensão do depósito não é obrigatória.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="7a8e3-107">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="7a8e3-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="7a8e3-108">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="7a8e3-109">Essa configuração não pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="7a8e3-110">A dimensão do depósito não está definida como obrigatória.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="7a8e3-111">O depósito pode ser conhecido, mas não é usado no cálculo do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="7a8e3-112">As dimensões do site e do depósito estão definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="7a8e3-113">Outras dimensões também podem ser definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="7a8e3-114">No entanto, elas não são afetadas pela funcionalidade multissite.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="7a8e3-115">O gráfico a seguir ilustra como o planejamento mestre ocorre.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="7a8e3-116">Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:</span><span class="sxs-lookup"><span data-stu-id="7a8e3-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="7a8e3-117">O depósito está definido como Manual.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="7a8e3-118">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="7a8e3-119">Na Guia Rápida **Planejamento mestre**, consulte o campo **Manual**.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="7a8e3-120">A cobertura de item é definida para o item.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="7a8e3-121">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="7a8e3-122">Selecione o item, e depois, no Painel de Ação, na guia **Plano**, clique em **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-122">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="7a8e3-123">As relações de reabastecimento são definidas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="7a8e3-124">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="7a8e3-125">Na Guia Rápida **Planejamento mestre**, consulte o grupo de campos **Depósito principal**.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="7a8e3-126">O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="7a8e3-127">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="7a8e3-128">Selecione o item e, no Painel de Ação, na guia **Plano**, clique em **Configurações de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-128">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="7a8e3-129">No formulário **Configurações de ordem padrão**, consulte o **Tipo de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="7a8e3-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Demanda para site e depósito, depósito não obrigatório](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)

 
-



<a name="see-also"></a><span data-ttu-id="7a8e3-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7a8e3-131">See also</span></span>
--------

[<span data-ttu-id="7a8e3-132">Planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="7a8e3-132">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="7a8e3-133">Planejamento mestre - cobertura de site e depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="7a8e3-133">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="7a8e3-134">Planejamento mestre - cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="7a8e3-134">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="7a8e3-135">Planejamento mestre - cobertura de site, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="7a8e3-135">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="7a8e3-136">Planejamento mestre – como a versão da BOM é determinada</span><span class="sxs-lookup"><span data-stu-id="7a8e3-136">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




