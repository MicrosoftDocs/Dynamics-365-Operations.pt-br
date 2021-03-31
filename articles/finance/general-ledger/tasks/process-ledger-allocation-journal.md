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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a52a5ce2d789757a11c9e443c7f25058bd9d8a91
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222326"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="b741e-103">Processar diário de alocação do razão</span><span class="sxs-lookup"><span data-stu-id="b741e-103">Process ledger allocation journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b741e-104">Este tópico explica como processar uma solicitação de alocação.</span><span class="sxs-lookup"><span data-stu-id="b741e-104">This topic explains how to process an allocation request.</span></span> <span data-ttu-id="b741e-105">Use a página Processar solicitação de alocação para criar um diário de alocação que possa ser revisto e aprovado antes do lançamento na Contabilidade ou que possa ser lançado diretamente na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="b741e-105">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="b741e-106">Antes de criar um diário de alocações, deve haver pelo menos uma regra de alocação do razão ativa.</span><span class="sxs-lookup"><span data-stu-id="b741e-106">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="b741e-107">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="b741e-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="b741e-108">No painel de navegação, vá para **Módulos > Contabilidade > Alocações > Processar solicitação de alocação**.</span><span class="sxs-lookup"><span data-stu-id="b741e-108">In the navigation pane, go to **Modules > General ledger > Allocations > Process allocation request**.</span></span>
2. <span data-ttu-id="b741e-109">No campo **Regra**, selecione o registro desejado no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="b741e-109">In the **Rule** field, select the desired record in the drop-down menu.</span></span>
3. <span data-ttu-id="b741e-110">No campo **A partir da data**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b741e-110">In the **As of date** field, enter a date.</span></span>

    - <span data-ttu-id="b741e-111">O campo **A partir da data** é muito importante quando o razão é a fonte de dados para a regra.</span><span class="sxs-lookup"><span data-stu-id="b741e-111">The **As of Date** is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="b741e-112">Essa data controla quais saldos do razão serão incluídos na alocação.</span><span class="sxs-lookup"><span data-stu-id="b741e-112">This date controls which ledger balances to include for allocation.</span></span>  
    - <span data-ttu-id="b741e-113">No campo **Fonte zero**, selecione **Parar**.</span><span class="sxs-lookup"><span data-stu-id="b741e-113">In the **Zero source** field select **Stop**.</span></span> <span data-ttu-id="b741e-114">Isso interromperá o processo de alocação e exibirá uma mensagem informando que um valor de origem zero foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="b741e-114">This will stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  

4. <span data-ttu-id="b741e-115">No campo **Opções de proposta**, selecione **Somente proposta**.</span><span class="sxs-lookup"><span data-stu-id="b741e-115">In the **Proposal options** field, select **Proposal only**.</span></span> <span data-ttu-id="b741e-116">Selecione **Somente proposta** para revisar e opcionalmente aprovar o resultado em Diários de alocação antes de lançar a alocação na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="b741e-116">Select **Proposal only** to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
5. <span data-ttu-id="b741e-117">No campo Lançamento GL, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b741e-117">In the GL posting date field, enter a date.</span></span>
6. <span data-ttu-id="b741e-118">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b741e-118">Select **OK**.</span></span>
7. <span data-ttu-id="b741e-119">No painel de navegação, vá para **Módulos > Contabilidade > Alocações > Diários de alocação**.</span><span class="sxs-lookup"><span data-stu-id="b741e-119">In the navigation pane, go to **Modules > General ledger > Allocations > Allocation journals**.</span></span>
8. <span data-ttu-id="b741e-120">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="b741e-120">Select **Lines**.</span></span>
9. <span data-ttu-id="b741e-121">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="b741e-121">Select **Post**.</span></span>
10. <span data-ttu-id="b741e-122">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="b741e-122">Select **Post**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]