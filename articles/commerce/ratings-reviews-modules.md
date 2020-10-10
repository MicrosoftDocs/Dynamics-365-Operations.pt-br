---
title: Módulos de classificações e revisões
description: Este tópico aborda classificações e revisa os módulos usados nas páginas de detalhes do produto no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: 85fb1272103eed7d6e44635b7c20438471d96b34
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817721"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="534ec-103">Módulos de classificações e revisões</span><span class="sxs-lookup"><span data-stu-id="534ec-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="534ec-104">Este tópico aborda classificações e revisa os módulos usados nas páginas de detalhes do produto (PDPs) no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="534ec-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="534ec-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="534ec-105">Overview</span></span>

<span data-ttu-id="534ec-106">As avaliações e opiniões sobre sites comerciais online ajudam os clientes a aprenderem sobre produtos antes de realizarem uma decisão de compra, e também são um mecanismo para coleta de opinião do cliente sobre produtos.</span><span class="sxs-lookup"><span data-stu-id="534ec-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="534ec-107">As classificações são mostrados nas páginas de listagem de produto, nas páginas de listas de categoria, nas páginas de resultados da pesquisa, e outras páginas do site.</span><span class="sxs-lookup"><span data-stu-id="534ec-107">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="534ec-108">Os histogramas de avaliação e os comentários sobre os produtos são exibidos nas PDPs.</span><span class="sxs-lookup"><span data-stu-id="534ec-108">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="534ec-109">Um botão **Escrever uma avaliação** permite que os clientes enviem avaliações e comentários sobre um produto.</span><span class="sxs-lookup"><span data-stu-id="534ec-109">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="534ec-110">Esses recursos de PDP são controlados por classificação e módulos de revisão.</span><span class="sxs-lookup"><span data-stu-id="534ec-110">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="534ec-111">Módulos de classificações e opiniões em PDPs</span><span class="sxs-lookup"><span data-stu-id="534ec-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="534ec-112">Três módulos mostram as avaliações e opiniões resumidas em PDPs:</span><span class="sxs-lookup"><span data-stu-id="534ec-112">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="534ec-113">Módulo para escrever uma avaliação</span><span class="sxs-lookup"><span data-stu-id="534ec-113">Write review module</span></span>
- <span data-ttu-id="534ec-114">Módulo da lista de revisões de produto</span><span class="sxs-lookup"><span data-stu-id="534ec-114">Product reviews list module</span></span>
- <span data-ttu-id="534ec-115">Módulo de histograma de avaliação</span><span class="sxs-lookup"><span data-stu-id="534ec-115">Ratings histogram module</span></span>
 
<span data-ttu-id="534ec-116">A ilustração a seguir mostra como os módulos de avaliações e opiniões se parecem em um PDP.</span><span class="sxs-lookup"><span data-stu-id="534ec-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Módulos de classificações e opiniões em um PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="534ec-118">Para obter informações sobre como otimizar modelos e layouts de PDP para que você possa compartilhar configurações para módulos de avaliação e opiniões entre vários PDPs no site comercial online, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="534ec-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="534ec-119">A ilustração a seguir mostra como a caixa de diálogo **Adicionar o módulo** apresenta módulos de avaliações e opiniões no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="534ec-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="534ec-120">![Adicionar a caixa de diálogo do módulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="534ec-120">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="534ec-121">Módulo para escrever uma avaliação</span><span class="sxs-lookup"><span data-stu-id="534ec-121">Write review module</span></span>

<span data-ttu-id="534ec-122">O módulo de escrita de avaliação contém um botão **Escrever uma avaliação** que permite que os usuários se conectem, atribuam uma avaliação e escrevam uma revisão de um produto.</span><span class="sxs-lookup"><span data-stu-id="534ec-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="534ec-123">Este módulo também permite que os usuários editem uma classificação ou opinião enviada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="534ec-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="534ec-124">Esse módulos geralmente aparecerá acima do histograma de avaliações e módulos de lista de opiniões sobre produto em um PDP.</span><span class="sxs-lookup"><span data-stu-id="534ec-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="534ec-125">A ilustração a seguir mostra a caixa de diálogo **Escrever uma avaliação** exibida quando um cliente seleciona **Escrever uma avaliação**.</span><span class="sxs-lookup"><span data-stu-id="534ec-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="534ec-126">O cliente pode usar esta caixa de diálogo para enviar uma avaliação e uma revisão.</span><span class="sxs-lookup"><span data-stu-id="534ec-126">The customer can use this dialog box to submit a rating and a review.</span></span>
<span data-ttu-id="534ec-127">![Caixa de diálogo escrever uma avaliação](media/rnr-eCommerce-write-review-module.png) A tabela a seguir mostra a propriedade do módulo para escrever uma revisão que precisa ser configurada na ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="534ec-127">![Write a review dialog box](media/rnr-eCommerce-write-review-module.png) The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>
| <span data-ttu-id="534ec-128">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="534ec-128">Property name</span></span> | <span data-ttu-id="534ec-129">Alíquota</span><span class="sxs-lookup"><span data-stu-id="534ec-129">Value</span></span>        | <span data-ttu-id="534ec-130">Descrição de propriedade</span><span class="sxs-lookup"><span data-stu-id="534ec-130">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="534ec-131">Nome</span><span class="sxs-lookup"><span data-stu-id="534ec-131">Name</span></span>          | <span data-ttu-id="534ec-132">Escrever avaliação</span><span class="sxs-lookup"><span data-stu-id="534ec-132">Write review</span></span> | <span data-ttu-id="534ec-133">O nome do módulo escrever uma revisão.</span><span class="sxs-lookup"><span data-stu-id="534ec-133">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="534ec-134">Módulo de histograma de avaliação</span><span class="sxs-lookup"><span data-stu-id="534ec-134">Ratings histogram module</span></span>

