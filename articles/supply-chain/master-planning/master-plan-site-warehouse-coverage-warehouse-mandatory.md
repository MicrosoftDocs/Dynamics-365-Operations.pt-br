---
title: Planejamento mestre para cobertura de site e depósito, depósito obrigatório
description: Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado. A dimensão do depósito é obrigatória.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 132a7171488b3c4da8ef13e11bed87c78071744d
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187449"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a><span data-ttu-id="d3b29-104">Planejamento mestre para cobertura de site e depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="d3b29-104">Master planning for site and warehouse coverage, warehouse mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d3b29-105">Este tópico descreve como um item que tem o local e o depósito como dimensões da cobertura é planejado.</span><span class="sxs-lookup"><span data-stu-id="d3b29-105">This topic describes how an item that has site and warehouse as coverage dimensions is planned.</span></span> <span data-ttu-id="d3b29-106">A dimensão do depósito é obrigatória.</span><span class="sxs-lookup"><span data-stu-id="d3b29-106">The warehouse dimension is mandatory.</span></span>

<span data-ttu-id="d3b29-107">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="d3b29-107">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="d3b29-108">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="d3b29-108">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="d3b29-109">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="d3b29-109">The warehouse dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="d3b29-110">As dimensões do site e do depósito estão definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="d3b29-110">The site and warehouse dimensions are set for coverage planning.</span></span> <span data-ttu-id="d3b29-111">Outras dimensões também podem ser definidas como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="d3b29-111">Other dimensions may be set for coverage planning also.</span></span> <span data-ttu-id="d3b29-112">No entanto, elas não são afetadas pela funcionalidade multissite.</span><span class="sxs-lookup"><span data-stu-id="d3b29-112">However, they are not affected by the multisite functionality.</span></span>

<span data-ttu-id="d3b29-113">O gráfico a seguir ilustra como o planejamento mestre ocorre.</span><span class="sxs-lookup"><span data-stu-id="d3b29-113">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="d3b29-114">Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:</span><span class="sxs-lookup"><span data-stu-id="d3b29-114">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="d3b29-115">O depósito está definido como **Manual**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-115">The warehouse is set to **Manual**.</span></span> <span data-ttu-id="d3b29-116">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-116">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="d3b29-117">Na Guia Rápida **Planejamento mestre**, consulte o campo **Manual**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-117">On the **Master planning** FastTab, see the **Manual** field.</span></span>
-   <span data-ttu-id="d3b29-118">A cobertura de item é definida para o item.</span><span class="sxs-lookup"><span data-stu-id="d3b29-118">Item coverage is defined for the item.</span></span> <span data-ttu-id="d3b29-119">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-119">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="d3b29-120">Selecione o item, e depois, no Painel de Ações, na guia **Plano**, clique em **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-120">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Item coverage**.</span></span>
-   <span data-ttu-id="d3b29-121">As relações de reabastecimento são definidas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="d3b29-121">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="d3b29-122">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-122">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="d3b29-123">Na Guia Rápida **Planejamento mestre**, consulte o grupo de campos **Depósito principal**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-123">On the **Master planning** FastTab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="d3b29-124">O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="d3b29-124">The default order type is set to Production, Purchase order, or Kanban.</span></span> <span data-ttu-id="d3b29-125">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-125">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="d3b29-126">Selecione o item e, no Painel de Ações, na guia **Plano**, clique em **Configurações de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-126">Select the item, and then, on the Action Pane, on the **Plan** tab, click **Default order settings**.</span></span> <span data-ttu-id="d3b29-127">No formulário **Configurações de ordem padrão**, consulte o **Tipo de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="d3b29-127">In the **Default order settings** form, see the **Default order type**.</span></span>

![Cobertura de demanda do depósito e do site, depósito obrigatório](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a><span data-ttu-id="d3b29-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d3b29-129">Additional resources</span></span>

[<span data-ttu-id="d3b29-130">Visão geral de planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="d3b29-130">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="d3b29-131">Planejamento mestre para cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="d3b29-131">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="d3b29-132">Planejamento mestre para cobertura de site, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="d3b29-132">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="d3b29-133">Planejamento mestre para de site e cobertura de depósito, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="d3b29-133">Master planning for site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="d3b29-134">Determinar a versão da BOM</span><span class="sxs-lookup"><span data-stu-id="d3b29-134">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]