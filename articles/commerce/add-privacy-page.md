---
title: Adicionar página de política de privacidade
description: Este tópico descreve como adicionar uma página de política de privacidade ao seu site no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ee9a68f46c91299065732e5f65479906f9e06079
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001314"
---
# <a name="add-a-privacy-policy-page"></a><span data-ttu-id="44688-103">Adicionar página de política de privacidade</span><span class="sxs-lookup"><span data-stu-id="44688-103">Add a privacy policy page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="44688-104">Este tópico descreve como adicionar uma página de política de privacidade ao seu site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="44688-104">This topic describes how to add a privacy policy page to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="44688-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="44688-105">Overview</span></span>

<span data-ttu-id="44688-106">A conformidade com privacidade inclui medidas organizacionais que informam os usuários do site sobre como os dados são coletados e manipulados.</span><span class="sxs-lookup"><span data-stu-id="44688-106">Privacy compliance includes organizational measures that inform site users about how their data is collected and handled.</span></span> <span data-ttu-id="44688-107">Os usuários podem então decidir como querem que seus dados pessoais sejam manuseados e podem tomar a ação apropriada.</span><span class="sxs-lookup"><span data-stu-id="44688-107">Users can then decide how they want their personal data to be handled and can take appropriate action.</span></span>

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a><span data-ttu-id="44688-108">Rever a declaração de privacidade da Microsoft em Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="44688-108">Review the Microsoft privacy statement in Dynamics 365 Commerce</span></span>

<span data-ttu-id="44688-109">Para revisar a declaração de privacidade da Microsoft enquanto você está nas ferramentas de criação Dynamics 365 Commerce, selecione o botão **Ajuda** (**?**) no canto superior direito, e depois selecione **Privacidade e cookies**.</span><span class="sxs-lookup"><span data-stu-id="44688-109">To review the Microsoft privacy statement while you're signed in to the Dynamics 365 Commerce authoring tools, select the **Help** button (**?**) in the upper-right corner, and then select **Privacy and cookies**.</span></span> <span data-ttu-id="44688-110">Uma nova guia é aberta e tem um link para a [Declaração de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="44688-110">A new tab is opened that has a link to the [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

## <a name="build-a-privacy-policy-page-for-your-site"></a><span data-ttu-id="44688-111">Criar uma página de política de privacidade para o seu site</span><span class="sxs-lookup"><span data-stu-id="44688-111">Build a privacy policy page for your site</span></span>

<span data-ttu-id="44688-112">No Dynamics 365 Commerce, há várias maneiras de fornecer aos usuários do site acesso à sua política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="44688-112">In Dynamics 365 Commerce, there are several ways to give users of your site access to your privacy policy.</span></span> <span data-ttu-id="44688-113">Esta seção mostra como criar uma página de política de privacidade e, depois, faz referência à página usando um fragmento de rodapé.</span><span class="sxs-lookup"><span data-stu-id="44688-113">This section shows how to build a privacy policy page and then reference the page by using a footer fragment.</span></span>

<span data-ttu-id="44688-114">A diretriz a seguir é um exemplo que mostra como criar uma página de diretiva de privacidade genérica para um site de comércio.</span><span class="sxs-lookup"><span data-stu-id="44688-114">The guidance that follows is an example that shows how to build a generic privacy policy page for a Commerce site.</span></span> <span data-ttu-id="44688-115">Você é responsável por criar e implementar uma solução de página de diretiva de privacidade que atende melhor aos requisitos legais da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="44688-115">You're responsible for designing and implementing a privacy policy page solution that best meets your company's legal requirements.</span></span>

<span data-ttu-id="44688-116">Para iniciar, nas ferramentas de criação, vá para o site para o qual você deseja criar uma página de política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="44688-116">To start, in the authoring tools, go to the site that you want to build a privacy policy page for.</span></span>

### <a name="create-a-template"></a><span data-ttu-id="44688-117">Criar um modelo</span><span class="sxs-lookup"><span data-stu-id="44688-117">Create a template</span></span>

