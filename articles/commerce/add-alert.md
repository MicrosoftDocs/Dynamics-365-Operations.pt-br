---
title: Módulo de faixa promocional
description: Este tópico abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: da5e220e4578d1064eb7b627b441d3f585b3c095
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025611"
---
# <a name="promo-banner-module"></a><span data-ttu-id="4276a-103">Módulo de faixa promocional</span><span class="sxs-lookup"><span data-stu-id="4276a-103">Promo banner module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4276a-104">Este tópico abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4276a-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4276a-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="4276a-105">Overview</span></span>

<span data-ttu-id="4276a-106">Os módulos de faixa promocional são usados para mostrar mensagens informativas em linha em uma página.</span><span class="sxs-lookup"><span data-stu-id="4276a-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="4276a-107">Eles podem ser usados para mostrar promoções em todo o site que aparecem em todas as páginas de um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4276a-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="4276a-108">Os módulos de faixa promocional fornecem suporte a uma mensagem de texto e um link.</span><span class="sxs-lookup"><span data-stu-id="4276a-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="4276a-109">Se várias mensagens forem adicionadas a um módulo de faixa promocional, ele se tornará uma faixa de carrossel giratória que permite aos clientes percorrerem todas as mensagens.</span><span class="sxs-lookup"><span data-stu-id="4276a-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="4276a-110">Os módulos de faixa promocional são controlados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="4276a-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="4276a-111">Exemplos de uso de faixas promocionais no comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="4276a-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="4276a-112">As faixas promocionais podem ser usadas no cabeçalho do site para mostrar promoções ou mensagens em todo o site, como nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="4276a-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="4276a-113">"A venda anual termina em 10 dias"</span><span class="sxs-lookup"><span data-stu-id="4276a-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="4276a-114">"Economize bastante com a venda na volta às aulas.</span><span class="sxs-lookup"><span data-stu-id="4276a-114">"Save big with back to school sale.</span></span> <span data-ttu-id="4276a-115">Compre agora."</span><span class="sxs-lookup"><span data-stu-id="4276a-115">Shop Now."</span></span>

## <a name="promo-banner-module-properties"></a><span data-ttu-id="4276a-116">Propriedades do módulo de faixa promocional</span><span class="sxs-lookup"><span data-stu-id="4276a-116">Promo banner module properties</span></span>

| <span data-ttu-id="4276a-117">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="4276a-117">Property name</span></span>             | <span data-ttu-id="4276a-118">Value</span><span class="sxs-lookup"><span data-stu-id="4276a-118">Value</span></span>                              | <span data-ttu-id="4276a-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="4276a-119">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="4276a-120">Mensagens da faixa</span><span class="sxs-lookup"><span data-stu-id="4276a-120">Banner messages</span></span>           | <span data-ttu-id="4276a-121">Textos e links</span><span class="sxs-lookup"><span data-stu-id="4276a-121">Text and links</span></span>                     | <span data-ttu-id="4276a-122">Uma matriz de texto e links.</span><span class="sxs-lookup"><span data-stu-id="4276a-122">An array of text and links.</span></span> |
| <span data-ttu-id="4276a-123">Reprodução automática</span><span class="sxs-lookup"><span data-stu-id="4276a-123">Autoplay</span></span>                  | <span data-ttu-id="4276a-124">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="4276a-124">**True** or **False**</span></span>              | <span data-ttu-id="4276a-125">Um valor que indica se é possível percorrer automaticamente as mensagens caso várias mensagens estejam configuradas.</span><span class="sxs-lookup"><span data-stu-id="4276a-125">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="4276a-126">Intervalo de transição de slides</span><span class="sxs-lookup"><span data-stu-id="4276a-126">Slide transition interval</span></span> | <span data-ttu-id="4276a-127">Um número de milissegundos (ms)</span><span class="sxs-lookup"><span data-stu-id="4276a-127">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="4276a-128">O intervalo usado para percorrer as mensagens.</span><span class="sxs-lookup"><span data-stu-id="4276a-128">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="4276a-129">Permitir ignorar</span><span class="sxs-lookup"><span data-stu-id="4276a-129">Allow dismiss</span></span>             | <span data-ttu-id="4276a-130">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="4276a-130">**True** or **False**</span></span>              | <span data-ttu-id="4276a-131">Se o valor estiver definido como **Verdadeiro**, os clientes poderão dispensar o alerta.</span><span class="sxs-lookup"><span data-stu-id="4276a-131">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="4276a-132">Mostrar palheta do carrossel</span><span class="sxs-lookup"><span data-stu-id="4276a-132">Show carousel flipper</span></span>     | <span data-ttu-id="4276a-133">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="4276a-133">**True** or **False**</span></span>              | <span data-ttu-id="4276a-134">Um valor que indica se as palhetas do carrossel devem ser mostradas, de forma que os clientes possam percorrer vários itens de faixa manualmente.</span><span class="sxs-lookup"><span data-stu-id="4276a-134">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="4276a-135">Alinhamento de texto</span><span class="sxs-lookup"><span data-stu-id="4276a-135">Text alignment</span></span>            | <span data-ttu-id="4276a-136">**Direito**, **Esquerdo** ou **Centro**</span><span class="sxs-lookup"><span data-stu-id="4276a-136">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="4276a-137">O alinhamento do texto no módulo de faixa promocional.</span><span class="sxs-lookup"><span data-stu-id="4276a-137">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="4276a-138">Vincular</span><span class="sxs-lookup"><span data-stu-id="4276a-138">Link</span></span>                      | <span data-ttu-id="4276a-139">URL A</span><span class="sxs-lookup"><span data-stu-id="4276a-139">A URL</span></span>                              | <span data-ttu-id="4276a-140">A URL para um link opcional.</span><span class="sxs-lookup"><span data-stu-id="4276a-140">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="4276a-141">Adicionar um módulo de faixa promocional a uma página</span><span class="sxs-lookup"><span data-stu-id="4276a-141">Add a promo banner module to a page</span></span> 

