---
title: Módulo de faixa promocional
description: Este tópico abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: dae824cdbaaf56f85f125c5f36aaa56171bbd6bc
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411356"
---
# <a name="promo-banner-module"></a><span data-ttu-id="b902a-103">Módulo de faixa promocional</span><span class="sxs-lookup"><span data-stu-id="b902a-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b902a-104">Este tópico abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b902a-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b902a-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="b902a-105">Overview</span></span>

<span data-ttu-id="b902a-106">Os módulos de faixa promocional são usados para mostrar mensagens informativas em linha em uma página.</span><span class="sxs-lookup"><span data-stu-id="b902a-106">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="b902a-107">Eles podem ser usados para mostrar promoções em todo o site que aparecem em todas as páginas de um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b902a-107">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="b902a-108">Os módulos de faixa promocional fornecem suporte a uma mensagem de texto e um link.</span><span class="sxs-lookup"><span data-stu-id="b902a-108">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="b902a-109">Se várias mensagens forem adicionadas a um módulo de faixa promocional, ele se tornará uma faixa de carrossel giratória que permite aos clientes percorrerem todas as mensagens.</span><span class="sxs-lookup"><span data-stu-id="b902a-109">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="b902a-110">Os módulos de faixa promocional são controlados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="b902a-110">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="b902a-111">Exemplos de uso de faixas promocionais no comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="b902a-111">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="b902a-112">As faixas promocionais podem ser usadas no cabeçalho do site para mostrar promoções ou mensagens em todo o site, como nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b902a-112">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="b902a-113">"A venda anual termina em 10 dias"</span><span class="sxs-lookup"><span data-stu-id="b902a-113">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="b902a-114">"Economize bastante com a venda na volta às aulas.</span><span class="sxs-lookup"><span data-stu-id="b902a-114">"Save big with back to school sale.</span></span> <span data-ttu-id="b902a-115">Compre agora."</span><span class="sxs-lookup"><span data-stu-id="b902a-115">Shop Now."</span></span>

<span data-ttu-id="b902a-116">"Comprar em VENDA de ação de graças!"</span><span class="sxs-lookup"><span data-stu-id="b902a-116">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="b902a-117">A imagem a seguir mostra um exemplo de uma faixa promocional.</span><span class="sxs-lookup"><span data-stu-id="b902a-117">The following image shows an example of a promo banner.</span></span>

