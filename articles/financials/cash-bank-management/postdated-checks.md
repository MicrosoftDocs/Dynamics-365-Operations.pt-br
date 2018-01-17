---
title: "Cheques pós-datados"
description: "Este artigo fornece informações sobre o suporte para cheques pós-datados no Microsoft Dynamics 365 for Finance and Operations, edição Enterprise. Cheques pós-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura. Consequentemente, a verificação não pode ser descontada até a data especificada."
author: twheeloc
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 4462b9b9df9a14deba05c43d3f87321d263f42f6
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="postdated-checks"></a><span data-ttu-id="5b987-105">Cheques pós-datados</span><span class="sxs-lookup"><span data-stu-id="5b987-105">Postdated checks</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5b987-106">Este artigo fornece informações sobre o suporte para cheques pós-datados no Microsoft Dynamics 365 for Finance and Operations, edição Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5b987-106">This article provides information about support for postdated checks in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="5b987-107">Cheques pós-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura.</span><span class="sxs-lookup"><span data-stu-id="5b987-107">Postdated checks are checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="5b987-108">Consequentemente, a verificação não pode ser descontada até a data especificada.</span><span class="sxs-lookup"><span data-stu-id="5b987-108">Therefore, the check can't be cashed until the specified date.</span></span>

<span data-ttu-id="5b987-109">O Microsoft Dynamics 365 for Finance and Operations oferece suporte ao ciclo completo de gerenciamento de cheques pós-datados em contas a receber e em contas a pagar, como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5b987-109">Microsoft Dynamics 365 for Finance and Operations supports the full management cycle for postdated checks in both Accounts receivable and Accounts payable, as shown in the following table.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b987-110">Cenário</span><span class="sxs-lookup"><span data-stu-id="5b987-110">Scenario</span></span></th>
<th><span data-ttu-id="5b987-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5b987-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5b987-112">Configurar cheques pós-datados</span><span class="sxs-lookup"><span data-stu-id="5b987-112">Set up postdated checks</span></span></td>
<td><span data-ttu-id="5b987-113">Você deve configurar um novo método de pagamento, e especificar a rotina de pagamento para limpar contas de cheques emitidos, cheques recebidos e o imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="5b987-113">You must set up a new payment method, and specify the payment routine for clearing accounts for issued checks, received checks, and withholding tax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5b987-114">Registrar e lançar um cheque pós-datado de um fornecedor</span><span class="sxs-lookup"><span data-stu-id="5b987-114">Register and post a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="5b987-115">Registrar os detalhes de um cheque pós-datado da saída para um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5b987-115">Register the details of a postdated check that you issue to a vendor.</span></span> <span data-ttu-id="5b987-116">Quando o pagamento é lançado, a responsabilidade do fornecedor é reconhecida, mas a conta bancária ainda não é crédito.</span><span class="sxs-lookup"><span data-stu-id="5b987-116">When the payment is posted, the vendor liability is recognized, but the bank account isn’t yet credit.</span></span> <span data-ttu-id="5b987-117">Em vez disso, uma conta de compensação é usada com essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="5b987-117">Instead, a clearing account is used for this purpose.</span></span> </td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5b987-118">Registrar e lançar um cheque pós-datado para um cliente</span><span class="sxs-lookup"><span data-stu-id="5b987-118">Register and post a postdated check for a customer</span></span></td>
<td><span data-ttu-id="5b987-119">Registre os detalhes de um cheque pós-datado recebido de um cliente.</span><span class="sxs-lookup"><span data-stu-id="5b987-119">Register the details of a postdated check that you receive from a customer.</span></span> <span data-ttu-id="5b987-120">Quando o pagamento é lançado, o recebível do cliente é crédito, mas a conta bancária ainda não é débito.</span><span class="sxs-lookup"><span data-stu-id="5b987-120">When the payment is posted, the customer receivable is credit, but the bank account isn’t yet debit.</span></span> <span data-ttu-id="5b987-121">Em vez disso, uma conta de compensação é usada com essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="5b987-121">Instead, a clearing account is used for this purpose.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5b987-122">Registrar e lançar um cheque pós-datado de substituição de um cliente ou um fornecedor</span><span class="sxs-lookup"><span data-stu-id="5b987-122">Register and post a replacement postdated check for a customer or a vendor</span></span></td>
<td>
<span data-ttu-id="5b987-123">Se o cheque original para um fornecedor ou um cliente for perdido ou danificado, você poderá emitir um cheque pós-datado de substituição.</span><span class="sxs-lookup"><span data-stu-id="5b987-123">If your original check to a vendor or from a customer is lost or damaged, you can issue a replacement postdated check.</span></span> <span data-ttu-id="5b987-124">Quando você registra os detalhes do cheque, fornece uma referência ao cheque original e indica se o novo cheque é uma substituição do original.</span><span class="sxs-lookup"><span data-stu-id="5b987-124">When you register the check details, provide a reference to the original check, and indicate that the new check is a replacement for the original.</span></span> <span data-ttu-id="5b987-125">Também é possível lançar o cheque de substituição.</span><span class="sxs-lookup"><span data-stu-id="5b987-125">You can also post the replacement check.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5b987-126">Transferir um cheque pós-datado de um cliente a um fornecedor</span><span class="sxs-lookup"><span data-stu-id="5b987-126">Transfer a customer postdated check to a vendor</span></span></td>
<td><span data-ttu-id="5b987-127">Ao receber um cheque pós-datado de um cliente, você pode transferir esse cheque para um fornecedor como um pagamento.</span><span class="sxs-lookup"><span data-stu-id="5b987-127">When you receive a postdated check from a customer, you can transfer that check to a vendor as a payment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5b987-128">Liquidar um cheque pós-datado de um cliente ou fornecedor</span><span class="sxs-lookup"><span data-stu-id="5b987-128">Settle a postdated check for a customer or a vendor</span></span></td>
<td><span data-ttu-id="5b987-129">Defina um cheque pós-datado lançado em uma conta de transição para um cliente ou fornecedor quando o cheque finalmente cair.</span><span class="sxs-lookup"><span data-stu-id="5b987-129">Settle a postdated check that is posted to a bridging account for a customer or a vendor when the check finally matures.</span></span> <span data-ttu-id="5b987-130">Quando o cheque é liquidado, o banco será finalmente débito ou crédito na conta de compensação anteriormente usada</span><span class="sxs-lookup"><span data-stu-id="5b987-130">When the check is settled, the bank is finally debit or credit against the clearing account that was used earlier.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5b987-131">Cancelar um cheque pós-datado de um fornecedor</span><span class="sxs-lookup"><span data-stu-id="5b987-131">Cancel a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="5b987-132">Você pode cancelar um cheque pós-datado lançado nestas situações: - O cheque é devolvido pelo banco.</span><span class="sxs-lookup"><span data-stu-id="5b987-132">You can cancel a posted postdated check in these situations: - The check is returned by the bank.</span></span>
<span data-ttu-id="5b987-133">- O cheque é aplicado a uma fatura incorreta.</span><span class="sxs-lookup"><span data-stu-id="5b987-133">- The check is applied to an incorrect invoice.</span></span>
<span data-ttu-id="5b987-134">- Um pagamento à vista é feito no cheque.</span><span class="sxs-lookup"><span data-stu-id="5b987-134">- A cash payment is made against the check.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="5b987-135">Parar pagamento de um cheque pós-datado</span><span class="sxs-lookup"><span data-stu-id="5b987-135">Stop payment for a postdated check</span></span></td>
<td><span data-ttu-id="5b987-136">Você pode suspender o pagamento de um cheque pós-datado emitido para um fornecedor, por razões como fundos insuficientes, alterações nas condições do contrato com o fornecedor, fornecimento de mercadorias defeituosos pelo fornecedor ou devolução de mercadorias ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5b987-136">You can stop payment on a postdated check that was issued to a vendor, for reasons such as not sufficient funds, changes in the terms of the agreement with the vendor, supply of defective goods by the vendor, or return of goods to the vendor.</span></span> <span data-ttu-id="5b987-137">Você pode suspender o pagamento somente de cheques não desmarcados.</span><span class="sxs-lookup"><span data-stu-id="5b987-137">You can stop payment only on checks that haven’t cleared.</span></span></td>
</tr>
</tbody>
</table>



