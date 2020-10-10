---
title: Módulo do menu de navegação
description: Este tópico abrange os módulos do menu de navegação e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: 91239bd1db3f5819b7ad8d45ccfd8ab0d88b1b41
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817865"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="50c97-103">Módulo do menu de navegação</span><span class="sxs-lookup"><span data-stu-id="50c97-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="50c97-104">Este tópico abrange os módulos do menu de navegação e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="50c97-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="50c97-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="50c97-105">Overview</span></span>

<span data-ttu-id="50c97-106">A finalidade principal dos módulos do menu de navegação é permitir que os usuários do site naveguem por produtos e páginas do site de acordo com a hierarquia de navegação de canal definida na matriz do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="50c97-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="50c97-107">Os itens configurados em um módulo de menu de navegação aparecem como uma navegação de cabeçalho de site.</span><span class="sxs-lookup"><span data-stu-id="50c97-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="50c97-108">Os módulos do menu de navegação também dão suporte a itens de menu estático que se vinculam a outras páginas em um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="50c97-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="50c97-109">O módulo do menu de navegação pode ser adicionado ao módulo de cabeçalho de uma página.</span><span class="sxs-lookup"><span data-stu-id="50c97-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="50c97-110">Por padrão, no tema Fabrikam, o menu de navegação mostra dois níveis.</span><span class="sxs-lookup"><span data-stu-id="50c97-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="50c97-111">Por padrão, no tema Início, o menu de navegação mostra três níveis.</span><span class="sxs-lookup"><span data-stu-id="50c97-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="50c97-112">Para alterar para o número de níveis, é necessário ter uma extensão de exibição no tema.</span><span class="sxs-lookup"><span data-stu-id="50c97-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="50c97-113">A ilustração a seguir mostra um exemplo de um menu de navegação para o site da Fabrikam com dois níveis de hierarquia de categoria e alguns itens de menu estático.</span><span class="sxs-lookup"><span data-stu-id="50c97-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="50c97-114">![Exemplo de um módulo menu de navegação](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="50c97-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="50c97-115">Propriedades do módulo do menu de navegação</span><span class="sxs-lookup"><span data-stu-id="50c97-115">Navigation menu module properties</span></span>

| <span data-ttu-id="50c97-116">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="50c97-116">Property name</span></span>             | <span data-ttu-id="50c97-117">Alíquota</span><span class="sxs-lookup"><span data-stu-id="50c97-117">Value</span></span>                 | <span data-ttu-id="50c97-118">descrição</span><span class="sxs-lookup"><span data-stu-id="50c97-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="50c97-119">Origem</span><span class="sxs-lookup"><span data-stu-id="50c97-119">Source</span></span>                  | <span data-ttu-id="50c97-120">**Varejo**, **Criação manual**, **Varejo e criação manual**</span><span class="sxs-lookup"><span data-stu-id="50c97-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="50c97-121">O valor **Varejo** permite que a hierarquia de navegação de canal da matriz do Commerce seja exibida no menu de navegação.</span><span class="sxs-lookup"><span data-stu-id="50c97-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="50c97-122">O valor **Criação manual** permite que os itens de menu estático sejam organizados.</span><span class="sxs-lookup"><span data-stu-id="50c97-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="50c97-123">O valor **Criação manual e de varejo** permite uma combinação de ambos.</span><span class="sxs-lookup"><span data-stu-id="50c97-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="50c97-124">Mostrar imagens da categoria</span><span class="sxs-lookup"><span data-stu-id="50c97-124">Show category images</span></span> | <span data-ttu-id="50c97-125">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="50c97-125">**True** or **False**</span></span>    | <span data-ttu-id="50c97-126">Quando habilitada, essa propriedade exibe imagens de categoria no menu de navegação, conforme definido na matriz do Commerce para cada categoria.</span><span class="sxs-lookup"><span data-stu-id="50c97-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="50c97-127">Adicionado ao Commerce Release 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="50c97-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="50c97-128">Item de menu estático</span><span class="sxs-lookup"><span data-stu-id="50c97-128">Static menu item</span></span>| <span data-ttu-id="50c97-129">Matriz de valores</span><span class="sxs-lookup"><span data-stu-id="50c97-129">Array of values</span></span>| <span data-ttu-id="50c97-130">Os itens de menu estático que associam um nome de item de menu a um link para uma página de site estática.</span><span class="sxs-lookup"><span data-stu-id="50c97-130">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="50c97-131">Você pode criar itens de menu abaixo de outros itens de menu.</span><span class="sxs-lookup"><span data-stu-id="50c97-131">You can create menu items below other menu items.</span></span> <span data-ttu-id="50c97-132">Por padrão, os menus estáticos aparecem no nível raiz e serão acrescentados à hierarquia de navegação de canal, caso exista.</span><span class="sxs-lookup"><span data-stu-id="50c97-132">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |

<span data-ttu-id="50c97-133">A ilustração a seguir mostra um exemplo de uma imagem de categoria exibida no menu de navegação do site da Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="50c97-133">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="50c97-134">![Exemplo de um módulo de meu de navegação com imagens de categoria](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="50c97-134">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="50c97-135">Adicionar um módulo de menu de navegação a um módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="50c97-135">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="50c97-136">Para obter detalhes sobre como adicionar um módulo de menu de navegação a um módulo de cabeçalho, consulte [Módulo de cabeçalho](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="50c97-136">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50c97-137">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="50c97-137">Additional resources</span></span>

[<span data-ttu-id="50c97-138">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="50c97-138">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="50c97-139">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="50c97-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="50c97-140">Compatível com cookies</span><span class="sxs-lookup"><span data-stu-id="50c97-140">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="50c97-141">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="50c97-141">Header module</span></span>](author-header-module.md)
