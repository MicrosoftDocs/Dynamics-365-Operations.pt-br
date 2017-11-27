---
title: "Perfis de lançamentos de fornecedores"
description: "Os perfis de lançamentos que controlam o lançamento de transações de fornecedor na contabilidade."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7bf37ff484323fb05a35419889f2f89ab124fb27
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="vendor-posting-profiles"></a><span data-ttu-id="5e1c1-103">Perfis de lançamentos de fornecedores</span><span class="sxs-lookup"><span data-stu-id="5e1c1-103">Vendor posting profiles</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5e1c1-104">Os perfis de lançamentos que controlam o lançamento de transações de fornecedor na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-104">Vendor posting profiles control the posting of vendor transactions to the general ledger.</span></span>

<a name="vendor-posting-profiles"></a><span data-ttu-id="5e1c1-105">Perfis de lançamentos de fornecedores</span><span class="sxs-lookup"><span data-stu-id="5e1c1-105">Vendor posting profiles</span></span>
-----------------------

<span data-ttu-id="5e1c1-106">Os perfis de lançamento de fornecedor permitem que você atribua configurações de documento e de contas de contabilidade a todos os fornecedores, um grupo de fornecedores ou um único fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-106">Vendor posting profiles enable you to assign general ledger accounts and document settings to all vendors, a group of vendors or a single vendor.</span></span> <span data-ttu-id="5e1c1-107">Essas configurações serão usadas quando você criar ordens de compra, faturas de fornecedor e pagamentos em dinheiro.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-107">These settings will be used when you create purchase orders, vendor invoices and cash payments.</span></span> <span data-ttu-id="5e1c1-108">Para algumas transações, você pode selecionar um perfil de lançamento diferente dos perfis de lançamento configurados para as transações nesta página e que seja prioritário.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-108">For some transactions, you can select a posting profile that differs from and takes precedence over the posting profiles that are set up for transactions in this page.</span></span> <span data-ttu-id="5e1c1-109">O perfil de lançamento padrão é definido na Guia Rápida Razão e Imposto na página Parâmetros de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-109">The default posting profile is defined in the Ledger and Sales Tax fasttab on the Accounts payable parameters page.</span></span> <span data-ttu-id="5e1c1-110">O perfil de lançamento padrão é incluído automaticamente no cabeçalho dos novos documentos onde você pode alterá-lo para um perfil de lançamento diferente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-110">The default posting profile is then included automatically on the header of new documents where you can change it to a different posting profile if needed.</span></span>

<span data-ttu-id="5e1c1-111">Você também pode associar definições de lançamento com os tipos de lançamento de transação na página Definições de lançamento da transação.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-111">You can also associate posting definitions with transaction posting types in the Transaction posting definitions page.</span></span> <span data-ttu-id="5e1c1-112">As definições de lançamento controlam o lançamento de transações de fornecedor na contabilidade em vez de perfis de lançamento.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-112">Posting definitions control the posting of vendor transactions to the general ledger instead of posting profiles.</span></span>

## <a name="creating-a-posting-profile"></a><span data-ttu-id="5e1c1-113">Criando um perfil de lançamento</span><span class="sxs-lookup"><span data-stu-id="5e1c1-113">Creating a posting profile</span></span>
### <a name="setup"></a><span data-ttu-id="5e1c1-114">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-114">**Setup**</span></span>

<span data-ttu-id="5e1c1-115">Especifique as contas contábeis que são usadas no lançamento de transações que usam o perfil de lançamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-115">Specify the ledger accounts that are used in the posting of transactions that use the selected posting profile.</span></span> <span data-ttu-id="5e1c1-116">Selecione um código de conta e, sempre que possível, uma conta ou número de grupo para o perfil de lançamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-116">Select an account code and, whenever possible, an account or group number for the selected posting profile.</span></span> <span data-ttu-id="5e1c1-117">No processo de lançamento, o perfil de lançamento mais apropriado para cada transação é localizado procurando a combinação de código de conta, número de conta, grupo e número mais específica segundo esta prioridade:</span><span class="sxs-lookup"><span data-stu-id="5e1c1-117">In the posting process, the most appropriate posting profile for each transaction is located by searching for the most specific account code, account number, or group and number combination in the following priority:</span></span>

