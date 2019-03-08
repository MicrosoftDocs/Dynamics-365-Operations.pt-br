---
title: Planejamento mestre para cobertura de site, depósito não obrigatório
description: Este tópico descreve como um item com o conjunto de dimensões do local da cobertura é planejado.
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
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9475a7fbe40d7feb60c23e0d7164222469dffa75
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "353922"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="dece9-103">Planejamento mestre para cobertura de site, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="dece9-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dece9-104">Este tópico descreve como um item com o conjunto de dimensões do local da cobertura é planejado.</span><span class="sxs-lookup"><span data-stu-id="dece9-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="dece9-105">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="dece9-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="dece9-106">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="dece9-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="dece9-107">A dimensão do depósito não está definida como obrigatória.</span><span class="sxs-lookup"><span data-stu-id="dece9-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="dece9-108">O depósito pode ser conhecido, mas não é usado no cálculo do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="dece9-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="dece9-109">A dimensão do site está definida como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="dece9-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="dece9-110">A dimensão do depósito não está definida como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="dece9-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="dece9-111">Assim, a oferta e a demanda são agregadas por site (e talvez outras dimensões de cobertura planejada também).</span><span class="sxs-lookup"><span data-stu-id="dece9-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="dece9-112">O gráfico a seguir ilustra como o planejamento mestre ocorre.</span><span class="sxs-lookup"><span data-stu-id="dece9-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="dece9-113">Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:</span><span class="sxs-lookup"><span data-stu-id="dece9-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="dece9-114">A cobertura de item é definida para o item.</span><span class="sxs-lookup"><span data-stu-id="dece9-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="dece9-115">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="dece9-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="dece9-116">Selecione o item e então clique em **Planejar &gt; Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="dece9-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="dece9-117">As relações de reabastecimento são definidas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="dece9-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="dece9-118">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="dece9-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="dece9-119">Na guia **Planejamento mestre**, consulte o grupo de campos **Depósito principal** .</span><span class="sxs-lookup"><span data-stu-id="dece9-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="dece9-120">O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="dece9-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="dece9-121">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="dece9-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="dece9-122">Selecione o item e clique em **Planejar &gt; Configurações padrão da ordem**.</span><span class="sxs-lookup"><span data-stu-id="dece9-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="dece9-123">No formulário **Configurações de ordem padrão**, veja o campo **Tipo de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="dece9-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Demanda para cobertura de site, depósito não obrigatório    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="dece9-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="dece9-125">Additional resources</span></span>
--------

[<span data-ttu-id="dece9-126">Planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="dece9-126">Master planning and multisite functionality</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="dece9-127">Planejamento mestre - cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="dece9-127">Master planning - site coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="dece9-128">Planejamento mestre - cobertura de site e depósito, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="dece9-128">Master planning - site and warehouse coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="dece9-129">Planejamento mestre - cobertura de site e depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="dece9-129">Master planning - site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="dece9-130">Planejamento mestre – como a versão da BOM é determinada</span><span class="sxs-lookup"><span data-stu-id="dece9-130">Master planning - how the BOM version is determined</span></span>](master-plan-bom-version-determined.md)



