---
title: Configurar livros fiscais
description: "Este tópico explica como configurar livros fiscais. Eles ajudam a consolidar livros fiscais e estatutários em arquivos eletrônicos para que você possa atender aos requisitos do SPED."
author: v-gonode
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FBTaxStatement_BR
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: v-gonode
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: d8f984a53aa6557676fc82db702495011eab65fa
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="configure-fiscal-books"></a><span data-ttu-id="5c833-104">Configurar livros fiscais</span><span class="sxs-lookup"><span data-stu-id="5c833-104">Configure fiscal books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5c833-105">Os livros fiscais ajudam a criar a apuração de imposto do estabelecimento fiscal, o pagamento de imposto e o relatório de imposto por meio do Sistema Público de Escrituração Digital (SPED).</span><span class="sxs-lookup"><span data-stu-id="5c833-105">Fiscal books can help you create the fiscal establishment's tax assessment, tax payment, and tax reporting through Sistema Publico de Escrituração Digital (SPED), the Public Digital Bookkeeping System.</span></span> <span data-ttu-id="5c833-106">Os arquivos do SPED fornecem informações detalhadas sobre as apurações e pagamentos de imposto em transações com mercadorias, ativos fixos e serviços, bem como em transações na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="5c833-106">The SPED files provide detailed information about the tax assessments and tax payments on transactions that have goods, fixed assets, and services, and also transactions in the general ledger.</span></span> 

## <a name="set-up-requirements-for-sped-fiscal-text-files"></a><span data-ttu-id="5c833-107">Configurar requisitos para arquivos de texto fiscais SPED</span><span class="sxs-lookup"><span data-stu-id="5c833-107">Set up requirements for SPED fiscal text files</span></span>

> [!NOTE]
> <span data-ttu-id="5c833-108">Antes de configurar seu arquivo de texto fiscal do SPED, é preciso importar o modelo de dados **Modelo do SPED** e a configuração de arquivo **EFD ICMS IPI - nnn (BR)** no módulo **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="5c833-108">Before you configure your SPED fiscal text file, you must import the **SPED model** data model and the **EFD ICMS IPI - nnn (BR)** file configuration from the **Electronic reporting** module.</span></span> <span data-ttu-id="5c833-109">No Relatório eletrônico, é possível baixar o modelo e a configuração de arquivo do repositório publicado pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c833-109">In Electronic reporting, you can download both the model and the file configuration from the repository that is published by Microsoft.</span></span> <span data-ttu-id="5c833-110">Como alternativa, você pode obter uma versão atualizada do Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5c833-110">Alternatively, you can get an updated version from Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="5c833-111">Na página **Parâmetros das extensões de obrigações fiscais**, clique em **Novo na geração eletrônica de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="5c833-111">On the **Tax statements parameters** page, click **New from electronic reporting**.</span></span>
2. <span data-ttu-id="5c833-112">Insira um nome para a obrigação fiscal.</span><span class="sxs-lookup"><span data-stu-id="5c833-112">Enter a name for the tax statement.</span></span>
3. <span data-ttu-id="5c833-113">Selecione **Modelo do SPED** como o nome do mapeamento de modelo e **EFD ICMS IPI - nnn (BR)** como mapeamento do formato.</span><span class="sxs-lookup"><span data-stu-id="5c833-113">Select **SPED model** as the name of the model mapping and **EFD ICMS IPI - nnn (BR)** as the format mapping.</span></span>

## <a name="set-up-requirements-for-gia-text-files"></a><span data-ttu-id="5c833-114">Configurar requisitos para arquivos de texto GIA</span><span class="sxs-lookup"><span data-stu-id="5c833-114">Set up requirements for GIA text files</span></span>

> [!NOTE]
> <span data-ttu-id="5c833-115">Antes de configurar seu arquivo de texto do Guia de Informação e Apuração (GIA), é preciso importar o modelo de dados **Modelo do SPED** e a configuração de arquivo **GIA** no Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="5c833-115">Before you configure your Guia de Informação e Apuração (GIA) text file, you must import the **SPED model** data model and the **GIA** file configuration from Electronic reporting.</span></span> <span data-ttu-id="5c833-116">No Relatório eletrônico, é possível baixar o modelo e a configuração de arquivo do repositório publicado pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c833-116">In Electronic reporting, you can download both the model and the file configuration from the repository that is published by Microsoft.</span></span> <span data-ttu-id="5c833-117">Como alternativa, é possível obter uma versão atualizada do LCS.</span><span class="sxs-lookup"><span data-stu-id="5c833-117">Alternatively, you can get an updated version from LCS.</span></span>

