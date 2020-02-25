---
title: Configurar e executar trabalho para lançar declarações
description: Este procedimento orienta como configurar e executar um trabalho em lotes recorrente para lançar demonstrativos para uma loja ou grupo de lojas selecionado.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09a47e268e271cf86e63ceff913435842f017bb5
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021585"
---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="ea531-103">Configurar e executar trabalho para lançar declarações</span><span class="sxs-lookup"><span data-stu-id="ea531-103">Configure and run job to post statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="ea531-104">Este procedimento orienta como configurar e executar um trabalho em lotes recorrente para lançar demonstrativos para uma loja ou grupo de lojas selecionado.</span><span class="sxs-lookup"><span data-stu-id="ea531-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="ea531-105">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="ea531-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="ea531-106">Vá para Todos os espaços de trabalho > ..</span><span class="sxs-lookup"><span data-stu-id="ea531-106">Go to All workspaces > ..</span></span> <span data-ttu-id="ea531-107">> Finanças da loja.</span><span class="sxs-lookup"><span data-stu-id="ea531-107">> Store financials.</span></span>
2. <span data-ttu-id="ea531-108">Clique em Lançar demonstrativos em lote.</span><span class="sxs-lookup"><span data-stu-id="ea531-108">Click Post statements in batch.</span></span>
    * <span data-ttu-id="ea531-109">Selecione uma hierarquia da organização e, na árvore de nós da organização, selecione uma loja individual ou um nó.</span><span class="sxs-lookup"><span data-stu-id="ea531-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="ea531-110">Selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.</span><span class="sxs-lookup"><span data-stu-id="ea531-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="ea531-111">Clique na seta para adicionar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="ea531-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="ea531-112">Clique na guia Executar em segundo plano. ![Executar em segundo plano](../dev-itpro/media/runbackground.png "Executar em segundo plano")</span><span class="sxs-lookup"><span data-stu-id="ea531-112">Click the Run in the background tab. ![Run in the background](../dev-itpro/media/runbackground.png "Run in the background")</span></span> 
4. <span data-ttu-id="ea531-113">Marque ou desmarque a caixa de seleção Processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="ea531-113">Check or uncheck the Batch processing checkbox.</span></span>
<span data-ttu-id="ea531-114">![Processamento em lotes](../dev-itpro/media/batchprocessing.png "Recorrência e processamento em lotes")</span><span class="sxs-lookup"><span data-stu-id="ea531-114">![Batch Processing](../dev-itpro/media/batchprocessing.png "Batch Processing & Recurrance")</span></span> 
5. <span data-ttu-id="ea531-115">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="ea531-115">Click Recurrence.</span></span>
6. <span data-ttu-id="ea531-116">No campo Data de início, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="ea531-116">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="ea531-117">No campo Hora de início, insira um horário.</span><span class="sxs-lookup"><span data-stu-id="ea531-117">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="ea531-118">Escolha se deseja terminar a recorrência após um número específico de execuções, em uma data específica ou nunca.</span><span class="sxs-lookup"><span data-stu-id="ea531-118">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="ea531-119">Escolha dentre as várias opções para definir com que frequência deseja que o trabalho seja executado.</span><span class="sxs-lookup"><span data-stu-id="ea531-119">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="ea531-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ea531-120">Click OK.</span></span>
9. <span data-ttu-id="ea531-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ea531-121">Click OK.</span></span>

