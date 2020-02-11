---
title: Módulo de rodapé
description: Este tópico abrange os módulos de rodapés e como criá-los no Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c253cd9620180b09f2f5cae232e46d236deabdd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697304"
---
# <a name="footer-module"></a><span data-ttu-id="2581d-103">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="2581d-103">Footer module</span></span>  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="2581d-104">Este tópico abrange os módulos de rodapé e descreve como criá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2581d-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2581d-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="2581d-105">Overview</span></span>

<span data-ttu-id="2581d-106">O módulo de rodapé é um contêiner especial usado para armazenar os módulos que aparecem no rodapé da página.</span><span class="sxs-lookup"><span data-stu-id="2581d-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="2581d-107">Por exemplo, pode incluir os links para várias páginas no site, como **Fale conosco** e **Armazenar políticas**.</span><span class="sxs-lookup"><span data-stu-id="2581d-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

## <a name="footer-module-properties"></a><span data-ttu-id="2581d-108">Propriedades de módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="2581d-108">Footer module properties</span></span> 

<span data-ttu-id="2581d-109">Como a maioria dos contêineres, propriedades do suporte do módulo de rodapé para o título e largura.</span><span class="sxs-lookup"><span data-stu-id="2581d-109">Like most containers, a footer module support properties for the heading and the width.</span></span> <span data-ttu-id="2581d-110">Também oferece suporte a adição de diversos módulos de categoria de rodapé.</span><span class="sxs-lookup"><span data-stu-id="2581d-110">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="2581d-111">Cada módulo de categoria de rodapé que é adicionado é renderizado como uma coluna no módulo de rodapé.</span><span class="sxs-lookup"><span data-stu-id="2581d-111">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="2581d-112">Módulos disponíveis em um módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="2581d-112">Modules available in a footer module</span></span>

<span data-ttu-id="2581d-113">**Itens do rodapé** – Um módulo de itens do rodapé pode conter um título, uma figura e um link.</span><span class="sxs-lookup"><span data-stu-id="2581d-113">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="2581d-114">O cabeçalho pode ser usados independentemente ou em combinação com uma imagem e um link.</span><span class="sxs-lookup"><span data-stu-id="2581d-114">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="2581d-115">Cada link no rodapé pode ser configurado de forma que tenha apenas texto (por exemplo, links de "Fale conosco" e "Privacidade"), de forma que possua um texto e uma imagem (por exemplo, links de mídias sociais.)</span><span class="sxs-lookup"><span data-stu-id="2581d-115">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="2581d-116">**Voltar para a parte superior** – Um módulo para voltar ao módulo superior fornece um link para navegação rápida ao topo da página.</span><span class="sxs-lookup"><span data-stu-id="2581d-116">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="2581d-117">Um destino é necessário.</span><span class="sxs-lookup"><span data-stu-id="2581d-117">A destination is required.</span></span> <span data-ttu-id="2581d-118">O valor de destino padrão é #, que leva o usuário ao topo da página.</span><span class="sxs-lookup"><span data-stu-id="2581d-118">The default destination value is #, which takes the user to the top of the page.</span></span>

## <a name="author-a-footer-module"></a><span data-ttu-id="2581d-119">Criar um módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="2581d-119">Author a footer module</span></span>

1. <span data-ttu-id="2581d-120">No painel de navegação, selecione **Fragmentos** e depois **Novo fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="2581d-120">In the navigation pane, select **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="2581d-121">Na caixa de diálogo **Novo fragmento de página**, selecione o módulo do rodapé, insira um nome para a parte mais importante de página, e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2581d-121">In the **New Page Fragment** dialog box, select the footer module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="2581d-122">Na árvore em destaque à esquerda, selecione o botão de reticências (**…**) no módulo de rodapé, e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="2581d-122">In the outline tree on the left, select the ellipsis button (**...**) for the footer module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="2581d-123">Na caixa de diálogo **Adicionar módulo**, selecione o módulo da categoria do rodapé, e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2581d-123">In the **Add Module** dialog box, select the footer category module, and then select **OK**.</span></span>
1. <span data-ttu-id="2581d-124">Na árvore em destaque, selecione o botão de reticências no módulo de categoria do rodapé, e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="2581d-124">In the outline tree, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="2581d-125">Na caixa de diálogo **Adicionar módulo**, selecione o módulo de item do rodapé, e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2581d-125">In the **Add Module** dialog box, select the footer item module, and then select **OK**.</span></span>
1. <span data-ttu-id="2581d-126">Na árvore em destaque, selecione o módulo de item do rodapé.</span><span class="sxs-lookup"><span data-stu-id="2581d-126">In the outline tree, select the footer item module.</span></span> <span data-ttu-id="2581d-127">Em seguida, no painel de propriedades à direita, configure o cabeçalho, link e vincule texto e imagem como quiser.</span><span class="sxs-lookup"><span data-stu-id="2581d-127">Then, in the properties pane on the right, configure the heading, link and link text, and image as you require.</span></span>
1. <span data-ttu-id="2581d-128">Para adicionar mais itens de rodapé, repita as etapas 5 a 7.</span><span class="sxs-lookup"><span data-stu-id="2581d-128">To add more footer items, repeat steps 5 through 7.</span></span>
1. <span data-ttu-id="2581d-129">Para adicionar um link "voltar ao topo" em seu rodapé, selecione o botão de reticências no módulo de categoria do rodapé, e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="2581d-129">To add a "back to top" link to your footer, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="2581d-130">Na caixa de diálogo **Adicionar módulo**, selecione o módulo voltar ao topo, e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2581d-130">In the **Add Module** dialog box, select the back to top module, and then select **OK**.</span></span>
1. <span data-ttu-id="2581d-131">Na árvore em destaque, selecione o módulo voltar ao topo.</span><span class="sxs-lookup"><span data-stu-id="2581d-131">In the outline tree, select the back to top module.</span></span> <span data-ttu-id="2581d-132">Em seguida, no painel de propriedades à direita, configure o módulo voltar ao topo conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2581d-132">Then, in the properties pane on the right, configure the back to top module as you require.</span></span>
1. <span data-ttu-id="2581d-133">Salve o fragmento de página, insira-o e publique-o.</span><span class="sxs-lookup"><span data-stu-id="2581d-133">Save the page fragment, check it in, and publish it.</span></span>

<span data-ttu-id="2581d-134">Em cada modelo da página criada no site, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="2581d-134">On every page template that has been created for the site, follow these steps.</span></span>

1. <span data-ttu-id="2581d-135">No slot **Principal** da página padrão, no módulo de rodapé, adicione a parte mais importante de rodapé que você criou.</span><span class="sxs-lookup"><span data-stu-id="2581d-135">In the **Main** slot of the default page, in the footer module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="2581d-136">Salve o modelo, insira-o e publique-o.</span><span class="sxs-lookup"><span data-stu-id="2581d-136">Save the template, check it in, and publish it.</span></span>

<span data-ttu-id="2581d-137">Ao adicionar o fragmento de página aos modelos de página, você ajuda a garantir que o rodapé está renderizado em cada página.</span><span class="sxs-lookup"><span data-stu-id="2581d-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2581d-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="2581d-138">Additional resources</span></span>

[<span data-ttu-id="2581d-139">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="2581d-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2581d-140">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="2581d-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="2581d-141">Comprar módulo de caixa</span><span class="sxs-lookup"><span data-stu-id="2581d-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="2581d-142">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="2581d-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="2581d-143">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="2581d-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="2581d-144">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="2581d-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="2581d-145">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="2581d-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="2581d-146">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="2581d-146">Footer module</span></span>](author-footer-module.md)