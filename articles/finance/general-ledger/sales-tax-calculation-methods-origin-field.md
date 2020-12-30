---
title: Métodos de cálculo de imposto no campo Origem
description: Este artigo explica as opções no campo Origem na página de códigos de imposto e como os impostos são calculados com base na opção selecionada para um código de imposto.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
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
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0eb3671051d9a3be9430050e2a0ad4227b17677e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440359"
---
# <a name="sales-tax-calculation-methods-in-the-origin-field"></a><span data-ttu-id="8e0be-103">Métodos de cálculo de imposto no campo Origem</span><span class="sxs-lookup"><span data-stu-id="8e0be-103">Sales tax calculation methods in the Origin field</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e0be-104">Este artigo explica as opções no campo Origem na página de códigos de imposto e como os impostos são calculados com base na opção selecionada para um código de imposto.</span><span class="sxs-lookup"><span data-stu-id="8e0be-104">This article explains the options in the Origin field on the sales tax codes page and how sales tax is calculated based on the selected option for a sales tax code.</span></span>

<span data-ttu-id="8e0be-105">Para cada código de imposto que você cria na página Códigos de imposto, será necessário selecionar o método de cálculo a ser aplicado ao valor de base do imposto no campo Origem.</span><span class="sxs-lookup"><span data-stu-id="8e0be-105">For each sales tax code that you create in the Sales tax codes page, you must select the method of calculation to apply to the tax base amount in the Origin field.</span></span>

## <a name="percentage-of-net-amount"></a><span data-ttu-id="8e0be-106">Porcentagem do valor líquido</span><span class="sxs-lookup"><span data-stu-id="8e0be-106">Percentage of net amount</span></span>
<span data-ttu-id="8e0be-107">A Porcentagem do método de cálculo de valor líquido é o valor padrão no campo Origem.</span><span class="sxs-lookup"><span data-stu-id="8e0be-107">The Percentage of net amount calculation method is the default value in the Origin field.</span></span> <span data-ttu-id="8e0be-108">O imposto é calculado como uma porcentagem do valor de compra ou de venda, excluindo todos os demais impostos.</span><span class="sxs-lookup"><span data-stu-id="8e0be-108">The sales tax is calculated as a percentage of the purchase or sales amount, excluding any other sales taxes.</span></span>
### <a name="example"></a><span data-ttu-id="8e0be-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8e0be-109">Example</span></span>

<span data-ttu-id="8e0be-110">A taxa do imposto é de 25%.</span><span class="sxs-lookup"><span data-stu-id="8e0be-110">The tax rate is 25%.</span></span> <span data-ttu-id="8e0be-111">A linha da fatura mostra uma quantidade de 10 itens a 1,00 cada, e o cliente pode ter um desconto de linha de 10%.</span><span class="sxs-lookup"><span data-stu-id="8e0be-111">The invoice line shows a quantity of 10 items at 1.00 each, and the customer is allowed a 10% line discount.</span></span> <span data-ttu-id="8e0be-112">Valor líquido: (10 x 1,00) -10% = 9,00 Imposto: 9,00 x 25% = 2,25 Valor total: 9,00 + 2,25 = 11,25</span><span class="sxs-lookup"><span data-stu-id="8e0be-112">Net amount: (10 x 1.00) -10% = 9.00 Sales tax: 9.00 x 25% = 2.25 Total amount: 9.00 + 2.25 = 11.25</span></span>

## <a name="percentage-of-gross-amount"></a><span data-ttu-id="8e0be-113">Porcentagem do valor bruto</span><span class="sxs-lookup"><span data-stu-id="8e0be-113">Percentage of gross amount</span></span>
<span data-ttu-id="8e0be-114">Se você selecionar o método Porcentagem do valor bruto, o imposto será calculado como uma porcentagem do valor das vendas brutas.</span><span class="sxs-lookup"><span data-stu-id="8e0be-114">If you select the Percentage of gross amount method, the sales tax is calculated as a percentage of the gross sales amount.</span></span> <span data-ttu-id="8e0be-115">O valor bruto é o valor líquido da linha mais todos os impostos e taxas da linha, com exceção de um imposto com Origem = Porcentagem do valor bruto.</span><span class="sxs-lookup"><span data-stu-id="8e0be-115">The gross amount is the line net amount plus all taxes and fees for the line except the one tax with Origin = Percentage of gross amount.</span></span>
### <a name="example"></a><span data-ttu-id="8e0be-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8e0be-116">Example</span></span>

