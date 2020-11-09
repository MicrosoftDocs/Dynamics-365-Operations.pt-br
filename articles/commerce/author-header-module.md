---
title: Módulo de cabeçalho
description: Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 52069af5ca2211473d4a096ad850b5be1290bba1
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055441"
---
# <a name="header-module"></a><span data-ttu-id="2d1c2-103">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="2d1c2-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2d1c2-104">Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2d1c2-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="2d1c2-105">Overview</span></span>

<span data-ttu-id="2d1c2-106">No Dynamics 365 Commerce, um cabeçalho de página é configurado como um fragmento de página que inclui os módulos de cabeçalho, faixa promocional e consentimento de cookie.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-106">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="2d1c2-107">O módulo de cabeçalho inclui um logotipo do site, links para a hierarquia de navegação, links para outras páginas do site, um módulo de ícone de carrinho, um símbolo de lista de desejos, opções de entrada e a barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="2d1c2-108">Um módulo de cabeçalho é otimizado automaticamente para o dispositivo onde o site está sendo exibido (ou seja, um dispositivo móvel ou de desktop).</span><span class="sxs-lookup"><span data-stu-id="2d1c2-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="2d1c2-109">Por exemplo, em um dispositivo móvel, a barra de navegação é recolhida em um botão **Menu** (que é conhecido ocasionalmente como *menu hambúrguer* ).</span><span class="sxs-lookup"><span data-stu-id="2d1c2-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu* ).</span></span>

<span data-ttu-id="2d1c2-110">A imagem a seguir mostra um exemplo de um módulo de cabeçalho em uma home page.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-110">The following image shows an example of a header module on a home page.</span></span>