1. <span data-ttu-id="5c833-118">Na página **Parâmetros das extensões de obrigações fiscais**, clique em **Novo na geração eletrônica de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="5c833-118">On the **Tax statements parameters** page, click **New from electronic reporting**.</span></span>
2. <span data-ttu-id="5c833-119">Insira um nome para a obrigação fiscal.</span><span class="sxs-lookup"><span data-stu-id="5c833-119">Enter a name for the tax statement.</span></span>
3. <span data-ttu-id="5c833-120">Selecione **Modelo do SPED** como o nome do mapeamento de modelo e **GIA** como mapeamento do formato.</span><span class="sxs-lookup"><span data-stu-id="5c833-120">Select **SPED model** as the name of the model mapping and **GIA** as the format mapping.</span></span>

## <a name="set-up-requirements-for-gia-st-text-files"></a><span data-ttu-id="5c833-121">Configurar requisitos para arquivos de texto GIA-ST</span><span class="sxs-lookup"><span data-stu-id="5c833-121">Set up requirements for GIA-ST text files</span></span>

> [!NOTE]
> <span data-ttu-id="5c833-122">Antes de configurar seu arquivo de texto do GIA-ST, é preciso importar o modelo de dados **Modelo do SPED** e a configuração de arquivo **GIA-ST** no Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="5c833-122">Before you configure your GIA-ST text file, you must import the **SPED model** data model and the **GIA-ST** file configuration from Electronic reporting.</span></span> <span data-ttu-id="5c833-123">No Relatório eletrônico, é possível baixar o modelo e a configuração de arquivo do repositório publicado pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c833-123">In Electronic reporting, you can download both the model and the file configuration from the repository that is published by Microsoft.</span></span> <span data-ttu-id="5c833-124">Como alternativa, é possível obter uma versão atualizada do LCS.</span><span class="sxs-lookup"><span data-stu-id="5c833-124">Alternatively, you can get an updated version from LCS.</span></span>

1. <span data-ttu-id="5c833-125">Na página **Parâmetros das extensões de obrigações fiscais**, clique em **Novo na geração eletrônica de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="5c833-125">On the **Tax statements parameters** page, click **New from electronic reporting**.</span></span>
2. <span data-ttu-id="5c833-126">Insira um nome para a obrigação fiscal.</span><span class="sxs-lookup"><span data-stu-id="5c833-126">Enter a name for the tax statement.</span></span>
3. <span data-ttu-id="5c833-127">Selecione **Modelo do SPED** como o nome do mapeamento de modelo e **GIA-ST** como mapeamento do formato.</span><span class="sxs-lookup"><span data-stu-id="5c833-127">Select **SPED model** as the name of the model mapping and **GIA-ST** as the format mapping.</span></span>

## <a name="set-up-requirements-for-sped-contributions-text-files"></a><span data-ttu-id="5c833-128">Configurar requisitos para arquivos de texto de contribuições SPED</span><span class="sxs-lookup"><span data-stu-id="5c833-128">Set up requirements for SPED contributions text files</span></span>

> [!NOTE]
> <span data-ttu-id="5c833-129">Antes de configurar seu arquivo de texto de contribuições SPED, é preciso importar o modelo de dados **Modelo do SPED** e a configuração de arquivo **EFD Contribuições - nnn (BR)** no Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="5c833-129">Before you configure your SPED contributions text file, you must import the **SPED model** data model and the **EFD Contributions - nnn (BR)** file configuration from Electronic reporting.</span></span> <span data-ttu-id="5c833-130">No Relatório eletrônico, é possível baixar o modelo e a configuração de arquivo do repositório publicado pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c833-130">In Electronic reporting, you can download both the model and the file configuration from the repository that is published by Microsoft.</span></span> <span data-ttu-id="5c833-131">Como alternativa, é possível obter uma versão atualizada do LCS.</span><span class="sxs-lookup"><span data-stu-id="5c833-131">Alternatively, you can get an updated version from LCS.</span></span>

