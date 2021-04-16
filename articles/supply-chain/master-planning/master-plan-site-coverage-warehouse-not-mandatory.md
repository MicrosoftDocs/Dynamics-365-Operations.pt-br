---
title: Planejamento mestre para cobertura de site, depósito não obrigatório
description: Este tópico descreve como um item com o conjunto de dimensões do local da cobertura é planejado.
author: roxanadiaconu
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40ea467b9dcac20e163f8b6e6f91b238d40278f7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833512"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a><span data-ttu-id="0cb6d-103">Planejamento mestre para cobertura de site, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="0cb6d-103">Master planning for site coverage, warehouse not mandatory</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0cb6d-104">Este tópico descreve como um item com o conjunto de dimensões do local da cobertura é planejado.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-104">This topic describes how an item that has the site dimension set for coverage is planned.</span></span>

<span data-ttu-id="0cb6d-105">Este cenário de planejamento mestre envolve estas condições:</span><span class="sxs-lookup"><span data-stu-id="0cb6d-105">This master planning scenario involves the following conditions:</span></span>

-   <span data-ttu-id="0cb6d-106">A dimensão de estoque é definida como obrigatória e deve ser inserida na transação de demanda.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-106">The site dimension is set to mandatory and must be entered on the demand transaction.</span></span>
-   <span data-ttu-id="0cb6d-107">A dimensão do depósito não está definida como obrigatória.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-107">The warehouse dimension is not set to mandatory.</span></span> <span data-ttu-id="0cb6d-108">O depósito pode ser conhecido, mas não é usado no cálculo do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-108">The warehouse may be known, but it is not used in the master planning calculation.</span></span>
-   <span data-ttu-id="0cb6d-109">A dimensão do site está definida como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-109">The site dimension is set for coverage planning.</span></span>
-   <span data-ttu-id="0cb6d-110">A dimensão do depósito não está definida como planejamento de cobertura.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-110">The warehouse dimension is not set for coverage planning.</span></span> <span data-ttu-id="0cb6d-111">Assim, a oferta e a demanda são agregadas por site (e talvez outras dimensões de cobertura planejada também).</span><span class="sxs-lookup"><span data-stu-id="0cb6d-111">Therefore, supply and demand are aggregated by site and, perhaps, other coverage-planned dimensions also.</span></span>

<span data-ttu-id="0cb6d-112">O gráfico a seguir ilustra como o planejamento mestre ocorre.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-112">The following graphic illustrates how master planning proceeds.</span></span> <span data-ttu-id="0cb6d-113">Os parâmetros referidos no gráfico, e as respectivas localizações, são estes:</span><span class="sxs-lookup"><span data-stu-id="0cb6d-113">The parameters that are referred to in the graphic, and their locations, are as follows:</span></span>
-   <span data-ttu-id="0cb6d-114">A cobertura de item é definida para o item.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-114">Item coverage is defined for the item.</span></span> <span data-ttu-id="0cb6d-115">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-115">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="0cb6d-116">Selecione o item e então clique em **Planejar &gt; Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-116">Select the item, and then click **Plan &gt; Item coverage**.</span></span>
-   <span data-ttu-id="0cb6d-117">As relações de reabastecimento são definidas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-117">Refill relations are defined for the warehouse.</span></span> <span data-ttu-id="0cb6d-118">Clique em **Gerenciamento de estoque &gt; Configuração &gt; Divisão de estoque &gt; Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-118">Click **Inventory management &gt; Setup &gt; Inventory breakdown &gt; Warehouses**.</span></span> <span data-ttu-id="0cb6d-119">Na guia **Planejamento mestre**, consulte o grupo de campos **Depósito principal** .</span><span class="sxs-lookup"><span data-stu-id="0cb6d-119">On the **Master planning** tab, see the **Main warehouse** field group.</span></span>
-   <span data-ttu-id="0cb6d-120">O tipo de ordem padrão é definido como Produção, Ordem de compra ou Kanban.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-120">The default order type is set to Production, Purchase order or Kanban.</span></span> <span data-ttu-id="0cb6d-121">Clique em **Gerenciamento de informações do produto &gt; Produtos&gt; Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-121">Click **Product information management &gt; Products&gt; Released products**.</span></span> <span data-ttu-id="0cb6d-122">Selecione o item e clique em **Planejar &gt; Configurações padrão da ordem**.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-122">Select the item, and then click **Plan &gt; Default order settings**.</span></span> <span data-ttu-id="0cb6d-123">No formulário **Configurações de ordem padrão**, veja o campo **Tipo de ordem padrão**.</span><span class="sxs-lookup"><span data-stu-id="0cb6d-123">In the **Default order settings** form, see the **Default order type** field.</span></span>

![Demanda para cobertura de site, depósito não obrigatório    ](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a><span data-ttu-id="0cb6d-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0cb6d-125">Additional resources</span></span>
--------

[<span data-ttu-id="0cb6d-126">Visão geral de planejamento mestre e funcionalidade multissite</span><span class="sxs-lookup"><span data-stu-id="0cb6d-126">Master planning and multisite functionality overview</span></span>](master-plan-multisite-functionality.md)

[<span data-ttu-id="0cb6d-127">Planejamento mestre para de site e cobertura de depósito, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="0cb6d-127">Master planning for site and warehouse coverage, warehouse mandatory</span></span>](master-plan-site-coverage-warehouse-mandatory.md)

[<span data-ttu-id="0cb6d-128">Planejamento mestre para cobertura de site, depósito obrigatório</span><span class="sxs-lookup"><span data-stu-id="0cb6d-128">Master planning for site coverage, mandatory warehouse</span></span>](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[<span data-ttu-id="0cb6d-129">Planejamento mestre para cobertura de site, depósito não obrigatório</span><span class="sxs-lookup"><span data-stu-id="0cb6d-129">Master planning for site coverage, warehouse not mandatory</span></span>](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[<span data-ttu-id="0cb6d-130">Determinar a versão da BOM</span><span class="sxs-lookup"><span data-stu-id="0cb6d-130">Determine the BOM version</span></span>](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]