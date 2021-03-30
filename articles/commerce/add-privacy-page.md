---
title: Adicionar página de política de privacidade
description: Este tópico descreve como adicionar uma página de política de privacidade ao seu site no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 07a806ac040df9dee284e2466629221fbc3403a4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209266"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="3e755-103">Adicionar página de política de privacidade</span><span class="sxs-lookup"><span data-stu-id="3e755-103">Add a privacy policy page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3e755-104">Este tópico descreve como adicionar uma página de política de privacidade ao seu site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e755-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3e755-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="3e755-105">Overview</span></span>

<span data-ttu-id="3e755-106">A conformidade com privacidade inclui medidas organizacionais que informam os usuários do site sobre como os dados são coletados e manipulados.</span><span class="sxs-lookup"><span data-stu-id="3e755-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="3e755-107">Os usuários podem então decidir como querem que seus dados pessoais sejam manuseados e podem tomar a ação apropriada.</span><span class="sxs-lookup"><span data-stu-id="3e755-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="3e755-108">Rever a declaração de privacidade da Microsoft em Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="3e755-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="3e755-109">Para revisar a declaração de privacidade da Microsoft enquanto você está nas ferramentas de criação Dynamics 365 Commerce, selecione o botão **Ajuda** (**?**) no canto superior direito, e depois selecione **Privacidade e cookies**.</span><span class="sxs-lookup"><span data-stu-id="3e755-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="3e755-110">Uma nova guia é aberta e tem um link para a [Declaração de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="3e755-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="3e755-111">Criar uma página de política de privacidade para o seu site</span><span class="sxs-lookup"><span data-stu-id="3e755-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="3e755-112">No Dynamics 365 Commerce, há várias maneiras de fornecer aos usuários do site acesso à sua política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="3e755-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="3e755-113">Esta seção mostra como criar uma página de política de privacidade e, depois, faz referência à página usando um fragmento de rodapé.</span><span class="sxs-lookup"><span data-stu-id="3e755-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="3e755-114">A diretriz a seguir é um exemplo que mostra como criar uma página de diretiva de privacidade genérica para um site de comércio.</span><span class="sxs-lookup"><span data-stu-id="3e755-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="3e755-115">Você é responsável por criar e implementar uma solução de página de diretiva de privacidade que atende melhor aos requisitos legais da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="3e755-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="3e755-116">Para iniciar, nas ferramentas de criação, vá para o site para o qual você deseja criar uma página de política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="3e755-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="3e755-117">Criar um modelo</span><span class="sxs-lookup"><span data-stu-id="3e755-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="3e755-118">Se um modelo que pode ser usado para a página política de privacidade já foi criado, pule para a seção de página [Criar uma política de privacidade](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="3e755-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="3e755-119">Para criar um modelo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e755-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="3e755-120">Vá para **Modelos** e selecione **Novo** para criar um modelo de página.</span><span class="sxs-lookup"><span data-stu-id="3e755-120">Go to **Templates**, and then select **New** to create a page template.</span></span>
1. <span data-ttu-id="3e755-121">Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira **Modelo do banner da promoção** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e755-121">In the **New Template** dialog box, under **Template Name**, enter **Promo banner template**, and then select **OK**.</span></span>
1. <span data-ttu-id="3e755-122">No modelo, adicione os módulos necessários aos slots de página necessários.</span><span class="sxs-lookup"><span data-stu-id="3e755-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="3e755-123">Para obter orientação, passe o mouse sobre os pontos de exclamação vermelhos.</span><span class="sxs-lookup"><span data-stu-id="3e755-123">For guidance, hover over the red exclamation marks.</span></span> <span data-ttu-id="3e755-124">(Por exemplo, o slot **Head do HTML** pode precisar de um módulo **Script externo padrão**.)</span><span class="sxs-lookup"><span data-stu-id="3e755-124">(For example, the **HTML Head** slot might require a **Default External Script** module.)</span></span>
1. <span data-ttu-id="3e755-125">No slot **Corpo**, adicione um módulo **Página padrão**.</span><span class="sxs-lookup"><span data-stu-id="3e755-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="3e755-126">No módulo **Página padrão**, no slot **Principal**, adicione um módulo **Bloco de conteúdo sofisticado**.</span><span class="sxs-lookup"><span data-stu-id="3e755-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="3e755-127">No módulo **Bloco de conteúdo sofisticado**, adicione um módulo **Item de bloco de conteúdo sofisticado**.</span><span class="sxs-lookup"><span data-stu-id="3e755-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="3e755-128">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="3e755-128">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="3e755-129">Criar uma página de política de privacidade</span><span class="sxs-lookup"><span data-stu-id="3e755-129">Build a privacy policy page</span></span>

<span data-ttu-id="3e755-130">Para criar uma página de política de privacidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e755-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="3e755-131">Vá para **Páginas** e selecione **Novo** para criar uma página.</span><span class="sxs-lookup"><span data-stu-id="3e755-131">Go to **Pages**, and then select **New** to create a page.</span></span>
1. <span data-ttu-id="3e755-132">Na caixa de diálogo **Escolha um modelo**, selecione o modelo para a página da política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="3e755-132">In the **Choose a template** dialog box, select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="3e755-133">Insira um nome de página e a URL da página, e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e755-133">Enter a page name and page URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="3e755-134">No slot **Principal** da página, adicione um módulo **Bloco de conteúdo sofisticado**.</span><span class="sxs-lookup"><span data-stu-id="3e755-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="3e755-135">No módulo **Bloco de conteúdo sofisticado**, adicione um módulo **Item de bloco de conteúdo sofisticado**.</span><span class="sxs-lookup"><span data-stu-id="3e755-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="3e755-136">No painel de propriedades do módulo **Bloco de conteúdo sofisticado**, selecione **Adicionar Fonte de Dados**, e depois selecione **Conteúdo de Rich Text**.</span><span class="sxs-lookup"><span data-stu-id="3e755-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="3e755-137">No editor de Rich Text, insira o conteúdo da página de política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="3e755-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="3e755-138">Expanda o editor de Rich Text para o modo de tela inteira, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e755-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="3e755-139">Ao concluir a inserção de conteúdo, selecione **Visualização** para visualizar a página no navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="3e755-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="3e755-140">Preencha as adições restantes nas propriedades de página e módulo.</span><span class="sxs-lookup"><span data-stu-id="3e755-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="3e755-141">Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="3e755-141">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="3e755-142">Para publicar a URL para a página de política de privacidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e755-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="3e755-143">Vá para **URLs** e selecione a URL para a página de política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="3e755-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="3e755-144">Selecione **Publicar** para publicar a URL selecionada.</span><span class="sxs-lookup"><span data-stu-id="3e755-144">Select **Publish** to publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="3e755-145">Crie um link para a página de política de privacidade em um rodapé</span><span class="sxs-lookup"><span data-stu-id="3e755-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="3e755-146">Você pode adicionar um link à página de política de privacidade a um fragmento.</span><span class="sxs-lookup"><span data-stu-id="3e755-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="3e755-147">Dessa forma, você pode compartilhar o link e atualizá-lo em várias páginas do site referenciando o fragmento.</span><span class="sxs-lookup"><span data-stu-id="3e755-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="3e755-148">Este exemplo mostra como adicionar um link à página de política de privacidade a um fragmento de rodapé.</span><span class="sxs-lookup"><span data-stu-id="3e755-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="3e755-149">Para adicionar um link a um fragmento de rodapé, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e755-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="3e755-150">Vá para **Fragmentos** e selecione **Novo** para criar um fragmento de página.</span><span class="sxs-lookup"><span data-stu-id="3e755-150">Go to **Fragments**, and then select **New** to create a page fragment.</span></span>
1. <span data-ttu-id="3e755-151">Na caixa de diálogo **Novo fragmento**, selecione o módulo **Rodapé**.</span><span class="sxs-lookup"><span data-stu-id="3e755-151">In the **New fragment** dialog box, select the **Footer** module.</span></span>
1. <span data-ttu-id="3e755-152">Em **Nome do fragmento**, digite um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e755-152">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="3e755-153">No slot **Categoria de rodapé**, adicione um módulo de **Item de cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="3e755-153">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="3e755-154">No painel de propriedades à direita, selecione **Vincular texto**.</span><span class="sxs-lookup"><span data-stu-id="3e755-154">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="3e755-155">Na caixa de diálogo **Vincular texto**, insira o texto de link e destino do link da página de política de privacidade, e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e755-155">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>
1. <span data-ttu-id="3e755-156">Para obter a URL da página de política de privacidade, vá para **Páginas**, vá para a página de política de privacidade e copie a URL do painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="3e755-156">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>
1. <span data-ttu-id="3e755-157">Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="3e755-157">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="3e755-158">Visualize o fragmento e teste o link da página de política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="3e755-158">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="3e755-159">Agora, o fragmento pode ser referenciado no modelo para outras páginas do site.</span><span class="sxs-lookup"><span data-stu-id="3e755-159">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="3e755-160">Quando este fragmento é referenciado no módulo **rodapé** de um modelo, a referência de link aparece em todas as páginas criadas com o uso desse modelo.</span><span class="sxs-lookup"><span data-stu-id="3e755-160">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e755-161">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3e755-161">Additional resources</span></span>

[<span data-ttu-id="3e755-162">Visão geral de conformidade</span><span class="sxs-lookup"><span data-stu-id="3e755-162">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="3e755-163">Recursos e funcionalidades de acessibilidade</span><span class="sxs-lookup"><span data-stu-id="3e755-163">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="3e755-164">Compatível com cookies</span><span class="sxs-lookup"><span data-stu-id="3e755-164">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="3e755-165">Substitua os IDs de usuário associados às alterações de conteúdo controladas</span><span class="sxs-lookup"><span data-stu-id="3e755-165">Replace user IDs associated with tracked content changes</span></span>](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]