<span data-ttu-id="4276a-142">Para adicionar um módulo de faixa promocional a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4276a-142">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="4276a-143">Criar um modelo da página chamado **Modelo de faixa promocional**.</span><span class="sxs-lookup"><span data-stu-id="4276a-143">Create a page template that is named **Promo banner template**.</span></span>
1. <span data-ttu-id="4276a-144">Em **Estrutura de Tópicos de Página**, adicione um módulo **Página padrão** ao slot **Corpo**.</span><span class="sxs-lookup"><span data-stu-id="4276a-144">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="4276a-145">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="4276a-145">Check in the template, and publish it.</span></span> 
1. <span data-ttu-id="4276a-146">Use o modelo que você acabou de criar para criar uma página com o nome **Página de faixa promocional**.</span><span class="sxs-lookup"><span data-stu-id="4276a-146">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="4276a-147">No slot **Principal** da nova página, adicione um módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="4276a-147">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="4276a-148">No painel à direita, defina o valor da **Largura** como **Preencher Contêiner**.</span><span class="sxs-lookup"><span data-stu-id="4276a-148">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="4276a-149">Em **Estrutura de Tópicos de Página**, adicione um módulo de faixa promocional ao módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="4276a-149">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="4276a-150">Nas configurações do módulo de faixa, adicione uma ou mais mensagens de faixa.</span><span class="sxs-lookup"><span data-stu-id="4276a-150">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="4276a-151">Cada mensagem pode ter texto juntamente com um link.</span><span class="sxs-lookup"><span data-stu-id="4276a-151">Each message can have text together with a link.</span></span> <span data-ttu-id="4276a-152">É possível editar as outras propriedades para personalizar ainda mais o módulo.</span><span class="sxs-lookup"><span data-stu-id="4276a-152">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="4276a-153">Salve e exiba a página.</span><span class="sxs-lookup"><span data-stu-id="4276a-153">Save and preview the page.</span></span> <span data-ttu-id="4276a-154">Na parte superior da página, você verá um alerta que mostra o texto que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="4276a-154">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="4276a-155">Termine de editar a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="4276a-155">Finish editing the page, and publish it.</span></span> 

> [!NOTE]
> <span data-ttu-id="4276a-156">Em geral, uma faixa promocional é usada no slot do cabeçalho da página ou em um slot de subcabeçalho.</span><span class="sxs-lookup"><span data-stu-id="4276a-156">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="4276a-157">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4276a-157">Additional resources</span></span>

[<span data-ttu-id="4276a-158">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="4276a-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4276a-159">Módulo do carrossel</span><span class="sxs-lookup"><span data-stu-id="4276a-159">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="4276a-160">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="4276a-160">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="4276a-161">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="4276a-161">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="4276a-162">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="4276a-162">Video player module</span></span>](add-video-player.md)
