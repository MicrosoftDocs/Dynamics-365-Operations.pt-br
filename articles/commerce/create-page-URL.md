---
title: Criar uma URL da página
description: Este tópico cobre conceitos básicos e os procedimentos para criar uma página na URL do site.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 98743d8948669f32d3c74e1915c7ed53db81141c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795682"
---
# <a name="create-a-page-url"></a><span data-ttu-id="68136-103">Criar uma URL da página</span><span class="sxs-lookup"><span data-stu-id="68136-103">Create a page URL</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="68136-104">Este tópico cobre conceitos básicos e os procedimentos para criar uma página na URL do site.</span><span class="sxs-lookup"><span data-stu-id="68136-104">This topic covers the basic concepts and procedures for creating a page URL on your site.</span></span>

<span data-ttu-id="68136-105">A URL total ou absoluta que aponta para uma página no site consiste em partes diferentes.</span><span class="sxs-lookup"><span data-stu-id="68136-105">The full, or absolute, URL that points to a page on your site consists of distinct parts.</span></span> <span data-ttu-id="68136-106">Por exemplo, a URL `https://www.contoso.com/en-us/contactus` tem as seguintes partes:</span><span class="sxs-lookup"><span data-stu-id="68136-106">For example, the URL `https://www.contoso.com/en-us/contactus` has the following parts:</span></span>

- <span data-ttu-id="68136-107">`https://www.contoso.com` – O protocolo do HTTP e o domínio do site.</span><span class="sxs-lookup"><span data-stu-id="68136-107">`https://www.contoso.com` – The HTTP protocol and the site's domain.</span></span>
- <span data-ttu-id="68136-108">`/en-us` – O caminho de idioma do site.</span><span class="sxs-lookup"><span data-stu-id="68136-108">`/en-us` – The site's language path.</span></span>
- <span data-ttu-id="68136-109">`/contactus` – A URL relacionada à página  **Fale conosco**.</span><span class="sxs-lookup"><span data-stu-id="68136-109">`/contactus` – The relative URL for the **Contact Us** page.</span></span> <span data-ttu-id="68136-110">Uma URL relacionada também é conhecida como uma URL *Campo de dados dinâmico*.</span><span class="sxs-lookup"><span data-stu-id="68136-110">A relative URL is also known as a URL *slug*.</span></span>

<span data-ttu-id="68136-111">Você estabelece o domínio do site e o caminho opcional do idioma quando configura o site.</span><span class="sxs-lookup"><span data-stu-id="68136-111">You establish your site's domain and optional language path when you set up the site.</span></span> <span data-ttu-id="68136-112">Você pode adicionar mais domínios e caminhos de idioma ao site por meio da página de armazenamento online nas configurações do site.</span><span class="sxs-lookup"><span data-stu-id="68136-112">You can add more domains and language paths to your site through the online stores page in the site's settings.</span></span>

<span data-ttu-id="68136-113">A URL de Campo de dados dinâmico de uma página existe como uma entidade autônoma no ambiente de criação do site.</span><span class="sxs-lookup"><span data-stu-id="68136-113">The URL slug for a page exists as a standalone entity in the site authoring environment.</span></span> <span data-ttu-id="68136-114">Uma página de URL é feita de duas partes: um nome que representa o Campo de dados dinâmico da URL e um ponteiro a uma página em seu site ou em um site externo.</span><span class="sxs-lookup"><span data-stu-id="68136-114">A page URL consists of two parts: a name that represents the URL slug, and a pointer to a page on either your site or an external site.</span></span> <span data-ttu-id="68136-115">Uma página URL também pode ser configurada para agir como um redirecionamento a outra página em seu site ou em um site externo.</span><span class="sxs-lookup"><span data-stu-id="68136-115">A page URL can also be configured to act as a redirect to another page on either your site or an external site.</span></span>

## <a name="create-a-page-url"></a><span data-ttu-id="68136-116">Criar uma URL da página</span><span class="sxs-lookup"><span data-stu-id="68136-116">Create a page URL</span></span>

<span data-ttu-id="68136-117">Há duas maneiras de criar a URLs de página:</span><span class="sxs-lookup"><span data-stu-id="68136-117">There are two ways to create page URLs:</span></span>

- <span data-ttu-id="68136-118">Automaticamente, quando você cria uma página</span><span class="sxs-lookup"><span data-stu-id="68136-118">Automatically, when you create a page</span></span>
- <span data-ttu-id="68136-119">Manualmente, da página de **URLs**</span><span class="sxs-lookup"><span data-stu-id="68136-119">Manually, from the **URLs** page</span></span>

### <a name="create-a-page-url-when-you-create-a-page"></a><span data-ttu-id="68136-120">Crie uma URL da página ao criar uma página</span><span class="sxs-lookup"><span data-stu-id="68136-120">Create a page URL when you create a page</span></span>