<span data-ttu-id="8e0be-117">A autoridade de imposto impôs impostos especiais sobre um item.</span><span class="sxs-lookup"><span data-stu-id="8e0be-117">The tax authority has imposed special duties on an item.</span></span> <span data-ttu-id="8e0be-118">Os valores do imposto são adicionados ao valor líquido antes do cálculo do imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="8e0be-118">The duty amounts are added to the net amount before sales tax is calculated.</span></span> <span data-ttu-id="8e0be-119">Determinado os seguintes códigos de imposto:</span><span class="sxs-lookup"><span data-stu-id="8e0be-119">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="8e0be-120">IMPOSTO 1 = 10%, usando o método de cálculo Porcentagem do valor líquido</span><span class="sxs-lookup"><span data-stu-id="8e0be-120">DUTY 1 = 10%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="8e0be-121">IMPOSTO 2 = 20%, usando o método de cálculo Porcentagem do valor líquido</span><span class="sxs-lookup"><span data-stu-id="8e0be-121">DUTY 2 = 20%, using the Percentage of net amount calculation method</span></span>
-   <span data-ttu-id="8e0be-122">IMPOSTO = 25%, usando o método de cálculo Porcentagem do valor bruto</span><span class="sxs-lookup"><span data-stu-id="8e0be-122">SALESTAX = 25%, using the Percentage of gross amount calculation method</span></span>

<span data-ttu-id="8e0be-123">Se o valor líquido for 10,00, o IMPOSTO 1 será 1,00 (10,00 x 10%) e o IMPOSTO 2 = 2,00 (10,00 x 20%).</span><span class="sxs-lookup"><span data-stu-id="8e0be-123">If the net amount is 10.00, then DUTY 1 is 1.00 (10.00 x 10%) and DUTY 2 = 2.00 (10.00 x 20%).</span></span> <span data-ttu-id="8e0be-124">Os valores seriam da seguinte maneira: Valor bruto: Valor líquido + valor do IMPOSTO 1 + valor do IMPOSTO 2 (10,00 + 1,00 + 2,00) = 13,00 IMPOSTO = 13,00 x 25% = 3,25 Total de IMPOSTOS: 1,00 + 2,00 + 3,25 = 6,25 Valores totais: 10,00 + 6,25 = 16,25</span><span class="sxs-lookup"><span data-stu-id="8e0be-124">The amounts would be as follows: Gross amount: Net amount + DUTY 1 amount + DUTY 2 amount (10.00 + 1.00 + 2.00) = 13.00 SALESTAX = 13.00 x 25% = 3.25 Total DUTIES and SALESTAX: 1.00 + 2.00 + 3.25 = 6.25 Total amount: 10.00 + 6.25 = 16.25</span></span>

| <span data-ttu-id="8e0be-125">**Nota**</span><span class="sxs-lookup"><span data-stu-id="8e0be-125">**Note**</span></span>                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8e0be-126">Somente um código de imposto a Origem = Porcentagem do valor bruto pode ser usado para uma transação.</span><span class="sxs-lookup"><span data-stu-id="8e0be-126">Only one tax code with Origin = Percentage of gross amount can be used for a transaction.</span></span> <span data-ttu-id="8e0be-127">Se mais de um código de imposto for determinado por uma transação será exibido um erro informando que os impostos não podem ser calculados.</span><span class="sxs-lookup"><span data-stu-id="8e0be-127">If more than one such tax code is determined for a transaction an error will be displayed that sales tax cannot be calculated.</span></span> |


<a name="percentage-of-sales-tax"></a><span data-ttu-id="8e0be-128">Porcentagem do imposto</span><span class="sxs-lookup"><span data-stu-id="8e0be-128">Percentage of sales tax</span></span>
-----------------------