1. <span data-ttu-id="5c833-132">Na página **Parâmetros das extensões de obrigações fiscais**, clique em **Novo na geração eletrônica de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="5c833-132">On the **Tax statements parameters** page, click **New from electronic reporting**.</span></span>
2. <span data-ttu-id="5c833-133">Insira um nome para a obrigação fiscal.</span><span class="sxs-lookup"><span data-stu-id="5c833-133">Enter a name for the tax statement.</span></span>
3. <span data-ttu-id="5c833-134">Selecione **Modelo do SPED** como o nome do mapeamento de modelo e **EFD Contribuições - nnn (BR)** como mapeamento do formato.</span><span class="sxs-lookup"><span data-stu-id="5c833-134">Select **SPED model** as the name of the model mapping and **EFD Contributions - nnn (BR)** as the format mapping.</span></span>

## <a name="set-up-adjustment-codes-for-icms-taxes-on-fiscal-documents"></a><span data-ttu-id="5c833-135">Configurar códigos de ajuste para impostos ICMS em notas fiscais</span><span class="sxs-lookup"><span data-stu-id="5c833-135">Set up adjustment codes for ICMS taxes on fiscal documents</span></span>

1. <span data-ttu-id="5c833-136">Na página **Ajuste e informações para documentos fiscais**, no campo **Identificação**, insira um código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c833-136">On the **Adjustment and information for fiscal documents** page, in the **Identification** field, enter an adjustment code.</span></span> <span data-ttu-id="5c833-137">Depois insira uma descrição do código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c833-137">Then enter a description of the adjustment code.</span></span>
2. <span data-ttu-id="5c833-138">Selecione valores apropriados nos campos **Estado**, **Classificação**, **Tipo de apuração**, **Responsabilidade**, **Tipo de pagamento de imposto** e **Origem do imposto**.</span><span class="sxs-lookup"><span data-stu-id="5c833-138">Select appropriate values in the **State**, **Classification**, **Assessment type**, **Responsibility**, **Tax payment type** and **Source of the tax** fields.</span></span>

    <span data-ttu-id="5c833-139">O campo **Código de ajuste** é preenchido automaticamente, com base nos valores dos outros campos na página.</span><span class="sxs-lookup"><span data-stu-id="5c833-139">The **Adjustment code** field is filled automatically, based on the values of the other fields on the page.</span></span>

3. <span data-ttu-id="5c833-140">Insira o código de ocorrência para a obrigação fiscal GIA.</span><span class="sxs-lookup"><span data-stu-id="5c833-140">Enter the occurrence code for the GIA fiscal obligation.</span></span>
4. <span data-ttu-id="5c833-141">Insira a primeira e última datas a que os códigos de ajuste se aplicam.</span><span class="sxs-lookup"><span data-stu-id="5c833-141">Enter the first and last dates that the adjustment codes apply.</span></span>
5. <span data-ttu-id="5c833-142">Na Guia Rápida **Pagamento**, marque a caixa de seleção **Outro débito** para criar um pagamento de ajuste de imposto adicional que não está incluído no pagamento periódico.</span><span class="sxs-lookup"><span data-stu-id="5c833-142">On the **Payment** FastTab, select the **Other debit** check box to create an additional tax adjustment payment that isn't included in the periodic payment.</span></span>
6. <span data-ttu-id="5c833-143">Na Guia Rápida **Lançamento**, no campo **Contas da empresa**, selecione a entidade legal na qual as transações de ajuste de impostos serão lançadas.</span><span class="sxs-lookup"><span data-stu-id="5c833-143">On the **Posting** FastTab, in the **Company accounts** field, select the legal entity where the tax adjustment transactions should be posted.</span></span>
7. <span data-ttu-id="5c833-144">No campo **Código do imposto**, selecione o código de imposto que deve ser usado para selecionar contas a receber ou a conta de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="5c833-144">In the **Sales tax code** field, select the tax code that should be used to select the accounts receivable or accounts payable account.</span></span> <span data-ttu-id="5c833-145">A conta selecionada depende do ajuste de imposto ser um débito ou crédito.</span><span class="sxs-lookup"><span data-stu-id="5c833-145">The account that is selected depends on whether the tax adjustment is a debit or a credit.</span></span> 
8. <span data-ttu-id="5c833-146">Selecione a conta principal que deve ser usada para lançar a parte da receita ou as despesas da transação de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c833-146">Select the main account that should be used to post the revenue or expense part of the adjustment transaction.</span></span>

