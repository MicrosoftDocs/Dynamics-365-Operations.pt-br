---
title: Módulo do mapa
description: Este tópico abrange os módulos do módulo e descreve como configurá-los no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 659211f3a74c38389f991cd2385366d175b0c7c0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020250"
---
# <a name="map-module"></a><span data-ttu-id="26460-103">Módulo de mapa</span><span class="sxs-lookup"><span data-stu-id="26460-103">Map module</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="26460-104">Este tópico abrange os módulos do módulo e descreve como configurá-los no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="26460-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="26460-105">Um módulo de mapa mostra os locais de armazenamentos em um mapa interativo processado usando o [Controle da Web V8 do Bing Maps](/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="26460-105">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="26460-106">Uma chave de API do Bing Maps é necessária e deve ser adicionada à página de parâmetros compartilhados na Sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="26460-106">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="26460-107">Os módulos de mapa fornecem exibições diferentes, como estrada, aérea e Streetside, que os usuários podem selecionar para exibir os locais dos mapas.</span><span class="sxs-lookup"><span data-stu-id="26460-107">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="26460-108">Eles também permitem interações como o zoom e o uso do local do usuário.</span><span class="sxs-lookup"><span data-stu-id="26460-108">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="26460-109">Um módulo de mapa trabalha em conjunto com o módulo seletor de lojas para determinar os locais geográficos das lojas que devem ser renderizados em um mapa.</span><span class="sxs-lookup"><span data-stu-id="26460-109">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="26460-110">O seletor de armazenamento e os módulos de mapa interagem quando um usuário seleciona um armazenamento em um desses módulos em uma página do site.</span><span class="sxs-lookup"><span data-stu-id="26460-110">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="26460-111">Os módulos de mapa podem ser estendidos para outros cenários, além da interação com os módulos do seletor de loja.</span><span class="sxs-lookup"><span data-stu-id="26460-111">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="26460-112">No entanto, a personalização do módulo é necessária.</span><span class="sxs-lookup"><span data-stu-id="26460-112">However, module customization is required.</span></span>

