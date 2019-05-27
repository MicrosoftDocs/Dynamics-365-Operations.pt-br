---
title: Planejamento mestre para cobertura de site e depósito, depósito obrigatório
description: Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado. A dimensão do depósito é obrigatória.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c52fc9955afe2a7502d0e1f9e7cdfc5b89bbb31d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559266"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="f241f-104">Planejamento mestre para cobertura de site e depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="f241f-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f241f-105">Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado.</span><span class="sxs-lookup"><span data-stu-id="f241f-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="f241f-106">A dimensão do depósito é obrigatória.</span><span class="sxs-lookup"><span data-stu-id="f241f-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="f241f-107">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="f241f-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="f241f-108">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="f241f-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="f241f-109">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="f241f-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="f241f-110">As dimensões do site e do depósito estão definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="f241f-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="f241f-111">Outras dimensões também podem ser definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="f241f-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="f241f-112">No entanto, elas não são afetadas pela funcionalidade multissite.</span><span class="sxs-lookup"><span data-stu-id="f241f-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="f241f-113">O gráfico a seguir ilustra como o planejamento mestre ocorre.</span><span class="sxs-lookup"><span data-stu-id="f241f-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="f241f-114">Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:</span><span class="sxs-lookup"><span data-stu-id="f241f-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="f241f-115">O depósito está definido como **Manual**.</span><span class="sxs-lookup"><span data-stu-id="f241f-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="f241f-116">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="f241f-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="f241f-117">Na Guia Rápida **Planejamento mestre**, consulte o campo **Manual**.</span><span class="sxs-lookup"><span data-stu-id="f241f-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="f241f-118">A cobertura de item é definida para o item.</span><span class="sxs-lookup"><span data-stu-id="f241f-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="f241f-119">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="f241f-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="f241f-120">Selecione o item, e depois, no Painel de Ação, na guia **Plano**, clique em **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="f241f-120">Select the item, and then, on the Action pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="f241f-121">As relações de reabastecimento são definidas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="f241f-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="f241f-122">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="f241f-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="f241f-123">Na Guia Rápida **Planejamento mestre**, consulte o grupo de campos **Depósito principal**.</span><span class="sxs-lookup"><span data-stu-id="f241f-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="f241f-124">O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="f241f-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="f241f-125">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="f241f-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="f241f-126">Selecione o item e, no Painel de Ação, na guia **Plano**, clique em **Configurações de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="f241f-126">Select the item, and then, on the Action pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="f241f-127">No formulário **Configurações de ordem padrão**, consulte o **Tipo de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="f241f-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Cobertura de demanda do depósito e do site, depósito obrigatório](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="f241f-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f241f-129">Additional resources</span></span>
--------

[<span data-ttu-id="f241f-130">Planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="f241f-130">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="f241f-131">Planejamento mestre - cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="f241f-131">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="f241f-132">Planejamento mestre - cobertura de site, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="f241f-132">Master planning - site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="f241f-133">Planejamento mestre - cobertura de site e depósito, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="f241f-133">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="f241f-134">Planejamento mestre – como a versão da BOM é determinada</span><span class="sxs-lookup"><span data-stu-id="f241f-134">Master planning - How the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



