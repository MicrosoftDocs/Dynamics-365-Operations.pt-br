---
title: "Fechar a contabilidade no fim do período"
description: "Este tópico descreve as tarefas geralmente concluídas durante a realização de um fechamento periódico de contabilidade."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 23d4b9b070a48e1964ecd6896afe071b564d1194
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="close-the-general-ledger-at-period-end"></a><span data-ttu-id="075a6-103">Fechar a contabilidade no fim do período</span><span class="sxs-lookup"><span data-stu-id="075a6-103">Close the general ledger at period end</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="075a6-104">Este tópico descreve as tarefas geralmente concluídas durante a realização de um fechamento periódico de contabilidade.</span><span class="sxs-lookup"><span data-stu-id="075a6-104">This topic describes the tasks that are typically completed when performing a period closing for General ledger.</span></span> 

<span data-ttu-id="075a6-105">Na contabilidade, é possível concluir os procedimentos de fechamento por um período ou por um ano.</span><span class="sxs-lookup"><span data-stu-id="075a6-105">In General ledger, you can complete closing procedures for a period or a year.</span></span> <span data-ttu-id="075a6-106">Os processos de fechamento preparam o sistema para um novo período.</span><span class="sxs-lookup"><span data-stu-id="075a6-106">Closing processes prepare the system for a new period.</span></span> <span data-ttu-id="075a6-107">Para preparar o sistema para um novo ano, você deve executar o processo do fechamento de final de ano.</span><span class="sxs-lookup"><span data-stu-id="075a6-107">To prepare the system for a new year, you must run the year end close process.</span></span> <span data-ttu-id="075a6-108">Cada organização possui processos e etapas diferentes que ela executa para o final de um período.</span><span class="sxs-lookup"><span data-stu-id="075a6-108">Each organization has different processes and steps that it performs for the end of a period.</span></span> <span data-ttu-id="075a6-109">Veja a seguir algumas etapas opcionais para o fim do período:</span><span class="sxs-lookup"><span data-stu-id="075a6-109">Here are some optional steps for period ends:</span></span>

-   <span data-ttu-id="075a6-110">Conclua todas as tarefas para todos os outros módulos, como Contas a receber, Contas a pagar e Inventário.</span><span class="sxs-lookup"><span data-stu-id="075a6-110">Complete all the tasks for all other modules, such as Accounts receivable, Accounts payable, and Inventory.</span></span>
-   <span data-ttu-id="075a6-111">Verifique se todo todos os diários foram lançados.</span><span class="sxs-lookup"><span data-stu-id="075a6-111">Verify that all journals are posted.</span></span>
-   <span data-ttu-id="075a6-112">Execute a reavaliação de moeda estrangeira para gerar um lucro não realizado ou valores de perda.</span><span class="sxs-lookup"><span data-stu-id="075a6-112">Run foreign currency revaluation to generate any unrealized gain or loss amounts.</span></span>
-   <span data-ttu-id="075a6-113">Liquide transações para cada conta contábil.</span><span class="sxs-lookup"><span data-stu-id="075a6-113">Settle transactions for each ledger account.</span></span>
-   <span data-ttu-id="075a6-114">Processe as alocações necessárias.</span><span class="sxs-lookup"><span data-stu-id="075a6-114">Process any required allocations.</span></span>
-   <span data-ttu-id="075a6-115">Lançar manualmente ajustes de fim de período.Realize ajustes manuais após o período.</span><span class="sxs-lookup"><span data-stu-id="075a6-115">Manually post period-end adjustments.</span></span>
-   <span data-ttu-id="075a6-116">Lance transações e revise o relatório **diário do razão**.</span><span class="sxs-lookup"><span data-stu-id="075a6-116">Journalize transactions, and review the **Ledger journal** report.</span></span>
-   <span data-ttu-id="075a6-117">Realize a consolidação usando uma empresa de consolidação ou de relatórios financeiros.</span><span class="sxs-lookup"><span data-stu-id="075a6-117">Perform a consolidation by using a consolidation company or Financial reporting.</span></span>
-   <span data-ttu-id="075a6-118">Gere o demonstrativo financeiro do final do período usando o relatório financeiro.</span><span class="sxs-lookup"><span data-stu-id="075a6-118">Generate period-end financial statements by using Financial reporting.</span></span>
-   <span data-ttu-id="075a6-119">Defina períodos do razão para **Em espera**, de modo que não haja novos lançamentos.</span><span class="sxs-lookup"><span data-stu-id="075a6-119">Set ledger periods to **On hold**, so that no further posting occurs.</span></span> <span data-ttu-id="075a6-120">Também é possível restringir um período para um grupo de usuários específico durante as atividades de fim de período, para um melhor controle.</span><span class="sxs-lookup"><span data-stu-id="075a6-120">You can also restrict a period to a specific user group while period-end activities are occurring, for better control.</span></span> <span data-ttu-id="075a6-121">Não é recomendável definir períodos para **Fechado de forma permanente**, pois não é possível reabrir um período que foi fechado.</span><span class="sxs-lookup"><span data-stu-id="075a6-121">It's not a good idea to set periods to **Permanently closed**, because you can't reopen a period that has been closed.</span></span>

<span data-ttu-id="075a6-122">O espaço de trabalho financeiro de fechamento de período pode ser usado para organizar e controlar as tarefas necessárias para diversos processos de fechamento de período.</span><span class="sxs-lookup"><span data-stu-id="075a6-122">The Financial period close workspace can be used to organize and track the tasks required for various period end processes.</span></span> 


<span data-ttu-id="075a6-123">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="075a6-123">For more information, see the following topics for more information:</span></span>
- [<span data-ttu-id="075a6-124">Espaço de trabalho de fechamento do período financeiro</span><span class="sxs-lookup"><span data-stu-id="075a6-124">Financial period close workspace</span></span>](financial-period-close-workspace.md) 
- [<span data-ttu-id="075a6-125">Fechamento do exercício</span><span class="sxs-lookup"><span data-stu-id="075a6-125">Year end close</span></span>](Year-end-close.md)  
- [<span data-ttu-id="075a6-126">Fechamento em massa do período financeiro</span><span class="sxs-lookup"><span data-stu-id="075a6-126">Mass financial period close</span></span>](tasks/mass-financial-period-close.md)





