---
title: Módulo de cabeçalho
description: Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025641"
---
# <a name="header-module"></a><span data-ttu-id="e5500-103">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="e5500-103">Header module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e5500-104">Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e5500-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e5500-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e5500-105">Overview</span></span>

<span data-ttu-id="e5500-106">No Dynamics 365 Commerce, um cabeçalho de página consiste em vários módulos, como os de cabeçalho, menu de navegação, pesquisa, faixa promocional e consentimento de cookie.</span><span class="sxs-lookup"><span data-stu-id="e5500-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="e5500-107">O módulo de cabeçalho inclui um logotipo do site, links para a hierarquia de navegação, links para outras páginas do site, um símbolo de carrinho, um símbolo de lista de desejos, opções de entrada e a barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e5500-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="e5500-108">Um módulo de cabeçalho é otimizado automaticamente para o dispositivo onde o site está sendo exibido (ou seja, um dispositivo móvel ou de desktop).</span><span class="sxs-lookup"><span data-stu-id="e5500-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="e5500-109">Por exemplo, em um dispositivo móvel, a barra de navegação é recolhida em um botão **Menu** (que é conhecido ocasionalmente como *menu hambúrguer*).</span><span class="sxs-lookup"><span data-stu-id="e5500-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header-module"></a><span data-ttu-id="e5500-110">Propriedades de um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="e5500-110">Properties of a header module</span></span>

