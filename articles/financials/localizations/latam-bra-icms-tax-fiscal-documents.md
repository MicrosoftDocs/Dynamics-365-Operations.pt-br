---
title: Notas fiscais de transferência ou apropriação de imposto ICMS para o Brasil
description: Este tópico explica o conceito de notas fiscais de transferência ou apropriação de imposto e descreve os requisitos para gerá-las.
author: sndray
manager: AnnBe
ms.date: 08/08/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxFiscalDocument_BR, TaxFiscalDocumentCancel_BR, TaxFiscalDocumentListPage_BR, TaxFiscalDocumentPost_BR
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 269524
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e6b2792d645a42a616439a143550250a7c5019c3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555185"
---
# <a name="icms-tax-fiscal-documents-for-brazil"></a><span data-ttu-id="47f32-103">Notas fiscais de transferência ou apropriação de imposto ICMS para o Brasil</span><span class="sxs-lookup"><span data-stu-id="47f32-103">ICMS tax fiscal documents for Brazil</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="47f32-104">Este tópico explica o conceito de notas fiscais de transferência ou apropriação de imposto e descreve os requisitos para gerá-las.</span><span class="sxs-lookup"><span data-stu-id="47f32-104">This topic explains the concept of tax fiscal documents and describes the requirements for generating them.</span></span>

<span data-ttu-id="47f32-105">No Brasil, alguns tipos de notas fiscais não têm efeito em fornecedores, clientes ou saldos de estoque.</span><span class="sxs-lookup"><span data-stu-id="47f32-105">In Brazil, some types of fiscal documents have no effect on vendors, customers, or inventory balances.</span></span> <span data-ttu-id="47f32-106">Normalmente, a finalidade dessas notas fiscais é habilitar entidades legais para especificar ajustes de impostos para transferi-las, entre outras subsidiárias, ou recuperar impostos (imposto a receber) em prestações durante um período.</span><span class="sxs-lookup"><span data-stu-id="47f32-106">In general, the purpose of these fiscal documents is to enable legal entities to enter tax adjustments, transfer between other subsidiaries, or recover taxes (sales tax receivables) in installments for a period.</span></span> <span data-ttu-id="47f32-107">Para registrar essas operações na entidade legal, notas fiscais específicas devem ser geradas que afetam o relatório de Contabilidade e os livros fiscais.</span><span class="sxs-lookup"><span data-stu-id="47f32-107">To register these operations in the legal entity, specific fiscal documents must be generated that affect the General ledger and fiscal books reporting.</span></span>

## <a name="imposto-sobre-circulao-de-mercadorias-e-servios-icms-tax-transfers-between-subsidiaries"></a><span data-ttu-id="47f32-108">Transferências do Imposto sobre Circulação de Mercadorias e Serviços (ICMS) entre subsidiárias</span><span class="sxs-lookup"><span data-stu-id="47f32-108">Imposto sobre Circulação de Mercadorias e Serviços (ICMS) tax transfers between subsidiaries</span></span>
<span data-ttu-id="47f32-109">Este tipo de impostos é considerado um imposto recuperável e as regulamentações de imposto de renda corporativo não permitem que o imposto ICMS seja deduzido.</span><span class="sxs-lookup"><span data-stu-id="47f32-109">This type of tax is considered a recoverable tax and corporate income tax regulations don't allow ICMS tax to be deducted.</span></span> <span data-ttu-id="47f32-110">Portanto, os créditos acumulados do ICMS não podem ser usados para diminuir o valor tributável para avaliação de impostos sobre rendimento corporativo (IRPJ e CSSL).</span><span class="sxs-lookup"><span data-stu-id="47f32-110">Therefore, accumulated ICMS tax credits can't be used to decrease the taxable amount for the assessment of corporate income taxes (IRPJ and CSSL).</span></span> <span data-ttu-id="47f32-111">Os modos de acumular créditos de ICMS incluem:</span><span class="sxs-lookup"><span data-stu-id="47f32-111">Ways to accumulate ICMS tax credits include:</span></span>

-   <span data-ttu-id="47f32-112">Exportação – isenção de ICMS</span><span class="sxs-lookup"><span data-stu-id="47f32-112">Exportation – ICMS tax–free</span></span>
-   <span data-ttu-id="47f32-113">Diferimentos</span><span class="sxs-lookup"><span data-stu-id="47f32-113">Deferrals</span></span>
-   <span data-ttu-id="47f32-114">Taxa reduzida</span><span class="sxs-lookup"><span data-stu-id="47f32-114">Reduced rate</span></span>
-   <span data-ttu-id="47f32-115">Créditos presumidos</span><span class="sxs-lookup"><span data-stu-id="47f32-115">Presumed credits</span></span>

