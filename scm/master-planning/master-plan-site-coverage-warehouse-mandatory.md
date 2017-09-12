---
title: "Planejamento mestre para cobertura de site, depósito obrigatório"
description: "Este tópico descreve como um item que tem o local com dimensões da cobertura é planejado. O depósito é a dimensão obrigatória."
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
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 14df626025a22237afe30cc5b08d42b475fc3a4f
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="03fd3-104">Planejamento mestre para cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="03fd3-104">Master planning for site coverage, mandatory warehouse</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="03fd3-105">Este tópico descreve como um item que tem o local com dimensões da cobertura é planejado.</span><span class="sxs-lookup"><span data-stu-id="03fd3-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="03fd3-106">O depósito é a dimensão obrigatória.</span><span class="sxs-lookup"><span data-stu-id="03fd3-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="03fd3-107">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="03fd3-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="03fd3-108">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="03fd3-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="03fd3-109">Essa configuração não pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="03fd3-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="03fd3-110">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="03fd3-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="03fd3-111">A dimensão do site está definida como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="03fd3-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="03fd3-112">Outras dimensões também podem ser definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="03fd3-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="03fd3-113">No entanto, elas não são afetadas pela funcionalidade multissite.</span><span class="sxs-lookup"><span data-stu-id="03fd3-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="03fd3-114">A dimensão do depósito não está definida como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="03fd3-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="03fd3-115">Assim, a oferta e a demanda são agregadas por site (e talvez outras dimensões de cobertura planejada também).</span><span class="sxs-lookup"><span data-stu-id="03fd3-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="03fd3-116">O gráfico a seguir ilustra como o planejamento mestre ocorre.</span><span class="sxs-lookup"><span data-stu-id="03fd3-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="03fd3-117">Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:</span><span class="sxs-lookup"><span data-stu-id="03fd3-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="03fd3-118">A cobertura de item é definida para o item.</span><span class="sxs-lookup"><span data-stu-id="03fd3-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="03fd3-119">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="03fd3-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="03fd3-120">Selecione o item e então clique em **Planejar &gt; Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="03fd3-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="03fd3-121">As relações de reabastecimento são definidas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="03fd3-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="03fd3-122">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="03fd3-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="03fd3-123">Na guia **Planejamento mestre**, consulte o grupo de campos **Depósito principal** .</span><span class="sxs-lookup"><span data-stu-id="03fd3-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="03fd3-124">O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="03fd3-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="03fd3-125">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="03fd3-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="03fd3-126">Selecione o item e clique em **Planejar &gt; Configurações padrão da ordem**.</span><span class="sxs-lookup"><span data-stu-id="03fd3-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="03fd3-127">No formulário **Configurações de ordem padrão**, consulte o **Tipo de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="03fd3-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Demanda para cobertura de site, depósito obrigatório](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a><span data-ttu-id="03fd3-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="03fd3-129">See also</span></span>
--------

[<span data-ttu-id="03fd3-130">Planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="03fd3-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="03fd3-131">Planejamento mestre - cobertura de site e depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="03fd3-131">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="03fd3-132">Planejamento mestre - cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="03fd3-132">Master planning - site coverage. warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="03fd3-133">Planejamento mestre - cobertura de site e depósito, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="03fd3-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="03fd3-134">Planejamento mestre – como a versão da BOM é determinada</span><span class="sxs-lookup"><span data-stu-id="03fd3-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




