---
title: Promover uma variação e concluir um experimento
description: Este tópico descreve como promover uma variação bem-sucedida e concluir um experimento no Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 0ea0fc8d50c25312b184ec1d3bd613695870d121
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792550"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="7d990-103">Promover uma variação e concluir um experimento</span><span class="sxs-lookup"><span data-stu-id="7d990-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="7d990-104">Este tópico descreve como promover a variação que produziu os melhores resultados no seu experimento e como concluí-lo.</span><span class="sxs-lookup"><span data-stu-id="7d990-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="7d990-105">O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7d990-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="7d990-106">Etapas adicionais são abordadas em tópicos separados.</span><span class="sxs-lookup"><span data-stu-id="7d990-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="7d990-107">[ ![Jornada do usuário na experimentação - análise e conclusão](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7d990-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="7d990-108">Depois de [executar seu experimento](experimentation-run-monitor.md) e retirar dados suficientes para determinar qual variação você deseja usar no seu site ativo, promova a variação e encerre o experimento.</span><span class="sxs-lookup"><span data-stu-id="7d990-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="7d990-109">Promover uma variação</span><span class="sxs-lookup"><span data-stu-id="7d990-109">Promote a variation</span></span>
<span data-ttu-id="7d990-110">Use os dados e a análise relacionados ao experimento no serviço de terceiros para decidir que variação produziu os melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="7d990-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="7d990-111">Você poderá então promovê-la substituindo o conteúdo atual no site ativo com a variação vencedora para que fique disponível para todos os usuários do seu site, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="7d990-111">You can then promote it by replacing the current content on the live site with the winning variation so that it's available to all users of your website.</span></span>

<span data-ttu-id="7d990-112">Para promover a variação vencedora, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7d990-112">To promote the winning variation, follow these steps.</span></span> 

1. <span data-ttu-id="7d990-113">No construtor de sites do Commerce, selecione **Experimentos** no painel de navegação esquerdo e selecione o experimento.</span><span class="sxs-lookup"><span data-stu-id="7d990-113">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span>
1. <span data-ttu-id="7d990-114">Na barra de comando, selecione **Concluir experimento**.</span><span class="sxs-lookup"><span data-stu-id="7d990-114">On the command bar, select **Complete experiment**.</span></span>
1. <span data-ttu-id="7d990-115">Na caixa de diálogo **Completar o experimento**, selecione **Analisar os dados do experimento**.</span><span class="sxs-lookup"><span data-stu-id="7d990-115">In the **Complete the experiment** dialog box, select **Review the experiment data**.</span></span> <span data-ttu-id="7d990-116">O serviço de terceiros abre onde você pode validar as métricas e determinar qual variação teve o melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="7d990-116">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="7d990-117">Na caixa de diálogo **Completar o experimento** no construtor de sites, selecione a variação vencedora e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7d990-117">In the **Complete the experiment** dialog box, select the winning variation, and then select **Next**.</span></span>
1. <span data-ttu-id="7d990-118">Abra o serviço de terceiros e interrompa o experimento.</span><span class="sxs-lookup"><span data-stu-id="7d990-118">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="7d990-119">No construtor de sites, selecione **Completar** para substituir a página ativa original e publicar a variação vencedora para que ela fique disponível para todos os usuários do seu site.</span><span class="sxs-lookup"><span data-stu-id="7d990-119">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="7d990-120">Se você optar por manter a página ativa atual e não publicar uma variação, selecione **Republicar a página original**.</span><span class="sxs-lookup"><span data-stu-id="7d990-120">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="7d990-121">Excluir seu experimento</span><span class="sxs-lookup"><span data-stu-id="7d990-121">Delete your experiment</span></span>
<span data-ttu-id="7d990-122">Embora não seja necessário excluir um experimento concluído no Commerce, você pode optar por excluí-lo para economizar espaço ou limpar o espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7d990-122">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> 

<span data-ttu-id="7d990-123">Para excluir um experimento no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7d990-123">To delete an experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="7d990-124">Selecione **Experimentos** no painel de navegação esquerdo e selecione o experimento.</span><span class="sxs-lookup"><span data-stu-id="7d990-124">Select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="7d990-125">Se o experimento ainda estiver ativo, interrompa-o no serviço de terceiros antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="7d990-125">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="7d990-126">Na barra de comando, selecione **Cancelar publicação** para remover o conteúdo da variação do site ativo.</span><span class="sxs-lookup"><span data-stu-id="7d990-126">On the command bar, select **Unpublish**  to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="7d990-127">Selecione **Excluir** para excluir o experimento.</span><span class="sxs-lookup"><span data-stu-id="7d990-127">Select **Delete** to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="7d990-128">Etapa anterior</span><span class="sxs-lookup"><span data-stu-id="7d990-128">Previous step</span></span>
[<span data-ttu-id="7d990-129">Executar e monitorar um experimento</span><span class="sxs-lookup"><span data-stu-id="7d990-129">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]