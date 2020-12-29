---
title: Carregar e atender arquivos estáticos
description: Este tópico descreve como carregar um arquivo estático no assistente para criação de sites do Microsoft Dynamics 365 Commerce e como criar uma URL personalizada e um nome de arquivo que podem ser usados para solicitar esse arquivo.
author: StuHarg
manager: annbe
ms.date: 11/16/2020
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
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 981bbf03480abfd812b4020173b7acfdad0fef14
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594943"
---
# <a name="upload-and-serve-static-files"></a><span data-ttu-id="16de3-103">Carregar e atender arquivos estáticos</span><span class="sxs-lookup"><span data-stu-id="16de3-103">Upload and serve static files</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="16de3-104">Este tópico descreve como carregar um arquivo estático no assistente para criação de sites do Microsoft Dynamics 365 Commerce e como criar uma URL personalizada e um nome de arquivo que podem ser usados para solicitar esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="16de3-104">This topic describes how to upload a static file into Microsoft Dynamics 365 Commerce site builder, and how to create a custom URL and file name that can be used to request that file.</span></span>

<span data-ttu-id="16de3-105">Alguns conectores de terceiros exigem que um arquivo seja hospedado e fornecido usando o site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="16de3-105">Some third-party connectors require that a file be hosted and served from the e-commerce site.</span></span> <span data-ttu-id="16de3-106">Esses conectores esperam que o arquivo seja retornado por solicitações a um caminho de URL de retorno de chamada e nome de arquivo específicos.</span><span class="sxs-lookup"><span data-stu-id="16de3-106">These connectors expect that the file will be returned by requests to a specific callback URL path and file name.</span></span> <span data-ttu-id="16de3-107">Portanto, este tópico explica como carregar e fornecer um arquivo estático que possui uma URL e um nome de arquivo definidos pelo usuário em um site de comércio eletrônico do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="16de3-107">Therefore, this topic explains how to upload and serve a static file that has a user-definable URL and file name on a Dynamics 365 Commerce e-commerce site.</span></span>

## <a name="create-a-site-url-that-returns-a-static-file"></a><span data-ttu-id="16de3-108">Criar uma URL de site que retorne um arquivo estático</span><span class="sxs-lookup"><span data-stu-id="16de3-108">Create a site URL that returns a static file</span></span>

<span data-ttu-id="16de3-109">Para criar uma URL de site que retorna um arquivo estático no assistente de criação de sites do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="16de3-109">To create a site URL that returns a static file in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="16de3-110">Acesse a Biblioteca de Mídia do seu site e carregue o arquivo que deve ser fornecido por solicitações para a URL que você definirá.</span><span class="sxs-lookup"><span data-stu-id="16de3-110">Go to your site's Media library, and upload the file that should be served by requests to the URL that you will define.</span></span> <span data-ttu-id="16de3-111">Se você já carregou o arquivo, pode ignorar essa etapa.</span><span class="sxs-lookup"><span data-stu-id="16de3-111">If you've already uploaded the file, you can skip this step.</span></span>
1. <span data-ttu-id="16de3-112">Vá para **URLs** do seu site.</span><span class="sxs-lookup"><span data-stu-id="16de3-112">Go to **URLs** for your site.</span></span>
1. <span data-ttu-id="16de3-113">Selecione **Novo \> Nova URL**.</span><span class="sxs-lookup"><span data-stu-id="16de3-113">Select **New \> New URL**.</span></span>
1. <span data-ttu-id="16de3-114">Na caixa de diálogo **Nova URL**, selecione **Ativo de biblioteca de mídia**.</span><span class="sxs-lookup"><span data-stu-id="16de3-114">In the **New URL** dialog box, select **Media library asset**.</span></span>
1. <span data-ttu-id="16de3-115">No campo **Caminho da URL**, insira o caminho da URL.</span><span class="sxs-lookup"><span data-stu-id="16de3-115">In the **URL path** field, enter the URL path.</span></span> <span data-ttu-id="16de3-116">Inclua o nome do arquivo no caminho.</span><span class="sxs-lookup"><span data-stu-id="16de3-116">Include the file name in the path.</span></span>
1. <span data-ttu-id="16de3-117">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="16de3-117">Select **Next**.</span></span> <span data-ttu-id="16de3-118">A Biblioteca de Mídia é aberta e mostra todos os ativos de mídia do tipo **documento** que foram carregados.</span><span class="sxs-lookup"><span data-stu-id="16de3-118">The Media library is opened and shows all media assets of the **document** type that have been uploaded.</span></span>
1. <span data-ttu-id="16de3-119">Selecione o arquivo que deve ser fornecido por solicitações à URL que você definiu na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="16de3-119">Select the file that should be served for requests to the URL that you defined in step 5.</span></span>
1. <span data-ttu-id="16de3-120">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="16de3-120">Select **Save**.</span></span>

