---
title: Módulo de resultados de pesquisa
description: Este tópico abrange os módulos de resultados de pesquisa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3761be29955458099d01f2271057884fc1fd6f28
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097169"
---
# <a name="search-results-module"></a><span data-ttu-id="f2376-103">Módulo de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="f2376-103">Search results module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="f2376-104">Este tópico abrange os módulos de resultados de pesquisa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2376-104">This topic covers search results modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f2376-105">O módulo de resultados da pesquisa retorna resultados de pesquisa de produtos e uma lista de refinadores aplicáveis para os produtos.</span><span class="sxs-lookup"><span data-stu-id="f2376-105">The search results module returns product search results and a list of applicable refiners for the products.</span></span> <span data-ttu-id="f2376-106">Os módulos de resultados de pesquisa em sites do Dynamics 365 Commerce podem ser usados para processar páginas para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="f2376-106">Search results modules on Dynamics 365 Commerce sites can be used to render pages for the following scenarios:</span></span>

- <span data-ttu-id="f2376-107">Resultados de pesquisa iniciados por uma pesquisa do usuário</span><span class="sxs-lookup"><span data-stu-id="f2376-107">Search results that are initiated by a user search</span></span>
- <span data-ttu-id="f2376-108">Resultados de pesquisa que mostram um conjunto específico de produtos, como "comprar visuais semelhantes"</span><span class="sxs-lookup"><span data-stu-id="f2376-108">Search results that show a specific set of products, such as "Shop similar looks"</span></span>
- <span data-ttu-id="f2376-109">Lista de produtos que pertencem uma categoria</span><span class="sxs-lookup"><span data-stu-id="f2376-109">Lists of products that belong to a category</span></span>