<span data-ttu-id="47f32-116">Há várias opções para gerenciar como os créditos acumulados de ICMS são usados quando o saldo devido resultante é maior que o débito/crédito acumulado.</span><span class="sxs-lookup"><span data-stu-id="47f32-116">There are several options for managing how accumulated ICMS tax credits are used when the resulting balance due is greater than the debt accumulated credit.</span></span> <span data-ttu-id="47f32-117">O crédito de imposto ICMS acumulado pode ser transferido nestas situações:</span><span class="sxs-lookup"><span data-stu-id="47f32-117">The accumulated ICMS tax credit can be transferred in the following situations:</span></span>

-   <span data-ttu-id="47f32-118">Transferir o crédito de ICMS para outras subsidiárias que têm um maior volume de transações onde o ICMS é devido.</span><span class="sxs-lookup"><span data-stu-id="47f32-118">Transfer the ICMS tax credit to other subsidiaries that have a higher volume of transactions where the ICMS is due.</span></span> <span data-ttu-id="47f32-119">Isso se aplica apenas às subsidiárias localizadas no mesmo estado.</span><span class="sxs-lookup"><span data-stu-id="47f32-119">This only applies to subsidiaries located in the same state.</span></span>
-   <span data-ttu-id="47f32-120">Transferir o crédito de ICMS para pagar contas de fornecedor em operações de compra por material bruto e secundário, pacotes de equipamento e, equipamento industrial.</span><span class="sxs-lookup"><span data-stu-id="47f32-120">Transfer the ICMS tax credit to pay vendor accounts in purchase operations for raw and secondary material, equipment packages, and industrial equipment.</span></span>
-   <span data-ttu-id="47f32-121">Transferir o crédito de ICMS para outras subsidiárias.</span><span class="sxs-lookup"><span data-stu-id="47f32-121">Transfer the ICMS tax credit to other subsidiaries.</span></span> <span data-ttu-id="47f32-122">Até 30% de cada operação de ativo fixo que é destinada para ativos fixos permanentes pode ser transferido.</span><span class="sxs-lookup"><span data-stu-id="47f32-122">Up to the 30 percent of each fixed asset operation that is intended for permanent fixed assets can be transferred.</span></span>
-   <span data-ttu-id="47f32-123">Pagamento de aquisição de chassi do caminhão com novo motor, ou combustível, feito pelo estabelecimento de transporte rodoviário.</span><span class="sxs-lookup"><span data-stu-id="47f32-123">Payment of truck chassis acquisition with new engine, or fuel, made by the establishment of road transport.</span></span>
-   <span data-ttu-id="47f32-124">Transferir o crédito de ICMS de uma empresa que fabrique álcool etílico a empresa que cooperativa centraliza vendas.</span><span class="sxs-lookup"><span data-stu-id="47f32-124">Transfer the ICMS tax credit from a company that manufactures ethanol to the cooperative company that centralizes sales.</span></span> <span data-ttu-id="47f32-125">Até 30 dos impostos cobrados na remessa desse produto podem ser transferidos.</span><span class="sxs-lookup"><span data-stu-id="47f32-125">Up to 30 percent of the tax that is charged in the shipment of that product can be transferred.</span></span>
-   <span data-ttu-id="47f32-126">Transferir o crédito de ICMS para o estabelecimento industrial de óleo bruto.</span><span class="sxs-lookup"><span data-stu-id="47f32-126">Transfer the ICMS tax credit for the industrial establishment of crude oil.</span></span>

