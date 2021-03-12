---
title: Cálculo de imposto nas linhas do diário geral
description: Este tópico explica como os impostos são calculados para diferentes tipos de conta (fornecedor, cliente, razão e projeto) nas linhas do diário geral.
author: EricWang
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: e420632c248b5b43d4983c5eb483cac580e67f20
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975549"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="a9487-103">Cálculo de imposto nas linhas do diário geral</span><span class="sxs-lookup"><span data-stu-id="a9487-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9487-104">Este tópico explica como os impostos são calculados para diferentes tipos de conta (fornecedor, cliente, razão e projeto) nas linhas do diário geral.</span><span class="sxs-lookup"><span data-stu-id="a9487-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="a9487-105">O processo pode ser dividido em três etapas:</span><span class="sxs-lookup"><span data-stu-id="a9487-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="a9487-106">Determinar a direção do imposto.</span><span class="sxs-lookup"><span data-stu-id="a9487-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="a9487-107">Determinar o valor do imposto que será armazenado em uma tabela de impostos temporária.</span><span class="sxs-lookup"><span data-stu-id="a9487-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="a9487-108">Determinar o valor do imposto e a conta no comprovante.</span><span class="sxs-lookup"><span data-stu-id="a9487-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="a9487-109">Determinar a direção do imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-109">Determine the sales tax direction</span></span>

<span data-ttu-id="a9487-110">A maneira como a direção do imposto é determinada depende do tipo de conta no comprovante.</span><span class="sxs-lookup"><span data-stu-id="a9487-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="a9487-111">A direção do imposto é determinada pela combinação de tipo de conta e de código de imposto.</span><span class="sxs-lookup"><span data-stu-id="a9487-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="a9487-112">As seguintes seções listam as possibilidades mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="a9487-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="a9487-113">Tipo de conta é Projeto</span><span class="sxs-lookup"><span data-stu-id="a9487-113">Account type is Project</span></span>

<span data-ttu-id="a9487-114">Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Projeto**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto.</span><span class="sxs-lookup"><span data-stu-id="a9487-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="a9487-115">A ilustração a seguir mostra a regra.</span><span class="sxs-lookup"><span data-stu-id="a9487-115">The following illustration shows the rule.</span></span> <span data-ttu-id="a9487-116">Os seguintes pontos mostram as possíveis direções de imposto para contas do projeto.</span><span class="sxs-lookup"><span data-stu-id="a9487-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="a9487-117">•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.</span><span class="sxs-lookup"><span data-stu-id="a9487-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="a9487-118">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="a9487-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="a9487-119">•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="a9487-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9487-120">•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="a9487-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9487-121">Caso contrário, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="a9487-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="a9487-122">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="a9487-122">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas do projeto](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="a9487-124">Tipo de conta é Fornecedor</span><span class="sxs-lookup"><span data-stu-id="a9487-124">Account type is Vendor</span></span>

<span data-ttu-id="a9487-125">Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Fornecedor**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto.</span><span class="sxs-lookup"><span data-stu-id="a9487-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="a9487-126">Os seguintes pontos mostram as possíveis direções de imposto para contas de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a9487-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="a9487-127">•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.</span><span class="sxs-lookup"><span data-stu-id="a9487-127">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="a9487-128">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="a9487-128">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="a9487-129">•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="a9487-129">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9487-130">•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="a9487-130">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9487-131">Caso contrário, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="a9487-131">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="a9487-132">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="a9487-132">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas de fornecedor](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="a9487-134">Tipo de conta é Cliente</span><span class="sxs-lookup"><span data-stu-id="a9487-134">Account type is Customer</span></span>

