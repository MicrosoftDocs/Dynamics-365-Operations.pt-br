---
title: Módulo de faixa promocional
description: Este tópico abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: be3cc9729b58fce9ebc9885d8cb20b63114362a0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796237"
---
# <a name="promo-banner-module"></a><span data-ttu-id="c4e77-103">Módulo de banner de promoção</span><span class="sxs-lookup"><span data-stu-id="c4e77-103">Promo banner module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c4e77-104">Este tópico abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c4e77-104">This topic covers promo banner modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c4e77-105">Os módulos de faixa promocional são usados para mostrar mensagens informativas em linha em uma página.</span><span class="sxs-lookup"><span data-stu-id="c4e77-105">Promo banner modules are used to show inline informational messages on a page.</span></span> <span data-ttu-id="c4e77-106">Eles podem ser usados para mostrar promoções em todo o site que aparecem em todas as páginas de um site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c4e77-106">They can be used to show site-wide promotions that appear on all pages of an e-Commerce site.</span></span> 

<span data-ttu-id="c4e77-107">Os módulos de faixa promocional fornecem suporte a uma mensagem de texto e um link.</span><span class="sxs-lookup"><span data-stu-id="c4e77-107">Promo banner modules support a text message and a link.</span></span> <span data-ttu-id="c4e77-108">Se várias mensagens forem adicionadas a um módulo de faixa promocional, ele se tornará uma faixa de carrossel giratória que permite aos clientes percorrerem todas as mensagens.</span><span class="sxs-lookup"><span data-stu-id="c4e77-108">If multiple messages are added to a promo banner module, it becomes a rotating carousel banner that lets customers cycle through all the messages.</span></span> 

<span data-ttu-id="c4e77-109">Os módulos de faixa promocional são controlados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="c4e77-109">Promo banner modules are driven by data from the content management system (CMS) and can be put on any page.</span></span>

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a><span data-ttu-id="c4e77-110">Exemplos de uso de faixas promocionais no comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="c4e77-110">Usage examples of promo banners in e-Commerce</span></span>

<span data-ttu-id="c4e77-111">As faixas promocionais podem ser usadas no cabeçalho do site para mostrar promoções ou mensagens em todo o site, como nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="c4e77-111">Promo banners can be used in the site header to show site-wide promotions or messages, as in the following examples.</span></span>

<span data-ttu-id="c4e77-112">"A venda anual termina em 10 dias"</span><span class="sxs-lookup"><span data-stu-id="c4e77-112">"Annual sale ends in 10 days"</span></span>

<span data-ttu-id="c4e77-113">"Economize bastante com a venda na volta às aulas.</span><span class="sxs-lookup"><span data-stu-id="c4e77-113">"Save big with back to school sale.</span></span> <span data-ttu-id="c4e77-114">Compre agora."</span><span class="sxs-lookup"><span data-stu-id="c4e77-114">Shop Now."</span></span>

<span data-ttu-id="c4e77-115">"Comprar em VENDA de ação de graças!"</span><span class="sxs-lookup"><span data-stu-id="c4e77-115">"Shop for Thanksgiving SALE!"</span></span> 

<span data-ttu-id="c4e77-116">A imagem a seguir mostra um exemplo de uma faixa promocional.</span><span class="sxs-lookup"><span data-stu-id="c4e77-116">The following image shows an example of a promo banner.</span></span>