<span data-ttu-id="47f32-127">Nessas situações, o valor que uma empresa pode obter do ICMS acumulado depende de regras específicas estabelecidas pelo governo.</span><span class="sxs-lookup"><span data-stu-id="47f32-127">In these situations, the amount that a company that can take from the accumulated ICMS tax depends on specific rules that are established by the government.</span></span> <span data-ttu-id="47f32-128">O valor não é aplicável sempre a 100% do valor de ICMS acumulado.</span><span class="sxs-lookup"><span data-stu-id="47f32-128">The amount isn't always applicable to 100 percent of the accumulated ICMS tax amount.</span></span> <span data-ttu-id="47f32-129">Os créditos de ICMS são transferidos pela emissão de uma nota fiscal que é conhecida como nota fiscal de transferência ou apropriação de imposto.</span><span class="sxs-lookup"><span data-stu-id="47f32-129">ICMS tax credits are transferred by the issuing a fiscal document that is known as a tax fiscal document.</span></span> <span data-ttu-id="47f32-130">Esse documento deve incluir informações específicas que refletem a operação.</span><span class="sxs-lookup"><span data-stu-id="47f32-130">This document must include specific information that reflects the operation.</span></span> <span data-ttu-id="47f32-131">O contribuinte também pode emitir uma nota fiscal eletrônica (NF-e) para transferir o crédito de ICMS acumulado para outra subsidiária.</span><span class="sxs-lookup"><span data-stu-id="47f32-131">The taxpayer can also issue an electronic invoice nota fiscal elêtronica (NF-e) to transfer the accumulated ICMS tax credit to another subsidiary.</span></span>

## <a name="recovering-icms-tax-in-installments"></a><span data-ttu-id="47f32-132">Recuperando ICMS em parcelas</span><span class="sxs-lookup"><span data-stu-id="47f32-132">Recovering ICMS tax in installments</span></span>
<span data-ttu-id="47f32-133">De acordo com a lei brasileira nº 102/2000, a partir de 1º de janeiro de 2001, os créditos de ICMS decorrentes da compra de ativos fixos que são usados especificamente na atividade relacionada à tributação do ICMS pode ser apropriados em 1/48 por mês.</span><span class="sxs-lookup"><span data-stu-id="47f32-133">In accordance with Brazilian law No 102/2000, starting January 1, 2001, ICMS tax credits that arise from the purchase of fixed assets that are used specifically in activity that is related to taxation of ICMS can be appropriated 1/48 per month.</span></span> <span data-ttu-id="47f32-134">Portanto, o crédito de ICMS não pode ser completamente recuperado quando o usuário registra a compra.</span><span class="sxs-lookup"><span data-stu-id="47f32-134">Therefore, the ICMS tax credit can't be completely recovered when the user records the purchase.</span></span> <span data-ttu-id="47f32-135">Em vez disso, o crédito de ICMS deve ser recuperado em 48 parcelas ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="47f32-135">Instead, the ICMS tax credit must be recovered in 48 installments over time.</span></span> <span data-ttu-id="47f32-136">Veja a seguir um exemplo:</span><span class="sxs-lookup"><span data-stu-id="47f32-136">Here is an example:</span></span>

-   <span data-ttu-id="47f32-137">Valor de aquisição de ativo: R$ 100.000, 00</span><span class="sxs-lookup"><span data-stu-id="47f32-137">Asset acquisition amount : R$ 100.000,00</span></span>
-   <span data-ttu-id="47f32-138">Valor do ICMS: R$ 12.000,00</span><span class="sxs-lookup"><span data-stu-id="47f32-138">ICMS tax amount: R$ 12.000,00</span></span>
-   <span data-ttu-id="47f32-139">Cálculo de IVA recuperável com a finalidade de distribuição em contas de ativos atuais e de contas a receber a long prazo:</span><span class="sxs-lookup"><span data-stu-id="47f32-139">VAT recoverable calculation for the purpose of distribution in the accounts of current assets and long-term receivables:</span></span>
    -   <span data-ttu-id="47f32-140">Ativo atual:</span><span class="sxs-lookup"><span data-stu-id="47f32-140">Current asset:</span></span>
        1.  <span data-ttu-id="47f32-141">R$ 12.000, 00 ÷ 48 meses = R$ 250,00</span><span class="sxs-lookup"><span data-stu-id="47f32-141">R$ 12.000,00 ÷ 48 months = R$ 250,00</span></span>
        2.  <span data-ttu-id="47f32-142">R$ 250,00 × 12 meses (1 ano) = R$ 3.000, 00</span><span class="sxs-lookup"><span data-stu-id="47f32-142">R$ 250,00 × 12 months (1 year) = R$ 3.000,00</span></span>
    -   <span data-ttu-id="47f32-143">Ativo a longo prazo:</span><span class="sxs-lookup"><span data-stu-id="47f32-143">Long-term asset:</span></span>
        1.  <span data-ttu-id="47f32-144">R$ 12.000, 00 ÷ 48 meses = R$ 250,00</span><span class="sxs-lookup"><span data-stu-id="47f32-144">R$ 12.000,00 ÷ 48 months = R$ 250,00</span></span>
        2.  <span data-ttu-id="47f32-145">R$ 250,00 × 36 meses (1 ano) = R$ 9.000, 00</span><span class="sxs-lookup"><span data-stu-id="47f32-145">R$ 250,00 × 36 months (1 year) = R$ 9.000,00</span></span>

