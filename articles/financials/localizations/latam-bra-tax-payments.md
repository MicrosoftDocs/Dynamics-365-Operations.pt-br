---
title: Pagamentos de impostos no Brasil
description: "Este tópico fornece informações sobre pagamentos de impostos no Brasil. No Brasil, os usuários podem registrar e lançar pagamentos de impostos junto com as informações fiscais relacionadas que será reportadas às autoridades fiscais."
author: sndray
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FBTaxAssessmentPayment_BR, FBTaxAssessmentPaymentOtherDebits_BR
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 270254
ms.assetid: 92223189-69a8-4a40-b867-ef9b4f14c23d
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 84fa30694142fce091cb64203e9fd60f1b2c4654
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="tax-payments-in-brazil"></a><span data-ttu-id="51d57-104">Pagamentos de impostos no Brasil</span><span class="sxs-lookup"><span data-stu-id="51d57-104">Tax payments in Brazil</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="51d57-105">Este tópico fornece informações sobre pagamentos de impostos no Brasil.</span><span class="sxs-lookup"><span data-stu-id="51d57-105">This topic provides information about tax payments in Brazil.</span></span> <span data-ttu-id="51d57-106">No Brasil, os usuários podem registrar e lançar pagamentos de impostos junto com as informações fiscais relacionadas que será reportadas às autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="51d57-106">In Brazil, users can register and post tax payments together with related fiscal information that must be reported to the tax authorities.</span></span>

<a name="overview"></a><span data-ttu-id="51d57-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="51d57-107">Overview</span></span>
--------

<span data-ttu-id="51d57-108">Cada tipo de imposto no Brasil tem seu próprio processo, data de vencimento e informações adicionais de demonstrativo de imposto que é exigido pelas autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="51d57-108">Every type of tax in Brazil has its own process, due date, and additional tax statement information that is required by the tax authorities.</span></span> <span data-ttu-id="51d57-109">O módulo **Livros fiscais** gera as instruções do Sistema Público de Escrituração Digital (SPED) obrigatórias para os impostos.</span><span class="sxs-lookup"><span data-stu-id="51d57-109">The **Fiscal books** module generates the Sistema Publico de Escrituração Digital (SPED) statements that are required for taxes.</span></span> <span data-ttu-id="51d57-110">O processo de pagamento de impostos é separado por tipos de imposto: ICMS, ICMS-ST, ICMS-DIF, IPI, ISS e PIS-COFINS.</span><span class="sxs-lookup"><span data-stu-id="51d57-110">The tax payment process is separated by tax types: ICMS, ICMS-ST, ICMS-DIF, IPI, ISS, and PIS-COFINS.</span></span>

-   <span data-ttu-id="51d57-111">ICMS, ICMS-ST e ICMS-DIF são impostos estaduais relacionados à movimentação de mercadorias.</span><span class="sxs-lookup"><span data-stu-id="51d57-111">ICMS, ICMS-ST, and ICMS-DIF are state taxes that are related to merchandise movement.</span></span>
-   <span data-ttu-id="51d57-112">ISS é um imposto municipal que é cobrado pela cidade.</span><span class="sxs-lookup"><span data-stu-id="51d57-112">ISS is a city tax that is charged by the city.</span></span>
-   <span data-ttu-id="51d57-113">IPI é um imposto de produção que é cobrado pelo governo federal.</span><span class="sxs-lookup"><span data-stu-id="51d57-113">IPI is a production tax that is charged by the federal government.</span></span> <span data-ttu-id="51d57-114">O governo federal também é responsável pelos impostos PIS e COFINS que são aplicados aos produtos.</span><span class="sxs-lookup"><span data-stu-id="51d57-114">The federal government is also responsible for the PIS and COFINS taxes that are applied to products.</span></span>

