---
title: Resolver discrepâncias durante conciliação de totais de fatura
description: Você pode usar a conciliação de totais de fatura para ajudar a garantir que os valores totais de fatura não desviem dos valores esperados por mais de uma variação aceitável.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67aa0b89eed1f82290659029dfcce92ca3710aea
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "331497"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching"></a><span data-ttu-id="34815-103">Resolver discrepâncias durante conciliação de totais de fatura</span><span class="sxs-lookup"><span data-stu-id="34815-103">Resolve discrepancies during invoice totals matching</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34815-104">Um tipo de validação de conciliação de faturas é a conciliação de totais de faturas.</span><span class="sxs-lookup"><span data-stu-id="34815-104">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="34815-105">Para especificar que o sistema deve executar a conciliação de totais de faturas, na página **Parâmetros de contas a pagar**, na guia **Validação de fatura**, defina a opção **Conciliar totais de fatura** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="34815-105">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="34815-106">Você pode usar a conciliação de totais de fatura para ajudar a garantir que os valores totais de fatura não desviem dos valores esperados por mais de uma variação aceitável.</span><span class="sxs-lookup"><span data-stu-id="34815-106">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="34815-107">Seis totais são comparados na página **Detalhes de conciliação de totais de fatura**.</span><span class="sxs-lookup"><span data-stu-id="34815-107">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="34815-108">Se um dos totais se desviar do total de ordem de compra correspondente esperado, uma discrepância de conciliação será sinalizada.</span><span class="sxs-lookup"><span data-stu-id="34815-108">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="34815-109">Para revisar a fatura que contém os totais de discrepâncias correspondentes, no espaço de trabalho **Entrada de fatura de fornecedor**, clique no bloco **Faturas pendentes**.</span><span class="sxs-lookup"><span data-stu-id="34815-109">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="34815-110">Depois, no Painel de Ação, na guia **Revisão**, clique em **Detalhes da conciliação**.</span><span class="sxs-lookup"><span data-stu-id="34815-110">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="34815-111">Se as discrepâncias de conciliação foram detectadas, os ícones de aviso aparecerão ao lado do valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="34815-111">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="34815-112">Você pode ver mais detalhes sobre os totais exibindo os detalhes da conciliação de totais da fatura.</span><span class="sxs-lookup"><span data-stu-id="34815-112">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="34815-113">Após identificar uma discrepância, talvez você precise contatar o fornecedor se achar que as informações na fatura estão incorretas.</span><span class="sxs-lookup"><span data-stu-id="34815-113">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="34815-114">Dependendo do contrato resultante com o fornecedor, execute uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="34815-114">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="34815-115">Aceitar a diferença de preço e lançar a fatura com discrepâncias de conciliação.</span><span class="sxs-lookup"><span data-stu-id="34815-115">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="34815-116">O sistema pode ser configurado para exigir aprovação antes de lançar se há discrepâncias de conciliação.</span><span class="sxs-lookup"><span data-stu-id="34815-116">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="34815-117">Nesse caso, você deve aprovar a discrepância da conciliação e pode inserir um comentário de aprovação.</span><span class="sxs-lookup"><span data-stu-id="34815-117">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="34815-118">Você pode optar por lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="34815-118">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="34815-119">Revisar o valor da fatura para o valor esperado e lançar a fatura.</span><span class="sxs-lookup"><span data-stu-id="34815-119">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="34815-120">Solicitar um crédito completo de uma nova fatura corrigida do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="34815-120">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="34815-121">Para saber mais, consulte [Pesquisar ou resolver exceções](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="34815-121">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>


