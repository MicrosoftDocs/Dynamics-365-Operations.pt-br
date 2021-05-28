---
title: O imposto não é calculado ou o valor do imposto é zero
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudar quando o valor do imposto for 0 (zero) ou o imposto não for calculado.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: c398579a0a408e7f5625a3e801a967955c4b1e5b
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020106"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a><span data-ttu-id="3a404-103">O imposto não é calculado ou o valor do imposto é zero</span><span class="sxs-lookup"><span data-stu-id="3a404-103">Tax isn't calculated or the tax amount is zero</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a404-104">Uma transação pode ter um valor de linha diferente de 0 (zero), mas o imposto não é calculado ou o valor do imposto calculado é 0.</span><span class="sxs-lookup"><span data-stu-id="3a404-104">A transaction might have a line amount that isn't 0 (zero), but either tax isn't calculated or the calculated tax amount is 0.</span></span> <span data-ttu-id="3a404-105">Para solucionar esse problema, siga as etapas nas seguintes seções, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3a404-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a><span data-ttu-id="3a404-106">Verificar se os códigos de imposto foram selecionados corretamente pela transação</span><span class="sxs-lookup"><span data-stu-id="3a404-106">Verify that tax codes are correctly selected by the transaction</span></span>

<span data-ttu-id="3a404-107">Se a transação não selecionar os códigos de imposto corretos ou se não selecionar nenhum código de imposto, os impostos não serão calculados nela.</span><span class="sxs-lookup"><span data-stu-id="3a404-107">If the transaction doesn't select the correct tax codes, or if it doesn't select any tax codes, taxes won't be calculated on it.</span></span> <span data-ttu-id="3a404-108">Siga estas etapas para verificar se os códigos de imposto foram selecionados corretamente pela transação.</span><span class="sxs-lookup"><span data-stu-id="3a404-108">Follow these steps to verify that tax codes are correctly selected by the transaction.</span></span> 

