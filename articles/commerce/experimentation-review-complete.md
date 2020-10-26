---
title: Promover uma variação e concluir um experimento
description: Este tópico descreve como promover uma variação bem-sucedida e concluir um experimento no Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930136"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="ed162-103">Promover uma variação e concluir um experimento</span><span class="sxs-lookup"><span data-stu-id="ed162-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="ed162-104">Este tópico descreve como promover a variação que produziu os melhores resultados no seu experimento e como concluí-lo.</span><span class="sxs-lookup"><span data-stu-id="ed162-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="ed162-105">O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed162-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="ed162-106">Etapas adicionais são abordadas em tópicos separados.</span><span class="sxs-lookup"><span data-stu-id="ed162-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="ed162-107">[ ![Jornada do usuário na experimentação - análise e conclusão](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ed162-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="ed162-108">Depois de [executar seu experimento](experimentation-run-monitor.md) e retirar dados suficientes para determinar qual variação você deseja usar no seu site ativo, promova a variação e encerre o experimento.</span><span class="sxs-lookup"><span data-stu-id="ed162-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="ed162-109">Promover uma variação</span><span class="sxs-lookup"><span data-stu-id="ed162-109">Promote a variation</span></span>
<span data-ttu-id="ed162-110">Use os dados e a análise relacionados ao experimento no serviço de terceiros para decidir que variação produziu os melhores resultados.</span><span class="sxs-lookup"><span data-stu-id="ed162-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="ed162-111">Para substituir o conteúdo atual no site ativo com a variação vencedora para que fique disponível para todos os usuários do seu site, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="ed162-111">To replace the current content on the live site with the winning variation so that it's available to all users of your website, do the following.</span></span> 

1. <span data-ttu-id="ed162-112">Vá para a guia **Experimentos** no construtor de sites e selecione o experimento.</span><span class="sxs-lookup"><span data-stu-id="ed162-112">Go to the **Experiments** tab in site builder and select the experiment.</span></span>
1. <span data-ttu-id="ed162-113">Selecione **Experimento completo** na barra superior.</span><span class="sxs-lookup"><span data-stu-id="ed162-113">Select **Complete experiment** on the top bar.</span></span>
1. <span data-ttu-id="ed162-114">No menu de diálogo **Completar o experimento**, selecione **Analisar os dados do experimento**.</span><span class="sxs-lookup"><span data-stu-id="ed162-114">In the **Complete the experiment** dialog menu, select **Review the experiment data**.</span></span> <span data-ttu-id="ed162-115">O serviço de terceiros abre onde você pode validar as métricas e determinar qual variação teve o melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="ed162-115">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="ed162-116">No menu do diálogo **Completar o experimento** no construtor de sites, selecione a variação vencedora e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ed162-116">In the **Complete the experiment** dialog menu in site builder, select the winning variation and then select **Next**.</span></span>
1. <span data-ttu-id="ed162-117">Abra o serviço de terceiros e interrompa o experimento.</span><span class="sxs-lookup"><span data-stu-id="ed162-117">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="ed162-118">No construtor de sites, selecione **Completar** para substituir a página ativa original e publicar a variação vencedora para que ela fique disponível para todos os usuários do seu site.</span><span class="sxs-lookup"><span data-stu-id="ed162-118">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="ed162-119">Se você optar por manter a página ativa atual e não publicar uma variação, selecione **Republicar a página original**.</span><span class="sxs-lookup"><span data-stu-id="ed162-119">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="ed162-120">Excluir seu experimento</span><span class="sxs-lookup"><span data-stu-id="ed162-120">Delete your experiment</span></span>
<span data-ttu-id="ed162-121">Embora não seja necessário excluir um experimento concluído no Commerce, você pode optar por excluí-lo para economizar espaço ou limpar o espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ed162-121">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> <span data-ttu-id="ed162-122">Para excluir um experimento, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="ed162-122">To delete an experiment, do the following.</span></span>

1. <span data-ttu-id="ed162-123">Vá para a guia **Experimentos** no construtor de sites e selecione o experimento.</span><span class="sxs-lookup"><span data-stu-id="ed162-123">Go to the **Experiments** tab in site builder and select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="ed162-124">Se o experimento ainda estiver ativo, interrompa-o no serviço de terceiros antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="ed162-124">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="ed162-125">Selecione **Cancelar publicação** na barra de comandos para remover o conteúdo da variação do site ativo.</span><span class="sxs-lookup"><span data-stu-id="ed162-125">Select **Unpublish** in the command bar to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="ed162-126">Selecione **Excluir** na barra de comandos para excluir o experimento.</span><span class="sxs-lookup"><span data-stu-id="ed162-126">Select **Delete** in the command bar to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="ed162-127">Etapa anterior</span><span class="sxs-lookup"><span data-stu-id="ed162-127">Previous step</span></span>
[<span data-ttu-id="ed162-128">Executar e monitorar um experimento</span><span class="sxs-lookup"><span data-stu-id="ed162-128">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
