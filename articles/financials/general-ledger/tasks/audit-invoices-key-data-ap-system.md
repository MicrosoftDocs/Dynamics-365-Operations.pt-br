--- 
title: Auditar faturas e dados-chave em contas a pagar
description: "Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento."
author: saraschi2
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: eb46f33ff07a6b95b4fc5a48c42da4c04c7dab70
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a><span data-ttu-id="5f136-103">Auditar faturas e dados-chave em contas a pagar</span><span class="sxs-lookup"><span data-stu-id="5f136-103">Audit invoices and key data in accounts payable</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5f136-104">Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento.</span><span class="sxs-lookup"><span data-stu-id="5f136-104">When you receive an invoice from a vendor for goods or services on a purchase order, the business processes might require that the goods or services be received before the invoice can be approved for payment.</span></span> <span data-ttu-id="5f136-105">Antes de começar, verifique se a configuração conciliação de faturas está marcada.</span><span class="sxs-lookup"><span data-stu-id="5f136-105">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span> 

<span data-ttu-id="5f136-106">Na página de parâmetros de contas a pagar, verifique se a opção de validação de conciliação de nota fiscal está selecionada, o campo Lançar nota fiscal com discrepâncias é configurado para exigir aprovação, e o campo da diretiva de conciliação de linha está definido à conciliação tripla.</span><span class="sxs-lookup"><span data-stu-id="5f136-106">In the Accounts payable parameters page, ensure that the Enable invoice matching validation option is selected, the Post invoice with discrepancies field is set to Require approval, and the Line matching policy field is set to Three-way matching.</span></span>

<span data-ttu-id="5f136-107">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="5f136-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="5f136-108">A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas.</span><span class="sxs-lookup"><span data-stu-id="5f136-108">The accounts payable manager or accounting manager role would perform these steps.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="5f136-109">Crie uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="5f136-109">Create a purchase order</span></span>
1. <span data-ttu-id="5f136-110">Ir para Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="5f136-110">Go to All purchase orders.</span></span>
2. <span data-ttu-id="5f136-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5f136-111">Click New.</span></span>
3. <span data-ttu-id="5f136-112">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5f136-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="5f136-113">No campo Conta de fornecedor, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="5f136-113">In the Vendor account field, type a value.</span></span>
5. <span data-ttu-id="5f136-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5f136-114">Click OK.</span></span>
6. <span data-ttu-id="5f136-115">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="5f136-115">Click Add line.</span></span>
7. <span data-ttu-id="5f136-116">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5f136-116">In the Item number field, type a value.</span></span>
8. <span data-ttu-id="5f136-117">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="5f136-117">On the Action Pane, click Purchase.</span></span>
9. <span data-ttu-id="5f136-118">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="5f136-118">Click Confirm.</span></span>

## <a name="post-a-product-receipt"></a><span data-ttu-id="5f136-119">Lançar um recebimento de produto</span><span class="sxs-lookup"><span data-stu-id="5f136-119">Post a product receipt</span></span>
1. <span data-ttu-id="5f136-120">No Painel de Ação, clique em Receber.</span><span class="sxs-lookup"><span data-stu-id="5f136-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="5f136-121">Clique em Recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="5f136-121">Click Product receipt.</span></span>
3. <span data-ttu-id="5f136-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5f136-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="5f136-123">No campo Recebimento de produtos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5f136-123">In the Product receipt field, type a value.</span></span>
5. <span data-ttu-id="5f136-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5f136-124">Click OK.</span></span>

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a><span data-ttu-id="5f136-125">Registre e a concilie uma fatura de fornecedor com um recebimento de produto</span><span class="sxs-lookup"><span data-stu-id="5f136-125">Record and match a vendor invoice to a product receipt</span></span>
1. <span data-ttu-id="5f136-126">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="5f136-126">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="5f136-127">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="5f136-127">Click Invoice.</span></span>
3. <span data-ttu-id="5f136-128">No campo Número, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5f136-128">In the Number field, type a value.</span></span>
4. <span data-ttu-id="5f136-129">Clique no padrão de: Quantidade encomendada para abrir a caixa de diálogo de descarte.</span><span class="sxs-lookup"><span data-stu-id="5f136-129">Click Default from: Ordered quantity to open the drop dialog.</span></span>
5. <span data-ttu-id="5f136-130">No campo Quantidade padrão para linhas, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="5f136-130">In the Default quantity for lines field, select an option.</span></span>
6. <span data-ttu-id="5f136-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5f136-131">Click OK.</span></span>
7. <span data-ttu-id="5f136-132">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="5f136-132">Click Yes.</span></span>
8. <span data-ttu-id="5f136-133">Clique em Conciliar recebimentos de produtos.</span><span class="sxs-lookup"><span data-stu-id="5f136-133">Click Match product receipts.</span></span>
9. <span data-ttu-id="5f136-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5f136-134">Click OK.</span></span>
10. <span data-ttu-id="5f136-135">No Painel de Ação, clique em Revisar.</span><span class="sxs-lookup"><span data-stu-id="5f136-135">On the Action Pane, click Review.</span></span>
11. <span data-ttu-id="5f136-136">Clique em Detalhes da conciliação.</span><span class="sxs-lookup"><span data-stu-id="5f136-136">Click Matching details.</span></span>


