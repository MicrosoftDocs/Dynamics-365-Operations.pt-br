---
title: Adicionar uma mensagem de boas-vindas
description: Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site do Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e61f43eca7d1343d020e1c01b5b1140f07b63c6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797374"
---
# <a name="add-a-welcome-message"></a><span data-ttu-id="9a9e9-103">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="9a9e9-103">Add a welcome message</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9a9e9-104">Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-104">This topic describes how to add a welcome message to your Microsoft Dynamics 365 Commerce website.</span></span>

<span data-ttu-id="9a9e9-105">Uma mensagem de boas-vindas em seu site de comércio online pode informar os visitantes sobre ofertas em andamento, atualizações do site ou disponibilidade de coleções sazonais.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-105">A welcome message on your e-Commerce website can inform visitors about ongoing sales, site updates, or availability of seasonal collections.</span></span> <span data-ttu-id="9a9e9-106">A mensagem de boas-vindas é configurada usando o módulo de alerta.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-106">The welcome message is set by using the alert module.</span></span>

<span data-ttu-id="9a9e9-107">O módulo de alerta deverá ser adicionado ao slot **Mensagens de erro/informações** do fragmento do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-107">The alert module should be added to the **Error/Information messages** slot of the header fragment.</span></span> <span data-ttu-id="9a9e9-108">O módulo de alerta permite que você especifique o texto exibido, a cor do texto e o alinhamento.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-108">The alert module lets you specify the text that is shown, the text color, and the alignment.</span></span> <span data-ttu-id="9a9e9-109">Também permite especificar se os visitantes do site podem ignorar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-109">It also lets you specify whether visitors to the site can dismiss the message.</span></span>

<span data-ttu-id="9a9e9-110">Quando uma mensagem de boas-vindas é adicionada a um fragmento de cabeçalho compartilhado, ela será exibida em cada página que usa o modelo onde o fragmento de cabeçalho compartilhado é usado.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-110">When a welcome message is added to a shared header fragment, it will be shown on every page that uses the template where that shared header fragment is used.</span></span>

<span data-ttu-id="9a9e9-111">Para adicionar uma mensagem de boas-vindas ao site, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-111">To add a welcome message to your site, follow these steps.</span></span>

1. <span data-ttu-id="9a9e9-112">No construtor de sites do Commerce, navegue até o seu site.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-112">In Commerce site builder, go to your site.</span></span>
1. <span data-ttu-id="9a9e9-113">Selecionar **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-113">Select **Fragments**.</span></span>
1. <span data-ttu-id="9a9e9-114">Selecione o fragmento do cabeçalho ao qual adicionar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-114">Select the header fragment to add the message to.</span></span>
1. <span data-ttu-id="9a9e9-115">Na árvore em destaque, abra **Mensagens de erro/informações**.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-115">In the outline tree, expand **Error/Information messages**.</span></span>
1. <span data-ttu-id="9a9e9-116">Selecione o módulo de alerta e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-116">Select the alert module, and then select **OK**.</span></span> <span data-ttu-id="9a9e9-117">Se um módulo de alerta não existir ainda, primeiro selecione o botão de reticências (**...**) ao lado de **Mensagens de erro/ informações** e depois selecione, **Adicionar o módulo**.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-117">If an alert module doesn't yet exist, first select the ellipsis button (**...**) next to **Error/Information messages**, and then select **Add module**.</span></span>
1. <span data-ttu-id="9a9e9-118">No painel de propriedade à direita, na guia **Dados**, selecione **Adicionar fonte de dados** e **Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-118">In the property pane on the right, on the **Data** tab, select **Add Data Source**, and then select **Content**.</span></span>
1. <span data-ttu-id="9a9e9-119">No campo **Texto da entrada**, insira o texto da mensagem de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-119">In the **Input Text** field, enter the text of the welcome message.</span></span>
1. <span data-ttu-id="9a9e9-120">Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento do cabeçalho e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-120">Select **Save**, select **Finish editing** to check in the header fragment, and then select **Publish** to publish it.</span></span> 

<span data-ttu-id="9a9e9-121">A mensagem de boas-vindas aparecerá na parte superior de cada página do site usando o fragmento do cabeçalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="9a9e9-121">The welcome message will now appear at the top of every site page that uses the selected header fragment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9a9e9-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9a9e9-122">Additional resources</span></span>

[<span data-ttu-id="9a9e9-123">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="9a9e9-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="9a9e9-124">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="9a9e9-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="9a9e9-125">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="9a9e9-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="9a9e9-126">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="9a9e9-126">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="9a9e9-127">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="9a9e9-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="9a9e9-128">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="9a9e9-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="9a9e9-129">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="9a9e9-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
