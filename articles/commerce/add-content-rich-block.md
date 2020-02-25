---
title: Módulo de bloco de texto
description: Este tópico abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025588"
---
# <a name="text-block-module"></a><span data-ttu-id="5212e-103">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="5212e-103">Text block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5212e-104">Este tópico abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5212e-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5212e-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="5212e-105">Overview</span></span>

<span data-ttu-id="5212e-106">Um módulo de bloco de texto é um módulo usado para adicionar conteúdo textual.</span><span class="sxs-lookup"><span data-stu-id="5212e-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="5212e-107">Esse conteúdo pode ser informativo ou promocional.</span><span class="sxs-lookup"><span data-stu-id="5212e-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="5212e-108">Os módulos de bloco de texto são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="5212e-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="5212e-109">São módulos autônomos que não dependem do contexto da página ou de outros módulos.</span><span class="sxs-lookup"><span data-stu-id="5212e-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="5212e-110">Exemplos de módulos de bloco de texto no comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="5212e-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="5212e-111">Os módulos de bloco de texto podem ser usados das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="5212e-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="5212e-112">Para exibir os recursos do produto em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="5212e-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="5212e-113">Para fins informativos em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="5212e-113">For informational purposes on any page.</span></span> <span data-ttu-id="5212e-114">Por exemplo, eles podem explicar os benefícios dos programas de fidelidade, descrever as políticas de remessa e devolução, responder a perguntas frequentes ou fornecer conteúdo "sobre nós".</span><span class="sxs-lookup"><span data-stu-id="5212e-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="5212e-115">Para adicionar mensagens personalizadas em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="5212e-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="5212e-116">(por exemplo, "Frete grátis para pedidos acima de US$ 50").</span><span class="sxs-lookup"><span data-stu-id="5212e-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="5212e-117">Para avisos de isenção de responsabilidade e detalhes de contato nas páginas de detalhes do produto, páginas de carrinho, páginas de finalização de compra e outras páginas (por exemplo, "Remessas e devoluções estão sujeitas às políticas da loja").</span><span class="sxs-lookup"><span data-stu-id="5212e-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="text-block-module-properties"></a><span data-ttu-id="5212e-118">Propriedades do módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="5212e-118">Text block module properties</span></span>

| <span data-ttu-id="5212e-119">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="5212e-119">Property name</span></span>     | <span data-ttu-id="5212e-120">Value</span><span class="sxs-lookup"><span data-stu-id="5212e-120">Value</span></span>                                            | <span data-ttu-id="5212e-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="5212e-121">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="5212e-122">Rich text</span><span class="sxs-lookup"><span data-stu-id="5212e-122">Rich text</span></span>         | <span data-ttu-id="5212e-123">Rich text</span><span class="sxs-lookup"><span data-stu-id="5212e-123">Rich text</span></span>                                        | <span data-ttu-id="5212e-124">Texto do parágrafo.</span><span class="sxs-lookup"><span data-stu-id="5212e-124">Paragraph text.</span></span> <span data-ttu-id="5212e-125">Há suporte para alguns recursos básicos de rich text, como negrito, sublinhado e itálico.</span><span class="sxs-lookup"><span data-stu-id="5212e-125">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="5212e-126">Nome da classe personalizada</span><span class="sxs-lookup"><span data-stu-id="5212e-126">Custom class name</span></span> | <span data-ttu-id="5212e-127">Um nome de classe de folhas de estilo em cascata (CSS)</span><span class="sxs-lookup"><span data-stu-id="5212e-127">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="5212e-128">O nome de uma classe CSS personalizada que um desenvolvedor fornece para formatar esse módulo.</span><span class="sxs-lookup"><span data-stu-id="5212e-128">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="5212e-129">O nome da classe deve ser definido no pacote de tema.</span><span class="sxs-lookup"><span data-stu-id="5212e-129">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="5212e-130">Tamanho da fonte</span><span class="sxs-lookup"><span data-stu-id="5212e-130">Font size</span></span>         | <span data-ttu-id="5212e-131">**Pequeno**, **Médio**, **Grande** ou **Extra-grande**</span><span class="sxs-lookup"><span data-stu-id="5212e-131">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="5212e-132">O tamanho da fonte do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5212e-132">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="5212e-133">Adicionar um módulo de bloco de texto a uma página</span><span class="sxs-lookup"><span data-stu-id="5212e-133">Add a text block module to a page</span></span>

<span data-ttu-id="5212e-134">Para adicionar um módulo de bloco de texto a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="5212e-134">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="5212e-135">Criar um modelo da página chamado **Modelo de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="5212e-135">Create a page template that is named **Content template**.</span></span> 
1. <span data-ttu-id="5212e-136">No slot **Corpo**, adicione um módulo **Página padrão**.</span><span class="sxs-lookup"><span data-stu-id="5212e-136">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="5212e-137">Termine de editar o modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="5212e-137">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="5212e-138">Use o modelo de conteúdo que criou para criar uma página nomeada **Página do conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="5212e-138">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="5212e-139">No slot **Principal** da nova página, adicione um módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="5212e-139">In the **Main** slot of the new page, add a container module.</span></span>
1. <span data-ttu-id="5212e-140">No painel de propriedades do módulo de contêiner, defina a propriedade **Largura** como **Preencher contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5212e-140">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="5212e-141">Adicione um módulo de bloco de texto ao módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="5212e-141">Add a text block module to the container module.</span></span> 
1. <span data-ttu-id="5212e-142">No painel de propriedades do módulo de bloco de texto, adicione um texto ao campo **Texto rico**.</span><span class="sxs-lookup"><span data-stu-id="5212e-142">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="5212e-143">Termine de editar a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="5212e-143">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5212e-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5212e-144">Additional resources</span></span>

[<span data-ttu-id="5212e-145">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="5212e-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="5212e-146">Módulo de faixa promocional</span><span class="sxs-lookup"><span data-stu-id="5212e-146">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="5212e-147">Módulo do carrossel</span><span class="sxs-lookup"><span data-stu-id="5212e-147">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="5212e-148">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="5212e-148">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="5212e-149">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="5212e-149">Video player module</span></span>](add-video-player.md)

