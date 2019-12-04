---
title: Cheques pós-datados
description: Este artigo fornece informações sobre o suporte para cheques pré-datados no Microsoft Dynamics 365 Finance. Cheques pós-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura. Consequentemente, a verificação não pode ser descontada até a data especificada.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, CustPostDatedChecks
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 38ee6c5b3d258c313a2066b388a83330bf696d39
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176438"
---
# <a name="postdated-checks"></a><span data-ttu-id="008b7-105">Cheques pós-datados</span><span class="sxs-lookup"><span data-stu-id="008b7-105">Postdated checks</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="008b7-106">Este artigo fornece informações sobre o suporte para cheques pré-datados.</span><span class="sxs-lookup"><span data-stu-id="008b7-106">This article provides information about support for postdated checks.</span></span> <span data-ttu-id="008b7-107">Cheques pós-datados são cheques emitidos com a finalidade de fazer e receber pagamentos em uma data futura.</span><span class="sxs-lookup"><span data-stu-id="008b7-107">Postdated checks are checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="008b7-108">Consequentemente, a verificação não pode ser descontada até a data especificada.</span><span class="sxs-lookup"><span data-stu-id="008b7-108">Therefore, the check can't be cashed until the specified date.</span></span>

<span data-ttu-id="008b7-109">O Dynamics 365 Finance oferece suporte ao ciclo completo de gerenciamento de cheques pré-datados em Contas a Receber e em Contas a Pagar, como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="008b7-109">Dynamics 365 Finance supports the full management cycle for postdated checks in both Accounts receivable and Accounts payable, as shown in the following table.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="008b7-110">Cenário</span><span class="sxs-lookup"><span data-stu-id="008b7-110">Scenario</span></span></th>
<th><span data-ttu-id="008b7-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="008b7-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="008b7-112">Configurar cheques pós-datados</span><span class="sxs-lookup"><span data-stu-id="008b7-112">Set up postdated checks</span></span></td>
<td><span data-ttu-id="008b7-113">Você deve configurar um novo método de pagamento, e especificar a rotina de pagamento para limpar contas de cheques emitidos, cheques recebidos e o imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="008b7-113">You must set up a new payment method, and specify the payment routine for clearing accounts for issued checks, received checks, and withholding tax.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="008b7-114">Registrar e lançar um cheque pós-datado de um fornecedor</span><span class="sxs-lookup"><span data-stu-id="008b7-114">Register and post a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="008b7-115">Registrar os detalhes de um cheque pós-datado da saída para um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="008b7-115">Register the details of a postdated check that you issue to a vendor.</span></span> <span data-ttu-id="008b7-116">Quando o pagamento é lançado, a responsabilidade do fornecedor é reconhecida, mas a conta bancária ainda não é crédito.</span><span class="sxs-lookup"><span data-stu-id="008b7-116">When the payment is posted, the vendor liability is recognized, but the bank account isn’t yet credit.</span></span> <span data-ttu-id="008b7-117">Em vez disso, uma conta de compensação é usada com essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="008b7-117">Instead, a clearing account is used for this purpose.</span></span> </td>
</tr>
<tr class="odd">
<td><span data-ttu-id="008b7-118">Registrar e lançar um cheque pós-datado para um cliente</span><span class="sxs-lookup"><span data-stu-id="008b7-118">Register and post a postdated check for a customer</span></span></td>
<td><span data-ttu-id="008b7-119">Registre os detalhes de um cheque pós-datado recebido de um cliente.</span><span class="sxs-lookup"><span data-stu-id="008b7-119">Register the details of a postdated check that you receive from a customer.</span></span> <span data-ttu-id="008b7-120">Quando o pagamento é lançado, o recebível do cliente é crédito, mas a conta bancária ainda não é débito.</span><span class="sxs-lookup"><span data-stu-id="008b7-120">When the payment is posted, the customer receivable is credit, but the bank account isn’t yet debit.</span></span> <span data-ttu-id="008b7-121">Em vez disso, uma conta de compensação é usada com essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="008b7-121">Instead, a clearing account is used for this purpose.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="008b7-122">Registrar e lançar um cheque pós-datado de substituição de um cliente ou um fornecedor</span><span class="sxs-lookup"><span data-stu-id="008b7-122">Register and post a replacement postdated check for a customer or a vendor</span></span></td>
<td>
<span data-ttu-id="008b7-123">Se o cheque original para um fornecedor ou um cliente for perdido ou danificado, você poderá emitir um cheque pós-datado de substituição.</span><span class="sxs-lookup"><span data-stu-id="008b7-123">If your original check to a vendor or from a customer is lost or damaged, you can issue a replacement postdated check.</span></span> <span data-ttu-id="008b7-124">Quando você registra os detalhes do cheque, fornece uma referência ao cheque original e indica se o novo cheque é uma substituição do original.</span><span class="sxs-lookup"><span data-stu-id="008b7-124">When you register the check details, provide a reference to the original check, and indicate that the new check is a replacement for the original.</span></span> <span data-ttu-id="008b7-125">Também é possível lançar o cheque de substituição.</span><span class="sxs-lookup"><span data-stu-id="008b7-125">You can also post the replacement check.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="008b7-126">Transferir um cheque pós-datado de um cliente a um fornecedor</span><span class="sxs-lookup"><span data-stu-id="008b7-126">Transfer a customer postdated check to a vendor</span></span></td>
<td><span data-ttu-id="008b7-127">Ao receber um cheque pós-datado de um cliente, você pode transferir esse cheque para um fornecedor como um pagamento.</span><span class="sxs-lookup"><span data-stu-id="008b7-127">When you receive a postdated check from a customer, you can transfer that check to a vendor as a payment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="008b7-128">Liquidar um cheque pós-datado de um cliente ou fornecedor</span><span class="sxs-lookup"><span data-stu-id="008b7-128">Settle a postdated check for a customer or a vendor</span></span></td>
<td><span data-ttu-id="008b7-129">Defina um cheque pós-datado lançado em uma conta de transição para um cliente ou fornecedor quando o cheque finalmente cair.</span><span class="sxs-lookup"><span data-stu-id="008b7-129">Settle a postdated check that is posted to a bridging account for a customer or a vendor when the check finally matures.</span></span> <span data-ttu-id="008b7-130">Quando o cheque é liquidado, o banco será finalmente débito ou crédito na conta de compensação anteriormente usada</span><span class="sxs-lookup"><span data-stu-id="008b7-130">When the check is settled, the bank is finally debit or credit against the clearing account that was used earlier.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="008b7-131">Cancelar um cheque pós-datado de um fornecedor</span><span class="sxs-lookup"><span data-stu-id="008b7-131">Cancel a postdated check for a vendor</span></span></td>
<td><span data-ttu-id="008b7-132">Você pode cancelar um cheque pós-datado lançado nestas situações: - O cheque é devolvido pelo banco.</span><span class="sxs-lookup"><span data-stu-id="008b7-132">You can cancel a posted postdated check in these situations: - The check is returned by the bank.</span></span>
<span data-ttu-id="008b7-133">- O cheque é aplicado a uma fatura incorreta.</span><span class="sxs-lookup"><span data-stu-id="008b7-133">- The check is applied to an incorrect invoice.</span></span>
<span data-ttu-id="008b7-134">- Um pagamento à vista é feito em vez do cheque.</span><span class="sxs-lookup"><span data-stu-id="008b7-134">- A cash payment is made against the check.</span></span>
  </td>
  </tr>
  <tr class="even">
  <td><span data-ttu-id="008b7-135">Parar pagamento de um cheque pós-datado</span><span class="sxs-lookup"><span data-stu-id="008b7-135">Stop payment for a postdated check</span></span></td>
  <td><span data-ttu-id="008b7-136">Você pode suspender o pagamento de um cheque pós-datado emitido para um fornecedor, por razões como fundos insuficientes, alterações nas condições do contrato com o fornecedor, fornecimento de mercadorias defeituosos pelo fornecedor ou devolução de mercadorias ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="008b7-136">You can stop payment on a postdated check that was issued to a vendor, for reasons such as not sufficient funds, changes in the terms of the agreement with the vendor, supply of defective goods by the vendor, or return of goods to the vendor.</span></span> <span data-ttu-id="008b7-137">Você pode suspender o pagamento somente de cheques não desmarcados.</span><span class="sxs-lookup"><span data-stu-id="008b7-137">You can stop payment only on checks that haven’t cleared.</span></span></td>
  </tr>
  </tbody>
  </table>



