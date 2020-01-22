---
title: Adicionar uma mensagem de boas-vindas
description: Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4e9deeeaf491b77700ba0833e429f05d376a4392
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914507"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="b2c20-103">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="b2c20-103">Add a welcome message</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="b2c20-104">Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b2c20-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="b2c20-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="b2c20-105">Overview</span></span>

<span data-ttu-id="b2c20-106">Uma mensagem de boas-vindas em seu site de comércio online pode informar os visitantes sobre ofertas em andamento, atualizações do site ou disponibilidade de coleções sazonais.</span><span class="sxs-lookup"><span data-stu-id="b2c20-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="b2c20-107">A mensagem de boas-vindas é configurada usando o módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="b2c20-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="b2c20-108">O módulo de alerta deverá ser adicionado ao slot **Mensagens de erro/informações** do fragmento do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b2c20-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="b2c20-109">O módulo de alerta permite que você especifique o texto exibido, a cor do texto e o alinhamento.</span><span class="sxs-lookup"><span data-stu-id="b2c20-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="b2c20-110">Também permite especificar se os visitantes do site podem ignorar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="b2c20-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="b2c20-111">Quando uma mensagem de boas-vindas é adicionada a um fragmento de cabeçalho compartilhado, ela será exibida em cada página que usa o modelo onde o fragmento de cabeçalho compartilhado é usado.</span><span class="sxs-lookup"><span data-stu-id="b2c20-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="b2c20-112">Para adicionar uma mensagem de boas-vindas ao site, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="b2c20-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="b2c20-113">No Dynamics 365 Commerce, vá para o site.</span><span class="sxs-lookup"><span data-stu-id="b2c20-113">In Dynamics 365 Commerce, go to your site.</span></span>
1. <span data-ttu-id="b2c20-114">Selecionar **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="b2c20-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="b2c20-115">Selecione o fragmento do cabeçalho ao qual adicionar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="b2c20-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="b2c20-116">Na árvore em destaque, abra **Mensagens de erro/informações**.</span><span class="sxs-lookup"><span data-stu-id="b2c20-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="b2c20-117">Selecione o módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="b2c20-117">Select the alert module.</span></span>

    <span data-ttu-id="b2c20-118">Se um módulo de alerta não existir ainda, selecione o botão de reticências (**...**) ao lado de **Mensagens de erro/ informações** e depois selecione, **Adicionar o módulo**.</span><span class="sxs-lookup"><span data-stu-id="b2c20-118">If an alert module doesn't yet exist, select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span> <span data-ttu-id="b2c20-119">Selecione o módulo de alerta e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2c20-119">Select the alert module, and then select **OK**.</span></span>

1. <span data-ttu-id="b2c20-120">No painel de propriedade à direita, na guia **Dados**, selecione **Adicionar fonte de dados** e **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="b2c20-120">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="b2c20-121">No campo **Texto da entrada**, insira o texto da mensagem de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="b2c20-121">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="b2c20-122">Salve o fragmento do cabeçalho, insira-o e publique-o.</span><span class="sxs-lookup"><span data-stu-id="b2c20-122">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="b2c20-123">A mensagem de boas-vindas aparecerá na parte superior de cada página do site usando o fragmento do cabeçalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="b2c20-123">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2c20-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b2c20-124">Additional resources</span></span>

[<span data-ttu-id="b2c20-125">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="b2c20-125">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="b2c20-126">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="b2c20-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="b2c20-127">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="b2c20-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="b2c20-128">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="b2c20-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="b2c20-129">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="b2c20-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="b2c20-130">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="b2c20-130">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="b2c20-131">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="b2c20-131">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

