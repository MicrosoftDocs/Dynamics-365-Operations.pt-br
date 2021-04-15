---
title: Configurar classificações e opiniões
description: Este tópico descreve como configurar seu site comercial online para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5161755b9e15e93fbb5eeb6404ea0820f7068ea7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796066"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="06080-103">Configurar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="06080-103">Configure ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="06080-104">Este tópico descreve como configurar seu site comercial online para mostrar avaliações de cliente e opiniões no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="06080-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="06080-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="06080-105">Overview</span></span>

<span data-ttu-id="06080-106">As avaliações e opiniões sobre sites comerciais online ajudam os clientes a aprenderem sobre produtos antes de realizarem uma decisão de compra, mostrando a eles o que os clientes pensam sobre esses produtos.</span><span class="sxs-lookup"><span data-stu-id="06080-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision by showing them what other customers think about those products.</span></span> <span data-ttu-id="06080-107">Para sites de comércio online, avaliações e opiniões também são um mecanismo para coletar feedback de clientes sobre produtos.</span><span class="sxs-lookup"><span data-stu-id="06080-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="06080-108">Configurar um site para exibir classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="06080-108">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="06080-109">Os valores de configuração de classificações e revisões, como ID de locatário, comprimento do texto de avaliação, e comprimento de título de avaliação são configurados no nível do site.</span><span class="sxs-lookup"><span data-stu-id="06080-109">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="06080-110">Para configurar um site para exibir avaliações e opiniões, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="06080-110">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="06080-111">Vá para **Início \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="06080-111">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="06080-112">Selecione o nome do site.</span><span class="sxs-lookup"><span data-stu-id="06080-112">Select the name of your site.</span></span> 
1. <span data-ttu-id="06080-113">Acesse **Configurações do site \> Extensões**.</span><span class="sxs-lookup"><span data-stu-id="06080-113">Go to **Site settings \> Extensions**.</span></span> 
1. <span data-ttu-id="06080-114">No campo **Revisar o tamanho máximo do texto**, insira o número máximo de caracteres que o texto de avaliação pode ter (por exemplo, **1000**).</span><span class="sxs-lookup"><span data-stu-id="06080-114">In the **Review text max length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="06080-115">No campo **Revisar o tamanho máximo do título**, insira o número máximo de caracteres que os títulos de avaliação pode ter (por exemplo, **55**).</span><span class="sxs-lookup"><span data-stu-id="06080-115">In the **Review title max length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="06080-116">Selecione **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="06080-116">Select **Save and Publish**.</span></span> 

<span data-ttu-id="06080-117">A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="06080-117">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configurando um site para exibir classificações e opiniões](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="06080-119">Vincule uma avaliação de produto à seção Avaliações de um PDP</span><span class="sxs-lookup"><span data-stu-id="06080-119">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="06080-120">Uma classificação de produtos é exibida abaixo do título do produto na parte superior de PDP.</span><span class="sxs-lookup"><span data-stu-id="06080-120">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="06080-121">A classificação de produto pode ser configurada de forma que está vinculada à seção **Revisões** do mesmo PDP.</span><span class="sxs-lookup"><span data-stu-id="06080-121">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="06080-122">Para vincular um produto que avalie a seção **Avaliações** do PDP, rastreie essas etapas.</span><span class="sxs-lookup"><span data-stu-id="06080-122">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="06080-123">Abra o modelo do PDP.</span><span class="sxs-lookup"><span data-stu-id="06080-123">Open the PDP template.</span></span> 
1. <span data-ttu-id="06080-124">Vá para **Comprar configurações de módulo de contêiner de caixa**.</span><span class="sxs-lookup"><span data-stu-id="06080-124">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="06080-125">Em **Comprar uma caixa**, selecione **Classificações de produtos**, e selecione a caixa de seleção **Vincular o clique ao módulo inteiro de revisões de desempenho**.</span><span class="sxs-lookup"><span data-stu-id="06080-125">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="06080-126">A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="06080-126">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Vinculando uma avaliação de produto à seção Avaliações de um PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="06080-128">Configurar o link para a página de privacidade e política</span><span class="sxs-lookup"><span data-stu-id="06080-128">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="06080-129">Para configurar o link para a página de privacidade e política, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="06080-129">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="06080-130">Vá para **Início \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="06080-130">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="06080-131">Selecione o nome do site.</span><span class="sxs-lookup"><span data-stu-id="06080-131">Select the name of your site.</span></span> 
1. <span data-ttu-id="06080-132">Acesse **Configurações do site \> Extensões**.</span><span class="sxs-lookup"><span data-stu-id="06080-132">Go to **Site settings \> Extensions**.</span></span>
1. <span data-ttu-id="06080-133">Na guia **Roteiros**, em **Privacidade e política de RNR**, selecione **Adicionar um link**.</span><span class="sxs-lookup"><span data-stu-id="06080-133">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="06080-134">Se um link já tiver sido inserido e você desejar substituí-lo, selecione o link.</span><span class="sxs-lookup"><span data-stu-id="06080-134">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="06080-135">Na caixa de diálogo **Adicionar um link**, selecione o link para a página de privacidade e política, e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="06080-135">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="06080-136">Selecione **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="06080-136">Select **Save and Publish**.</span></span> 

<span data-ttu-id="06080-137">A ilustração a seguir mostra como essa configuração se parece no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="06080-137">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configurando o link para a página de privacidade e política](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a><span data-ttu-id="06080-139">Configurar os módulos de classificações e revisões nas páginas de detalhes do produto</span><span class="sxs-lookup"><span data-stu-id="06080-139">Configure ratings and reviews modules on product details pages</span></span>

<span data-ttu-id="06080-140">Para obter informações sobre como configurar módulos de classificações e revisões nas páginas de detalhes do produto, consulte [Módulos de classificações e opiniões](ratings-reviews-modules.md).</span><span class="sxs-lookup"><span data-stu-id="06080-140">For information on configuring ratings and reviews modules on product details pages, see [Ratings and reviews modules](ratings-reviews-modules.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="06080-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="06080-141">Additional resources</span></span>

[<span data-ttu-id="06080-142">Visão geral de classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="06080-142">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="06080-143">Aceitar usar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="06080-143">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="06080-144">Gerenciar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="06080-144">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="06080-145">Configurar os módulos de classificações e revisões nas páginas de detalhes do produto</span><span class="sxs-lookup"><span data-stu-id="06080-145">Configure ratings and reviews modules on product details pages</span></span>](ratings-reviews-modules.md)

[<span data-ttu-id="06080-146">Sincronizar classificações de produto no Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="06080-146">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]