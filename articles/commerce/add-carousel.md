---
title: Módulo de carrossel
description: Este tópico abrange os módulos de carrossel e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: f09f3f98d174f965a75e27ee6a5c2ed8599042fc
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3816977"
---
# <a name="carousel-module"></a><span data-ttu-id="71987-103">Módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="71987-103">Carousel module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="71987-104">Este tópico abrange os módulos de carrossel e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="71987-104">This topic covers carousel modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="71987-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="71987-105">Overview</span></span>

<span data-ttu-id="71987-106">Um módulo de carrossel é usado para colocar vários itens promocionais (incluindo imagens sofisticadas) em uma faixa de carrossel rotatória na qual os clientes possam navegar.</span><span class="sxs-lookup"><span data-stu-id="71987-106">A carousel module is used to put multiple promotional items (including rich images) in a rotating carousel banner that customers can browse.</span></span> <span data-ttu-id="71987-107">Por exemplo, um varejista pode usar um módulo de carrossel em uma home page para exibir vários novos produtos ou promoções.</span><span class="sxs-lookup"><span data-stu-id="71987-107">For example, a retailer can use a carousel module on a home page to showcase multiple new products or promotions.</span></span>

<span data-ttu-id="71987-108">Você pode adicionar módulos de bloco de conteúdo dentro de um módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="71987-108">You can add content block modules inside a carousel module.</span></span> <span data-ttu-id="71987-109">As propriedades do módulo de carrossel definem como esses módulos são renderizados.</span><span class="sxs-lookup"><span data-stu-id="71987-109">The properties of the carousel module then define how those modules are rendered.</span></span>

## <a name="examples-of-carousel-modules-in-e-commerce"></a><span data-ttu-id="71987-110">Exemplos de módulos de carrossel no comércio online</span><span class="sxs-lookup"><span data-stu-id="71987-110">Examples of carousel modules in e-Commerce</span></span>

- <span data-ttu-id="71987-111">Um carrossel que possui vários módulos promocionais pode ser usado em uma home page.</span><span class="sxs-lookup"><span data-stu-id="71987-111">A carousel that has multiple promotional modules inside it can be used on a home page.</span></span>
- <span data-ttu-id="71987-112">Um carrossel que possui vários módulos promocionais pode ser usado em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="71987-112">A carousel that has multiple promotional modules inside it can be used on a product details page.</span></span>
- <span data-ttu-id="71987-113">Um carrossel pode ser usado em qualquer página de marketing para promover várias promoções ou produtos.</span><span class="sxs-lookup"><span data-stu-id="71987-113">A carousel can be used on any marketing page to promote multiple promotions or products.</span></span>

<span data-ttu-id="71987-114">A imagem a seguir mostra um exemplo de um módulo de carrossel que é usado em uma home page.</span><span class="sxs-lookup"><span data-stu-id="71987-114">The following image shows an example of a carousel module that is used on a home page.</span></span> <span data-ttu-id="71987-115">Este módulo de carrossel contém vários itens de bloco de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="71987-115">This carousel module contains multiple content block items.</span></span>

![Exemplo de um módulo de carrossel](./media/Hero.PNG)

## <a name="carousel-module-properties"></a><span data-ttu-id="71987-117">Propriedades do módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="71987-117">Carousel module properties</span></span>

| <span data-ttu-id="71987-118">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="71987-118">Property name</span></span>             | <span data-ttu-id="71987-119">Alíquota</span><span class="sxs-lookup"><span data-stu-id="71987-119">Value</span></span>                 | <span data-ttu-id="71987-120">descrição</span><span class="sxs-lookup"><span data-stu-id="71987-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="71987-121">Reprodução automática</span><span class="sxs-lookup"><span data-stu-id="71987-121">Autoplay</span></span>                  | <span data-ttu-id="71987-122">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="71987-122">**True** or **False**</span></span> | <span data-ttu-id="71987-123">Se o valor estiver definido como **Verdadeiro**, a transição entre os itens dentro no carrossel ocorrerá automaticamente.</span><span class="sxs-lookup"><span data-stu-id="71987-123">If the value is set to **True**, the transition between items inside the carousel occurs automatically.</span></span> <span data-ttu-id="71987-124">Se o valor estiver definido como **Falso**, nenhuma transição ocorrerá, a menos que o cliente use o teclado ou o mouse para passar de um item para o próximo.</span><span class="sxs-lookup"><span data-stu-id="71987-124">If the value is set to **False**, no transition occurs unless the customer uses the keyboard or mouse to move from one item to the next item.</span></span> |
| <span data-ttu-id="71987-125">Intervalo de transição de slides</span><span class="sxs-lookup"><span data-stu-id="71987-125">Slide transition interval</span></span> | <span data-ttu-id="71987-126">Um valor em segundos</span><span class="sxs-lookup"><span data-stu-id="71987-126">A value in seconds</span></span>    | <span data-ttu-id="71987-127">O intervalo para transições entre itens.</span><span class="sxs-lookup"><span data-stu-id="71987-127">The interval for transitions between items.</span></span> |
| <span data-ttu-id="71987-128">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="71987-128">Transition type</span></span>           | <span data-ttu-id="71987-129">**Slide** ou **Fade**</span><span class="sxs-lookup"><span data-stu-id="71987-129">**Slide** or **Fade**</span></span> | <span data-ttu-id="71987-130">O efeito de transição entre itens.</span><span class="sxs-lookup"><span data-stu-id="71987-130">The transition effect between items.</span></span> |
| <span data-ttu-id="71987-131">Ocultar palheta do carrossel</span><span class="sxs-lookup"><span data-stu-id="71987-131">Hide carousel flipper</span></span>     | <span data-ttu-id="71987-132">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="71987-132">**True** or **False**</span></span> | <span data-ttu-id="71987-133">Se o valor for definido como **True**, a palheta do carrossel e o indicador de sequência ficarão ocultos.</span><span class="sxs-lookup"><span data-stu-id="71987-133">If the value is set to **True**, the carousel flipper and sequence indicator are hidden.</span></span> |
| <span data-ttu-id="71987-134">Permitir descarte do carrossel</span><span class="sxs-lookup"><span data-stu-id="71987-134">Allow carousel dismiss</span></span>    | <span data-ttu-id="71987-135">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="71987-135">**True** or **False**</span></span> | <span data-ttu-id="71987-136">Se o valor estiver definido como **True**, os usuários poderão dispensar o carrossel.</span><span class="sxs-lookup"><span data-stu-id="71987-136">If the value is set to **True**, users can dismiss the carousel.</span></span> |

