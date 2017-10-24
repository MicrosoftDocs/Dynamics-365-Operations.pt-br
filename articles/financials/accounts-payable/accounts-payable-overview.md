---
title: Configurar contas a pagar
description: "Este artigo descreve as páginas que você usa para configurar funcionalidades básicas e opcionais de Contas a pagar no Microsoft Dynamics 365 for Finance and Operations, edição Enterprise. Também mostra as etapas de configuração que devem ser concluídas antes de começar a configurar as contas a pagar."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 49e5c81dda8434a6e02106a8d7ee10233e43d172
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="configure-accounts-payable"></a><span data-ttu-id="94628-104">Configurar contas a pagar</span><span class="sxs-lookup"><span data-stu-id="94628-104">Configure Accounts payable</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="94628-105">Este artigo descreve as páginas que você usa para configurar funcionalidades básicas e opcionais de Contas a pagar no Microsoft Dynamics 365 for Finance and Operations, edição Enterprise.</span><span class="sxs-lookup"><span data-stu-id="94628-105">This article describes the pages that you use to set up basic and optional functionality for Accounts payable in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="94628-106">Também mostra as etapas de configuração que devem ser concluídas antes de começar a configurar as contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="94628-106">It also describes setup steps that you must complete before you start to set up Accounts payable.</span></span>

<a name="prerequisites-for-accounts-payable-setup"></a><span data-ttu-id="94628-107">Pré-requisitos para a configuração de contas a pagar</span><span class="sxs-lookup"><span data-stu-id="94628-107">Prerequisites for Accounts payable setup</span></span>
----------------------------------------

<span data-ttu-id="94628-108">Antes de poder configurar contas a pagar, é necessário concluir a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="94628-108">Before you can set up Accounts payable, you must complete the following setup:</span></span>

-   <span data-ttu-id="94628-109">Na contabilidade:</span><span class="sxs-lookup"><span data-stu-id="94628-109">In General ledger:</span></span>
    -   <span data-ttu-id="94628-110">Se você planeja usar diários de pagamentos, configure os diários de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="94628-110">If you plan to use payment journals, set up payment journals.</span></span>
    -   <span data-ttu-id="94628-111">Se você planeja executar ajustes cambiais, configure os códigos de moeda na página Moedas, configure os tipos de taxa de câmbio na página Tipos de taxa de câmbio, e configure as taxas de câmbio de moeda na página Taxas de câmbio de moeda.</span><span class="sxs-lookup"><span data-stu-id="94628-111">If you plan to run exchange rate adjustments, set up currency codes on the Currencies page, set up exchange rate types on the Exchange rate types page, and set up currency exchange rates on the Currency exchange rates page.</span></span>
-   <span data-ttu-id="94628-112">No Gerenciamento de caixa e bancos, configure as contas bancárias a serem usadas com os métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="94628-112">In Cash and bank management, set up bank accounts to use with methods of payment.</span></span>

## <a name="setup-pages-for-accounts-payable"></a><span data-ttu-id="94628-113">Páginas de configuração de contas a pagar</span><span class="sxs-lookup"><span data-stu-id="94628-113">Setup pages for Accounts payable</span></span>