<span data-ttu-id="f2376-110">Para obter mais informações sobre as páginas de categoria e de resultados de pesquisa, consulte [Visão geral da página inicial de categorias e da página de resultados de pesquisa](category-search-page-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f2376-110">For more information about category and search results pages, see [Default category landing page and search results page overview](category-search-page-overview.md).</span></span>

<span data-ttu-id="f2376-111">A ilustração a seguir mostra um exemplo de uma página de resultados de pesquisa para uma categoria do site da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="f2376-111">The following illustration shows an example of a search results page for a category on the Fabrikam site.</span></span>

![Exemplo de uma página de resultados de pesquisa no site da Fabrikam](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a><span data-ttu-id="f2376-113">Propriedades do módulo de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="f2376-113">Search results module properties</span></span>

<span data-ttu-id="f2376-114">A tabela a seguir lista as propriedades dos módulos de resultados de pesquisa, juntamente com seus valores e descrições.</span><span class="sxs-lookup"><span data-stu-id="f2376-114">The following table lists the properties of search result modules, together with their values and descriptions.</span></span>

| <span data-ttu-id="f2376-115">Propriedade</span><span class="sxs-lookup"><span data-stu-id="f2376-115">Property</span></span> | <span data-ttu-id="f2376-116">Valores</span><span class="sxs-lookup"><span data-stu-id="f2376-116">Values</span></span> | <span data-ttu-id="f2376-117">descrição</span><span class="sxs-lookup"><span data-stu-id="f2376-117">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="f2376-118">Itens por página</span><span class="sxs-lookup"><span data-stu-id="f2376-118">Items per page</span></span> | <span data-ttu-id="f2376-119">Inteiro</span><span class="sxs-lookup"><span data-stu-id="f2376-119">Integer</span></span> | <span data-ttu-id="f2376-120">O número de itens que devem ser mostrados em cada página.</span><span class="sxs-lookup"><span data-stu-id="f2376-120">The number of items that should be shown on each page.</span></span> |
| <span data-ttu-id="f2376-121">Permitir voltar no PDP</span><span class="sxs-lookup"><span data-stu-id="f2376-121">Allow back on PDP</span></span> | <span data-ttu-id="f2376-122">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="f2376-122">**True** or **False**</span></span> | <span data-ttu-id="f2376-123">Se esta propriedade for definida como **Verdadeiro**, quando um usuário selecionar um produto na página de resultados de pesquisa, a navegação estrutural na página de detalhes do produto (PDP) que for aberta mostrará um link "Voltar para os resultados".</span><span class="sxs-lookup"><span data-stu-id="f2376-123">If this property is set to **True**, when a user selects a product on the search results page, the breadcrumb navigation on the product details page (PDP) that is opened will show a "Back to results" link.</span></span> |
| <span data-ttu-id="f2376-124">Expandir Refinadores</span><span class="sxs-lookup"><span data-stu-id="f2376-124">Expand Refiners</span></span> | <span data-ttu-id="f2376-125">**Todos**, **1**, **2**, **3** ou **4**</span><span class="sxs-lookup"><span data-stu-id="f2376-125">**All**, **1**, **2**, **3**, or **4**</span></span> | <span data-ttu-id="f2376-126">O número de refinadores principais que devem ser expandidos quando uma página é carregada.</span><span class="sxs-lookup"><span data-stu-id="f2376-126">The number of top refiners that should be expanded when a page is loaded.</span></span> <span data-ttu-id="f2376-127">Por exemplo, se esta propriedade for definida como **3**, os três primeiros refinadores na página serão expandidos.</span><span class="sxs-lookup"><span data-stu-id="f2376-127">For example, if this property is set to **3**, the first three refiners on the page will be expanded.</span></span> |
| <span data-ttu-id="f2376-128">Ocultar exibição da hierarquia de categoria</span><span class="sxs-lookup"><span data-stu-id="f2376-128">Hide category hierarchy display</span></span> | <span data-ttu-id="f2376-129">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="f2376-129">**True** or **False**</span></span> | <span data-ttu-id="f2376-130">Se esta propriedade for definida como **Verdadeiro**, a exibição da hierarquia de categoria na página ficará oculta.</span><span class="sxs-lookup"><span data-stu-id="f2376-130">If this property is set to **True**, the category hierarchy display on the page will be hidden.</span></span> <span data-ttu-id="f2376-131">Essa propriedade deve ser definida como **Verdadeiro** se você estiver usando o [módulo de trilha de navegação](add-breadcrumb.md) para mostrar a hierarquia de categoria.</span><span class="sxs-lookup"><span data-stu-id="f2376-131">This property should be set to **True** if you're using the [breadcrumb module](add-breadcrumb.md) to show the category hierarchy.</span></span>|
| <span data-ttu-id="f2376-132">Incluir atributos de produto nos resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="f2376-132">Include product attributes in search results</span></span> | <span data-ttu-id="f2376-133">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="f2376-133">**True** or **False**</span></span> | <span data-ttu-id="f2376-134">Se esta propriedade for definida como **Verdadeiro**, os atributos serão devolvidos para os produtos nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f2376-134">If this property is set to **True**, attributes will be returned for the products in the search results.</span></span> <span data-ttu-id="f2376-135">Embora esses atributos possam ser mostrados em um site do Commerce, é necessária uma extensão.</span><span class="sxs-lookup"><span data-stu-id="f2376-135">Although these attributes can be shown on a Commerce site, an extension is required.</span></span>|
| <span data-ttu-id="f2376-136">Mostrar preços de afiliação</span><span class="sxs-lookup"><span data-stu-id="f2376-136">Show affiliation prices</span></span> | <span data-ttu-id="f2376-137">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="f2376-137">**True** or **False**</span></span> | <span data-ttu-id="f2376-138">Se esta propriedade for definida como **Verdadeiro**, os preços de afiliação para produtos serão mostrados nos resultados da pesquisa quando um usuário conectado navegar na página.</span><span class="sxs-lookup"><span data-stu-id="f2376-138">If this property is set to **True**, affiliation prices for products will be shown in the search results when a signed-in user browses the page.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="f2376-139">No Dynamics 365 Commerce versão 10.0.16 e posterior, a configuração **Mostrar preços de afiliação** pode ser usada para mostrar os preços de afiliação na página.</span><span class="sxs-lookup"><span data-stu-id="f2376-139">In the Dynamics 365 Commerce 10.0.16 release and later, the **Show affiliation prices** configuration can be used to show affiliation prices on the page.</span></span>

## <a name="supported-modules"></a><span data-ttu-id="f2376-140">Módulos com suporte</span><span class="sxs-lookup"><span data-stu-id="f2376-140">Supported modules</span></span>

<span data-ttu-id="f2376-141">O módulo de resultados de pesquisa oferece suporte ao [módulo de exibição rápida](quick-view-module.md), que permite que os usuários vejam informações sobre o produto e adicionem itens ao carrinho usando uma página de resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f2376-141">The search results module supports the [quick view module](quick-view-module.md), which lets users view product information and add items to the cart from the search results page.</span></span>

## <a name="add-a-search-results-module-to-a-category-page"></a><span data-ttu-id="f2376-142">Adicionar um módulo de resultados de pesquisa a uma página de categoria</span><span class="sxs-lookup"><span data-stu-id="f2376-142">Add a search results module to a category page</span></span>

<span data-ttu-id="f2376-143">Para adicionar um módulo de resultados de pesquisa a uma página de categoria, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f2376-143">To add a search results module to a category page, follow these steps.</span></span>

1. <span data-ttu-id="f2376-144">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="f2376-144">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="f2376-145">Na caixa de diálogo **Novo modelo**, digite o nome **Resultados de pesquisa** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2376-145">In the **New template** dialog box, enter the name **Search results**, and then select **OK**.</span></span>
1. <span data-ttu-id="f2376-146">No slot **Corpo**, selecione as reticências (...) e, depois, **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f2376-146">In the **Body** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f2376-147">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Página Padrão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2376-147">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f2376-148">No slot **Principal** do módulo **Página padrão**, selecione as reticências (...) e, em seguida, **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f2376-148">In the **Main** slot of the **Default Page** module, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f2376-149">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2376-149">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f2376-150">No slot **Contêiner**, selecione as reticências (...) e, depois, **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f2376-150">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f2376-151">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Trilha de navegação** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2376-151">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f2376-152">No painel de propriedades **Trilha de navegação**, digite o valor **1** para **Mínimo ocorrer**.</span><span class="sxs-lookup"><span data-stu-id="f2376-152">In the **Breadcrumb** properties pane, enter the value **1** for **Min Occurs**.</span></span>
1. <span data-ttu-id="f2376-153">No slot **Contêiner**, selecione as reticências (...) e, depois, **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f2376-153">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f2376-154">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Resultados de pesquisa** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2376-154">In the **Add Module** dialog box, select the **Search results** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f2376-155">No painel **Propriedades de resultados da pesquisa**, digite o valor **1** para **Mínimo ocorrer** e, em seguida, defina outras propriedades necessárias para o módulo de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f2376-155">In the **Search results** properties pane, enter the value **1** for **Min Occurs**, and then set any other required properties for the search results module.</span></span> <span data-ttu-id="f2376-156">Ao definir essas propriedades no modelo, você garante que todas as personalizações em uma página de categoria específica incluam automaticamente essas configurações.</span><span class="sxs-lookup"><span data-stu-id="f2376-156">By setting these properties in the template, you ensure that any customizations to a specific category page will automatically include these settings.</span></span>
1. <span data-ttu-id="f2376-157">Selecione **Concluir edição** e depois selecione **Publicar** para publicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="f2376-157">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>
1. <span data-ttu-id="f2376-158">Vá para **Páginas** e selecione **Novo** para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="f2376-158">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="f2376-159">Na caixa de diálogo **Escolher um modelo**, selecione o modelo **Resultados de pesquisa** que você criou, digite **Página da categoria** para **Nome da página** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2376-159">In the **Choose a template** dialog box, select the **Search results** template that you created, enter **Category page** for **Page name**, and then select **OK**.</span></span> <span data-ttu-id="f2376-160">Como todos os valores são definidos no modelo, a página está pronta para ser publicada.</span><span class="sxs-lookup"><span data-stu-id="f2376-160">Because all the values are set in the template, the page is ready to be published.</span></span>
1. <span data-ttu-id="f2376-161">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="f2376-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f2376-162">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f2376-162">Additional resources</span></span>

[<span data-ttu-id="f2376-163">Visão geral da página de aterrissagem da categoria padrão e da página de resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="f2376-163">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="f2376-164">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="f2376-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f2376-165">Módulo de exibição rápida</span><span class="sxs-lookup"><span data-stu-id="f2376-165">Quick view module</span></span>](quick-view-module.md)