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
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885469"
---
# <a name="header-module"></a><span data-ttu-id="0704e-103">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="0704e-103">Header module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="0704e-104">Este tópico abrange os módulos de cabeçalho e descreve como criá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0704e-104">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0704e-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="0704e-105">Overview</span></span>

<span data-ttu-id="0704e-106">Um módulo de cabeçalho é um contêiner especial usado para todos os módulos que serão mostrados em um cabeçalho de página.</span><span class="sxs-lookup"><span data-stu-id="0704e-106">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="0704e-107">Por exemplo, pode incluir o logotipo do site, links para a hierarquia de navegação, links para outras páginas no site e a barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0704e-107">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="0704e-108">Um módulo de cabeçalho é otimizado automaticamente paro dispositivo onde o site está sendo exibido (isto é, um dispositivo da área de trabalho ou um dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="0704e-108">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="0704e-109">Por exemplo, em um dispositivo móvel, a barra de navegação é recolhida em um botão **Menu** (que é conhecido ocasionalmente como *menu hambúrguer*).</span><span class="sxs-lookup"><span data-stu-id="0704e-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="0704e-110">Propriedades de um cabeçalho</span><span class="sxs-lookup"><span data-stu-id="0704e-110">Properties of a header</span></span>

<span data-ttu-id="0704e-111">Como contêiner genéricos, um módulo de cabeçalho suporta as propriedades de **cabeçalho** e **largura** .</span><span class="sxs-lookup"><span data-stu-id="0704e-111">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="0704e-112">Um módulo de cabeçalho tem várias slots.</span><span class="sxs-lookup"><span data-stu-id="0704e-112">A header module has multiple slots.</span></span> <span data-ttu-id="0704e-113">Por exemplo, há slots para uma mensagem informativa, um menu de navegação, um logotipo, uma barra de pesquisa, um ícone móvel, um ícone da lista de objetivos e informações da conta.</span><span class="sxs-lookup"><span data-stu-id="0704e-113">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="0704e-114">Cada slot suporta um conjunto específico de módulos.</span><span class="sxs-lookup"><span data-stu-id="0704e-114">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="0704e-115">Módulos disponíveis em um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="0704e-115">Modules that are available in a header module</span></span>