<span data-ttu-id="94628-114">Use as páginas a seguir para configurar a funcionalidade básica de Contas a pagar para cada entidade legal.</span><span class="sxs-lookup"><span data-stu-id="94628-114">Use the following pages to set up the basic functionality of Accounts payable for each legal entity.</span></span> <span data-ttu-id="94628-115">As páginas são listadas na ordem de configuração recomendada.</span><span class="sxs-lookup"><span data-stu-id="94628-115">The pages are listed in the recommended order of setup.</span></span> <span data-ttu-id="94628-116">Para simplificar o processo de configuração, você pode criar modelos a partir dos primeiros registros criados.</span><span class="sxs-lookup"><span data-stu-id="94628-116">To make the setup process easier, you can create templates from the first records that you create.</span></span> <span data-ttu-id="94628-117">Em um modelo, os valores são normalmente inseridos em vários campos para refletir os recursos que a organização quer implementar para um determinado tipo de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="94628-117">In a template, values are typically entered in many fields to reflect the features that the organization wants to implement for a particular type of vendor.</span></span>
1.  <span data-ttu-id="94628-118">Na página Condições de pagamento, defina as condições de pagamento que você atribui às ordens de venda, ordens de compra, clientes, e fornecedores, e que determinam as datas de validade de fatura.</span><span class="sxs-lookup"><span data-stu-id="94628-118">On the Terms of payment page, define the terms of payment that you assign to sales orders, purchase orders, customers, and vendors, and that determine invoice due dates.</span></span> <span data-ttu-id="94628-119">Para obter mais informações, consulte [Definir taxas de pagamento de fornecedor](tasks/define-vendor-payment-fees.md).</span><span class="sxs-lookup"><span data-stu-id="94628-119">For more information, see [Define vendor payment fees](tasks/define-vendor-payment-fees.md).</span></span>
2.  <span data-ttu-id="94628-120">Na página Métodos de pagamento - fornecedores, crie e mantenha informações sobre como a organização paga seus fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94628-120">On the Methods of payment - vendors page, create and maintain information about how the organization pays its vendors.</span></span>
3.  <span data-ttu-id="94628-121">Na página Grupos de fornecedores, crie e mantenha grupos de fornecedores que compartilham parâmetros importantes para lançamento, liquidação e pagamento, relatórios, e previsão.</span><span class="sxs-lookup"><span data-stu-id="94628-121">On the Vendor groups page, create and maintain groups of vendors that share important parameters for posting, settlement and payment, reporting, and forecasting.</span></span>
4.  <span data-ttu-id="94628-122">Na página Perfis de lançamento de fornecedor, defina como as transações de fornecedor são lançadas na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="94628-122">On the Vendor posting profiles page, define how vendor transactions are posted to the general ledger.</span></span>
5.  <span data-ttu-id="94628-123">Na página Parâmetros de contas a pagar, defina as configurações padrão aplicadas na ausência de uma configuração mais específica, os parâmetros para vários tipos de funcionalidades e as diversas sequências numéricas para Contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="94628-123">On the Accounts payable parameters page, set up default settings that are applied if a more specific setting isn't specified, parameters for various kinds of functionality, and the various number sequences for Accounts payable.</span></span>
6.  <span data-ttu-id="94628-124">Na página Configuração do formulário, defina o formato de vários documentos relacionados a fornecedores que são usados na organização para rastrear recebimentos de fornecedores e para inserir motivos para o fluxo de pagamentos aos fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94628-124">On the Form setup page, define the format of various documents that are related to vendors, and that the organization uses to keep track of receipts from vendors and enter reasons for the flow of payments to vendors.</span></span>
7.  <span data-ttu-id="94628-125">Na página Fornecedores, crie e mantenha contas de fornecedor, e também as autoridades fiscais às quais sua organização declara os impostos sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="94628-125">On the Vendors page, create and maintain vendor accounts, and also the tax authorities that your organization reports sales taxes to.</span></span>

## <a name="optional-setup-pages-for-accounts-payable"></a><span data-ttu-id="94628-126">Páginas de configuração opcionais de contas a pagar</span><span class="sxs-lookup"><span data-stu-id="94628-126">Optional setup pages for Accounts payable</span></span>
<span data-ttu-id="94628-127">Além da funcionalidade básica, a sessão de contas a pagar possui outras funcionalidades que você pode configurar.</span><span class="sxs-lookup"><span data-stu-id="94628-127">In addition to the basic functionality, Accounts payable has other functionality that you can set up.</span></span>

<span data-ttu-id="94628-128">As páginas de configuração adicional são organizados por funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="94628-128">The additional setup pages are organized by functionality.</span></span>

<span data-ttu-id="94628-129">**Políticas**</span><span class="sxs-lookup"><span data-stu-id="94628-129">**Policies**</span></span>
-   <span data-ttu-id="94628-130">Na página Política de fatura de fornecedor, configure as políticas de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="94628-130">On the Vendor invoice policy page, set up vendor invoice policies.</span></span>

<span data-ttu-id="94628-131">**Conciliação de fatura**</span><span class="sxs-lookup"><span data-stu-id="94628-131">**Invoice matching**</span></span>

