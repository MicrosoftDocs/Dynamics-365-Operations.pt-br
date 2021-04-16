---
title: Criar páginas de resposta personalizadas para erros do código de status 4xx/5xx
description: Este tópico descreve como criar páginas de resposta personalizadas para erros de código de status 4xx e 5xx usando as ferramentas de criação no Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b35b3c07b1edd41e6a3763c0001529e125e4636
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799629"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a><span data-ttu-id="b8f84-103">Criar páginas de resposta personalizadas para erros do código de status 4xx/5xx</span><span class="sxs-lookup"><span data-stu-id="b8f84-103">Build custom response pages for 4xx/5xx status code errors</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b8f84-104">Este tópico descreve como criar páginas de resposta personalizadas para erros de código de status 4xx e 5xx usando as ferramentas de criação no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b8f84-104">This topic describes how to build custom response pages for 4xx and 5xx status code errors by using the authoring tools in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b8f84-105">Se uma solicitação não tiver êxito, o servidor emite respostas de erro do código de status do HTTP.</span><span class="sxs-lookup"><span data-stu-id="b8f84-105">If a request isn't successful, the server issues HTTP status code error responses.</span></span> <span data-ttu-id="b8f84-106">O código de status 404 é capturado e retornado se uma página não for encontrada e o código de status 500 é capturado e retornado se um erro de servidor ocorrer.</span><span class="sxs-lookup"><span data-stu-id="b8f84-106">The 404 status code is captured and returned if a page isn't found, and the 500 status code is captured and returned if a server error occurs.</span></span> <span data-ttu-id="b8f84-107">No Dynamics 365 Commerce, os usuários do aplicativo podem criar as páginas de resposta de erro de código de status personalizado que são exibidas para usuários dessas respostas de erro de código de status.</span><span class="sxs-lookup"><span data-stu-id="b8f84-107">In Dynamics 365 Commerce, application users can build custom status code error response pages that are shown to users for these status code error responses.</span></span>

## <a name="build-a-status-code-error-response-page"></a><span data-ttu-id="b8f84-108">Criar uma página de resposta de erro do código de status</span><span class="sxs-lookup"><span data-stu-id="b8f84-108">Build a status code error response page</span></span>

<span data-ttu-id="b8f84-109">Para começar a criar uma página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="b8f84-109">To start to build a status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="b8f84-110">Em seu navegador preferido, conecte-se ao Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b8f84-110">In your preferred web browser, sign in to Dynamics 365 Commerce.</span></span> 
1. <span data-ttu-id="b8f84-111">Selecione o site no qual você deseja criar uma página de resposta de erro de código do status 4xx/5xx.</span><span class="sxs-lookup"><span data-stu-id="b8f84-111">Select the site that you want to build a 4xx/5xx status code error response page for.</span></span>

### <a name="build-the-template"></a><span data-ttu-id="b8f84-112">Criar o modelo</span><span class="sxs-lookup"><span data-stu-id="b8f84-112">Build the template</span></span>

<span data-ttu-id="b8f84-113">Para criar o modelo para a página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="b8f84-113">To build the template for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="b8f84-114">Vá para **Modelos**.</span><span class="sxs-lookup"><span data-stu-id="b8f84-114">Go to **Templates**.</span></span>
1. <span data-ttu-id="b8f84-115">Selecione **Novo** para criar um modelo de página.</span><span class="sxs-lookup"><span data-stu-id="b8f84-115">Select **New** to create a page template.</span></span>
1. <span data-ttu-id="b8f84-116">Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira um nome para o novo modelo e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8f84-116">In the **New Template** dialog box, under **Template Name**, enter a name for the new template, and then select **OK**.</span></span>
1. <span data-ttu-id="b8f84-117">Crie modelo, com base na estrutura que deseja que a página de resposta de erro do código de status apareça.</span><span class="sxs-lookup"><span data-stu-id="b8f84-117">Build the template, based on the structure that you want the status code error response page to have.</span></span>
1. <span data-ttu-id="b8f84-118">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="b8f84-118">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span> 

### <a name="build-the-status-code-error-response-page"></a><span data-ttu-id="b8f84-119">Crie a página de resposta de erro do código de status</span><span class="sxs-lookup"><span data-stu-id="b8f84-119">Build the status code error response page</span></span>

