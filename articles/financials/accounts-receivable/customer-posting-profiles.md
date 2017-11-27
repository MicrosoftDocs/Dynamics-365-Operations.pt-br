---
title: "Perfis de lançamentos de cliente"
description: "Perfis de postagem de cliente controlam o lançamento de transações de cliente na contabilidade."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ccd663a769aa98afb800f6fcd6217f39bb513597
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="customer-posting-profiles"></a><span data-ttu-id="d206b-103">Perfis de lançamentos de cliente</span><span class="sxs-lookup"><span data-stu-id="d206b-103">Customer posting profiles</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d206b-104">Perfis de postagem de cliente controlam o lançamento de transações de cliente na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="d206b-104">Customer posting profiles control the posting of customer transactions to the general ledger.</span></span>

<a name="customer-posting-profiles"></a><span data-ttu-id="d206b-105">Perfis de lançamentos de cliente</span><span class="sxs-lookup"><span data-stu-id="d206b-105">Customer posting profiles</span></span>
-------------------------

<span data-ttu-id="d206b-106">Os perfis de lançamento de cliente permitem que você atribua configurações de documento e de contas de contabilidade a todos os clientes, um grupo de clientes ou um único cliente.</span><span class="sxs-lookup"><span data-stu-id="d206b-106">Customer posting profiles enable you to assign general ledger accounts and document settings to all customers, a group of customers or a single customer.</span></span> <span data-ttu-id="d206b-107">Essas configurações serão usadas ao criar ordens de venda, faturas de texto livre, pagamentos em dinheiro, cartas de cobrança e notas de juros.</span><span class="sxs-lookup"><span data-stu-id="d206b-107">These settings will be used when you create sales orders, free text invoices, cash payments, collection letters, and interest notes.</span></span> <span data-ttu-id="d206b-108">Para algumas transações, você pode selecionar um perfil de lançamento diferente dos perfis de lançamento configurados para as transações nesta página e que seja prioritário.</span><span class="sxs-lookup"><span data-stu-id="d206b-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> 

<span data-ttu-id="d206b-109">O perfil de lançamento padrão é definido na Guia Rápida Razão e Imposto na página Parâmetros de contas a receber.</span><span class="sxs-lookup"><span data-stu-id="d206b-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts receivable parameters page.</span></span> <span data-ttu-id="d206b-110">O perfil de lançamento padrão é incluído automaticamente no cabeçalho dos novos documentos onde você pode alterá-lo para um perfil de lançamento diferente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d206b-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="d206b-111">Você também pode associar definições de lançamento com os tipos de lançamento de transação na página Definições de lançamento da transação.</span><span class="sxs-lookup"><span data-stu-id="d206b-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="d206b-112">As definições de lançamento controlam o lançamento de transações de cliente na contabilidade em vez de perfis de lançamento.</span><span class="sxs-lookup"><span data-stu-id="d206b-112">Posting definitions control the posting of customer transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="d206b-113">Criando um perfil de lançamento</span><span class="sxs-lookup"><span data-stu-id="d206b-113">Creating a posting profile</span></span>
<span data-ttu-id="d206b-114">Especifique as contas contábeis que são usadas no lançamento de transações que usam o perfil de lançamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="d206b-114">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="d206b-115">Selecione um código de conta e, sempre que possível, uma conta ou número de grupo para o perfil de lançamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="d206b-115">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="d206b-116">No processo de lançamento, o perfil de lançamento mais apropriado para cada transação é localizado procurando a combinação de código de conta, número de conta, grupo e número mais específica segundo esta prioridade:</span><span class="sxs-lookup"><span data-stu-id="d206b-116">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="d206b-117">Valor do campo **Código de conta**</span><span class="sxs-lookup"><span data-stu-id="d206b-117">**Account code** field value</span></span> | <span data-ttu-id="d206b-118">Valor do campo **Conta/número de grupo**</span><span class="sxs-lookup"><span data-stu-id="d206b-118">**Account/Group number** field value</span></span>            | <span data-ttu-id="d206b-119">Prioridade de pesquisa</span><span class="sxs-lookup"><span data-stu-id="d206b-119">Search priority</span></span> |
|------------------------------|-------------------------------------------------|-----------------|
| <span data-ttu-id="d206b-120">**Tabela**</span><span class="sxs-lookup"><span data-stu-id="d206b-120">**Table**</span></span>                    | <span data-ttu-id="d206b-121">Conta de cliente específico</span><span class="sxs-lookup"><span data-stu-id="d206b-121">Specific customer account</span></span>                       | <span data-ttu-id="d206b-122">1</span><span class="sxs-lookup"><span data-stu-id="d206b-122">1</span></span>               |
| <span data-ttu-id="d206b-123">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="d206b-123">**Group**</span></span>                    | <span data-ttu-id="d206b-124">Grupo de clientes atribuído ao cliente</span><span class="sxs-lookup"><span data-stu-id="d206b-124">Customer group that is assigned to the customer</span></span> | <span data-ttu-id="d206b-125">2</span><span class="sxs-lookup"><span data-stu-id="d206b-125">2</span></span>               |
| <span data-ttu-id="d206b-126">**Todos**</span><span class="sxs-lookup"><span data-stu-id="d206b-126">**All**</span></span>                      | <span data-ttu-id="d206b-127">Em Branco</span><span class="sxs-lookup"><span data-stu-id="d206b-127">Blank</span></span>                                           | <span data-ttu-id="d206b-128">3</span><span class="sxs-lookup"><span data-stu-id="d206b-128">3</span></span>               |