-   <span data-ttu-id="94628-132">Na página Tolerâncias dos totais de fatura, configure as tolerâncias para os totais de faturas.</span><span class="sxs-lookup"><span data-stu-id="94628-132">On the Invoice totals tolerances page, set up tolerances for invoice totals.</span></span>
-   <span data-ttu-id="94628-133">Na página Política de conciliação, configure as políticas de conciliação dupla e tripla.</span><span class="sxs-lookup"><span data-stu-id="94628-133">On the Matching policy page, set up two-way and three-way matching policies.</span></span>
-   <span data-ttu-id="94628-134">Na página Tolerâncias de preço, configure as tolerâncias para preços unitários.</span><span class="sxs-lookup"><span data-stu-id="94628-134">On the Price tolerances page, set up tolerances for unit prices.</span></span>
-   <span data-ttu-id="94628-135">Na página Grupos de tolerância de preços de item, configure os grupos de tolerância para os preços de item.</span><span class="sxs-lookup"><span data-stu-id="94628-135">On the Item price tolerance groups page, set up tolerance groups for item prices.</span></span>
-   <span data-ttu-id="94628-136">Na página Grupos de tolerância de preços de fornecedor, configure os grupos de tolerância para os preços de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="94628-136">On the Vendor price tolerance groups page, set up  tolerance groups for vendor prices.</span></span>
-   <span data-ttu-id="94628-137">Na página Tolerâncias de encargos, configure as tolerâncias para encargos.</span><span class="sxs-lookup"><span data-stu-id="94628-137">On the Charges tolerances page, set up tolerances for charges.</span></span>

<span data-ttu-id="94628-138">**Fluxo de trabalho**</span><span class="sxs-lookup"><span data-stu-id="94628-138">**Workflow**</span></span>

-   <span data-ttu-id="94628-139">Na página Fluxos de trabalho de contas a pagar, defina as configurações de fluxo de trabalho para aprovações de diários e requisições de compra.</span><span class="sxs-lookup"><span data-stu-id="94628-139">On the Accounts payable workflows page, set up workflow configurations for journal approvals and purchase requisitions.</span></span>

<span data-ttu-id="94628-140">**Motivos**</span><span class="sxs-lookup"><span data-stu-id="94628-140">**Reasons**</span></span>

-   <span data-ttu-id="94628-141">Na página Motivos de fornecedor, configure os códigos de motivo.</span><span class="sxs-lookup"><span data-stu-id="94628-141">On the Vendor reasons page, set up reason codes.</span></span>

<span data-ttu-id="94628-142">**Encargos**</span><span class="sxs-lookup"><span data-stu-id="94628-142">**Charges**</span></span>

-   <span data-ttu-id="94628-143">Na página Código de encargos, configure os códigos para os encargos que são usados em ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="94628-143">On the Charges code page, set up codes for the charges that are used in purchase orders.</span></span>
-   <span data-ttu-id="94628-144">Na página Grupo de encargos de fornecedor, crie e mantenha grupos de encargos para fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94628-144">On the Vendor charges group page, create and maintain charges groups for vendors.</span></span>
-   <span data-ttu-id="94628-145">Na página Grupos de encargos de item , crie e mantenha grupos de encargos para itens.</span><span class="sxs-lookup"><span data-stu-id="94628-145">On the Item charge groups page, create and maintain charges groups for items.</span></span>
-   <span data-ttu-id="94628-146">Na página Encargos automáticos , defina os encargos que são atribuídos automaticamente às ordens.</span><span class="sxs-lookup"><span data-stu-id="94628-146">On the Auto charges page, define the charges that are automatically assigned to orders.</span></span>

<span data-ttu-id="94628-147">**Itens suplementares**</span><span class="sxs-lookup"><span data-stu-id="94628-147">**Supplementary items**</span></span>

-   <span data-ttu-id="94628-148">Na página Grupos de itens complementares - Fornecedor , crie e mantenha grupos de itens complementadores para fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94628-148">On the Supplementary item groups - Vendor page, create and maintain supplementary item groups for vendors.</span></span>
-   <span data-ttu-id="94628-149">Na página Grupos de itens complementares - Estoque , crie e mantenha grupos de itens complementadores para itens.</span><span class="sxs-lookup"><span data-stu-id="94628-149">On the Supplementary item groups - Inventory page, create and maintain supplementary item groups for items.</span></span>

<span data-ttu-id="94628-150">**Distribuição**</span><span class="sxs-lookup"><span data-stu-id="94628-150">**Distribution**</span></span>