<span data-ttu-id="8e0be-129">Quando você selecionar Porcentagem de imposto no campo Origem, o imposto é calculado como uma porcentagem do imposto selecionado no campo Imposto de imposto.</span><span class="sxs-lookup"><span data-stu-id="8e0be-129">When you select Percentage of sales tax in the Origin field, sales tax is calculated as a percentage of the sales tax that is selected in the Sales tax on sales tax field.</span></span> <span data-ttu-id="8e0be-130">O imposto selecionado no campo Imposto de imposto é calculado primeiro.</span><span class="sxs-lookup"><span data-stu-id="8e0be-130">The sales tax that is selected in the Sales tax on sales tax field is calculated first.</span></span> <span data-ttu-id="8e0be-131">Em seguida, o segundo imposto sobre vendas é calculado com base no valor do primeiro imposto sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="8e0be-131">The second sales tax is then calculated based on the first sales tax amount.</span></span>
### <a name="example"></a><span data-ttu-id="8e0be-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8e0be-132">Example</span></span>

<span data-ttu-id="8e0be-133">Determinado os seguintes códigos de imposto:</span><span class="sxs-lookup"><span data-stu-id="8e0be-133">Given the following sales tax codes:</span></span>
-   <span data-ttu-id="8e0be-134">IMPOSTO 1 = 10%, usando o método de Porcentagem do valor líquido</span><span class="sxs-lookup"><span data-stu-id="8e0be-134">DUTY 1 = 10%, using the Percentage of net amount method</span></span>
-   <span data-ttu-id="8e0be-135">DIREITOS 2 = 20%, usando a Porcentagem do método de imposto, com Imposto 1 no campo Imposto do imposto</span><span class="sxs-lookup"><span data-stu-id="8e0be-135">DUTY 2 = 20%, using the Percentage of sales tax method, with Duty 1 in the Sales tax on sales tax field</span></span>
-   <span data-ttu-id="8e0be-136">IMPOSTO = 25%, usando o método Porcentagem do valor bruto</span><span class="sxs-lookup"><span data-stu-id="8e0be-136">SALESTAX = 25%, using the Percentage of gross amount method</span></span>

<span data-ttu-id="8e0be-137">Valor líquido: 10,00 IMPOSTO 1: 10,00 x 10% = 1,00 IMPOSTO 2: 1,00 x 20% = 0,20 Valor bruto: 10,00 + 1,00 + 0,20 = 11,20 IMPOSTO: 11,20 x 25% = 2,80 Total de IMPOSTOS: 1,00 + 0,20 + 2,80 = 4,00 Valor total: 10,00 + 4,00 = 14,00</span><span class="sxs-lookup"><span data-stu-id="8e0be-137">Net amount: 10.00 DUTY 1: 10.00 x 10% = 1.00 DUTY 2: 1.00 x 20% = 0.20 Gross amount: 10.00 + 1.00 + 0.20 = 11.20 SALESTAX: 11.20 x 25% = 2.80 Total DUTIES and SALESTAX: 1.00 + 0.20 + 2.80 = 4.00 Total amount: 10.00 + 4.00 = 14.00</span></span>

| <span data-ttu-id="8e0be-138">**Nota**</span><span class="sxs-lookup"><span data-stu-id="8e0be-138">**Note**</span></span>                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8e0be-139">Os impostos de vários níveis nos cálculos de impostos não são possíveis.</span><span class="sxs-lookup"><span data-stu-id="8e0be-139">Multilevel tax on tax calculations are not possible.</span></span> <span data-ttu-id="8e0be-140">Um imposto não pode ser calculado com base em um imposto que já tenha sido calculado com base em outro imposto.</span><span class="sxs-lookup"><span data-stu-id="8e0be-140">A tax cannot be calculated based on a tax which already is calculated based on another tax.</span></span> <span data-ttu-id="8e0be-141">Os vários impostos de nível único sobre códigos de imposto podem ser calculados em uma transação.</span><span class="sxs-lookup"><span data-stu-id="8e0be-141">Multiple single level tax on tax codes can be calculated on a transaction.</span></span> |

