---
title: Acúmulo de subscrições
description: Com as subscrições de serviço, você acumula a receita manualmente nos períodos após a data em que faturou uma transação de taxa.
author: ShylaThompson
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a2b581c8ae52f4c379e8e511dc898a8d106d149
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908051"
---
# <a name="accruing-subscriptions"></a><span data-ttu-id="a3aed-103">Acúmulo de subscrições</span><span class="sxs-lookup"><span data-stu-id="a3aed-103">Accruing subscriptions</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a3aed-104">Com as subscrições de serviço, você acumula a receita manualmente nos períodos após a data em que faturou uma transação de taxa.</span><span class="sxs-lookup"><span data-stu-id="a3aed-104">With service subscriptions, you manually accrue revenue in the periods following the date when you invoiced a fee transaction.</span></span>

<span data-ttu-id="a3aed-105">Os períodos de acumulação são criados para o período da nota fiscal configurado para a taxa de subscrição e se baseiam no código de período da subscrição.</span><span class="sxs-lookup"><span data-stu-id="a3aed-105">Accrual periods are created for the invoice period that you set up for the subscription fee, and the accrual periods are based on the period code of the subscription.</span></span>

<span data-ttu-id="a3aed-106">Você pode acumular e reverter a receita acumulada.</span><span class="sxs-lookup"><span data-stu-id="a3aed-106">You can accrue and reverse accrued revenue.</span></span>

## <a name="reverse-accruals-of-credit-amounts"></a><span data-ttu-id="a3aed-107">Reverter acúmulos dos valores de crédito</span><span class="sxs-lookup"><span data-stu-id="a3aed-107">Reverse accruals of credit amounts</span></span>

<span data-ttu-id="a3aed-108">Se você creditar valores de subscrição faturados, poderá usar dois métodos para reverter os valores acumulados:</span><span class="sxs-lookup"><span data-stu-id="a3aed-108">If you credit invoiced subscription amounts, you can use two methods to reverse the accrual amounts:</span></span>

  - <span data-ttu-id="a3aed-109">Você pode reverter cada transação de receita acumulada individualmente antes de criar a proposta de nota de crédito para a transação.</span><span class="sxs-lookup"><span data-stu-id="a3aed-109">You can reverse each accrued revenue transaction individually before you create the credit note proposal for the transaction.</span></span> <span data-ttu-id="a3aed-110">Esse é o método manual.</span><span class="sxs-lookup"><span data-stu-id="a3aed-110">This is the manual method.</span></span> <span data-ttu-id="a3aed-111">(manual)</span><span class="sxs-lookup"><span data-stu-id="a3aed-111">(manual)</span></span>

  - <span data-ttu-id="a3aed-112">Você pode ter os valores acumulados revertidos na data em que a nota de crédito é lançada ou na data de lançamento original da competência.</span><span class="sxs-lookup"><span data-stu-id="a3aed-112">You can have the accrued amounts reversed on the date where the credit note is posted or on the original posting date of the accrual.</span></span>

