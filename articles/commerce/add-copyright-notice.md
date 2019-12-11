---
title: Adicionar um aviso de direitos autorais
description: Este tópico descreve como adicionar um aviso de direitos autorais ao seu site de comércio eletrônico.
author: psimolin
manager: AnnBe
ms.date: 10/31/2019
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 39135a2eca25336097ee9eddf06dc6709c102571
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696936"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="40038-103">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="40038-103">Add a copyright notice</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="40038-104">Este tópico descreve como adicionar um aviso de direitos autorais ao seu site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="40038-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="40038-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="40038-105">Prerequisites</span></span>

<span data-ttu-id="40038-106">Antes de adicionar um aviso de direitos autorais ao seu site, você deve ter os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="40038-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="40038-107">Um modelo que inclui um fragmento de rodapé compartilhado.</span><span class="sxs-lookup"><span data-stu-id="40038-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="40038-108">Uma página que usa esse modelo.</span><span class="sxs-lookup"><span data-stu-id="40038-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="40038-109">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="40038-109">Add a copyright notice</span></span>

<span data-ttu-id="40038-110">Para adicionar um aviso de direitos autorais na parte inferior de cada página que usa um modelo específico, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="40038-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="40038-111">Vá para **Fragmentos** e selecione **Novo Fragmento de Página**.</span><span class="sxs-lookup"><span data-stu-id="40038-111">Go to **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="40038-112">Na caixa de diálogo, selecione o módulo **Rodapé** e nomeie o fragmento.</span><span class="sxs-lookup"><span data-stu-id="40038-112">In the dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="40038-113">Por exemplo, insira **Footer-Copyright**.</span><span class="sxs-lookup"><span data-stu-id="40038-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="40038-114">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="40038-114">Select **OK**.</span></span>
1. <span data-ttu-id="40038-115">No painel de navegação, selecione o botão de reticências (**...**) ao lado de **Rodapé** e depois **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="40038-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="40038-116">Na caixa de diálogo, selecione **Categoria de rodapé** e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="40038-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="40038-117">No painel de navegação, selecione o botão de reticências ao lado de **Categoria de rodapé** e depois **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="40038-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="40038-118">Na caixa de diálogo, selecione **Item de bloco de conteúdo sofisticado** e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="40038-118">In the dialog box, select **Content rich block item**, and then select **OK**.</span></span>
1. <span data-ttu-id="40038-119">No painel de navegação, selecione **Item de bloco de conteúdo sofisticado**.</span><span class="sxs-lookup"><span data-stu-id="40038-119">In the navigation pane, select **Content rich block item**.</span></span>
1. <span data-ttu-id="40038-120">No painel de propriedades à direita, no campo **Parágrafo**, adicione sua mensagem de direitos autorais.</span><span class="sxs-lookup"><span data-stu-id="40038-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="40038-121">Por exemplo, insira **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="40038-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="40038-122">Selecione **Save**, **Fazer Check-in** e depois **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="40038-122">Select **Save**, select **Check In**, and then select **Publish**.</span></span>
1. <span data-ttu-id="40038-123">Vá para **Modelos**, selecione o modelo e depois **Fazer Check-out**.</span><span class="sxs-lookup"><span data-stu-id="40038-123">Go to **Templates**, select the template, and then select **Check Out**.</span></span>
1. <span data-ttu-id="40038-124">Em **Estrutura de Tópicos da Página**, expanda **Corpo** e depois **Página Padrão**.</span><span class="sxs-lookup"><span data-stu-id="40038-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="40038-125">Selecione o botão de reticências ao lado de **Slot de rodapé** e depois escolha **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="40038-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="40038-126">Selecione o fragmento que você criou antes e escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="40038-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="40038-127">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="40038-127">Check in the template, and publish it.</span></span>

<span data-ttu-id="40038-128">O rodapé que contém o aviso de direitos autorais aparece automaticamente na parte inferior de todas as páginas que usam o modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="40038-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40038-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="40038-129">Additional resources</span></span>

[<span data-ttu-id="40038-130">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="40038-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="40038-131">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="40038-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="40038-132">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="40038-132">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="40038-133">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="40038-133">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="40038-134">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="40038-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="40038-135">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="40038-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