<span data-ttu-id="51d57-115">A diferença entre o valor do imposto arrecadado em vendas de mercadorias e o valor do imposto ICMS pago em compras de mercadorias é calculada.</span><span class="sxs-lookup"><span data-stu-id="51d57-115">The difference between the tax amount that is collected on sales of goods and the ICMS tax amount that is paid on purchases of goods is calculated.</span></span> <span data-ttu-id="51d57-116">Se o valor líquido for uma obrigação fiscal, uma entrada de diário de nota fiscal do fornecedor poderá ser criada.</span><span class="sxs-lookup"><span data-stu-id="51d57-116">If the net amount is a tax liability, a vendor invoice journal entry can be created.</span></span> <span data-ttu-id="51d57-117">Depois, o valor do imposto devido à autoridade fiscal é pago.</span><span class="sxs-lookup"><span data-stu-id="51d57-117">Then the amount of tax that is owed to the tax authority is paid.</span></span> <span data-ttu-id="51d57-118">Para pagar impostos, uma apuração do imposto relacionado é criada.</span><span class="sxs-lookup"><span data-stu-id="51d57-118">To pay the taxes, a related tax assessment is created.</span></span> <span data-ttu-id="51d57-119">A apuração de imposto coleta informações das transações para o período correto, conforme exigido pelo imposto.</span><span class="sxs-lookup"><span data-stu-id="51d57-119">The tax assessment collects information from the transactions for the correct time frame, as required by the tax.</span></span> <span data-ttu-id="51d57-120">Na página **Apuração de imposto**, você seleciona o imposto desejado.</span><span class="sxs-lookup"><span data-stu-id="51d57-120">On the **Tax assessment** page, you select the tax to work with.</span></span> <span data-ttu-id="51d57-121">Na página **Pagamento de imposto**, você gera o pagamento do imposto relacionado.</span><span class="sxs-lookup"><span data-stu-id="51d57-121">On the **Tax payment** page, you generate the related tax payment.</span></span> <span data-ttu-id="51d57-122">Dependendo do requisito de cobrança, há duas maneiras de criar o pagamento de impostos:</span><span class="sxs-lookup"><span data-stu-id="51d57-122">Depending on the collection requirement, there are two ways to create the tax payment:</span></span>

-   <span data-ttu-id="51d57-123">**Criar a partir da apuração** – Coletar e pagar imposto mensalmente, de acordo com as regras que são estabelecidas pela autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="51d57-123">**Create from assessment** – Collect and pay tax monthly, in accordance with the rules that are established by the tax authority.</span></span>
-   <span data-ttu-id="51d57-124">**Outros débitos** – coletar e pagar um determinado valor de imposto fora do processo normal quando a autoridade de imposto requer o pagamento.</span><span class="sxs-lookup"><span data-stu-id="51d57-124">**Other debits** – Collect and pay a specific tax amount outside the regular process when the tax authority requires the payment.</span></span>

![Criando pagamentos de impostos](./media/taxpaymentsbra.jpg) 


