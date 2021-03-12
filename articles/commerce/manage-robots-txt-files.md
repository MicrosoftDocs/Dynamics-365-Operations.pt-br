---
title: Gerenciar arquivos robots.txt
description: Este tópico descreve como gerenciar os arquivos robots. txt no Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2e25a584121b700e566c29dbfe3fbbd72bf998cc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982532"
---
# <a name="manage-robotstxt-files"></a><span data-ttu-id="70788-103">Gerenciar arquivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="70788-103">Manage robots.txt files</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="70788-104">Este tópico descreve como gerenciar os arquivos robots. txt no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="70788-104">This topic describes how to manage robots.txt files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="70788-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="70788-105">Overview</span></span>

<span data-ttu-id="70788-106">O padrão de exclusão de robôs, ou robots. txt é um padrão que os sites usam para comunicar-se com os robôs da Web.</span><span class="sxs-lookup"><span data-stu-id="70788-106">The robots exclusion standard, or robots.txt, is a standard that websites use to communicate with web robots.</span></span> <span data-ttu-id="70788-107">Ele instrui os robôs da Web sobre as áreas de um site que não devem ser visitadas.</span><span class="sxs-lookup"><span data-stu-id="70788-107">It instructs web robots about any areas of a website that should not be visited.</span></span> <span data-ttu-id="70788-108">Os robôs geralmente são usados por mecanismos de pesquisa para indexar sites.</span><span class="sxs-lookup"><span data-stu-id="70788-108">Robots are often used by search engines to index websites.</span></span>

<span data-ttu-id="70788-109">Para excluir os robôs de um servidor, crie um arquivo no servidor.</span><span class="sxs-lookup"><span data-stu-id="70788-109">To exclude robots from a server, you create a file on the server.</span></span> <span data-ttu-id="70788-110">Neste arquivo, especifique uma política de acesso para robôs.</span><span class="sxs-lookup"><span data-stu-id="70788-110">In this file, you specify an access policy for robots.</span></span> <span data-ttu-id="70788-111">O arquivo deve ser acessível via HTTP no URL local **/robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="70788-111">The file must be accessible via HTTP at the local URL **/robots.txt**.</span></span> <span data-ttu-id="70788-112">O arquivo robots. txt ajuda os mecanismos de pesquisa a indexar o conteúdo no site.</span><span class="sxs-lookup"><span data-stu-id="70788-112">The robots.txt file helps search engines index the content on your site.</span></span>

<span data-ttu-id="70788-113">O Dynamics 365 Commerce permite carregar um arquivo robots. txt para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="70788-113">Dynamics 365 Commerce lets you upload a robots.txt file for your domain.</span></span> <span data-ttu-id="70788-114">Para cada domínio no seu ambiente de Commerce, você pode carregar um arquivo robots. txt e associá-lo a esse domínio.</span><span class="sxs-lookup"><span data-stu-id="70788-114">For each domain in your Commerce environment, you can upload one robots.txt file and associate it with that domain.</span></span>