![Exemplo de um módulo de faixa promocional](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="b902a-119">Propriedades do módulo de faixa promocional</span><span class="sxs-lookup"><span data-stu-id="b902a-119">Promo banner module properties</span></span>

| <span data-ttu-id="b902a-120">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="b902a-120">Property name</span></span>             | <span data-ttu-id="b902a-121">Alíquota</span><span class="sxs-lookup"><span data-stu-id="b902a-121">Value</span></span>                              | <span data-ttu-id="b902a-122">descrição</span><span class="sxs-lookup"><span data-stu-id="b902a-122">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="b902a-123">Mensagens da faixa</span><span class="sxs-lookup"><span data-stu-id="b902a-123">Banner messages</span></span>           | <span data-ttu-id="b902a-124">Textos e links</span><span class="sxs-lookup"><span data-stu-id="b902a-124">Text and links</span></span>                     | <span data-ttu-id="b902a-125">Uma matriz de texto e links.</span><span class="sxs-lookup"><span data-stu-id="b902a-125">An array of text and links.</span></span> |
| <span data-ttu-id="b902a-126">Reprodução automática</span><span class="sxs-lookup"><span data-stu-id="b902a-126">Autoplay</span></span>                  | <span data-ttu-id="b902a-127">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="b902a-127">**True** or **False**</span></span>              | <span data-ttu-id="b902a-128">Um valor que indica se é possível percorrer automaticamente as mensagens caso várias mensagens estejam configuradas.</span><span class="sxs-lookup"><span data-stu-id="b902a-128">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="b902a-129">Intervalo de transição de slides</span><span class="sxs-lookup"><span data-stu-id="b902a-129">Slide transition interval</span></span> | <span data-ttu-id="b902a-130">Um número de milissegundos (ms)</span><span class="sxs-lookup"><span data-stu-id="b902a-130">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="b902a-131">O intervalo usado para percorrer as mensagens.</span><span class="sxs-lookup"><span data-stu-id="b902a-131">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="b902a-132">Permitir ignorar</span><span class="sxs-lookup"><span data-stu-id="b902a-132">Allow dismiss</span></span>             | <span data-ttu-id="b902a-133">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="b902a-133">**True** or **False**</span></span>              | <span data-ttu-id="b902a-134">Se o valor estiver definido como **Verdadeiro**, os clientes poderão dispensar o alerta.</span><span class="sxs-lookup"><span data-stu-id="b902a-134">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="b902a-135">Mostrar palheta do carrossel</span><span class="sxs-lookup"><span data-stu-id="b902a-135">Show carousel flipper</span></span>     | <span data-ttu-id="b902a-136">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="b902a-136">**True** or **False**</span></span>              | <span data-ttu-id="b902a-137">Um valor que indica se as palhetas do carrossel devem ser mostradas, de forma que os clientes possam percorrer vários itens de faixa manualmente.</span><span class="sxs-lookup"><span data-stu-id="b902a-137">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="b902a-138">Alinhamento de texto</span><span class="sxs-lookup"><span data-stu-id="b902a-138">Text alignment</span></span>            | <span data-ttu-id="b902a-139">**Direito**, **Esquerdo** ou **Centro**</span><span class="sxs-lookup"><span data-stu-id="b902a-139">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="b902a-140">O alinhamento do texto no módulo de faixa promocional.</span><span class="sxs-lookup"><span data-stu-id="b902a-140">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="b902a-141">Vincular</span><span class="sxs-lookup"><span data-stu-id="b902a-141">Link</span></span>                      | <span data-ttu-id="b902a-142">URL A</span><span class="sxs-lookup"><span data-stu-id="b902a-142">A URL</span></span>                              | <span data-ttu-id="b902a-143">A URL para um link opcional.</span><span class="sxs-lookup"><span data-stu-id="b902a-143">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="b902a-144">Adicionar um módulo de faixa promocional a uma página</span><span class="sxs-lookup"><span data-stu-id="b902a-144">Add a promo banner module to a page</span></span> 

<span data-ttu-id="b902a-145">Para adicionar um módulo de faixa promocional a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b902a-145">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b902a-146">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="b902a-146">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="b902a-147">Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira **Modelo do banner da promoção** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b902a-147">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="b902a-148">Em **Estrutura de Tópicos de Página**, adicione um módulo **Página padrão** ao slot **Corpo**.</span><span class="sxs-lookup"><span data-stu-id="b902a-148">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="b902a-149">Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="b902a-149">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="b902a-150">Use o modelo que você acabou de criar para criar uma página com o nome **Página de faixa promocional**.</span><span class="sxs-lookup"><span data-stu-id="b902a-150">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="b902a-151">No slot **Principal** da nova página, adicione um módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="b902a-151">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="b902a-152">No painel à direita, defina o valor da **Largura** como **Preencher Contêiner**.</span><span class="sxs-lookup"><span data-stu-id="b902a-152">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="b902a-153">Em **Estrutura de Tópicos de Página**, adicione um módulo de faixa promocional ao módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="b902a-153">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="b902a-154">Nas configurações do módulo de faixa, adicione uma ou mais mensagens de faixa.</span><span class="sxs-lookup"><span data-stu-id="b902a-154">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="b902a-155">Cada mensagem pode ter texto juntamente com um link.</span><span class="sxs-lookup"><span data-stu-id="b902a-155">Each message can have text together with a link.</span></span> <span data-ttu-id="b902a-156">É possível editar as outras propriedades para personalizar ainda mais o módulo.</span><span class="sxs-lookup"><span data-stu-id="b902a-156">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="b902a-157">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="b902a-157">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="b902a-158">Na parte superior da página, você verá um alerta que mostra o texto que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="b902a-158">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="b902a-159">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="b902a-159">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="b902a-160">Em geral, uma faixa promocional é usada no slot do cabeçalho da página ou em um slot de subcabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b902a-160">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="b902a-161">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b902a-161">Additional resources</span></span>

[<span data-ttu-id="b902a-162">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="b902a-162">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b902a-163">Módulo do carrossel</span><span class="sxs-lookup"><span data-stu-id="b902a-163">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="b902a-164">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="b902a-164">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="b902a-165">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b902a-165">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="b902a-166">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="b902a-166">Video player module</span></span>](add-video-player.md)
