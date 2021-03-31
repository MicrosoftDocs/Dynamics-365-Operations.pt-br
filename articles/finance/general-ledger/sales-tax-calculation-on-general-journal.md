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
ms.openlocfilehash: 25eb8dd6965f659f0febe53a6340cb1381c5664f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204897"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="1c841-103">Cálculo de imposto nas linhas do diário geral</span><span class="sxs-lookup"><span data-stu-id="1c841-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="1c841-104">Este tópico explica como os impostos são calculados para diferentes tipos de conta (fornecedor, cliente, razão e projeto) nas linhas do diário geral.</span><span class="sxs-lookup"><span data-stu-id="1c841-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="1c841-105">O processo pode ser dividido em três etapas:</span><span class="sxs-lookup"><span data-stu-id="1c841-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="1c841-106">Determinar a direção do imposto.</span><span class="sxs-lookup"><span data-stu-id="1c841-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="1c841-107">Determinar o valor do imposto que será armazenado em uma tabela de impostos temporária.</span><span class="sxs-lookup"><span data-stu-id="1c841-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="1c841-108">Determinar o valor do imposto e a conta no comprovante.</span><span class="sxs-lookup"><span data-stu-id="1c841-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="1c841-109">Determinar a direção do imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-109">Determine the sales tax direction</span></span>

<span data-ttu-id="1c841-110">A maneira como a direção do imposto é determinada depende do tipo de conta no comprovante.</span><span class="sxs-lookup"><span data-stu-id="1c841-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="1c841-111">A direção do imposto é determinada pela combinação de tipo de conta e de código de imposto.</span><span class="sxs-lookup"><span data-stu-id="1c841-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="1c841-112">As seguintes seções listam as possibilidades mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="1c841-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="1c841-113">Tipo de conta é Projeto</span><span class="sxs-lookup"><span data-stu-id="1c841-113">Account type is Project</span></span>

<span data-ttu-id="1c841-114">Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Projeto**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto.</span><span class="sxs-lookup"><span data-stu-id="1c841-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="1c841-115">A ilustração a seguir mostra a regra.</span><span class="sxs-lookup"><span data-stu-id="1c841-115">The following illustration shows the rule.</span></span> <span data-ttu-id="1c841-116">Os seguintes pontos mostram as possíveis direções de imposto para contas do projeto.</span><span class="sxs-lookup"><span data-stu-id="1c841-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="1c841-117">•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.</span><span class="sxs-lookup"><span data-stu-id="1c841-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="1c841-118">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="1c841-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="1c841-119">•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="1c841-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1c841-120">•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="1c841-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1c841-121">Caso contrário, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="1c841-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="1c841-122">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="1c841-122">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas do projeto](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="1c841-124">Tipo de conta é Fornecedor</span><span class="sxs-lookup"><span data-stu-id="1c841-124">Account type is Vendor</span></span>

