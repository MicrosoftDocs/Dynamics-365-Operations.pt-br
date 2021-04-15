---
title: Módulo de compartilhamento social
description: Este tópico abrange os módulos de compartilhamento social e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: c34410a8c817de9fed350bf2cd2dd918a37c230f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795348"
---
# <a name="social-share-module"></a><span data-ttu-id="46702-103">Módulo de compartilhamento social</span><span class="sxs-lookup"><span data-stu-id="46702-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="46702-104">Este tópico abrange os módulos de compartilhamento social e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="46702-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="46702-105">Os modelos de compartilhamento social permitem que os usuários compartilhem as URLs de páginas de site de comércio eletrônico em mídias sociais, como Facebook, Twitter, Pinterest e LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="46702-105">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="46702-106">As URLs da página do site também podem ser compartilhadas por email.</span><span class="sxs-lookup"><span data-stu-id="46702-106">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="46702-107">Os módulos de compartilhamento social são geralmente usados em páginas de detalhes do produto (PDPs) para ajudar os usuários a compartilhar informações.</span><span class="sxs-lookup"><span data-stu-id="46702-107">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="46702-108">Cada módulo de compartilhamento social é um contêiner de módulos de item de compartilhamento social.</span><span class="sxs-lookup"><span data-stu-id="46702-108">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="46702-109">Cada módulo de item de compartilhamento social pode ser configurado para apontar para um site de mídia social específico.</span><span class="sxs-lookup"><span data-stu-id="46702-109">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="46702-110">A integração com o Facebook, o Twitter, o Pinterest, o LinkedIn e o email tem suporte imediato.</span><span class="sxs-lookup"><span data-stu-id="46702-110">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="46702-111">Quando um usuário do site seleciona um símbolo de mídia social, um iFrame HTML é iniciado para o respectivo site de mídia social.</span><span class="sxs-lookup"><span data-stu-id="46702-111">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="46702-112">No iFrame, o usuário pode entrar e publicar o conteúdo da página sendo exibida.</span><span class="sxs-lookup"><span data-stu-id="46702-112">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="46702-113">Cada plataforma de mídia social pode rastrear cookies, portanto, este módulo requer que os usuários do site aceitem a mensagem de notificação de consentimento de cookie.</span><span class="sxs-lookup"><span data-stu-id="46702-113">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="46702-114">Quando o consentimento do cookie não foi aceito, o módulo ficará oculto na página.</span><span class="sxs-lookup"><span data-stu-id="46702-114">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="46702-115">Para obter mais informações, consulte [Conformidade do cookie](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="46702-115">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="46702-116">A ilustração a seguir destaca um exemplo de módulo de compartilhamento social usado na página de detalhes de um produto.</span><span class="sxs-lookup"><span data-stu-id="46702-116">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Exemplo de um módulo de compartilhamento social](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="46702-118">Propriedades do módulo de compartilhamento social</span><span class="sxs-lookup"><span data-stu-id="46702-118">Social share module properties</span></span>