<span data-ttu-id="008b7-138">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="008b7-138">For more information, see the following topics:</span></span>

[<span data-ttu-id="008b7-139">Configurar cheques pré-datados</span><span class="sxs-lookup"><span data-stu-id="008b7-139">Set up postdated checks</span></span>](tasks/set-up-postdated-checks.md)

[<span data-ttu-id="008b7-140">Registrar e lançar um cheque pré-datado para um cliente</span><span class="sxs-lookup"><span data-stu-id="008b7-140">Register and post a postdated check for a customer</span></span>](tasks/register-post-postdated-check-customer.md)

[<span data-ttu-id="008b7-141">Liquidar um cheque pré-datado de um cliente</span><span class="sxs-lookup"><span data-stu-id="008b7-141">Settle a postdated check from a customer</span></span>](tasks/settle-postdated-check-customer.md)

[<span data-ttu-id="008b7-142">Registrar e lançar um cheque pré-datado para um fornecedor</span><span class="sxs-lookup"><span data-stu-id="008b7-142">Register and post a postdated check for a vendor</span></span>](tasks/register-post-postdated-check-vendor.md) 

[<span data-ttu-id="008b7-143">Liquidar um cheque pré-datado de um fornecedor</span><span class="sxs-lookup"><span data-stu-id="008b7-143">Settle a postdated check for a vendor</span></span>](tasks/settle-postdated-check-vendor.md)


