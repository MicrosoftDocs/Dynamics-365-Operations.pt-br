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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 354076dbc14f34b83d1cd24f591874b9af856af1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186293"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a><span data-ttu-id="885f3-103">Cálculo de imposto nas linhas do diário geral</span><span class="sxs-lookup"><span data-stu-id="885f3-103">Sales tax calculation on general journal lines</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="885f3-104">Este tópico explica como os impostos são calculados para diferentes tipos de conta (fornecedor, cliente, razão e projeto) nas linhas do diário geral.</span><span class="sxs-lookup"><span data-stu-id="885f3-104">This topic explains how sales taxes are calculated for different types of accounts (vendor, customer, ledger, and project) on general journal lines.</span></span>

<span data-ttu-id="885f3-105">O processo pode ser dividido em três etapas:</span><span class="sxs-lookup"><span data-stu-id="885f3-105">The process can be divided into three steps:</span></span>

- <span data-ttu-id="885f3-106">Determinar a direção do imposto.</span><span class="sxs-lookup"><span data-stu-id="885f3-106">Determine the sales tax direction.</span></span>

- <span data-ttu-id="885f3-107">Determinar o valor do imposto que será armazenado em uma tabela de impostos temporária.</span><span class="sxs-lookup"><span data-stu-id="885f3-107">Determine the sales tax amount that will be stored a temporary sales tax table.</span></span>

- <span data-ttu-id="885f3-108">Determinar o valor do imposto e a conta no comprovante.</span><span class="sxs-lookup"><span data-stu-id="885f3-108">Determine the sales tax amount and account on the voucher.</span></span>

## <a name="determine-the-sales-tax-direction"></a><span data-ttu-id="885f3-109">Determinar a direção do imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-109">Determine the sales tax direction</span></span>

<span data-ttu-id="885f3-110">A maneira como a direção do imposto é determinada depende do tipo de conta no comprovante.</span><span class="sxs-lookup"><span data-stu-id="885f3-110">The way that the sales tax direction is determined depends on the type of account in the voucher.</span></span> <span data-ttu-id="885f3-111">A direção do imposto é determinada pela combinação de tipo de conta e de código de imposto.</span><span class="sxs-lookup"><span data-stu-id="885f3-111">The sales tax direction is determined by the combination of account type and sales tax code.</span></span> <span data-ttu-id="885f3-112">As seguintes seções listam as possibilidades mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="885f3-112">The following sections the possibilities in more detail.</span></span> 

### <a name="account-type-is-project"></a><span data-ttu-id="885f3-113">Tipo de conta é Projeto</span><span class="sxs-lookup"><span data-stu-id="885f3-113">Account type is Project</span></span>

<span data-ttu-id="885f3-114">Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Projeto**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto.</span><span class="sxs-lookup"><span data-stu-id="885f3-114">If a voucher has journal line where the account type is **Project**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="885f3-115">A ilustração a seguir mostra a regra.</span><span class="sxs-lookup"><span data-stu-id="885f3-115">The following illustration shows the rule.</span></span> <span data-ttu-id="885f3-116">Os seguintes pontos mostram as possíveis direções de imposto para contas do projeto.</span><span class="sxs-lookup"><span data-stu-id="885f3-116">The following points show the possible tax directions for project accounts.</span></span>

