---
title: Módulo de compartilhamento social
description: Este tópico abrange os módulos de compartilhamento social e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 82a8795360f453cdee19fa6e9e376a42e8276849
ms.sourcegitcommit: 69075e001d1fb4ef69282667052cd8d082273094
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022066"
---
# <a name="social-share-module"></a><span data-ttu-id="097ee-103">Módulo de compartilhamento social</span><span class="sxs-lookup"><span data-stu-id="097ee-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="097ee-104">Este tópico abrange os módulos de compartilhamento social e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="097ee-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="097ee-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="097ee-105">Overview</span></span>

<span data-ttu-id="097ee-106">Os modelos de compartilhamento social permitem que os usuários compartilhem as URLs de páginas de site de comércio eletrônico em mídias sociais, como Facebook, Twitter, Pinterest e LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="097ee-106">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="097ee-107">As URLs da página do site também podem ser compartilhadas por email.</span><span class="sxs-lookup"><span data-stu-id="097ee-107">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="097ee-108">Os módulos de compartilhamento social são geralmente usados em páginas de detalhes do produto (PDPs) para ajudar os usuários a compartilhar informações.</span><span class="sxs-lookup"><span data-stu-id="097ee-108">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="097ee-109">Cada módulo de compartilhamento social é um contêiner de módulos de item de compartilhamento social.</span><span class="sxs-lookup"><span data-stu-id="097ee-109">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="097ee-110">Cada módulo de item de compartilhamento social pode ser configurado para apontar para um site de mídia social específico.</span><span class="sxs-lookup"><span data-stu-id="097ee-110">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="097ee-111">A integração com o Facebook, o Twitter, o Pinterest, o LinkedIn e o email tem suporte imediato.</span><span class="sxs-lookup"><span data-stu-id="097ee-111">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="097ee-112">Quando um usuário do site seleciona um símbolo de mídia social, um iFrame HTML é iniciado para o respectivo site de mídia social.</span><span class="sxs-lookup"><span data-stu-id="097ee-112">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="097ee-113">No iFrame, o usuário pode entrar e publicar o conteúdo da página sendo exibida.</span><span class="sxs-lookup"><span data-stu-id="097ee-113">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="097ee-114">Cada plataforma de mídia social pode rastrear cookies, portanto, este módulo requer que os usuários do site aceitem a mensagem de notificação de consentimento de cookie.</span><span class="sxs-lookup"><span data-stu-id="097ee-114">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="097ee-115">Quando o consentimento do cookie não foi aceito, o módulo ficará oculto na página.</span><span class="sxs-lookup"><span data-stu-id="097ee-115">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="097ee-116">Para obter mais informações, consulte [Conformidade do cookie](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="097ee-116">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="097ee-117">A ilustração a seguir destaca um exemplo de módulo de compartilhamento social usado na página de detalhes de um produto.</span><span class="sxs-lookup"><span data-stu-id="097ee-117">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Exemplo de um módulo de compartilhamento social](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="097ee-119">Propriedades do módulo de compartilhamento social</span><span class="sxs-lookup"><span data-stu-id="097ee-119">Social share module properties</span></span>

| <span data-ttu-id="097ee-120">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="097ee-120">Property name</span></span>             | <span data-ttu-id="097ee-121">Alíquota</span><span class="sxs-lookup"><span data-stu-id="097ee-121">Value</span></span>                 | <span data-ttu-id="097ee-122">descrição</span><span class="sxs-lookup"><span data-stu-id="097ee-122">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="097ee-123">Legenda</span><span class="sxs-lookup"><span data-stu-id="097ee-123">Caption</span></span>                  | <span data-ttu-id="097ee-124">Texto</span><span class="sxs-lookup"><span data-stu-id="097ee-124">Text</span></span> | <span data-ttu-id="097ee-125">Esta propriedade especifica uma legenda para o módulo.</span><span class="sxs-lookup"><span data-stu-id="097ee-125">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="097ee-126">Orientação</span><span class="sxs-lookup"><span data-stu-id="097ee-126">Orientation</span></span> | <span data-ttu-id="097ee-127">**Horizontal** ou **Vertical**</span><span class="sxs-lookup"><span data-stu-id="097ee-127">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="097ee-128">Esta propriedade define a orientação do layout para os itens de mídia social.</span><span class="sxs-lookup"><span data-stu-id="097ee-128">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="097ee-129">Propriedades do módulo do item de compartilhamento social</span><span class="sxs-lookup"><span data-stu-id="097ee-129">Social share item module properties</span></span>
| <span data-ttu-id="097ee-130">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="097ee-130">Property name</span></span>             | <span data-ttu-id="097ee-131">Alíquota</span><span class="sxs-lookup"><span data-stu-id="097ee-131">Value</span></span>                 | <span data-ttu-id="097ee-132">descrição</span><span class="sxs-lookup"><span data-stu-id="097ee-132">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="097ee-133">Mídia social</span><span class="sxs-lookup"><span data-stu-id="097ee-133">Social media</span></span>              | <span data-ttu-id="097ee-134">**Facebook** , **Twitter** , **Pinterest** , **LinkedIn** , **Email**</span><span class="sxs-lookup"><span data-stu-id="097ee-134">**Facebook** , **Twitter** , **Pinterest** , **LinkedIn** , **Mail**</span></span> | <span data-ttu-id="097ee-135">Um menu suspenso com uma lista de plataformas de mídia social.</span><span class="sxs-lookup"><span data-stu-id="097ee-135">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="097ee-136">Ícone</span><span class="sxs-lookup"><span data-stu-id="097ee-136">Icon</span></span> |<span data-ttu-id="097ee-137">Imagem</span><span class="sxs-lookup"><span data-stu-id="097ee-137">Image</span></span>    | <span data-ttu-id="097ee-138">Esta será a imagem que será exibida para a respectiva mídia social.</span><span class="sxs-lookup"><span data-stu-id="097ee-138">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="097ee-139">Como prática recomendada, consulte o SDK da plataforma de mídia social para obter a imagem recomendada a ser usada para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="097ee-139">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="097ee-140">Adicionar um módulo de compartilhamento social a um módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="097ee-140">Add a social share module to a buy box module</span></span>

<span data-ttu-id="097ee-141">Para adicionar um módulo de compartilhamento social a um módulo de caixa de compra, execute as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="097ee-141">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="097ee-142">No site Fabrikam, selecione **Páginas** e depois selecione a página **DefaultPDP** para abrir a página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="097ee-142">In the Fabrikam site, select **Pages** , and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="097ee-143">No slot **Caixa de compra (obrigatório)** , selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="097ee-143">In the **Buybox (required)** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="097ee-144">Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Compartilhamento Social** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="097ee-144">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="097ee-145">No slot **Compartilhamento Social** , selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="097ee-145">In the **Social Share** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="097ee-146">Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Compartilhamento Social** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="097ee-146">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="097ee-147">No painel de propriedades do módulo **Compartilhamento Social** , em **Orientação** , selecione **Horizontal**.</span><span class="sxs-lookup"><span data-stu-id="097ee-147">In the properties pane of the **SocialShare** module, under **Orientation** , select **Horizontal**.</span></span> <span data-ttu-id="097ee-148">Adicione uma legenda conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="097ee-148">Add a caption as needed.</span></span>
1. <span data-ttu-id="097ee-149">No slot **Compartilhamento Social** , selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="097ee-149">In the **SocialShare** slot, select the ellipsis ( **...** ), and then select **Add Module**.</span></span>
1. <span data-ttu-id="097ee-150">Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Item de Compartilhamento Social** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="097ee-150">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="097ee-151">No painel de propriedades do módulo **Item de Compartilhamento Social** , em **Mídia Social** , selecione **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="097ee-151">In the properties pane of the **SocialShareItem** module, under **Social Media** , select **Facebook**.</span></span>
1. <span data-ttu-id="097ee-152">No painel de propriedades do módulo Item de **Item de Compartilhamento Social** , em **Ícone** , selecione **+ Adicionar imagem**.</span><span class="sxs-lookup"><span data-stu-id="097ee-152">In the properties pane of the **SocialShareItem** module, under **Icon** , select **+ Add an image**.</span></span>
1. <span data-ttu-id="097ee-153">Na caixa de diálogo **Seletor de mídia** , selecione a imagem do logotipo do Facebook e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="097ee-153">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="097ee-154">Se não houver uma imagem de logotipo do Facebook, selecione **Carregar novo item de mídia** para carregar uma imagem.</span><span class="sxs-lookup"><span data-stu-id="097ee-154">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="097ee-155">Adicione e configure módulos adicionais de **Item de Compartilhamento Social** conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="097ee-155">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="097ee-156">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="097ee-156">Select **Save** , and then select **Preview** to preview the page.</span></span> <span data-ttu-id="097ee-157">A página exibirá o módulo de compartilhamento social.</span><span class="sxs-lookup"><span data-stu-id="097ee-157">The page will show the social share module.</span></span>
1. <span data-ttu-id="097ee-158">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="097ee-158">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="097ee-159">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="097ee-159">Additional resources</span></span>

[<span data-ttu-id="097ee-160">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="097ee-160">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="097ee-161">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="097ee-161">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="097ee-162">Compatível com cookies</span><span class="sxs-lookup"><span data-stu-id="097ee-162">Cookie compliance</span></span>](cookie-compliance.md)
