---
title: Adicionar um aviso de direitos autorais
description: Este tópico descreve como adicionar um aviso de direitos autorais ao seu site de comércio eletrônico.
author: psimolin
manager: AnnBe
ms.date: 10/16/2020
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
ms.openlocfilehash: 838047cac694c65047332e146a7c43ee2ae0f401
ms.sourcegitcommit: 1a12b42cc17f004a981c716aed3da6cf538475a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4410316"
---
# <a name="add-a-copyright-notice"></a><span data-ttu-id="0cb37-103">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="0cb37-103">Add a copyright notice</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0cb37-104">Este tópico descreve como adicionar um aviso de direitos autorais ao seu site de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0cb37-104">This topic describes how to add a copyright notice to your e-Commerce website.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0cb37-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0cb37-105">Prerequisites</span></span>

<span data-ttu-id="0cb37-106">Antes de adicionar um aviso de direitos autorais ao seu site, você deve ter os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="0cb37-106">Before you can add a copyright notice to your site, you must have the following items:</span></span>

- <span data-ttu-id="0cb37-107">Um modelo que inclui um fragmento de rodapé compartilhado.</span><span class="sxs-lookup"><span data-stu-id="0cb37-107">A template that includes a shared footer fragment.</span></span>
- <span data-ttu-id="0cb37-108">Uma página que usa esse modelo.</span><span class="sxs-lookup"><span data-stu-id="0cb37-108">A page that uses that template.</span></span>

## <a name="add-a-copyright-notice"></a><span data-ttu-id="0cb37-109">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="0cb37-109">Add a copyright notice</span></span>

<span data-ttu-id="0cb37-110">Para adicionar um aviso de direitos autorais na parte inferior de cada página que usa um modelo específico, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="0cb37-110">To add a copyright notice to the bottom of every page that uses a specific template, follow these steps.</span></span>

1. <span data-ttu-id="0cb37-111">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-111">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="0cb37-112">Na caixa de diálogo **Novo fragmento**, selecione o módulo **Rodapé** e nomeie o fragmento.</span><span class="sxs-lookup"><span data-stu-id="0cb37-112">In the **New fragment** dialog box, select the **Footer** module, and name the fragment.</span></span> <span data-ttu-id="0cb37-113">Por exemplo, insira **Footer-Copyright**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-113">For example, enter **Footer-Copyright**.</span></span>
1. <span data-ttu-id="0cb37-114">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-114">Select **OK**.</span></span>
1. <span data-ttu-id="0cb37-115">No painel de navegação, selecione o botão de reticências (**...**) ao lado de **Rodapé** e depois **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-115">In the navigation pane, select the ellipsis button (**...**) next to **Footer**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="0cb37-116">Na caixa de diálogo, selecione **Categoria de rodapé** e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-116">In the dialog box, select **Footer category**, and then select **OK**.</span></span>
1. <span data-ttu-id="0cb37-117">No painel de navegação, selecione o botão de reticências ao lado de **Categoria de rodapé** e depois **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-117">In the navigation pane, select the ellipsis button next to **Footer category**, and then select **Add Module**.</span></span>
1. <span data-ttu-id="0cb37-118">Na caixa de diálogo, selecione **Bloco de texto** e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-118">In the dialog box, select **Text block**, and then select **OK**.</span></span>
1. <span data-ttu-id="0cb37-119">No painel de navegação, selecione **Bloco de texto**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-119">In the navigation pane, select **Text block**.</span></span>
1. <span data-ttu-id="0cb37-120">No painel de propriedades à direita, no campo **Parágrafo**, adicione sua mensagem de direitos autorais.</span><span class="sxs-lookup"><span data-stu-id="0cb37-120">In the properties pane on the right, in the **Paragraph** field, add your copyright message.</span></span> <span data-ttu-id="0cb37-121">Por exemplo, insira **(C) Fabrikam 2019**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-121">For example, enter **(C) Fabrikam 2019**.</span></span>
1. <span data-ttu-id="0cb37-122">Selecione **Salvar**, **Concluir a edição** e depois **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-122">Select **Save**, select **Finish editing**, and then select **Publish**.</span></span>
1. <span data-ttu-id="0cb37-123">Vá para **Modelos**, selecione o modelo e depois **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-123">Go to **Templates**, select the template, and then select **Edit**.</span></span>
1. <span data-ttu-id="0cb37-124">Em **Estrutura de Tópicos da Página**, expanda **Corpo** e depois **Página Padrão**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-124">Under **Page Outline**, expand **Body**, and then expand **Default Page**.</span></span>
1. <span data-ttu-id="0cb37-125">Selecione o botão de reticências ao lado de **Slot de rodapé** e depois escolha **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-125">Select the ellipsis button next to **Footer Slot**, and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="0cb37-126">Selecione o fragmento que você criou antes e escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="0cb37-126">Select the fragment that you created earlier, and then select **Select**.</span></span>
1. <span data-ttu-id="0cb37-127">Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="0cb37-127">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="0cb37-128">O rodapé que contém o aviso de direitos autorais aparece automaticamente na parte inferior de todas as páginas que usam o modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="0cb37-128">The footer that contains the copyright notice automatically appears at the bottom of all pages that use the selected template.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0cb37-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0cb37-129">Additional resources</span></span>

[<span data-ttu-id="0cb37-130">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="0cb37-130">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="0cb37-131">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="0cb37-131">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="0cb37-132">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="0cb37-132">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="0cb37-133">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="0cb37-133">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="0cb37-134">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="0cb37-134">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="0cb37-135">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="0cb37-135">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="0cb37-136">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="0cb37-136">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

