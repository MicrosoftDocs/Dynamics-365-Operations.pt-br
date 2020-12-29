---
title: Módulo de seletor de site
description: Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.openlocfilehash: b4e5f715efcac7f883df99508d282db904be0d80
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665214"
---
# <a name="site-selector-module"></a><span data-ttu-id="f3107-103">Módulo de seletor de site</span><span class="sxs-lookup"><span data-stu-id="f3107-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f3107-104">Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3107-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f3107-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="f3107-105">Overview</span></span>

<span data-ttu-id="f3107-106">Quando uma empresa tem sites diferentes em mercados, regiões e locais, os usuários do site precisam de uma maneira fácil de alternar entre sites e selecionar o site de compras preferido.</span><span class="sxs-lookup"><span data-stu-id="f3107-106">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="f3107-107">Para acomodar esse cenário, o módulo de seletor de sites permite que os usuários naveguem por vários sites.</span><span class="sxs-lookup"><span data-stu-id="f3107-107">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="f3107-108">O módulo de seletor de sites deve ser configurado com a lista de sites (mercados, regiões ou localidades) em que os usuários do site podem navegar.</span><span class="sxs-lookup"><span data-stu-id="f3107-108">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="f3107-109">O módulo de seletor de sites está disponível na versão 10.0.14 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3107-109">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="f3107-110">A ilustração a seguir mostra um exemplo de um módulo de seletor de sites que é apresentado no cabeçalho de uma página do site.</span><span class="sxs-lookup"><span data-stu-id="f3107-110">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Exemplo de um módulo do seletor de site no cabeçalho de uma página do site](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="f3107-112">Propriedades do módulo de seletor de sites</span><span class="sxs-lookup"><span data-stu-id="f3107-112">Site selector module properties</span></span>

| <span data-ttu-id="f3107-113">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="f3107-113">Property name</span></span> | <span data-ttu-id="f3107-114">Alíquota</span><span class="sxs-lookup"><span data-stu-id="f3107-114">Value</span></span>                 | <span data-ttu-id="f3107-115">descrição</span><span class="sxs-lookup"><span data-stu-id="f3107-115">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="f3107-116">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="f3107-116">Heading</span></span>       | <span data-ttu-id="f3107-117">Texto</span><span class="sxs-lookup"><span data-stu-id="f3107-117">Text</span></span>                  | <span data-ttu-id="f3107-118">O título do módulo.</span><span class="sxs-lookup"><span data-stu-id="f3107-118">The heading for the module.</span></span> |
| <span data-ttu-id="f3107-119">Opções de site</span><span class="sxs-lookup"><span data-stu-id="f3107-119">Site options</span></span>  | <span data-ttu-id="f3107-120">Nome, Imagem, URL</span><span class="sxs-lookup"><span data-stu-id="f3107-120">Name, Image, URL</span></span>      | <span data-ttu-id="f3107-121">Essa propriedade especifica um nome, um link para a home page do site e uma imagem opcional a ser mostrada para cada site incluído no módulo.</span><span class="sxs-lookup"><span data-stu-id="f3107-121">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="f3107-122">A imagem pode ser um sinalizador ou alguma representação de mercado, região ou localidade.</span><span class="sxs-lookup"><span data-stu-id="f3107-122">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="f3107-123">Adicionar um módulo de seletor de sites a uma página</span><span class="sxs-lookup"><span data-stu-id="f3107-123">Add a site selector module to a page</span></span>

<span data-ttu-id="f3107-124">O módulo de seletor de sites pode ser adicionado ao [módulo Cabeçalho](author-header-module.md) sob o slot de seletor de sites.</span><span class="sxs-lookup"><span data-stu-id="f3107-124">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="f3107-125">Depois de adicionado, você pode definir as opções de cabeçalho e site do módulo.</span><span class="sxs-lookup"><span data-stu-id="f3107-125">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f3107-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f3107-126">Additional resources</span></span>

[<span data-ttu-id="f3107-127">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="f3107-127">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f3107-128">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="f3107-128">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="f3107-129">Módulo de trilha de navegação</span><span class="sxs-lookup"><span data-stu-id="f3107-129">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="f3107-130">Módulos de menu de navegação</span><span class="sxs-lookup"><span data-stu-id="f3107-130">Navigation menu module</span></span>](nav-menu-module.md)