## <a name="set-up-adjustment-codes-for-icms-tax"></a><span data-ttu-id="5c833-147">Configurar códigos de ajuste para o imposto de ICMS</span><span class="sxs-lookup"><span data-stu-id="5c833-147">Set up adjustment codes for ICMS tax</span></span>

1. <span data-ttu-id="5c833-148">Na página **Tabela de códigos de ajuste de ICMS e ICMS-ST**, no campo **Identificação**, insira um código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c833-148">On the **ICMS and ICMS-ST adjustment codes table** page, in the **Identification** field, enter an adjustment code.</span></span> <span data-ttu-id="5c833-149">Depois insira uma descrição do código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c833-149">Then enter a description of the adjustment code.</span></span>
2. <span data-ttu-id="5c833-150">Selecione um estado.</span><span class="sxs-lookup"><span data-stu-id="5c833-150">Select a state.</span></span>
3. <span data-ttu-id="5c833-151">Selecione o tipo de imposto:</span><span class="sxs-lookup"><span data-stu-id="5c833-151">Select the tax type:</span></span> 

    - <span data-ttu-id="5c833-152">**ICMS** – O código de ajusta é usado para o imposto federal Imposto sobre Circulação de Mercadorias e Serviços (ICMS).</span><span class="sxs-lookup"><span data-stu-id="5c833-152">**ICMS** – The adjustment code is used for federal Imposto sobre Circulação de Mercadorias e Serviços (ICMS) tax.</span></span>
    - <span data-ttu-id="5c833-153">**ICMS-ST** – O código de ajuste é usado para imposto federal de ICMS-ST.</span><span class="sxs-lookup"><span data-stu-id="5c833-153">**ICMS-ST** – The adjustment code is used for federal ICMS-ST tax.</span></span>
    - <span data-ttu-id="5c833-154">**ICMS-DIFF** – O código de ajuste é usado para imposto federal de ICMS-DIFF.</span><span class="sxs-lookup"><span data-stu-id="5c833-154">**ICMS-DIFF** – The adjustment code is used for federal ICMS-DIFF tax.</span></span>

4. <span data-ttu-id="5c833-155">Selecione uma classificação e insira um código de ocorrência.</span><span class="sxs-lookup"><span data-stu-id="5c833-155">Select a classification, and enter an occurrence code.</span></span>

    <span data-ttu-id="5c833-156">O campo **Código de ajuste** é preenchido automaticamente, com base nos valores dos outros campos na página.</span><span class="sxs-lookup"><span data-stu-id="5c833-156">The **Adjustment code** field is filled automatically, based on the values of the other fields on the page.</span></span>