> [!NOTE]
> <span data-ttu-id="44688-118">Se um modelo que pode ser usado para a página política de privacidade já foi criado, pule para a seção de página [Criar uma política de privacidade](#build-a-privacy-policy-page).</span><span class="sxs-lookup"><span data-stu-id="44688-118">If a template that can be used for the privacy policy page has already been created, skip ahead to the [Build a privacy policy page](#build-a-privacy-policy-page) section.</span></span>

<span data-ttu-id="44688-119">Para criar um modelo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="44688-119">To create a template, follow these steps.</span></span>

1. <span data-ttu-id="44688-120">Vá para **Modelos \> Novo modelo**.</span><span class="sxs-lookup"><span data-stu-id="44688-120">Go to **Templates \> New Template**.</span></span>
1. <span data-ttu-id="44688-121">Insira o nome do modelo e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="44688-121">Enter the template name, and then select **OK**.</span></span>
1. <span data-ttu-id="44688-122">No modelo, adicione os módulos necessários aos slots de página necessários.</span><span class="sxs-lookup"><span data-stu-id="44688-122">In the template, add any required modules to the required page slots.</span></span> <span data-ttu-id="44688-123">Para obter orientação, passe o mouse sobre os pontos de exclamação vermelhos.</span><span class="sxs-lookup"><span data-stu-id="44688-123">For guidance, hover over the red exclamation marks.</span></span>

    <span data-ttu-id="44688-124">Por exemplo, o slot **Head do HTML** pode precisar de um módulo **Script externo padrão**.</span><span class="sxs-lookup"><span data-stu-id="44688-124">For example, the **HTML Head** slot might require a **Default External Script** module.</span></span>

1. <span data-ttu-id="44688-125">No slot **Corpo**, adicione um módulo **Página padrão**.</span><span class="sxs-lookup"><span data-stu-id="44688-125">In the **Body** slot, add a **Default Page** module.</span></span>
1. <span data-ttu-id="44688-126">No módulo **Página padrão**, no slot **Principal**, adicione um módulo **Bloco de conteúdo sofisticado**.</span><span class="sxs-lookup"><span data-stu-id="44688-126">In the **Default Page** module, in the **Main** slot, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="44688-127">No módulo **Bloco de conteúdo sofisticado**, adicione um módulo **Item de bloco de conteúdo sofisticado**.</span><span class="sxs-lookup"><span data-stu-id="44688-127">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="44688-128">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="44688-128">Check the template in, and publish it.</span></span>

### <a name="build-a-privacy-policy-page"></a><span data-ttu-id="44688-129">Criar uma página de política de privacidade</span><span class="sxs-lookup"><span data-stu-id="44688-129">Build a privacy policy page</span></span>

<span data-ttu-id="44688-130">Para criar uma página de política de privacidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="44688-130">To build a privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="44688-131">Vá para **Páginas \> Nova página**.</span><span class="sxs-lookup"><span data-stu-id="44688-131">Go to **Pages \> New Page**.</span></span>
1. <span data-ttu-id="44688-132">Selecione o modelo para a página política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="44688-132">Select the template for the privacy policy page.</span></span>
1. <span data-ttu-id="44688-133">Insira um nome de página e URL e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="44688-133">Enter a page name and URL, and then select **OK**.</span></span> 
1. <span data-ttu-id="44688-134">No slot **Principal** da página, adicione um módulo **Bloco de conteúdo sofisticado**.</span><span class="sxs-lookup"><span data-stu-id="44688-134">In the **Main** slot of the page, add a **Content Rich Block** module.</span></span>
1. <span data-ttu-id="44688-135">No módulo **Bloco de conteúdo sofisticado**, adicione um módulo **Item de bloco de conteúdo sofisticado**.</span><span class="sxs-lookup"><span data-stu-id="44688-135">In the **Content Rich Block** module, add a **Content rich block item** module.</span></span>
1. <span data-ttu-id="44688-136">No painel de propriedades do módulo **Bloco de conteúdo sofisticado**, selecione **Adicionar Fonte de Dados**, e depois selecione **Conteúdo de Rich Text**.</span><span class="sxs-lookup"><span data-stu-id="44688-136">In the properties pane for the **Content Rich Block** module, select **Add Data Source**, and then select **Rich Text Content**.</span></span>
1. <span data-ttu-id="44688-137">No editor de Rich Text, insira o conteúdo da página de política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="44688-137">In the rich text editor, enter the content for the privacy policy page.</span></span> <span data-ttu-id="44688-138">Expanda o editor de Rich Text para o modo de tela inteira, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="44688-138">Expand the rich text editor to full-screen mode as you require.</span></span>
1. <span data-ttu-id="44688-139">Ao concluir a inserção de conteúdo, selecione **Visualização** para visualizar a página no navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="44688-139">When you've finished entering content, select **Preview** to preview the page in the web browser.</span></span>
1. <span data-ttu-id="44688-140">Preencha as adições restantes nas propriedades de página e módulo.</span><span class="sxs-lookup"><span data-stu-id="44688-140">Complete any remaining additions to the page and module properties.</span></span>
1. <span data-ttu-id="44688-141">Verifique a página de política de privacidade e publique-a.</span><span class="sxs-lookup"><span data-stu-id="44688-141">Check the privacy policy page in, and publish it.</span></span>

<span data-ttu-id="44688-142">Para publicar a URL para a página de política de privacidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="44688-142">To publish the URL for the privacy policy page, follow these steps.</span></span>

1. <span data-ttu-id="44688-143">Vá para **URLs** e selecione a URL para a página de política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="44688-143">Go to **URLs**, and select the URL for the privacy policy page.</span></span>
1. <span data-ttu-id="44688-144">Publique a URL selecionada.</span><span class="sxs-lookup"><span data-stu-id="44688-144">Publish the selected URL.</span></span>

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a><span data-ttu-id="44688-145">Crie um link para a página de política de privacidade em um rodapé</span><span class="sxs-lookup"><span data-stu-id="44688-145">Create a link to the privacy policy page in a footer</span></span>

<span data-ttu-id="44688-146">Você pode adicionar um link à página de política de privacidade a um fragmento.</span><span class="sxs-lookup"><span data-stu-id="44688-146">You can add a link to the privacy policy page to a fragment.</span></span> <span data-ttu-id="44688-147">Dessa forma, você pode compartilhar o link e atualizá-lo em várias páginas do site referenciando o fragmento.</span><span class="sxs-lookup"><span data-stu-id="44688-147">In this way, you can share the link and update it across multiple site pages by referencing the fragment.</span></span> <span data-ttu-id="44688-148">Este exemplo mostra como adicionar um link à página de política de privacidade a um fragmento de rodapé.</span><span class="sxs-lookup"><span data-stu-id="44688-148">This example shows how to add a link to the privacy policy page to a footer fragment.</span></span>

<span data-ttu-id="44688-149">Para adicionar um link a um fragmento de rodapé, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="44688-149">To add a link to a footer fragment, follow these steps.</span></span>

1. <span data-ttu-id="44688-150">Vá para **Fragmentos de página \> Novo fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="44688-150">Go to **Page Fragments \> New Page Fragment**.</span></span>
1. <span data-ttu-id="44688-151">Selecione o módulo do **Cabeçalho** e insira um nome no campo nome **Nome do Fragmento de Página**.</span><span class="sxs-lookup"><span data-stu-id="44688-151">Select the **Footer** module, and then enter a name in the **Page Fragment Name** field.</span></span>
1. <span data-ttu-id="44688-152">No slot **Categoria de rodapé**, adicione um módulo de **Item de cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="44688-152">In the **Footer category** slot, add a **Footer item** module.</span></span>
1. <span data-ttu-id="44688-153">No painel de propriedades à direita, selecione **Vincular texto**.</span><span class="sxs-lookup"><span data-stu-id="44688-153">In the properties pane on the right, select **Link text**.</span></span>
1. <span data-ttu-id="44688-154">Na caixa de diálogo **Vincular texto**, insira o texto de link e destino do link da página de política de privacidade, e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="44688-154">In the **Link text** dialog box, enter the link text and link target of the privacy policy page, and then click **OK**.</span></span>

    <span data-ttu-id="44688-155">Para obter a URL da página de política de privacidade, vá para **Páginas**, vá para a página de política de privacidade e copie a URL do painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="44688-155">To get the URL of the privacy policy page, go to **Pages**, go to the privacy policy page, and copy the URL from the properties pane.</span></span>

1. <span data-ttu-id="44688-156">Salve o fragmento, insira-o e publique-o.</span><span class="sxs-lookup"><span data-stu-id="44688-156">Save the fragment, check it in, and publish it.</span></span>
1. <span data-ttu-id="44688-157">Visualize o fragmento e teste o link da página de política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="44688-157">Preview the fragment, and test the link to the privacy policy page.</span></span>

<span data-ttu-id="44688-158">Agora, o fragmento pode ser referenciado no modelo para outras páginas do site.</span><span class="sxs-lookup"><span data-stu-id="44688-158">The fragment can now be referenced in the template for other site pages.</span></span> <span data-ttu-id="44688-159">Quando este fragmento é referenciado no módulo **rodapé** de um modelo, a referência de link aparece em todas as páginas criadas com o uso desse modelo.</span><span class="sxs-lookup"><span data-stu-id="44688-159">When this fragment is referenced in the **Footer** module of a template, the link reference will appear on any pages that are built by using that template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="44688-160">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="44688-160">Additional resources</span></span>

[<span data-ttu-id="44688-161">Visão geral de conformidade</span><span class="sxs-lookup"><span data-stu-id="44688-161">Compliance overview</span></span>](compliance-overview.md)

[<span data-ttu-id="44688-162">Recursos e funcionalidades de acessibilidade</span><span class="sxs-lookup"><span data-stu-id="44688-162">Accessibility features and capabilities</span></span>](accessibility.md)

[<span data-ttu-id="44688-163">Compatível com cookies</span><span class="sxs-lookup"><span data-stu-id="44688-163">Cookie compliance</span></span>](cookie-compliance.md)