<span data-ttu-id="70788-115">Para obter mais informações sobre o arquivo robots. txt, visite [As Páginas de Robôs da Web](https://www.robotstxt.org/).</span><span class="sxs-lookup"><span data-stu-id="70788-115">For more information about the robots.txt file, visit [The Web Robots Pages](https://www.robotstxt.org/).</span></span>

## <a name="upload-a-robotstxt-file"></a><span data-ttu-id="70788-116">Carregar um arquivo robots. txt</span><span class="sxs-lookup"><span data-stu-id="70788-116">Upload a robots.txt file</span></span>

<span data-ttu-id="70788-117">Depois de criar e editar o arquivo robots. txt de acordo com o [padrão de exclusão de robôs](https://www.robotstxt.org/orig.html), verifique se o arquivo está acessível no computador em que você usará as ferramentas de criação do Commerce.</span><span class="sxs-lookup"><span data-stu-id="70788-117">After you've created and edited your robots.txt file according to the [robots exclusion standard](https://www.robotstxt.org/orig.html), make sure that the file is accessible on the computer where you will use the Commerce authoring tools.</span></span> <span data-ttu-id="70788-118">O arquivo deve ter o nome **robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="70788-118">The file must be named **robots.txt**.</span></span> <span data-ttu-id="70788-119">Para obter melhores resultados, ele deve estar no formato observado no padrão.</span><span class="sxs-lookup"><span data-stu-id="70788-119">For best results, it must be in the format that is noted in the standard.</span></span> <span data-ttu-id="70788-120">Cada cliente do Commerce é responsável por validar e manter o conteúdo do arquivo robots. txt.</span><span class="sxs-lookup"><span data-stu-id="70788-120">Each Commerce customer is responsible for validating and maintaining the contents of its robots.txt file.</span></span> <span data-ttu-id="70788-121">Para carregar um arquivo robots.txt, você deve fazer logon no Commerce como um administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="70788-121">To upload a robots.txt file, you must be signed in to Commerce as a system admin.</span></span>

<span data-ttu-id="70788-122">Para carregar um arquivo robots. txt no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="70788-122">To upload a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="70788-123">Faça logon no Commerce como um administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="70788-123">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="70788-124">No painel de navegação esquerdo, selecione **Configurações do Locatário** (próximo ao símbolo de engrenagem) para expandi-las.</span><span class="sxs-lookup"><span data-stu-id="70788-124">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="70788-125">Em **Configurações do Locatário**, selecione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="70788-125">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="70788-126">Uma lista de todos os domínios associados ao seu ambiente aparece na parte principal da janela.</span><span class="sxs-lookup"><span data-stu-id="70788-126">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="70788-127">Selecione **Gerenciar** para carregar um arquivo robots. txt para um domínio no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="70788-127">Select **Manage** to upload a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="70788-128">No menu à direita, selecione o botão **Carregar** (a seta apontando para cima) próximo ao domínio associado ao arquivo robots. txt.</span><span class="sxs-lookup"><span data-stu-id="70788-128">On the menu on the right, select the **Upload** button (the upward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="70788-129">Uma caixa de diálogo do navegador de arquivos é exibida.</span><span class="sxs-lookup"><span data-stu-id="70788-129">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="70788-130">Na caixa de diálogo, procure e selecione o arquivo robots. txt que deseja carregar para o domínio associado e, em seguida, selecione **Abrir** para concluir o carregamento.</span><span class="sxs-lookup"><span data-stu-id="70788-130">In the dialog box, browse to and select the robots.txt file that you want to upload for the associated domain, and then select **Open** to complete the upload.</span></span>

> [!NOTE] 
> <span data-ttu-id="70788-131">Durante o carregamento, o Commerce verifica se o arquivo é um arquivo de texto, mas não valida o conteúdo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="70788-131">During upload, Commerce verifies that the file is a text file, but it doesn't validate the file's contents.</span></span>

## <a name="download-a-robotstxt-file"></a><span data-ttu-id="70788-132">Baixar um arquivo robots. txt</span><span class="sxs-lookup"><span data-stu-id="70788-132">Download a robots.txt file</span></span>

<span data-ttu-id="70788-133">Para baixar um arquivo robots. txt no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="70788-133">To download a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="70788-134">Faça logon no Commerce como um administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="70788-134">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="70788-135">No painel de navegação esquerdo, selecione **Configurações do Locatário** (próximo ao símbolo de engrenagem) para expandi-las.</span><span class="sxs-lookup"><span data-stu-id="70788-135">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="70788-136">Em **Configurações do Locatário**, selecione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="70788-136">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="70788-137">Uma lista de todos os domínios associados ao seu ambiente aparece na parte principal da janela.</span><span class="sxs-lookup"><span data-stu-id="70788-137">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="70788-138">Selecione **Gerenciar** para baixar um arquivo robots. txt para um domínio no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="70788-138">Select **Manage** to download a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="70788-139">No menu à direita, selecione o botão **Baixar** (a seta apontando para baixo) próximo ao domínio associado ao arquivo robots. txt.</span><span class="sxs-lookup"><span data-stu-id="70788-139">On the menu on the right, select the **Download** button (the downward-pointing arrow) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="70788-140">Uma caixa de diálogo do navegador de arquivos é exibida.</span><span class="sxs-lookup"><span data-stu-id="70788-140">A file browser dialog box appears.</span></span>
6. <span data-ttu-id="70788-141">Na caixa de diálogo, vá para o local desejado na unidade local, confirme ou insira um nome de arquivo e selecione **Salvar** para concluir o download.</span><span class="sxs-lookup"><span data-stu-id="70788-141">In the dialog box, go to the desired location on your local drive, confirm or enter a file name, and then select **Save** to complete the download.</span></span>

> [!NOTE]
> <span data-ttu-id="70788-142">Este procedimento pode ser usado para baixar somente os arquivos robots. txt que foram previamente carregados por meio das ferramentas de criação do Commerce.</span><span class="sxs-lookup"><span data-stu-id="70788-142">This procedure can be used to download only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="delete-a-robotstxt-file"></a><span data-ttu-id="70788-143">Excluir um arquivo robots. txt</span><span class="sxs-lookup"><span data-stu-id="70788-143">Delete a robots.txt file</span></span>

<span data-ttu-id="70788-144">Para excluir um arquivo robots. txt no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="70788-144">To delete a robots.txt file in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="70788-145">Faça logon no Commerce como um administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="70788-145">Sign in to Commerce as a system admin.</span></span>
2. <span data-ttu-id="70788-146">No painel de navegação esquerdo, selecione **Configurações do Locatário** (próximo ao símbolo de engrenagem) para expandi-las.</span><span class="sxs-lookup"><span data-stu-id="70788-146">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
3. <span data-ttu-id="70788-147">Em **Configurações do Locatário**, selecione **Robots.txt**.</span><span class="sxs-lookup"><span data-stu-id="70788-147">Under **Tenant Settings**, select **Robots.txt**.</span></span> <span data-ttu-id="70788-148">Uma lista de todos os domínios associados ao seu ambiente aparece na parte principal da janela.</span><span class="sxs-lookup"><span data-stu-id="70788-148">A list of all the domains that are associated with your environment appears in the main part of the window.</span></span>
4. <span data-ttu-id="70788-149">Selecione **Gerenciar** para excluir um arquivo robots. txt para um domínio no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="70788-149">Select **Manage** to delete a robots.txt file for a domain in your environment.</span></span>
5. <span data-ttu-id="70788-150">No menu à direita, selecione o botão **Excluir** (o símbolo de lata de lixo) próximo ao domínio associado ao arquivo robots. txt.</span><span class="sxs-lookup"><span data-stu-id="70788-150">On the menu on the right, select the **Delete** button (the trash can symbol) next to the domain that is associated with the robots.txt file.</span></span> <span data-ttu-id="70788-151">Uma janela do navegador de arquivos é exibida.</span><span class="sxs-lookup"><span data-stu-id="70788-151">A file browser window appears.</span></span>
6. <span data-ttu-id="70788-152">Na janela do navegador de arquivos, procure e selecione o arquivo robots. txt que deseja excluir do domínio e, em seguida, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="70788-152">In the file browser window, browse to and select the robots.txt file that you want to delete for the domain, and then select **Open**.</span></span> <span data-ttu-id="70788-153">Uma caixa de mensagem de aviso é exibida.</span><span class="sxs-lookup"><span data-stu-id="70788-153">A warning message box appears.</span></span>
7. <span data-ttu-id="70788-154">Na caixa de mensagem, selecione **Excluir** para confirmar a exclusão do arquivo robots. txt.</span><span class="sxs-lookup"><span data-stu-id="70788-154">In the message box, select **Delete** to confirm deletion of the robots.txt file.</span></span>

> [!NOTE] 
> <span data-ttu-id="70788-155">Este procedimento pode ser usado para excluir somente os arquivos robots. txt que foram previamente carregados por meio das ferramentas de criação do Commerce.</span><span class="sxs-lookup"><span data-stu-id="70788-155">This procedure can be used to delete only robots.txt files that were previously uploaded via the Commerce authoring tools.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="70788-156">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="70788-156">Additional resources</span></span>

[<span data-ttu-id="70788-157">Configurar seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="70788-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="70788-158">Implantar um novo locatário de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="70788-158">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="70788-159">Criar um site de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="70788-159">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="70788-160">Associar um site do Dynamics 365 Commerce a um canal online</span><span class="sxs-lookup"><span data-stu-id="70788-160">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="70788-161">Carregar redirecionamentos de URL em massa</span><span class="sxs-lookup"><span data-stu-id="70788-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="70788-162">Configurar um locatário de B2C no Commerce</span><span class="sxs-lookup"><span data-stu-id="70788-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="70788-163">Configurar páginas personalizadas para logons dos usuários</span><span class="sxs-lookup"><span data-stu-id="70788-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="70788-164">Configurar múltiplos locatários B2C em um ambiente do Commerce</span><span class="sxs-lookup"><span data-stu-id="70788-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="70788-165">Adicionar suporte para uma rede de entrega de conteúdo (CDN)</span><span class="sxs-lookup"><span data-stu-id="70788-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="70788-166">Habilitar detecção de lojas com base na localização</span><span class="sxs-lookup"><span data-stu-id="70788-166">Enable location-based store detection</span></span>](enable-store-detection.md)