<span data-ttu-id="68136-121">Se fornecer um nome no campo **URL** quando você cria uma nova página, uma URL de página que aponta para essa página será criada automaticamente na **URL**.</span><span class="sxs-lookup"><span data-stu-id="68136-121">If you provide a name in the **URL** field when you create a new page, a page URL that points to that page is automatically created on the **URLs** page.</span></span> <span data-ttu-id="68136-122">Após publicar a URL e a página que a redireciona, os usuários de sites (os clientes) podem acessar a página associada à URL.</span><span class="sxs-lookup"><span data-stu-id="68136-122">After you publish the URL and the page that it points to, site users (your customers) can access the page that is associated with the URL.</span></span>

> [!NOTE]
> <span data-ttu-id="68136-123">Se você um publica uma URL sem publicar a página que redireciona, os usuários recebem um erro 404 quando tentar acessar a página.</span><span class="sxs-lookup"><span data-stu-id="68136-123">If you publish a URL without publishing the page that it points to, site users receive a 404 error when they try to access the page.</span></span> <span data-ttu-id="68136-124">Se você publicar páginas sem publicar a URL que a redireciona, a página não pode ser acessada usando uma URL.</span><span class="sxs-lookup"><span data-stu-id="68136-124">If you publish a page without publishing the URL that points to it, the page can't be accessed by using a URL.</span></span>

### <a name="manually-create-a-page-url"></a><span data-ttu-id="68136-125">Crie manualmente uma URL da página</span><span class="sxs-lookup"><span data-stu-id="68136-125">Manually create a page URL</span></span>

<span data-ttu-id="68136-126">Quando você cria novas páginas, não é necessário especificar uma URL da página.</span><span class="sxs-lookup"><span data-stu-id="68136-126">When you create new pages, you aren't required to specify a page URL.</span></span> <span data-ttu-id="68136-127">Se você deixar o campo da URL em branco, a página é criada em um estado não vinculado.</span><span class="sxs-lookup"><span data-stu-id="68136-127">If you leave the URL field blank, the page is created in an unlinked state.</span></span> <span data-ttu-id="68136-128">Nesse caso, os clientes não poderão acessar a página, mesmo se estiver publicada.</span><span class="sxs-lookup"><span data-stu-id="68136-128">In this case, customers won't be able to access the page, even if it's published.</span></span> <span data-ttu-id="68136-129">Para tornar a página acessível, você deverá criar manualmente a URL e vinculá-lo a página.</span><span class="sxs-lookup"><span data-stu-id="68136-129">To make the page accessible, you must manually create the URL and link it to the page.</span></span>

<span data-ttu-id="68136-130">Para criar manualmente a URL de página para uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="68136-130">To manually create the page URL for a page, follow these steps.</span></span>

1. <span data-ttu-id="68136-131">Na página **URLs**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="68136-131">On the **URLs** page, select **New**.</span></span>
1. <span data-ttu-id="68136-132">Selecione a página do site para associar com a URL.</span><span class="sxs-lookup"><span data-stu-id="68136-132">Select the site page to associate with the URL.</span></span>
1. <span data-ttu-id="68136-133">Insira a URL de Campo de dados dinâmico e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="68136-133">Enter the URL slug, and then select **OK**.</span></span>

<span data-ttu-id="68136-134">Nesse momento, a URL em um estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="68136-134">At this point, the URL is in a draft state.</span></span> <span data-ttu-id="68136-135">Deve ser publicada antes que os usuários possam acessar o site da página associada.</span><span class="sxs-lookup"><span data-stu-id="68136-135">It must be published before site users can access the associated page.</span></span>

## <a name="update-a-page-url"></a><span data-ttu-id="68136-136">Atualizar uma URL da página</span><span class="sxs-lookup"><span data-stu-id="68136-136">Update a page URL</span></span>

<span data-ttu-id="68136-137">Para atualizar a página de destino de uma URL de página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="68136-137">To update the target page of a page URL, follow these steps.</span></span>

1. <span data-ttu-id="68136-138">Na página de **URLs**, selecione a URL para atualizar.</span><span class="sxs-lookup"><span data-stu-id="68136-138">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="68136-139">No painel de propriedade à direita, selecione o botão de reticências (**...**) ao lado do campo da página de destino.</span><span class="sxs-lookup"><span data-stu-id="68136-139">In the property pane on the right, select the ellipsis button (**...**) next to the target page field.</span></span>
1. <span data-ttu-id="68136-140">Na caixa de diálogo, selecione uma página diferente e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="68136-140">In the dialog box, select a different page, and then select **OK**.</span></span>
1. <span data-ttu-id="68136-141">Salvar e publicar a URL.</span><span class="sxs-lookup"><span data-stu-id="68136-141">Save and publish the URL.</span></span>

## <a name="redirect-a-page-url"></a><span data-ttu-id="68136-142">Redirecionar uma URL de página</span><span class="sxs-lookup"><span data-stu-id="68136-142">Redirect a page URL</span></span>

