---
title: Módulos de classificações e revisões
description: Este tópico aborda classificações e revisa os módulos usados nas páginas de detalhes do produto no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: dee9a6a7e2a5278f069958ce00689b1beb9b1bd7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792138"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="df21b-103">Módulos de classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="df21b-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="df21b-104">Este tópico aborda classificações e revisa os módulos usados nas páginas de detalhes do produto (PDPs) no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="df21b-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="df21b-105">As avaliações e opiniões sobre sites comerciais online ajudam os clientes a aprenderem sobre produtos antes de realizarem uma decisão de compra, e também são um mecanismo para coleta de opinião do cliente sobre produtos.</span><span class="sxs-lookup"><span data-stu-id="df21b-105">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="df21b-106">As classificações são mostrados nas páginas de listagem de produto, nas páginas de listas de categoria, nas páginas de resultados da pesquisa, e outras páginas do site.</span><span class="sxs-lookup"><span data-stu-id="df21b-106">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="df21b-107">Os histogramas de avaliação e os comentários sobre os produtos são exibidos nas PDPs.</span><span class="sxs-lookup"><span data-stu-id="df21b-107">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="df21b-108">Um botão **Escrever uma avaliação** permite que os clientes enviem avaliações e comentários sobre um produto.</span><span class="sxs-lookup"><span data-stu-id="df21b-108">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="df21b-109">Esses recursos de PDP são controlados por classificação e módulos de revisão.</span><span class="sxs-lookup"><span data-stu-id="df21b-109">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="df21b-110">Módulos de classificações e opiniões em PDPs</span><span class="sxs-lookup"><span data-stu-id="df21b-110">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="df21b-111">Três módulos mostram as avaliações e opiniões resumidas em PDPs:</span><span class="sxs-lookup"><span data-stu-id="df21b-111">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="df21b-112">Módulo para escrever uma avaliação</span><span class="sxs-lookup"><span data-stu-id="df21b-112">Write review module</span></span>
- <span data-ttu-id="df21b-113">Módulo da lista de revisões de produto</span><span class="sxs-lookup"><span data-stu-id="df21b-113">Product reviews list module</span></span>
- <span data-ttu-id="df21b-114">Módulo de histograma de avaliação</span><span class="sxs-lookup"><span data-stu-id="df21b-114">Ratings histogram module</span></span>
 