> [!NOTE]
> <span data-ttu-id="26460-113">O mapa está disponível na versão 10.0.13 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="26460-113">The map module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="26460-114">A imagem a seguir mostra um exemplo de um módulo de mapa que é usado em uma página de locais da loja.</span><span class="sxs-lookup"><span data-stu-id="26460-114">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Exemplo de um módulo de seletor de loja](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="26460-116">Propriedades do módulo</span><span class="sxs-lookup"><span data-stu-id="26460-116">Module properties</span></span>

| <span data-ttu-id="26460-117">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="26460-117">Property name</span></span>             | <span data-ttu-id="26460-118">Alíquota</span><span class="sxs-lookup"><span data-stu-id="26460-118">Value</span></span>                 | <span data-ttu-id="26460-119">descrição</span><span class="sxs-lookup"><span data-stu-id="26460-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="26460-120">Título</span><span class="sxs-lookup"><span data-stu-id="26460-120">Heading</span></span> | <span data-ttu-id="26460-121">Texto</span><span class="sxs-lookup"><span data-stu-id="26460-121">Text</span></span> | <span data-ttu-id="26460-122">O título do módulo.</span><span class="sxs-lookup"><span data-stu-id="26460-122">The heading for the module.</span></span> |
| <span data-ttu-id="26460-123">Opções de anotações: ícone padrão</span><span class="sxs-lookup"><span data-stu-id="26460-123">Pushpin options: Default icon</span></span> | <span data-ttu-id="26460-124">Imagem</span><span class="sxs-lookup"><span data-stu-id="26460-124">Image</span></span> | <span data-ttu-id="26460-125">A imagem do símbolo de anotação a ser usada para lojas mostradas em um mapa.</span><span class="sxs-lookup"><span data-stu-id="26460-125">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="26460-126">Opções de anotações: ícone Ativo</span><span class="sxs-lookup"><span data-stu-id="26460-126">Pushpin options: Active icon</span></span> | <span data-ttu-id="26460-127">Imagem</span><span class="sxs-lookup"><span data-stu-id="26460-127">Image</span></span> | <span data-ttu-id="26460-128">A imagem do símbolo de anotação a ser usada para uma loja selecionada em um mapa.</span><span class="sxs-lookup"><span data-stu-id="26460-128">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="26460-129">Opções de anotações: cor do ícone padrão</span><span class="sxs-lookup"><span data-stu-id="26460-129">Pushpin options: Default icon color</span></span> | <span data-ttu-id="26460-130">String de caracteres</span><span class="sxs-lookup"><span data-stu-id="26460-130">Character string</span></span> | <span data-ttu-id="26460-131">O texto ou valor hexadecimal da cor dos símbolos de anotações em um mapa.</span><span class="sxs-lookup"><span data-stu-id="26460-131">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="26460-132">Opções de anotações: cor do ícone Ativo</span><span class="sxs-lookup"><span data-stu-id="26460-132">Pushpin options: Active icon color</span></span> | <span data-ttu-id="26460-133">String de caracteres</span><span class="sxs-lookup"><span data-stu-id="26460-133">Character string</span></span> | <span data-ttu-id="26460-134">O texto ou valor hexadecimal da cor dos símbolos de anotações selecionados em um mapa.</span><span class="sxs-lookup"><span data-stu-id="26460-134">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="26460-135">Mostrar índice</span><span class="sxs-lookup"><span data-stu-id="26460-135">Show index</span></span> | <span data-ttu-id="26460-136">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="26460-136">**True** or **False**</span></span> | <span data-ttu-id="26460-137">Se esta propriedade for definida como **verdadeira**, cada símbolo de anotação que indicar uma loja mostrará um índice.</span><span class="sxs-lookup"><span data-stu-id="26460-137">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="26460-138">Esse índice corresponderá ao índice na exibição de lista mostrada pelo módulo seletor de loja.</span><span class="sxs-lookup"><span data-stu-id="26460-138">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="26460-139">Adicionar URLs de mapeamento permitido a diretivas de diretiva de segurança de conteúdo de um site</span><span class="sxs-lookup"><span data-stu-id="26460-139">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="26460-140">Para que o módulo de mapas interaja com o Bing Mapas, você deve garantir que as seguintes URLs de mapeamento sejam permitidas conforme a política de segurança de conteúdo (CSP) do site.</span><span class="sxs-lookup"><span data-stu-id="26460-140">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed per your site's content security policy (CSP).</span></span> <span data-ttu-id="26460-141">Essa configuração é executada na criação de site do Commerce, adicionando as URLs permitidas às várias diretivas da CSP do site (por exemplo, **img-src**).</span><span class="sxs-lookup"><span data-stu-id="26460-141">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="26460-142">Para obter mais informações, consulte [Política de segurança de conteúdo](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="26460-142">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="26460-143">Para a diretiva **connect-src**, adicione **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="26460-143">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="26460-144">Para a diretiva **img-src**, adicione **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="26460-144">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="26460-145">Para a diretiva **script-src**, adicione **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="26460-145">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="26460-146">Para a diretiva **script style-src**, adicione **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="26460-146">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="26460-147">Adicionar um módulo de mapa a uma página</span><span class="sxs-lookup"><span data-stu-id="26460-147">Add a map module to a page</span></span>

<span data-ttu-id="26460-148">Para obter informações detalhadas sobre como configurar um módulo de mapa em uma página, consulte [módulo do seletor de loja](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="26460-148">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="26460-149">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="26460-149">Additional resources</span></span>

[<span data-ttu-id="26460-150">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="26460-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="26460-151">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="26460-151">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="26460-152">Módulo de carrinho</span><span class="sxs-lookup"><span data-stu-id="26460-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="26460-153">Módulo de seletor de loja</span><span class="sxs-lookup"><span data-stu-id="26460-153">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="26460-154">Gerenciar o Bing Mapas da sua organização</span><span class="sxs-lookup"><span data-stu-id="26460-154">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="26460-155">Controle da Web V8 do Bing Maps</span><span class="sxs-lookup"><span data-stu-id="26460-155">Bing Maps V8 Web Control</span></span>](/bingmaps/v8-web-control/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]