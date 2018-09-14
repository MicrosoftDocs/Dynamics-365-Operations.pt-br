--- 
title: Registrar fatura de fornecedor e corresponder com a quantidade recebida
description: "Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 5d7458c62b3b71adf981a1ce5a7260da9bfdbcd2
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a><span data-ttu-id="663e8-103">Registrar fatura de fornecedor e corresponder com a quantidade recebida</span><span class="sxs-lookup"><span data-stu-id="663e8-103">Record vendor invoice and match against received quantity</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="663e8-104">Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento.</span><span class="sxs-lookup"><span data-stu-id="663e8-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="663e8-105">Antes de começar, verifique se a configuração conciliação de faturas está marcada.</span><span class="sxs-lookup"><span data-stu-id="663e8-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="663e8-106">Na página de parâmetros de contas a pagar, verifique se a opção de validação de conciliação de nota fiscal está selecionada, o campo Lançar nota fiscal com discrepâncias é configurado para exigir aprovação, e o campo da diretiva de conciliação de linha está definido à conciliação tripla.</span><span class="sxs-lookup"><span data-stu-id="663e8-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="663e8-107">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="663e8-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="663e8-108">A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas.</span><span class="sxs-lookup"><span data-stu-id="663e8-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="663e8-109">Crie uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="663e8-109">Create a purchase order</span></span>
1. <span data-ttu-id="663e8-110">Ir para Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="663e8-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="663e8-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="663e8-111">Click New.</span></span>
3. <span data-ttu-id="663e8-112">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="663e8-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="663e8-113">No campo Conta de fornecedor, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="663e8-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="663e8-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="663e8-114">Click OK.</span></span>
6. <span data-ttu-id="663e8-115">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="663e8-115">Click Add line.</span></span>
7. <span data-ttu-id="663e8-116">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="663e8-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="663e8-117">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="663e8-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="663e8-118">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="663e8-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="663e8-119">Lançar um recebimento de produto</span><span class="sxs-lookup"><span data-stu-id="663e8-119">Post a product receipt</span></span>
1. <span data-ttu-id="663e8-120">No Painel de Ação, clique em Receber.</span><span class="sxs-lookup"><span data-stu-id="663e8-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="663e8-121">Clique em Recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="663e8-121">Click Product receipt.</span></span>
3. <span data-ttu-id="663e8-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="663e8-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="663e8-123">No campo Recebimento de produtos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="663e8-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="663e8-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="663e8-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="663e8-125">Registre e a concilie uma fatura de fornecedor com um recebimento de produto</span><span class="sxs-lookup"><span data-stu-id="663e8-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="663e8-126">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="663e8-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="663e8-127">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="663e8-127">Click Invoice.</span></span>
3. <span data-ttu-id="663e8-128">No campo Número, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="663e8-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="663e8-129">Clique no padrão de: Quantidade encomendada para abrir a caixa de diálogo de descarte.</span><span class="sxs-lookup"><span data-stu-id="663e8-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="663e8-130">No campo Quantidade padrão para linhas, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="663e8-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="663e8-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="663e8-131">Click OK.</span></span>
7. <span data-ttu-id="663e8-132">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="663e8-132">Click Yes.</span></span>
8. <span data-ttu-id="663e8-133">Clique em Conciliar recebimentos de produtos.</span><span class="sxs-lookup"><span data-stu-id="663e8-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="663e8-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="663e8-134">Click OK.</span></span>
10. <span data-ttu-id="663e8-135">No Painel de Ação, clique em Revisar.</span><span class="sxs-lookup"><span data-stu-id="663e8-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="663e8-136">Clique em Detalhes da conciliação.</span><span class="sxs-lookup"><span data-stu-id="663e8-136">Click Matching details.</span></span>