| <span data-ttu-id="5e1c1-118">Valor do campo **Código de conta**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-118">**Account code** field value</span></span> | <span data-ttu-id="5e1c1-119">Valor do campo **Conta/número de grupo**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-119">**Account/Group number** field value</span></span>        | <span data-ttu-id="5e1c1-120">Prioridade de pesquisa</span><span class="sxs-lookup"><span data-stu-id="5e1c1-120">Search priority</span></span> |
|------------------------------|---------------------------------------------|-----------------|
| <span data-ttu-id="5e1c1-121">**Tabela**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-121">**Table**</span></span>                    | <span data-ttu-id="5e1c1-122">Conta de fornecedor específica</span><span class="sxs-lookup"><span data-stu-id="5e1c1-122">Specific vendor account</span></span>                     | <span data-ttu-id="5e1c1-123">1</span><span class="sxs-lookup"><span data-stu-id="5e1c1-123">1</span></span>               |
| <span data-ttu-id="5e1c1-124">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-124">**Group**</span></span>                    | <span data-ttu-id="5e1c1-125">grupo de fornecedores atribuído ao fornecedor</span><span class="sxs-lookup"><span data-stu-id="5e1c1-125">vendor group that is assigned to the vendor</span></span> | <span data-ttu-id="5e1c1-126">2</span><span class="sxs-lookup"><span data-stu-id="5e1c1-126">2</span></span>               |
| <span data-ttu-id="5e1c1-127">**Todos**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-127">**All**</span></span>                      | <span data-ttu-id="5e1c1-128">Em Branco</span><span class="sxs-lookup"><span data-stu-id="5e1c1-128">Blank</span></span>                                       | <span data-ttu-id="5e1c1-129">3</span><span class="sxs-lookup"><span data-stu-id="5e1c1-129">3</span></span>               |