<span data-ttu-id="47f32-146">No Microsoft Dynamics 365 for Operations, as entradas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="47f32-146">In Microsoft Dynamics 365 for Operations, the entries are as follows:</span></span>

<span data-ttu-id="47f32-147">**Compra de Ativo Fixo** **Microsoft Dynamics 365 for Finance and Operations: Fatura de Compra do Ativo de Recebimento**</span><span class="sxs-lookup"><span data-stu-id="47f32-147">**Purchase of Fixed Asset** **Microsoft Dynamics 365 for Finance and Operations: Receipt Asset Purchase invoice**</span></span>

<span data-ttu-id="47f32-148">**Ajuste de ICMS do ano** **Finance and Operations: Comprovante de diário manual** **(R$ 12.000,00 / 48 parcelas) \* 12 (meses)**</span><span class="sxs-lookup"><span data-stu-id="47f32-148">**ICMS Tax adjustment of year** **Finance and Operations: Manual Journal voucher** **(R$ 12.000,00 / 48 installments) \* 12 (months)**</span></span>

<span data-ttu-id="47f32-149">ICMS recuperável **longo prazo** (conta diferida)</span><span class="sxs-lookup"><span data-stu-id="47f32-149">Recoverable ICMS **long term** (deferred account)</span></span>

<span data-ttu-id="47f32-150">*R$ 12.000,00 D*</span><span class="sxs-lookup"><span data-stu-id="47f32-150">*R$ 12.000,00 D*</span></span>

<span data-ttu-id="47f32-151">ICMS recuperável **curto prazo** (conta diferida)</span><span class="sxs-lookup"><span data-stu-id="47f32-151">Recoverable ICMS **short term** (deferred account)</span></span>

<span data-ttu-id="47f32-152">R$ 3.000,00 D</span><span class="sxs-lookup"><span data-stu-id="47f32-152">R$ 3.000,00 D</span></span>

<span data-ttu-id="47f32-153">Ativo Fixo</span><span class="sxs-lookup"><span data-stu-id="47f32-153">Fixed Asset</span></span>

<span data-ttu-id="47f32-154">R$ 88.000, 00 C</span><span class="sxs-lookup"><span data-stu-id="47f32-154">R$ 88.000,00 C</span></span>

<span data-ttu-id="47f32-155">ICMS recuperável, longo prazo (conta diferida)</span><span class="sxs-lookup"><span data-stu-id="47f32-155">Recoverable ICMS long term (deferred account)</span></span>

<span data-ttu-id="47f32-156">*R$ 3.000,00 C*</span><span class="sxs-lookup"><span data-stu-id="47f32-156">*R$ 3.000,00 C*</span></span>

<span data-ttu-id="47f32-157">**Saldo de Ativo de longo prazo** (conta diferida): R$ 9.000,00</span><span class="sxs-lookup"><span data-stu-id="47f32-157">**Long term asset** (deferred account) balance: R$ 9.000,00</span></span>

<span data-ttu-id="47f32-158">**Ajuste de ICMS do mês** **Finance and Operations: Emissão de uma Nota fiscal de entrada**</span><span class="sxs-lookup"><span data-stu-id="47f32-158">**ICMS Tax adjustment of month** **Finance and Operations: Issue an Incoming Tax fiscal document**</span></span>

<span data-ttu-id="47f32-159">Conta de ICMS recuperável</span><span class="sxs-lookup"><span data-stu-id="47f32-159">Recoverable ICMS tax account</span></span>

<span data-ttu-id="47f32-160">R$ 250,00 D</span><span class="sxs-lookup"><span data-stu-id="47f32-160">R$ 250,00 D</span></span>

<span data-ttu-id="47f32-161">ICMS recuperável curto prazo (conta diferida)</span><span class="sxs-lookup"><span data-stu-id="47f32-161">Recoverable ICMS short term (deferred account)</span></span>

<span data-ttu-id="47f32-162">*R$ 250,00 C*</span><span class="sxs-lookup"><span data-stu-id="47f32-162">*R$ 250,00 C*</span></span>

