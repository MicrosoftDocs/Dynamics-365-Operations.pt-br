---
title: Módulo de cabeçalho
description: Este tópico abrange os módulos de cabeçalho e descreve como criá-los no Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: d393701dacb88ab03a4b56724d93c794da6bb5c8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697266"
---
# <a name="header-module"></a><span data-ttu-id="4dfd7-103">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="4dfd7-103">Header module</span></span>

<span data-ttu-id="4dfd7-104">[!include [banner](includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span><span class="sxs-lookup"><span data-stu-id="4dfd7-104">[!include [banner]includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span></span>

<span data-ttu-id="4dfd7-105">Este tópico abrange os módulos de cabeçalho e descreve como criá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-105">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4dfd7-106">Visão geral</span><span class="sxs-lookup"><span data-stu-id="4dfd7-106">Overview</span></span>

<span data-ttu-id="4dfd7-107">Um módulo de cabeçalho é um contêiner especial usado para todos os módulos que serão mostrados em um cabeçalho de página.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-107">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="4dfd7-108">Por exemplo, pode incluir o logotipo do site, links para a hierarquia de navegação, links para outras páginas no site e a barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-108">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="4dfd7-109">Um módulo de cabeçalho é otimizado automaticamente paro dispositivo onde o site está sendo exibido (isto é, um dispositivo da área de trabalho ou um dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="4dfd7-109">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="4dfd7-110">Por exemplo, em um dispositivo móvel, a barra de navegação é recolhida em um botão **Menu** (que é conhecido ocasionalmente como *menu hambúrguer*).</span><span class="sxs-lookup"><span data-stu-id="4dfd7-110">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="4dfd7-111">Propriedades de um cabeçalho</span><span class="sxs-lookup"><span data-stu-id="4dfd7-111">Properties of a header</span></span>

<span data-ttu-id="4dfd7-112">Como contêiner genéricos, um módulo de cabeçalho suporta as propriedades de **cabeçalho** e **largura** .</span><span class="sxs-lookup"><span data-stu-id="4dfd7-112">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="4dfd7-113">Um módulo de cabeçalho tem várias slots.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-113">A header module has multiple slots.</span></span> <span data-ttu-id="4dfd7-114">Por exemplo, há slots para uma mensagem informativa, um menu de navegação, um logotipo, uma barra de pesquisa, um ícone móvel, um ícone da lista de objetivos e informações da conta.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-114">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="4dfd7-115">Cada slot suporta um conjunto específico de módulos.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-115">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="4dfd7-116">Módulos disponíveis em um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="4dfd7-116">Modules that are available in a header module</span></span>

<span data-ttu-id="4dfd7-117">Os módulos a seguir podem ser usados em um módulo de cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="4dfd7-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="4dfd7-118">**Menu de navegação** – O menu de navegação representa a hierarquia de navegação de canal e outros links estáticos de navegação.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="4dfd7-119">A hierarquia de navegação de canal pode ser configurada no Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-119">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="4dfd7-120">Os itens configurados aparecerão como navegação de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-120">Configured items then appear as header navigation.</span></span> <span data-ttu-id="4dfd7-121">Além disso, links estáticos de navegação podem ser configurados e links links relativos a outras páginas no site comercial online pode ser promovido.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-121">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="4dfd7-122">O cabeçalho em si pode ser alinhado à esquerda e direita ou no centro.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-122">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="4dfd7-123">**Ícone de carrinho** – O ícone de carrinho é um ícone especial que representa o carrinho.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-123">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="4dfd7-124">É exibido no cabeçalho e indica o número de itens no carrinho.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-124">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="4dfd7-125">Um link para a página do carrinho deve acompanhar o ícone do carrinho para que os clientes possam ser redirecionados à página do carrinho quando interagem com o ícone.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-125">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="4dfd7-126">**Ícone da lista de desejos** – O ícone da lista de desejos é exibido no cabeçalho e indica o número de itens que foram adicionados à lista de desejos do cliente.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-126">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="4dfd7-127">Um link para a página de lista de desejos deve acompanhar esse ícone para que os clientes possam ser redirecionados à página de lista de desejos quando interagem com o ícone.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-127">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="4dfd7-128">**Módulo de login** – O módulo de login é exibido no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-128">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="4dfd7-129">Permite que os clientes entrem em sua conta ou se inscrevam em uma conta.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-129">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="4dfd7-130">Se o cliente já estiver conectado, o módulo pode ser configurado para exibir links na página da conta, a página de histórico de ordens ou outra página.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-130">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="4dfd7-131">**Módulo de logotipo** – Este módulo mostra o logotipo representando o fornecedor e a marca.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-131">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="4dfd7-132">É uma imagem que tem o link.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-132">It's an image that has a link.</span></span> <span data-ttu-id="4dfd7-133">O link é normalmente configurado de forma que possa redirecionar para a página principal. Portanto, os clientes podem retornar rapidamente para a página inicial de qualquer página no site.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-133">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="4dfd7-134">**Alerta** – Um alerta é exibido no cabeçalho e é usado para mostrar a mensagem embutida que se aplica a quaisquer páginas no site.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-134">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="4dfd7-135">Por exemplo, o alerta pode mostrar a mensagem como "Venda anual termina em 2 dias".</span><span class="sxs-lookup"><span data-stu-id="4dfd7-135">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="4dfd7-136">**Barra de pesquisa** – A barra de tarefas permite que o usuário insira tais termos para que possam pesquisar por produtos.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-136">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="4dfd7-137">O módulo deve ser configurado com a URL da página de resultados de busca.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-137">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="4dfd7-138">O parâmetro de sequência de pesquisa pode ser configurado (o valor padrão é **"q"**).</span><span class="sxs-lookup"><span data-stu-id="4dfd7-138">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="4dfd7-139">A barra de pesquisa têm um slot de sugestão automática que sugere automaticamente o módulo que deve ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-139">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="4dfd7-140">**Sugestão automática** – O módulo de sugestão automática mostra resultados sugeridos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-140">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="4dfd7-141">Os resultados podem ser palavras-chave, produtos ou categorias onde o termo de pesquisa é encontrado.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-141">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="4dfd7-142">Criar um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="4dfd7-142">Create a header module</span></span>

<span data-ttu-id="4dfd7-143">Para criar um módulo de cabeçalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-143">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="4dfd7-144">Criar um fragmento de página que inclui um módulo de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-144">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="4dfd7-145">Adicionar os módulos aos slots no módulo de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-145">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="4dfd7-146">Atualizar as configurações de cada módulo.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-146">Update the settings for each module.</span></span>
1. <span data-ttu-id="4dfd7-147">Salvar o fragmento de página.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-147">Save the page fragment.</span></span> 
1. <span data-ttu-id="4dfd7-148">Insira a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-148">Check in the page, and publish it.</span></span>

<span data-ttu-id="4dfd7-149">Para ajudar a garantir que um cabeçalho aparece em cada página, siga estas etapas em cada modelo da página que é desenvolvido para o site.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-149">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="4dfd7-150">Na página padrão, adicione a parte mais importante da página que contém o módulo de cabeçalho no cabeçalho no slot principal.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-150">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="4dfd7-151">Salve o modelo.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-151">Save the template.</span></span> 
1. <span data-ttu-id="4dfd7-152">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="4dfd7-152">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4dfd7-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4dfd7-153">Additional resources</span></span>

[<span data-ttu-id="4dfd7-154">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="4dfd7-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4dfd7-155">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="4dfd7-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="4dfd7-156">Comprar módulo de caixa</span><span class="sxs-lookup"><span data-stu-id="4dfd7-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="4dfd7-157">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="4dfd7-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="4dfd7-158">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="4dfd7-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="4dfd7-159">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="4dfd7-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="4dfd7-160">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="4dfd7-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="4dfd7-161">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="4dfd7-161">Footer module</span></span>](author-footer-module.md)
