---
title: Módulo de carrossel
description: Este tópico abrange os módulos do carrossel e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5bc2227e08dbbf5f76a37180114e5affff131658
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797878"
---
# <a name="carousel-module"></a><span data-ttu-id="da0e4-103">Módulo do carrossel</span><span class="sxs-lookup"><span data-stu-id="da0e4-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="da0e4-104">Este tópico abrange os módulos do carrossel e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="da0e4-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="da0e4-105">Um módulo de carrossel é usado para colocar vários itens promocionais (incluindo imagens sofisticadas) em uma faixa de carrossel rotatória na qual os clientes possam navegar.</span><span class="sxs-lookup"><span data-stu-id="da0e4-105">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="da0e4-106">Por exemplo, um varejista pode usar um módulo de carrossel em uma home page para exibir vários novos produtos ou promoções.</span><span class="sxs-lookup"><span data-stu-id="da0e4-106">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="da0e4-107">Você pode adicionar módulos de bloco de conteúdo dentro de um módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="da0e4-107">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="da0e4-108">As propriedades do módulo de carrossel definem como esses módulos são renderizados.</span><span class="sxs-lookup"><span data-stu-id="da0e4-108">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="da0e4-109">Exemplos de módulos de carrossel no comércio online</span><span class="sxs-lookup"><span data-stu-id="da0e4-109">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="da0e4-110">Um carrossel que possui vários módulos promocionais pode ser usado em uma home page.</span><span class="sxs-lookup"><span data-stu-id="da0e4-110">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="da0e4-111">Um carrossel que possui vários módulos promocionais pode ser usado em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="da0e4-111">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="da0e4-112">Um carrossel pode ser usado em qualquer página de marketing para promover várias promoções ou produtos.</span><span class="sxs-lookup"><span data-stu-id="da0e4-112">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="da0e4-113">A imagem a seguir mostra um exemplo de um módulo de carrossel que é usado em uma home page.</span><span class="sxs-lookup"><span data-stu-id="da0e4-113">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="da0e4-114">Este módulo de carrossel contém vários itens de bloco de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="da0e4-114">This carousel module contains multiple content block items.</span></span>