<span data-ttu-id="47f32-163">Na página **Todas notas fiscais de transferência ou apropriação de imposto**, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47f32-163">On the **All tax fiscal documents** page, you can do the following:</span></span>

-   <span data-ttu-id="47f32-164">Criar e lançar uma nota fiscal de transferência ou apropriação de imposto para transferir o valor de ICMS a um cliente ou fornecedor, ou para recuperar o valor do imposto ICMS em prestações para compra de ativos fixos por uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="47f32-164">Create and post an ICMS tax fiscal document to transfer the ICMS tax amount to a customer or vendor, or to recover the ICMS tax amount in installments for the purchase of fixed assets by a legal entity.</span></span>
-   <span data-ttu-id="47f32-165">Adicionar texto da nota fiscal a uma nota fiscal de transferência ou apropriação de imposto ICMS.</span><span class="sxs-lookup"><span data-stu-id="47f32-165">Add fiscal document text to an ICMS tax fiscal document.</span></span>
-   <span data-ttu-id="47f32-166">Exibir as transações de comprovante que estão relacionadas a uma nota fiscal de transferência ou apropriação de imposto ICMS na página **Transações de comprovante**.</span><span class="sxs-lookup"><span data-stu-id="47f32-166">View the voucher transactions that are related to an ICMS tax fiscal document on the **Voucher transactions** page.</span></span>
-   <span data-ttu-id="47f32-167">Cancelar uma nota fiscal de transferência ou apropriação de imposto ICMS lançada e gerar uma transação de comprovante cancelada.</span><span class="sxs-lookup"><span data-stu-id="47f32-167">Cancel a posted ICMS tax fiscal document and generate a canceled voucher transaction.</span></span> <span data-ttu-id="47f32-168">O valor da fatura da transação do comprovante cancelado é igual ao valor da fatura original, mas o valor da fatura é negativo.</span><span class="sxs-lookup"><span data-stu-id="47f32-168">The invoice amount of the canceled voucher transaction is the same as the amount of the original invoice, but the invoice amount is negative.</span></span>
-   <span data-ttu-id="47f32-169">Lançar a fatura cancelada e exibir as transações de comprovante originais e canceladas na página **Transações de comprovante**.</span><span class="sxs-lookup"><span data-stu-id="47f32-169">Post the canceled invoice, and view the original and canceled voucher transactions on the **Voucher transactions** page.</span></span>
-   <span data-ttu-id="47f32-170">Imprimir uma nota fiscal de transferência ou apropriação de imposto ICMS da Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="47f32-170">Print an ICMS tax fiscal document from General ledger.</span></span> <span data-ttu-id="47f32-171">O texto do rodapé configurado na página **Configuração de gerenciamento de impressão** não é impresso nas notas fiscais de transferência ou apropriação de imposto ICMS.</span><span class="sxs-lookup"><span data-stu-id="47f32-171">The footer text that is set up on the **Print management setup** page is not printed on ICMS tax fiscal documents.</span></span>

<span data-ttu-id="47f32-172">Quando uma nova nota fiscal de transferência ou apropriação de imposto é criada, as seguintes opções ficam disponíveis:</span><span class="sxs-lookup"><span data-stu-id="47f32-172">When a new tax fiscal document is created, the following options are available:</span></span>

-   <span data-ttu-id="47f32-173">Transferência de imposto ICMS</span><span class="sxs-lookup"><span data-stu-id="47f32-173">ICMS tax transfer</span></span>
-   <span data-ttu-id="47f32-174">Parcela de ICMS para utilizar o crédito de ativos fixos (CIAP)</span><span class="sxs-lookup"><span data-stu-id="47f32-174">ICMS installment to appropriate the credit of fixes assets (CIAP)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="47f32-175">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="47f32-175">Prerequisites</span></span>
<span data-ttu-id="47f32-176">Os seguintes pré-requisitos devem ser configurados antes de você criar e lançar notas fiscais de transferência ou apropriação de imposto.</span><span class="sxs-lookup"><span data-stu-id="47f32-176">The following prerequisites must be set up before you can create and post tax fiscal documents.</span></span> <span data-ttu-id="47f32-177">Os parâmetros determinam como os dados serão exibidos em notas fiscais, e todos são necessários.</span><span class="sxs-lookup"><span data-stu-id="47f32-177">The parameters determine how the data will be shown on the fiscal documents, and all of them are required.</span></span> <span data-ttu-id="47f32-178">Parâmetros ausentes podem causar inconsistências ou validações incorretas durante o processo de lançamento.</span><span class="sxs-lookup"><span data-stu-id="47f32-178">Missing parameters can cause inconsistencies or incorrect validations during the posting process.</span></span>

