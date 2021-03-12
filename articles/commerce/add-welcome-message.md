---
title: Adicionar uma mensagem de boas-vindas
description: Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5910ab85b1b0b2df992a24ad3cf7a032e7b98ea9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980123"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="54367-103">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="54367-103">Add a welcome message</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="54367-104">Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="54367-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

## <a name="overview"></a><span data-ttu-id="54367-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="54367-105">Overview</span></span>

<span data-ttu-id="54367-106">Uma mensagem de boas-vindas em seu site de comércio online pode informar os visitantes sobre ofertas em andamento, atualizações do site ou disponibilidade de coleções sazonais.</span><span class="sxs-lookup"><span data-stu-id="54367-106">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="54367-107">A mensagem de boas-vindas é configurada usando o módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="54367-107">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="54367-108">O módulo de alerta deverá ser adicionado ao slot **Mensagens de erro/informações** do fragmento do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="54367-108">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="54367-109">O módulo de alerta permite que você especifique o texto exibido, a cor do texto e o alinhamento.</span><span class="sxs-lookup"><span data-stu-id="54367-109">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="54367-110">Também permite especificar se os visitantes do site podem ignorar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="54367-110">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="54367-111">Quando uma mensagem de boas-vindas é adicionada a um fragmento de cabeçalho compartilhado, ela será exibida em cada página que usa o modelo onde o fragmento de cabeçalho compartilhado é usado.</span><span class="sxs-lookup"><span data-stu-id="54367-111">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="54367-112">Para adicionar uma mensagem de boas-vindas ao site, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="54367-112">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="54367-113">No construtor de sites do Commerce, navegue até o seu site.</span><span class="sxs-lookup"><span data-stu-id="54367-113">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="54367-114">Selecionar **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="54367-114">Select **Fragments**.</span></span>
1. <span data-ttu-id="54367-115">Selecione o fragmento do cabeçalho ao qual adicionar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="54367-115">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="54367-116">Na árvore em destaque, abra **Mensagens de erro/informações**.</span><span class="sxs-lookup"><span data-stu-id="54367-116">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="54367-117">Selecione o módulo de alerta e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="54367-117">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="54367-118">Se um módulo de alerta não existir ainda, primeiro selecione o botão de reticências (**...**) ao lado de **Mensagens de erro/ informações** e depois selecione, **Adicionar o módulo**.</span><span class="sxs-lookup"><span data-stu-id="54367-118">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="54367-119">No painel de propriedade à direita, na guia **Dados**, selecione **Adicionar fonte de dados** e **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="54367-119">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="54367-120">No campo **Texto da entrada**, insira o texto da mensagem de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="54367-120">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="54367-121">Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento do cabeçalho e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="54367-121">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="54367-122">A mensagem de boas-vindas aparecerá na parte superior de cada página do site usando o fragmento do cabeçalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="54367-122">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="54367-123">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="54367-123">Additional resources</span></span>

[<span data-ttu-id="54367-124">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="54367-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="54367-125">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="54367-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="54367-126">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="54367-126">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="54367-127">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="54367-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="54367-128">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="54367-128">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="54367-129">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="54367-129">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="54367-130">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="54367-130">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

