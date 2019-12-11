---
title: Módulo de alerta
description: Este tópico abrange os módulos de alerta e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785343"
---
# <a name="alert-module"></a><span data-ttu-id="a4dd3-103">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="a4dd3-103">Alert module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a4dd3-104">Este tópico abrange os módulos de alerta e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-104">This topic covers alert modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a4dd3-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="a4dd3-105">Overview</span></span>

<span data-ttu-id="a4dd3-106">Um módulo de alerta é usado para mostrar mensagens informativas em linha em uma página.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-106">An alert module is used to show inline informational messages on a page.</span></span> <span data-ttu-id="a4dd3-107">Os módulos de alerta permitem uma mensagem de texto e um link.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-107">Alert modules support a text message and a link.</span></span> <span data-ttu-id="a4dd3-108">Eles podem ser usados para mostrar promoções em todo o site que aparecem em todas as páginas de um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-108">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="a4dd3-109">Os módulos de alerta são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-109">Alert modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="examples-of-alert-modules-in-e-commerce"></a><span data-ttu-id="a4dd3-110">Exemplos de módulos de alerta no comércio online</span><span class="sxs-lookup"><span data-stu-id="a4dd3-110">Examples of alert modules in e-Commerce</span></span>

<span data-ttu-id="a4dd3-111">Os módulos de alerta podem ser usados no cabeçalho do site para indicar promoções ou mensagens em todo o site.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-111">Alert modules can be used in the site header to indicate site-wide promotions or messages.</span></span> <span data-ttu-id="a4dd3-112">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="a4dd3-112">Here are some examples:</span></span>

<span data-ttu-id="a4dd3-113">"A venda anual termina em 10 dias"</span><span class="sxs-lookup"><span data-stu-id="a4dd3-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="a4dd3-114">"Economize bastante com a venda na volta às aulas.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-114">"Save big with back to school sale.</span></span> <span data-ttu-id="a4dd3-115">Compre agora."</span><span class="sxs-lookup"><span data-stu-id="a4dd3-115">Shop Now."</span></span>

## <a name="alert-module-properties"></a><span data-ttu-id="a4dd3-116">Propriedades de módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="a4dd3-116">Alert module properties</span></span>

| <span data-ttu-id="a4dd3-117">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="a4dd3-117">Property name</span></span>  | <span data-ttu-id="a4dd3-118">Alíquota</span><span class="sxs-lookup"><span data-stu-id="a4dd3-118">Value</span></span>                              | <span data-ttu-id="a4dd3-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="a4dd3-119">Description</span></span> |
|----------------|------------------------------------|-------------|
| <span data-ttu-id="a4dd3-120">Texto</span><span class="sxs-lookup"><span data-stu-id="a4dd3-120">Text</span></span>           | <span data-ttu-id="a4dd3-121">Texto</span><span class="sxs-lookup"><span data-stu-id="a4dd3-121">Text</span></span>                               | <span data-ttu-id="a4dd3-122">A mensagem de texto que aparece no módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-122">The text message that appears in the alert module.</span></span> |
| <span data-ttu-id="a4dd3-123">Alinhamento de texto</span><span class="sxs-lookup"><span data-stu-id="a4dd3-123">Text alignment</span></span> | <span data-ttu-id="a4dd3-124">**Direito**, **Esquerdo** ou **Centro**</span><span class="sxs-lookup"><span data-stu-id="a4dd3-124">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="a4dd3-125">Um valor que define como o texto é alinhado no módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-125">A value that defines how text is aligned in the alert module.</span></span> |
| <span data-ttu-id="a4dd3-126">Ignorar alerta</span><span class="sxs-lookup"><span data-stu-id="a4dd3-126">Dismiss alert</span></span>  | <span data-ttu-id="a4dd3-127">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="a4dd3-127">**True** or **False**</span></span>              | <span data-ttu-id="a4dd3-128">Se o valor estiver definido como **Verdadeiro**, o cliente poderá descartar o alerta.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-128">If the value is set to **True**, the customer can dismiss the alert.</span></span> |
| <span data-ttu-id="a4dd3-129">Vincular</span><span class="sxs-lookup"><span data-stu-id="a4dd3-129">Link</span></span>           | <span data-ttu-id="a4dd3-130">URL</span><span class="sxs-lookup"><span data-stu-id="a4dd3-130">URL</span></span>                                | <span data-ttu-id="a4dd3-131">A URL para um link opcional.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-131">The URL for an optional link.</span></span> |

## <a name="add-an-alert-module-to-a-page"></a><span data-ttu-id="a4dd3-132">Adicionar um módulo de alerta a uma página</span><span class="sxs-lookup"><span data-stu-id="a4dd3-132">Add an alert module to a page</span></span> 

<span data-ttu-id="a4dd3-133">Para adicionar um módulo de alerta a uma página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-133">To add an alert module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="a4dd3-134">Criar um modelo da página chamado **modelo de alerta**.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-134">Create a page template that is named **alert template**.</span></span>
1. <span data-ttu-id="a4dd3-135">No slot **Principal** da página padrão, adicione um módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-135">In the **Main** slot of the default page, add an alert module.</span></span>
1. <span data-ttu-id="a4dd3-136">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-136">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="a4dd3-137">Use o modelo de alerta que criou para criar uma página nomeada **página de alerta**.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-137">Use the alert template that you just created to create a page that is named **alert page**.</span></span> 
1. <span data-ttu-id="a4dd3-138">No slot **Principal** da nova página, adicione um módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-138">In the **Main** slot of the new page, add an alert module.</span></span>
1. <span data-ttu-id="a4dd3-139">Nas configurações do módulo de alerta, insira o texto do alerta.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-139">In the settings for the alert module, enter the alert text.</span></span> <span data-ttu-id="a4dd3-140">É possível editar as outras propriedades se desejar personalizar ainda mais o módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-140">You can edit the other properties if you want to customize the alert module further.</span></span>
1. <span data-ttu-id="a4dd3-141">Salve e exiba a página.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-141">Save and preview the page.</span></span> <span data-ttu-id="a4dd3-142">Na parte superior da página, você verá um alerta com o texto que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-142">At the top of the page, you should see an alert that has the text that you added.</span></span>
1. <span data-ttu-id="a4dd3-143">Insira a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="a4dd3-143">Check in the page, and publish it.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="a4dd3-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a4dd3-144">Additional resources</span></span>

[<span data-ttu-id="a4dd3-145">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="a4dd3-145">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a4dd3-146">Módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="a4dd3-146">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="a4dd3-147">Módulo de bloco de conteúdo sofisticado</span><span class="sxs-lookup"><span data-stu-id="a4dd3-147">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="a4dd3-148">Módulo de posicionamento de conteúdo</span><span class="sxs-lookup"><span data-stu-id="a4dd3-148">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="a4dd3-149">Módulo de recurso</span><span class="sxs-lookup"><span data-stu-id="a4dd3-149">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="a4dd3-150">Módulo de hero</span><span class="sxs-lookup"><span data-stu-id="a4dd3-150">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="a4dd3-151">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="a4dd3-151">Video player module</span></span>](add-video-player.md)