5. <span data-ttu-id="5c833-157">Insira a primeira e última datas a que os códigos de ajuste se aplicam.</span><span class="sxs-lookup"><span data-stu-id="5c833-157">Enter the first and last dates that the adjustment codes apply.</span></span>
6. <span data-ttu-id="5c833-158">No grupo do campo **GIA**, selecione um código de ocorrência.</span><span class="sxs-lookup"><span data-stu-id="5c833-158">In the **GIA** field group, select an occurrence code.</span></span>
7. <span data-ttu-id="5c833-159">Na Guia Rápida **Pagamento**, selecione a opção **Outro débito** para criar um pagamento de ajuste de imposto adicional que não está incluído no pagamento periódico.</span><span class="sxs-lookup"><span data-stu-id="5c833-159">On the **Payment** FastTab, select the **Other debit** option to create an additional tax adjustment payment that isn't included in the periodic payment.</span></span>
8. <span data-ttu-id="5c833-160">Na Guia Rápida **Lançamento**, no campo **Contas da empresa**, selecione a entidade legal na qual as transações de ajuste de impostos serão lançadas.</span><span class="sxs-lookup"><span data-stu-id="5c833-160">On the **Posting** FastTab, in the **Company accounts** field, select the legal entity where the tax adjustment transactions should be posted.</span></span>
9. <span data-ttu-id="5c833-161">No campo **Código do imposto**, selecione o código de imposto que deve ser usado para selecionar contas a receber ou a conta de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="5c833-161">In the **Sales tax code** field, select the tax code that should be used to select the accounts receivable or accounts payable account.</span></span> <span data-ttu-id="5c833-162">A conta selecionada depende do ajuste de imposto ser um débito ou crédito.</span><span class="sxs-lookup"><span data-stu-id="5c833-162">The account that is selected depends on whether the tax adjustment is a debit or a credit.</span></span> 
10. <span data-ttu-id="5c833-163">Selecione a conta principal que deve ser usada para lançar a parte da receita ou as despesas da transação de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c833-163">Select the main account that should be used to post the revenue or expense part of the adjustment transaction.</span></span>

## <a name="set-up-adjustment-codes-for-ipi-taxes"></a><span data-ttu-id="5c833-164">Configurar códigos de ajuste para impostos IPI</span><span class="sxs-lookup"><span data-stu-id="5c833-164">Set up adjustment codes for IPI taxes</span></span>

1. <span data-ttu-id="5c833-165">Na página **Tabela de códigos de ajuste de IPI**, insira um código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="5c833-165">On the **IPI adjustment codes table** page, enter an adjustment code.</span></span> <span data-ttu-id="5c833-166">O primeiro caractere deve ser **0** (zero) para um ajuste de crédito ou **1** para um ajuste de débito.</span><span class="sxs-lookup"><span data-stu-id="5c833-166">The first character must be **0** (zero) for a credit adjustment or **1** for a debit adjustment.</span></span>
2. <span data-ttu-id="5c833-167">Insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="5c833-167">Enter a description.</span></span>
3. <span data-ttu-id="5c833-168">Se o código do ajuste for usado para relatar a reversão de um valor de imposto IPI (Imposto sobre Produtos Industrializados) que foi relatado anteriormente, selecione a opção **Código de ajuste de estorno**.</span><span class="sxs-lookup"><span data-stu-id="5c833-168">If the adjustment code will be used to report the reversal of an Imposto sobre Produtos Industrializados (IPI) tax amount that was previously reported, select the **Reversal adjustment code** option.</span></span>
4. <span data-ttu-id="5c833-169">Insira a primeira e última datas a que o código de ajuste se aplica.</span><span class="sxs-lookup"><span data-stu-id="5c833-169">Enter the first and last dates that the adjustment code applies.</span></span>

<span data-ttu-id="5c833-170">Na página **Códigos de observação**, é possível configurar os códigos de observação a serem usados para ajustar os valores de ICMS ou ICMS-ST.</span><span class="sxs-lookup"><span data-stu-id="5c833-170">On the **Observation codes** page, you can set up observation codes to adjust ICMS or ICMS-ST amounts.</span></span>

## <a name="set-up-fiscal-books-parameters-per-state"></a><span data-ttu-id="5c833-171">Configurar parâmetros de livros fiscais por estado</span><span class="sxs-lookup"><span data-stu-id="5c833-171">Set up fiscal books parameters per state</span></span>

1. <span data-ttu-id="5c833-172">Na página **Parâmetros de livros fiscais por estado**, selecione um estado.</span><span class="sxs-lookup"><span data-stu-id="5c833-172">On the **Fiscal books parameters per state** page, select a state.</span></span>
2. <span data-ttu-id="5c833-173">Se os valores do imposto ICMS puderem ser ajustados em notas fiscais, selecione a opção **Por nota fiscal** e selecione o código de ajuste padrão e o código de observação.</span><span class="sxs-lookup"><span data-stu-id="5c833-173">If the ICMS tax amounts can be adjusted on fiscal documents, select the **By fiscal document** option, and then select the default adjustment code and observation code.</span></span>

    <span data-ttu-id="5c833-174">Se os valores do imposto ICMS não puderem ser ajustados em notas fiscais, selecione a opção **Por nota fiscal** e selecione o código de ajuste padrão.</span><span class="sxs-lookup"><span data-stu-id="5c833-174">If the ICMS tax amounts can't be adjusted on fiscal documents, clear the **By fiscal document** option, and then select the default adjustment code.</span></span>