<span data-ttu-id="b8f84-120">Para criar a página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="b8f84-120">To build the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="b8f84-121">Vá para **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="b8f84-121">Go to **Pages**.</span></span>
1. <span data-ttu-id="b8f84-122">Selecione **Novo** para criar uma página.</span><span class="sxs-lookup"><span data-stu-id="b8f84-122">Select **New** to create a page.</span></span>
1. <span data-ttu-id="b8f84-123">Na caixa de diálogo **Escolha um modelo**, selecione um modelo e, em **Nome da página**, insira um nome para a página da resposta do erro do código de status.</span><span class="sxs-lookup"><span data-stu-id="b8f84-123">In the **Choose a template** dialog box, select a template, and then, under **Page name**, enter a name for the status code error response page.</span></span> <span data-ttu-id="b8f84-124">Deixe o campo **URL da Página** em branco.</span><span class="sxs-lookup"><span data-stu-id="b8f84-124">Leave the **Page URL** field blank.</span></span>
1. <span data-ttu-id="b8f84-125">Crie a página.</span><span class="sxs-lookup"><span data-stu-id="b8f84-125">Build the page.</span></span>
1. <span data-ttu-id="b8f84-126">Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="b8f84-126">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="b8f84-127">Você pode criar páginas de resposta de erro de código do status separada para erros de código do status 4xx e 5xx.</span><span class="sxs-lookup"><span data-stu-id="b8f84-127">You can create separate status code error response pages for 4xx and 5xx status code errors.</span></span> <span data-ttu-id="b8f84-128">Alternativamente, você pode usar a mesma página geral da resposta de erro do código de status para ambas as categorias de erro.</span><span class="sxs-lookup"><span data-stu-id="b8f84-128">Alternatively, you can use the same general status code error response page for both error categories.</span></span>

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a><span data-ttu-id="b8f84-129">Configurar um redirecionamento para a página de resposta de erro do código de status</span><span class="sxs-lookup"><span data-stu-id="b8f84-129">Set up a redirect for the status code error response page</span></span>

<span data-ttu-id="b8f84-130">Para configurar um redirecionamento para a página de resposta de erro do código de status, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="b8f84-130">To set up a redirect for the status code error response page, follow these steps.</span></span>

1. <span data-ttu-id="b8f84-131">Vá para **URLs \> Novo \> Novo alias**, e selecione a página de resposta de erro do código de status que você compilou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b8f84-131">Go to **URLs \> New \> New Alias**, and select the status code error response page that you built earlier.</span></span>
1. <span data-ttu-id="b8f84-132">No campo **Alias**, **default-4xx** ou **default-5xx**, dependendo da página de resposta de erro do código de status para a qual você está configurando o redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="b8f84-132">In the **Alias** field, enter either **default-4xx** or **default-5xx**, depending on the status code error response page that you're setting up a redirect for.</span></span> <span data-ttu-id="b8f84-133">Essas alias devem ser publicados.</span><span class="sxs-lookup"><span data-stu-id="b8f84-133">These aliases must be published.</span></span> <span data-ttu-id="b8f84-134">Caso contrário, o redirecionamento não funcionará.</span><span class="sxs-lookup"><span data-stu-id="b8f84-134">Otherwise, the redirect won't work.</span></span>
1. <span data-ttu-id="b8f84-135">Selecione **OK** para enviar o link.</span><span class="sxs-lookup"><span data-stu-id="b8f84-135">Select **OK** to commit the linking.</span></span>

> [!NOTE]
> <span data-ttu-id="b8f84-136">Se estiver usando uma única página de resposta de erro do código de status para ambas as categorias de erro, repita este procedimento para vincular uma apelido da outra categoria de erro na mesma página.</span><span class="sxs-lookup"><span data-stu-id="b8f84-136">If you're using a single status code error response page for both error categories, repeat this procedure to link an alias for the other error category to the same page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8f84-137">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b8f84-137">Additional resources</span></span>

[<span data-ttu-id="b8f84-138">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="b8f84-138">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="b8f84-139">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="b8f84-139">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="b8f84-140">Criar uma URL da página</span><span class="sxs-lookup"><span data-stu-id="b8f84-140">Create a page URL</span></span>](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
