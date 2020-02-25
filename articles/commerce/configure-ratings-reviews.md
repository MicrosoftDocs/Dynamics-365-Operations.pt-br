---
title: Configurar classificações e opiniões
description: Este tópico descreve como configurar seu site comercial online para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0aac4b680590a95f465d33950f2933c4a4582e54
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002188"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="875ff-103">Configurar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="875ff-103">Configure ratings and reviews</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="875ff-104">Este tópico descreve como configurar seu site comercial online para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="875ff-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="875ff-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="875ff-105">Overview</span></span>

<span data-ttu-id="875ff-106">As avaliações e opiniões sobre sites comerciais online ajudam os clientes a aprenderem sobre produtos antes de realizarem uma decisão de compra, mostrando a eles o que os clientes pensam sobre esses produtos.</span><span class="sxs-lookup"><span data-stu-id="875ff-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, by showing them what other customers think about those products.</span></span> <span data-ttu-id="875ff-107">Para sites de comércio online, avaliações e opiniões também são um mecanismo para coletar feedback de clientes sobre produtos.</span><span class="sxs-lookup"><span data-stu-id="875ff-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="875ff-108">As classificações são mostrados nas páginas de listagem de produto, nas páginas de listas de categoria, nas páginas de resultados da pesquisa, e outras páginas do site.</span><span class="sxs-lookup"><span data-stu-id="875ff-108">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> <span data-ttu-id="875ff-109">Os histogramas de avaliação e os comentários sobre os produtos são exibidos nas páginas de detalhes do produto (PDPs).</span><span class="sxs-lookup"><span data-stu-id="875ff-109">Ratings histograms and product reviews are shown on product details pages (PDPs).</span></span> <span data-ttu-id="875ff-110">Um botão **Escrever uma avaliação** permite que os clientes enviem avaliações e comentários sobre um produto.</span><span class="sxs-lookup"><span data-stu-id="875ff-110">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="875ff-111">Módulos de classificações e opiniões em PDPs</span><span class="sxs-lookup"><span data-stu-id="875ff-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="875ff-112">Três módulos mostram as avaliações e opiniões resumidas em PDPs:</span><span class="sxs-lookup"><span data-stu-id="875ff-112">Three modules show the ratings and reviews summary on PDPs:</span></span>

- <span data-ttu-id="875ff-113">Módulo para escrever uma avaliação</span><span class="sxs-lookup"><span data-stu-id="875ff-113">Write review module</span></span>
- <span data-ttu-id="875ff-114">Módulo da lista de revisões de produto</span><span class="sxs-lookup"><span data-stu-id="875ff-114">Product reviews list module</span></span>
- <span data-ttu-id="875ff-115">Módulo de histograma de avaliação</span><span class="sxs-lookup"><span data-stu-id="875ff-115">Ratings histogram module</span></span>
 
<span data-ttu-id="875ff-116">A ilustração a seguir mostra como os módulos de avaliações e opiniões se parecem em um PDP.</span><span class="sxs-lookup"><span data-stu-id="875ff-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Módulos de classificações e opiniões em um PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="875ff-118">Para obter informações sobre como otimizar modelos e layouts de PDP para que você possa compartilhar configurações para módulos de avaliação e opiniões entre vários PDPs no site comercial online, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="875ff-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="875ff-119">A ilustração a seguir mostra como a caixa de diálogo **Adicionar o módulo** apresenta módulos de avaliações e opiniões no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="875ff-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>

