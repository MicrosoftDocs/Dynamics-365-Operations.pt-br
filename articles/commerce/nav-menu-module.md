---
title: Módulo do menu de navegação
description: Este tópico abrange os módulos do menu de navegação e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: eee3523be26369aecdb36c0143a6ee3dab4b7966
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4410325"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="db35d-103">Módulo do menu de navegação</span><span class="sxs-lookup"><span data-stu-id="db35d-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="db35d-104">Este tópico abrange os módulos do menu de navegação e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="db35d-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="db35d-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="db35d-105">Overview</span></span>

<span data-ttu-id="db35d-106">A finalidade principal dos módulos do menu de navegação é permitir que os usuários do site naveguem por produtos e páginas do site de acordo com a hierarquia de navegação de canal definida na matriz do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="db35d-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="db35d-107">Os itens configurados em um módulo de menu de navegação aparecem como uma navegação de cabeçalho de site.</span><span class="sxs-lookup"><span data-stu-id="db35d-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="db35d-108">Os módulos do menu de navegação também dão suporte a itens de menu estático que se vinculam a outras páginas em um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="db35d-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="db35d-109">O módulo do menu de navegação pode ser adicionado ao módulo de cabeçalho de uma página.</span><span class="sxs-lookup"><span data-stu-id="db35d-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="db35d-110">Por padrão, no tema Fabrikam, o menu de navegação mostra dois níveis.</span><span class="sxs-lookup"><span data-stu-id="db35d-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="db35d-111">Por padrão, no tema Início, o menu de navegação mostra três níveis.</span><span class="sxs-lookup"><span data-stu-id="db35d-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="db35d-112">Para alterar para o número de níveis, é necessário ter uma extensão de exibição no tema.</span><span class="sxs-lookup"><span data-stu-id="db35d-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="db35d-113">A ilustração a seguir mostra um exemplo de um menu de navegação para o site da Fabrikam com dois níveis de hierarquia de categoria e alguns itens de menu estático.</span><span class="sxs-lookup"><span data-stu-id="db35d-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="db35d-114">![Exemplo de um módulo menu de navegação](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="db35d-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="db35d-115">Propriedades do módulo do menu de navegação</span><span class="sxs-lookup"><span data-stu-id="db35d-115">Navigation menu module properties</span></span>

| <span data-ttu-id="db35d-116">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="db35d-116">Property name</span></span>             | <span data-ttu-id="db35d-117">Alíquota</span><span class="sxs-lookup"><span data-stu-id="db35d-117">Value</span></span>                 | <span data-ttu-id="db35d-118">descrição</span><span class="sxs-lookup"><span data-stu-id="db35d-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="db35d-119">Origem</span><span class="sxs-lookup"><span data-stu-id="db35d-119">Source</span></span>                  | <span data-ttu-id="db35d-120">**Varejo**, **Criação manual**, **Varejo e criação manual**</span><span class="sxs-lookup"><span data-stu-id="db35d-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="db35d-121">O valor **Varejo** permite que a hierarquia de navegação de canal da matriz do Commerce seja exibida no menu de navegação.</span><span class="sxs-lookup"><span data-stu-id="db35d-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="db35d-122">O valor **Criação manual** permite que os itens de menu estático sejam organizados.</span><span class="sxs-lookup"><span data-stu-id="db35d-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="db35d-123">O valor **Criação manual e de varejo** permite uma combinação de ambos.</span><span class="sxs-lookup"><span data-stu-id="db35d-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="db35d-124">Mostrar imagens da categoria</span><span class="sxs-lookup"><span data-stu-id="db35d-124">Show category images</span></span> | <span data-ttu-id="db35d-125">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="db35d-125">**True** or **False**</span></span>    | <span data-ttu-id="db35d-126">Quando habilitada, essa propriedade exibe imagens de categoria no menu de navegação, conforme definido na matriz do Commerce para cada categoria.</span><span class="sxs-lookup"><span data-stu-id="db35d-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="db35d-127">Adicionado ao Commerce Release 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="db35d-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="db35d-128">Habilitar menu de navegação de vários níveis</span><span class="sxs-lookup"><span data-stu-id="db35d-128">Enable multi-level navigation menu</span></span> | <span data-ttu-id="db35d-129">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="db35d-129">**True** or **False**</span></span> | <span data-ttu-id="db35d-130">Quando esta propriedade estiver habilitada, o menu de navegação poderá mostrar vários níveis da hierarquia de navegação.</span><span class="sxs-lookup"><span data-stu-id="db35d-130">When this property is enabled, the navigation menu can show multiple levels of the navigation hierarchy.</span></span> <span data-ttu-id="db35d-131">Esse recurso só está disponível na versão 10.0.15 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="db35d-131">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="db35d-132">Número de níveis</span><span class="sxs-lookup"><span data-stu-id="db35d-132">Number of levels</span></span> | <span data-ttu-id="db35d-133">inteiro</span><span class="sxs-lookup"><span data-stu-id="db35d-133">integer</span></span> | <span data-ttu-id="db35d-134">Essa propriedade define os números de níveis que deverão ser mostrados se a propriedade **Habilitar menu de navegação de vários níveis** estiver definida como **Verdadeira**.</span><span class="sxs-lookup"><span data-stu-id="db35d-134">This property defines the numbers of levels that should be shown if the **Enable multilevel navigation menu** property is set to **True**.</span></span> |
| <span data-ttu-id="db35d-135">Item de menu estático</span><span class="sxs-lookup"><span data-stu-id="db35d-135">Static menu item</span></span>| <span data-ttu-id="db35d-136">Matriz de valores</span><span class="sxs-lookup"><span data-stu-id="db35d-136">Array of values</span></span>| <span data-ttu-id="db35d-137">Os itens de menu estático que associam um nome de item de menu a um link para uma página de site estática.</span><span class="sxs-lookup"><span data-stu-id="db35d-137">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="db35d-138">Você pode criar itens de menu abaixo de outros itens de menu.</span><span class="sxs-lookup"><span data-stu-id="db35d-138">You can create menu items below other menu items.</span></span> <span data-ttu-id="db35d-139">Por padrão, os menus estáticos aparecem no nível raiz e serão acrescentados à hierarquia de navegação de canal, caso exista.</span><span class="sxs-lookup"><span data-stu-id="db35d-139">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |
| <span data-ttu-id="db35d-140">Mostrar menu raiz</span><span class="sxs-lookup"><span data-stu-id="db35d-140">Show root menu</span></span> | <span data-ttu-id="db35d-141">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="db35d-141">**True** or **False**</span></span> | <span data-ttu-id="db35d-142">Quando essa propriedade estiver habilitada, o menu de navegação poderá ser definido em uma raiz personalizada (por exemplo, **Compre agora**).</span><span class="sxs-lookup"><span data-stu-id="db35d-142">When this property is enabled, the navigation menu can be defined under a custom root (for example, **Shop now**).</span></span> <span data-ttu-id="db35d-143">Esse recurso só está disponível na versão 10.0.15 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="db35d-143">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="db35d-144">Menu raiz</span><span class="sxs-lookup"><span data-stu-id="db35d-144">Root menu</span></span> | <span data-ttu-id="db35d-145">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="db35d-145">string</span></span> | <span data-ttu-id="db35d-146">Essa propriedade pode ser usada para definir texto para uma raiz personalizada se a propriedade **Mostrar menu raiz** estiver definida como **Verdadeira**.</span><span class="sxs-lookup"><span data-stu-id="db35d-146">This property can be used to define text for a custom root if the **Show root menu** property is set to **True**.</span></span> |

<span data-ttu-id="db35d-147">A ilustração a seguir mostra um exemplo de uma imagem de categoria exibida no menu de navegação do site da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="db35d-147">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="db35d-148">![Exemplo de um módulo de meu de navegação com imagens de categoria](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="db35d-148">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="db35d-149">Adicionar um módulo de menu de navegação a um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="db35d-149">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="db35d-150">Para obter detalhes sobre como adicionar um módulo de menu de navegação a um módulo de cabeçalho, consulte [Módulo de cabeçalho](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="db35d-150">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="db35d-151">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="db35d-151">Additional resources</span></span>

[<span data-ttu-id="db35d-152">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="db35d-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="db35d-153">Módulo de trilha de navegação</span><span class="sxs-lookup"><span data-stu-id="db35d-153">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="db35d-154">Módulo de seletor de site</span><span class="sxs-lookup"><span data-stu-id="db35d-154">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="db35d-155">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="db35d-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="db35d-156">Compatível com cookies</span><span class="sxs-lookup"><span data-stu-id="db35d-156">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="db35d-157">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="db35d-157">Header module</span></span>](author-header-module.md)
