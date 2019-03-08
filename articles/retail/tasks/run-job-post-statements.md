---
title: Configurar e executar trabalho para lançar declarações
description: Este procedimento orienta como configurar e executar um trabalho em lotes recorrente para lançar demonstrativos para uma loja ou grupo de lojas selecionado.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 676216d90c50c0d3fa1a839cab7a734e624708ba
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "346286"
---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="5f8f8-103">Configurar e executar trabalho para lançar declarações</span><span class="sxs-lookup"><span data-stu-id="5f8f8-103">Configure and run job to post statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5f8f8-104">Este procedimento orienta como configurar e executar um trabalho em lotes recorrente para lançar demonstrativos para uma loja ou grupo de lojas selecionado.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="5f8f8-105">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="5f8f8-106">Vá para Todos os espaços de trabalho > ..</span><span class="sxs-lookup"><span data-stu-id="5f8f8-106">Go to All workspaces > ..</span></span> <span data-ttu-id="5f8f8-107">> Finanças da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-107">> Retail store financials.</span></span>
2. <span data-ttu-id="5f8f8-108">Clique em Lançar demonstrativos.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-108">Click Post statements.</span></span>
    * <span data-ttu-id="5f8f8-109">Selecione uma hierarquia da organização e, na árvore de nós da organização, selecione uma loja individual ou um nó.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="5f8f8-110">Selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="5f8f8-111">Clique na seta para adicionar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="5f8f8-112">Clique na guia Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-112">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="5f8f8-113">Marque ou desmarque a caixa de seleção Processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-113">Check or uncheck the Batch processing checkbox.</span></span>
5. <span data-ttu-id="5f8f8-114">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-114">Click Recurrence.</span></span>
6. <span data-ttu-id="5f8f8-115">No campo Data de início, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-115">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="5f8f8-116">No campo Hora de início, insira um horário.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-116">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="5f8f8-117">Escolha se deseja terminar a recorrência após um número específico de execuções, em uma data específica ou nunca.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-117">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="5f8f8-118">Escolha dentre as várias opções para definir com que frequência deseja que o trabalho seja executado.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-118">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="5f8f8-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-119">Click OK.</span></span>
9. <span data-ttu-id="5f8f8-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5f8f8-120">Click OK.</span></span>