### <a name="overview"></a><span data-ttu-id="51d57-126">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="51d57-126">Overview</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51d57-127">Campo</span><span class="sxs-lookup"><span data-stu-id="51d57-127">Field</span></span></th>
<th><span data-ttu-id="51d57-128">descrição</span><span class="sxs-lookup"><span data-stu-id="51d57-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="51d57-129">Tipo de Pagamento</span><span class="sxs-lookup"><span data-stu-id="51d57-129">Payment type</span></span></td>
<td><span data-ttu-id="51d57-130">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="51d57-130">Select one of the following options:</span></span>
<ul>
<li><span data-ttu-id="51d57-131"><strong>Periódico</strong> – Cria um pagamento periódico mensal (regular).</span><span class="sxs-lookup"><span data-stu-id="51d57-131"><strong>Periodic</strong> – Create a monthly periodic payment (regular).</span></span> <span data-ttu-id="51d57-132">Todas as transações de impostos gerados de notas fiscais, e todos ajustes de transação (geral ou por documento fiscal) em que a configurações especiais do débito de ajuste não são marcadas, são resumidas para gerar pagamento periódico.</span><span class="sxs-lookup"><span data-stu-id="51d57-132">All tax transactions that are generated from fiscal documents, and all transaction adjustments (general or by fiscal document) where the special debit configuration of adjustment isn't marked, are summarized to generate the periodic payment.</span></span></li>
<li><span data-ttu-id="51d57-133"><strong>Outros débitos</strong> – Faz um pagamento específico de ICMS fora do processo normal, porque o pagamento é solicitado por lei.</span><span class="sxs-lookup"><span data-stu-id="51d57-133"><strong>Other debits</strong> – Make a specific payment of ICMS outside the regular process, because the payment is required by law.</span></span> <span data-ttu-id="51d57-134">Os exemplos incluem diferencial % do ICMS e Importação de mercadorias.</span><span class="sxs-lookup"><span data-stu-id="51d57-134">Examples include differential of % ICMS and Import goods.</span></span> <span data-ttu-id="51d57-135">Todas as transações de ajuste marcadas como <strong>Pagamento de outros débitos</strong> na configuração são resumidas para gerar um pagamento.</span><span class="sxs-lookup"><span data-stu-id="51d57-135">All adjustment transactions that are marked as <strong>Other debit payment</strong> in the configuration are summarized to generate a payment.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51d57-136">Data</span><span class="sxs-lookup"><span data-stu-id="51d57-136">Date</span></span></td>
<td><span data-ttu-id="51d57-137">A data do pagamento.</span><span class="sxs-lookup"><span data-stu-id="51d57-137">The payment date.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="51d57-138">Código do ICMS a recolher</span><span class="sxs-lookup"><span data-stu-id="51d57-138">ICMS to pay code</span></span></td>
<td><span data-ttu-id="51d57-139">O código de pagamento do ICMS que as autoridades fiscais exigem.</span><span class="sxs-lookup"><span data-stu-id="51d57-139">The ICMS to pay code that the tax authorities require.</span></span> <span data-ttu-id="51d57-140">Este campo está disponível apenas para impostos ICMS, ICMS-ST e ICMS-DIF.</span><span class="sxs-lookup"><span data-stu-id="51d57-140">This field is available only for ICMS, ICMS-ST, and ICMS-DIF taxes.</span></span> <span data-ttu-id="51d57-141">As opções a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="51d57-141">The following options are available:</span></span>
<ul>
<li><span data-ttu-id="51d57-142">000: ICMS a coletar</span><span class="sxs-lookup"><span data-stu-id="51d57-142">000: ICMS to collect</span></span></li>
<li><span data-ttu-id="51d57-143">003: Antecipação de parte diferencial de alíquota</span><span class="sxs-lookup"><span data-stu-id="51d57-143">003: Anticipation of Aliquot differential</span></span></li>
<li><span data-ttu-id="51d57-144">004: Antecipação de mercadorias de importação</span><span class="sxs-lookup"><span data-stu-id="51d57-144">004: Anticipation of Import goods</span></span></li>
<li><span data-ttu-id="51d57-145">005: Antecipação de impostos</span><span class="sxs-lookup"><span data-stu-id="51d57-145">005: Anticipate tax</span></span></li>
<li><span data-ttu-id="51d57-146">006: Antecipação de ICMS adicional</span><span class="sxs-lookup"><span data-stu-id="51d57-146">006: Anticipation of additional ICMS</span></span></li>
<li><span data-ttu-id="51d57-147">090: Outras obrigações</span><span class="sxs-lookup"><span data-stu-id="51d57-147">090: Other obligations</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51d57-148">Código da receita</span><span class="sxs-lookup"><span data-stu-id="51d57-148">Receita code</span></span></td>
<td><span data-ttu-id="51d57-149">A classificação de pagamento, conforme definido pelas autoridades fiscais estaduais.</span><span class="sxs-lookup"><span data-stu-id="51d57-149">The classification of the payment, as defined by the state tax authorities.</span></span> <span data-ttu-id="51d57-150">O programa deve oferecer o código de receita mais recente usado nas transações anteriores.</span><span class="sxs-lookup"><span data-stu-id="51d57-150">The program must offer the latest receita code that is used in the previous transactions.</span></span> <span data-ttu-id="51d57-151">Os códigos de receita variam, dependendo do tipo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="51d57-151">Receita codes vary, depending on the payment type.</span></span> <span data-ttu-id="51d57-152">Se selecionar <strong>Outros débitos</strong> como o tipo de pagamento, o código de receita será inserido automaticamente as transações de ajuste, desde que as transações de ajuste possuam um código padrão de receita.</span><span class="sxs-lookup"><span data-stu-id="51d57-152">If you select <strong>Other debits</strong> as the payment type, the receita code is entered automatically from the adjustment transactions, provided that the adjustment transactions have a default receita code.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="51d57-153">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="51d57-153">Due date</span></span></td>
<td><span data-ttu-id="51d57-154">A data de vencimento do pagamento.</span><span class="sxs-lookup"><span data-stu-id="51d57-154">The due date of the payment.</span></span> <span data-ttu-id="51d57-155">Se o campo <strong>Condições de pagamento</strong> estiver em branco, você deve inserir um valor neste campo.</span><span class="sxs-lookup"><span data-stu-id="51d57-155">If the <strong>Terms of payment</strong> field is blank, you must enter a value in this field.</span></span> <span data-ttu-id="51d57-156">Caso contrário, o valor será definido como a data de vencimento que é gerada com base nas condições de pagamento.</span><span class="sxs-lookup"><span data-stu-id="51d57-156">Otherwise, the value is set to the due date that is generated based on terms of payment.</span></span> <span data-ttu-id="51d57-157">Depois que a integração do razão for ativada, a data de vencimento da transação do razão será inserida.</span><span class="sxs-lookup"><span data-stu-id="51d57-157">After ledger integration is activated, the due date in the ledger transaction will be entered.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51d57-158">Valor do imposto</span><span class="sxs-lookup"><span data-stu-id="51d57-158">Sales tax amount</span></span></td>
<td><span data-ttu-id="51d57-159">O valor total do ICMS a pagar.</span><span class="sxs-lookup"><span data-stu-id="51d57-159">The total amount of ICMS to pay.</span></span> <span data-ttu-id="51d57-160">O valor é calculado com base no tipo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="51d57-160">The amount is calculated based on the payment type.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="51d57-161">Valor dos juros</span><span class="sxs-lookup"><span data-stu-id="51d57-161">Interest amount</span></span></td>
<td><span data-ttu-id="51d57-162">O valor dos juros no caso de pagamentos atrasados.</span><span class="sxs-lookup"><span data-stu-id="51d57-162">The amount of interest in the event of late payments.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51d57-163">Valor da multa</span><span class="sxs-lookup"><span data-stu-id="51d57-163">Fine amount</span></span></td>
<td><span data-ttu-id="51d57-164">O valor de multas, no caso de pagamentos atrasados.</span><span class="sxs-lookup"><span data-stu-id="51d57-164">The amount of fines in the event of late payments.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="51d57-165">Valor</span><span class="sxs-lookup"><span data-stu-id="51d57-165">Amount</span></span></td>
<td><span data-ttu-id="51d57-166">A soma do valor do imposto, o valor dos juros e o valor da multa.</span><span class="sxs-lookup"><span data-stu-id="51d57-166">The sum of the sales tax amount, interest amount, and fine amount.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51d57-167">Mês de referência</span><span class="sxs-lookup"><span data-stu-id="51d57-167">Reference month</span></span></td>
<td><span data-ttu-id="51d57-168">O mês de referência para este pagamento de ICMS, como <strong>012017</strong>.</span><span class="sxs-lookup"><span data-stu-id="51d57-168">The reference month for this ICMS tax payment, such as <strong>012017</strong>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="51d57-169">Comprovante</span><span class="sxs-lookup"><span data-stu-id="51d57-169">Voucher</span></span></td>
<td><span data-ttu-id="51d57-170">O número do comprovante.</span><span class="sxs-lookup"><span data-stu-id="51d57-170">The voucher number.</span></span> <span data-ttu-id="51d57-171">Esse número é atribuído automaticamente quando o pagamento é lançado e a integração do razão é ativada.</span><span class="sxs-lookup"><span data-stu-id="51d57-171">This number is automatically assigned when the payment is posted and the ledger integration is activated.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="general"></a><span data-ttu-id="51d57-172">Geral</span><span class="sxs-lookup"><span data-stu-id="51d57-172">General</span></span>

