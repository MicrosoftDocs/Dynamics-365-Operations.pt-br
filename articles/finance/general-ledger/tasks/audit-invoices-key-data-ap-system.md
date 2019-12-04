---
title: Auditar faturas e dados-chave no sistema de AP
description: Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c6e8967fe4db67ff98fc7093792bdb82b73a33d9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176359"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a><span data-ttu-id="4d020-103">Auditar faturas e dados-chave no sistema de AP</span><span class="sxs-lookup"><span data-stu-id="4d020-103">Audit invoices and key data in AP system</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4d020-104">Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento.</span><span class="sxs-lookup"><span data-stu-id="4d020-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="4d020-105">Antes de começar, verifique se a configuração conciliação de faturas está marcada.</span><span class="sxs-lookup"><span data-stu-id="4d020-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="4d020-106">Na página de parâmetros de contas a pagar, verifique se a opção de validação de conciliação de nota fiscal está selecionada, o campo Lançar nota fiscal com discrepâncias é configurado para exigir aprovação, e o campo da diretiva de conciliação de linha está definido à conciliação tripla.</span><span class="sxs-lookup"><span data-stu-id="4d020-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="4d020-107">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="4d020-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="4d020-108">A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4d020-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="4d020-109">Crie uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="4d020-109">Create a purchase order</span></span>
1. <span data-ttu-id="4d020-110">Ir para **Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="4d020-110">Go to **All purchase orders**.</span></span>
2. <span data-ttu-id="4d020-111">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4d020-111">Click **New**.</span></span>
3. <span data-ttu-id="4d020-112">No campo **Conta de fornecedor**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="4d020-112">In the **Vendor account** field, type a value.</span></span>
4. <span data-ttu-id="4d020-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d020-113">Click **OK**.</span></span>
5. <span data-ttu-id="4d020-114">Clique em **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="4d020-114">Click **Add line**.</span></span>
6. <span data-ttu-id="4d020-115">No campo **Número de item**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4d020-115">In the **Item number** field, type a value.</span></span>
7. <span data-ttu-id="4d020-116">No Painel de Ação, clique em **Compra**.</span><span class="sxs-lookup"><span data-stu-id="4d020-116">On the Action Pane, click **Purchase**.</span></span>
8. <span data-ttu-id="4d020-117">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4d020-117">Click **Confirm**.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="4d020-118">Lançar um recebimento de produto</span><span class="sxs-lookup"><span data-stu-id="4d020-118">Post a product receipt</span></span>
1. <span data-ttu-id="4d020-119">No Painel de Ação, clique em **Receber**.</span><span class="sxs-lookup"><span data-stu-id="4d020-119">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="4d020-120">Clique em **Recebimento de produtos**.</span><span class="sxs-lookup"><span data-stu-id="4d020-120">Click **Product receipt**.</span></span>
3. <span data-ttu-id="4d020-121">No campo **Recebimento de produtos**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4d020-121">In the **Product receipt** field, type a value.</span></span>
4. <span data-ttu-id="4d020-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d020-122">Click **OK**.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="4d020-123">Registre e a concilie uma fatura de fornecedor com um recebimento de produto</span><span class="sxs-lookup"><span data-stu-id="4d020-123">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="4d020-124">No Painel de Ação, clique em **Fatura > Fatura**.</span><span class="sxs-lookup"><span data-stu-id="4d020-124">On the Action Pane, click **Invoice > Invoice**.</span></span>
2. <span data-ttu-id="4d020-125">No campo **Número**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4d020-125">In the **Number** field, type a value.</span></span>
3. <span data-ttu-id="4d020-126">Clique no **padrão de: Quantidade encomendada** para abrir a caixa de diálogo de descarte.</span><span class="sxs-lookup"><span data-stu-id="4d020-126">Click **Default from: Ordered quantity** to open the drop dialog.</span></span>
4. <span data-ttu-id="4d020-127">No campo **Quantidade padrão para linhas**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="4d020-127">In the **Default quantity for lines** field, select an option.</span></span>
5. <span data-ttu-id="4d020-128">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d020-128">Click **OK**.</span></span>
6. <span data-ttu-id="4d020-129">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="4d020-129">Click **Yes**.</span></span>
7. <span data-ttu-id="4d020-130">Clique em **Conciliar recebimentos de produtos**.</span><span class="sxs-lookup"><span data-stu-id="4d020-130">Click **Match product receipts**.</span></span>
8. <span data-ttu-id="4d020-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d020-131">Click **OK**.</span></span>
9. <span data-ttu-id="4d020-132">No Painel de Ação, clique em **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="4d020-132">On the Action Pane, click **Review**.</span></span>
10. <span data-ttu-id="4d020-133">Clique em **Detalhes da conciliação**.</span><span class="sxs-lookup"><span data-stu-id="4d020-133">Click **Matching details**.</span></span>
