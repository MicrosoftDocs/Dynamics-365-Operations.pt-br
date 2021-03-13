---
title: Solucionar problemas de fabricação de processo
description: Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com fabricação de processos.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d999c91aa1cc14f29ebfa6be8e456e45ef0d3fa4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966171"
---
# <a name="troubleshoot-process-manufacturing"></a><span data-ttu-id="78312-103">Solucionar problemas de fabricação de processo</span><span class="sxs-lookup"><span data-stu-id="78312-103">Troubleshoot process manufacturing</span></span>

<span data-ttu-id="78312-104">Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com fabricação de processos.</span><span class="sxs-lookup"><span data-stu-id="78312-104">This topic describes how to fix issues that you might encounter while you work with process manufacturing.</span></span>

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a><span data-ttu-id="78312-105">Quando eu uso o dispositivo de ficha de trabalho para relatar uma quantidade parcial do último trabalho em uma ordem de produção, todos os trabalhos anteriores nessa ordem com status Em andamento são encerrados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="78312-105">When I use the job card device to report a partial quantity on the last job in a production order, all the previous jobs on that order that have a status of In progress are automatically ended.</span></span>

<span data-ttu-id="78312-106">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="78312-106">This behavior is by design.</span></span> <span data-ttu-id="78312-107">Na página **Padrões de ordem de produção**, na guia **Relatar como concluído**, há uma opção chamada **Marcar fim de roteiro**.</span><span class="sxs-lookup"><span data-stu-id="78312-107">On the **Production order defaults** page, on the **Report as finished** tab, there is an option that is named **End-mark route**.</span></span> <span data-ttu-id="78312-108">Se este tópico for definido como *Sim*, um diário de cartão de rota será lançado quando um trabalhador usar o dispositivo de cartão de trabalho ou terminal de cartão de trabalho para relatar a operação mais recente.</span><span class="sxs-lookup"><span data-stu-id="78312-108">If this topic is set to *Yes*, a route card journal is posted when a worker uses the job card device or job card terminal to report the last operation.</span></span> <span data-ttu-id="78312-109">Esse diário marca todas as operações como concluídas e encerra todos os trabalhos de produção.</span><span class="sxs-lookup"><span data-stu-id="78312-109">This journal marks all the operations as completed and ends all the production jobs.</span></span> <span data-ttu-id="78312-110">Quando a opção **Marcar fim de roteiro** é definida como *Sim*, o sistema não considera o status do trabalho que o trabalhador selecionou quando relatou a operação mais recente.</span><span class="sxs-lookup"><span data-stu-id="78312-110">When the **End-mark route** option is set to *Yes*, the system doesn't consider the job status that the worker selected when they reported the last operation.</span></span> <span data-ttu-id="78312-111">O sistema também não considera se o trabalhador está relatando uma quantidade total ou parcial.</span><span class="sxs-lookup"><span data-stu-id="78312-111">The system also doesn't consider whether the worker is reporting a full or partial quantity.</span></span>

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a><span data-ttu-id="78312-112">Quando tento um fechamento de estoque, recebo a seguinte mensagem de aviso: "Nenhuma execução de cálculo de custos de fluxo inverso com uma data %1 que corresponde ao final do período foi registrada."</span><span class="sxs-lookup"><span data-stu-id="78312-112">When I attempt a stock closing, I receive the following warning message: "No execution of Backflush costing calculation with a date %1 matching period end has been registered."</span></span>

<span data-ttu-id="78312-113">Em versões anteriores à versão 10.0.13, se você não estiver usando o fluxo de custo de produção de lean receberá a seguinte mensagem de aviso incorreta durante o fechamento de estoque:</span><span class="sxs-lookup"><span data-stu-id="78312-113">In releases before release 10.0.13, if you aren't using the lean production costing flow, you receive the following erroneous warning message during inventory closing:</span></span>

> <span data-ttu-id="78312-114">Você está prestes a executar um fechamento de estoque com uma data %1.</span><span class="sxs-lookup"><span data-stu-id="78312-114">You are about to execute an Inventory close with a date %1.</span></span> <span data-ttu-id="78312-115">Nenhuma execução de custos de fluxo inverso com uma data %1 que corresponde ao fim do período foi registrada.</span><span class="sxs-lookup"><span data-stu-id="78312-115">No execution of Backflush costing calculation with a date %1 matching period end has been registered.</span></span> <span data-ttu-id="78312-116">Lembre-se de executar um cálculo de custos de fluxo inverso com uma data de %1 que corresponda ao final do período.</span><span class="sxs-lookup"><span data-stu-id="78312-116">Please remember to execute a Backflush costing calculation with a date of %1 matching period end.</span></span> <span data-ttu-id="78312-117">A avaliação de estoques, custo dos produtos vendidos e variações podem não estar corretos no razão auxiliar ou na contabilidade até que seja executado.</span><span class="sxs-lookup"><span data-stu-id="78312-117">The valuation of inventories, cost of goods sold and variances might not be correct in Subledger or General ledger until this has been executed.</span></span>

<span data-ttu-id="78312-118">Esse problema foi corrigido na versão 10.0.13 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="78312-118">This issue has been fixed in release 10.0.13 and later.</span></span> <span data-ttu-id="78312-119">Para obter mais informações, consulte [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span><span class="sxs-lookup"><span data-stu-id="78312-119">For more information, see [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span></span>