3. <span data-ttu-id="5c833-175">Para calcular automaticamente uma parcela de crédito ICMS quando uma transação de saída é criada, selecione a opção **Calcular parcela para transações de saída**.</span><span class="sxs-lookup"><span data-stu-id="5c833-175">To automatically calculate an ICMS credit installment when an outgoing transaction is created, select the **Calculate installment for outgoing transactions** option.</span></span>

## <a name="set-up-a-fiscal-organization"></a><span data-ttu-id="5c833-176">Configurar uma organização fiscal</span><span class="sxs-lookup"><span data-stu-id="5c833-176">Set up a fiscal organization</span></span>

1. <span data-ttu-id="5c833-177">Na página **Organização fiscal**, no campo **Estabelecimento fiscal matriz**, selecione uma organização fiscal que é usada para as contribuições SPED.</span><span class="sxs-lookup"><span data-stu-id="5c833-177">On the **Fiscal organization** page, in the **Root fiscal establishment** field, select a fiscal organization that is used for SPED contributions.</span></span>
2. <span data-ttu-id="5c833-178">Na Guia Rápida **Estabelecimento fiscal**, os estabelecimentos fiscais são automaticamente adicionados à lista se tiverem o mesmo número de nove dígitos do Cadastro Nacional de Pessoas Jurídicas (CNPJ)/Cadastro de Pessoas Físicas (CPF) como a organização fiscal que você selecionou no campo **Estabelecimento fiscal matriz**.</span><span class="sxs-lookup"><span data-stu-id="5c833-178">On the **Fiscal establishment** FastTab, fiscal establishments are automatically added to the list if they have the same nine-digit Cadastro Nacional de Pessoas Jurídicas (CNPJ)/Cadastro de Pessoas Físicas (CPF) number as the fiscal organization that you selected in the **Root fiscal establishment** field.</span></span> <span data-ttu-id="5c833-179">Para remover um estabelecimento fiscal adicionado à lista, clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="5c833-179">To remove a fiscal establishment that has been added to the list, click **Remove**.</span></span> 
3. <span data-ttu-id="5c833-180">Na Guia Rápida **Contrato social da empresa**, insira a data de arquivo morto do contrato de constituição da empresa e a conversão da empresa.</span><span class="sxs-lookup"><span data-stu-id="5c833-180">On the **Company social contract** FastTab, enter the archive date of the company’s constitution contract and the company’s conversion.</span></span>
4. <span data-ttu-id="5c833-181">Na Guia Rápida **SCP**, selecione o tipo de empresa Sociedade em Conta de Participação (SCP):</span><span class="sxs-lookup"><span data-stu-id="5c833-181">On the **SCP** FastTab, select the type of Sociedade em Conta de Participação (SCP) company:</span></span> 

    - <span data-ttu-id="5c833-182">Não participante de SCP como sócio ostensivo</span><span class="sxs-lookup"><span data-stu-id="5c833-182">Not participant as SCP partner</span></span>
    - <span data-ttu-id="5c833-183">Participante como parceiro SCP</span><span class="sxs-lookup"><span data-stu-id="5c833-183">Participant as SCP partner</span></span>
    - <span data-ttu-id="5c833-184">SCP</span><span class="sxs-lookup"><span data-stu-id="5c833-184">SCP</span></span>

5. <span data-ttu-id="5c833-185">Na Guia Rápida **SCP relacionado**, clique em **Adicionar** para inserir o nome e o código de uma empresa relacionada ao SCP.</span><span class="sxs-lookup"><span data-stu-id="5c833-185">On the **Related SCP** FastTab, click **Add** to enter the name and code of an SCP-related company.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5c833-186">Essas informações estão disponíveis se você selecionou **Participante como parceiro SCP** como o tipo de empresa SCP.</span><span class="sxs-lookup"><span data-stu-id="5c833-186">This information is available if you selected **Participant as SCP partner** as they type of SCP company.</span></span>

