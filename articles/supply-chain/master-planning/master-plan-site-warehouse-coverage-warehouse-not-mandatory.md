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
ms.search.scope: Core, Operations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b9214a8f2b62aa261b05f0b360fd03faa63ce1ea
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a><span data-ttu-id="c6aa2-104">Planejamento mestre para cobertura de site e depósito, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="c6aa2-104">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c6aa2-105">Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="c6aa2-106">A dimensão do depósito não é obrigatória.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-106">The warehouse dimension is not mandatory.</span></span>

<span data-ttu-id="c6aa2-107">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="c6aa2-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="c6aa2-108">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="c6aa2-109">Essa configuração não pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="c6aa2-110">A dimensão do depósito não está definida como obrigatória.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-110">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="c6aa2-111">O depósito pode ser conhecido, mas não é usado no cálculo do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-111">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="c6aa2-112">As dimensões do site e do depósito estão definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-112">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="c6aa2-113">Outras dimensões também podem ser definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-113">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="c6aa2-114">No entanto, elas não são afetadas pela funcionalidade multissite.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-114">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="c6aa2-115">O gráfico a seguir ilustra como o planejamento mestre ocorre.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-115">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="c6aa2-116">Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:</span><span class="sxs-lookup"><span data-stu-id="c6aa2-116">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="c6aa2-117">O depósito está definido como Manual.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-117">The warehouse is set to Manual.</span></span> <span data-ttu-id="c6aa2-118">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="c6aa2-119">Na Guia Rápida **Planejamento mestre**, consulte o campo **Manual**.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-119">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="c6aa2-120">A cobertura de item é definida para o item.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-120">Item coverage is defined for the item.</span></span> <span data-ttu-id="c6aa2-121">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="c6aa2-122">Selecione o item, e depois, no Painel de Ação, na guia **Plano**, clique em **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-122">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="c6aa2-123">As relações de reabastecimento são definidas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-123">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="c6aa2-124">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-124">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="c6aa2-125">Na Guia Rápida **Planejamento mestre**, consulte o grupo de campos **Depósito principal**.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-125">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="c6aa2-126">O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-126">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="c6aa2-127">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-127">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="c6aa2-128">Selecione o item e, no Painel de Ação, na guia **Plano**, clique em **Configurações de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-128">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="c6aa2-129">No formulário **Configurações de ordem padrão**, consulte o **Tipo de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="c6aa2-129">In the **Default order settings** form, see the **Default order type**.</span></span>

![Demanda para site e depósito, depósito não obrigatório](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)

 
-



<a name="see-also"></a><span data-ttu-id="c6aa2-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c6aa2-131">See also</span></span>
--------

[<span data-ttu-id="c6aa2-132">Planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="c6aa2-132">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="c6aa2-133">Planejamento mestre - cobertura de site e depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="c6aa2-133">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="c6aa2-134">Planejamento mestre - cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="c6aa2-134">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="c6aa2-135">Planejamento mestre - cobertura de site, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="c6aa2-135">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="c6aa2-136">Planejamento mestre – como a versão da BOM é determinada</span><span class="sxs-lookup"><span data-stu-id="c6aa2-136">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)




