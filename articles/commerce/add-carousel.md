---
title: Módulo de carrossel
description: Este tópico abrange os módulos de carrossel e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785228"
---
# <a name="carousel-module"></a><span data-ttu-id="b0744-103">Módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="b0744-103">Carousel module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="b0744-104">Este tópico abrange os módulos de carrossel e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b0744-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b0744-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="b0744-105">Overview</span></span>

<span data-ttu-id="b0744-106">Um módulo de carrossel é usado para colocar vários itens promocionais em um carrossel que os clientes possam navegar.</span><span class="sxs-lookup"><span data-stu-id="b0744-106">A carousel module is used to put multiple promotional items in a carousel that customers can browse.</span></span> <span data-ttu-id="b0744-107">É um módulo de contêiner especial que hospeda outros módulos.</span><span class="sxs-lookup"><span data-stu-id="b0744-107">It's a special container module that hosts other modules.</span></span> <span data-ttu-id="b0744-108">Por exemplo, um varejista pode usar um módulo de carrossel em uma home page para exibir vários novos produtos ou promoções.</span><span class="sxs-lookup"><span data-stu-id="b0744-108">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="b0744-109">Você pode adicionar módulos de hero e recurso dentro de um módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="b0744-109">You can add hero and feature modules inside a carousel module.</span></span> <span data-ttu-id="b0744-110">As propriedades do módulo de carrossel definem como esses módulos são renderizados.</span><span class="sxs-lookup"><span data-stu-id="b0744-110">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="b0744-111">Exemplos de módulos de carrossel no comércio online</span><span class="sxs-lookup"><span data-stu-id="b0744-111">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="b0744-112">Um carrossel que possui vários módulos promocionais pode ser usado em uma home page.</span><span class="sxs-lookup"><span data-stu-id="b0744-112">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="b0744-113">Um carrossel que possui vários módulos promocionais pode ser usado em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="b0744-113">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="b0744-114">Um carrossel pode ser usado em qualquer página de marketing para promover várias promoções ou produtos.</span><span class="sxs-lookup"><span data-stu-id="b0744-114">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="b0744-115">Propriedades do módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="b0744-115">Carousel module properties</span></span>

| <span data-ttu-id="b0744-116">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="b0744-116">Property name</span></span>             | <span data-ttu-id="b0744-117">Alíquota</span><span class="sxs-lookup"><span data-stu-id="b0744-117">Value</span></span>                                | <span data-ttu-id="b0744-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="b0744-118">Description</span></span> |
|---------------------------|--------------------------------------|-------------|
| <span data-ttu-id="b0744-119">Reprodução automática</span><span class="sxs-lookup"><span data-stu-id="b0744-119">Autoplay</span></span>                  | <span data-ttu-id="b0744-120">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="b0744-120">**True** or **False**</span></span>                | <span data-ttu-id="b0744-121">Se o valor estiver definido como **Verdadeiro**, a transição entre os itens dentro no carrossel ocorrerá automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b0744-121">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="b0744-122">Se o valor estiver definido como **Falso**, nenhuma transição ocorrerá, a menos que o cliente use o teclado ou o mouse para passar de um item para o próximo.</span><span class="sxs-lookup"><span data-stu-id="b0744-122">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="b0744-123">Intervalo de transição de slides</span><span class="sxs-lookup"><span data-stu-id="b0744-123">Slide transition interval</span></span> | <span data-ttu-id="b0744-124">Um valor em segundos</span><span class="sxs-lookup"><span data-stu-id="b0744-124">A value in seconds</span></span>                   | <span data-ttu-id="b0744-125">O intervalo para transições entre itens.</span><span class="sxs-lookup"><span data-stu-id="b0744-125">The interval for transitions between items.</span></span> |
| <span data-ttu-id="b0744-126">Animação de transição</span><span class="sxs-lookup"><span data-stu-id="b0744-126">Transition animation</span></span>      | <span data-ttu-id="b0744-127">**Slide** ou **Fade**</span><span class="sxs-lookup"><span data-stu-id="b0744-127">**Slide** or **Fade**</span></span>                | <span data-ttu-id="b0744-128">O efeito de transição.</span><span class="sxs-lookup"><span data-stu-id="b0744-128">The transition effect.</span></span> |
| <span data-ttu-id="b0744-129">Largura</span><span class="sxs-lookup"><span data-stu-id="b0744-129">Width</span></span>                     | <span data-ttu-id="b0744-130">**Ajustar contêiner** ou **Preencher tela**</span><span class="sxs-lookup"><span data-stu-id="b0744-130">**Fit container** or **Fill screen**</span></span> | <span data-ttu-id="b0744-131">Se o valor estiver definido como **Ajustar contêiner**, os itens dentro do carrossel serão restritos à largura do carrossel.</span><span class="sxs-lookup"><span data-stu-id="b0744-131">If the value is set to **Fit container**, the items inside the carousel are restricted to the width of the carousel.</span></span> <span data-ttu-id="b0744-132">Se o valor estiver definido como **Preencher tela**, os itens não serão restritos à largura do carrossel, mas poderão entrar no modo de tela cheia.</span><span class="sxs-lookup"><span data-stu-id="b0744-132">If the value is set to **Fill screen**, the items aren't restricted to the carousel width but can go into full-screen mode.</span></span> <span data-ttu-id="b0744-133">É possível alterar o valor para obter o layout desejado.</span><span class="sxs-lookup"><span data-stu-id="b0744-133">You can change the value to achieve the desired layout.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="b0744-134">Adicionar um módulo de carrossel a uma página</span><span class="sxs-lookup"><span data-stu-id="b0744-134">Add a carousel module to a page</span></span>

