---
title: Configurar taxas de juros para um código de juros
description: Os códigos de juros contêm configurações que determinam quando os juros são cobrados e como são calculados em contas vencidas.
author: ShivamPandey-msft
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Interest
audience: Application User
ms.reviewer: roschlom
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc986ea752d1482f618401058f7a0b18f13efd5f
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188701"
---
# <a name="set-up-interest-rates-for-an-interest-code"></a><span data-ttu-id="34d9b-103">Configurar taxas de juros para um código de juros</span><span class="sxs-lookup"><span data-stu-id="34d9b-103">Set up interest rates for an interest code</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34d9b-104">Os códigos de juros contêm configurações que determinam quando os juros são cobrados e como são calculados em contas vencidas.</span><span class="sxs-lookup"><span data-stu-id="34d9b-104">Interest codes contain settings that determine when interest is charged and how it is calculated on overdue accounts.</span></span>

<span data-ttu-id="34d9b-105">Você pode configurar um único código de juros e aplicá-lo a vários perfis de lançamentos do cliente, códigos de cobrança ou às linhas da fatura específicas.</span><span class="sxs-lookup"><span data-stu-id="34d9b-105">You can set up a single interest code and apply it to multiple customer posting profiles, billing codes, or to specific invoice lines.</span></span> <span data-ttu-id="34d9b-106">Quando os detalhes do código de juros são alterados, todos os recursos que usam o código implementarão automaticamente as alterações nas novas transações.</span><span class="sxs-lookup"><span data-stu-id="34d9b-106">When the interest code details are changed, all features that use the code will automatically implement the changes on new transactions.</span></span> <span data-ttu-id="34d9b-107">Para cada código de juros, você pode configurar dois tipos de taxas:</span><span class="sxs-lookup"><span data-stu-id="34d9b-107">For each interest code, you can set up two types of rates:</span></span>
-   <span data-ttu-id="34d9b-108">Taxas para ganhos de juros − Representam a receita recebida pela alteração de juros em faturas ou notas de juros.</span><span class="sxs-lookup"><span data-stu-id="34d9b-108">Rates for interest earnings − These represent revenue that is earned by charging interest on invoices or interest notes.</span></span>
-   <span data-ttu-id="34d9b-109">Pagamentos de taxas de juros - Representam um custo pago por jutos sobre notas de crédito.</span><span class="sxs-lookup"><span data-stu-id="34d9b-109">Rates for interest payments − These represent a cost that is paid for interest on credit notes.</span></span>

<span data-ttu-id="34d9b-110">Ambas as taxas podem existir ao mesmo tempo e no mesmo código de juros.</span><span class="sxs-lookup"><span data-stu-id="34d9b-110">Both of these rate types can exist at the same time and in the same interest code.</span></span> <span data-ttu-id="34d9b-111">As taxas de juros podem ser baseadas em três tipos de cálculo:</span><span class="sxs-lookup"><span data-stu-id="34d9b-111">Interest rates can be based on three calculation types:</span></span>
-   <span data-ttu-id="34d9b-112">Juros por porcentagem.</span><span class="sxs-lookup"><span data-stu-id="34d9b-112">Interest by percentage.</span></span>
-   <span data-ttu-id="34d9b-113">Juros por valor.</span><span class="sxs-lookup"><span data-stu-id="34d9b-113">Interest by amount.</span></span>
-   <span data-ttu-id="34d9b-114">Juros pelo intervalo, o que resulta em uma única porcentagem ou valor.</span><span class="sxs-lookup"><span data-stu-id="34d9b-114">Interest by range, which results in a single percentage or amount.</span></span>

<span data-ttu-id="34d9b-115">Quando um código de juros é usado para calcular os juros, uma nota de juros separada é criada para cada taxa de juros em vigor durante o período em que o pagamento tiver excedido a data de vencimento da transação.</span><span class="sxs-lookup"><span data-stu-id="34d9b-115">When an interest code is used to calculate interest, a separate interest note is created for each interest rate that is in effect during the time that the payment has exceeded the transaction due date.</span></span> <span data-ttu-id="34d9b-116">Use a guia **Ganhos** na página **Código de juros** para configurar taxas de juros para os juros que você ganha ao cobrar juros.</span><span class="sxs-lookup"><span data-stu-id="34d9b-116">You use the **Earnings** tab on the **Interest code** page to set up interest rates for interest that you earn by charging interest.</span></span> <span data-ttu-id="34d9b-117">Use a guia **Pagamentos** para configurar as taxas de juros para os juros que você paga.</span><span class="sxs-lookup"><span data-stu-id="34d9b-117">Use the **Payments** tab to set up interest rates for interest that you pay.</span></span>