| <span data-ttu-id="46702-119">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="46702-119">Property name</span></span>             | <span data-ttu-id="46702-120">Alíquota</span><span class="sxs-lookup"><span data-stu-id="46702-120">Value</span></span>                 | <span data-ttu-id="46702-121">descrição</span><span class="sxs-lookup"><span data-stu-id="46702-121">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="46702-122">Legenda</span><span class="sxs-lookup"><span data-stu-id="46702-122">Caption</span></span>                  | <span data-ttu-id="46702-123">Texto</span><span class="sxs-lookup"><span data-stu-id="46702-123">Text</span></span> | <span data-ttu-id="46702-124">Esta propriedade especifica uma legenda para o módulo.</span><span class="sxs-lookup"><span data-stu-id="46702-124">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="46702-125">Orientação</span><span class="sxs-lookup"><span data-stu-id="46702-125">Orientation</span></span> | <span data-ttu-id="46702-126">**Horizontal** ou **Vertical**</span><span class="sxs-lookup"><span data-stu-id="46702-126">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="46702-127">Esta propriedade define a orientação do layout para os itens de mídia social.</span><span class="sxs-lookup"><span data-stu-id="46702-127">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="46702-128">Propriedades do módulo do item de compartilhamento social</span><span class="sxs-lookup"><span data-stu-id="46702-128">Social share item module properties</span></span>
| <span data-ttu-id="46702-129">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="46702-129">Property name</span></span>             | <span data-ttu-id="46702-130">Alíquota</span><span class="sxs-lookup"><span data-stu-id="46702-130">Value</span></span>                 | <span data-ttu-id="46702-131">descrição</span><span class="sxs-lookup"><span data-stu-id="46702-131">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="46702-132">Mídia social</span><span class="sxs-lookup"><span data-stu-id="46702-132">Social media</span></span>              | <span data-ttu-id="46702-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Email**</span><span class="sxs-lookup"><span data-stu-id="46702-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="46702-134">Um menu suspenso com uma lista de plataformas de mídia social.</span><span class="sxs-lookup"><span data-stu-id="46702-134">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="46702-135">Ícone</span><span class="sxs-lookup"><span data-stu-id="46702-135">Icon</span></span> |<span data-ttu-id="46702-136">Imagem</span><span class="sxs-lookup"><span data-stu-id="46702-136">Image</span></span>    | <span data-ttu-id="46702-137">Esta será a imagem que será exibida para a respectiva mídia social.</span><span class="sxs-lookup"><span data-stu-id="46702-137">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="46702-138">Como prática recomendada, consulte o SDK da plataforma de mídia social para obter a imagem recomendada a ser usada para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="46702-138">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="46702-139">Adicionar um módulo de compartilhamento social a um módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="46702-139">Add a social share module to a buy box module</span></span>

<span data-ttu-id="46702-140">Para adicionar um módulo de compartilhamento social a um módulo de caixa de compra, execute as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="46702-140">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="46702-141">No site Fabrikam, selecione **Páginas** e depois selecione a página **DefaultPDP** para abrir a página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="46702-141">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="46702-142">No slot **Caixa de compra (obrigatório)**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="46702-142">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46702-143">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Compartilhamento Social** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="46702-143">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="46702-144">No slot **Compartilhamento Social**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="46702-144">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46702-145">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Compartilhamento Social** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="46702-145">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="46702-146">No painel de propriedades do módulo **Compartilhamento Social**, em **Orientação**, selecione **Horizontal**.</span><span class="sxs-lookup"><span data-stu-id="46702-146">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="46702-147">Adicione uma legenda conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="46702-147">Add a caption as needed.</span></span>
1. <span data-ttu-id="46702-148">No slot **Compartilhamento Social**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="46702-148">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46702-149">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Item de Compartilhamento Social** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="46702-149">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="46702-150">No painel de propriedades do módulo **Item de Compartilhamento Social**, em **Mídia Social**, selecione **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="46702-150">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="46702-151">No painel de propriedades do módulo Item de **Item de Compartilhamento Social**, em **Ícone**, selecione **+ Adicionar imagem**.</span><span class="sxs-lookup"><span data-stu-id="46702-151">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="46702-152">Na caixa de diálogo **Seletor de mídia**, selecione a imagem do logotipo do Facebook e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="46702-152">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="46702-153">Se não houver uma imagem de logotipo do Facebook, selecione **Carregar novo item de mídia** para carregar uma imagem.</span><span class="sxs-lookup"><span data-stu-id="46702-153">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="46702-154">Adicione e configure módulos adicionais de **Item de Compartilhamento Social** conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="46702-154">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="46702-155">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="46702-155">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="46702-156">A página exibirá o módulo de compartilhamento social.</span><span class="sxs-lookup"><span data-stu-id="46702-156">The page will show the social share module.</span></span>
1. <span data-ttu-id="46702-157">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="46702-157">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46702-158">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="46702-158">Additional resources</span></span>

[<span data-ttu-id="46702-159">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="46702-159">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="46702-160">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="46702-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="46702-161">Compatível com cookies</span><span class="sxs-lookup"><span data-stu-id="46702-161">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]