<span data-ttu-id="d206b-129">Se desejar que todas as transações de clientes tenham o mesmo perfil de lançamento, configure somente um perfil de lançamento com a opção Todos no campo Código de conta.</span><span class="sxs-lookup"><span data-stu-id="d206b-129">If you want all customer transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="d206b-130">Especifique os seguintes valores para configurar o perfil de lançamento:</span><span class="sxs-lookup"><span data-stu-id="d206b-130">Specify the following values to set up your posting profile:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d206b-131">Campo</span><span class="sxs-lookup"><span data-stu-id="d206b-131">Field</span></span></th>
<th><span data-ttu-id="d206b-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="d206b-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d206b-133"><strong>Perfil de lançamentos</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-133"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="d206b-134">Insira um código para o perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="d206b-134">Enter a code for the posting profile.</span></span> <span data-ttu-id="d206b-135">Por exemplo, você pode criar dois perfis de lançamento para obter uma conta para os saldos de cliente na moeda nacional e outra para os saldos de cliente em uma moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="d206b-135">For example, you could create two posting profiles to obtain one account for customer balances in the national currency and another for customer balances in a foreign currency.</span></span> <span data-ttu-id="d206b-136">Você poderia chamar uma conta de Nacional e a outra de Estrangeira.</span><span class="sxs-lookup"><span data-stu-id="d206b-136">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d206b-137"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-137"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="d206b-138">Insira uma descrição do perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="d206b-138">Enter a description of the posting profile.</span></span> <span data-ttu-id="d206b-139">É usado apenas para melhor identificar o perfil de lançamento quando você o exibe nessa página.</span><span class="sxs-lookup"><span data-stu-id="d206b-139">This is only used to better identify the posting profile when you view it in this page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d206b-140"><strong>Código da conta</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="d206b-141">Especifique se o perfil de lançamento se aplica a um único cliente, um grupo de clientes ou todos os clientes:</span><span class="sxs-lookup"><span data-stu-id="d206b-141">Specify whether the posting profile applies to a single customer, a group of customers, or all customers:</span></span>
<ul>
<li><span data-ttu-id="d206b-142"><strong>Tabela</strong> – O perfil de lançamento se aplica a um único cliente.</span><span class="sxs-lookup"><span data-stu-id="d206b-142"><strong>Table</strong> – The posting profile applies to a single customer.</span></span> <span data-ttu-id="d206b-143">Selecione a conta de cliente no campo Conta/número de grupo.</span><span class="sxs-lookup"><span data-stu-id="d206b-143">Select the customer account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="d206b-144"><strong>Grupo</strong> – O perfil de lançamento se aplica a um grupo de cliente.</span><span class="sxs-lookup"><span data-stu-id="d206b-144"><strong>Group</strong> – The posting profile applies to a customer group.</span></span> <span data-ttu-id="d206b-145">Selecione o grupo de cliente no campo Conta/número de grupo.</span><span class="sxs-lookup"><span data-stu-id="d206b-145">Select the customer group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="d206b-146"><strong>Todos</strong> – O perfil de lançamento se aplica a todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="d206b-146"><strong>All</strong> – The posting profile applies to all customers.</span></span> <span data-ttu-id="d206b-147">Deixe o campo Conta/número de grupo em branco.</span><span class="sxs-lookup"><span data-stu-id="d206b-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d206b-148"><strong>Número de conta/grupo</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="d206b-149">Se Tabela for selecionado no campo Código de conta, selecione o número de conta do cliente que está associado ao perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="d206b-149">If Table is selected in the Account code field, select the account number of the customer who is associated with the posting profile.</span></span> <span data-ttu-id="d206b-150">Se Grupo for selecionado, selecione o grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="d206b-150">If Group is selected, select the customer group.</span></span> <span data-ttu-id="d206b-151">Se Todos for selecionado, deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="d206b-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d206b-152"><strong>Conta resumo</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="d206b-153">Selecione a conta contábil que será usada com conta resumo para os clientes associados ao perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="d206b-153">Select the ledger account that will be used as the customer summary account for the customers who are associated with the posting profile.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d206b-154"><strong>Liquidar conta</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-154"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="d206b-155">Selecione a conta contábil de liquidez usada para previsões de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="d206b-155">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="d206b-156">Este campo só aparecerá se as previsões de fluxo de caixa estiverem habilitadas.</span><span class="sxs-lookup"><span data-stu-id="d206b-156">This field will only appear if cash flow forecasts are enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d206b-157"><strong>Pagamentos antecipados de imposto</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-157"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="d206b-158">Selecione a conta para imposto sobre vendas para os pagamentos recebidos antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="d206b-158">Select the account for sales tax for payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="d206b-159"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Observação</span><span class="sxs-lookup"><span data-stu-id="d206b-159"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Note</span></span>" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="d206b-160"><strong>Observação</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-160"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d206b-161">Use a página Parâmetros de contas a receber para especificar o perfil de lançamento a ser usado quando um pagamento for marcado como pagamento antecipado.</span><span class="sxs-lookup"><span data-stu-id="d206b-161">Use the Accounts receivable parameters page to specify the posting profile to use when a payment is marked as a prepayment.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d206b-162"><strong>Passivos para conta de desconto</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-162"><strong>Liabilities for discount account</strong></span></span></td>
<td><span data-ttu-id="d206b-163">Selecione a conta contábil para passivos de desconto.</span><span class="sxs-lookup"><span data-stu-id="d206b-163">Select the ledger account for liabilities of discount.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d206b-164"><strong>Sequência de cartas de cobrança</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-164"><strong>Collection letter sequence</strong></span></span></td>
<td><span data-ttu-id="d206b-165">Selecione o identificador da sequência de cartas de cobrança a ser usado para clientes aos quais o perfil de lançamento é atribuído.</span><span class="sxs-lookup"><span data-stu-id="d206b-165">Select the identifier of the collection letter sequence to use for customers to whom the posting profile is assigned.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d206b-166"><strong>Código de juros</strong></span><span class="sxs-lookup"><span data-stu-id="d206b-166"><strong>Interest code</strong></span></span></td>
<td><span data-ttu-id="d206b-167">Selecione o código de juros a ser usado para o cálculo de juros para clientes aos quais o perfil de lançamento é atribuído.</span><span class="sxs-lookup"><span data-stu-id="d206b-167">Select the interest code to use for the calculation of interest for customers to whom the posting profile is assigned.</span></span></td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a><span data-ttu-id="d206b-168">**Restrições da tabela**</span><span class="sxs-lookup"><span data-stu-id="d206b-168">**Table restrictions**</span></span>

