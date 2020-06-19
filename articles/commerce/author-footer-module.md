---
title: Módulo de rodapé
description: Este tópico abrange os módulos de rodapés e como criá-los no Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 87ffc0204019f2f7122c40dc21bdb5de012929d6
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411186"
---
# <a name="footer-module"></a><span data-ttu-id="ae5a7-103">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="ae5a7-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="ae5a7-104">Este tópico abrange os módulos de rodapé e descreve como criá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ae5a7-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="ae5a7-105">Overview</span></span>

<span data-ttu-id="ae5a7-106">O módulo de rodapé é um contêiner especial usado para armazenar os módulos que aparecem no rodapé da página.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="ae5a7-107">Por exemplo, pode incluir os links para várias páginas no site, como **Fale conosco** e **Armazenar políticas**.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="ae5a7-108">A imagem a seguir mostra um exemplo de um módulo de rodapé em uma página de site.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-108">The following image shows an example of a footer module on a site page.</span></span>

![Exemplo de um módulo de rodapé](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="ae5a7-110">Propriedades de módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="ae5a7-110">Footer module properties</span></span> 

<span data-ttu-id="ae5a7-111">Como a maioria dos contêineres, o módulo de rodapé oferece suporte a propriedades para o título e a largura.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-111">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="ae5a7-112">Também oferece suporte a adição de diversos módulos de categoria de rodapé.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-112">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="ae5a7-113">Cada módulo de categoria de rodapé que é adicionado é renderizado como uma coluna no módulo de rodapé.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-113">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="ae5a7-114">Módulos disponíveis em um módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="ae5a7-114">Modules available in a footer module</span></span>

<span data-ttu-id="ae5a7-115">**Itens do rodapé** – Um módulo de itens do rodapé pode conter um título, uma figura e um link.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-115">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="ae5a7-116">O cabeçalho pode ser usados independentemente ou em combinação com uma imagem e um link.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-116">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="ae5a7-117">Cada link no rodapé pode ser configurado de forma que tenha apenas texto (por exemplo, links de "Fale conosco" e "Privacidade"), de forma que possua um texto e uma imagem (por exemplo, links de mídias sociais.)</span><span class="sxs-lookup"><span data-stu-id="ae5a7-117">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="ae5a7-118">**Voltar para a parte superior** – Um módulo para voltar ao módulo superior fornece um link para navegação rápida ao topo da página.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-118">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="ae5a7-119">Um destino é necessário.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-119">A destination is required.</span></span> <span data-ttu-id="ae5a7-120">O valor de destino padrão é \#, que leva o usuário ao topo da página.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-120">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="ae5a7-121">Criar um módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="ae5a7-121">Create a footer module</span></span>

1. <span data-ttu-id="ae5a7-122">Vá para **Fragmentos de Página** e selecione **Novo** para criar um novo fragmento.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-122">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="ae5a7-123">Na caixa de diálogo **Novo Fragmento de Página**, selecione o módulo **Contêiner**, insira um nome para o fragmento de página e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-123">In the **New Page Fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="ae5a7-124">No slot **Contêiner padrão**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-124">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ae5a7-125">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Categoria do rodapé** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-125">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="ae5a7-126">No slot **Categoria de rodapé**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-126">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ae5a7-127">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Item do rodapé** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-127">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="ae5a7-128">Selecione o slot **Item de rodapé** e, depois, no painel de propriedades à direita, configure cabeçalho, link, texto do link e imagem conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-128">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="ae5a7-129">Para adicionar mais itens de rodapé, repita as etapas 5 a 7 para cada.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-129">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="ae5a7-130">Para adicionar um link "voltar ao topo" ao rodapé, selecione as reticências (**...**) no slot **Categoria do rodapé** e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-130">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="ae5a7-131">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Voltar ao topo** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-131">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="ae5a7-132">Selecione o slot **Voltar ao tipo** e, depois, no painel de propriedades à direita, configure texto e outras propriedades do módulo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-132">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="ae5a7-133">Selecione **Concluir edição** para fazer check-in do fragmento e, depois, selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-133">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="ae5a7-134">Para ajudar a garantir que um cabeçalho aparece em cada página, siga estas etapas em cada modelo da página que é desenvolvido para o site.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-134">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="ae5a7-135">No slot **Rodapé** do módulo **Página padrão**, adicione o fragmento de rodapé que você criou.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-135">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="ae5a7-136">Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-136">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="ae5a7-137">Ao adicionar o fragmento de página aos modelos de página, você ajuda a garantir que o rodapé está renderizado em cada página.</span><span class="sxs-lookup"><span data-stu-id="ae5a7-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ae5a7-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ae5a7-138">Additional resources</span></span>

[<span data-ttu-id="ae5a7-139">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="ae5a7-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ae5a7-140">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="ae5a7-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ae5a7-141">Comprar módulo de caixa</span><span class="sxs-lookup"><span data-stu-id="ae5a7-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ae5a7-142">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="ae5a7-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ae5a7-143">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="ae5a7-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ae5a7-144">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="ae5a7-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ae5a7-145">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="ae5a7-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ae5a7-146">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="ae5a7-146">Footer module</span></span>](author-footer-module.md)