1. <span data-ttu-id="3a404-109">Na linha de transação, na FastTab **Detalhes da linha**, na guia **Configuração**, na seção **Imposto**, verifique se os grupos de impostos corretos foram selecionados nos campos **Grupo de impostos do item** e **Grupo de impostos**.</span><span class="sxs-lookup"><span data-stu-id="3a404-109">On the transaction line, on the **Line details** FastTab, on the **Setup** tab, in the **Sales tax** section, verify that the correct tax groups are selected in the **Item sales tax group** and **Sales tax group** fields.</span></span> <span data-ttu-id="3a404-110">Se os grupos de impostos corretos não tiverem sido selecionados, selecione-os.</span><span class="sxs-lookup"><span data-stu-id="3a404-110">If the correct tax groups aren't selected, select them.</span></span>

    <span data-ttu-id="3a404-111">[![Campos Grupo de impostos do item e Grupo de impostos](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="3a404-111">[![Item sales tax group and Sales tax group fields](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)</span></span>

2. <span data-ttu-id="3a404-112">Vá para **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Grupos de impostos**.</span><span class="sxs-lookup"><span data-stu-id="3a404-112">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
3. <span data-ttu-id="3a404-113">Selecione o grupo de impostos apropriado e, na FastTab **Configuração**, anote o código do imposto no campo **Código do imposto**.</span><span class="sxs-lookup"><span data-stu-id="3a404-113">Select the appropriate sales tax group, and then, on the **Setup** FastTab, make a note of the tax code in the **Sales tax code** field.</span></span>

    <span data-ttu-id="3a404-114">[![Página Grupos de impostos](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="3a404-114">[![Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)</span></span>

4. <span data-ttu-id="3a404-115">Vá para **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Grupos de impostos do item**.</span><span class="sxs-lookup"><span data-stu-id="3a404-115">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Item sales tax groups**.</span></span>
5. <span data-ttu-id="3a404-116">Selecione o grupo de impostos do item apropriado e, na FastTab **Configuração**, verifique se o código de imposto no campo **Código do imposto** corresponde ao código de imposto do grupo de impostos.</span><span class="sxs-lookup"><span data-stu-id="3a404-116">Select the appropriate item sales tax group, and then, on the **Setup** FastTab, verify that the tax code in the **Sales tax code** field matches the tax code of the sales tax group.</span></span>

    <span data-ttu-id="3a404-117">[![Página Grupos de impostos do item](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="3a404-117">[![Item sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)</span></span>

6. <span data-ttu-id="3a404-118">Se os códigos de imposto não corresponderem, atualize o código do imposto de um dos grupos.</span><span class="sxs-lookup"><span data-stu-id="3a404-118">If the tax codes don't match, update the sales tax code for one of the groups.</span></span>

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a><span data-ttu-id="3a404-119">Verificar se os códigos de imposto selecionados não estão isentos e se eles têm o valor correto da taxa de imposto</span><span class="sxs-lookup"><span data-stu-id="3a404-119">Verify that the selected tax codes aren't exempt and that they have the correct tax rate value</span></span>

<span data-ttu-id="3a404-120">Se os códigos de imposto estiverem isentos ou se a taxa de imposto for 0 (zero), o resultado do cálculo do imposto será 0.</span><span class="sxs-lookup"><span data-stu-id="3a404-120">If the tax codes are exempt, or if the tax rate is 0 (zero), the tax calculation result will be 0.</span></span> <span data-ttu-id="3a404-121">Siga estas etapas para determinar se os códigos de imposto selecionados estão isentos e para verificar se a taxa de imposto correta foi aplicada a eles.</span><span class="sxs-lookup"><span data-stu-id="3a404-121">Follow these steps to determine whether the selected tax codes are exempt and to verify that the correct tax rate is applied to them.</span></span>

1. <span data-ttu-id="3a404-122">Vá para **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Grupos de impostos**.</span><span class="sxs-lookup"><span data-stu-id="3a404-122">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax groups**.</span></span>
2. <span data-ttu-id="3a404-123">Selecione o grupo de impostos apropriado e, na FastTab **Configuração**, verifique se a caixa de seleção **Isento** está desmarcada.</span><span class="sxs-lookup"><span data-stu-id="3a404-123">Select the appropriate sales tax group, and then, on the **Setup** FastTab, verify that the **Exempt** check box is cleared.</span></span> <span data-ttu-id="3a404-124">Se estiver marcada, desmarque-a.</span><span class="sxs-lookup"><span data-stu-id="3a404-124">If it's selected, clear it.</span></span>

    <span data-ttu-id="3a404-125">[![Caixa de seleção Isento na página Grupos de impostos](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span><span class="sxs-lookup"><span data-stu-id="3a404-125">[![Exempt check box on the Sales tax groups page](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)</span></span>

3. <span data-ttu-id="3a404-126">Vá para **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Códigos de imposto**.</span><span class="sxs-lookup"><span data-stu-id="3a404-126">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="3a404-127">Selecione o código de imposto apropriado e verifique se o valor da taxa de imposto no campo **Valor** não é 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="3a404-127">Select the appropriate sales tax code, and then verify that the tax rate value in the **Value** field isn't 0 (zero).</span></span> <span data-ttu-id="3a404-128">Se for 0, atualize o campo para que seja definido como a taxa de imposto correta.</span><span class="sxs-lookup"><span data-stu-id="3a404-128">If it's 0, update the field so that it's set to the correct tax rate.</span></span>

    <span data-ttu-id="3a404-129">[![Campo Valor na página Valores do código de imposto](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span><span class="sxs-lookup"><span data-stu-id="3a404-129">[![Value field on the Sales tax code values page](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)</span></span>

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a><span data-ttu-id="3a404-130">Determinar se zero é o valor correto do imposto</span><span class="sxs-lookup"><span data-stu-id="3a404-130">Determine whether zero is the correct tax amount</span></span>

<span data-ttu-id="3a404-131">Em alguns cenários, um valor de imposto 0 (zero) é correto.</span><span class="sxs-lookup"><span data-stu-id="3a404-131">In some scenarios, a tax amount of 0 (zero) is correct.</span></span> <span data-ttu-id="3a404-132">Siga estas etapas para determinar se 0 é o valor correto do imposto para a sua transação.</span><span class="sxs-lookup"><span data-stu-id="3a404-132">Follow these steps to determine whether 0 is the correct tax amount for your transaction.</span></span>

1. <span data-ttu-id="3a404-133">Vá para **Contabilidade** \> **Configuração do razão** \> **Parâmetros da contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="3a404-133">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="3a404-134">Na guia **Imposto**, no campo **Método de cálculo**, verifique se o **Total** foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="3a404-134">On the **Sales tax** tab, in the **Calculation method** field, verify that **Total** is selected.</span></span>

    <span data-ttu-id="3a404-135">[![Campo Método de cálculo na página Parâmetros da contabilidade](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span><span class="sxs-lookup"><span data-stu-id="3a404-135">[![Calculation method field on the General ledger parameters page](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)</span></span>

3. <span data-ttu-id="3a404-136">Vá para **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Códigos de imposto**.</span><span class="sxs-lookup"><span data-stu-id="3a404-136">Go to **Tax** \> **Indirect taxes** \> **Sales tax** \> **Sales tax codes**.</span></span>
4. <span data-ttu-id="3a404-137">Selecione o código de imposto apropriado, selecione **Cálculo** \> **Base marginal** e verifique se a base marginal está definida como **Valor líquido do saldo da fatura** ou **Total da fatura incluindo outros valores de imposto**.</span><span class="sxs-lookup"><span data-stu-id="3a404-137">Select the appropriate sales tax code, select **Calculation** \> **Marginal base**, and verify that the marginal base is set to **Net amount of invoice balance** or **Invoice total incl. other sales tax amounts**.</span></span> <span data-ttu-id="3a404-138">Para obter mais informações, consulte o [Total da fatura incluindo outros valores de imposto](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span><span class="sxs-lookup"><span data-stu-id="3a404-138">For more information, see the [Invoice total incl. other sales tax amounts](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).</span></span>
5. <span data-ttu-id="3a404-139">Se os valores corretos foram definidos nas etapas 2 e 4, determine se o valor total da transação é 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="3a404-139">If the correct values are set in steps 2 and 4, determine whether the total amount of the transaction is 0 (zero).</span></span> <span data-ttu-id="3a404-140">Se o valor total for 0, um valor de imposto igual a 0 será o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="3a404-140">If the total amount is 0, a tax amount of 0 is the expected result.</span></span> <span data-ttu-id="3a404-141">Como o cálculo do imposto se baseia no valor total do saldo da fatura e esse valor não é linha por linha, o valor do imposto 0 será alocado a cada linha após o cálculo do imposto.</span><span class="sxs-lookup"><span data-stu-id="3a404-141">Because the tax calculation is based on the total amount of the invoice balance, and that amount isn't line by line, the tax amount of 0 will be allocated to each line after the tax calculation.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="3a404-142">Determinar se há personalização</span><span class="sxs-lookup"><span data-stu-id="3a404-142">Determine whether customization exists</span></span>

<span data-ttu-id="3a404-143">Se você concluiu as etapas nas seções anteriores, mas não encontrou nenhum problema, determine se há personalização.</span><span class="sxs-lookup"><span data-stu-id="3a404-143">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="3a404-144">Se não houver personalização, crie uma solicitação de serviço da Microsoft para obter suporte adicional.</span><span class="sxs-lookup"><span data-stu-id="3a404-144">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
