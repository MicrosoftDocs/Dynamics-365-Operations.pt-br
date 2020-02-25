---
title: Adicionar o código de script a páginas do site para oferecer suporte à telemetria
description: Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 674d00faf1b30f87a0b0062129e1b9fbff955dd4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001268"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="daf67-103">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="daf67-103">Add script code to site pages to support telemetry</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="daf67-104">Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.</span><span class="sxs-lookup"><span data-stu-id="daf67-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="daf67-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="daf67-105">Overview</span></span>

<span data-ttu-id="daf67-106">A análise da Web é uma ferramenta essencial quando você deseja entender como seus clientes interagem com seu site e tomar decisões que ajudarão a otimizar a experiência para obter a conversão máxima.</span><span class="sxs-lookup"><span data-stu-id="daf67-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="daf67-107">Muitos pacotes de análise da Web estão disponíveis para ajudar você a atingir esses objetivos, como Google Analytics, Clicky, Moz Analytics e KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="daf67-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="daf67-108">A maioria dos pacotes de análise da Web exige que você adicione o código de script do cliente no elemento **\<head\>** do HTML para todas as páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="daf67-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="daf67-109">As instruções neste tópico também se aplicam a outras funcionalidades personalizadas do cliente que o Microsoft Dynamics 365 Commerce não oferece nativamente.</span><span class="sxs-lookup"><span data-stu-id="daf67-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="daf67-110">Criar um fragmento reutilizável para o seu código de script</span><span class="sxs-lookup"><span data-stu-id="daf67-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="daf67-111">Depois de criar um fragmento para o seu código de script, ele pode ser reutilizado em todas as páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="daf67-111">After you create a fragment for your script code, it can be reused across all pages on your site.</span></span>

1. <span data-ttu-id="daf67-112">Vá para **Fragmentos \> Novo fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="daf67-112">Go to **Fragments \> New page fragment**.</span></span>
2. <span data-ttu-id="daf67-113">Selecione **Script externo**, insira um nome para o fragmento e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="daf67-113">Select **External Script**, enter a name for the fragment, and then select **OK**.</span></span>
3. <span data-ttu-id="daf67-114">Na hierarquia de fragmentos, selecione o filho do módulo **injetor de script** do fragmento que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="daf67-114">In the fragment hierarchy, select the **script injector** module child of the fragment that you just created.</span></span>
4. <span data-ttu-id="daf67-115">No painel de propriedades à direita, adicione seu script do cliente e defina outras opções de configuração conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="daf67-115">In the property pane on the right, add your client-side script, and set other configuration options as you require.</span></span>

## <a name="add-the-fragment-to-templates"></a><span data-ttu-id="daf67-116">Adicionar o fragmento aos modelos</span><span class="sxs-lookup"><span data-stu-id="daf67-116">Add the fragment to templates</span></span>

1. <span data-ttu-id="daf67-117">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="daf67-117">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
2. <span data-ttu-id="daf67-118">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="daf67-118">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
3. <span data-ttu-id="daf67-119">Selecione o botão de reticências (**...**) para o slot **Head do HTML** e depois selecione **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="daf67-119">Select the ellipsis button (**...**) for the **HTML Head** slot, and then select **Add fragment**.</span></span>
4. <span data-ttu-id="daf67-120">Selecione o fragmento que você criou para o seu código de script.</span><span class="sxs-lookup"><span data-stu-id="daf67-120">Select the fragment that you created for your script code.</span></span>
5. <span data-ttu-id="daf67-121">Salve o modelo e faça check-in dele.</span><span class="sxs-lookup"><span data-stu-id="daf67-121">Save the template, and check it in.</span></span>

> [!NOTE]
> <span data-ttu-id="daf67-122">Depois de terminar, você deve publicar o fragmento e o modelo mestre.</span><span class="sxs-lookup"><span data-stu-id="daf67-122">After you've finished, you must publish the fragment and the master template.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="daf67-123">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="daf67-123">Additional resources</span></span>

[<span data-ttu-id="daf67-124">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="daf67-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="daf67-125">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="daf67-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="daf67-126">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="daf67-126">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="daf67-127">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="daf67-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="daf67-128">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="daf67-128">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="daf67-129">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="daf67-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="daf67-130">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="daf67-130">Add languages to your site</span></span>](add-languages-to-site.md)