<span data-ttu-id="b0744-135">Para adicionar um módulo de carrossel a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b0744-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b0744-136">Criar um modelo da página chamado **modelo de carrossel**.</span><span class="sxs-lookup"><span data-stu-id="b0744-136">Create a page template that is named **carousel template**.</span></span>
1. <span data-ttu-id="b0744-137">No slot **Principal** da página padrão, adicione um módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="b0744-137">In the **Main** slot of the default page, add a carousel module.</span></span>
1. <span data-ttu-id="b0744-138">Adicione um módulo de hero ao módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="b0744-138">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="b0744-139">Adicione um módulo de recurso ao módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="b0744-139">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="b0744-140">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="b0744-140">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="b0744-141">Use o modelo de carrossel que criou para criar uma página nomeada **página do carrossel**.</span><span class="sxs-lookup"><span data-stu-id="b0744-141">Use the carousel template that you just created to create a page that is named **carousel page**.</span></span>
1. <span data-ttu-id="b0744-142">No slot **Principal** da nova página, adicione um módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="b0744-142">In the **Main** slot of the new page, add a carousel module.</span></span>
1. <span data-ttu-id="b0744-143">Defina a propriedade **Largura** do módulo de carrossel como **Preencher tela**.</span><span class="sxs-lookup"><span data-stu-id="b0744-143">Set the **Width** property of the carousel module to **Fill screen**.</span></span> 
1. <span data-ttu-id="b0744-144">Defina a propriedade **Animação de transição** como **Slide**.</span><span class="sxs-lookup"><span data-stu-id="b0744-144">Set the **Transition animation** property to **Slide**.</span></span>
1. <span data-ttu-id="b0744-145">Adicione um módulo de hero ao módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="b0744-145">Add a hero module to the carousel module.</span></span>
1. <span data-ttu-id="b0744-146">No módulo de hero, adicione uma imagem e um cabeçalho e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b0744-146">In the hero module, add an image and a heading, and then select **Save**.</span></span>
1. <span data-ttu-id="b0744-147">Adicione um módulo de recurso ao módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="b0744-147">Add a feature module to the carousel module.</span></span>
1. <span data-ttu-id="b0744-148">No módulo de recurso, adicione uma imagem, um cabeçalho e um parágrafo de texto.</span><span class="sxs-lookup"><span data-stu-id="b0744-148">In the feature module, add an image, a heading, and a paragraph of text.</span></span>
1. <span data-ttu-id="b0744-149">Salve e exiba a página.</span><span class="sxs-lookup"><span data-stu-id="b0744-149">Save and preview the page.</span></span> <span data-ttu-id="b0744-150">A página deve mostrar um carrossel que possui dois módulos (um módulo de hero e um módulo de recurso).</span><span class="sxs-lookup"><span data-stu-id="b0744-150">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="b0744-151">Você pode alterar propriedades adicionais para os módulos de carrossel, hero e recurso, para obter o efeito desejado.</span><span class="sxs-lookup"><span data-stu-id="b0744-151">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="b0744-152">Insira a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="b0744-152">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b0744-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b0744-153">Additional resources</span></span>

[<span data-ttu-id="b0744-154">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="b0744-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b0744-155">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="b0744-155">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="b0744-156">Módulo de bloco de conteúdo sofisticado</span><span class="sxs-lookup"><span data-stu-id="b0744-156">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="b0744-157">Módulo de posicionamento de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b0744-157">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="b0744-158">Módulo de recurso</span><span class="sxs-lookup"><span data-stu-id="b0744-158">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="b0744-159">Módulo de hero</span><span class="sxs-lookup"><span data-stu-id="b0744-159">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="b0744-160">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="b0744-160">Video player module</span></span>](add-video-player.md)
