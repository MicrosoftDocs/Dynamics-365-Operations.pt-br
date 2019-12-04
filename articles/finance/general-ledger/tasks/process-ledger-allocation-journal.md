---
title: Processar diário de alocação do razão
description: Este tópico explica como processar uma solicitação de alocação no Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 882362a03e4fc4e249b092caea374640813eef88
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186063"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="57cee-103">Processar diário de alocação do razão</span><span class="sxs-lookup"><span data-stu-id="57cee-103">Process ledger allocation journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57cee-104">Este tópico explica como processar uma solicitação de alocação.</span><span class="sxs-lookup"><span data-stu-id="57cee-104">This topic explains how to process an allocation request.</span></span> <span data-ttu-id="57cee-105">Use a página Processar solicitação de alocação para criar um diário de alocação que possa ser revisto e aprovado antes do lançamento na Contabilidade ou que possa ser lançado diretamente na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="57cee-105">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="57cee-106">Antes de criar um diário de alocações, deve haver pelo menos uma regra de alocação do razão ativa.</span><span class="sxs-lookup"><span data-stu-id="57cee-106">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="57cee-107">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="57cee-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="57cee-108">No painel de navegação, vá para **Módulos > Contabilidade > Alocações > Processar solicitação de alocação**.</span><span class="sxs-lookup"><span data-stu-id="57cee-108">In the navigation pane, go to **Modules > General ledger > Allocations > Process allocation request**.</span></span>
2. <span data-ttu-id="57cee-109">No campo **Regra**, selecione o registro desejado no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="57cee-109">In the **Rule** field, select the desired record in the drop-down menu.</span></span>
3. <span data-ttu-id="57cee-110">No campo **A partir da data**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="57cee-110">In the **As of date** field, enter a date.</span></span>

    - <span data-ttu-id="57cee-111">O campo **A partir da data** é muito importante quando o razão é a fonte de dados para a regra.</span><span class="sxs-lookup"><span data-stu-id="57cee-111">The **As of Date** is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="57cee-112">Essa data controla quais saldos do razão serão incluídos na alocação.</span><span class="sxs-lookup"><span data-stu-id="57cee-112">This date controls which ledger balances to include for allocation.</span></span>  
    - <span data-ttu-id="57cee-113">No campo **Fonte zero**, selecione **Parar**.</span><span class="sxs-lookup"><span data-stu-id="57cee-113">In the **Zero source** field select **Stop**.</span></span> <span data-ttu-id="57cee-114">Isso interromperá o processo de alocação e exibirá uma mensagem informando que um valor de origem zero foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="57cee-114">This will stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  

4. <span data-ttu-id="57cee-115">No campo **Opções de proposta**, selecione **Somente proposta**.</span><span class="sxs-lookup"><span data-stu-id="57cee-115">In the **Proposal options** field, select **Proposal only**.</span></span> <span data-ttu-id="57cee-116">Selecione **Somente proposta** para revisar e opcionalmente aprovar o resultado em Diários de alocação antes de lançar a alocação na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="57cee-116">Select **Proposal only** to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
5. <span data-ttu-id="57cee-117">No campo Lançamento GL, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="57cee-117">In the GL posting date field, enter a date.</span></span>
6. <span data-ttu-id="57cee-118">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="57cee-118">Select **OK**.</span></span>
7. <span data-ttu-id="57cee-119">No painel de navegação, vá para **Módulos > Contabilidade > Alocações > Diários de alocação**.</span><span class="sxs-lookup"><span data-stu-id="57cee-119">In the navigation pane, go to **Modules > General ledger > Allocations > Allocation journals**.</span></span>
8. <span data-ttu-id="57cee-120">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="57cee-120">Select **Lines**.</span></span>
9. <span data-ttu-id="57cee-121">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="57cee-121">Select **Post**.</span></span>
10. <span data-ttu-id="57cee-122">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="57cee-122">Select **Post**.</span></span>