| <span data-ttu-id="51d57-173">Campo</span><span class="sxs-lookup"><span data-stu-id="51d57-173">Field</span></span>                     | <span data-ttu-id="51d57-174">descrição</span><span class="sxs-lookup"><span data-stu-id="51d57-174">Description</span></span>                                                                                                                                                                                             |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="51d57-175">descrição</span><span class="sxs-lookup"><span data-stu-id="51d57-175">Description</span></span>               | <span data-ttu-id="51d57-176">Insira uma descrição para o pagamento de imposto.</span><span class="sxs-lookup"><span data-stu-id="51d57-176">Enter a description for the sales tax payments.</span></span>                                                                                                                                                         |
| <span data-ttu-id="51d57-177">Autoridade fiscal</span><span class="sxs-lookup"><span data-stu-id="51d57-177">Authority</span></span>                 | <span data-ttu-id="51d57-178">Selecione a autoridade fiscal na qual a apuração do imposto foi criada.</span><span class="sxs-lookup"><span data-stu-id="51d57-178">Select the tax authority where the tax assessment is created.</span></span> <span data-ttu-id="51d57-179">A autoridade fiscal define um número de conta de fornecedor usada para transferir pagamentos de impostos ao fornecedor que faz o pagamento.</span><span class="sxs-lookup"><span data-stu-id="51d57-179">The sales tax authority defines a vendor account number that is used to transfer sales tax payments to the vendor that makes the payment.</span></span> |
| <span data-ttu-id="51d57-180">Condições de pagamento</span><span class="sxs-lookup"><span data-stu-id="51d57-180">Terms of payment</span></span>          | <span data-ttu-id="51d57-181">As condições de pagamento que são usadas para determinar a data de vencimento de um pagamento de imposto.</span><span class="sxs-lookup"><span data-stu-id="51d57-181">The terms of payment that are used to determine the due date of a sales tax payment.</span></span> <span data-ttu-id="51d57-182">As condições de pagamento que você selecionar aqui serão usadas para a fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="51d57-182">The terms of payment that you select here will be used for the vendor invoice.</span></span>                                     |
| <span data-ttu-id="51d57-183">Empresa</span><span class="sxs-lookup"><span data-stu-id="51d57-183">Company</span></span>                   | <span data-ttu-id="51d57-184">A entidade legal na qual a transação de pagamento de imposto será lançada, se a integração do razão for ativada.</span><span class="sxs-lookup"><span data-stu-id="51d57-184">The legal entity where the tax payment transaction will be posted if ledger integration is activated.</span></span>                                                                                                   |
| <span data-ttu-id="51d57-185">Revertido</span><span class="sxs-lookup"><span data-stu-id="51d57-185">Reversed</span></span>                  | <span data-ttu-id="51d57-186">Uma opção selecionada indica que o pagamento do imposto foi revertido.</span><span class="sxs-lookup"><span data-stu-id="51d57-186">A selected option indicates that the tax payment was reversed.</span></span>                                                                                                                                          |
| <span data-ttu-id="51d57-187">Número de rastreamento</span><span class="sxs-lookup"><span data-stu-id="51d57-187">Trace number</span></span>              | <span data-ttu-id="51d57-188">O número de rastreamento do pagamento revertido.</span><span class="sxs-lookup"><span data-stu-id="51d57-188">The trace number for the reversed payment.</span></span>                                                                                                                                                              |
| <span data-ttu-id="51d57-189">Número do processo referenciado</span><span class="sxs-lookup"><span data-stu-id="51d57-189">Referenced process number</span></span> | <span data-ttu-id="51d57-190">O número do processo referenciado.</span><span class="sxs-lookup"><span data-stu-id="51d57-190">The referenced process number.</span></span>                                                                                                                                                                          |
| <span data-ttu-id="51d57-191">Agência</span><span class="sxs-lookup"><span data-stu-id="51d57-191">Agency</span></span>                    | <span data-ttu-id="51d57-192">A agência a qual o processo referenciado pertence.</span><span class="sxs-lookup"><span data-stu-id="51d57-192">The agency that the referenced process belongs to.</span></span>                                                                                                                                                      |
| <span data-ttu-id="51d57-193">descrição</span><span class="sxs-lookup"><span data-stu-id="51d57-193">Description</span></span>               | <span data-ttu-id="51d57-194">A descrição do processo referenciado.</span><span class="sxs-lookup"><span data-stu-id="51d57-194">The description of the referenced process.</span></span>                                                                                                                                                              |