<span data-ttu-id="1c841-125">Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Fornecedor**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto.</span><span class="sxs-lookup"><span data-stu-id="1c841-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="1c841-126">Os seguintes pontos mostram as possíveis direções de imposto para contas de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="1c841-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="1c841-127">•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.</span><span class="sxs-lookup"><span data-stu-id="1c841-127">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="1c841-128">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="1c841-128">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="1c841-129">•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="1c841-129">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1c841-130">•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="1c841-130">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1c841-131">Caso contrário, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="1c841-131">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="1c841-132">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="1c841-132">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas de fornecedor](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="1c841-134">Tipo de conta é Cliente</span><span class="sxs-lookup"><span data-stu-id="1c841-134">Account type is Customer</span></span>

<span data-ttu-id="1c841-135">Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Cliente**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto.</span><span class="sxs-lookup"><span data-stu-id="1c841-135">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="1c841-136">Os seguintes pontos mostram as possíveis direções de imposto para contas de cliente.</span><span class="sxs-lookup"><span data-stu-id="1c841-136">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="1c841-137">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="1c841-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="1c841-138">•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="1c841-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="1c841-139">•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="1c841-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="1c841-140">Caso contrário, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="1c841-140">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1c841-141">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="1c841-141">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas de cliente](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="1c841-143">Tipo de conta é Razão</span><span class="sxs-lookup"><span data-stu-id="1c841-143">Account type is Ledger</span></span>

<span data-ttu-id="1c841-144">A ilustração a seguir mostra a regra que se aplica quando um comprovante tem apenas linhas de diário onde o tipo de conta é **Razão**.</span><span class="sxs-lookup"><span data-stu-id="1c841-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="1c841-145">Os seguintes pontos mostram as possíveis direções de imposto para contas de razão.</span><span class="sxs-lookup"><span data-stu-id="1c841-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="1c841-146">•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.</span><span class="sxs-lookup"><span data-stu-id="1c841-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="1c841-147">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="1c841-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="1c841-148">Caso contrário, se o valor do diário for débito (positivo), a direção do imposto será Imposto a Receber; se o valor do diário for crédito (negativo), a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="1c841-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="1c841-149">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="1c841-149">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas de razão](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="1c841-151">Substituir a direção do imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-151">Override the sales tax direction</span></span>

<span data-ttu-id="1c841-152">Você poderá substituir a direção do imposto quando o comprovante contiver apenas linhas onde o tipo de conta for **Razão**.</span><span class="sxs-lookup"><span data-stu-id="1c841-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="1c841-153">Vá para **Contabilidade \> Plano de contas \> Contas \> Contas principais** e selecione a guia rápida **Substituições da entidade legal**.</span><span class="sxs-lookup"><span data-stu-id="1c841-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="1c841-154">Determinar o valor do imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-154">Determine the sales tax amount</span></span>

<span data-ttu-id="1c841-155">Esta seção descreve como o valor do sinal do imposto é calculado.</span><span class="sxs-lookup"><span data-stu-id="1c841-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Página Transações de imposto](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="1c841-157">A tabela a seguir mostra a regra genérica para determinar o sinal de valores do imposto na tabela temporária de impostos.</span><span class="sxs-lookup"><span data-stu-id="1c841-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="1c841-158">Valor da linha do diário</span><span class="sxs-lookup"><span data-stu-id="1c841-158">Journal line amount</span></span> | <span data-ttu-id="1c841-159">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-159">Sales tax direction</span></span>  | <span data-ttu-id="1c841-160">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="1c841-161">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-161">Positive</span></span>            | <span data-ttu-id="1c841-162">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-162">Sales Tax Receivable</span></span> | <span data-ttu-id="1c841-163">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-163">Positive</span></span>              |
| <span data-ttu-id="1c841-164">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-164">Positive</span></span>            | <span data-ttu-id="1c841-165">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="1c841-165">Sales Tax Payable</span></span>    | <span data-ttu-id="1c841-166">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-166">Negative</span></span>              |
| <span data-ttu-id="1c841-167">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-167">Negative</span></span>            | <span data-ttu-id="1c841-168">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-168">Sales Tax Receivable</span></span> | <span data-ttu-id="1c841-169">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-169">Negative</span></span>              |
| <span data-ttu-id="1c841-170">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-170">Negative</span></span>            | <span data-ttu-id="1c841-171">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="1c841-171">Sales Tax Payable</span></span>    | <span data-ttu-id="1c841-172">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-172">Positive</span></span>              |

<span data-ttu-id="1c841-173">Há uma regra especial para os comprovantes que têm apenas as linhas **Projeto** ou **Razão**, quando um grupo de impostos de item é selecionado na linha **Razão**.</span><span class="sxs-lookup"><span data-stu-id="1c841-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="1c841-174">A regra é controlada pelo recurso Habilitar cálculo de imposto independente para diários gerais.</span><span class="sxs-lookup"><span data-stu-id="1c841-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="1c841-175">Quando esse recurso está desativado, o valor do imposto da linha **Razão** usa a direção de débito/crédito da linha **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="1c841-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="1c841-176">Quando o recurso está ativado, o valor do imposto da linha **Razão** usa sua própria direção de débito/crédito.</span><span class="sxs-lookup"><span data-stu-id="1c841-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="1c841-177">As tabelas a seguir mostram a regra para cada cenário.</span><span class="sxs-lookup"><span data-stu-id="1c841-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="1c841-178">**Regra quando o recurso estiver ativado**</span><span class="sxs-lookup"><span data-stu-id="1c841-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="1c841-179">Valor da linha do diário do projeto</span><span class="sxs-lookup"><span data-stu-id="1c841-179">Journal line amount of project</span></span> | <span data-ttu-id="1c841-180">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-180">Sales tax direction</span></span>  | <span data-ttu-id="1c841-181">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="1c841-182">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-182">Positive</span></span>                       | <span data-ttu-id="1c841-183">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-183">Sales Tax Receivable</span></span> | <span data-ttu-id="1c841-184">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-184">Positive</span></span>              |
| <span data-ttu-id="1c841-185">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-185">Negative</span></span>                       | <span data-ttu-id="1c841-186">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-186">Sales Tax Receivable</span></span> | <span data-ttu-id="1c841-187">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-187">Negative</span></span>              |

<span data-ttu-id="1c841-188">**Regra quando o recurso estiver desativado**</span><span class="sxs-lookup"><span data-stu-id="1c841-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="1c841-189">Valor da linha do diário do razão</span><span class="sxs-lookup"><span data-stu-id="1c841-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="1c841-190">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-190">Sales tax direction</span></span>  | <span data-ttu-id="1c841-191">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="1c841-192">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-192">Positive</span></span>                       | <span data-ttu-id="1c841-193">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-193">Sales Tax Receivable</span></span> | <span data-ttu-id="1c841-194">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-194">Positive</span></span>              |
| <span data-ttu-id="1c841-195">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-195">Negative</span></span>                       | <span data-ttu-id="1c841-196">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-196">Sales Tax Receivable</span></span> | <span data-ttu-id="1c841-197">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="1c841-198">Determinar o valor do imposto e a conta no comprovante</span><span class="sxs-lookup"><span data-stu-id="1c841-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="1c841-199">Ao lançar impostos, a conta principal é recuperada do perfil do grupo de lançamento do razão.</span><span class="sxs-lookup"><span data-stu-id="1c841-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="1c841-200">Quando há impostos a receber, o sistema usa a conta Imposto a Receber que está especificada no perfil.</span><span class="sxs-lookup"><span data-stu-id="1c841-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="1c841-201">Quando há impostos a pagar, o sistema usa a conta Imposto a Pagar que está especificada no perfil.</span><span class="sxs-lookup"><span data-stu-id="1c841-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="1c841-202">A tabela a seguir mostra a regra genérica.</span><span class="sxs-lookup"><span data-stu-id="1c841-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="1c841-203">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-203">Sales tax direction</span></span>  | <span data-ttu-id="1c841-204">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-204">Sales tax amount sign</span></span> | <span data-ttu-id="1c841-205">Conta de imposto</span><span class="sxs-lookup"><span data-stu-id="1c841-205">Sales tax account</span></span>      | <span data-ttu-id="1c841-206">Valor no comprovante</span><span class="sxs-lookup"><span data-stu-id="1c841-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="1c841-207">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-207">Sales Tax Receivable</span></span> | <span data-ttu-id="1c841-208">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-208">Positive</span></span>              | <span data-ttu-id="1c841-209">Contas de Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-209">Tax Receivable Account</span></span> | <span data-ttu-id="1c841-210">Positivo (Débito)</span><span class="sxs-lookup"><span data-stu-id="1c841-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="1c841-211">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-211">Sales Tax Receivable</span></span> | <span data-ttu-id="1c841-212">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-212">Negative</span></span>              | <span data-ttu-id="1c841-213">Contas de Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="1c841-213">Tax Receivable Account</span></span> | <span data-ttu-id="1c841-214">Negativo (Crédito)</span><span class="sxs-lookup"><span data-stu-id="1c841-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="1c841-215">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="1c841-215">Sales Tax Payable</span></span>    | <span data-ttu-id="1c841-216">Positivo</span><span class="sxs-lookup"><span data-stu-id="1c841-216">Positive</span></span>              | <span data-ttu-id="1c841-217">Conta de Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="1c841-217">Tax Payable Account</span></span>    | <span data-ttu-id="1c841-218">Negativo (Crédito)</span><span class="sxs-lookup"><span data-stu-id="1c841-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="1c841-219">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="1c841-219">Sales Tax Payable</span></span>    | <span data-ttu-id="1c841-220">Negativo</span><span class="sxs-lookup"><span data-stu-id="1c841-220">Negative</span></span>              | <span data-ttu-id="1c841-221">Conta de Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="1c841-221">Tax Payable Account</span></span>    | <span data-ttu-id="1c841-222">Positivo (Débito)</span><span class="sxs-lookup"><span data-stu-id="1c841-222">Positive (Debit)</span></span>  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]