## <a name="amount-per-unit"></a><span data-ttu-id="8e0be-142">Valor por unidade</span><span class="sxs-lookup"><span data-stu-id="8e0be-142">Amount per unit</span></span>
<span data-ttu-id="8e0be-143">Quando você seleciona Valor por unidade no campo Origem, o imposto é calculado como um valor fixo por unidade multiplicado pela quantidade inserida na linha do documento.</span><span class="sxs-lookup"><span data-stu-id="8e0be-143">When you select Amount per unit in the Origin field, sales tax is calculated as a fixed amount per unit multiplied with the quantity entered on the document line.</span></span> <span data-ttu-id="8e0be-144">Uma unidade é selecionada no campo Unidade.</span><span class="sxs-lookup"><span data-stu-id="8e0be-144">A unit has to be selected in the Unit field.</span></span> <span data-ttu-id="8e0be-145">O valor por unidade é especificado na página Valores do código de imposto.</span><span class="sxs-lookup"><span data-stu-id="8e0be-145">The amount per unit is specified in the Sales tax code values page.</span></span>
### <a name="example"></a><span data-ttu-id="8e0be-146">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8e0be-146">Example</span></span>

<span data-ttu-id="8e0be-147">O código do imposto é configurado como: R$ 1,20 por unidade = caixa Em uma linha do imposto 25 caixas de um item são vendidas O imposto é calculado como 25 x 1,20 = 30,00</span><span class="sxs-lookup"><span data-stu-id="8e0be-147">Sales tax code is set up as: USD 1.20 per unit = box On a sales invoice line 25 boxes of an item are sold Sales tax is calculated as 25 x 1.20 = 30.00</span></span>

| <span data-ttu-id="8e0be-148">**Nota**</span><span class="sxs-lookup"><span data-stu-id="8e0be-148">**Note**</span></span>                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8e0be-149">Se a transação for inserida na unidade diferente da especificada no código do imposto, ela será convertida automaticamente com base nas conversões de unidade que são configuradas na página Conversões de unidade.</span><span class="sxs-lookup"><span data-stu-id="8e0be-149">If the transaction is entered in different unit than the unit specified on the sales tax code, it is converted automatically based on the unit conversions that are set up in the Unit conversions page.</span></span> |

###  <a name="amount-per-unit-additional-option"></a><span data-ttu-id="8e0be-150">Valor por unidade, opção adicional</span><span class="sxs-lookup"><span data-stu-id="8e0be-150">Amount per unit, additional option</span></span>

<span data-ttu-id="8e0be-151">Na guia Cálculo, você pode selecionar se um valor por imposto calculado da unidade é calculado antes de outros códigos de imposto e adicionado ao valor líquido antes que outros códigos de imposto com a Origem = Porcentagem do valor líquido sejam calculados.</span><span class="sxs-lookup"><span data-stu-id="8e0be-151">On the Calculation tab, you can select whether an amount per unit calculated tax is calculated before other tax codes and added to the net amount before other tax codes with Origin = Percentage of net amount are calculated.</span></span>

### <a name="examples"></a><span data-ttu-id="8e0be-152">Exemplos</span><span class="sxs-lookup"><span data-stu-id="8e0be-152">Examples</span></span>

<span data-ttu-id="8e0be-153">Suponha que calculamos 2 códigos de imposto em uma transação:</span><span class="sxs-lookup"><span data-stu-id="8e0be-153">Assume we calculate 2 tax codes on a transaction:</span></span>

-   <span data-ttu-id="8e0be-154">IMPOSTO: Origem = Valor por unidade e um imposto, o valor é definido como 5,00 por unidade = peças</span><span class="sxs-lookup"><span data-stu-id="8e0be-154">DUTY: Origin = Amount per unit and a sales tax, the value is set to 5.00 per unit = pcs</span></span>
-   <span data-ttu-id="8e0be-155">IMPOSTO: Origem = como mostrado nos os exemplos abaixo, o valor é definido como 25%</span><span class="sxs-lookup"><span data-stu-id="8e0be-155">SALESTAX: Origin = as shown in the examples below, the value is set to 25%</span></span>

<span data-ttu-id="8e0be-156">Vendemos 1 peça de um item ao preço unitário de 10,00</span><span class="sxs-lookup"><span data-stu-id="8e0be-156">We sell 1 piece of an item at a unit price of 10.00</span></span>
#### <a name="example-1"></a><span data-ttu-id="8e0be-157">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="8e0be-157">Example 1</span></span>