<span data-ttu-id="5b987-138">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5b987-138">For more information, see the following topics:</span></span>

[<span data-ttu-id="5b987-139">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="5b987-139">Set up postdated checks</span></span>](tasks/set-up-postdated-checks.md)

[<span data-ttu-id="5b987-140">Registrar e lançar um cheque pré-datado para um cliente</span><span class="sxs-lookup"><span data-stu-id="5b987-140">Register and post a postdated check for a customer</span></span>](tasks/register-post-postdated-check-customer.md)

[<span data-ttu-id="5b987-141">Liquidar um cheque pré-datado de um cliente</span><span class="sxs-lookup"><span data-stu-id="5b987-141">Settle a postdated check from a customer</span></span>](tasks/settle-postdated-check-customer.md)

[<span data-ttu-id="5b987-142">Registrar e lançar um cheque pré-datado para um fornecedor</span><span class="sxs-lookup"><span data-stu-id="5b987-142">Register and post a postdated check for a vendor</span></span>](tasks/register-post-postdated-check-vendor.md) 

[<span data-ttu-id="5b987-143">Liquidar um cheque pré-datado de um fornecedor</span><span class="sxs-lookup"><span data-stu-id="5b987-143">Settle a postdated check for a vendor</span></span>](tasks/settle-postdated-check-vendor.md)