-   <span data-ttu-id="94628-151">Na página Condições de entrega , crie e mantenha as condições para uma transferência de item do vendedor para o comprador.</span><span class="sxs-lookup"><span data-stu-id="94628-151">On the Terms of delivery page, create and maintain the conditions for an item's transfer from seller to buyer.</span></span>
-   <span data-ttu-id="94628-152">Na página Modos de entrega , crie e mantenha os métodos de transporte usados quando uma ordem é entregue do vendedor ao comprador.</span><span class="sxs-lookup"><span data-stu-id="94628-152">On the Modes of delivery page, create and maintain the methods of transport that are used when an order is delivered from the seller to the buyer.</span></span>
-   <span data-ttu-id="94628-153">Na página Códigos de destino , crie e mantenha identificadores e descrições para os destinos de entrega.</span><span class="sxs-lookup"><span data-stu-id="94628-153">On the Destination codes page, create and maintain identifiers and descriptions for delivery destinations.</span></span>

<span data-ttu-id="94628-154">**Formulários**</span><span class="sxs-lookup"><span data-stu-id="94628-154">**Forms**</span></span>

-   <span data-ttu-id="94628-155">Na página Notas do formulário , crie o texto padrão que aparece em diversas páginas.</span><span class="sxs-lookup"><span data-stu-id="94628-155">On the Form notes page, create the standard text that appears on various pages.</span></span>
-   <span data-ttu-id="94628-156">Na página Parâmetros de classificação de formulário , configure a ordem de classificação para requisições, listas de recebimento, guias de remessa, e faturas.</span><span class="sxs-lookup"><span data-stu-id="94628-156">On the Form sorting parameters page, set up the sorting order for requisitions, receipt lists, packing slips, and invoices.</span></span>
-   <span data-ttu-id="94628-157">Na página Gerenciamento de impressão , configure as informações de gerenciamento de impressão para documentos originais e cópias de páginas.</span><span class="sxs-lookup"><span data-stu-id="94628-157">On the Print management setup page, set up print management information for originals and copies of pages.</span></span>

<span data-ttu-id="94628-158">**Pagamentos**</span><span class="sxs-lookup"><span data-stu-id="94628-158">**Payments**</span></span>

-   <span data-ttu-id="94628-159">Na página Descontos à vista , configure e gerencie as condições para a obtenção de descontos à vista.</span><span class="sxs-lookup"><span data-stu-id="94628-159">On the Cash discounts page, set up and manage the terms for obtaining cash discounts.</span></span> <span data-ttu-id="94628-160">Os códigos de desconto à vista estão associados a fornecedores e são aplicados a ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="94628-160">The cash discount codes are linked to vendors and are applied to purchase orders.</span></span>
-   <span data-ttu-id="94628-161">Na página Planos de pagamento , configure os planos de pagamento usados para gerenciar pagamentos a prestação para fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94628-161">On the Payment schedules page, set up the payment schedules that are used to manage installment payments to vendors.</span></span>
-   <span data-ttu-id="94628-162">Na página Dias de pagamento , defina os dias de pagamento usados para calcular as datas de validade, e especifique os dias de pagamento para um dia específico da semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="94628-162">On the Payment days page, define the payment days that are used to calculate due dates, and specify payment days for a specific day of the week or month.</span></span>
-   <span data-ttu-id="94628-163">Na página Taxa de pagamento , crie e mantenha as taxas de pagamento que estão associadas aos fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94628-163">On the Payment fee page, create and maintain the payment fees that are associated with vendors.</span></span>
-   <span data-ttu-id="94628-164">Na página Instrução de pagamento , crie e mantenha as instruções de pagamento.</span><span class="sxs-lookup"><span data-stu-id="94628-164">On the Payment instruction page, create and maintain payment instructions.</span></span>

<span data-ttu-id="94628-165">**Estatísticas**</span><span class="sxs-lookup"><span data-stu-id="94628-165">**Statistics**</span></span>

-   <span data-ttu-id="94628-166">Na página Definições do período de classificação por vencimento , configure intervalos definidos pelo usuário para analisar a distribuição de vencimentos de contas de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94628-166">On the Aging period definitions page, set up user-defined intervals that are used to analyze the maturity distribution of vendor accounts.</span></span>
-   <span data-ttu-id="94628-167">Na página Linha de negócio , crie os códigos de linha de negócio (LOB) que são atribuídos aos fornecedores.</span><span class="sxs-lookup"><span data-stu-id="94628-167">On the Line of business page, create the line of business (LOB) codes that are assigned to vendors.</span></span>