<span data-ttu-id="8e0be-158">IMPOSTO: Origem = Método Porcentagem do valor bruto A opção Calcular antes do imposto não tem efeito porque o IMPOSTO é calculado como uma porcentagem do valor bruto.</span><span class="sxs-lookup"><span data-stu-id="8e0be-158">SALESTAX: Origin = Percentage of gross amount method The Calculate before sales tax option has no effect, because SALESTAX is calculated as a percentage of the gross amount.</span></span> <span data-ttu-id="8e0be-159">IMPOSTO: 1 x 5,00 = 5,00 Valor bruto: 10,00 + 5,00 = 15,00 IMPOSTO: 15,00 x 25% = 3,75 Total do imposto: 5,00 + 3,75 = 8,75 Valor total: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="8e0be-159">DUTY: 1 x 5.00 = 5.00 Gross amount: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-2"></a><span data-ttu-id="8e0be-160">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="8e0be-160">Example 2</span></span>

<span data-ttu-id="8e0be-161">IMPOSTO: Origem = Porcentagem do valor líquido A opção Calcular antes do imposto não é selecionada para cálculo do IMPOSTO.</span><span class="sxs-lookup"><span data-stu-id="8e0be-161">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is not selected for the DUTY calculation.</span></span> <span data-ttu-id="8e0be-162">Valor líquido: 10,00 IMPOSTO: 1 x 5,00 = 5,00 IMPOSTO: 10,00 x 25% = 2,50 Total de imposto: 5,00 + 2,50 = 7,50 Valor total: 10,00 + 7,50 = 17,50</span><span class="sxs-lookup"><span data-stu-id="8e0be-162">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: 10.00 x 25% = 2.50 Total sales tax: 5.00 + 2.50 = 7.50 Total amount: 10.00 + 7.50 = 17.50</span></span>

#### <a name="example-3"></a><span data-ttu-id="8e0be-163">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="8e0be-163">Example 3</span></span>

<span data-ttu-id="8e0be-164">IMPOSTO: Origem = Porcentagem do valor líquido A opção Calcular antes do imposto não é selecionada para cálculo do IMPOSTO.</span><span class="sxs-lookup"><span data-stu-id="8e0be-164">SALESTAX: Origin = Percentage of net amount The Calculate before sales tax option is selected for the DUTY calculation.</span></span> <span data-ttu-id="8e0be-165">Valor líquido: 10,00 DUTY: 1 x 5,00 = 5,00 IMPOSTO: (10,00 + 5,00) x 25% = 3,75 Imposto total: 5,00 + 3,75 = 8,75 Valor total: 10,00 + 8,75 = 18,75</span><span class="sxs-lookup"><span data-stu-id="8e0be-165">Net amount: 10.00 DUTY: 1 x 5.00 = 5.00 SALESTAX: (10.00 + 5.00) x 25% = 3.75 Total sales tax: 5.00 + 3.75 = 8.75 Total amount: 10.00 + 8.75 = 18.75</span></span>

#### <a name="example-4"></a><span data-ttu-id="8e0be-166">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="8e0be-166">Example 4</span></span>

<span data-ttu-id="8e0be-167">O resultado dos exemplos 1 e 3 são iguais porque só há um imposto.</span><span class="sxs-lookup"><span data-stu-id="8e0be-167">The result of Example 3 and Example 1 is the same, because there is only one duty.</span></span> <span data-ttu-id="8e0be-168">Suponha que você tenha dois IMPOSTOS e somente um deles esteja incluído no valor líquido para o cálculo do imposto sobre vendas: IMPOSTO 1: 5,00, usando o método de Valor por unidade, e a opção Calcular antes do imposto é selecionada IMPOSTO 2: 2.50, usando o método Valor por unidade e a opção Calcular antes do imposto selecionado Imposto: 25%, usando o método Porcentagem do valor líquido Valor líquido: 10,00 IMPOSTO 1: 1 x 5,00 = 5,00 IMPOSTO 2: 1 x 2,50 = 2,50 Valor líquido sujeito ao imposto: 10,00 + 5,00 = 15,00 IMPOSTO: 15,00 x 25% = 3,75 Imposto total, incluindo imposto: 5,00 + 2,50 + 3,75 = 11,25 Valor total: 10,00 + 11,25 = 21,25 O IMPOSTO de 25% é calculado para a soma do valor líquido (10,00) + IMPOSTO 1 (5,00) = 15,00.</span><span class="sxs-lookup"><span data-stu-id="8e0be-168">Assume that you have two DUTIES, and only one of them is included in the net amount for the sales tax calculation: DUTY 1: 5.00, using the Amount per unit method, and the Calculate before sales tax option is selected DUTY 2: 2.50, using the Amount per unit method, and the Calculate before sales tax option is not selected Sales tax: 25%, using the Percentage of net amount method Net amount: 10.00 DUTY 1: 1 x 5.00 = 5.00 DUTY 2: 1 x 2.50 = 2.50 Net amount subject to sales tax: 10.00 + 5.00 = 15.00 SALESTAX: 15.00 x 25% = 3.75 Total sales taxes, including duties: 5.00 + 2.50 + 3.75 = 11.25 Total amount: 10.00 + 11.25 = 21.25 The 25% SALESTAX is calculated for the sum of the net amount (10.00) + DUTY 1 (5.00) = 15.00.</span></span> <span data-ttu-id="8e0be-169">IMPOSTO 2 é adicionado ao valor do imposto após o cálculo do imposto ser calculado.</span><span class="sxs-lookup"><span data-stu-id="8e0be-169">DUTY 2 is added to the tax amount after the sales tax is calculated.</span></span>