<span data-ttu-id="5e1c1-130">Se desejar que todas as transações de fornecedores tenham o mesmo perfil de lançamento, configure somente um perfil de lançamento com a opção Todos no campo Código de conta.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-130">If you want all vendor transactions to have the same posting profile, set up only one posting profile with All in the Account code field.</span></span> <span data-ttu-id="5e1c1-131">Especifique os seguintes valores para configurar o perfil de lançamento:</span><span class="sxs-lookup"><span data-stu-id="5e1c1-131">Specify the following values to set up your posting profile:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e1c1-132">Campo</span><span class="sxs-lookup"><span data-stu-id="5e1c1-132">Field</span></span></th>
<th><span data-ttu-id="5e1c1-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e1c1-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5e1c1-134"><strong>Perfil de lançamentos</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-134"><strong>Posting profile</strong></span></span></td>
<td><span data-ttu-id="5e1c1-135">Insira um código para o perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-135">Enter a code for the posting profile.</span></span> <span data-ttu-id="5e1c1-136">Por exemplo, você pode criar dois perfis de lançamento para obter uma conta para os saldos do fornecedor na moeda nacional e outra para os saldos do fornecedor em moeda estrangeira.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-136">For example, you could create two posting profiles to obtain one account for vendor balances in the national currency and another for vendor balances in a foreign currency.</span></span> <span data-ttu-id="5e1c1-137">Você poderia chamar uma conta de Nacional e a outra de Estrangeira.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-137">You could call one account National and the other Foreign.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5e1c1-138"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-138"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="5e1c1-139">Insira uma descrição do perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-139">Enter a description of the posting profile.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5e1c1-140"><strong>Código da conta</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-140"><strong>Account code</strong></span></span></td>
<td><span data-ttu-id="5e1c1-141">Especifique se o perfil de lançamento se aplica a um fornecedor específico, a um grupo de fornecedores ou a todos os fornecedores:</span><span class="sxs-lookup"><span data-stu-id="5e1c1-141">Specify whether the posting profile applies to a specific vendor, a group of vendors, or all vendors:</span></span>
<ul>
<li><span data-ttu-id="5e1c1-142"><strong>Tabela</strong> – O perfil de lançamento se aplica a um único fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-142"><strong>Table</strong> – The posting profile applies to a single vendor.</span></span> <span data-ttu-id="5e1c1-143">Selecione a conta de fornecedor no campo Conta/número de grupo.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-143">Select the vendor account in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="5e1c1-144"><strong>Grupo</strong> – O perfil de lançamento se aplica a um grupo de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-144"><strong>Group</strong> – The posting profile applies to a vendor group.</span></span> <span data-ttu-id="5e1c1-145">Selecione o grupo de fornecedor no campo Conta/número de grupo.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-145">Select the vendor group in the Account/Group number field.</span></span></li>
<li><span data-ttu-id="5e1c1-146"><strong>Todos</strong> – O perfil de lançamento se aplica a todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-146"><strong>All</strong> – The posting profile applies to all vendors.</span></span> <span data-ttu-id="5e1c1-147">Deixe o campo Conta/número de grupo em branco.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-147">Leave the Account/Group number field blank.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5e1c1-148"><strong>Número de conta/grupo</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-148"><strong>Account/Group number</strong></span></span></td>
<td><span data-ttu-id="5e1c1-149">Se Tabela for selecionado no campo Código de conta, selecione o número de conta do fornecedor que está associado ao perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-149">If Table is selected in the Account code field, select the account number of the vendor that is associated with the posting profile.</span></span> <span data-ttu-id="5e1c1-150">Se Grupo for selecionado, selecione um grupo de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-150">If Group is selected, select a vendor group.</span></span> <span data-ttu-id="5e1c1-151">Se Todos for selecionado, deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-151">If All is selected, leave this field blank.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5e1c1-152"><strong>Conta resumo</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-152"><strong>Summary account</strong></span></span></td>
<td><span data-ttu-id="5e1c1-153">Selecione a conta contábil a ser usada como conta resumo para os fornecedores cobertos pelo perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-153">Select the ledger account that will be used as the summary account for the vendors that the posting profile relates to.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5e1c1-154"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Observação</span><span class="sxs-lookup"><span data-stu-id="5e1c1-154"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Note</span></span>" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="5e1c1-155"><strong>Observação</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-155"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5e1c1-156">Se a opção Alternância de definições de lançamento de uso estiver marcada na página Parâmetros da contabilidade, a definição de lançamento de transação para faturas de fornecedor será usada no lugar da conta resumo.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-156">If the Use posting definitions toggle is selected in the General ledger parameters page, the transaction posting definition for vendor invoices is used instead of the summary account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5e1c1-157"><strong>Liquidar conta</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-157"><strong>Settle account</strong></span></span></td>
<td><span data-ttu-id="5e1c1-158">Selecione a conta contábil de liquidez usada para previsões de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-158">Select the liquidity ledger account that is used for cash flow forecasts.</span></span> <span data-ttu-id="5e1c1-159">Este campo está disponível apenas quando a previsão de fluxo de caixa está habilitada.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-159">This fields is only available when cash flow forecasting is enabled.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5e1c1-160"><strong>Pagamentos antecipados de imposto</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-160"><strong>Sales tax prepayments</strong></span></span></td>
<td><span data-ttu-id="5e1c1-161">Selecione a conta para os pagamentos de imposto sobre vendas recebidos antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-161">Select the account for sales tax payments that are received in advance.</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5e1c1-162"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Observação</span><span class="sxs-lookup"><span data-stu-id="5e1c1-162"><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Note</span></span>" alt="Note" id="alert_note" class="cl_IC101471" /><span data-ttu-id="5e1c1-163"><strong>Observação</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5e1c1-164">O perfil de lançamento usado quando o pagamento é marcado como um pagamento antecipado é selecionado no perfil de lançamento com o campo do comprovante do diário de pagamentos antecipados na área do razão e do imposto sobre vendas da página Parâmetros de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-164">The posting profile that is used when the payment is marked as a prepayment is selected in the Posting profile with prepayment journal voucher field in the Ledger and sales tax area of the Accounts payable parameters page.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5e1c1-165"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-165"><strong>Arrival</strong></span></span></td>
<td><span data-ttu-id="5e1c1-166">Selecione a conta contábil na qual as informações sobre as faturas de fornecedor não aprovadas são lançadas.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-166">Select the ledger account that information about unapproved vendor invoices is posted to.</span></span> <span data-ttu-id="5e1c1-167">As informações são inseridas no diário de registro de fatura.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-167">The information is entered in the Invoice register journal.</span></span> <span data-ttu-id="5e1c1-168">Por exemplo, um usuário insere informações muito básicas sobre as faturas do fornecedor quando são recebidas no registro de faturas.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-168">For example, a user enters very basic information about vendor invoices when they are received in the invoice register.</span></span> <span data-ttu-id="5e1c1-169">Quando o registro de faturas é lançado, as transações são lançadas na conta que é inserida aqui e no campo Contrapartida.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-169">When the invoice register is posted, the transactions are posted to the account that is entered here and in the Offset account field.</span></span> <span data-ttu-id="5e1c1-170">Quando as faturas são aprovadas, o débito é transferido da conta de entrada para a conta resumo do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-170">When the invoices are approved, the debt is transferred from the Arrival account to the vendor summary account.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5e1c1-171"><strong>Contrapartida</strong></span><span class="sxs-lookup"><span data-stu-id="5e1c1-171"><strong>Offset account</strong></span></span></td>
<td><span data-ttu-id="5e1c1-172">Selecione a conta contábil usada para a compensação das faturas de fornecedor não aprovadas que são atualizadas por meio do registro de faturas.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-172">Select the ledger account that is used for offsetting unapproved vendor invoices that are updated by using the invoice register.</span></span> <span data-ttu-id="5e1c1-173">A contrapartida atua como contrapartida para as transações que são lançadas nas contas de entrada.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-173">The offset account acts as the offset account for transactions that are posted to arrival accounts.</span></span> <span data-ttu-id="5e1c1-174">Sendo assim, a conta contém as compras de fornecedor que ainda não foram aprovadas.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-174">Therefore, the account contains vendor purchases that have not yet been approved.</span></span></td>
</tr>
</tbody>
</table>
 