#### <a name="tax-payments"></a><span data-ttu-id="51d57-195">Pagamentos de imposto</span><span class="sxs-lookup"><span data-stu-id="51d57-195">Tax payments</span></span>

<span data-ttu-id="51d57-196">Os pagamentos de impostos a seguir podem ser feitos na página **Pagamento de imposto** (**Livros fiscais** &gt; **Comum** &gt; **Período de escrituração** &gt; **Apuração**):</span><span class="sxs-lookup"><span data-stu-id="51d57-196">The following tax payments can be made on the **Tax payment** page (**Fiscal books** &gt; **Common** &gt; **Booking period** &gt; **Assessment**):</span></span>

-   <span data-ttu-id="51d57-197">Apuração de imposto ICMS ou ICMS-ST</span><span class="sxs-lookup"><span data-stu-id="51d57-197">ICMS or ICMS-ST tax assessment</span></span>
-   <span data-ttu-id="51d57-198">Pagamento de IPI</span><span class="sxs-lookup"><span data-stu-id="51d57-198">IPI tax payment</span></span>
-   <span data-ttu-id="51d57-199">Pagamento de ICMS-DIF</span><span class="sxs-lookup"><span data-stu-id="51d57-199">ICMS-DIF tax payment</span></span>
-   <span data-ttu-id="51d57-200">Pagamento de ISS</span><span class="sxs-lookup"><span data-stu-id="51d57-200">ISS tax payment</span></span>
-   <span data-ttu-id="51d57-201">Pagamento de PIS e COFINS - Um pagamento é feito para PIS e outro para COFINS.</span><span class="sxs-lookup"><span data-stu-id="51d57-201">PIS and COFINS tax payment – One payment is made for PIS tax, and another payment is made for COFINS tax.</span></span> <span data-ttu-id="51d57-202">O tipo de regime de PIS e COFINS é mostrado na seção **Visão geral** do pagamento de imposto.</span><span class="sxs-lookup"><span data-stu-id="51d57-202">The type of PIS and COFINS regime is shown in the **Overview** section of the tax payment.</span></span> <span data-ttu-id="51d57-203">Um pagamento pode ser relacionado ao regime cumulativo, regime não cumulativo ou ambos.</span><span class="sxs-lookup"><span data-stu-id="51d57-203">A payment can be related to the cumulative regime, the non-cumulative regime, or both regimes.</span></span>

