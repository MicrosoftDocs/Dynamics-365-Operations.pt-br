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
ms.openlocfilehash: bd54695f54b501631f916328c05bfd47e538d50d
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055821"
---
# <a name="site-selector-module"></a><span data-ttu-id="8b635-103">Módulo de seletor de site</span><span class="sxs-lookup"><span data-stu-id="8b635-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="8b635-104">Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8b635-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8b635-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="8b635-105">Overview</span></span>

<span data-ttu-id="8b635-106">Quando uma empresa tem sites diferentes em mercados, regiões e locais, os usuários do site precisam de uma maneira fácil de alternar entre sites e selecionar o site de compras preferido.</span><span class="sxs-lookup"><span data-stu-id="8b635-106">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="8b635-107">Para acomodar esse cenário, o módulo de seletor de sites permite que os usuários naveguem por vários sites.</span><span class="sxs-lookup"><span data-stu-id="8b635-107">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="8b635-108">O módulo de seletor de sites deve ser configurado com a lista de sites (mercados, regiões ou localidades) em que os usuários do site podem navegar.</span><span class="sxs-lookup"><span data-stu-id="8b635-108">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="8b635-109">O módulo de seletor de sites está disponível na versão 10.0.14 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8b635-109">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="8b635-110">A ilustração a seguir mostra um exemplo de um módulo de seletor de sites que é apresentado no cabeçalho de uma página do site.</span><span class="sxs-lookup"><span data-stu-id="8b635-110">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Exemplo de um módulo do seletor de site no cabeçalho de uma página do site](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="8b635-112">Propriedades do módulo de seletor de sites</span><span class="sxs-lookup"><span data-stu-id="8b635-112">Site selector module properties</span></span>

| <span data-ttu-id="8b635-113">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="8b635-113">Property name</span></span> | <span data-ttu-id="8b635-114">Alíquota</span><span class="sxs-lookup"><span data-stu-id="8b635-114">Value</span></span>                 | <span data-ttu-id="8b635-115">descrição</span><span class="sxs-lookup"><span data-stu-id="8b635-115">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="8b635-116">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="8b635-116">Heading</span></span>       | <span data-ttu-id="8b635-117">Texto</span><span class="sxs-lookup"><span data-stu-id="8b635-117">Text</span></span>                  | <span data-ttu-id="8b635-118">O título do módulo.</span><span class="sxs-lookup"><span data-stu-id="8b635-118">The heading for the module.</span></span> |
| <span data-ttu-id="8b635-119">Opções de site</span><span class="sxs-lookup"><span data-stu-id="8b635-119">Site options</span></span>  | <span data-ttu-id="8b635-120">Nome, Imagem, URL</span><span class="sxs-lookup"><span data-stu-id="8b635-120">Name, Image, URL</span></span>      | <span data-ttu-id="8b635-121">Essa propriedade especifica um nome, um link para a home page do site e uma imagem opcional a ser mostrada para cada site incluído no módulo.</span><span class="sxs-lookup"><span data-stu-id="8b635-121">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="8b635-122">A imagem pode ser um sinalizador ou alguma representação de mercado, região ou localidade.</span><span class="sxs-lookup"><span data-stu-id="8b635-122">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="8b635-123">Adicionar um módulo de seletor de sites a uma página</span><span class="sxs-lookup"><span data-stu-id="8b635-123">Add a site selector module to a page</span></span>

<span data-ttu-id="8b635-124">O módulo de seletor de sites pode ser adicionado ao [módulo Cabeçalho](author-header-module.md) sob o slot de seletor de sites.</span><span class="sxs-lookup"><span data-stu-id="8b635-124">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="8b635-125">Depois de adicionado, você pode definir as opções de cabeçalho e site do módulo.</span><span class="sxs-lookup"><span data-stu-id="8b635-125">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8b635-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8b635-126">Additional resources</span></span>

[<span data-ttu-id="8b635-127">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="8b635-127">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8b635-128">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="8b635-128">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="8b635-129">Módulo de trilha de navegação</span><span class="sxs-lookup"><span data-stu-id="8b635-129">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="8b635-130">Módulos de menu de navegação</span><span class="sxs-lookup"><span data-stu-id="8b635-130">Navigation menu module</span></span>](nav-menu-module.md)