![Exemplo de um módulo de carrossel](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="da0e4-116">Propriedades do módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="da0e4-116">Carousel module properties</span></span>

| <span data-ttu-id="da0e4-117">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="da0e4-117">Property name</span></span>             | <span data-ttu-id="da0e4-118">Alíquota</span><span class="sxs-lookup"><span data-stu-id="da0e4-118">Value</span></span>                 | <span data-ttu-id="da0e4-119">descrição</span><span class="sxs-lookup"><span data-stu-id="da0e4-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="da0e4-120">Reprodução automática</span><span class="sxs-lookup"><span data-stu-id="da0e4-120">Autoplay</span></span>                  | <span data-ttu-id="da0e4-121">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="da0e4-121">**True** or **False**</span></span> | <span data-ttu-id="da0e4-122">Se o valor estiver definido como **Verdadeiro**, a transição entre os itens dentro no carrossel ocorrerá automaticamente.</span><span class="sxs-lookup"><span data-stu-id="da0e4-122">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="da0e4-123">Se o valor estiver definido como **Falso**, nenhuma transição ocorrerá, a menos que o cliente use o teclado ou o mouse para passar de um item para o próximo.</span><span class="sxs-lookup"><span data-stu-id="da0e4-123">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="da0e4-124">Intervalo de transição de slides</span><span class="sxs-lookup"><span data-stu-id="da0e4-124">Slide transition interval</span></span> | <span data-ttu-id="da0e4-125">Um valor em segundos</span><span class="sxs-lookup"><span data-stu-id="da0e4-125">A value in seconds</span></span>    | <span data-ttu-id="da0e4-126">O intervalo para transições entre itens.</span><span class="sxs-lookup"><span data-stu-id="da0e4-126">The interval for transitions between items.</span></span> |
| <span data-ttu-id="da0e4-127">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="da0e4-127">Transition type</span></span>           | <span data-ttu-id="da0e4-128">**Slide** ou **Fade**</span><span class="sxs-lookup"><span data-stu-id="da0e4-128">**Slide** or **Fade**</span></span> | <span data-ttu-id="da0e4-129">O efeito de transição entre itens.</span><span class="sxs-lookup"><span data-stu-id="da0e4-129">The transition effect between items.</span></span> |
| <span data-ttu-id="da0e4-130">Ocultar palheta do carrossel</span><span class="sxs-lookup"><span data-stu-id="da0e4-130">Hide carousel flipper</span></span>     | <span data-ttu-id="da0e4-131">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="da0e4-131">**True** or **False**</span></span> | <span data-ttu-id="da0e4-132">Se o valor for definido como **True**, a palheta do carrossel e o indicador de sequência ficarão ocultos.</span><span class="sxs-lookup"><span data-stu-id="da0e4-132">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="da0e4-133">Permitir descarte do carrossel</span><span class="sxs-lookup"><span data-stu-id="da0e4-133">Allow carousel dismiss</span></span>    | <span data-ttu-id="da0e4-134">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="da0e4-134">**True** or **False**</span></span> | <span data-ttu-id="da0e4-135">Se o valor estiver definido como **True**, os usuários poderão dispensar o carrossel.</span><span class="sxs-lookup"><span data-stu-id="da0e4-135">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="da0e4-136">Adicionar um módulo de carrossel a uma página</span><span class="sxs-lookup"><span data-stu-id="da0e4-136">Add a carousel module to a page</span></span>

<span data-ttu-id="da0e4-137">Para adicionar um módulo de carrossel a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="da0e4-137">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="da0e4-138">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="da0e4-138">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="da0e4-139">Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira **Modelo de carrossel** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="da0e4-139">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="da0e4-140">No slot **Corpo**, adicione um módulo **Página padrão**.</span><span class="sxs-lookup"><span data-stu-id="da0e4-140">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="da0e4-141">Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="da0e4-141">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="da0e4-142">Use o modelo de carrossel que criou para criar uma página nomeada **Página do carrossel**.</span><span class="sxs-lookup"><span data-stu-id="da0e4-142">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="da0e4-143">No slot **Principal** da nova página, adicione um módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="da0e4-143">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="da0e4-144">No painel à direita, defina o valor da **Largura** como **Preencher Tela**.</span><span class="sxs-lookup"><span data-stu-id="da0e4-144">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="da0e4-145">Em **Estrutura de Tópicos de Página**, adicione um módulo de carrossel ao módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="da0e4-145">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="da0e4-146">Adicione um módulo de bloco de conteúdo ao módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="da0e4-146">Add a content block module to the carousel module.</span></span> <span data-ttu-id="da0e4-147">Defina as propriedades do módulo de bloco de conteúdo fornecendo **Título**, **Link**, **Layout** e outras propriedades.</span><span class="sxs-lookup"><span data-stu-id="da0e4-147">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="da0e4-148">Adicione e configure outro módulo de bloco de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="da0e4-148">Add and configure another content block module.</span></span>
1. <span data-ttu-id="da0e4-149">Defina propriedades adicionais para o módulo do carrossel conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="da0e4-149">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="da0e4-150">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="da0e4-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="da0e4-151">A página deve mostrar um carrossel que possui dois módulos (um módulo de hero e um módulo de recurso).</span><span class="sxs-lookup"><span data-stu-id="da0e4-151">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="da0e4-152">Você pode alterar propriedades adicionais para os módulos de carrossel, hero e recurso, para obter o efeito desejado.</span><span class="sxs-lookup"><span data-stu-id="da0e4-152">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="da0e4-153">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="da0e4-153">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da0e4-154">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="da0e4-154">Additional resources</span></span>

[<span data-ttu-id="da0e4-155">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="da0e4-155">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="da0e4-156">Módulo de banner de promoção</span><span class="sxs-lookup"><span data-stu-id="da0e4-156">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="da0e4-157">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="da0e4-157">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="da0e4-158">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="da0e4-158">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="da0e4-159">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="da0e4-159">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]