<span data-ttu-id="a3aed-113">Para obter mais informações, consulte [Parâmetros de subscrição (formulário)](/dynamicsax-2012//subscription-parameters-form).</span><span class="sxs-lookup"><span data-stu-id="a3aed-113">For more information, see [Subscription parameters (form)](/dynamicsax-2012//subscription-parameters-form).</span></span>

## <a name="setup-requirements"></a><span data-ttu-id="a3aed-114">Requisitos de instalação</span><span class="sxs-lookup"><span data-stu-id="a3aed-114">Setup requirements</span></span>

<span data-ttu-id="a3aed-115">Para acumular receitas, verifique se os seguintes requisitos de dados são atendidos:</span><span class="sxs-lookup"><span data-stu-id="a3aed-115">To accrue revenue, make sure that the following data requirements are met:</span></span>

## <a name="account-setup"></a><span data-ttu-id="a3aed-116">Configuração da conta</span><span class="sxs-lookup"><span data-stu-id="a3aed-116">Account setup</span></span>

<span data-ttu-id="a3aed-117">As contas **WIP - subscrição** e **Receita acumulada - subscrição** devem ser configuradas no módulo **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a3aed-117">The **WIP - subscription** and the **Accrued revenue - subscription** accounts must be set up in the **Project** module.</span></span>

<span data-ttu-id="a3aed-118">Quando você lança a receita acumulada, o valor da acumulação é debitado da conta **WIP - subscrição** e creditado na conta **Receita acumulada - Subscrição**.</span><span class="sxs-lookup"><span data-stu-id="a3aed-118">When you post accrued revenue, the **WIP - subscription** account is debited with the accrual amount, and the **Accrued revenue - subscription** account is credited with the accrual amount.</span></span>

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a><span data-ttu-id="a3aed-119">Configurar contas para acumulação de receitas de subscrição</span><span class="sxs-lookup"><span data-stu-id="a3aed-119">Set up accounts for accrual of subscription revenue</span></span>

1.  <span data-ttu-id="a3aed-120">Clique em **Gerenciamento e contabilidade de projeto** \> **Configuração** \> **Lançamento** \> **Configuração de lançamento contábil**.</span><span class="sxs-lookup"><span data-stu-id="a3aed-120">Click **Project management and accounting** \> **Setup** \> **Posting** \> **Ledger posting setup**.</span></span>

2.  <span data-ttu-id="a3aed-121">Clique na guia **Contas de receita**, selecione **WIP - subscrição** ou **Receita acumulada - subscrição** para configurar as contas.</span><span class="sxs-lookup"><span data-stu-id="a3aed-121">Click the **Revenue accounts** tab, and select **WIP - subscription** or **Accrued revenue - subscription** to set up the accounts.</span></span>

## <a name="subscription-group-setup"></a><span data-ttu-id="a3aed-122">Configuração do grupo de subscrições</span><span class="sxs-lookup"><span data-stu-id="a3aed-122">Subscription group setup</span></span>

<span data-ttu-id="a3aed-123">Para acumular receita de subscrições, a caixa de seleção **Acumular receita** deve ser marcada.</span><span class="sxs-lookup"><span data-stu-id="a3aed-123">To be able to accrue revenue for subscriptions, the **Accrue revenue** check box must be selected.</span></span> <span data-ttu-id="a3aed-124">Isso é encontrado no formulário **Grupos de subscrições** do grupo que está anexado à subscrição.</span><span class="sxs-lookup"><span data-stu-id="a3aed-124">This is found on the **Subscription groups** form for the group that is attached to the subscription.</span></span> <span data-ttu-id="a3aed-125">Clique em **Gerenciamento de serviço** \> **Configuração** \> **Subscrições de serviço** \> **Grupos de subscrições**.</span><span class="sxs-lookup"><span data-stu-id="a3aed-125">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="enable-revenue-accrual-on-a-subscription-group"></a><span data-ttu-id="a3aed-126">Habilitar acumulação de receita em um grupo de subscrições</span><span class="sxs-lookup"><span data-stu-id="a3aed-126">Enable revenue accrual on a subscription group</span></span>

1.  <span data-ttu-id="a3aed-127">Clique em **Gerenciamento de serviço** \> **Configuração** \> **Subscrições de serviço** \> **Grupos de subscrições**.</span><span class="sxs-lookup"><span data-stu-id="a3aed-127">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="periods"></a><span data-ttu-id="a3aed-128">Períodos</span><span class="sxs-lookup"><span data-stu-id="a3aed-128">Periods</span></span>

<span data-ttu-id="a3aed-129">É necessário configurar um código de período de faturamento.</span><span class="sxs-lookup"><span data-stu-id="a3aed-129">You must set up an invoicing period code.</span></span> <span data-ttu-id="a3aed-130">A menos que você deseje acumular receitas nos mesmos intervalos de tempo usados no faturamento, também é necessário configurar um período de acúmulo.</span><span class="sxs-lookup"><span data-stu-id="a3aed-130">Unless you want to accrue revenue in the same time intervals as you use for invoicing, you must also set up an accrual period.</span></span>

<span data-ttu-id="a3aed-131">A seguinte tabela fornece uma visão geral dos períodos de acumulo que podem ser configurados para cada período de faturamento:</span><span class="sxs-lookup"><span data-stu-id="a3aed-131">The following table provides an overview of which accrual periods can be set up for each invoicing period:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a3aed-132">Período de faturamento</span><span class="sxs-lookup"><span data-stu-id="a3aed-132">Invoicing period</span></span></p></th>
<th><p><span data-ttu-id="a3aed-133">Período de acumulação</span><span class="sxs-lookup"><span data-stu-id="a3aed-133">Accrual period</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3aed-134"><strong>Anos</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-134"><strong>Years</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a3aed-135"><strong>Anos</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-135"><strong>Years</strong></span></span></p></li>
<li><p><span data-ttu-id="a3aed-136"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-136"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="a3aed-137"><strong>Mês</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-137"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="a3aed-138"><strong>Dia</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-138"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3aed-139"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-139"><strong>Quarter</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a3aed-140"><strong>Trimestre</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-140"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="a3aed-141"><strong>Mês</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-141"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="a3aed-142"><strong>Dia</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-142"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3aed-143"><strong>Mês</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-143"><strong>Month</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a3aed-144"><strong>Mês</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-144"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="a3aed-145"><strong>Dia</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-145"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3aed-146"><strong>Semana</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-146"><strong>Week</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a3aed-147"><strong>Dia</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-147"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3aed-148"><strong>Dia</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-148"><strong>Day</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a3aed-149"><strong>Dia</strong></span><span class="sxs-lookup"><span data-stu-id="a3aed-149"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a3aed-150">Configurar o período de faturamento é uma parte obrigatória da configuração geral do grupo de subscrições.</span><span class="sxs-lookup"><span data-stu-id="a3aed-150">Setting up the invoicing period is a mandatory part of the overall subscription group setup.</span></span> <span data-ttu-id="a3aed-151">Você também pode optar por configurar um período de acúmulo para o grupo de subscrições.</span><span class="sxs-lookup"><span data-stu-id="a3aed-151">You can decide whether to also set up an accrual period for the subscription group.</span></span> <span data-ttu-id="a3aed-152">Se você configurar um período de acúmulo para o grupo de subscrições, esse período será sugerido no campo **Código de período**.</span><span class="sxs-lookup"><span data-stu-id="a3aed-152">If you set up an accrual period for the subscription group, this period is suggested in the **Period code** field.</span></span> <span data-ttu-id="a3aed-153">Esse campo é encontrado no formulário **Acumular receita de subscrição**, quando você acumula receita de subscrição.</span><span class="sxs-lookup"><span data-stu-id="a3aed-153">This field is found in the **Accrue subscription revenue** form, when you accrue subscription revenue.</span></span> <span data-ttu-id="a3aed-154">Entretanto, o período de acumulação é uma informação opcional sobre o grupo de subscrições.</span><span class="sxs-lookup"><span data-stu-id="a3aed-154">However, the accrual period is optional information about the subscription group.</span></span>


> [!NOTE]
> <P><span data-ttu-id="a3aed-155">Use o seguinte caminho para abrir o formulário <STRONG>Acumular receita de subscrição</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a3aed-155">Use the following path to open the <STRONG>Accrue subscription revenue</STRONG> form.</span></span> <span data-ttu-id="a3aed-156">Clique em <STRONG>Gerenciamento de serviço</STRONG> &gt; <STRONG>Periódico</STRONG> &gt; <STRONG>Subscrições de serviço</STRONG> &gt; <STRONG>Acumular receita de subscrição</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a3aed-156">Click <STRONG>Service management</STRONG> &gt; <STRONG>Periodic</STRONG> &gt; <STRONG>Service subscriptions</STRONG> &gt; <STRONG>Accrue subscription revenue</STRONG>.</span></span></P>


## <a name="transactions"></a><span data-ttu-id="a3aed-157">Transações</span><span class="sxs-lookup"><span data-stu-id="a3aed-157">Transactions</span></span>

<span data-ttu-id="a3aed-158">Você pode controlar o número de transações do razão que são criadas quando você lança a receita acumulada.</span><span class="sxs-lookup"><span data-stu-id="a3aed-158">You can control the number of ledger transactions that are created when you post accrued revenue.</span></span> <span data-ttu-id="a3aed-159">Em subscrições, defina se as transações do razão devem ser criadas como um total ou por linha.</span><span class="sxs-lookup"><span data-stu-id="a3aed-159">On subscriptions, define if the ledger transactions should be created as a total or per line.</span></span>

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a><span data-ttu-id="a3aed-160">Especificar o nível de detalhes de lançamento a serem exibidos para transações acumuladas</span><span class="sxs-lookup"><span data-stu-id="a3aed-160">Specify the level of posting details to display for accrued transactions</span></span>

1.  <span data-ttu-id="a3aed-161">Clique em **Gerenciamento e contabilidade de projetos** \> **Configurar** \> **Parâmetros de gerenciamento e contabilidade de projetos**.</span><span class="sxs-lookup"><span data-stu-id="a3aed-161">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="a3aed-162">Na guia **Financeiro**, no campo **Fatura**, selecione **Total** ou **Linha**.</span><span class="sxs-lookup"><span data-stu-id="a3aed-162">On the **Financial** tab, in the **Invoice** field, select **Total** or **Line**.</span></span>


## <a name="see-also"></a><span data-ttu-id="a3aed-163">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a3aed-163">See also</span></span>

[<span data-ttu-id="a3aed-164">Acumular receita de subscrição</span><span class="sxs-lookup"><span data-stu-id="a3aed-164">Accrue subscription revenue</span></span>](accrue-subscription-revenue.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]