<span data-ttu-id="d206b-169">Para as transações com o perfil de lançamento selecionado, especifique se as transações serão automaticamente liquidadas, os juros calculados, e as cartas de cobrança emitidas.</span><span class="sxs-lookup"><span data-stu-id="d206b-169">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="d206b-170">Também é possível selecionar a conta usada quando transações com o perfil de lançamento selecionado forem fechadas.</span><span class="sxs-lookup"><span data-stu-id="d206b-170">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="d206b-171">Especifique os seguintes valores para configurar o perfil de lançamento:</span><span class="sxs-lookup"><span data-stu-id="d206b-171">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="d206b-172">Campo</span><span class="sxs-lookup"><span data-stu-id="d206b-172">Field</span></span>                 | <span data-ttu-id="d206b-173">Descrição</span><span class="sxs-lookup"><span data-stu-id="d206b-173">Description</span></span>                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d206b-174">**Liquidação**</span><span class="sxs-lookup"><span data-stu-id="d206b-174">**Settlement**</span></span>        | <span data-ttu-id="d206b-175">Selecione esta alternância para habilitar a liquidação automática de transações que possuem este perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="d206b-175">Select this toggle to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="d206b-176">Se esta alternância for desmarcada, você deverá liquidar manualmente as transações usando a página Liquidar transações em aberto ou a página Inserir pagamentos de cliente.</span><span class="sxs-lookup"><span data-stu-id="d206b-176">If this toggle is cleared, you must manually settle transactions by using the Settle open transactions page or the Enter customer payments page.</span></span> |
| <span data-ttu-id="d206b-177">**Interesse**</span><span class="sxs-lookup"><span data-stu-id="d206b-177">**Interest**</span></span>          | <span data-ttu-id="d206b-178">Selecione esta alternância se os juros precisarem ser calculados sobre saldos em aberto para contas de cliente que usam este perfil.</span><span class="sxs-lookup"><span data-stu-id="d206b-178">Select this toggle if interest should be calculated on outstanding balances for customer accounts that use this profile.</span></span> <span data-ttu-id="d206b-179">Se esta alternância for desmarcada, os juros não serão calculados para esses clientes.</span><span class="sxs-lookup"><span data-stu-id="d206b-179">If this toggle is cleared, interest will not be calculated for these customers.</span></span>                                           |
| <span data-ttu-id="d206b-180">**Carta de cobrança**</span><span class="sxs-lookup"><span data-stu-id="d206b-180">**Collection letter**</span></span> | <span data-ttu-id="d206b-181">Selecione esta alternância se as cartas de cobrança precisarem ser geradas para contas de cliente que usam este perfil.</span><span class="sxs-lookup"><span data-stu-id="d206b-181">Select this toggle if collection letters should be generated for customer accounts that use this profile.</span></span> <span data-ttu-id="d206b-182">Se esta alternância for desmarcada, as cartas de cobrança não serão geradas para esses clientes.</span><span class="sxs-lookup"><span data-stu-id="d206b-182">If this toggle is cleared, collection letters will not be generated for these customers.</span></span>                                                 |
| <span data-ttu-id="d206b-183">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="d206b-183">**Close**</span></span>             | <span data-ttu-id="d206b-184">Selecione um perfil de lançamento para o qual alternar quando as transações que tiverem este perfil de lançamento forem fechadas.</span><span class="sxs-lookup"><span data-stu-id="d206b-184">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="d206b-185">Uma transação é considerada fechada quando tiver sido integralmente liquidada.</span><span class="sxs-lookup"><span data-stu-id="d206b-185">A transaction is regarded as closed when it has been settled in full.</span></span>                                                                           |



<span data-ttu-id="d206b-186">Para obter mais informações, consulte [Visão geral de pagamentos do cliente](../cash-bank-management/tasks/customer-payment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d206b-186">For more information, see [Customer payment overview](../cash-bank-management/tasks/customer-payment-overview.md).</span></span>