<span data-ttu-id="a9487-135">Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Cliente**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto.</span><span class="sxs-lookup"><span data-stu-id="a9487-135">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="a9487-136">Os seguintes pontos mostram as possíveis direções de imposto para contas de cliente.</span><span class="sxs-lookup"><span data-stu-id="a9487-136">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="a9487-137">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="a9487-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="a9487-138">•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="a9487-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="a9487-139">•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="a9487-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="a9487-140">Caso contrário, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="a9487-140">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9487-141">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="a9487-141">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas de cliente](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="a9487-143">Tipo de conta é Razão</span><span class="sxs-lookup"><span data-stu-id="a9487-143">Account type is Ledger</span></span>

<span data-ttu-id="a9487-144">A ilustração a seguir mostra a regra que se aplica quando um comprovante tem apenas linhas de diário onde o tipo de conta é **Razão**.</span><span class="sxs-lookup"><span data-stu-id="a9487-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="a9487-145">Os seguintes pontos mostram as possíveis direções de imposto para contas de razão.</span><span class="sxs-lookup"><span data-stu-id="a9487-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="a9487-146">•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.</span><span class="sxs-lookup"><span data-stu-id="a9487-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="a9487-147">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="a9487-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="a9487-148">Caso contrário, se o valor do diário for débito (positivo), a direção do imposto será Imposto a Receber; se o valor do diário for crédito (negativo), a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="a9487-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="a9487-149">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="a9487-149">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas de razão](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="a9487-151">Substituir a direção do imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-151">Override the sales tax direction</span></span>

<span data-ttu-id="a9487-152">Você poderá substituir a direção do imposto quando o comprovante contiver apenas linhas onde o tipo de conta for **Razão**.</span><span class="sxs-lookup"><span data-stu-id="a9487-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="a9487-153">Vá para **Contabilidade \> Plano de contas \> Contas \> Contas principais** e selecione a guia rápida **Substituições da entidade legal**.</span><span class="sxs-lookup"><span data-stu-id="a9487-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="a9487-154">Determinar o valor do imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-154">Determine the sales tax amount</span></span>

<span data-ttu-id="a9487-155">Esta seção descreve como o valor do sinal do imposto é calculado.</span><span class="sxs-lookup"><span data-stu-id="a9487-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Página Transações de imposto](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="a9487-157">A tabela a seguir mostra a regra genérica para determinar o sinal de valores do imposto na tabela temporária de impostos.</span><span class="sxs-lookup"><span data-stu-id="a9487-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="a9487-158">Valor da linha do diário</span><span class="sxs-lookup"><span data-stu-id="a9487-158">Journal line amount</span></span> | <span data-ttu-id="a9487-159">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-159">Sales tax direction</span></span>  | <span data-ttu-id="a9487-160">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="a9487-161">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-161">Positive</span></span>            | <span data-ttu-id="a9487-162">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-162">Sales Tax Receivable</span></span> | <span data-ttu-id="a9487-163">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-163">Positive</span></span>              |
| <span data-ttu-id="a9487-164">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-164">Positive</span></span>            | <span data-ttu-id="a9487-165">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="a9487-165">Sales Tax Payable</span></span>    | <span data-ttu-id="a9487-166">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-166">Negative</span></span>              |
| <span data-ttu-id="a9487-167">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-167">Negative</span></span>            | <span data-ttu-id="a9487-168">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-168">Sales Tax Receivable</span></span> | <span data-ttu-id="a9487-169">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-169">Negative</span></span>              |
| <span data-ttu-id="a9487-170">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-170">Negative</span></span>            | <span data-ttu-id="a9487-171">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="a9487-171">Sales Tax Payable</span></span>    | <span data-ttu-id="a9487-172">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-172">Positive</span></span>              |

<span data-ttu-id="a9487-173">Há uma regra especial para os comprovantes que têm apenas as linhas **Projeto** ou **Razão**, quando um grupo de impostos de item é selecionado na linha **Razão**.</span><span class="sxs-lookup"><span data-stu-id="a9487-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="a9487-174">A regra é controlada pelo recurso Habilitar cálculo de imposto independente para diários gerais.</span><span class="sxs-lookup"><span data-stu-id="a9487-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="a9487-175">Quando esse recurso está desativado, o valor do imposto da linha **Razão** usa a direção de débito/crédito da linha **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a9487-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="a9487-176">Quando o recurso está ativado, o valor do imposto da linha **Razão** usa sua própria direção de débito/crédito.</span><span class="sxs-lookup"><span data-stu-id="a9487-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="a9487-177">As tabelas a seguir mostram a regra para cada cenário.</span><span class="sxs-lookup"><span data-stu-id="a9487-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="a9487-178">**Regra quando o recurso estiver ativado**</span><span class="sxs-lookup"><span data-stu-id="a9487-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="a9487-179">Valor da linha do diário do projeto</span><span class="sxs-lookup"><span data-stu-id="a9487-179">Journal line amount of project</span></span> | <span data-ttu-id="a9487-180">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-180">Sales tax direction</span></span>  | <span data-ttu-id="a9487-181">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="a9487-182">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-182">Positive</span></span>                       | <span data-ttu-id="a9487-183">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-183">Sales Tax Receivable</span></span> | <span data-ttu-id="a9487-184">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-184">Positive</span></span>              |
| <span data-ttu-id="a9487-185">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-185">Negative</span></span>                       | <span data-ttu-id="a9487-186">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-186">Sales Tax Receivable</span></span> | <span data-ttu-id="a9487-187">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-187">Negative</span></span>              |

<span data-ttu-id="a9487-188">**Regra quando o recurso estiver desativado**</span><span class="sxs-lookup"><span data-stu-id="a9487-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="a9487-189">Valor da linha do diário do razão</span><span class="sxs-lookup"><span data-stu-id="a9487-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="a9487-190">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-190">Sales tax direction</span></span>  | <span data-ttu-id="a9487-191">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="a9487-192">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-192">Positive</span></span>                       | <span data-ttu-id="a9487-193">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-193">Sales Tax Receivable</span></span> | <span data-ttu-id="a9487-194">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-194">Positive</span></span>              |
| <span data-ttu-id="a9487-195">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-195">Negative</span></span>                       | <span data-ttu-id="a9487-196">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-196">Sales Tax Receivable</span></span> | <span data-ttu-id="a9487-197">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="a9487-198">Determinar o valor do imposto e a conta no comprovante</span><span class="sxs-lookup"><span data-stu-id="a9487-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="a9487-199">Ao lançar impostos, a conta principal é recuperada do perfil do grupo de lançamento do razão.</span><span class="sxs-lookup"><span data-stu-id="a9487-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="a9487-200">Quando há impostos a receber, o sistema usa a conta Imposto a Receber que está especificada no perfil.</span><span class="sxs-lookup"><span data-stu-id="a9487-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="a9487-201">Quando há impostos a pagar, o sistema usa a conta Imposto a Pagar que está especificada no perfil.</span><span class="sxs-lookup"><span data-stu-id="a9487-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="a9487-202">A tabela a seguir mostra a regra genérica.</span><span class="sxs-lookup"><span data-stu-id="a9487-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="a9487-203">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-203">Sales tax direction</span></span>  | <span data-ttu-id="a9487-204">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-204">Sales tax amount sign</span></span> | <span data-ttu-id="a9487-205">Conta de imposto</span><span class="sxs-lookup"><span data-stu-id="a9487-205">Sales tax account</span></span>      | <span data-ttu-id="a9487-206">Valor no comprovante</span><span class="sxs-lookup"><span data-stu-id="a9487-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="a9487-207">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-207">Sales Tax Receivable</span></span> | <span data-ttu-id="a9487-208">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-208">Positive</span></span>              | <span data-ttu-id="a9487-209">Contas de Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-209">Tax Receivable Account</span></span> | <span data-ttu-id="a9487-210">Positivo (Débito)</span><span class="sxs-lookup"><span data-stu-id="a9487-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="a9487-211">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-211">Sales Tax Receivable</span></span> | <span data-ttu-id="a9487-212">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-212">Negative</span></span>              | <span data-ttu-id="a9487-213">Contas de Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="a9487-213">Tax Receivable Account</span></span> | <span data-ttu-id="a9487-214">Negativo (Crédito)</span><span class="sxs-lookup"><span data-stu-id="a9487-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="a9487-215">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="a9487-215">Sales Tax Payable</span></span>    | <span data-ttu-id="a9487-216">Positivo</span><span class="sxs-lookup"><span data-stu-id="a9487-216">Positive</span></span>              | <span data-ttu-id="a9487-217">Conta de Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="a9487-217">Tax Payable Account</span></span>    | <span data-ttu-id="a9487-218">Negativo (Crédito)</span><span class="sxs-lookup"><span data-stu-id="a9487-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="a9487-219">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="a9487-219">Sales Tax Payable</span></span>    | <span data-ttu-id="a9487-220">Negativo</span><span class="sxs-lookup"><span data-stu-id="a9487-220">Negative</span></span>              | <span data-ttu-id="a9487-221">Conta de Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="a9487-221">Tax Payable Account</span></span>    | <span data-ttu-id="a9487-222">Positivo (Débito)</span><span class="sxs-lookup"><span data-stu-id="a9487-222">Positive (Debit)</span></span>  |