<span data-ttu-id="e5500-111">Um módulo de cabeçalho oferece suporte às propriedades **Imagem de logotipo**, **Link de logotipo** e **Links da minha conta**.</span><span class="sxs-lookup"><span data-stu-id="e5500-111">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="e5500-112">As propriedades **Imagem de logotipo** e **Link de logotipo** são usadas para definir um logotipo na página.</span><span class="sxs-lookup"><span data-stu-id="e5500-112">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="e5500-113">Para obter mais informações, consulte [Adicionar um logotipo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="e5500-113">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="e5500-114">A propriedade **Links da minha conta** pode ser usada para definir as páginas da conta das quais o proprietário do site quer mostrar links rápidos no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="e5500-114">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="e5500-115">Módulos disponíveis em um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="e5500-115">Modules that are available in a header module</span></span>

<span data-ttu-id="e5500-116">Os módulos a seguir podem ser usados em um módulo de cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="e5500-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="e5500-117">**Menu de navegação** – O menu de navegação representa a hierarquia de navegação de canal e outros links estáticos de navegação.</span><span class="sxs-lookup"><span data-stu-id="e5500-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="e5500-118">A hierarquia de navegação de canal pode ser configurada no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e5500-118">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="e5500-119">O menu de navegação tem uma propriedade **Origem de Navegação** usada para especificar itens do menu de navegação do Retail Server e itens de menu estático como origem.</span><span class="sxs-lookup"><span data-stu-id="e5500-119">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="e5500-120">Se itens de menu estático forem especificados como origem, poderão ser fornecidos links relativos a outras páginas do site.</span><span class="sxs-lookup"><span data-stu-id="e5500-120">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="e5500-121">Os itens configurados aparecerão como navegação de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="e5500-121">Configured items then appear as header navigation.</span></span> 
- <span data-ttu-id="e5500-122">**Pesquisa** – O módulo de pesquisa permite que os usuários insiram termos para procurar produtos.</span><span class="sxs-lookup"><span data-stu-id="e5500-122">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="e5500-123">A URL da página de pesquisa padrão e os parâmetros de consulta de pesquisa devem ser fornecidos em **Configurações do Site \> Extensões**.</span><span class="sxs-lookup"><span data-stu-id="e5500-123">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="e5500-124">O módulo de pesquisa tem propriedades que permitem suprimir o botão ou o rótulo de pesquisa, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e5500-124">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="e5500-125">O módulo de pesquisa também oferece suporte a opções de sugestão automática, como resultados de pesquisa por produtos, palavras-chave e categorias.</span><span class="sxs-lookup"><span data-stu-id="e5500-125">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="e5500-126">Criar um módulo de cabeçalho para uma página</span><span class="sxs-lookup"><span data-stu-id="e5500-126">Create a header module for a page</span></span>

<span data-ttu-id="e5500-127">Para criar um módulo de cabeçalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e5500-127">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="e5500-128">Crie um fragmento chamado **Fragmento de cabeçalho** e adicione um módulo de contêiner a ele.</span><span class="sxs-lookup"><span data-stu-id="e5500-128">Create a fragment that is named **Header fragment**, and add a container module to it.</span></span>
1. <span data-ttu-id="e5500-129">No painel de propriedades do módulo de contêiner, defina a propriedade **Largura** como **Preencher contêiner**.</span><span class="sxs-lookup"><span data-stu-id="e5500-129">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="e5500-130">Adicione módulos de consentimento de cookie e de faixa promocional ao módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="e5500-130">Add promo banner and cookie consent modules to the container module.</span></span>
1. <span data-ttu-id="e5500-131">Adicione outro módulo de contêiner ao fragmento e defina a propriedade **Largura** como **Preencher contêiner**.</span><span class="sxs-lookup"><span data-stu-id="e5500-131">Add another container module to the fragment, and set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="e5500-132">Adicione um módulo de cabeçalho ao segundo módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="e5500-132">Add a header module to the second container module.</span></span>
1. <span data-ttu-id="e5500-133">No slot **Menu de navegação** do módulo de cabeçalho, adicione um módulo de menu de navegação.</span><span class="sxs-lookup"><span data-stu-id="e5500-133">In the **Navigation menu** slot of the header module, add a navigation menu module.</span></span> 
1. <span data-ttu-id="e5500-134">No painel de propriedades do módulo de menu de navegação, configure as propriedades do módulo.</span><span class="sxs-lookup"><span data-stu-id="e5500-134">In the property pane for the navigation menu module, configure the properties of the navigation menu module.</span></span>
1. <span data-ttu-id="e5500-135">No slot **Pesquisa** do módulo de cabeçalho, adicione um módulo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e5500-135">In the **Search** slot of the header module, add a search module.</span></span> 
1. <span data-ttu-id="e5500-136">No painel de propriedades do módulo de pesquisa, configure as propriedades do módulo.</span><span class="sxs-lookup"><span data-stu-id="e5500-136">In the property pane for the search module, configure the properties of the search module.</span></span> 
1. <span data-ttu-id="e5500-137">Salve o fragmento de página, termine de editá-lo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="e5500-137">Save the page fragment, finish editing it, and publish it.</span></span> 

<span data-ttu-id="e5500-138">Para ajudar a garantir que um cabeçalho aparece em cada página, siga estas etapas em cada modelo da página que é desenvolvido para o site.</span><span class="sxs-lookup"><span data-stu-id="e5500-138">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="e5500-139">No slot **Principal** da página padrão, adicione ao cabeçalho o fragmento de página de cabeçalho que contém o módulo de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="e5500-139">In the **Main** slot of the default page, add the header page fragment that contains the header module to the header.</span></span>
1. <span data-ttu-id="e5500-140">Salve o modelo, termine de editá-lo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="e5500-140">Save the template, finish editing it, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e5500-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e5500-141">Additional resources</span></span>

[<span data-ttu-id="e5500-142">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="e5500-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e5500-143">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="e5500-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="e5500-144">Comprar módulo de caixa</span><span class="sxs-lookup"><span data-stu-id="e5500-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="e5500-145">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="e5500-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="e5500-146">Módulo de finalização da compra</span><span class="sxs-lookup"><span data-stu-id="e5500-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="e5500-147">Módulo de confirmação da ordem</span><span class="sxs-lookup"><span data-stu-id="e5500-147">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="e5500-148">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="e5500-148">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="e5500-149">Módulo de rodapé</span><span class="sxs-lookup"><span data-stu-id="e5500-149">Footer module</span></span>](author-footer-module.md)
