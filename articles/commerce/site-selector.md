---
title: Módulo de seletor de site
description: Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/20/2020
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
ms.openlocfilehash: 6e8eefe7afe385ca77eca6027638ff938e1356e3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791766"
---
# <a name="site-selector-module"></a><span data-ttu-id="a8172-103">Módulo de seletor de site</span><span class="sxs-lookup"><span data-stu-id="a8172-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a8172-104">Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a8172-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a8172-105">Quando uma empresa tem sites diferentes em mercados, regiões e locais, os usuários do site precisam de uma maneira fácil de alternar entre sites e selecionar o site de compras preferido.</span><span class="sxs-lookup"><span data-stu-id="a8172-105">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="a8172-106">Para acomodar esse cenário, o módulo de seletor de sites permite que os usuários naveguem por vários sites.</span><span class="sxs-lookup"><span data-stu-id="a8172-106">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="a8172-107">O módulo de seletor de sites deve ser configurado com a lista de sites (mercados, regiões ou localidades) em que os usuários do site podem navegar.</span><span class="sxs-lookup"><span data-stu-id="a8172-107">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="a8172-108">O módulo de seletor de sites está disponível na versão 10.0.14 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a8172-108">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="a8172-109">A ilustração a seguir mostra um exemplo de um módulo de seletor de sites que é apresentado no cabeçalho de uma página do site.</span><span class="sxs-lookup"><span data-stu-id="a8172-109">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Exemplo de um módulo do seletor de site no cabeçalho de uma página do site](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="a8172-111">Propriedades do módulo de seletor de sites</span><span class="sxs-lookup"><span data-stu-id="a8172-111">Site selector module properties</span></span>

| <span data-ttu-id="a8172-112">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="a8172-112">Property name</span></span> | <span data-ttu-id="a8172-113">Alíquota</span><span class="sxs-lookup"><span data-stu-id="a8172-113">Value</span></span>                 | <span data-ttu-id="a8172-114">descrição</span><span class="sxs-lookup"><span data-stu-id="a8172-114">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="a8172-115">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="a8172-115">Heading</span></span>       | <span data-ttu-id="a8172-116">Texto</span><span class="sxs-lookup"><span data-stu-id="a8172-116">Text</span></span>                  | <span data-ttu-id="a8172-117">O título do módulo.</span><span class="sxs-lookup"><span data-stu-id="a8172-117">The heading for the module.</span></span> |
| <span data-ttu-id="a8172-118">Opções de site</span><span class="sxs-lookup"><span data-stu-id="a8172-118">Site options</span></span>  | <span data-ttu-id="a8172-119">Nome, Imagem, URL</span><span class="sxs-lookup"><span data-stu-id="a8172-119">Name, Image, URL</span></span>      | <span data-ttu-id="a8172-120">Essa propriedade especifica um nome, um link para a home page do site e uma imagem opcional a ser mostrada para cada site incluído no módulo.</span><span class="sxs-lookup"><span data-stu-id="a8172-120">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="a8172-121">A imagem pode ser um sinalizador ou alguma representação de mercado, região ou localidade.</span><span class="sxs-lookup"><span data-stu-id="a8172-121">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="a8172-122">Adicionar um módulo de seletor de sites a uma página</span><span class="sxs-lookup"><span data-stu-id="a8172-122">Add a site selector module to a page</span></span>

<span data-ttu-id="a8172-123">O módulo de seletor de sites pode ser adicionado ao [módulo Cabeçalho](author-header-module.md) sob o slot de seletor de sites.</span><span class="sxs-lookup"><span data-stu-id="a8172-123">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="a8172-124">Depois de adicionado, você pode definir as opções de cabeçalho e site do módulo.</span><span class="sxs-lookup"><span data-stu-id="a8172-124">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8172-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a8172-125">Additional resources</span></span>

[<span data-ttu-id="a8172-126">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="a8172-126">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a8172-127">Módulo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="a8172-127">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="a8172-128">Módulo de trilha de navegação</span><span class="sxs-lookup"><span data-stu-id="a8172-128">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="a8172-129">Módulos de menu de navegação</span><span class="sxs-lookup"><span data-stu-id="a8172-129">Navigation menu module</span></span>](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]