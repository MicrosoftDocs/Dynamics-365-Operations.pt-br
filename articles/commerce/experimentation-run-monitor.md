---
title: Executar e monitorar um experimento
description: Este tópico descreve como executar e monitorar um experimento em um serviço de terceiros. Também descreve como fazer alterações em variações após o início do experimento.
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
ms.openlocfilehash: ee86a6761b27f3c08a65a2e250659cdcfd71db44
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "4097013"
---
# <a name="run-and-monitor-an-experiment"></a><span data-ttu-id="47252-104">Executar e monitorar um experimento</span><span class="sxs-lookup"><span data-stu-id="47252-104">Run and monitor an experiment</span></span>

<span data-ttu-id="47252-105">Este tópico descreve como executar e monitorar seu experimento em um aplicativo de terceiros e alterar variações, se necessário.</span><span class="sxs-lookup"><span data-stu-id="47252-105">This topic describes how to run and monitor your experiment in a third-party app, and change variations if needed.</span></span> <span data-ttu-id="47252-106">Antes de concluir as etapas deste tópico, primeiro você precisará [publicar](experimentation-preview-publish.md) seu experimento no Commerce.</span><span class="sxs-lookup"><span data-stu-id="47252-106">Before you complete the steps in this topic, you'll first need to [publish](experimentation-preview-publish.md) your experiment in Commerce.</span></span> 

<span data-ttu-id="47252-107">O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="47252-107">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="47252-108">Etapas adicionais são abordadas em tópicos separados.</span><span class="sxs-lookup"><span data-stu-id="47252-108">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="47252-109">[ ![Usuário de teste de experimentação - executar e monitorar](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="47252-109">[ ![Experimentation user journey - Run & Monitor](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span></span>

<span data-ttu-id="47252-110">Depois de publicar as variações, todas as etapas necessárias no Commerce para executar seu experimento estarão concluídas.</span><span class="sxs-lookup"><span data-stu-id="47252-110">After you publish your variations, all of the steps you need to do in Commerce to run your experiment are complete.</span></span> <span data-ttu-id="47252-111">A próxima etapa é determinar qual variação mostrar para cada usuário quando ele solicitar uma página.</span><span class="sxs-lookup"><span data-stu-id="47252-111">The next step is determining which variation to show to each user when they request a page.</span></span> <span data-ttu-id="47252-112">O serviço de terceiros faz essa determinação, mas primeiro você precisa ativar o experimento no serviço.</span><span class="sxs-lookup"><span data-stu-id="47252-112">The third-party service makes that determination, but first you have to activate the experiment within the service.</span></span> <span data-ttu-id="47252-113">Como as etapas para ativar um experimento variam de serviço para serviço, você precisará seguir as instruções incluídas no serviço ou provedor.</span><span class="sxs-lookup"><span data-stu-id="47252-113">Since the steps for activating an experiment vary from service to service, you'll need to follow the instructions included with your service or provider.</span></span> <span data-ttu-id="47252-114">Se o experimento não estiver ativado, os usuários verão apenas a versão padrão da página (nenhuma variação será exibida).</span><span class="sxs-lookup"><span data-stu-id="47252-114">If the experiment is not activated, users will only see the default version of the page (no variations will be displayed).</span></span>

<span data-ttu-id="47252-115">Você precisará manter a execução de experimento longa o bastante para retirar dados para resultados válidos estatisticamente.</span><span class="sxs-lookup"><span data-stu-id="47252-115">You'll need to keep the experiment running long enough to gather data for statistically valid results.</span></span> <span data-ttu-id="47252-116">Use o serviço de terceiros para monitorar os dados relacionados à experimentação e a análise durante a execução do experimento.</span><span class="sxs-lookup"><span data-stu-id="47252-116">Use the third-party service to monitor the experiment-related data and analytics while the experiment is running.</span></span>

## <a name="adjust-your-variations"></a><span data-ttu-id="47252-117">Ajustar suas variações</span><span class="sxs-lookup"><span data-stu-id="47252-117">Adjust your variations</span></span>
<span data-ttu-id="47252-118">Se, por alguma razão, você precisar modificar suas variações, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="47252-118">If for any reason you need to modify your variations, follow the steps below.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47252-119">Se você fizer alterações em um experimento ativo no Commerce ou no serviço de terceiros, seus resultados poderão ser significativamente afetados.</span><span class="sxs-lookup"><span data-stu-id="47252-119">If you make changes to a live experiment in Commerce or the third-party service, your results may be significantly impacted.</span></span> <span data-ttu-id="47252-120">É recomendável deixar o experimento seguir seu curso e criar um novo experimento para alterações importantes.</span><span class="sxs-lookup"><span data-stu-id="47252-120">Consider letting the experiment run its course and then creating a new experiment for major changes.</span></span>

1. <span data-ttu-id="47252-121">No construtor de sites do Commerce, selecione **Experimentos** no painel de navegação esquerdo e selecione o experimento.</span><span class="sxs-lookup"><span data-stu-id="47252-121">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
1. <span data-ttu-id="47252-122">Selecione a variação que deseja atualizar no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="47252-122">Select the variation you want to update from the drop-down menu.</span></span>
1. <span data-ttu-id="47252-123">Faça as alterações necessárias e visualize e publique as variações.</span><span class="sxs-lookup"><span data-stu-id="47252-123">Make any needed changes, and then preview and publish the variations.</span></span> <span data-ttu-id="47252-124">Para obter mais informações, consulte [Visualizar e publicar um experimento](experimentation-preview-publish.md).</span><span class="sxs-lookup"><span data-stu-id="47252-124">For more information, see [Preview and publish an experiment](experimentation-preview-publish.md).</span></span>
1. <span data-ttu-id="47252-125">Acesse o serviço de terceiros para fazer as alterações relacionadas à configuração de experimentos.</span><span class="sxs-lookup"><span data-stu-id="47252-125">Go to the third-party service to make any experiment setup-related changes.</span></span>
    
## <a name="previous-step"></a><span data-ttu-id="47252-126">Etapa anterior</span><span class="sxs-lookup"><span data-stu-id="47252-126">Previous step</span></span>
[<span data-ttu-id="47252-127">Visualizar e publicar um experimento</span><span class="sxs-lookup"><span data-stu-id="47252-127">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)

## <a name="next-step"></a><span data-ttu-id="47252-128">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="47252-128">Next step</span></span>
[<span data-ttu-id="47252-129">Promover uma variação e concluir um experimento</span><span class="sxs-lookup"><span data-stu-id="47252-129">Promote a variation and complete an experiment</span></span>](experimentation-review-complete.md)