<span data-ttu-id="df21b-115">A ilustração a seguir mostra como os módulos de avaliações e opiniões se parecem em um PDP.</span><span class="sxs-lookup"><span data-stu-id="df21b-115">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Módulos de classificações e opiniões em um PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="df21b-117">Para obter informações sobre como otimizar modelos e layouts de PDP para que você possa compartilhar configurações para módulos de avaliação e opiniões entre vários PDPs no site comercial online, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="df21b-117">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="df21b-118">A ilustração a seguir mostra como a caixa de diálogo **Adicionar o módulo** apresenta módulos de avaliações e opiniões no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="df21b-118">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="df21b-119">![Adicionar a caixa de diálogo do módulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="df21b-119">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="df21b-120">Módulo para escrever uma avaliação</span><span class="sxs-lookup"><span data-stu-id="df21b-120">Write review module</span></span>

<span data-ttu-id="df21b-121">O módulo de escrita de avaliação contém um botão **Escrever uma avaliação** que permite que os usuários se conectem, atribuam uma avaliação e escrevam uma revisão de um produto.</span><span class="sxs-lookup"><span data-stu-id="df21b-121">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="df21b-122">Este módulo também permite que os usuários editem uma classificação ou opinião enviada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="df21b-122">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="df21b-123">Esse módulos geralmente aparecerá acima do histograma de avaliações e módulos de lista de opiniões sobre produto em um PDP.</span><span class="sxs-lookup"><span data-stu-id="df21b-123">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="df21b-124">A ilustração a seguir mostra a caixa de diálogo **Escrever uma avaliação** exibida quando um cliente seleciona **Escrever uma avaliação**.</span><span class="sxs-lookup"><span data-stu-id="df21b-124">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="df21b-125">O cliente pode usar esta caixa de diálogo para enviar uma avaliação e uma revisão.</span><span class="sxs-lookup"><span data-stu-id="df21b-125">The customer can use this dialog box to submit a rating and a review.</span></span>
<span data-ttu-id="df21b-126">![Caixa de diálogo escrever uma avaliação](media/rnr-eCommerce-write-review-module.png) A tabela a seguir mostra a propriedade do módulo para escrever uma revisão que precisa ser configurada na ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="df21b-126">![Write a review dialog box](media/rnr-eCommerce-write-review-module.png) The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>
| <span data-ttu-id="df21b-127">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="df21b-127">Property name</span></span> | <span data-ttu-id="df21b-128">Alíquota</span><span class="sxs-lookup"><span data-stu-id="df21b-128">Value</span></span>        | <span data-ttu-id="df21b-129">Descrição de propriedade</span><span class="sxs-lookup"><span data-stu-id="df21b-129">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="df21b-130">Nome</span><span class="sxs-lookup"><span data-stu-id="df21b-130">Name</span></span>          | <span data-ttu-id="df21b-131">Escrever avaliação</span><span class="sxs-lookup"><span data-stu-id="df21b-131">Write review</span></span> | <span data-ttu-id="df21b-132">O nome do módulo escrever uma revisão.</span><span class="sxs-lookup"><span data-stu-id="df21b-132">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="df21b-133">Módulo de histograma de avaliação</span><span class="sxs-lookup"><span data-stu-id="df21b-133">Ratings histogram module</span></span>

<span data-ttu-id="df21b-134">O módulo de histograma de avaliações exibe um histograma de avaliações.</span><span class="sxs-lookup"><span data-stu-id="df21b-134">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="df21b-135">Este módulo aparece normalmente entre o módulo para escrever avaliação e o módulo de lista de avaliações de produto em um PDP.</span><span class="sxs-lookup"><span data-stu-id="df21b-135">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="df21b-136">O módulo de histograma de avaliação não exige configuração.</span><span class="sxs-lookup"><span data-stu-id="df21b-136">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="df21b-137">Você só tem que adicionar o módulo no modelo de PDP.</span><span class="sxs-lookup"><span data-stu-id="df21b-137">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="df21b-138">As ilustrações a seguir mostram como um modelo de PDP se parece no Dynamics 365 Commerce quando os módulos de avaliação e revisão são configurados para exibição em PDPs.</span><span class="sxs-lookup"><span data-stu-id="df21b-138">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="df21b-139">![Modelo de PDP quando as avaliações e revisões estão configuradas para a exibição em PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="df21b-139">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="df21b-140">Módulo da lista de revisões de produto</span><span class="sxs-lookup"><span data-stu-id="df21b-140">Product reviews list module</span></span>

<span data-ttu-id="df21b-141">O módulo da lista de avaliações de produto mostra uma lista de revisões de produto com o tipo, o filtro, e as opções de paginação.</span><span class="sxs-lookup"><span data-stu-id="df21b-141">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="df21b-142">Este módulo geralmente aparece após o módulo de histograma de avaliação em um PDP.</span><span class="sxs-lookup"><span data-stu-id="df21b-142">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="df21b-143">A tabela a seguir mostra as propriedades do módulo de lista de avaliações de produto que precisam ser configurados na ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="df21b-143">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="df21b-144">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="df21b-144">Property name</span></span>              | <span data-ttu-id="df21b-145">Alíquota</span><span class="sxs-lookup"><span data-stu-id="df21b-145">Value</span></span> | <span data-ttu-id="df21b-146">Descrição de propriedade</span><span class="sxs-lookup"><span data-stu-id="df21b-146">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="df21b-147">Revisões mostradas em cada página</span><span class="sxs-lookup"><span data-stu-id="df21b-147">Reviews shown on each page</span></span> | <span data-ttu-id="df21b-148">10</span><span class="sxs-lookup"><span data-stu-id="df21b-148">10</span></span>    | <span data-ttu-id="df21b-149">O número de revisões que devem ser mostradas em vez em um PDP.</span><span class="sxs-lookup"><span data-stu-id="df21b-149">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="df21b-150">Os botões **Avançar** e **Voltar** estão incluídos, para que os usuários possam mover entre as páginas de avaliações.</span><span class="sxs-lookup"><span data-stu-id="df21b-150">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="df21b-151">Histograma de avaliação – Exibição de resumo</span><span class="sxs-lookup"><span data-stu-id="df21b-151">Ratings histogram – Summary view</span></span>

<span data-ttu-id="df21b-152">O módulo de lista de avaliações de produto inclui um slot onde você pode adicionar um módulo de histograma de avaliações.</span><span class="sxs-lookup"><span data-stu-id="df21b-152">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="df21b-153">A ilustração a seguir mostra como é possível adicionar um módulo de histograma de avaliação no módulo da lista de revisões de produtos no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="df21b-153">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Adicionando um módulo de histograma de avaliação em um módulo de lista de avaliações de produto](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="df21b-155">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="df21b-155">Additional resources</span></span>

[<span data-ttu-id="df21b-156">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="df21b-156">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="df21b-157">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="df21b-157">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="df21b-158">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="df21b-158">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="df21b-159">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="df21b-159">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="df21b-160">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="df21b-160">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="df21b-161">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="df21b-161">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="df21b-162">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="df21b-162">Footer module</span></span>](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]