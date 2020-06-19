---
title: Módulo de cabeçalho
description: Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: a5f7ad7d9c5ff63c3c3a8fe38275eec0d138891d
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411188"
---
# <a name="header-module"></a><span data-ttu-id="c9a5f-103">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="c9a5f-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c9a5f-104">Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c9a5f-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c9a5f-105">Overview</span></span>

<span data-ttu-id="c9a5f-106">No Dynamics 365 Commerce, um cabeçalho de página consiste em vários módulos, como os de cabeçalho, menu de navegação, pesquisa, faixa promocional e consentimento de cookie.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="c9a5f-107">O módulo de cabeçalho inclui um logotipo do site, links para a hierarquia de navegação, links para outras páginas do site, um símbolo de carrinho, um símbolo de lista de desejos, opções de entrada e a barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="c9a5f-108">Um módulo de cabeçalho é otimizado automaticamente para o dispositivo onde o site está sendo exibido (ou seja, um dispositivo móvel ou de desktop).</span><span class="sxs-lookup"><span data-stu-id="c9a5f-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="c9a5f-109">Por exemplo, em um dispositivo móvel, a barra de navegação é recolhida em um botão **Menu** (que é conhecido ocasionalmente como *menu hambúrguer*).</span><span class="sxs-lookup"><span data-stu-id="c9a5f-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="c9a5f-110">A imagem a seguir mostra um exemplo de um módulo de cabeçalho em uma home page.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-110">The following image shows an example of a header module on a home page.</span></span>

![Exemplo de um módulo de cabeçalho](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="c9a5f-112">Propriedades de um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="c9a5f-112">Properties of a header module</span></span>

<span data-ttu-id="c9a5f-113">Um módulo de cabeçalho oferece suporte às propriedades **Imagem de logotipo**, **Link de logotipo** e **Links da minha conta**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="c9a5f-114">As propriedades **Imagem de logotipo** e **Link de logotipo** são usadas para definir um logotipo na página.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="c9a5f-115">Para obter mais informações, consulte [Adicionar um logotipo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="c9a5f-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="c9a5f-116">A propriedade **Links da minha conta** pode ser usada para definir as páginas da conta das quais o proprietário do site quer mostrar links rápidos no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="c9a5f-117">Módulos disponíveis em um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="c9a5f-117">Modules that are available in a header module</span></span>

<span data-ttu-id="c9a5f-118">Os módulos a seguir podem ser usados em um módulo de cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="c9a5f-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="c9a5f-119">**Menu de navegação** – O menu de navegação representa a hierarquia de navegação de canal e outros links estáticos de navegação.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="c9a5f-120">A hierarquia de navegação de canal pode ser configurada no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-120">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="c9a5f-121">O menu de navegação tem uma propriedade **Origem de Navegação** usada para especificar itens do menu de navegação do Retail Server e itens de menu estático como origem.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-121">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="c9a5f-122">Se itens de menu estático forem especificados como origem, poderão ser fornecidos links relativos a outras páginas do site.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-122">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="c9a5f-123">Os itens configurados aparecerão como navegação de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-123">Configured items then appear as header navigation.</span></span> 

- <span data-ttu-id="c9a5f-124">**Pesquisa** – O módulo de pesquisa permite que os usuários insiram termos para procurar produtos.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-124">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="c9a5f-125">A URL da página de pesquisa padrão e os parâmetros de consulta de pesquisa devem ser fornecidos em **Configurações do Site \> Extensões**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-125">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="c9a5f-126">O módulo de pesquisa tem propriedades que permitem suprimir o botão ou o rótulo de pesquisa, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-126">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="c9a5f-127">O módulo de pesquisa também oferece suporte a opções de sugestão automática, como resultados de pesquisa por produtos, palavras-chave e categorias.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-127">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="c9a5f-128">**Ícone do carrinho** - O módulo de ícone do carrinho representa o ícone do carrinho, que mostra o número de itens no carrinho a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-128">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="c9a5f-129">Para obter mais informações, consulte [Módulo de ícone de carrinho](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="c9a5f-129">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="c9a5f-130">Criar um módulo de cabeçalho para uma página</span><span class="sxs-lookup"><span data-stu-id="c9a5f-130">Create a header module for a page</span></span>

<span data-ttu-id="c9a5f-131">Para criar um módulo de cabeçalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-131">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="c9a5f-132">Vá para **Fragmentos de Página** e selecione **Novo** para criar um novo fragmento.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-132">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="c9a5f-133">Na caixa de diálogo **Novo Fragmento de Página**, selecione o módulo **Contêiner**, insira um nome para o fragmento de página e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-133">In the **New Page Fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="c9a5f-134">Selecione o slot **Contêiner padrão** e, no painel de propriedades à direita, defina a propriedade **Largura** como **Preencher contêiner**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-134">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="c9a5f-135">No slot **Contêiner padrão**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-135">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c9a5f-136">Na caixa de diálogo **Adicionar Módulo**, selecione os módulos **Faixa promocional** e **Consentimento de cookie** e, depois, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-136">In the **Add Module** dialog box, select the **Promo banner** and **Cookie consent** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="c9a5f-137">No slot **Contêiner padrão**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-137">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c9a5f-138">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-138">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c9a5f-139">Selecione o slot **Contêiner** e, no painel de propriedades à direita, defina a propriedade **Largura** como **Preencher contêiner**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-139">Select the **Container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="c9a5f-140">No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-140">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c9a5f-141">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Cabeçalho** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-141">In the **Add Module** dialog box, select the **Header** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c9a5f-142">No slot **Menu de navegação** do módulo de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-142">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c9a5f-143">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Menu de navegação** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-143">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c9a5f-144">No painel de propriedades do módulo de menu de navegação, configure as propriedades conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-144">In the property pane for the navigation menu module, configure the properties as needed.</span></span>
1. <span data-ttu-id="c9a5f-145">No slot **Pesquisar** do módulo de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c9a5f-146">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Pesquisar** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c9a5f-147">No painel de propriedades do módulo de pesquisa, configure as propriedades conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="c9a5f-148">No slot **Ícone de carrinho** do módulo de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="c9a5f-149">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo de **Ícone de carrinho** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="c9a5f-150">No painel de propriedades do módulo de ícone de carrinho, configure as propriedades conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="c9a5f-151">Se desejar que o ícone de carrinho exiba um resumo de carrinho (também conhecido como um minicarrinho) quando os usuários passarem o mouse sobre ele, selecione **Mostrar minicarrinho**.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="c9a5f-152">Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="c9a5f-153">Para ajudar a garantir que um cabeçalho aparece em cada página, siga estas etapas em cada modelo da página que é desenvolvido para o site.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-153">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="c9a5f-154">No slot **Cabeçalho** do módulo **Página padrão**, adicione o fragmento de rodapé que você criou.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="c9a5f-155">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="c9a5f-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c9a5f-156">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c9a5f-156">Additional resources</span></span>

[<span data-ttu-id="c9a5f-157">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="c9a5f-157">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c9a5f-158">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="c9a5f-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="c9a5f-159">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="c9a5f-159">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="c9a5f-160">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="c9a5f-160">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c9a5f-161">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="c9a5f-161">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="c9a5f-162">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="c9a5f-162">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="c9a5f-163">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="c9a5f-163">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="c9a5f-164">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="c9a5f-164">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="c9a5f-165">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="c9a5f-165">Footer module</span></span>](author-footer-module.md)
