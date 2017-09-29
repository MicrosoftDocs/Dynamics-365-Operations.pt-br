---
title: "Resolver discrepâncias durante a conciliação de totais de faturas"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3f7e1261838866688c97529b0edfa1354034247b
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a><span data-ttu-id="79411-102">Resolver discrepâncias durante a conciliação de totais de faturas</span><span class="sxs-lookup"><span data-stu-id="79411-102">Resolve discrepancies during invoice totals matching</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="79411-103">Um tipo de validação de conciliação de faturas é a conciliação de totais de faturas.</span><span class="sxs-lookup"><span data-stu-id="79411-103">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="79411-104">Para especificar que o sistema deve executar a conciliação de totais de faturas, na página **Parâmetros de contas a pagar**, na guia **Validação de fatura**, defina a opção **Conciliar totais de fatura** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="79411-104">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="79411-105">Você pode usar a conciliação de totais de fatura para ajudar a garantir que os valores totais de fatura não desviem dos valores esperados por mais de uma variação aceitável.</span><span class="sxs-lookup"><span data-stu-id="79411-105">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="79411-106">Seis totais são comparados na página **Detalhes de conciliação de totais de fatura**.</span><span class="sxs-lookup"><span data-stu-id="79411-106">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="79411-107">Se um dos totais se desviar do total de ordem de compra correspondente esperado, uma discrepância de conciliação será sinalizada.</span><span class="sxs-lookup"><span data-stu-id="79411-107">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="79411-108">Para revisar a fatura que contém os totais de discrepâncias correspondentes, no espaço de trabalho **Entrada de fatura de fornecedor**, clique no bloco **Faturas pendentes**.</span><span class="sxs-lookup"><span data-stu-id="79411-108">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="79411-109">Depois, no Painel de Ação, na guia **Revisão**, clique em **Detalhes da conciliação**.</span><span class="sxs-lookup"><span data-stu-id="79411-109">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="79411-110">Se as discrepâncias de conciliação foram detectadas, os ícones de aviso aparecerão ao lado do valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="79411-110">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="79411-111">Você pode ver mais detalhes sobre os totais exibindo os detalhes da conciliação de totais da fatura.</span><span class="sxs-lookup"><span data-stu-id="79411-111">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="79411-112">Após identificar uma discrepância, talvez você precise contatar o fornecedor se achar que as informações na fatura estão incorretas.</span><span class="sxs-lookup"><span data-stu-id="79411-112">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="79411-113">Dependendo do contrato resultante com o fornecedor, execute uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="79411-113">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="79411-114">Aceitar a diferença de preço e lançar a fatura com discrepâncias de conciliação.</span><span class="sxs-lookup"><span data-stu-id="79411-114">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="79411-115">O sistema pode ser configurado para exigir aprovação antes de lançar se há discrepâncias de conciliação.</span><span class="sxs-lookup"><span data-stu-id="79411-115">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="79411-116">Nesse caso, você deve aprovar a discrepância da conciliação e pode inserir um comentário de aprovação.</span><span class="sxs-lookup"><span data-stu-id="79411-116">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="79411-117">Você pode optar por lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="79411-117">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="79411-118">Revisar o valor da fatura para o valor esperado e lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="79411-118">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="79411-119">Solicitar um crédito completo de uma nova fatura corrigida do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="79411-119">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="79411-120">Para saber mais, consulte [Pesquisar ou resolver exceções](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="79411-120">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>