<span data-ttu-id="0704e-116">Os módulos a seguir podem ser usados em um módulo de cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="0704e-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="0704e-117">**Menu de navegação** – O menu de navegação representa a hierarquia de navegação de canal e outros links estáticos de navegação.</span><span class="sxs-lookup"><span data-stu-id="0704e-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="0704e-118">A hierarquia de navegação de canal pode ser configurada no Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="0704e-118">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="0704e-119">Os itens configurados aparecerão como navegação de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="0704e-119">Configured items then appear as header navigation.</span></span> <span data-ttu-id="0704e-120">Além disso, links estáticos de navegação podem ser configurados e links links relativos a outras páginas no site comercial online pode ser promovido.</span><span class="sxs-lookup"><span data-stu-id="0704e-120">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="0704e-121">O cabeçalho em si pode ser alinhado à esquerda e direita ou no centro.</span><span class="sxs-lookup"><span data-stu-id="0704e-121">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="0704e-122">**Ícone de carrinho** – O ícone de carrinho é um ícone especial que representa o carrinho.</span><span class="sxs-lookup"><span data-stu-id="0704e-122">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="0704e-123">É exibido no cabeçalho e indica o número de itens no carrinho.</span><span class="sxs-lookup"><span data-stu-id="0704e-123">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="0704e-124">Um link para a página do carrinho deve acompanhar o ícone do carrinho para que os clientes possam ser redirecionados à página do carrinho quando interagem com o ícone.</span><span class="sxs-lookup"><span data-stu-id="0704e-124">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="0704e-125">**Ícone da lista de desejos** – O ícone da lista de desejos é exibido no cabeçalho e indica o número de itens que foram adicionados à lista de desejos do cliente.</span><span class="sxs-lookup"><span data-stu-id="0704e-125">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="0704e-126">Um link para a página de lista de desejos deve acompanhar esse ícone para que os clientes possam ser redirecionados à página de lista de desejos quando interagem com o ícone.</span><span class="sxs-lookup"><span data-stu-id="0704e-126">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="0704e-127">**Módulo de login** – O módulo de login é exibido no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="0704e-127">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="0704e-128">Permite que os clientes entrem em sua conta ou se inscrevam em uma conta.</span><span class="sxs-lookup"><span data-stu-id="0704e-128">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="0704e-129">Se o cliente já estiver conectado, o módulo pode ser configurado para exibir links na página da conta, a página de histórico de ordens ou outra página.</span><span class="sxs-lookup"><span data-stu-id="0704e-129">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="0704e-130">**Módulo de logotipo** – Este módulo mostra o logotipo representando o fornecedor e a marca.</span><span class="sxs-lookup"><span data-stu-id="0704e-130">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="0704e-131">É uma imagem que tem o link.</span><span class="sxs-lookup"><span data-stu-id="0704e-131">It's an image that has a link.</span></span> <span data-ttu-id="0704e-132">O link é normalmente configurado de forma que possa redirecionar para a página principal. Portanto, os clientes podem retornar rapidamente para a página inicial de qualquer página no site.</span><span class="sxs-lookup"><span data-stu-id="0704e-132">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="0704e-133">**Alerta** – Um alerta é exibido no cabeçalho e é usado para mostrar a mensagem embutida que se aplica a quaisquer páginas no site.</span><span class="sxs-lookup"><span data-stu-id="0704e-133">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="0704e-134">Por exemplo, o alerta pode mostrar a mensagem como "Venda anual termina em 2 dias".</span><span class="sxs-lookup"><span data-stu-id="0704e-134">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="0704e-135">**Barra de pesquisa** – A barra de tarefas permite que o usuário insira tais termos para que possam pesquisar por produtos.</span><span class="sxs-lookup"><span data-stu-id="0704e-135">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="0704e-136">O módulo deve ser configurado com a URL da página de resultados de busca.</span><span class="sxs-lookup"><span data-stu-id="0704e-136">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="0704e-137">O parâmetro de sequência de pesquisa pode ser configurado (o valor padrão é **"q"**).</span><span class="sxs-lookup"><span data-stu-id="0704e-137">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="0704e-138">A barra de pesquisa têm um slot de sugestão automática que sugere automaticamente o módulo que deve ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="0704e-138">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="0704e-139">**Sugestão automática** – O módulo de sugestão automática mostra resultados sugeridos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0704e-139">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="0704e-140">Os resultados podem ser palavras-chave, produtos ou categorias onde o termo de pesquisa é encontrado.</span><span class="sxs-lookup"><span data-stu-id="0704e-140">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="0704e-141">Criar um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="0704e-141">Create a header module</span></span>

<span data-ttu-id="0704e-142">Para criar um módulo de cabeçalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0704e-142">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="0704e-143">Criar um fragmento de página que inclui um módulo de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="0704e-143">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="0704e-144">Adicionar os módulos aos slots no módulo de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="0704e-144">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="0704e-145">Atualizar as configurações de cada módulo.</span><span class="sxs-lookup"><span data-stu-id="0704e-145">Update the settings for each module.</span></span>
1. <span data-ttu-id="0704e-146">Salvar o fragmento de página.</span><span class="sxs-lookup"><span data-stu-id="0704e-146">Save the page fragment.</span></span> 
1. <span data-ttu-id="0704e-147">Insira a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="0704e-147">Check in the page, and publish it.</span></span>

<span data-ttu-id="0704e-148">Para ajudar a garantir que um cabeçalho aparece em cada página, siga estas etapas em cada modelo da página que é desenvolvido para o site.</span><span class="sxs-lookup"><span data-stu-id="0704e-148">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="0704e-149">Na página padrão, adicione a parte mais importante da página que contém o módulo de cabeçalho no cabeçalho no slot principal.</span><span class="sxs-lookup"><span data-stu-id="0704e-149">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="0704e-150">Salve o modelo.</span><span class="sxs-lookup"><span data-stu-id="0704e-150">Save the template.</span></span> 
1. <span data-ttu-id="0704e-151">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="0704e-151">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0704e-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0704e-152">Additional resources</span></span>

[<span data-ttu-id="0704e-153">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="0704e-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0704e-154">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="0704e-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="0704e-155">Comprar módulo de caixa</span><span class="sxs-lookup"><span data-stu-id="0704e-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="0704e-156">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="0704e-156">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="0704e-157">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="0704e-157">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="0704e-158">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="0704e-158">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="0704e-159">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="0704e-159">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="0704e-160">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="0704e-160">Footer module</span></span>](author-footer-module.md)