<span data-ttu-id="534ec-135">O módulo de histograma de avaliações exibe um histograma de avaliações.</span><span class="sxs-lookup"><span data-stu-id="534ec-135">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="534ec-136">Este módulo aparece normalmente entre o módulo para escrever avaliação e o módulo de lista de avaliações de produto em um PDP.</span><span class="sxs-lookup"><span data-stu-id="534ec-136">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="534ec-137">O módulo de histograma de avaliação não exige configuração.</span><span class="sxs-lookup"><span data-stu-id="534ec-137">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="534ec-138">Você só tem que adicionar o módulo no modelo de PDP.</span><span class="sxs-lookup"><span data-stu-id="534ec-138">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="534ec-139">As ilustrações a seguir mostram como um modelo de PDP se parece no Dynamics 365 Commerce quando os módulos de avaliação e revisão são configurados para exibição em PDPs.</span><span class="sxs-lookup"><span data-stu-id="534ec-139">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="534ec-140">![Modelo de PDP quando as avaliações e revisões estão configuradas para a exibição em PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="534ec-140">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="534ec-141">Módulo da lista de revisões de produto</span><span class="sxs-lookup"><span data-stu-id="534ec-141">Product reviews list module</span></span>

<span data-ttu-id="534ec-142">O módulo da lista de avaliações de produto mostra uma lista de revisões de produto com o tipo, o filtro, e as opções de paginação.</span><span class="sxs-lookup"><span data-stu-id="534ec-142">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="534ec-143">Este módulo geralmente aparece após o módulo de histograma de avaliação em um PDP.</span><span class="sxs-lookup"><span data-stu-id="534ec-143">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="534ec-144">A tabela a seguir mostra as propriedades do módulo de lista de avaliações de produto que precisam ser configurados na ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="534ec-144">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="534ec-145">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="534ec-145">Property name</span></span>              | <span data-ttu-id="534ec-146">Alíquota</span><span class="sxs-lookup"><span data-stu-id="534ec-146">Value</span></span> | <span data-ttu-id="534ec-147">Descrição de propriedade</span><span class="sxs-lookup"><span data-stu-id="534ec-147">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="534ec-148">Revisões mostradas em cada página</span><span class="sxs-lookup"><span data-stu-id="534ec-148">Reviews shown on each page</span></span> | <span data-ttu-id="534ec-149">10</span><span class="sxs-lookup"><span data-stu-id="534ec-149">10</span></span>    | <span data-ttu-id="534ec-150">O número de revisões que devem ser mostradas em vez em um PDP.</span><span class="sxs-lookup"><span data-stu-id="534ec-150">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="534ec-151">Os botões **Avançar** e **Voltar** estão incluídos, para que os usuários possam mover entre as páginas de avaliações.</span><span class="sxs-lookup"><span data-stu-id="534ec-151">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="534ec-152">Histograma de avaliação – Exibição de resumo</span><span class="sxs-lookup"><span data-stu-id="534ec-152">Ratings histogram – Summary view</span></span>

<span data-ttu-id="534ec-153">O módulo de lista de avaliações de produto inclui um slot onde você pode adicionar um módulo de histograma de avaliações.</span><span class="sxs-lookup"><span data-stu-id="534ec-153">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="534ec-154">A ilustração a seguir mostra como é possível adicionar um módulo de histograma de avaliação no módulo da lista de revisões de produtos no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="534ec-154">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Adicionando um módulo de histograma de avaliação em um módulo de lista de avaliações de produto](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="534ec-156">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="534ec-156">Additional resources</span></span>

[<span data-ttu-id="534ec-157">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="534ec-157">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="534ec-158">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="534ec-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="534ec-159">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="534ec-159">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="534ec-160">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="534ec-160">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="534ec-161">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="534ec-161">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="534ec-162">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="534ec-162">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="534ec-163">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="534ec-163">Footer module</span></span>](author-footer-module.md)