<span data-ttu-id="885f3-117">•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.</span><span class="sxs-lookup"><span data-stu-id="885f3-117">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="885f3-118">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="885f3-118">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="885f3-119">•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="885f3-119">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="885f3-120">•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="885f3-120">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="885f3-121">Caso contrário, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="885f3-121">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="885f3-122">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="885f3-122">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas do projeto](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a><span data-ttu-id="885f3-124">Tipo de conta é Fornecedor</span><span class="sxs-lookup"><span data-stu-id="885f3-124">Account type is Vendor</span></span>

<span data-ttu-id="885f3-125">Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Fornecedor**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto.</span><span class="sxs-lookup"><span data-stu-id="885f3-125">If a voucher has journal line where the account type is **Vendor**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="885f3-126">Os seguintes pontos mostram as possíveis direções de imposto para contas de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="885f3-126">The following points show the possible tax directions for vendor accounts.</span></span> 

<span data-ttu-id="885f3-127">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="885f3-127">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="885f3-128">•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="885f3-128">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="885f3-129">•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="885f3-129">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Receivable.</span></span>


<span data-ttu-id="885f3-130">Caso contrário, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="885f3-130">Otherwise, sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="885f3-131">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="885f3-131">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas de fornecedor](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a><span data-ttu-id="885f3-133">Tipo de conta é Cliente</span><span class="sxs-lookup"><span data-stu-id="885f3-133">Account type is Customer</span></span>

<span data-ttu-id="885f3-134">Se um comprovante tiver uma linha de diário, onde o tipo de conta for **Cliente**, todas as linhas do diário no comprovante aplicarão a mesma direção de imposto.</span><span class="sxs-lookup"><span data-stu-id="885f3-134">If a voucher has journal line where the account type is **Customer**, all the journal lines in the voucher apply the same tax direction.</span></span> <span data-ttu-id="885f3-135">Os seguintes pontos mostram as possíveis direções de imposto para contas de cliente.</span><span class="sxs-lookup"><span data-stu-id="885f3-135">The following points show the possible tax directions for customer accounts.</span></span>

<span data-ttu-id="885f3-136">•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.</span><span class="sxs-lookup"><span data-stu-id="885f3-136">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="885f3-137">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="885f3-137">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="885f3-138">•   Se o código do imposto for IVA intracom, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="885f3-138">•   If the sales tax code is intracom VAT, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="885f3-139">•   Se o código do imposto for encargo revertido, a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="885f3-139">•   If the sales tax code is reverse charge, then sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="885f3-140">Caso contrário, a direção do imposto será Imposto a Receber.</span><span class="sxs-lookup"><span data-stu-id="885f3-140">Otherwise, sales tax direction is Sales Tax Receivable.</span></span>

<span data-ttu-id="885f3-141">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="885f3-141">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas de cliente](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a><span data-ttu-id="885f3-143">Tipo de conta é Razão</span><span class="sxs-lookup"><span data-stu-id="885f3-143">Account type is Ledger</span></span>

<span data-ttu-id="885f3-144">A ilustração a seguir mostra a regra que se aplica quando um comprovante tem apenas linhas de diário onde o tipo de conta é **Razão**.</span><span class="sxs-lookup"><span data-stu-id="885f3-144">The following illustration shows the rule that applies when a voucher has only journal lines where the account type is **Ledger**.</span></span> <span data-ttu-id="885f3-145">Os seguintes pontos mostram as possíveis direções de imposto para contas de razão.</span><span class="sxs-lookup"><span data-stu-id="885f3-145">The following points show the possible tax directions for ledger accounts.</span></span>

<span data-ttu-id="885f3-146">•   Se o código do imposto for imposto sobre uso, a direção do imposto será Imposto sobre o Uso.</span><span class="sxs-lookup"><span data-stu-id="885f3-146">•   If the sales tax code is use tax, then sales tax direction is Use Tax.</span></span>

<span data-ttu-id="885f3-147">•   Se o código do imposto for isenção de imposto, a direção do imposto será Compra Isenta de Imposto.</span><span class="sxs-lookup"><span data-stu-id="885f3-147">•   If the sales tax code is exempt tax, then sales tax direction is Tax Free Purchase.</span></span>

<span data-ttu-id="885f3-148">Caso contrário, se o valor do diário for débito (positivo), a direção do imposto será Imposto a Receber; se o valor do diário for crédito (negativo), a direção do imposto será Imposto a Pagar.</span><span class="sxs-lookup"><span data-stu-id="885f3-148">Otherwise, if the journal amount is debit (positive) ,sales tax direction is Sales Tax Receivable; if the journal amount is credit (negative) ,sales tax direction is Sales Tax Payable.</span></span>

<span data-ttu-id="885f3-149">O diagrama a seguir ilustra a regra graficamente.</span><span class="sxs-lookup"><span data-stu-id="885f3-149">The following diagram illustrates the rule graphically.</span></span>

![Possibilidades de direção do imposto para contas de razão](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a><span data-ttu-id="885f3-151">Substituir a direção do imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-151">Override the sales tax direction</span></span>

<span data-ttu-id="885f3-152">Você poderá substituir a direção do imposto quando o comprovante contiver apenas linhas onde o tipo de conta for **Razão**.</span><span class="sxs-lookup"><span data-stu-id="885f3-152">You can override the sales tax direction when the voucher contains only lines where the account type is **Ledger**.</span></span>

<span data-ttu-id="885f3-153">Vá para **Contabilidade \> Plano de contas \> Contas \> Contas principais** e selecione a guia rápida **Substituições da entidade legal**.</span><span class="sxs-lookup"><span data-stu-id="885f3-153">Go to **General ledger \> Chart of accounts \> Accounts \> Main accounts**, and select the **Legal entity overrides** FastTab.</span></span>

## <a name="determine-the-sales-tax-amount"></a><span data-ttu-id="885f3-154">Determinar o valor do imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-154">Determine the sales tax amount</span></span>

<span data-ttu-id="885f3-155">Esta seção descreve como o valor do sinal do imposto é calculado.</span><span class="sxs-lookup"><span data-stu-id="885f3-155">This section describes how the sales tax amount sign is calculated.</span></span>

![Página Transações de imposto](media/sales-tax-amount-sign.jpg)

<span data-ttu-id="885f3-157">A tabela a seguir mostra a regra genérica para determinar o sinal de valores do imposto na tabela temporária de impostos.</span><span class="sxs-lookup"><span data-stu-id="885f3-157">The following table shows the generic rule for determining the sign of sales tax amounts in the temporary sales tax table.</span></span>

| <span data-ttu-id="885f3-158">Valor da linha do diário</span><span class="sxs-lookup"><span data-stu-id="885f3-158">Journal line amount</span></span> | <span data-ttu-id="885f3-159">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-159">Sales tax direction</span></span>  | <span data-ttu-id="885f3-160">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-160">Sales tax amount sign</span></span> |
|---------------------|----------------------|-----------------------|
| <span data-ttu-id="885f3-161">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-161">Positive</span></span>            | <span data-ttu-id="885f3-162">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-162">Sales Tax Receivable</span></span> | <span data-ttu-id="885f3-163">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-163">Positive</span></span>              |
| <span data-ttu-id="885f3-164">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-164">Positive</span></span>            | <span data-ttu-id="885f3-165">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="885f3-165">Sales Tax Payable</span></span>    | <span data-ttu-id="885f3-166">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-166">Negative</span></span>              |
| <span data-ttu-id="885f3-167">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-167">Negative</span></span>            | <span data-ttu-id="885f3-168">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-168">Sales Tax Receivable</span></span> | <span data-ttu-id="885f3-169">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-169">Negative</span></span>              |
| <span data-ttu-id="885f3-170">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-170">Negative</span></span>            | <span data-ttu-id="885f3-171">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="885f3-171">Sales Tax Payable</span></span>    | <span data-ttu-id="885f3-172">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-172">Positive</span></span>              |

<span data-ttu-id="885f3-173">Há uma regra especial para os comprovantes que têm apenas as linhas **Projeto** ou **Razão**, quando um grupo de impostos de item é selecionado na linha **Razão**.</span><span class="sxs-lookup"><span data-stu-id="885f3-173">There is a special rule for vouchers that have only **Project** or **Ledger** lines, when a sales tax group or item sales tax group is selected on the **Ledger** line.</span></span> <span data-ttu-id="885f3-174">A regra é controlada pelo recurso Habilitar cálculo de imposto independente para diários gerais.</span><span class="sxs-lookup"><span data-stu-id="885f3-174">This rule is controlled by Enable independent sales tax calculation feature for general journals.</span></span> <span data-ttu-id="885f3-175">Quando esse recurso está desativado, o valor do imposto da linha **Razão** usa a direção de débito/crédito da linha **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="885f3-175">When this feature is turned off, the tax amount of the **Ledger** line uses the debit/credit direction of the **Project** line.</span></span> <span data-ttu-id="885f3-176">Quando o recurso está ativado, o valor do imposto da linha **Razão** usa sua própria direção de débito/crédito.</span><span class="sxs-lookup"><span data-stu-id="885f3-176">When the feature is turned on, the tax amount of the **Ledger** line uses its own debit/credit direction.</span></span> <span data-ttu-id="885f3-177">As tabelas a seguir mostram a regra para cada cenário.</span><span class="sxs-lookup"><span data-stu-id="885f3-177">The following tables show the rule for each scenario.</span></span> 

<span data-ttu-id="885f3-178">**Regra quando o recurso estiver ativado**</span><span class="sxs-lookup"><span data-stu-id="885f3-178">**Rule when the feature is turned on**</span></span>

| <span data-ttu-id="885f3-179">Valor da linha do diário do projeto</span><span class="sxs-lookup"><span data-stu-id="885f3-179">Journal line amount of project</span></span> | <span data-ttu-id="885f3-180">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-180">Sales tax direction</span></span>  | <span data-ttu-id="885f3-181">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-181">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="885f3-182">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-182">Positive</span></span>                       | <span data-ttu-id="885f3-183">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-183">Sales Tax Receivable</span></span> | <span data-ttu-id="885f3-184">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-184">Positive</span></span>              |
| <span data-ttu-id="885f3-185">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-185">Negative</span></span>                       | <span data-ttu-id="885f3-186">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-186">Sales Tax Receivable</span></span> | <span data-ttu-id="885f3-187">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-187">Negative</span></span>              |

<span data-ttu-id="885f3-188">**Regra quando o recurso estiver desativado**</span><span class="sxs-lookup"><span data-stu-id="885f3-188">**Rule when the feature is turned off**</span></span>

| <span data-ttu-id="885f3-189">Valor da linha do diário do razão</span><span class="sxs-lookup"><span data-stu-id="885f3-189">Journal line amount of ledger</span></span>  | <span data-ttu-id="885f3-190">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-190">Sales tax direction</span></span>  | <span data-ttu-id="885f3-191">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-191">Sales tax amount sign</span></span> |
|--------------------------------|----------------------|-----------------------|
| <span data-ttu-id="885f3-192">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-192">Positive</span></span>                       | <span data-ttu-id="885f3-193">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-193">Sales Tax Receivable</span></span> | <span data-ttu-id="885f3-194">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-194">Positive</span></span>              |
| <span data-ttu-id="885f3-195">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-195">Negative</span></span>                       | <span data-ttu-id="885f3-196">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-196">Sales Tax Receivable</span></span> | <span data-ttu-id="885f3-197">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-197">Negative</span></span>              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a><span data-ttu-id="885f3-198">Determinar o valor do imposto e a conta no comprovante</span><span class="sxs-lookup"><span data-stu-id="885f3-198">Determine the sales tax amount and account on the voucher</span></span>

<span data-ttu-id="885f3-199">Ao lançar impostos, a conta principal é recuperada do perfil do grupo de lançamento do razão.</span><span class="sxs-lookup"><span data-stu-id="885f3-199">When you post sales taxes, the main account is retrieved from the ledger posting group profile.</span></span> <span data-ttu-id="885f3-200">Quando há impostos a receber, o sistema usa a conta Imposto a Receber que está especificada no perfil.</span><span class="sxs-lookup"><span data-stu-id="885f3-200">When sales taxes are receivable, the system uses the Sales Tax Receivable account that is specified in the profile.</span></span> <span data-ttu-id="885f3-201">Quando há impostos a pagar, o sistema usa a conta Imposto a Pagar que está especificada no perfil.</span><span class="sxs-lookup"><span data-stu-id="885f3-201">For sales taxes that are payable, the system uses Sales Tax Payable account that is specified in the profile.</span></span>

<span data-ttu-id="885f3-202">A tabela a seguir mostra a regra genérica.</span><span class="sxs-lookup"><span data-stu-id="885f3-202">The following table shows the generic rule.</span></span>

| <span data-ttu-id="885f3-203">Direção de imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-203">Sales tax direction</span></span>  | <span data-ttu-id="885f3-204">Sinal do valor do imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-204">Sales tax amount sign</span></span> | <span data-ttu-id="885f3-205">Conta de imposto</span><span class="sxs-lookup"><span data-stu-id="885f3-205">Sales tax account</span></span>      | <span data-ttu-id="885f3-206">Valor no comprovante</span><span class="sxs-lookup"><span data-stu-id="885f3-206">Amount on voucher</span></span> |
|----------------------|-----------------------|------------------------|-------------------|
| <span data-ttu-id="885f3-207">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-207">Sales Tax Receivable</span></span> | <span data-ttu-id="885f3-208">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-208">Positive</span></span>              | <span data-ttu-id="885f3-209">Contas de Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-209">Tax Receivable Account</span></span> | <span data-ttu-id="885f3-210">Positivo (Débito)</span><span class="sxs-lookup"><span data-stu-id="885f3-210">Positive (Debit)</span></span>  |
| <span data-ttu-id="885f3-211">Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-211">Sales Tax Receivable</span></span> | <span data-ttu-id="885f3-212">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-212">Negative</span></span>              | <span data-ttu-id="885f3-213">Contas de Imposto a Receber</span><span class="sxs-lookup"><span data-stu-id="885f3-213">Tax Receivable Account</span></span> | <span data-ttu-id="885f3-214">Negativo (Crédito)</span><span class="sxs-lookup"><span data-stu-id="885f3-214">Negative(Credit)</span></span>  |
| <span data-ttu-id="885f3-215">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="885f3-215">Sales Tax Payable</span></span>    | <span data-ttu-id="885f3-216">Positivo</span><span class="sxs-lookup"><span data-stu-id="885f3-216">Positive</span></span>              | <span data-ttu-id="885f3-217">Conta de Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="885f3-217">Tax Payable Account</span></span>    | <span data-ttu-id="885f3-218">Negativo (Crédito)</span><span class="sxs-lookup"><span data-stu-id="885f3-218">Negative(Credit)</span></span>  |
| <span data-ttu-id="885f3-219">Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="885f3-219">Sales Tax Payable</span></span>    | <span data-ttu-id="885f3-220">Negativo</span><span class="sxs-lookup"><span data-stu-id="885f3-220">Negative</span></span>              | <span data-ttu-id="885f3-221">Conta de Imposto a Pagar</span><span class="sxs-lookup"><span data-stu-id="885f3-221">Tax Payable Account</span></span>    | <span data-ttu-id="885f3-222">Positivo (Débito)</span><span class="sxs-lookup"><span data-stu-id="885f3-222">Positive (Debit)</span></span>  |