<span data-ttu-id="16de3-121">Nesse momento, a URL que você criou está em estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="16de3-121">At this point, the URL that you created is in a draft state.</span></span> <span data-ttu-id="16de3-122">O arquivo para o qual a URL aponta não será retornado até que você publique a URL.</span><span class="sxs-lookup"><span data-stu-id="16de3-122">The file that the URL points to won't be returned until you publish the URL.</span></span> <span data-ttu-id="16de3-123">Antes de publicar a URL, você pode validar se ela retornará os dados corretos.</span><span class="sxs-lookup"><span data-stu-id="16de3-123">Before you publish the URL, you can validate that it returns the correct data.</span></span>

## <a name="validate-and-publish-a-url"></a><span data-ttu-id="16de3-124">Validar e publicar uma URL</span><span class="sxs-lookup"><span data-stu-id="16de3-124">Validate and publish a URL</span></span>

<span data-ttu-id="16de3-125">Para validar uma URL antes de publicá-la, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="16de3-125">To validate an URL before you publish it, follow these steps.</span></span>

1. <span data-ttu-id="16de3-126">Vá até **URLs** do seu site e selecione a URL para exibição.</span><span class="sxs-lookup"><span data-stu-id="16de3-126">Go to **URLs** for your site, and select the URL to preview.</span></span>
2. <span data-ttu-id="16de3-127">No painel de propriedades à direita, abaixo do botão **Editar**, selecione o link de URL correto.</span><span class="sxs-lookup"><span data-stu-id="16de3-127">In the properties pane on the right, below the **Edit** button, select the correct URL link.</span></span> <span data-ttu-id="16de3-128">Uma nova janela do navegador é aberta e você deve receber um erro 404.</span><span class="sxs-lookup"><span data-stu-id="16de3-128">A new browser window is opened, and you should receive a 404 error.</span></span>
3. <span data-ttu-id="16de3-129">Anexe a cadeia de caracteres de consulta **?preview=inprogress** à URL (por exemplo, `https://yoursite.com/callback.html?preview=inprogress`) e recarregue a página.</span><span class="sxs-lookup"><span data-stu-id="16de3-129">Append the **?preview=inprogress** query string to the URL (for example, `https://yoursite.com/callback.html?preview=inprogress`), and reload the page.</span></span> <span data-ttu-id="16de3-130">O arquivo que você carregou na Biblioteca de Mídia deve ser retornado na resposta.</span><span class="sxs-lookup"><span data-stu-id="16de3-130">The file that you uploaded to the Media library should be returned in the response.</span></span>

<span data-ttu-id="16de3-131">Depois de validar a URL, você pode publicá-la.</span><span class="sxs-lookup"><span data-stu-id="16de3-131">After you've validated the URL, you can publish it.</span></span>

1. <span data-ttu-id="16de3-132">Vá até **URLs** do seu site e selecione a URL.</span><span class="sxs-lookup"><span data-stu-id="16de3-132">Go to **URLs** for your site, and select the URL.</span></span>
2. <span data-ttu-id="16de3-133">Selecione **Publicar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="16de3-133">Select **Publish** on the command bar.</span></span>

## <a name="update-the-file-that-a-url-points-to"></a><span data-ttu-id="16de3-134">Atualizar o arquivo para o qual uma URL aponta</span><span class="sxs-lookup"><span data-stu-id="16de3-134">Update the file that a URL points to</span></span>

<span data-ttu-id="16de3-135">Após a publicação de uma URL, você pode atualizá-la para que aponte para um arquivo diferente.</span><span class="sxs-lookup"><span data-stu-id="16de3-135">After a URL is published, you can update it so that it points to a different file.</span></span> <span data-ttu-id="16de3-136">Como alternativa, você pode atualizar a URL para que aponte para um tipo diferente de recurso, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="16de3-136">Alternatively, you can update the URL so that it points to a different the type of resource, as described in the next section.</span></span> <span data-ttu-id="16de3-137">Por exemplo, você pode apontar a URL para uma página interna ou um redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="16de3-137">For example, you can point the URL to an internal page or a redirect.</span></span>

<span data-ttu-id="16de3-138">Para atualizar o arquivo para o qual uma URL aponta, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="16de3-138">To update the file that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="16de3-139">Vá até **URLs** do seu site e selecione a URL para atualização.</span><span class="sxs-lookup"><span data-stu-id="16de3-139">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="16de3-140">No painel de propriedades à direita, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="16de3-140">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="16de3-141">Em **Atribuição de URL**, selecione a caixa **Etapa 2** e, em seguida, selecione um novo documento na Biblioteca de Mídia.</span><span class="sxs-lookup"><span data-stu-id="16de3-141">Under **URL assignment**, select the **Step 2** box, and then select a new document from the Media library.</span></span>
1. <span data-ttu-id="16de3-142">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="16de3-142">Select **Apply**.</span></span>

