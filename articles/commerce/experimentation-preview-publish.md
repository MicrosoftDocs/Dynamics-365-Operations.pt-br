---
title: Visualizar e publicar um experimento
description: Este tópico descreve como visualizar e publicar um experimento desde o Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
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
ms.openlocfilehash: f1a565917ab7a048d4d455bc0a0fbd9316237aeb
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "4410327"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="96c94-103">Visualizar e publicar um experimento</span><span class="sxs-lookup"><span data-stu-id="96c94-103">Preview and publish an experiment</span></span>

<span data-ttu-id="96c94-104">Este tópico descreve como visualizar e publicar seu experimento no Dynamics 365 Commerce depois de [conectar seu experimento e editar suas variações](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="96c94-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="96c94-105">O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="96c94-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="96c94-106">Etapas adicionais são abordadas em tópicos separados.</span><span class="sxs-lookup"><span data-stu-id="96c94-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="96c94-107">[ ![Jornada do usuário na experimentação - visualizar e publicar](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="96c94-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="96c94-108">Visualizar suas variações de experimento</span><span class="sxs-lookup"><span data-stu-id="96c94-108">Preview your experiment variations</span></span>
<span data-ttu-id="96c94-109">Você pode visualizar suas variações e continuar editando-as até que tenham a aparência desejada.</span><span class="sxs-lookup"><span data-stu-id="96c94-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

<span data-ttu-id="96c94-110">Para visualizar suas variações de experimento no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="96c94-110">To preview your experiment variations in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="96c94-111">No menu suspenso de variações, abaixo da barra de comandos, selecione o conteúdo a ser visualizado.</span><span class="sxs-lookup"><span data-stu-id="96c94-111">From the variations drop-down menu below the command bar, select the content you want to preview.</span></span> 
1. <span data-ttu-id="96c94-112">Na barra de comandos, selecione **Visualização**.</span><span class="sxs-lookup"><span data-stu-id="96c94-112">On the command bar, select **Preview**.</span></span> <span data-ttu-id="96c94-113">Será exibida uma visualização da aparência do conteúdo quando publicado.</span><span class="sxs-lookup"><span data-stu-id="96c94-113">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="96c94-114">Para visualizar uma variação diferente, selecione-a no menu suspensa de variação e selecione **Visualização** novamente.</span><span class="sxs-lookup"><span data-stu-id="96c94-114">To preview a different variation, select it from the variation drop-down menu and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="96c94-115">Publicar seu experimento</span><span class="sxs-lookup"><span data-stu-id="96c94-115">Publish your experiment</span></span>
<span data-ttu-id="96c94-116">Se você não estiver usando um grupo de publicação para agendar quando o experimento ficará ativo e desejar publicar imediatamente, selecione **Publicar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="96c94-116">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="96c94-117">Todas as variações que pertencem ao experimento serão publicadas.</span><span class="sxs-lookup"><span data-stu-id="96c94-117">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="96c94-118">Se a página tiver uma URL não publicada, você deverá primeiro publicar a URL ou ela não ficará visível para os usuários do site.</span><span class="sxs-lookup"><span data-stu-id="96c94-118">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="96c94-119">Para obter detalhes, consulte [Salvar, visualizar, e publicar uma página](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="96c94-119">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="96c94-120">Usar grupos de publicação para agendar quando o experimento ficará ativo</span><span class="sxs-lookup"><span data-stu-id="96c94-120">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="96c94-121">As variações criadas no construtor de sites podem ser agendadas para publicação usando um grupo de publicação.</span><span class="sxs-lookup"><span data-stu-id="96c94-121">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="96c94-122">Em um grupo de publicações, você pode conectar uma página ou fragmento ao seu experimento selecionando **Experimentos** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="96c94-122">Within a publish group, you can connect a page or fragment to your experiment by selecting **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="96c94-123">Você também pode fazer isso selecionando **Páginas** ou **Fragmentos** e seguindo as instruções em [Conectar um experimento e editar variações](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="96c94-123">You can also do this by selecting **Pages** or **Fragments** and following the instructions in [Connect an experiment and edit variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="96c94-124">Para obter informações sobre grupos de publicação, consulte [Trabalhar com grupos de publicação](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="96c94-124">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="96c94-125">Ao usar grupos de publicação com experimentos, há algumas considerações importantes a serem observadas.</span><span class="sxs-lookup"><span data-stu-id="96c94-125">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="96c94-126">Quando você adiciona uma página ou um fragmento com um experimento em execução em um grupo de publicação, o experimento será removido da página ou fragmento no grupo de publicação.</span><span class="sxs-lookup"><span data-stu-id="96c94-126">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="96c94-127">Os experimentos conectados a páginas em um site ativo não estão disponíveis para páginas em grupos de publicação e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="96c94-127">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="96c94-128">Da mesma forma, as páginas com experimentos em execução em um site ativo não estão disponíveis para outros experimentos em grupos de publicação e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="96c94-128">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="96c94-129">Quando você publica ou planeja um grupo de publicação, todo o conteúdo do grupo de publicação é publicado, independentemente de haver um experimento associado ao grupo de publicação.</span><span class="sxs-lookup"><span data-stu-id="96c94-129">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="96c94-130">Como um grupo de publicação continua a persistir após ser publicado em um site ativo, os experimentos no grupo de publicação também persistirão.</span><span class="sxs-lookup"><span data-stu-id="96c94-130">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="96c94-131">Portanto, você não poderá associar outros experimentos à mesma página ou fragmento.</span><span class="sxs-lookup"><span data-stu-id="96c94-131">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="96c94-132">Para evitar essa limitação, exclua todos os grupos de publicações com experimentos persistentes.</span><span class="sxs-lookup"><span data-stu-id="96c94-132">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="96c94-133">Da mesma forma, se você deseja excluir um experimento em um site ativo que também existe em um grupo de publicação, exclua-a do grupo de publicação primeiro.</span><span class="sxs-lookup"><span data-stu-id="96c94-133">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="96c94-134">Etapa anterior</span><span class="sxs-lookup"><span data-stu-id="96c94-134">Previous step</span></span>
[<span data-ttu-id="96c94-135">Conectar e editar um experimento</span><span class="sxs-lookup"><span data-stu-id="96c94-135">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="96c94-136">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="96c94-136">Next step</span></span>
[<span data-ttu-id="96c94-137">Executar e monitorar um experimento</span><span class="sxs-lookup"><span data-stu-id="96c94-137">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
