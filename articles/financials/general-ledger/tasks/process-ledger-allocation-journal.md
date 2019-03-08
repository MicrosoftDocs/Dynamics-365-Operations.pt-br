---
title: Processar diário de alocação do razão
description: Use a página Processar solicitação de alocação para criar um diário de alocação que possa ser revisto e aprovado antes do lançamento na Contabilidade ou que possa ser lançado diretamente na Contabilidade.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2046e25719c9023bee99736488a4ee6f22723fe
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "335637"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="4a9e6-103">Processar diário de alocação do razão</span><span class="sxs-lookup"><span data-stu-id="4a9e6-103">Process ledger allocation journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4a9e6-104">Use a página Processar solicitação de alocação para criar um diário de alocação que possa ser revisto e aprovado antes do lançamento na Contabilidade ou que possa ser lançado diretamente na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-104">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="4a9e6-105">Antes de criar um diário de alocações, deve haver pelo menos uma regra de alocação do razão ativa.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-105">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="4a9e6-106">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="4a9e6-107">Vá para Contabilidade > Alocações > Processar solicitação de alocação.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-107">Go to General ledger > Allocations > Process allocation request.</span></span>
2. <span data-ttu-id="4a9e6-108">No campo Regra, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-108">In the Rule field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="4a9e6-109">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="4a9e6-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="4a9e6-111">No campo A partir da data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-111">In the As of date field, enter a date.</span></span>
    * <span data-ttu-id="4a9e6-112">O campo A partir da data é muito importante quando o razão é a fonte de dados para a regra.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-112">The As of Date is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="4a9e6-113">Essa data controla quais saldos do razão serão incluídos na alocação.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-113">This date controls which ledger balances to include for allocation.</span></span>     <span data-ttu-id="4a9e6-114">No campo Fonte zero, selecione Parar.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-114">In the Zero source field select Stop.</span></span> <span data-ttu-id="4a9e6-115">Isso interromperá o processo de alocação e exibirá uma mensagem informando que um valor de origem zero foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-115">This will  Stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  
6. <span data-ttu-id="4a9e6-116">No campo Opções de proposta, selecione 'Somente proposta'.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-116">In the Proposal options field, select 'Proposal only'.</span></span>
    * <span data-ttu-id="4a9e6-117">Selecione Proposta apenas para revisar e opcionalmente aprovar o resultado em Diários de alocação antes de lançar a alocação na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-117">Select Proposal only to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
7. <span data-ttu-id="4a9e6-118">No campo Lançamento GL, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-118">In the GL posting date field, enter a date.</span></span>
8. <span data-ttu-id="4a9e6-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-119">Click OK.</span></span>
9. <span data-ttu-id="4a9e6-120">Vá para Contabilidade > Alocações > Diários de alocação.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-120">Go to General ledger > Allocations > Allocation journals.</span></span>
10. <span data-ttu-id="4a9e6-121">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-121">Click Lines.</span></span>
11. <span data-ttu-id="4a9e6-122">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-122">Click Post.</span></span>
12. <span data-ttu-id="4a9e6-123">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="4a9e6-123">Click Post.</span></span>

