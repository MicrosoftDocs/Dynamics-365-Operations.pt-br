---
title: Módulo do mapa
description: Este tópico abrange os módulos do módulo e descreve como configurá-los no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: a0f5d902289c5867095e34a135c50d342f3c4f13
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646860"
---
# <a name="map-module"></a><span data-ttu-id="65da6-103">Módulo do mapa</span><span class="sxs-lookup"><span data-stu-id="65da6-103">Map module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="65da6-104">Este tópico abrange os módulos do módulo e descreve como configurá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="65da6-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="65da6-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="65da6-105">Overview</span></span>

<span data-ttu-id="65da6-106">Um módulo de mapa mostra os locais de armazenamentos em um mapa interativo processado usando o [Controle da Web V8 do Bing Maps](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="65da6-106">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="65da6-107">Uma chave de API do Bing Maps é necessária e deve ser adicionada à página de parâmetros compartilhados na Sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="65da6-107">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="65da6-108">Os módulos de mapa fornecem exibições diferentes, como estrada, aérea e Streetside, que os usuários podem selecionar para exibir os locais dos mapas.</span><span class="sxs-lookup"><span data-stu-id="65da6-108">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="65da6-109">Eles também permitem interações como o zoom e o uso do local do usuário.</span><span class="sxs-lookup"><span data-stu-id="65da6-109">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="65da6-110">Um módulo de mapa trabalha em conjunto com o módulo seletor de lojas para determinar os locais geográficos das lojas que devem ser renderizados em um mapa.</span><span class="sxs-lookup"><span data-stu-id="65da6-110">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="65da6-111">O seletor de armazenamento e os módulos de mapa interagem quando um usuário seleciona um armazenamento em um desses módulos em uma página do site.</span><span class="sxs-lookup"><span data-stu-id="65da6-111">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="65da6-112">Os módulos de mapa podem ser estendidos para outros cenários, além da interação com os módulos do seletor de loja.</span><span class="sxs-lookup"><span data-stu-id="65da6-112">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="65da6-113">No entanto, a personalização do módulo é necessária.</span><span class="sxs-lookup"><span data-stu-id="65da6-113">However, module customization is required.</span></span>

<span data-ttu-id="65da6-114">O módulo do mapa foi introduzido no Commerce versão 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="65da6-114">The map module was introduced in Commerce version 10.0.13.</span></span>

<span data-ttu-id="65da6-115">A imagem a seguir mostra um exemplo de um módulo de mapa que é usado em uma página de locais da loja.</span><span class="sxs-lookup"><span data-stu-id="65da6-115">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Exemplo de um módulo de seletor de loja](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="65da6-117">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="65da6-117">Module properties</span></span>

| <span data-ttu-id="65da6-118">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="65da6-118">Property name</span></span>             | <span data-ttu-id="65da6-119">Alíquota</span><span class="sxs-lookup"><span data-stu-id="65da6-119">Value</span></span>                 | <span data-ttu-id="65da6-120">descrição</span><span class="sxs-lookup"><span data-stu-id="65da6-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="65da6-121">Título</span><span class="sxs-lookup"><span data-stu-id="65da6-121">Heading</span></span> | <span data-ttu-id="65da6-122">Texto</span><span class="sxs-lookup"><span data-stu-id="65da6-122">Text</span></span> | <span data-ttu-id="65da6-123">O título do módulo.</span><span class="sxs-lookup"><span data-stu-id="65da6-123">The heading for the module.</span></span> |
| <span data-ttu-id="65da6-124">Opções de anotações: ícone padrão</span><span class="sxs-lookup"><span data-stu-id="65da6-124">Pushpin options: Default icon</span></span> | <span data-ttu-id="65da6-125">Imagem</span><span class="sxs-lookup"><span data-stu-id="65da6-125">Image</span></span> | <span data-ttu-id="65da6-126">A imagem do símbolo de anotação a ser usada para lojas mostradas em um mapa.</span><span class="sxs-lookup"><span data-stu-id="65da6-126">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="65da6-127">Opções de anotações: ícone Ativo</span><span class="sxs-lookup"><span data-stu-id="65da6-127">Pushpin options: Active icon</span></span> | <span data-ttu-id="65da6-128">Imagem</span><span class="sxs-lookup"><span data-stu-id="65da6-128">Image</span></span> | <span data-ttu-id="65da6-129">A imagem do símbolo de anotação a ser usada para uma loja selecionada em um mapa.</span><span class="sxs-lookup"><span data-stu-id="65da6-129">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="65da6-130">Opções de anotações: cor do ícone padrão</span><span class="sxs-lookup"><span data-stu-id="65da6-130">Pushpin options: Default icon color</span></span> | <span data-ttu-id="65da6-131">String de caracteres</span><span class="sxs-lookup"><span data-stu-id="65da6-131">Character string</span></span> | <span data-ttu-id="65da6-132">O texto ou valor hexadecimal da cor dos símbolos de anotações em um mapa.</span><span class="sxs-lookup"><span data-stu-id="65da6-132">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="65da6-133">Opções de anotações: cor do ícone Ativo</span><span class="sxs-lookup"><span data-stu-id="65da6-133">Pushpin options: Active icon color</span></span> | <span data-ttu-id="65da6-134">String de caracteres</span><span class="sxs-lookup"><span data-stu-id="65da6-134">Character string</span></span> | <span data-ttu-id="65da6-135">O texto ou valor hexadecimal da cor dos símbolos de anotações selecionados em um mapa.</span><span class="sxs-lookup"><span data-stu-id="65da6-135">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="65da6-136">Mostrar índice</span><span class="sxs-lookup"><span data-stu-id="65da6-136">Show index</span></span> | <span data-ttu-id="65da6-137">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="65da6-137">**True** or **False**</span></span> | <span data-ttu-id="65da6-138">Se esta propriedade for definida como **verdadeira**, cada símbolo de anotação que indicar uma loja mostrará um índice.</span><span class="sxs-lookup"><span data-stu-id="65da6-138">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="65da6-139">Esse índice corresponderá ao índice na exibição de lista mostrada pelo módulo seletor de loja.</span><span class="sxs-lookup"><span data-stu-id="65da6-139">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="65da6-140">Adicionar URLs de mapeamento permitido a diretivas de diretiva de segurança de conteúdo de um site</span><span class="sxs-lookup"><span data-stu-id="65da6-140">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="65da6-141">Para que o módulo mapas interaja com o Bing Maps, você deve garantir que as seguintes URLs de mapeamento são permitidas (também conhecidas como "lista de permissões"), conforme a política de segurança de conteúdo (CSP) do site.</span><span class="sxs-lookup"><span data-stu-id="65da6-141">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed (also known as "whitelisted") per your site's content security policy (CSP).</span></span> <span data-ttu-id="65da6-142">Essa configuração é executada na criação de site do Commerce, adicionando as URLs permitidas às várias diretivas da CSP do site (por exemplo, **img-src**).</span><span class="sxs-lookup"><span data-stu-id="65da6-142">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="65da6-143">Para obter mais informações, consulte [Política de segurança de conteúdo](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="65da6-143">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="65da6-144">Para a diretiva **connect-src**, adicione **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="65da6-144">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="65da6-145">Para a diretiva **img-src**, adicione **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="65da6-145">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="65da6-146">Para a diretiva **script-src**, adicione **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="65da6-146">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="65da6-147">Para a diretiva **script style-src**, adicione **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="65da6-147">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="65da6-148">Adicionar um módulo de mapa a uma página</span><span class="sxs-lookup"><span data-stu-id="65da6-148">Add a map module to a page</span></span>

<span data-ttu-id="65da6-149">Para obter informações detalhadas sobre como configurar um módulo de mapa em uma página, consulte [módulo do seletor de loja](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="65da6-149">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="65da6-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="65da6-150">Additional resources</span></span>

[<span data-ttu-id="65da6-151">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="65da6-151">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="65da6-152">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="65da6-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="65da6-153">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="65da6-153">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="65da6-154">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="65da6-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="65da6-155">Gerenciar o Bing Mapas da sua organização</span><span class="sxs-lookup"><span data-stu-id="65da6-155">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="65da6-156">Controle da Web V8 do Bing Maps</span><span class="sxs-lookup"><span data-stu-id="65da6-156">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)
