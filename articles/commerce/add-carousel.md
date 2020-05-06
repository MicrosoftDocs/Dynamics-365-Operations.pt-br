---
title: Módulo de carrossel
description: Este tópico abrange os módulos de carrossel e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: f399e4c5618b65b781fdd3ec835e841614579313
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269719"
---
# <a name="carousel-module"></a><span data-ttu-id="fab6f-103">Módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="fab6f-103">Carousel module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="fab6f-104">Este tópico abrange os módulos de carrossel e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fab6f-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fab6f-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="fab6f-105">Overview</span></span>

<span data-ttu-id="fab6f-106">Um módulo de carrossel é usado para colocar vários itens promocionais (incluindo imagens sofisticadas) em uma faixa de carrossel rotatória na qual os clientes possam navegar.</span><span class="sxs-lookup"><span data-stu-id="fab6f-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="fab6f-107">Por exemplo, um varejista pode usar um módulo de carrossel em uma home page para exibir vários novos produtos ou promoções.</span><span class="sxs-lookup"><span data-stu-id="fab6f-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="fab6f-108">Você pode adicionar módulos de bloco de conteúdo dentro de um módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="fab6f-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="fab6f-109">As propriedades do módulo de carrossel definem como esses módulos são renderizados.</span><span class="sxs-lookup"><span data-stu-id="fab6f-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="fab6f-110">Exemplos de módulos de carrossel no comércio online</span><span class="sxs-lookup"><span data-stu-id="fab6f-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="fab6f-111">Um carrossel que possui vários módulos promocionais pode ser usado em uma home page.</span><span class="sxs-lookup"><span data-stu-id="fab6f-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="fab6f-112">Um carrossel que possui vários módulos promocionais pode ser usado em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="fab6f-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="fab6f-113">Um carrossel pode ser usado em qualquer página de marketing para promover várias promoções ou produtos.</span><span class="sxs-lookup"><span data-stu-id="fab6f-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

## <a name="carousel-module-properties"></a><span data-ttu-id="fab6f-114">Propriedades do módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="fab6f-114">Carousel module properties</span></span>

| <span data-ttu-id="fab6f-115">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="fab6f-115">Property name</span></span>             | <span data-ttu-id="fab6f-116">Alíquota</span><span class="sxs-lookup"><span data-stu-id="fab6f-116">Value</span></span>                 | <span data-ttu-id="fab6f-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="fab6f-117">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="fab6f-118">Reprodução automática</span><span class="sxs-lookup"><span data-stu-id="fab6f-118">Autoplay</span></span>                  | <span data-ttu-id="fab6f-119">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="fab6f-119">**True** or **False**</span></span> | <span data-ttu-id="fab6f-120">Se o valor estiver definido como **Verdadeiro**, a transição entre os itens dentro no carrossel ocorrerá automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fab6f-120">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="fab6f-121">Se o valor estiver definido como **Falso**, nenhuma transição ocorrerá, a menos que o cliente use o teclado ou o mouse para passar de um item para o próximo.</span><span class="sxs-lookup"><span data-stu-id="fab6f-121">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="fab6f-122">Intervalo de transição de slides</span><span class="sxs-lookup"><span data-stu-id="fab6f-122">Slide transition interval</span></span> | <span data-ttu-id="fab6f-123">Um valor em segundos</span><span class="sxs-lookup"><span data-stu-id="fab6f-123">A value in seconds</span></span>    | <span data-ttu-id="fab6f-124">O intervalo para transições entre itens.</span><span class="sxs-lookup"><span data-stu-id="fab6f-124">The interval for transitions between items.</span></span> |
| <span data-ttu-id="fab6f-125">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="fab6f-125">Transition type</span></span>           | <span data-ttu-id="fab6f-126">**Slide** ou **Fade**</span><span class="sxs-lookup"><span data-stu-id="fab6f-126">**Slide** or **Fade**</span></span> | <span data-ttu-id="fab6f-127">O efeito de transição entre itens.</span><span class="sxs-lookup"><span data-stu-id="fab6f-127">The transition effect between items.</span></span> |
| <span data-ttu-id="fab6f-128">Ocultar palheta do carrossel</span><span class="sxs-lookup"><span data-stu-id="fab6f-128">Hide carousel flipper</span></span>     | <span data-ttu-id="fab6f-129">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="fab6f-129">**True** or **False**</span></span> | <span data-ttu-id="fab6f-130">Se o valor for definido como **True**, a palheta do carrossel e o indicador de sequência ficarão ocultos.</span><span class="sxs-lookup"><span data-stu-id="fab6f-130">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="fab6f-131">Permitir descarte do carrossel</span><span class="sxs-lookup"><span data-stu-id="fab6f-131">Allow carousel dismiss</span></span>    | <span data-ttu-id="fab6f-132">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="fab6f-132">**True** or **False**</span></span> | <span data-ttu-id="fab6f-133">Se o valor estiver definido como **True**, os usuários poderão dispensar o carrossel.</span><span class="sxs-lookup"><span data-stu-id="fab6f-133">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="fab6f-134">Adicionar um módulo de carrossel a uma página</span><span class="sxs-lookup"><span data-stu-id="fab6f-134">Add a carousel module to a page</span></span>