![Adicionar a caixa de diálogo do módulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a><span data-ttu-id="875ff-121">Módulo para escrever uma avaliação</span><span class="sxs-lookup"><span data-stu-id="875ff-121">Write review module</span></span>

<span data-ttu-id="875ff-122">O módulo de escrita de avaliação contém um botão **Escrever uma avaliação** que permite que os usuários se conectem, atribuam uma avaliação e escrevam uma revisão de um produto.</span><span class="sxs-lookup"><span data-stu-id="875ff-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="875ff-123">Este módulo também permite que os usuários editem uma classificação ou opinião enviada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="875ff-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="875ff-124">Esse módulos geralmente aparecerá acima do histograma de avaliações e módulos de lista de opiniões sobre produto em um PDP.</span><span class="sxs-lookup"><span data-stu-id="875ff-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>

<span data-ttu-id="875ff-125">A ilustração a seguir mostra a caixa de diálogo **Escrever uma avaliação** exibida quando um cliente seleciona **Escrever uma avaliação**.</span><span class="sxs-lookup"><span data-stu-id="875ff-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="875ff-126">O cliente pode usar esta caixa de diálogo para enviar uma avaliação e uma revisão.</span><span class="sxs-lookup"><span data-stu-id="875ff-126">The customer can use this dialog box to submit a rating and a review.</span></span>

![Caixa de diálogo escrever uma avaliação](media/rnr-eCommerce-write-review-module.png)

<span data-ttu-id="875ff-128">A tabela a seguir mostra a propriedade do módulo para escrever uma revisão que precisa ser configurado na ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="875ff-128">The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>

| <span data-ttu-id="875ff-129">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="875ff-129">Property name</span></span> | <span data-ttu-id="875ff-130">Alíquota</span><span class="sxs-lookup"><span data-stu-id="875ff-130">Value</span></span>        | <span data-ttu-id="875ff-131">Descrição de propriedade</span><span class="sxs-lookup"><span data-stu-id="875ff-131">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="875ff-132">Nome</span><span class="sxs-lookup"><span data-stu-id="875ff-132">Name</span></span>          | <span data-ttu-id="875ff-133">Escrever avaliação</span><span class="sxs-lookup"><span data-stu-id="875ff-133">Write review</span></span> | <span data-ttu-id="875ff-134">O nome do módulo escrever uma revisão.</span><span class="sxs-lookup"><span data-stu-id="875ff-134">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="875ff-135">Módulo de histograma de avaliação</span><span class="sxs-lookup"><span data-stu-id="875ff-135">Ratings histogram module</span></span>

<span data-ttu-id="875ff-136">O módulo de histograma de avaliações exibe um histograma de avaliações.</span><span class="sxs-lookup"><span data-stu-id="875ff-136">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="875ff-137">Este módulo aparece normalmente entre o módulo para escrever avaliação e o módulo de lista de avaliações de produto em um PDP.</span><span class="sxs-lookup"><span data-stu-id="875ff-137">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>

<span data-ttu-id="875ff-138">O módulo de histograma de avaliação não exige configuração.</span><span class="sxs-lookup"><span data-stu-id="875ff-138">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="875ff-139">Você só tem que adicionar o módulo no modelo de PDP.</span><span class="sxs-lookup"><span data-stu-id="875ff-139">You just have to add the module in the PDP template.</span></span> 

<span data-ttu-id="875ff-140">As ilustrações a seguir mostram como um modelo de PDP se parece no Dynamics 365 Commerce quando os módulos de avaliação e revisão são configurados para exibição em PDPs.</span><span class="sxs-lookup"><span data-stu-id="875ff-140">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>

![Modelo de PDP quando as avaliações e revisões estão configuradas para a exibição em PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a><span data-ttu-id="875ff-142">Módulo da lista de revisões de produto</span><span class="sxs-lookup"><span data-stu-id="875ff-142">Product reviews list module</span></span>

<span data-ttu-id="875ff-143">O módulo da lista de avaliações de produto mostra uma lista de revisões de produto com o tipo, o filtro, e as opções de paginação.</span><span class="sxs-lookup"><span data-stu-id="875ff-143">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="875ff-144">Este módulo geralmente aparece após o módulo de histograma de avaliação em um PDP.</span><span class="sxs-lookup"><span data-stu-id="875ff-144">This module typically appears after the ratings histogram module on a PDP.</span></span>

<span data-ttu-id="875ff-145">A tabela a seguir mostra as propriedades do módulo de lista de avaliações de produto que precisam ser configurados na ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="875ff-145">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="875ff-146">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="875ff-146">Property name</span></span>              | <span data-ttu-id="875ff-147">Alíquota</span><span class="sxs-lookup"><span data-stu-id="875ff-147">Value</span></span> | <span data-ttu-id="875ff-148">Descrição de propriedade</span><span class="sxs-lookup"><span data-stu-id="875ff-148">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="875ff-149">Revisões mostradas em cada página</span><span class="sxs-lookup"><span data-stu-id="875ff-149">Reviews shown on each page</span></span> | <span data-ttu-id="875ff-150">10</span><span class="sxs-lookup"><span data-stu-id="875ff-150">10</span></span>    | <span data-ttu-id="875ff-151">O número de revisões que devem ser mostradas em vez em um PDP.</span><span class="sxs-lookup"><span data-stu-id="875ff-151">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="875ff-152">Os botões **Avançar** e **Voltar** estão incluídos, para que os usuários possam mover entre as páginas de avaliações.</span><span class="sxs-lookup"><span data-stu-id="875ff-152">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="875ff-153">Histograma de avaliação – Exibição de resumo</span><span class="sxs-lookup"><span data-stu-id="875ff-153">Ratings histogram – Summary view</span></span>

<span data-ttu-id="875ff-154">O módulo de lista de avaliações de produto inclui um slot onde você pode adicionar um módulo de histograma de avaliações.</span><span class="sxs-lookup"><span data-stu-id="875ff-154">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="875ff-155">A ilustração a seguir mostra como é possível adicionar um módulo de histograma de avaliação no módulo da lista de revisões de produtos no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="875ff-155">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Adicionando um módulo de histograma de avaliação em um módulo de lista de avaliações de produto](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="875ff-157">Configurar um site para exibir classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="875ff-157">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="875ff-158">Os valores de configuração de classificações e revisões, como ID de locatário, comprimento do texto de avaliação, e comprimento de título de avaliação são configurados no nível do site.</span><span class="sxs-lookup"><span data-stu-id="875ff-158">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="875ff-159">Para configurar um site para exibir avaliações e opiniões, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="875ff-159">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="875ff-160">Vá para **Início \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="875ff-160">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="875ff-161">Selecione o nome do site.</span><span class="sxs-lookup"><span data-stu-id="875ff-161">Select the name of your site.</span></span> 
1. <span data-ttu-id="875ff-162">Vá para **Gerenciamento de sites \> Extensibilidade**.</span><span class="sxs-lookup"><span data-stu-id="875ff-162">Go to **Site management \> Extensibility**.</span></span> 
1. <span data-ttu-id="875ff-163">No campo **Revisar o tamanho máximo do texto**, insira o número máximo de caracteres que o texto de avaliação pode ter (por exemplo, **1000**).</span><span class="sxs-lookup"><span data-stu-id="875ff-163">In the **Review Text Max Length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="875ff-164">No campo **Revisar o tamanho máximo do título**, insira o número máximo de caracteres que os títulos de avaliação pode ter (por exemplo, **55**).</span><span class="sxs-lookup"><span data-stu-id="875ff-164">In the **Review Title Max Length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="875ff-165">Selecione **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="875ff-165">Select **Save and Publish**.</span></span> 

<span data-ttu-id="875ff-166">A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="875ff-166">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configurando um site para exibir classificações e opiniões](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="875ff-168">Vincule uma avaliação de produto à seção Avaliações de um PDP</span><span class="sxs-lookup"><span data-stu-id="875ff-168">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="875ff-169">Uma classificação de produtos é exibida abaixo do título do produto na parte superior de PDP.</span><span class="sxs-lookup"><span data-stu-id="875ff-169">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="875ff-170">A classificação de produto pode ser configurada de forma que está vinculada à seção **Revisões** do mesmo PDP.</span><span class="sxs-lookup"><span data-stu-id="875ff-170">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="875ff-171">Para vincular um produto que avalie a seção **Avaliações** do PDP, rastreie essas etapas.</span><span class="sxs-lookup"><span data-stu-id="875ff-171">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="875ff-172">Abra o modelo do PDP.</span><span class="sxs-lookup"><span data-stu-id="875ff-172">Open the PDP template.</span></span> 
1. <span data-ttu-id="875ff-173">Vá para **Comprar configurações de módulo de contêiner de caixa**.</span><span class="sxs-lookup"><span data-stu-id="875ff-173">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="875ff-174">Em **Comprar uma caixa**, selecione **Classificações de produtos**, e selecione a caixa de seleção **Vincular o clique ao módulo inteiro de revisões de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="875ff-174">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="875ff-175">A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="875ff-175">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Vinculando uma avaliação de produto à seção Avaliações de um PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="875ff-177">Configurar o link para a página de privacidade e política</span><span class="sxs-lookup"><span data-stu-id="875ff-177">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="875ff-178">Para configurar o link para a página de privacidade e política, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="875ff-178">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="875ff-179">Vá para **Início \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="875ff-179">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="875ff-180">Selecione o nome do site.</span><span class="sxs-lookup"><span data-stu-id="875ff-180">Select the name of your site.</span></span> 
1. <span data-ttu-id="875ff-181">Vá para **Gerenciamento de sites \> Extensibilidade**</span><span class="sxs-lookup"><span data-stu-id="875ff-181">Go to **Site management \> Extensibility**</span></span>
1. <span data-ttu-id="875ff-182">Na guia **Roteiros**, em **Privacidade e política de RNR**, selecione **Adicionar um link**.</span><span class="sxs-lookup"><span data-stu-id="875ff-182">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="875ff-183">Se um link já tiver sido inserido e você desejar substituí-lo, selecione o link.</span><span class="sxs-lookup"><span data-stu-id="875ff-183">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="875ff-184">Na caixa de diálogo **Adicionar um link**, selecione o link para a página de privacidade e política, e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="875ff-184">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="875ff-185">Selecione **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="875ff-185">Select **Save and Publish**.</span></span> 

<span data-ttu-id="875ff-186">A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="875ff-186">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configurando o link para a página de privacidade e política](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a><span data-ttu-id="875ff-188">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="875ff-188">Additional resources</span></span>

[<span data-ttu-id="875ff-189">Visão geral de classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="875ff-189">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="875ff-190">Aceitar usar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="875ff-190">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="875ff-191">Gerenciar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="875ff-191">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="875ff-192">Sincronizar classificações de produto no Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="875ff-192">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