6. <span data-ttu-id="5c833-187">Na Guia Rápida **Representante legal**, clique em **Adicionar** para inserir o nome do representante legal da empresa.</span><span class="sxs-lookup"><span data-stu-id="5c833-187">On the **Legal representative** FastTab, click **Add** to enter the name of the company’s legal representative.</span></span>
7. <span data-ttu-id="5c833-188">Insira o número do CPF e a função do representante legal.</span><span class="sxs-lookup"><span data-stu-id="5c833-188">Enter the CPF registration number and the role of the legal representative.</span></span> 
8. <span data-ttu-id="5c833-189">Na Guia Rápida **Auditores independentes**, clique em **Adicionar** para inserir o nome do auditor e o número de registro.</span><span class="sxs-lookup"><span data-stu-id="5c833-189">On the **Independent auditors** FastTab, click **Add** to enter the name of the auditor and the registration number.</span></span>
9. <span data-ttu-id="5c833-190">Para remover um auditor independente que foi adicionado à lista, clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="5c833-190">To remove an independent auditor that has been added to the list, click **Remove**.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="5c833-191">Essa opção está disponível quando a opção **Empresa de grande porte** é selecionada.</span><span class="sxs-lookup"><span data-stu-id="5c833-191">This option is available when the **Large company** option is selected.</span></span>

<span data-ttu-id="5c833-192">Na página **Grupos de ativos fixos**, você pode configurar um grupo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="5c833-192">On the **Fixed asset groups** page, you can set up a fixed asset group.</span></span>

## <a name="set-up-requirements-for-the-sped-ecd-tax-statement"></a><span data-ttu-id="5c833-193">Configurar requisitos para a declaração de imposto SPED ECD</span><span class="sxs-lookup"><span data-stu-id="5c833-193">Set up requirements for the SPED ECD tax statement</span></span>

1. <span data-ttu-id="5c833-194">Na página **Parâmetros das extensões de obrigações fiscais**, clique em **SPED ECD**.</span><span class="sxs-lookup"><span data-stu-id="5c833-194">On the **Tax statements parameters** page, click **SPED ECD**.</span></span> <span data-ttu-id="5c833-195">Depois, na Guia Rápida **Parâmetros de configuração**, clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5c833-195">Then, on the **Setup parameters** FastTab, click **Open**.</span></span>
2. <span data-ttu-id="5c833-196">Selecione a empresa para a qual gerar o arquivo de texto do SPED ECD (Escrituração Contábil Digital).</span><span class="sxs-lookup"><span data-stu-id="5c833-196">Select the company to generate the SPED Escrituração Contábil Digital (ECD) text file for.</span></span>
3. <span data-ttu-id="5c833-197">Selecione o conjunto de dimensões financeiras na qual o formato de arquivo de texto do SPED ECD deve se basear.</span><span class="sxs-lookup"><span data-stu-id="5c833-197">Select the financial dimension set that the format of the SPED ECD text file should be based on.</span></span> <span data-ttu-id="5c833-198">O conjunto de dimensões financeiras deve incluir a conta principal e as dimensões de centro de custo.</span><span class="sxs-lookup"><span data-stu-id="5c833-198">The financial dimension set should include the main account and the cost center dimensions.</span></span>
4. <span data-ttu-id="5c833-199">Selecione o local onde o arquivo de texto do SPED ECD deve ser gerado.</span><span class="sxs-lookup"><span data-stu-id="5c833-199">Select the file location where the SPED ECD text file should be generated.</span></span>

    <span data-ttu-id="5c833-200">O tipo de registro é atribuído automaticamente com base no tipo da organização fiscal:</span><span class="sxs-lookup"><span data-stu-id="5c833-200">The booking type is assigned automatically, based on the type of fiscal organization:</span></span>
    
    - <span data-ttu-id="5c833-201">**G** – O registro é usado para todas as transações do diário do razão.</span><span class="sxs-lookup"><span data-stu-id="5c833-201">**G** – The booking is used for all the ledger journal transactions.</span></span>
    - <span data-ttu-id="5c833-202">**S** – O registro é usado para a empresa SCP.</span><span class="sxs-lookup"><span data-stu-id="5c833-202">**S** – The booking is used for the SCP company.</span></span>