## <a name="interest-rates-based-on-a-percentage"></a><span data-ttu-id="34d9b-118">Taxas de juros com base em um porcentagem</span><span class="sxs-lookup"><span data-stu-id="34d9b-118">Interest rates based on a percentage</span></span>
<span data-ttu-id="34d9b-119">Você pode configurar taxas de juros para calcular um percentual especificado.</span><span class="sxs-lookup"><span data-stu-id="34d9b-119">You can set up interest rates that calculate a specified percentage.</span></span>

- <span data-ttu-id="34d9b-120">O valor dos juros se aplica a todas as moedas.</span><span class="sxs-lookup"><span data-stu-id="34d9b-120">Interest amount applies to all currencies.</span></span>
- <span data-ttu-id="34d9b-121">Os limites do valor de juros opcional podem ser inseridos.</span><span class="sxs-lookup"><span data-stu-id="34d9b-121">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="34d9b-122">**Porcentagem** é selecionado no campo **Calcular juros com base em** na página **Configurar Códigos de juros**.</span><span class="sxs-lookup"><span data-stu-id="34d9b-122">**Percentage** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="34d9b-123">Por exemplo, para configurar um código de juros que avalie 5% de juros para cada dois meses, se o pagamento da fatura exceder a data de vencimento da transação, digite 2 no campo **Calcular juros a cada** e selecione **Mês**.</span><span class="sxs-lookup"><span data-stu-id="34d9b-123">For example, to set up an interest code that assesses 5 percent interest for every two months that the invoice payment exceeds the transaction due date, you would enter 2 in the **Calculate interest every** field and select **Month**.</span></span>