![Exemplo de um módulo de faixa promocional](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a><span data-ttu-id="c4e77-118">Propriedades do módulo de faixa promocional</span><span class="sxs-lookup"><span data-stu-id="c4e77-118">Promo banner module properties</span></span>

| <span data-ttu-id="c4e77-119">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="c4e77-119">Property name</span></span>             | <span data-ttu-id="c4e77-120">Alíquota</span><span class="sxs-lookup"><span data-stu-id="c4e77-120">Value</span></span>                              | <span data-ttu-id="c4e77-121">descrição</span><span class="sxs-lookup"><span data-stu-id="c4e77-121">Description</span></span> |
|---------------------------|------------------------------------|-------------|
| <span data-ttu-id="c4e77-122">Mensagens da faixa</span><span class="sxs-lookup"><span data-stu-id="c4e77-122">Banner messages</span></span>           | <span data-ttu-id="c4e77-123">Textos e links</span><span class="sxs-lookup"><span data-stu-id="c4e77-123">Text and links</span></span>                     | <span data-ttu-id="c4e77-124">Uma matriz de texto e links.</span><span class="sxs-lookup"><span data-stu-id="c4e77-124">An array of text and links.</span></span> |
| <span data-ttu-id="c4e77-125">Reprodução automática</span><span class="sxs-lookup"><span data-stu-id="c4e77-125">Autoplay</span></span>                  | <span data-ttu-id="c4e77-126">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="c4e77-126">**True** or **False**</span></span>              | <span data-ttu-id="c4e77-127">Um valor que indica se é possível percorrer automaticamente as mensagens caso várias mensagens estejam configuradas.</span><span class="sxs-lookup"><span data-stu-id="c4e77-127">A value that indicates whether messages are automatically cycled through, if multiple messages are configured.</span></span> |
| <span data-ttu-id="c4e77-128">Intervalo de transição de slides</span><span class="sxs-lookup"><span data-stu-id="c4e77-128">Slide transition interval</span></span> | <span data-ttu-id="c4e77-129">Um número de milissegundos (ms)</span><span class="sxs-lookup"><span data-stu-id="c4e77-129">A number of milliseconds (ms)</span></span>      | <span data-ttu-id="c4e77-130">O intervalo usado para percorrer as mensagens.</span><span class="sxs-lookup"><span data-stu-id="c4e77-130">The interval that is used to cycle through messages.</span></span> |
| <span data-ttu-id="c4e77-131">Permitir ignorar</span><span class="sxs-lookup"><span data-stu-id="c4e77-131">Allow dismiss</span></span>             | <span data-ttu-id="c4e77-132">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="c4e77-132">**True** or **False**</span></span>              | <span data-ttu-id="c4e77-133">Se o valor estiver definido como **Verdadeiro**, os clientes poderão dispensar o alerta.</span><span class="sxs-lookup"><span data-stu-id="c4e77-133">If the value is set to **True**, customers can dismiss the alert.</span></span> |
| <span data-ttu-id="c4e77-134">Mostrar palheta do carrossel</span><span class="sxs-lookup"><span data-stu-id="c4e77-134">Show carousel flipper</span></span>     | <span data-ttu-id="c4e77-135">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="c4e77-135">**True** or **False**</span></span>              | <span data-ttu-id="c4e77-136">Um valor que indica se as palhetas do carrossel devem ser mostradas, de forma que os clientes possam percorrer vários itens de faixa manualmente.</span><span class="sxs-lookup"><span data-stu-id="c4e77-136">A value that indicates whether the carousel flippers should be shown, so that customers can manually cycle through multiple banner items.</span></span> |
| <span data-ttu-id="c4e77-137">Alinhamento de texto</span><span class="sxs-lookup"><span data-stu-id="c4e77-137">Text alignment</span></span>            | <span data-ttu-id="c4e77-138">**Direito**, **Esquerdo** ou **Centro**</span><span class="sxs-lookup"><span data-stu-id="c4e77-138">**Right**, **Left**, or **Center**</span></span> | <span data-ttu-id="c4e77-139">O alinhamento do texto no módulo de faixa promocional.</span><span class="sxs-lookup"><span data-stu-id="c4e77-139">The text alignment in the promo banner module.</span></span> |
| <span data-ttu-id="c4e77-140">Vincular</span><span class="sxs-lookup"><span data-stu-id="c4e77-140">Link</span></span>                      | <span data-ttu-id="c4e77-141">URL A</span><span class="sxs-lookup"><span data-stu-id="c4e77-141">A URL</span></span>                              | <span data-ttu-id="c4e77-142">A URL para um link opcional.</span><span class="sxs-lookup"><span data-stu-id="c4e77-142">The URL for an optional link.</span></span> |

## <a name="add-a-promo-banner-module-to-a-page"></a><span data-ttu-id="c4e77-143">Adicionar um módulo de faixa promocional a uma página</span><span class="sxs-lookup"><span data-stu-id="c4e77-143">Add a promo banner module to a page</span></span> 

<span data-ttu-id="c4e77-144">Para adicionar um módulo de faixa promocional a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c4e77-144">To add a promo banner module to a page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="c4e77-145">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="c4e77-145">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="c4e77-146">Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira **Modelo do banner da promoção** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4e77-146">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="c4e77-147">Em **Estrutura de Tópicos de Página**, adicione um módulo **Página padrão** ao slot **Corpo**.</span><span class="sxs-lookup"><span data-stu-id="c4e77-147">Under **Page Outline**, add a **Default page** module to the **Body** slot.</span></span> 
1. <span data-ttu-id="c4e77-148">Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="c4e77-148">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 
1. <span data-ttu-id="c4e77-149">Use o modelo que você acabou de criar para criar uma página com o nome **Página de faixa promocional**.</span><span class="sxs-lookup"><span data-stu-id="c4e77-149">Use the template that you just created to create a page that is named **Promo banner page**.</span></span> 
1. <span data-ttu-id="c4e77-150">No slot **Principal** da nova página, adicione um módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="c4e77-150">In the **Main** slot of the new page, add a container module.</span></span> 
1. <span data-ttu-id="c4e77-151">No painel à direita, defina o valor da **Largura** como **Preencher Contêiner**.</span><span class="sxs-lookup"><span data-stu-id="c4e77-151">In the pane on the right, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="c4e77-152">Em **Estrutura de Tópicos de Página**, adicione um módulo de faixa promocional ao módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="c4e77-152">Under **Page Outline**, add a promo banner module to the container module.</span></span>
1. <span data-ttu-id="c4e77-153">Nas configurações do módulo de faixa, adicione uma ou mais mensagens de faixa.</span><span class="sxs-lookup"><span data-stu-id="c4e77-153">In the settings for the banner module, add one or more banner messages.</span></span> <span data-ttu-id="c4e77-154">Cada mensagem pode ter texto juntamente com um link.</span><span class="sxs-lookup"><span data-stu-id="c4e77-154">Each message can have text together with a link.</span></span> <span data-ttu-id="c4e77-155">É possível editar as outras propriedades para personalizar ainda mais o módulo.</span><span class="sxs-lookup"><span data-stu-id="c4e77-155">You can edit the other properties to customize the module further.</span></span>
1. <span data-ttu-id="c4e77-156">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="c4e77-156">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="c4e77-157">Na parte superior da página, você verá um alerta que mostra o texto que você adicionou.</span><span class="sxs-lookup"><span data-stu-id="c4e77-157">At the top of the page, you should see an alert that shows the text that you added.</span></span>
1. <span data-ttu-id="c4e77-158">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="c4e77-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="c4e77-159">Em geral, uma faixa promocional é usada no slot do cabeçalho da página ou em um slot de subcabeçalho.</span><span class="sxs-lookup"><span data-stu-id="c4e77-159">A promo banner is typically used in the page header slot or a subheader slot.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="c4e77-160">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c4e77-160">Additional resources</span></span>

[<span data-ttu-id="c4e77-161">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="c4e77-161">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c4e77-162">Módulo do carrossel</span><span class="sxs-lookup"><span data-stu-id="c4e77-162">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="c4e77-163">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="c4e77-163">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="c4e77-164">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="c4e77-164">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="c4e77-165">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="c4e77-165">Video player module</span></span>](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]