5. <span data-ttu-id="5c833-203">Selecione o tipo de situação de empresa ou deixe o campo em branco se ele deve representar a situação regular.</span><span class="sxs-lookup"><span data-stu-id="5c833-203">Select the type of company situation, or leave the field blank if it should represent the regular situation.</span></span>
6. <span data-ttu-id="5c833-204">No campo **Período fiscal de abertura**, selecione uma das seguintes opções: **Regular**, **Abertura**, **Divisão, Fusão ou Aquisição** ou **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5c833-204">In the **Opening fiscal period** field, select one of the following options: **Regular**, **Opening**, **Split, Merge or Acquisition**, or **Mandatory**.</span></span>
7. <span data-ttu-id="5c833-205">Selecione a versão de layout de arquivo do formato de arquivo de texto fiscal do SPED ECD a ser gerado.</span><span class="sxs-lookup"><span data-stu-id="5c833-205">Select the file layout version of the SPED ECD text file format to generate.</span></span> <span data-ttu-id="5c833-206">As seguintes versões de layout de arquivo para ECD são suportadas atualmente:</span><span class="sxs-lookup"><span data-stu-id="5c833-206">The following file layout versions for ECD are currently supported:</span></span>

    - <span data-ttu-id="5c833-207">Versão 2.00 para SPED ECD até o ano fiscal 2013</span><span class="sxs-lookup"><span data-stu-id="5c833-207">Version 2.00 for SPED ECD until fiscal year 2013</span></span>
    - <span data-ttu-id="5c833-208">Versão 3.00 para SPED ECD até o ano fiscal 2014</span><span class="sxs-lookup"><span data-stu-id="5c833-208">Version 3.00 for SPED ECD until fiscal year 2014</span></span>
    - <span data-ttu-id="5c833-209">Versão 4.00 para SPED ECD até o ano fiscal 2015</span><span class="sxs-lookup"><span data-stu-id="5c833-209">Version 4.00 for SPED ECD until fiscal year 2015</span></span>
    - <span data-ttu-id="5c833-210">Versão 5.00 para SPED ECD até o ano fiscal 2016</span><span class="sxs-lookup"><span data-stu-id="5c833-210">Version 5.00 for SPED ECD until fiscal year 2016</span></span>

8. <span data-ttu-id="5c833-211">No campo **Número de inscrição do auditor**, insira o número do auditor da empresa.</span><span class="sxs-lookup"><span data-stu-id="5c833-211">In the **Auditor registration number** field, enter the number of the company’s auditor.</span></span>
9. <span data-ttu-id="5c833-212">Insira o nome do auditor.</span><span class="sxs-lookup"><span data-stu-id="5c833-212">Enter the auditor’s name.</span></span>
10. <span data-ttu-id="5c833-213">Se a empresa for uma empresa de grande porte, selecione a opção **Empresa de grande porte**.</span><span class="sxs-lookup"><span data-stu-id="5c833-213">If the company is a large company, select the **Large company** option.</span></span> 

> [!NOTE]
> <span data-ttu-id="5c833-214">Os campos para as etapas 8, 9 e 10 não estão disponíveis quando a versão 3.0 for selecionada.</span><span class="sxs-lookup"><span data-stu-id="5c833-214">The fields for steps 8, 9, and 10 aren't available when version 3.0 is selected.</span></span> <span data-ttu-id="5c833-215">Essas informações foram alteradas e incluídas na configuração da organização fiscal.</span><span class="sxs-lookup"><span data-stu-id="5c833-215">This information has been changed and is included in the configuration of the fiscal organization.</span></span>

<span data-ttu-id="5c833-216">Na página **Detalhes do contador**, você pode configurar informações de contador para a escrituração de imposto.</span><span class="sxs-lookup"><span data-stu-id="5c833-216">On the **Accountant details** page, you can set up accountant information for tax booking.</span></span>

