---
title: Relatório de classificação por vencimento de clientes
description: O relatório Classificação por vencimento do cliente exibe os saldos devidos de clientes, classificados por intervalo de datas ou por período de classificação por vencimento.
author: JodiChristiansen
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f3a1bba4596c7b645c20a790a6cbe8725ab665d
ms.sourcegitcommit: e43aef72b7d65db1dcb014dfada5233ac051ba7c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2020
ms.locfileid: "4013044"
---
# <a name="customer-aging-report"></a><span data-ttu-id="7c3cd-103">Relatório de classificação por vencimento de clientes</span><span class="sxs-lookup"><span data-stu-id="7c3cd-103">Customer aging report</span></span> 

<span data-ttu-id="7c3cd-104">O relatório **Classificação por vencimento do cliente** exibe os saldos devidos de clientes, classificados por intervalo de datas ou por período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-104">The **Customer aging** report displays the balances that are due from customers, sorted by date interval, or aging period.</span></span>

<span data-ttu-id="7c3cd-105">Quando você gera o relatório, os seguintes parâmetros padrão serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-105">When you generate this report, the following default parameters are displayed.</span></span> <span data-ttu-id="7c3cd-106">Você pode usar esses parâmetros para filtrar os dados que são exibidos no relatório.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-106">You can use these parameters to filter the data that will be displayed on the report.</span></span> <span data-ttu-id="7c3cd-107">Para saber mais, consulte [Configurar coleções](set-up-collections.md).</span><span class="sxs-lookup"><span data-stu-id="7c3cd-107">For more information, see [Set up collections](set-up-collections.md).</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7c3cd-108">Campo</span><span class="sxs-lookup"><span data-stu-id="7c3cd-108">Field</span></span></p></th>
<th><p><span data-ttu-id="7c3cd-109">descrição</span><span class="sxs-lookup"><span data-stu-id="7c3cd-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c3cd-110"><strong>Classificação de cobrança</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-110"><strong>Billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-111">Selecione uma ou mais classificações de cobrança para incluir no relatório.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-111">Select one or more billing classifications to include on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="7c3cd-112">**Observação:** esse controle só estará disponível se a chave de configuração <STRONG>Setor Público</STRONG> estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-112">**Note:** This control is available only if the <STRONG>Public Sector</STRONG> configuration key is selected.</span></span></P>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c3cd-113"><strong>Incluir transações sem uma classificação de cobrança</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-113"><strong>Include transactions without a billing classification</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-114">Se essa caixa de seleção for marcada, todas as transações que não têm uma classificação de cobrança atribuída serão exibidas no relatório.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-114">If this check box is selected, all transactions that do not have a billing classification assigned to them will be displayed on the report.</span></span></p>
<div class="alert">

<span data-ttu-id="7c3cd-115">**Observação:** esse controle só estará disponível se a chave de configuração <STRONG>Setor Público</STRONG> estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-115">**Note:** This control is available only if the <STRONG>Public sector</STRONG> configuration key is selected.</span></span></P>

</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c3cd-116"><strong>Classificação por vencimento a partir de</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-116"><strong>Aging as of</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-117">Insira a data usada no bucket de classificação por vencimento atual.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-117">Enter the date used on the current aging bucket.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c3cd-118"><strong>Saldo a partir de</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-118"><strong>Balance as of</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-119">Insira a data para a qual deseja exibir os saldos do cliente.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-119">Enter the date to view the customer balances for.</span></span> <span data-ttu-id="7c3cd-120">Isso também é conhecido como data de fechamento para transações.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-120">This is also known as a cutoff date for transactions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c3cd-121"><strong>Data inicial:</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-121"><strong>Start date</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-122">Insira uma data que esteja no primeiro intervalo do período ou no período de classificação por vencimento para incluir no relatório.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-122">Enter a date that is in the first period interval or aging period to include on the report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c3cd-123"><strong>Critérios</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-123"><strong>Criteria</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-124">Selecione o tipo de data no qual basear o relatório.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-124">Select the type of date to base the report on.</span></span></p>
<ul>
<li><p><span data-ttu-id="7c3cd-125"><strong>Data da transação</strong> – a data de lançamento das transações.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-125"><strong>Transaction date</strong> – The posting date of the transactions.</span></span> <span data-ttu-id="7c3cd-126">Por exemplo, pode ser uma data da fatura que é a base para o cálculo da data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-126">For example, this might be an invoice date that is the basis for the calculation of the due date.</span></span></p></li>
<li><p><span data-ttu-id="7c3cd-127"><strong>Data de vencimento</strong> – a data de vencimento das transações, com base nas condições de pagamento.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-127"><strong>Due date</strong> – The due date of the transactions, based on the terms of payment.</span></span></p></li>
<li><p><span data-ttu-id="7c3cd-128"><strong>Data do documento</strong> – uma data do documento definida pelo usuário que é a base para o cálculo da data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-128"><strong>Document date</strong> – A user-defined document date that is the basis for the calculation of the due date.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c3cd-129"><strong>Definição do período de classificação por vencimento</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-129"><strong>Aging period definition</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-130">Selecione uma definição de período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-130">Select an aging period definition.</span></span> <span data-ttu-id="7c3cd-131">O campo <strong>Intervalo</strong> não será usado se você selecionar uma definição de período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-131">The <strong>Interval</strong> field is not used if you select an aging period definition.</span></span></p>
<p><span data-ttu-id="7c3cd-132">As definições do período de classificação por vencimento com mais de seis períodos de classificação por vencimento não podem ser usadas no relatório impresso.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-132">Aging period definitions that have more than six aging periods cannot be used on the printed report.</span></span></p>
<div class="alert">

