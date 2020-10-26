---
title: Visualizar e publicar um experimento
description: Este tópico descreve como visualizar e publicar um experimento desde o Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 91e2e4840a2d53f195d881279050b6415d48b070
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930141"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="2c30c-103">Visualizar e publicar um experimento</span><span class="sxs-lookup"><span data-stu-id="2c30c-103">Preview and publish an experiment</span></span>

<span data-ttu-id="2c30c-104">Este tópico descreve como visualizar e publicar seu experimento no Dynamics 365 Commerce depois de [conectar seu experimento e editar suas variações](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="2c30c-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="2c30c-105">O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2c30c-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="2c30c-106">Etapas adicionais são abordadas em tópicos separados.</span><span class="sxs-lookup"><span data-stu-id="2c30c-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="2c30c-107">[ ![Jornada do usuário na experimentação - visualizar e publicar](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2c30c-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="2c30c-108">Visualizar suas variações de experimento</span><span class="sxs-lookup"><span data-stu-id="2c30c-108">Preview your experiment variations</span></span>
<span data-ttu-id="2c30c-109">Você pode visualizar suas variações e continuar editando-as até que tenham a aparência desejada.</span><span class="sxs-lookup"><span data-stu-id="2c30c-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

1. <span data-ttu-id="2c30c-110">No construtor de sites, use o menu suspenso de variações, abaixo da barra de comandos, para selecionar o conteúdo a ser visualizado.</span><span class="sxs-lookup"><span data-stu-id="2c30c-110">In site builder, use the variations drop-down menu below the command bar to select the content you want to preview.</span></span> 
1. <span data-ttu-id="2c30c-111">Selecione **Visualização** na barra superior.</span><span class="sxs-lookup"><span data-stu-id="2c30c-111">Select **Preview** in the top bar.</span></span> <span data-ttu-id="2c30c-112">Será exibida uma visualização da aparência do conteúdo quando publicado.</span><span class="sxs-lookup"><span data-stu-id="2c30c-112">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="2c30c-113">Para visualizar uma variação diferente, selecione-a na lista suspensa de variação e selecione **Visualização** novamente.</span><span class="sxs-lookup"><span data-stu-id="2c30c-113">To preview a different variation, select it from the variation drop-down and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="2c30c-114">Publicar seu experimento</span><span class="sxs-lookup"><span data-stu-id="2c30c-114">Publish your experiment</span></span>
<span data-ttu-id="2c30c-115">Se você não estiver usando um grupo de publicação para agendar quando o experimento ficará ativo e desejar publicar imediatamente, selecione **Publicar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="2c30c-115">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="2c30c-116">Todas as variações que pertencem ao experimento serão publicadas.</span><span class="sxs-lookup"><span data-stu-id="2c30c-116">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="2c30c-117">Se a página tiver uma URL não publicada, você deverá primeiro publicar a URL ou ela não ficará visível para os usuários do site.</span><span class="sxs-lookup"><span data-stu-id="2c30c-117">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="2c30c-118">Para obter detalhes, consulte [Salvar, visualizar, e publicar uma página](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="2c30c-118">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="2c30c-119">Usar grupos de publicação para agendar quando o experimento ficará ativo</span><span class="sxs-lookup"><span data-stu-id="2c30c-119">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="2c30c-120">As variações criadas no construtor de sites podem ser agendadas para publicação usando um grupo de publicação.</span><span class="sxs-lookup"><span data-stu-id="2c30c-120">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="2c30c-121">Em um grupo de publicação, você pode conectar uma página ou fragmento ao seu experimento indo para a guia **Experimentos** ou a guia **Páginas** ou **Fragmentos**. Para obter mais , consulte [Conectar um tópico de variações de experimento e edição](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="2c30c-121">Within a publish group, you can connect a page or fragment to your experiment by going to the **Experiments** tab or the **Pages** or **Fragments** tab. For more information, see [Connect an experiment and edit variations](experimentation-connect-edit.md) topic.</span></span> <span data-ttu-id="2c30c-122">Para obter informações sobre grupos de publicação, consulte [Trabalhar com grupos de publicação](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="2c30c-122">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="2c30c-123">Ao usar grupos de publicação com experimentos, há algumas considerações importantes a serem observadas.</span><span class="sxs-lookup"><span data-stu-id="2c30c-123">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="2c30c-124">Quando você adiciona uma página ou um fragmento com um experimento em execução em um grupo de publicação, o experimento será removido da página ou fragmento no grupo de publicação.</span><span class="sxs-lookup"><span data-stu-id="2c30c-124">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="2c30c-125">Os experimentos conectados a páginas em um site ativo não estão disponíveis para páginas em grupos de publicação e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="2c30c-125">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="2c30c-126">Da mesma forma, as páginas com experimentos em execução em um site ativo não estão disponíveis para outros experimentos em grupos de publicação e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="2c30c-126">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="2c30c-127">Quando você publica ou planeja um grupo de publicação, todo o conteúdo do grupo de publicação é publicado, independentemente de haver um experimento associado ao grupo de publicação.</span><span class="sxs-lookup"><span data-stu-id="2c30c-127">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="2c30c-128">Como um grupo de publicação continua a persistir após ser publicado em um site ativo, os experimentos no grupo de publicação também persistirão.</span><span class="sxs-lookup"><span data-stu-id="2c30c-128">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="2c30c-129">Portanto, você não poderá associar outros experimentos à mesma página ou fragmento.</span><span class="sxs-lookup"><span data-stu-id="2c30c-129">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="2c30c-130">Para evitar essa limitação, exclua todos os grupos de publicações com experimentos persistentes.</span><span class="sxs-lookup"><span data-stu-id="2c30c-130">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="2c30c-131">Da mesma forma, se você deseja excluir um experimento em um site ativo que também existe em um grupo de publicação, exclua-a do grupo de publicação primeiro.</span><span class="sxs-lookup"><span data-stu-id="2c30c-131">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="2c30c-132">Etapa anterior</span><span class="sxs-lookup"><span data-stu-id="2c30c-132">Previous step</span></span>
[<span data-ttu-id="2c30c-133">Conectar e editar um experimento</span><span class="sxs-lookup"><span data-stu-id="2c30c-133">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="2c30c-134">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2c30c-134">Next step</span></span>
[<span data-ttu-id="2c30c-135">Executar e monitorar um experimento</span><span class="sxs-lookup"><span data-stu-id="2c30c-135">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