<span data-ttu-id="94628-168">**Imposto 1099**</span><span class="sxs-lookup"><span data-stu-id="94628-168">**Tax 1099**</span></span>

-   <span data-ttu-id="94628-169">Na página **Campos 1099**, verifique e atualize os valores mínimos que devem ser informados à Administração Fiscal (IRS), com base nos requisitos mais recentes da IRS.</span><span class="sxs-lookup"><span data-stu-id="94628-169">On the **1099 fields** page, verify and update the minimum amounts that must be reported to the Internal Revenue Service (IRS), based on the latest IRS requirements.</span></span>

## <a name="optional-setup-for-other-modules"></a><span data-ttu-id="94628-170">**Configuração opcional para outros módulos**</span><span class="sxs-lookup"><span data-stu-id="94628-170">**Optional setup for other modules**</span></span>
<span data-ttu-id="94628-171">**Administração da organização**</span><span class="sxs-lookup"><span data-stu-id="94628-171">**Organization administration**</span></span>

-   <span data-ttu-id="94628-172">Na página Sequências numéricas , configure os grupos de sequência numérica para números de fatura.</span><span class="sxs-lookup"><span data-stu-id="94628-172">On the Number sequences page, set up number sequence groups for invoice numbers.</span></span>
-   <span data-ttu-id="94628-173">Nas páginas a seguir, configure as informações de endereço:</span><span class="sxs-lookup"><span data-stu-id="94628-173">On the following pages, set up address information:</span></span>
    -   <span data-ttu-id="94628-174">Configuração de endereço</span><span class="sxs-lookup"><span data-stu-id="94628-174">Address setup</span></span>
    -   <span data-ttu-id="94628-175">Códigos NAF</span><span class="sxs-lookup"><span data-stu-id="94628-175">NAF codes</span></span>
    -   <span data-ttu-id="94628-176">Importar CEPs</span><span class="sxs-lookup"><span data-stu-id="94628-176">Import ZIP/postal codes</span></span>

<span data-ttu-id="94628-177">**Contabilidade**</span><span class="sxs-lookup"><span data-stu-id="94628-177">**General ledger**</span></span>

-   <span data-ttu-id="94628-178">Na página Dimensões financeiras , configure as dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="94628-178">On the Financial dimensions page, set up financial dimensions.</span></span>
-   <span data-ttu-id="94628-179">Nas páginas a seguir, configure as informações de imposto:</span><span class="sxs-lookup"><span data-stu-id="94628-179">On the following pages, set up tax information:</span></span>
    -   <span data-ttu-id="94628-180">Códigos de imposto</span><span class="sxs-lookup"><span data-stu-id="94628-180">Sales tax codes</span></span>
    -   <span data-ttu-id="94628-181">Grupos de impostos</span><span class="sxs-lookup"><span data-stu-id="94628-181">Sales tax groups</span></span>
    -   <span data-ttu-id="94628-182">Grupos de impostos do item</span><span class="sxs-lookup"><span data-stu-id="94628-182">Item sales tax groups</span></span>
    -   <span data-ttu-id="94628-183">Grupo de contas</span><span class="sxs-lookup"><span data-stu-id="94628-183">Account group</span></span>
    -   <span data-ttu-id="94628-184">Códigos de isenção do imposto</span><span class="sxs-lookup"><span data-stu-id="94628-184">Sales tax exempt codes</span></span>
    -   <span data-ttu-id="94628-185">Jurisdições de impostos</span><span class="sxs-lookup"><span data-stu-id="94628-185">Sales tax jurisdictions</span></span>
    -   <span data-ttu-id="94628-186">Autoridades do imposto</span><span class="sxs-lookup"><span data-stu-id="94628-186">Sales tax authorities</span></span>
    -   <span data-ttu-id="94628-187">Períodos de liquidação de imposto</span><span class="sxs-lookup"><span data-stu-id="94628-187">Sales tax settlement periods</span></span>

<span data-ttu-id="94628-188">**Gerenciamento de caixa e bancos**</span><span class="sxs-lookup"><span data-stu-id="94628-188">**Cash and bank management**</span></span>

-   <span data-ttu-id="94628-189">Na página Códigos de finalidade de pagamento, configure o código de finalidade do banco central.</span><span class="sxs-lookup"><span data-stu-id="94628-189">On the Payment purpose codes page, set up the Central Bank purpose code.</span></span>