## <a name="add-a-carousel-module-to-a-page"></a><span data-ttu-id="71987-137">Adicionar um módulo de carrossel a uma página</span><span class="sxs-lookup"><span data-stu-id="71987-137">Add a carousel module to a page</span></span>

<span data-ttu-id="71987-138">Para adicionar um módulo de carrossel a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="71987-138">To add a carousel module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="71987-139">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="71987-139">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="71987-140">Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira **Modelo de carrossel** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="71987-140">In the **New Template** dialog box, under **Template Name**, enter **Carousel template**, and then select **OK**.</span></span>
1. <span data-ttu-id="71987-141">No slot **Corpo**, adicione um módulo **Página padrão**.</span><span class="sxs-lookup"><span data-stu-id="71987-141">In the **Body** slot, add a **Default page** module.</span></span>
1. <span data-ttu-id="71987-142">Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="71987-142">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>  
1. <span data-ttu-id="71987-143">Use o modelo de carrossel que criou para criar uma página nomeada **Página do carrossel**.</span><span class="sxs-lookup"><span data-stu-id="71987-143">Use the carousel template that you just created to create a page that is named **Carousel page**.</span></span>
1. <span data-ttu-id="71987-144">No slot **Principal** da nova página, adicione um módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="71987-144">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="71987-145">No painel à direita, defina o valor da **Largura** como **Preencher Tela**.</span><span class="sxs-lookup"><span data-stu-id="71987-145">In the pane on the right, set the **Width** value to **Fill Screen**.</span></span>
1. <span data-ttu-id="71987-146">Em **Estrutura de Tópicos de Página**, adicione um módulo de carrossel ao módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="71987-146">Under **Page Outline**, add a carousel module to the container module.</span></span>
1. <span data-ttu-id="71987-147">Adicione um módulo de bloco de conteúdo ao módulo de carrossel.</span><span class="sxs-lookup"><span data-stu-id="71987-147">Add a content block module to the carousel module.</span></span> <span data-ttu-id="71987-148">Defina as propriedades do módulo de bloco de conteúdo fornecendo **Título**, **Link**, **Layout** e outras propriedades.</span><span class="sxs-lookup"><span data-stu-id="71987-148">Set the properties of the content block module by providing **Heading**, **Link**, **Layout**, and other properties.</span></span>
1. <span data-ttu-id="71987-149">Adicione e configure outro módulo de bloco de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="71987-149">Add and configure another content block module.</span></span>
1. <span data-ttu-id="71987-150">Defina propriedades adicionais para o módulo do carrossel conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="71987-150">Set additional properties for the carousel module as you require.</span></span>
1. <span data-ttu-id="71987-151">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="71987-151">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="71987-152">A página deve mostrar um carrossel que possui dois módulos (um módulo de hero e um módulo de recurso).</span><span class="sxs-lookup"><span data-stu-id="71987-152">The page should show a carousel that has two modules inside it (a hero module and a feature module).</span></span> <span data-ttu-id="71987-153">Você pode alterar propriedades adicionais para os módulos de carrossel, hero e recurso, para obter o efeito desejado.</span><span class="sxs-lookup"><span data-stu-id="71987-153">You can change additional properties for the carousel, hero, and feature modules to achieve the desired effect.</span></span>
1. <span data-ttu-id="71987-154">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="71987-154">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71987-155">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="71987-155">Additional resources</span></span>

[<span data-ttu-id="71987-156">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="71987-156">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="71987-157">Módulo de banner de promoção</span><span class="sxs-lookup"><span data-stu-id="71987-157">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="71987-158">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="71987-158">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="71987-159">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="71987-159">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="71987-160">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="71987-160">Video player module</span></span>](add-video-player.md)