## <a name="reversing-tax-payments"></a><span data-ttu-id="51d57-204">Revertendo pagamentos de impostos</span><span class="sxs-lookup"><span data-stu-id="51d57-204">Reversing tax payments</span></span>
<span data-ttu-id="51d57-205">Você pode reverter a transação para um pagamento de impostos que foi lançado, selecionando o pagamento de impostos e clicando em **Transação**.</span><span class="sxs-lookup"><span data-stu-id="51d57-205">You can reverse the transaction for a tax payment that has been posted by selecting the tax payment and clicking **Transaction**.</span></span> <span data-ttu-id="51d57-206">O processo de reversão de transação reverte a transação original e todas as transações relacionadas criadas quando a transação original foi lançada.</span><span class="sxs-lookup"><span data-stu-id="51d57-206">The transaction reversal process reverses the original transaction and all related transactions that were created when the original transaction was posted.</span></span> <span data-ttu-id="51d57-207">A sequência numérica para as referências do número de rastreamento e reversão da transação nas sequências numéricas deve ser configurada para permitir o registro das reversões.</span><span class="sxs-lookup"><span data-stu-id="51d57-207">The number sequence for the transaction reversal and trace number references in the number sequences must be configured to allow for the registration of reversals.</span></span> <span data-ttu-id="51d57-208">Os pagamentos de impostos existentes podem ser revertidos nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="51d57-208">Existing tax payments can be reversed under the following conditions:</span></span>