### <a name="table-restrictions"></a><span data-ttu-id="5e1c1-175">**Restrições da tabela**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-175">**Table restrictions**</span></span>

<span data-ttu-id="5e1c1-176">Para as transações com o perfil de lançamento selecionado, especifique se as transações serão automaticamente liquidadas, os juros calculados, e as cartas de cobrança emitidas.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-176">For transactions that have the selected posting profile, specify whether transactions will be settled automatically, interest will be calculated, and collection letters will be issued.</span></span> <span data-ttu-id="5e1c1-177">Também é possível selecionar a conta usada quando transações com o perfil de lançamento selecionado forem fechadas.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-177">You can also select the account that is used when transactions that have the selected posting profile are closed.</span></span>

<span data-ttu-id="5e1c1-178">Especifique os seguintes valores para configurar o perfil de lançamento:</span><span class="sxs-lookup"><span data-stu-id="5e1c1-178">Specify the following values to set up your posting profile:</span></span>

| <span data-ttu-id="5e1c1-179">Campo</span><span class="sxs-lookup"><span data-stu-id="5e1c1-179">Field</span></span>          | <span data-ttu-id="5e1c1-180">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e1c1-180">Description</span></span>                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5e1c1-181">**Liquidação**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-181">**Settlement**</span></span> | <span data-ttu-id="5e1c1-182">Selecione esta opção para habilitar a liquidação automática de transações que possuem este perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-182">Select this option to enable automatic settlement of transactions that have this posting profile.</span></span> <span data-ttu-id="5e1c1-183">Se esta opção for desmarcada, você deverá liquidar manualmente as transações usando a página Liquidar transações em aberto.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-183">If this option is cleared, you must manually settle transactions by using the Settle open transactions page.</span></span> |
| <span data-ttu-id="5e1c1-184">**Cancelamento**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-184">**Cancel**</span></span>     | <span data-ttu-id="5e1c1-185">Selecione esta opção se você deseja ser capaz de cancelar as transações que possuem este perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-185">Select this option if you want to be able to cancel transactions that have this posting profile.</span></span>                                                                                                               |
| <span data-ttu-id="5e1c1-186">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="5e1c1-186">**Close**</span></span>      | <span data-ttu-id="5e1c1-187">Selecione um perfil de lançamento para o qual alternar quando as transações que tiverem este perfil de lançamento forem fechadas.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-187">Select a posting profile to change to when transactions that have this posting profile are closed.</span></span> <span data-ttu-id="5e1c1-188">Uma transação é considerada fechada quando tiver sido integralmente liquidada.</span><span class="sxs-lookup"><span data-stu-id="5e1c1-188">A transaction is regarded as closed when it has been settled in full.</span></span>                                       |