## <a name="update-the-asset-type-that-a-url-points-to"></a><span data-ttu-id="16de3-143">Atualizar o tipo de ativo para o qual uma URL aponta</span><span class="sxs-lookup"><span data-stu-id="16de3-143">Update the asset type that a URL points to</span></span>

<span data-ttu-id="16de3-144">Você também pode atualizar uma URL para que aponte para um tipo diferente de ativo (recurso), como uma página interna ou um redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="16de3-144">You can also update a URL so that it points to a different type of asset (resource), such as an internal page or a redirect.</span></span>

<span data-ttu-id="16de3-145">Para atualizar o tipo de ativo para o qual uma URL aponta, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="16de3-145">To update the asset type that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="16de3-146">Vá até **URLs** do seu site e selecione a URL para atualização.</span><span class="sxs-lookup"><span data-stu-id="16de3-146">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="16de3-147">No painel de propriedades à direita, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="16de3-147">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="16de3-148">Em **Atribuição de URL**, em **Etapa 1**, selecione um tipo de ativo diferente.</span><span class="sxs-lookup"><span data-stu-id="16de3-148">Under **URL assignment**, under **Step 1**, select a different asset type.</span></span>
1. <span data-ttu-id="16de3-149">Selecione a caixa **Etapa 2** e, em seguida, selecione o novo ativo.</span><span class="sxs-lookup"><span data-stu-id="16de3-149">Select the **Step 2** box, and then select the new asset.</span></span>
1. <span data-ttu-id="16de3-150">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="16de3-150">Select **Apply**.</span></span>

## <a name="change-the-url-path"></a><span data-ttu-id="16de3-151">Alterar o caminho da URL</span><span class="sxs-lookup"><span data-stu-id="16de3-151">Change the URL path</span></span>

<span data-ttu-id="16de3-152">Depois que uma URL é criada, seu caminho não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="16de3-152">After a URL is created, its path can't be changed.</span></span> <span data-ttu-id="16de3-153">Se você precisar alterar o caminho da URL que atende a um arquivo ou qualquer outro tipo de recurso, será necessário criar uma nova URL, mapeá-la para o arquivo existente ou outro recurso e, em seguida, cancelar a publicação e excluir a URL antiga.</span><span class="sxs-lookup"><span data-stu-id="16de3-153">If you must change the URL path that serves a file or any other type of resource, you have to create a new URL, map it to the existing file or other resource, and then unpublish and delete the old URL.</span></span>

<span data-ttu-id="16de3-154">Para alterar o caminho do URL, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="16de3-154">To change the URL path, follow these steps.</span></span>

1. <span data-ttu-id="16de3-155">Para criar uma nova URL e mapeá-la para o arquivo existente ou outro recurso, siga as instruções na seção [Criar uma URL de site que retorna um arquivo estático](#create-a-site-url-that-returns-a-static-file) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="16de3-155">To create a new URL and map it to the existing file or another resource, follow the instructions in the [Create a site URL that returns a static file](#create-a-site-url-that-returns-a-static-file) section earlier in this topic.</span></span>
1. <span data-ttu-id="16de3-156">Selecione a novo URL e selecione **Publicar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="16de3-156">Select the new URL, and select **Publish** on the command bar.</span></span> <span data-ttu-id="16de3-157">A nova URL é publicada.</span><span class="sxs-lookup"><span data-stu-id="16de3-157">The new URL is published.</span></span>
1. <span data-ttu-id="16de3-158">Para cancelar a publicação da URL antiga, selecione-a e depois escolha **Cancelar publicação** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="16de3-158">To unpublish the old URL, select it, and then select **Unpublish** on the command bar.</span></span> <span data-ttu-id="16de3-159">Agora é possível excluir a URL antiga, se desejar.</span><span class="sxs-lookup"><span data-stu-id="16de3-159">You can now delete the old URL if you want.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="16de3-160">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="16de3-160">Additional resources</span></span>

[<span data-ttu-id="16de3-161">Visão geral do gerenciamento de ativos digitais</span><span class="sxs-lookup"><span data-stu-id="16de3-161">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="16de3-162">Carregar imagens</span><span class="sxs-lookup"><span data-stu-id="16de3-162">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="16de3-163">Carregar vídeos</span><span class="sxs-lookup"><span data-stu-id="16de3-163">Upload videos</span></span>](dam-upload-video.md)

[<span data-ttu-id="16de3-164">Carregar arquivos diferentes de imagens e vídeos</span><span class="sxs-lookup"><span data-stu-id="16de3-164">Upload files other than images and videos</span></span>](dam-upload-files.md)

[<span data-ttu-id="16de3-165">Cortar imagens</span><span class="sxs-lookup"><span data-stu-id="16de3-165">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="16de3-166">Personalizar pontos focais da imagem</span><span class="sxs-lookup"><span data-stu-id="16de3-166">Customize image focal points</span></span>](dam-custom-focal-point.md)