<span data-ttu-id="fab6f-135">Para adicionar um módulo de carrossel a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="fab6f-135">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="fab6f-136">Selecione **Novo** para criar um modelo de página.</span><span class="sxs-lookup"><span data-stu-id="fab6f-136">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="fab6f-137">Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira **Modelo de carrossel** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-137">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="fab6f-138">No slot **Corpo**, adicione um módulo **Página padrão**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-138">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="fab6f-139">Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="fab6f-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="fab6f-140">Use o modelo de carrossel que criou para criar uma página nomeada **Página do carrossel**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-140">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="fab6f-141">No slot **Principal** da nova página, adicione um módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="fab6f-141">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="fab6f-142">No painel à direita, defina o valor da **Largura** como **Preencher Tela**.</span><span class="sxs-lookup"><span data-stu-id="fab6f-142">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="fab6f-143">Em **Estrutura de Tópicos de Página**, adicione um módulo de carrossel ao módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="fab6f-143">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="fab6f-144">Adicione um módulo de bloco de conteúdo ao módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="fab6f-144">Add a content block module to the carousel module.</span></span> <span data-ttu-id="fab6f-145">Defina as propriedades do módulo de bloco de conteúdo fornecendo **Título**, **Link**, **Layout** e outras propriedades.</span><span class="sxs-lookup"><span data-stu-id="fab6f-145">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="fab6f-146">Adicione e configure outro módulo de bloco de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fab6f-146">Add and configure another content block module.</span></span>
1. <span data-ttu-id="fab6f-147">Defina propriedades adicionais para o módulo do carrossel conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fab6f-147">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="fab6f-148">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="fab6f-148">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="fab6f-149">A página deve mostrar um carrossel que possui dois módulos (um módulo de hero e um módulo de recurso).</span><span class="sxs-lookup"><span data-stu-id="fab6f-149">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="fab6f-150">Você pode alterar propriedades adicionais para os módulos de carrossel, hero e recurso, para obter o efeito desejado.</span><span class="sxs-lookup"><span data-stu-id="fab6f-150">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="fab6f-151">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="fab6f-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fab6f-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="fab6f-152">Additional resources</span></span>

[<span data-ttu-id="fab6f-153">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="fab6f-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="fab6f-154">Módulo de banner de promoção</span><span class="sxs-lookup"><span data-stu-id="fab6f-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="fab6f-155">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="fab6f-155">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="fab6f-156">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="fab6f-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="fab6f-157">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="fab6f-157">Video player module</span></span>](add-video-player.md)
