---
title: Visão geral sobre resolver discrepâncias durante a conciliação de totais de fatura
description: Você pode usar a conciliação de totais de fatura para ajudar a garantir que os valores totais de fatura não desviem dos valores esperados por mais de uma variação aceitável.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0cf5a48a0f6beafad3c9a657c44079b290a7ebd5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440302"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching-overview"></a><span data-ttu-id="c7172-103">Visão geral sobre resolver discrepâncias durante a conciliação de totais de fatura</span><span class="sxs-lookup"><span data-stu-id="c7172-103">Resolve discrepancies during invoice totals matching overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7172-104">Um tipo de validação de conciliação de faturas é a conciliação de totais de faturas.</span><span class="sxs-lookup"><span data-stu-id="c7172-104">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="c7172-105">Para especificar que o sistema deve executar a conciliação de totais de faturas, na página **Parâmetros de contas a pagar**, na guia **Validação de fatura**, defina a opção **Conciliar totais de fatura** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c7172-105">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="c7172-106">Você pode usar a conciliação de totais de fatura para ajudar a garantir que os valores totais de fatura não desviem dos valores esperados por mais de uma variação aceitável.</span><span class="sxs-lookup"><span data-stu-id="c7172-106">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="c7172-107">Seis totais são comparados na página **Detalhes de conciliação de totais de fatura**.</span><span class="sxs-lookup"><span data-stu-id="c7172-107">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="c7172-108">Se um dos totais se desviar do total de ordem de compra correspondente esperado, uma discrepância de conciliação será sinalizada.</span><span class="sxs-lookup"><span data-stu-id="c7172-108">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="c7172-109">Para revisar a fatura que contém os totais de discrepâncias correspondentes, no espaço de trabalho **Entrada de fatura de fornecedor**, clique no bloco **Faturas pendentes**.</span><span class="sxs-lookup"><span data-stu-id="c7172-109">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="c7172-110">Depois, no Painel de Ação, na guia **Revisão**, clique em **Detalhes da conciliação**.</span><span class="sxs-lookup"><span data-stu-id="c7172-110">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="c7172-111">Se as discrepâncias de conciliação foram detectadas, os ícones de aviso aparecerão ao lado do valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="c7172-111">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="c7172-112">Você pode ver mais detalhes sobre os totais exibindo os detalhes da conciliação de totais da fatura.</span><span class="sxs-lookup"><span data-stu-id="c7172-112">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="c7172-113">Após identificar uma discrepância, talvez você precise contatar o fornecedor se achar que as informações na fatura estão incorretas.</span><span class="sxs-lookup"><span data-stu-id="c7172-113">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="c7172-114">Dependendo do contrato resultante com o fornecedor, execute uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="c7172-114">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="c7172-115">Aceitar a diferença de preço e lançar a fatura com discrepâncias de conciliação.</span><span class="sxs-lookup"><span data-stu-id="c7172-115">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="c7172-116">O sistema pode ser configurado para exigir aprovação antes de lançar se há discrepâncias de conciliação.</span><span class="sxs-lookup"><span data-stu-id="c7172-116">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="c7172-117">Nesse caso, você deve aprovar a discrepância da conciliação e pode inserir um comentário de aprovação.</span><span class="sxs-lookup"><span data-stu-id="c7172-117">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="c7172-118">Você pode optar por lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="c7172-118">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="c7172-119">Revisar o valor da fatura para o valor esperado e lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="c7172-119">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="c7172-120">Solicitar um crédito completo de uma nova fatura corrigida do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="c7172-120">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="c7172-121">Para saber mais, consulte [Pesquisar/Resolver exceções](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="c7172-121">For more information, see [Research/Resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>


