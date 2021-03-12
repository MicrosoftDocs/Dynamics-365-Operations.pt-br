---
title: Planejamento mestre para cobertura de site, depósito obrigatório
description: Este tópico descreve como um item que tem o local com dimensões da cobertura é planejado. O depósito é a dimensão obrigatória.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72240e7db8ec914220cb8f8f1185a91a304ff66b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977954"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a><span data-ttu-id="64ef6-104">Planejamento mestre para cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="64ef6-104">Master planning for site coverage, mandatory warehouse</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64ef6-105">Este tópico descreve como um item que tem o local com dimensões da cobertura é planejado.</span><span class="sxs-lookup"><span data-stu-id="64ef6-105">This topic describes how an item that has the site as coverage dimension is planned.</span></span> <span data-ttu-id="64ef6-106">O depósito é a dimensão obrigatória.</span><span class="sxs-lookup"><span data-stu-id="64ef6-106">Warehouse is a mandatory dimension.</span></span>

<span data-ttu-id="64ef6-107">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="64ef6-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="64ef6-108">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="64ef6-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span> <span data-ttu-id="64ef6-109">Essa configuração não pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="64ef6-109">This setting can't be modified.</span></span>
-   <span data-ttu-id="64ef6-110">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="64ef6-110">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="64ef6-111">A dimensão do site está definida como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="64ef6-111">The site dimension is set for coverage planning.</span></span> <span data-ttu-id="64ef6-112">Outras dimensões também podem ser definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="64ef6-112">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="64ef6-113">No entanto, elas não são afetadas pela funcionalidade multissite.</span><span class="sxs-lookup"><span data-stu-id="64ef6-113">However, they are not affected by the multisite functionality.</span></span>
-   <span data-ttu-id="64ef6-114">A dimensão do depósito não está definida como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="64ef6-114">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="64ef6-115">Assim, a oferta e a demanda são agregadas por site (e talvez outras dimensões de cobertura planejada também).</span><span class="sxs-lookup"><span data-stu-id="64ef6-115">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="64ef6-116">O gráfico a seguir ilustra como o planejamento mestre ocorre.</span><span class="sxs-lookup"><span data-stu-id="64ef6-116">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="64ef6-117">Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:</span><span class="sxs-lookup"><span data-stu-id="64ef6-117">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="64ef6-118">A cobertura de item é definida para o item.</span><span class="sxs-lookup"><span data-stu-id="64ef6-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="64ef6-119">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="64ef6-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="64ef6-120">Selecione o item e então clique em **Planejar &gt; Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="64ef6-120">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="64ef6-121">As relações de reabastecimento são definidas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="64ef6-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="64ef6-122">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="64ef6-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="64ef6-123">Na guia **Planejamento mestre**, consulte o grupo de campos **Depósito principal** .</span><span class="sxs-lookup"><span data-stu-id="64ef6-123">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="64ef6-124">O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="64ef6-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="64ef6-125">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="64ef6-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="64ef6-126">Selecione o item e clique em **Planejar &gt; Configurações padrão da ordem**.</span><span class="sxs-lookup"><span data-stu-id="64ef6-126">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="64ef6-127">No formulário **Configurações de ordem padrão**, consulte o **Tipo de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="64ef6-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Demanda para cobertura de site, depósito obrigatório    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="64ef6-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="64ef6-129">Additional resources</span></span>
--------

[<span data-ttu-id="64ef6-130">Visão geral de planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="64ef6-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="64ef6-131">Planejamento mestre para de site e cobertura de depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="64ef6-131">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="64ef6-132">Planejamento mestre para cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="64ef6-132">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="64ef6-133">Planejamento mestre para de site e cobertura de depósito, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="64ef6-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="64ef6-134">Determinar a versão da BOM</span><span class="sxs-lookup"><span data-stu-id="64ef6-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)