<span data-ttu-id="68136-143">Certas vezes, você pode desejar que seus clientes vejam uma página diferente quando solicitam uma URL específica.</span><span class="sxs-lookup"><span data-stu-id="68136-143">Sometimes, you might want your customers to view a different page when they request a specific URL.</span></span> <span data-ttu-id="68136-144">Nesses casos, a melhor e mais fácil abordagem é mudar a página para a qual a URL aponta.</span><span class="sxs-lookup"><span data-stu-id="68136-144">In these cases, the best and easiest approach is often to change the page that the page URL points to.</span></span> <span data-ttu-id="68136-145">Entretanto, você pode ter motivos legítimos para usar os redirecionamentos do HTTP 301 ou 3023 para redirecionar solicitações de um a URL uma URL diferente.</span><span class="sxs-lookup"><span data-stu-id="68136-145">However, you might have legitimate reasons for using HTTP 301 or 3023 redirects to redirect requests for a URL to a different URL.</span></span>

<span data-ttu-id="68136-146">Para redirecionar uma URL a uma URL diferente, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="68136-146">To redirect a URL to a different URL, follow these steps.</span></span>

1. <span data-ttu-id="68136-147">Na página de **URLs**, selecione a URL para atualizar.</span><span class="sxs-lookup"><span data-stu-id="68136-147">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="68136-148">No painel de propriedade à direita, selecione **Redirecionar**.</span><span class="sxs-lookup"><span data-stu-id="68136-148">In the property pane on the right, select **Redirect**.</span></span>
1. <span data-ttu-id="68136-149">Selecione um destino para redirecionar:</span><span class="sxs-lookup"><span data-stu-id="68136-149">Select a destination for the redirect:</span></span>

    - <span data-ttu-id="68136-150">Para apontar para outra página em seu site, selecione **URL interna**, selecione o botão de reticências (**…**), e a URL para redirecionar para.</span><span class="sxs-lookup"><span data-stu-id="68136-150">To point to another page on your site, select **Internal URL**, select the ellipsis button (**...**), and then select the URL to redirect to.</span></span>
    - <span data-ttu-id="68136-151">Para apontar a uma página em um site externo, selecione **URL externa**, e depois insira a URL completa dessa página.</span><span class="sxs-lookup"><span data-stu-id="68136-151">To point to a page on an external site, select **External URL**, and then enter the full URL for that page.</span></span> <span data-ttu-id="68136-152">Não se esqueça de incluir o protocolo.</span><span class="sxs-lookup"><span data-stu-id="68136-152">Be sure to include the protocol.</span></span> <span data-ttu-id="68136-153">Por exemplo, insira `https://domain.com/new/page`.</span><span class="sxs-lookup"><span data-stu-id="68136-153">For example, enter `https://domain.com/new/page`.</span></span> <span data-ttu-id="68136-154">Se a URL já redireciona para uma URL interna, você deve selecionar **Limpar seleção** antes de inserir uma URL externa.</span><span class="sxs-lookup"><span data-stu-id="68136-154">If the URL already redirects to an internal URL, you must select **Clear selection** before you can enter an external URL.</span></span>

1. <span data-ttu-id="68136-155">Selecionar um tipo de redirecionamento:</span><span class="sxs-lookup"><span data-stu-id="68136-155">Select a redirect type:</span></span>

    - <span data-ttu-id="68136-156">**Redirecionamento permanente (301)** – Selecione esta opção quando você sabe que o conteúdo está se movendo permanentemente e não reverterá à URL anterior.</span><span class="sxs-lookup"><span data-stu-id="68136-156">**Permanent redirect (301)** – Select this option when you know that your content is moving permanently and won't revert to its previous URL.</span></span> <span data-ttu-id="68136-157">Os mecanismos de pesquisa atribuirão o valor de otimização de mecanismo de pesquisa (SEO) da URL de redirecionamento à URL que está sendo redirecionada e atualizará seu registro para exibir a nova URL.</span><span class="sxs-lookup"><span data-stu-id="68136-157">Search engines will assign the search engine optimization (SEO) value of the redirecting URL to the URL that is being redirected to and update their record to show the new URL.</span></span> 
    - <span data-ttu-id="68136-158">**Redirecionamento temporário (302)** – Selecione esta opção para redirecionar o tráfego sem atualizar os mecanismos de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68136-158">**Temporary redirect (302)** – Select this option to redirect traffic without updating search engines.</span></span> <span data-ttu-id="68136-159">Esta abordagem é normalmente usada se o conteúdo reverterá logo à URL anterior.</span><span class="sxs-lookup"><span data-stu-id="68136-159">This approach is typically used if the content will soon revert to its previous URL.</span></span>

1. <span data-ttu-id="68136-160">Quando estiver pronto para implementar redirecionar, salve e publique a URL.</span><span class="sxs-lookup"><span data-stu-id="68136-160">When you're ready to implement the redirect, save and publish the URL.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="68136-161">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="68136-161">Additional resources</span></span>

[<span data-ttu-id="68136-162">Personalizar a navegação do site</span><span class="sxs-lookup"><span data-stu-id="68136-162">Customize site navigation</span></span>](customize-site-navigation.md)

[<span data-ttu-id="68136-163">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="68136-163">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="68136-164">Configure seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="68136-164">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="68136-165">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="68136-165">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