-   <span data-ttu-id="47f32-179">**Parâmetros brasileiros:** Defina o item e os códigos de imposto **PIS** e **COFINS** que são usados para esses tipos de documentos fiscais.</span><span class="sxs-lookup"><span data-stu-id="47f32-179">**Brazilian parameters:** Define the item, and the **PIS** and **COFINS** sales tax codes that are used for these types of fiscal documents.</span></span>
-   <span data-ttu-id="47f32-180">**Grupos de lançamento contábil na Contabilidade**: Define a conta contábil **Imposto a receber a curto prazo**.</span><span class="sxs-lookup"><span data-stu-id="47f32-180">**Ledger posting groups in General ledger**: Define the **Sales tax receivable short terms** ledger account.</span></span>

## <a name="example"></a><span data-ttu-id="47f32-181">Exemplo</span><span class="sxs-lookup"><span data-stu-id="47f32-181">Example</span></span>
<span data-ttu-id="47f32-182">**Notas fiscais de saída**</span><span class="sxs-lookup"><span data-stu-id="47f32-182">**Outgoing fiscal documents**</span></span>

-   <span data-ttu-id="47f32-183">Notas fiscais de saída para transferência de crédito de ICMS de outras entidades legais, subsidiárias/afiliadas ad mesma empresa/organização destinadas para a compensação do saldo de débito de ICMS (CFOP: 5.601 e 5.602)</span><span class="sxs-lookup"><span data-stu-id="47f32-183">Outgoing fiscal document to transfer the ICMS tax credit for other legal entities, subsidiary/branch of same company/organization destined for compensation of the debt balance of the ICMS (CFOP: 5.601 and 5.602)</span></span>

<span data-ttu-id="47f32-184">**Notas fiscais de entrada**</span><span class="sxs-lookup"><span data-stu-id="47f32-184">**Incoming fiscal documents**</span></span>

-   <span data-ttu-id="47f32-185">Notas fiscais de entrada para transferência de crédito de ICMS de outras entidades legais, subsidiárias/afiliadas ad mesma empresa/organização destinadas para a compensação do saldo de débito de ICMS (CFOP: 1.601 e 1.602)</span><span class="sxs-lookup"><span data-stu-id="47f32-185">Incoming fiscal documents to transfer the ICMS tax credit from other legal entities, subsidiaries/branches of same company/organization destined for compensation of the debt balance of the ICMS (CFOP:1.601 and 1.602)</span></span>
-   <span data-ttu-id="47f32-186">Notas fiscais de entrada para utilizar 1/48 de crédito de ICMS (CFOP: 1.604) (CIAP)</span><span class="sxs-lookup"><span data-stu-id="47f32-186">Incoming fiscal documents to appropriate 1/48 of the ICMS credit (CFOP:1.604) (CIAP)</span></span>


<span data-ttu-id="47f32-187">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="47f32-187">For more information, see the following topics:</span></span>

[<span data-ttu-id="47f32-188">Configurar códigos de ajuste para o imposto ICMS (Brasil)</span><span class="sxs-lookup"><span data-stu-id="47f32-188">Set up adjustment codes for ICMS tax (Brazil)</span></span>](tasks/br-10001-1-set-up-adjustment-codes-icms-tax.md)

[<span data-ttu-id="47f32-189">Configurar códigos de ajuste para o imposto ICMS em notas fiscais (Brasil)</span><span class="sxs-lookup"><span data-stu-id="47f32-189">Set up adjustment codes for ICMS taxes on fiscal documents (Brazil)</span></span>](tasks/br-10001-2-set-up-adjustment-codes-icms-taxes-fiscal-documents.md)

[<span data-ttu-id="47f32-190">Inserir e lançar transações de ajuste de imposto (Brasil)</span><span class="sxs-lookup"><span data-stu-id="47f32-190">Enter and post tax adjustment transactions (Brazil)</span></span>](tasks/br-10001-3-enter-post-tax-adjustment-transactions.md)

[<span data-ttu-id="47f32-191">Criar uma apuração de imposto – ICMS (Brasil)</span><span class="sxs-lookup"><span data-stu-id="47f32-191">Create a tax assessment - ICMS (Brazil)</span></span>](tasks/br-10001-4-create-tax-assessment-icms.md)