<span data-ttu-id="7c3cd-133">**Observação:** você pode configurar períodos de classificação por vencimento na página <STRONG>Definições de período de classificação por vencimento</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-133">**Note:** You can set up aging periods on the <STRONG>Aging period definitions</STRONG> page.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c3cd-134"><strong>Imprimir a descrição do período de classificação por vencimento</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-134"><strong>Print aging period description</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-135">Selecione <strong>Sim</strong> para incluir descrições na parte superior de cada coluna de período de classificação por vencimento do relatório.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-135">Select <strong>Yes</strong> to include aging period descriptions at the top of each aging period column on the report.</span></span> <span data-ttu-id="7c3cd-136">Selecione <strong>Não</strong> para imprimir o relatório sem cabeçalhos de coluna.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-136">Select <strong>No</strong> to print the report without column headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c3cd-137"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-137"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-138">Defina o período a ser usado digitando o número de unidades de dias ou meses em cada período.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-138">Define the period to use by entering the number of the day or month units in each period.</span></span> <span data-ttu-id="7c3cd-139">Por exemplo, para ver as informações de classificação por vencimento por semana, digite 7 nesse campo e selecione <strong>Dia</strong> no campo <strong>Dia/Mês</strong>.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-139">For example, to view aging information by week, enter 7 in this field and select <strong>Day</strong> in the <strong>Day/Mth</strong> field.</span></span></p>
<div class="alert">

<span data-ttu-id="7c3cd-140">**Observação:** as informações que você digitar no campo serão usadas somente se você não tiver selecionado uma definição de período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-140">**Note:** The information that you enter in this field is used only if you have not selected an aging period definition.</span></span> <span data-ttu-id="7c3cd-141">Caso contrário, a direção de impressão será definida na definição do período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-141">Otherwise, the printing direction is defined on the aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c3cd-142"><strong>Dia/mês</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-142"><strong>Day/Mth</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-143">Selecione a unidade, <strong>Dia</strong> ou <strong>Mês</strong>, usada para definir o campo <strong>Intervalo</strong>.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-143">Select the unit, either <strong>Day</strong> or <strong>Month</strong>, that is used to define the period in the <strong>Interval</strong> field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c3cd-144"><strong>Direção de impressão</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-144"><strong>Printing direction</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-145">Selecione se deseja calcular saldos e imprimir o relatório de classificação por vencimento para períodos passados ou futuros.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-145">Select whether to calculate balances and print the aging report for past or future periods.</span></span> <span data-ttu-id="7c3cd-146">As datas são avaliadas em relação à data selecionada no campo <strong>Saldo como em</strong>.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-146">The dates are evaluated relative to the date that is selected in the <strong>Balance as on</strong> field.</span></span> <span data-ttu-id="7c3cd-147">Selecione <strong>Recuar</strong> para mostrar informações sobre períodos passados.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-147">Select <strong>Backward</strong> to show information for past periods.</span></span> <span data-ttu-id="7c3cd-148">Selecione <strong>Avançar</strong> para mostrar informações para períodos futuros.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-148">Select <strong>Forward</strong> to show information for future periods.</span></span></p>
<div class="alert"><span data-ttu-id="7c3cd-149">
  
<STRONG>Observação:</STRONG> as informações que você digitar no campo serão usadas somente se você não tiver selecionado uma definição de período de classificação por vencimento.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-149">
  
<STRONG>Note:</STRONG> The information that you enter in this field is used only if you have not selected an aging period definition.</span></span></P>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c3cd-150"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-150"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-151">Selecione para listar incluir as transações incluídas nos saldos mostrados no relatório.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-151">Select to list the transactions that are included in the balances that are shown on the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c3cd-152"><strong>Incluir valores na moeda de transação</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-152"><strong>Include amounts in transaction currency</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-153">Selecione para incluir valores na moeda da transação além dos valores na moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-153">Select to include amounts in the transaction currency in addition to amounts in the accounting currency.</span></span> <span data-ttu-id="7c3cd-154">Se essa caixa de seleção não estiver marcada, os valores no relatório só serão exibidos na moeda contábil.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-154">If this check box is not selected, the amounts on the report are displayed only in the accounting currency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c3cd-155"><strong>Saldo negativo</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-155"><strong>Negative balance</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-156">Selecione para incluir contas de cliente que têm saldos negativos.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-156">Select to include customer accounts that have negative balances.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c3cd-157"><strong>Excluir as contas de saldo zero</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-157"><strong>Exclude zero balance accounts</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-158">Selecione para excluir contas de cliente com saldo zerado.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-158">Select to exclude customer accounts that have a zero balance.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c3cd-159"><strong>Posição de pagamento</strong></span><span class="sxs-lookup"><span data-stu-id="7c3cd-159"><strong>Payment positioning</strong></span></span></p></td>
<td><p><span data-ttu-id="7c3cd-160">Selecione para exibir os pagamentos que não foram liquidados.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-160">Select to display payments that have not been settled.</span></span> <span data-ttu-id="7c3cd-161">Eles são exibidos na primeira coluna do relatório.</span><span class="sxs-lookup"><span data-stu-id="7c3cd-161">These are displayed in the first column of the report.</span></span></p></td>
</tr>
</tbody>
</table>