## <a name="calculated-percentage-of-net-amount"></a><span data-ttu-id="8e0be-170">Porcentagem do valor líquido calculada</span><span class="sxs-lookup"><span data-stu-id="8e0be-170">Calculated percentage of net amount</span></span>
<span data-ttu-id="8e0be-171">A Porcentagem calculada do valor líquido trata o cálculo do imposto de forma diferente, dependendo da configuração do parâmetro Os valores incluem imposto do documento ou do diário.</span><span class="sxs-lookup"><span data-stu-id="8e0be-171">The Calculated percentage of net amount handles tax calculation differently depending on the setting of the Amounts include sales tax parameter for the document or journal.</span></span>
### <a name="example-1"></a><span data-ttu-id="8e0be-172">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="8e0be-172">Example 1</span></span>

<span data-ttu-id="8e0be-173">O documento/diário é definido para Os valores incluem imposto = Sim Valor da linha da transação: 10,00 Taxa do imposto: 25% Imposto: Valor da linha de transação x Taxa do imposto (10,00 x 25%) = 2,50 Valor base do imposto (valor de origem): Valor da linha da transação - Imposto (10,00 - 2,50) = 7,50</span><span class="sxs-lookup"><span data-stu-id="8e0be-173">Document / journal is set to Amounts include sales tax = Yes Transaction line amount: 10.00 Tax rate: 25% Sales tax: Transaction line amount x tax rate (10.00 x 25%) = 2.50 Tax base amount (origin amount): Transaction line amount - Sales tax (10.00 - 2.50) = 7.50</span></span>

### <a name="example-2"></a><span data-ttu-id="8e0be-174">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="8e0be-174">Example 2</span></span>

<span data-ttu-id="8e0be-175">O documento/diário é definido para Os valores incluem imposto = Não Valor da linha da transação: 10,00 Taxa do imposto: 25% Imposto: (Valor da linha de transação x Taxa do imposto) / (100 - taxa do imposto) (10,00 x 25%) / (100% - 25%) = 3,33 Valor base do imposto (valor do origem): Valor da linha da transação = 10.00</span><span class="sxs-lookup"><span data-stu-id="8e0be-175">Document / journal is set to Amounts include sales tax = No Transaction line amount: 10.00 Tax rate: 25% Sales tax: (Transaction line amount x tax rate) / (100 - tax rate) (10.00 x 25%) / (100% - 25%) = 3.33 Tax base amount (origin amount): Transaction line amount = 10.00</span></span>



<a name="additional-resources"></a><span data-ttu-id="8e0be-176">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8e0be-176">Additional resources</span></span>
--------

[<span data-ttu-id="8e0be-177">Determinando as alíquotas de imposto com base nos campos Base marginal e Métodos de cálculo</span><span class="sxs-lookup"><span data-stu-id="8e0be-177">Sales tax rates based on the Marginal base and Calculation methods</span></span>](marginal-base-field.md)

[<span data-ttu-id="8e0be-178">Opções de cálculo do valor total e do intervalo para códigos de impostos</span><span class="sxs-lookup"><span data-stu-id="8e0be-178">Whole amount and Interval calculation options for sales tax codes</span></span>](whole-amount-interval-options-sales-tax-codes.md)