> [!NOTE] 
> <span data-ttu-id="34d9b-124">O novo algoritmo para o cálculo da nota de juros é adicionado usando o gerenciamento de Recursos.</span><span class="sxs-lookup"><span data-stu-id="34d9b-124">The new algorithm for interest note calculation is added using Feature management.</span></span> <span data-ttu-id="34d9b-125">Para usar esse algoritmo, habilite o recurso **(GBL) Permitir calcular juros por dia como porcentagem anual dividida por 365**.</span><span class="sxs-lookup"><span data-stu-id="34d9b-125">To use this algorithm, enable the **(GBL) Allow to calculate interest per day as yearly percent divided by 365** feature.</span></span> <span data-ttu-id="34d9b-126">Para obter mais informações sobre como habilitar os recursos, consulte [Visão geral do gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="34d9b-126">For information about how to enable the feature, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
> 
> <span data-ttu-id="34d9b-127">A fórmula para o cálculo do valor da nota de juros é:</span><span class="sxs-lookup"><span data-stu-id="34d9b-127">The formula for the calculation for the interest note amount is:</span></span> 
>  
> <span data-ttu-id="34d9b-128">Valor da nota de juros = valor devido \* juros anuais % / 365 \* número de dias de atraso</span><span class="sxs-lookup"><span data-stu-id="34d9b-128">Interest note amount = Amount owed \* Yearly interest % / 365 \* Number of days late</span></span>
>  
> <span data-ttu-id="34d9b-129">Este recurso está disponível na versão 10.0.18 e posterior.</span><span class="sxs-lookup"><span data-stu-id="34d9b-129">This feature is available in version 10.0.18 or later.</span></span>    
 
## <a name="interest-rates-based-on-amounts"></a><span data-ttu-id="34d9b-130">Taxas de juros baseadas em valores</span><span class="sxs-lookup"><span data-stu-id="34d9b-130">Interest rates based on amounts</span></span>
<span data-ttu-id="34d9b-131">Você pode configurar taxas de juros que calculam um valor por moeda específico.</span><span class="sxs-lookup"><span data-stu-id="34d9b-131">You can set up interest rates that calculate a specified amount per currency.</span></span>
- <span data-ttu-id="34d9b-132">Um valor de juros é especificado para cada moeda no código de juros.</span><span class="sxs-lookup"><span data-stu-id="34d9b-132">An interest amount is specified for each currency in the interest code.</span></span>
- <span data-ttu-id="34d9b-133">Os limites do valor de juros opcional podem ser inseridos.</span><span class="sxs-lookup"><span data-stu-id="34d9b-133">Optional interest amount limits can be entered.</span></span>
- <span data-ttu-id="34d9b-134">**Valor** é selecionado no campo **Calcular juros com base em** na página **Configurar códigos de juros**.</span><span class="sxs-lookup"><span data-stu-id="34d9b-134">**Amount** is selected in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

<span data-ttu-id="34d9b-135">Por exemplo, para configurar um código de juros que avalie juros de 25,00 para cada 20 dias que o pagamento da fatura excede a data de vencimento da transação, insira 20 no campo **Calcular juros a cada** e selecione **Dia**.</span><span class="sxs-lookup"><span data-stu-id="34d9b-135">For example, to set up an interest code that assesses interest of 25.00 for every 20 days that the invoice payment exceeds the transaction due date, you would enter 20 in the **Calculate interest every** field and select **Day**.</span></span>

## <a name="interest-rates-based-on-ranges"></a><span data-ttu-id="34d9b-136">Taxas de juros baseadas em intervalos</span><span class="sxs-lookup"><span data-stu-id="34d9b-136">Interest rates based on ranges</span></span>
<span data-ttu-id="34d9b-137">Você pode configurar taxas de juros que varia de acordo com o valor vencido, o número de dias ou de meses que o valor está atrasado.</span><span class="sxs-lookup"><span data-stu-id="34d9b-137">You can set up interest rates that vary depending on the overdue amount, the number of days that the amount is late, or the number of months that the amount is late.</span></span>
-   <span data-ttu-id="34d9b-138">Você pode usar a guia **Salário por moeda** para definir configurações específicas de juros para cada moeda.</span><span class="sxs-lookup"><span data-stu-id="34d9b-138">You can use the **Earnings by Currency** tab to define specific interest settings for each currency.</span></span> <span data-ttu-id="34d9b-139">Esse também é o local onde você definirá o intervalo.</span><span class="sxs-lookup"><span data-stu-id="34d9b-139">This is also where you will define the range.</span></span>
-   <span data-ttu-id="34d9b-140">Use o botão **Intervalos** para adicionar as linhas que representam os intervalos que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="34d9b-140">Use the **Ranges** button to add lines that represent the ranges that you want to set up.</span></span> <span data-ttu-id="34d9b-141">O valor **De** representa o início do intervalo e o número **Valor dos juros** representa uma porcentagem ou valor, dependendo da seleção no campo **Calcular juros com base em** da página **Configurar códigos de juros**.</span><span class="sxs-lookup"><span data-stu-id="34d9b-141">The **From** value represents the beginning of the range and the **Interest value** number represents either a percentage or an amount, depending on the selection in the **Calculate interest based on** field on the **Set up Interest codes** page.</span></span>

## <a name="example-1-interest-by-range--amount"></a><span data-ttu-id="34d9b-142">Exemplo 1: Juros por intervalo = valor</span><span class="sxs-lookup"><span data-stu-id="34d9b-142">Example 1: Interest by range = Amount</span></span>
<span data-ttu-id="34d9b-143">Você configura um código de juros que avalia juros uma vez a cada três meses que o pagamento da fatura ultrapassar a data de vencimento da transação.</span><span class="sxs-lookup"><span data-stu-id="34d9b-143">You set up an interest code that assesses interest one time for every three months that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="34d9b-144">Você deseja basear o cálculo de um valor dos juros em porcentagem, de acordo com o valor de nível dos intervalos.</span><span class="sxs-lookup"><span data-stu-id="34d9b-144">You want to base the calculation on a percentage interest value, according to stepped amount intervals.</span></span> <span data-ttu-id="34d9b-145">O valor dos juros será 1 por cento para valores da fatura de até 1.000,00, 2 por cento para valores de 1.001,00 para 5.000,00, e 3 por cento para os valores superiores a 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="34d9b-145">The interest value will be 1 percent for invoice amounts up to 1,000.00, 2 percent for amounts from 1,001.00 to 5,000.00, and 3 percent for amounts larger than 5,000.00.</span></span> <span data-ttu-id="34d9b-146">Configure os valores do campo código de juros como a seguir.</span><span class="sxs-lookup"><span data-stu-id="34d9b-146">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="34d9b-147">**Nome do campo**</span><span class="sxs-lookup"><span data-stu-id="34d9b-147">**Field name**</span></span>                  | <span data-ttu-id="34d9b-148">**Valor do campo**</span><span class="sxs-lookup"><span data-stu-id="34d9b-148">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="34d9b-149">**Código de juros**</span><span class="sxs-lookup"><span data-stu-id="34d9b-149">**Interest code**</span></span>               | <span data-ttu-id="34d9b-150">3M%ByAmt</span><span class="sxs-lookup"><span data-stu-id="34d9b-150">3M%ByAmt</span></span>        |
| <span data-ttu-id="34d9b-151">**Calcular juros a cada**</span><span class="sxs-lookup"><span data-stu-id="34d9b-151">**Calculate interest every**</span></span>    | <span data-ttu-id="34d9b-152">3/Mês</span><span class="sxs-lookup"><span data-stu-id="34d9b-152">3/Month</span></span>         |
| <span data-ttu-id="34d9b-153">**Juros por intervalo**</span><span class="sxs-lookup"><span data-stu-id="34d9b-153">**Interest by range**</span></span>           | <span data-ttu-id="34d9b-154">Valor</span><span class="sxs-lookup"><span data-stu-id="34d9b-154">Amount</span></span>          |
| <span data-ttu-id="34d9b-155">**Calcular juros baseados em**</span><span class="sxs-lookup"><span data-stu-id="34d9b-155">**Calculate interest based on**</span></span> | <span data-ttu-id="34d9b-156">Porcentagem</span><span class="sxs-lookup"><span data-stu-id="34d9b-156">Percentage</span></span>      |

<span data-ttu-id="34d9b-157">Configure as informações do intervalo conforme as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="34d9b-157">You set up the range information as follows.</span></span>

| <span data-ttu-id="34d9b-158">**Do valor**</span><span class="sxs-lookup"><span data-stu-id="34d9b-158">**From value**</span></span> | <span data-ttu-id="34d9b-159">**Valor dos juros**</span><span class="sxs-lookup"><span data-stu-id="34d9b-159">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="34d9b-160">0</span><span class="sxs-lookup"><span data-stu-id="34d9b-160">0</span></span>              | <span data-ttu-id="34d9b-161">1</span><span class="sxs-lookup"><span data-stu-id="34d9b-161">1</span></span>                  |
| <span data-ttu-id="34d9b-162">1,001</span><span class="sxs-lookup"><span data-stu-id="34d9b-162">1,001</span></span>          | <span data-ttu-id="34d9b-163">2</span><span class="sxs-lookup"><span data-stu-id="34d9b-163">2</span></span>                  |
| <span data-ttu-id="34d9b-164">5,001</span><span class="sxs-lookup"><span data-stu-id="34d9b-164">5,001</span></span>          | <span data-ttu-id="34d9b-165">3</span><span class="sxs-lookup"><span data-stu-id="34d9b-165">3</span></span>                  |


## <a name="example-2-interest-by-range--days"></a><span data-ttu-id="34d9b-166">Exemplo 2: Juros por intervalo = Dias</span><span class="sxs-lookup"><span data-stu-id="34d9b-166">Example 2: Interest by range = Days</span></span>

<span data-ttu-id="34d9b-167">Você configura um código de juros que avalia juros uma vez a cada 15 dias que o pagamento da fatura ultrapassar a data de vencimento da transação.</span><span class="sxs-lookup"><span data-stu-id="34d9b-167">You set up an interest code that assesses interest one time for every 15 days that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="34d9b-168">Você deseja basear o cálculo de um valor dos juros em valor, de acordo com os intervalos de dia de nível.</span><span class="sxs-lookup"><span data-stu-id="34d9b-168">You want to base the calculation on an amount interest value, according to stepped day intervals.</span></span> <span data-ttu-id="34d9b-169">O valor dos juros será 10,00 para 15 dias durante os primeiros 60 dias, 15,00 para 15 dias durante os dias 61 a 90 e 20,00 para 15 dias do dia 91 e os dias seguintes.</span><span class="sxs-lookup"><span data-stu-id="34d9b-169">The interest value will be 10.00 per 15 days during the first 60 days, 15.00 per 15 days during days 61 to 90, and 20.00 per 15 days from day 91 and after.</span></span> <span data-ttu-id="34d9b-170">Configure os valores do campo código de juros como a seguir.</span><span class="sxs-lookup"><span data-stu-id="34d9b-170">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="34d9b-171">**Nome do campo**</span><span class="sxs-lookup"><span data-stu-id="34d9b-171">**Field name**</span></span>                  | <span data-ttu-id="34d9b-172">**Valor do campo**</span><span class="sxs-lookup"><span data-stu-id="34d9b-172">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="34d9b-173">**Código de juros**</span><span class="sxs-lookup"><span data-stu-id="34d9b-173">**Interest code**</span></span>               | <span data-ttu-id="34d9b-174">15DAmtXDay</span><span class="sxs-lookup"><span data-stu-id="34d9b-174">15DAmtXDay</span></span>      |
| <span data-ttu-id="34d9b-175">**Calcular juros a cada**</span><span class="sxs-lookup"><span data-stu-id="34d9b-175">**Calculate interest every**</span></span>    | <span data-ttu-id="34d9b-176">15/Dia</span><span class="sxs-lookup"><span data-stu-id="34d9b-176">15/Day</span></span>          |
| <span data-ttu-id="34d9b-177">**Juros por intervalo**</span><span class="sxs-lookup"><span data-stu-id="34d9b-177">**Interest by range**</span></span>           | <span data-ttu-id="34d9b-178">Dias</span><span class="sxs-lookup"><span data-stu-id="34d9b-178">Days</span></span>            |
| <span data-ttu-id="34d9b-179">**Calcular juros baseados em**</span><span class="sxs-lookup"><span data-stu-id="34d9b-179">**Calculate interest based on**</span></span> | <span data-ttu-id="34d9b-180">Valor</span><span class="sxs-lookup"><span data-stu-id="34d9b-180">Amount</span></span>          |

<span data-ttu-id="34d9b-181">Configure as informações do intervalo conforme as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="34d9b-181">You set up the range information as follows.</span></span>

| <span data-ttu-id="34d9b-182">**Do valor**</span><span class="sxs-lookup"><span data-stu-id="34d9b-182">**From value**</span></span> | <span data-ttu-id="34d9b-183">**Valor dos juros**</span><span class="sxs-lookup"><span data-stu-id="34d9b-183">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="34d9b-184">0</span><span class="sxs-lookup"><span data-stu-id="34d9b-184">0</span></span>              | <span data-ttu-id="34d9b-185">10</span><span class="sxs-lookup"><span data-stu-id="34d9b-185">10</span></span>                 |
| <span data-ttu-id="34d9b-186">61</span><span class="sxs-lookup"><span data-stu-id="34d9b-186">61</span></span>             | <span data-ttu-id="34d9b-187">15</span><span class="sxs-lookup"><span data-stu-id="34d9b-187">15</span></span>                 |
| <span data-ttu-id="34d9b-188">91</span><span class="sxs-lookup"><span data-stu-id="34d9b-188">91</span></span>             | <span data-ttu-id="34d9b-189">20</span><span class="sxs-lookup"><span data-stu-id="34d9b-189">20</span></span>                 |


## <a name="example-3-interest-by-range--months"></a><span data-ttu-id="34d9b-190">Exemplo 3: Juros por intervalo = Meses</span><span class="sxs-lookup"><span data-stu-id="34d9b-190">Example 3: Interest by range = Months</span></span>

<span data-ttu-id="34d9b-191">Você configura um código de juros que avalia juros uma vez a cada mês que o pagamento da fatura ultrapassar a data de vencimento da transação.</span><span class="sxs-lookup"><span data-stu-id="34d9b-191">You set up an interest code that assesses interest one time for every month that the invoice payment exceeds the transaction due date.</span></span> <span data-ttu-id="34d9b-192">Você deseja basear o cálculo de um valor dos juros em porcentagem, de acordo com o mês de nível dos intervalos.</span><span class="sxs-lookup"><span data-stu-id="34d9b-192">You want to base the calculation on a percentage interest value, according to stepped month intervals.</span></span> <span data-ttu-id="34d9b-193">O valor dos juros será 1,5 por cento por mês para os três primeiros meses vencidos, 2,0 por cento por mês para os três meses seguintes, e 2,5 por cento por mês para cada mês além dos seis primeiros meses.</span><span class="sxs-lookup"><span data-stu-id="34d9b-193">The interest value will be 1.5 percent per month for the first three overdue months, 2.0 percent per month for the second three months, and 2.5 percent per month for each month beyond the first six months.</span></span> <span data-ttu-id="34d9b-194">Configure os valores do campo código de juros como a seguir.</span><span class="sxs-lookup"><span data-stu-id="34d9b-194">You set up the interest code field values as follows.</span></span>

| <span data-ttu-id="34d9b-195">**Nome do campo**</span><span class="sxs-lookup"><span data-stu-id="34d9b-195">**Field name**</span></span>                  | <span data-ttu-id="34d9b-196">**Valor do campo**</span><span class="sxs-lookup"><span data-stu-id="34d9b-196">**Field value**</span></span> |
|---------------------------------|-----------------|
| <span data-ttu-id="34d9b-197">**Código de juros**</span><span class="sxs-lookup"><span data-stu-id="34d9b-197">**Interest code**</span></span>               | <span data-ttu-id="34d9b-198">1M%ByMth</span><span class="sxs-lookup"><span data-stu-id="34d9b-198">1M%ByMth</span></span>        |
| <span data-ttu-id="34d9b-199">**Calcular juros a cada**</span><span class="sxs-lookup"><span data-stu-id="34d9b-199">**Calculate interest every**</span></span>    | <span data-ttu-id="34d9b-200">1/mês</span><span class="sxs-lookup"><span data-stu-id="34d9b-200">1/Month</span></span>         |
| <span data-ttu-id="34d9b-201">**Juros por intervalo**</span><span class="sxs-lookup"><span data-stu-id="34d9b-201">**Interest by range**</span></span>           | <span data-ttu-id="34d9b-202">Meses</span><span class="sxs-lookup"><span data-stu-id="34d9b-202">Months</span></span>          |
| <span data-ttu-id="34d9b-203">**Calcular juros baseados em**</span><span class="sxs-lookup"><span data-stu-id="34d9b-203">**Calculate interest based on**</span></span> | <span data-ttu-id="34d9b-204">Porcentagem</span><span class="sxs-lookup"><span data-stu-id="34d9b-204">Percentage</span></span>      |

<span data-ttu-id="34d9b-205">Configure as informações do intervalo conforme as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="34d9b-205">You set up the range information as follows.</span></span>

| <span data-ttu-id="34d9b-206">**Do valor**</span><span class="sxs-lookup"><span data-stu-id="34d9b-206">**From value**</span></span> | <span data-ttu-id="34d9b-207">**Valor dos juros**</span><span class="sxs-lookup"><span data-stu-id="34d9b-207">**Interest value**</span></span> |
|----------------|--------------------|
| <span data-ttu-id="34d9b-208">0</span><span class="sxs-lookup"><span data-stu-id="34d9b-208">0</span></span>              | <span data-ttu-id="34d9b-209">1.5</span><span class="sxs-lookup"><span data-stu-id="34d9b-209">1.5</span></span>                |
| <span data-ttu-id="34d9b-210">4</span><span class="sxs-lookup"><span data-stu-id="34d9b-210">4</span></span>              | <span data-ttu-id="34d9b-211">2</span><span class="sxs-lookup"><span data-stu-id="34d9b-211">2</span></span>                  |
| <span data-ttu-id="34d9b-212">7</span><span class="sxs-lookup"><span data-stu-id="34d9b-212">7</span></span>              | <span data-ttu-id="34d9b-213">2,5</span><span class="sxs-lookup"><span data-stu-id="34d9b-213">2.5</span></span>                |

## <a name="new-versions"></a><span data-ttu-id="34d9b-214">Novas versões</span><span class="sxs-lookup"><span data-stu-id="34d9b-214">New versions</span></span>
<span data-ttu-id="34d9b-215">Os códigos de juros possuem data efetiva.</span><span class="sxs-lookup"><span data-stu-id="34d9b-215">Interest codes are date effective.</span></span> <span data-ttu-id="34d9b-216">Se desejar alterar a taxa de juros, você pode criar uma **nova versão** que entrará em vigor a partir de uma data futura.</span><span class="sxs-lookup"><span data-stu-id="34d9b-216">If you want to modify the interest rate, you can create a **new version** that is effective as of a future date.</span></span>

<span data-ttu-id="34d9b-217">Para exibir versões diferentes, você pode usar a opção de menu **A partir da data** para selecionar a data de fechamento.</span><span class="sxs-lookup"><span data-stu-id="34d9b-217">To view different versions, you can use the **As of Date** menu choice to select the cutoff date.</span></span> <span data-ttu-id="34d9b-218">Você também pode selecionar **Exibir todos os registros** para exibir todos os códigos de juros na página.</span><span class="sxs-lookup"><span data-stu-id="34d9b-218">You can also select the **Display all records** to view all interest codes in the page.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