![Exemplo de um módulo de cabeçalho](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="2d1c2-112">Propriedades de um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="2d1c2-112">Properties of a header module</span></span>

<span data-ttu-id="2d1c2-113">Um módulo de cabeçalho oferece suporte às propriedades **Imagem de logotipo** , **Link de logotipo** e **Links da minha conta**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-113">A header module supports **Logo image** , **Logo link** , and **My account links** properties.</span></span> 

<span data-ttu-id="2d1c2-114">As propriedades **Imagem de logotipo** e **Link de logotipo** são usadas para definir um logotipo na página.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="2d1c2-115">Para obter mais informações, consulte [Adicionar um logotipo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="2d1c2-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="2d1c2-116">A propriedade **Links da minha conta** pode ser usada para definir as páginas da conta das quais o proprietário do site quer mostrar links rápidos no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="2d1c2-117">Módulos disponíveis em um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="2d1c2-117">Modules that are available within a header module</span></span>

<span data-ttu-id="2d1c2-118">Os módulos a seguir podem ser usados em um módulo de cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="2d1c2-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="2d1c2-119">**Menu de navegação** – O menu de navegação representa a hierarquia de navegação de canal e outros links estáticos de navegação.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="2d1c2-120">Para obter mais informações, consulte [Módulo do menu de navegação](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="2d1c2-120">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="2d1c2-121">**Pesquisa** – O módulo de pesquisa permite que os usuários insiram termos para procurar produtos.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-121">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="2d1c2-122">A URL da página de pesquisa padrão e os parâmetros de consulta de pesquisa devem ser fornecidos em **Configurações do Site \> Extensões**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-122">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="2d1c2-123">O módulo de pesquisa tem propriedades que permitem suprimir o botão ou o rótulo de pesquisa, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-123">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="2d1c2-124">O módulo de pesquisa também oferece suporte a opções de sugestão automática, como resultados de pesquisa por produtos, palavras-chave e categorias.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-124">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="2d1c2-125">**Ícone do carrinho** - O módulo de ícone do carrinho representa o ícone do carrinho, que mostra o número de itens no carrinho a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-125">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="2d1c2-126">Para obter mais informações, consulte [Módulo de ícone de carrinho](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="2d1c2-126">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

- <span data-ttu-id="2d1c2-127">**Seletor de site** — o módulo seletor de site permite que os usuários naveguem por diferentes sites predefinidos, com base no mercado, nas regiões e localidades.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-127">**Site selector** - The site selector module lets users browse across different predefined sites, based on market, regions, and locales.</span></span> <span data-ttu-id="2d1c2-128">Para obter mais informações, consulte [Módulo de seletor de site](site-selector.md).</span><span class="sxs-lookup"><span data-stu-id="2d1c2-128">For more information, see [Site selector module](site-selector.md).</span></span>

- <span data-ttu-id="2d1c2-129">**Seletor de loja** — o módulo seletor de loja pode ser incluído em um slot do seletor de loja do módulo de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-129">**Store selector** - The store selector module can be included in a header module's store selector slot.</span></span> <span data-ttu-id="2d1c2-130">Ele permite que os usuários procurem e encontrem lojas próximas.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-130">It lets users browse and find nearby stores.</span></span> <span data-ttu-id="2d1c2-131">Os usuários também podem especificar uma loja preferida.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-131">Users can also specify a preferred store.</span></span> <span data-ttu-id="2d1c2-132">Essa loja será mostrada no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-132">That store will then be shown in the header.</span></span> <span data-ttu-id="2d1c2-133">Quando o módulo seletor de loja é incluído no módulo de cabeçalho, sua propriedade **Modo** deve ser definida como **Localizar lojas**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-133">When the store selector module is included in the header module, its **Mode** property must be set to **Find stores**.</span></span> <span data-ttu-id="2d1c2-134">Para obter mais informações, consulte [Módulo de seletor de loja](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="2d1c2-134">For more information, see [Store selector module](store-selector.md).</span></span>

> [!NOTE]
> - <span data-ttu-id="2d1c2-135">O suporte ao uso do módulo de ícone de carrinho nos módulos de cabeçalho está disponível no Dynamics 365 Commerce versão 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-135">Support for using the cart icon module in header modules is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>
> - <span data-ttu-id="2d1c2-136">O suporte ao uso do módulo de ícone de selector de site nos módulos de cabeçalho está disponível no Dynamics 365 Commerce versão 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-136">Support for using the site selector module in header modules is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>
> - <span data-ttu-id="2d1c2-137">O suporte ao uso do módulo de ícone de selector de loja nos módulos de cabeçalho está disponível no Dynamics 365 Commerce versão 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-137">Support for using the store selector module in header modules is available in the Dynamics 365 Commerce 10.0.15 release.</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="2d1c2-138">Criar um fragmento de cabeçalho para uma página</span><span class="sxs-lookup"><span data-stu-id="2d1c2-138">Create a header fragment for a page</span></span>

<span data-ttu-id="2d1c2-139">Para criar um fragmento de cabeçalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-139">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="2d1c2-140">Vá para **Fragmentos** e selecione **Novo** para criar um novo fragmento.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-140">Go to **Fragments** , and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="2d1c2-141">Na caixa de diálogo **Novo fragmento** , selecione o módulo **Contêiner** , insira um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-141">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="2d1c2-142">Selecione o slot **Contêiner padrão** e, no painel de propriedades à direita, defina a propriedade **Largura** como **Preencher Tela**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-142">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="2d1c2-143">No slot **Contêiner padrão** , selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-143">In the **Default container** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2d1c2-144">Na caixa de diálogo **Adicionar Módulo** , selecione os módulos **Consentimento de cookie** , **Cabeçalho** e **Faixa promocional** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-144">In the **Add Module** dialog box, select the **Cookie consent** , **Header** , and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="2d1c2-145">No painel de propriedades do módulo **Faixa promocional** , selecione **Adicionar Mensagem** e, em seguida, selecione **Mensagem** .</span><span class="sxs-lookup"><span data-stu-id="2d1c2-145">In the properties pane of the **Promo banner** module, select **Add Message** , and then select **Message**.</span></span>
1. <span data-ttu-id="2d1c2-146">Na caixa de diálogo **Mensagem** , adicione texto e links para o conteúdo promocional e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-146">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="2d1c2-147">No painel de propriedades do módulo **Consentimento de cookie** , adicione e configure o texto e um link para a página de privacidade do site.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-147">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="2d1c2-148">No slot **Menu de navegação** do módulo de cabeçalho, selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-148">In the **Navigation menu** slot of the header module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2d1c2-149">Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Menu de navegação** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-149">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2d1c2-150">No painel de propriedades do módulo do menu de navegação, em **Origem do menu de navegação** , selecione **Retail Server**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-150">In the property pane for the navigation menu module, under **Source for navigation menu** , select **Retail Server**.</span></span>
1. <span data-ttu-id="2d1c2-151">No painel de propriedades do módulo do menu de navegação, em **Itens de menu estático** , selecione **Adicionar item de menu** e, em seguida, selecione **Item de menu**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-151">In the property pane for the navigation menu module, under **Static menu items** , select **Add Menu item** , and then select **Menu item**.</span></span> 
1. <span data-ttu-id="2d1c2-152">Na caixa de diálogo **Item de menu** , em **Texto do Item de Menu** , insira "Contato".</span><span class="sxs-lookup"><span data-stu-id="2d1c2-152">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="2d1c2-153">Na caixa de diálogo **Item de menu** , em **Destino do link do item de menu** , selecione **Adicionar um link**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-153">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="2d1c2-154">Na caixa de diálogo **Adicionar um link** , selecione a URL para a página "Contato" do site e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-154">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="2d1c2-155">Na caixa de diálogo **Item de menu** , selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-155">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="2d1c2-156">No slot **Pesquisar** do módulo de cabeçalho, selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-156">In the **Search** slot of the header module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2d1c2-157">Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Pesquisar** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-157">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2d1c2-158">No painel de propriedades do módulo de pesquisa, configure as propriedades conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-158">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="2d1c2-159">No slot **Ícone de carrinho** do módulo de cabeçalho, selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-159">In the **Cart icon** slot of the header module, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="2d1c2-160">Na caixa de diálogo **Adicionar Módulo** , selecione o módulo de **Ícone de carrinho** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-160">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="2d1c2-161">No painel de propriedades do módulo de ícone de carrinho, configure as propriedades conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-161">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="2d1c2-162">Se desejar que o ícone de carrinho exiba um resumo de carrinho (também conhecido como um minicarrinho) quando os usuários passarem o mouse sobre ele, selecione **Mostrar minicarrinho**.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-162">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="2d1c2-163">Selecione **Salvar** , **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-163">Select **Save** , select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="2d1c2-164">Para ajudar a garantir que um cabeçalho apareça em todas as páginas, siga estas etapas em todos os modelos de página criados para o site.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-164">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="2d1c2-165">No slot **Cabeçalho** do módulo **Página padrão** , adicione o fragmento de rodapé que você criou.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-165">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="2d1c2-166">Selecione **Salvar** , **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="2d1c2-166">Select **Save** , select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2d1c2-167">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="2d1c2-167">Additional resources</span></span>

[<span data-ttu-id="2d1c2-168">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="2d1c2-168">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2d1c2-169">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="2d1c2-169">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="2d1c2-170">Módulo de ícone de carrinho</span><span class="sxs-lookup"><span data-stu-id="2d1c2-170">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="2d1c2-171">Módulo de banner de promoção</span><span class="sxs-lookup"><span data-stu-id="2d1c2-171">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="2d1c2-172">Módulo do menu de navegação</span><span class="sxs-lookup"><span data-stu-id="2d1c2-172">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="2d1c2-173">Consentimento de cookie</span><span class="sxs-lookup"><span data-stu-id="2d1c2-173">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="2d1c2-174">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="2d1c2-174">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="2d1c2-175">Módulo de seletor de site</span><span class="sxs-lookup"><span data-stu-id="2d1c2-175">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="2d1c2-176">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="2d1c2-176">Store selector module</span></span>](store-selector.md)