-   <span data-ttu-id="51d57-209">A integração do razão com os Livros fiscais é ativada na página **Integração do razão**.</span><span class="sxs-lookup"><span data-stu-id="51d57-209">Ledger integration with Fiscal books is activated on the **Ledger integration** page.</span></span>
-   <span data-ttu-id="51d57-210">O passivo que é gerado quando o pagamento do imposto for lançado ainda está em aberto.</span><span class="sxs-lookup"><span data-stu-id="51d57-210">The liability that is generated when the tax payment was posted is still in open.</span></span> <span data-ttu-id="51d57-211">Além disso, o saldo atual da conta do fornecedor da autoridade fiscal deve ser maior ou menor que 0,00</span><span class="sxs-lookup"><span data-stu-id="51d57-211">Additionally, the current balance in the vendor account of the tax authority must be greater than or less than 0.00</span></span>

<span data-ttu-id="51d57-212">Quando um pagamento de imposto for revertido, o status da transação original é definido como **Revertido** e o número de sequência relacionado é inserido no campo **Número de rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="51d57-212">When a tax payment is reversed, the status of the original transaction is set to **Reverse**, and the related sequence number is entered in the **Trace number** field.</span></span>

## <a name="deleting-tax-payments"></a><span data-ttu-id="51d57-213">Excluindo pagamentos de impostos</span><span class="sxs-lookup"><span data-stu-id="51d57-213">Deleting tax payments</span></span>
<span data-ttu-id="51d57-214">Você pode excluir pagamentos de impostos se o número do comprovante não estiver em branco, quando a transação de pagamento for lançada.</span><span class="sxs-lookup"><span data-stu-id="51d57-214">You can delete tax payments if the voucher number wasn't blank when the payment transaction was posted.</span></span>

<span data-ttu-id="51d57-215">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="51d57-215">For more information, see the following topics:</span></span>

 - [<span data-ttu-id="51d57-216">Configurar juros e multas para pagamentos de fornecedores</span><span class="sxs-lookup"><span data-stu-id="51d57-216">Set up interest and fines for vendor payments</span></span>](tasks/br-00065-1-set-up-interest-fines-vendor-payments.md)
 - [<span data-ttu-id="51d57-217">Calcular juros e multas sobre pagamentos de fornecedores</span><span class="sxs-lookup"><span data-stu-id="51d57-217">Calculate interest and fines on vendor payments</span></span>](tasks/br-00065-2-calculate-interest-fines-vendor-payments.md)
 - [<span data-ttu-id="51d57-218">Configurar juros e multas em pagamentos de clientes</span><span class="sxs-lookup"><span data-stu-id="51d57-218">Set up interest and fines on customer payments</span></span>](tasks/br-00066-1-set-up-interest-fines-customer-payments.md)
 - [<span data-ttu-id="51d57-219">Calcular juros e multas em pagamentos de clientes</span><span class="sxs-lookup"><span data-stu-id="51d57-219">Calculate interest and fines on customer payments</span></span>](tasks/br-00066-2-calculate-interest-fines-customer-payments.md)



