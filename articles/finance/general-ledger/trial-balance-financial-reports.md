---
title: Relatórios financeiros de balancete
description: Este artigo descreve os relatórios padrão para saldos de teste. Ele também descreve os blocos de construção que estão associados a esses relatórios e como você pode modificar os relatórios para atender às suas necessidades de negócios.
author: jinniew
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26ec03422315a280f7e779f992cf694eb5f845ea
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103649"
---
# <a name="trial-balance-financial-reports"></a><span data-ttu-id="108de-104">Relatórios financeiros de balancete</span><span class="sxs-lookup"><span data-stu-id="108de-104">Trial balance financial reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="108de-105">Este artigo descreve os relatórios padrão para saldos de teste.</span><span class="sxs-lookup"><span data-stu-id="108de-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="108de-106">Ele também descreve os blocos de construção que estão associados a esses relatórios e como você pode modificar os relatórios para atender às suas necessidades de negócios.</span><span class="sxs-lookup"><span data-stu-id="108de-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

## <a name="default-trial-balance-reports"></a><span data-ttu-id="108de-107">Relatórios do balancete padrão</span><span class="sxs-lookup"><span data-stu-id="108de-107">Default trial balance reports</span></span>

<span data-ttu-id="108de-108">Três relatórios do balancete estão disponíveis no relatório financeiro.</span><span class="sxs-lookup"><span data-stu-id="108de-108">Three trial balance reports are available in Financial reporting.</span></span>

| <span data-ttu-id="108de-109">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="108de-109">Default report</span></span>                                 | <span data-ttu-id="108de-110">O que ele faz</span><span class="sxs-lookup"><span data-stu-id="108de-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="108de-111">Balancete Detalhado - Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="108de-112">Fornece informações de saldo para todas as contas e inclui saldos de débito e crédito e suas redes com a data de transação, comprovante e descrição do diário.</span><span class="sxs-lookup"><span data-stu-id="108de-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="108de-113">Resumo do Balancete – Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="108de-114">Fornece informações de saldo de todas as contas e inclui saldos de abertura e de fechamento e os saldos de débito e de crédito, com a diferença líquida.</span><span class="sxs-lookup"><span data-stu-id="108de-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="108de-115">Resumo do Balancete Ano a Ano – Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="108de-116">Fornece informações sobre saldo para todas as contas e inclui saldos de abertura e de fechamento e saldos de débito e crédito com a diferença líquida para o ano atual e o ano passado.</span><span class="sxs-lookup"><span data-stu-id="108de-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="108de-117">Bloco de construção</span><span class="sxs-lookup"><span data-stu-id="108de-117">Building blocks</span></span>
<span data-ttu-id="108de-118">Os relatórios financeiros de balancete usam os seguintes blocos de construção.</span><span class="sxs-lookup"><span data-stu-id="108de-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="108de-119">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="108de-119">Default report</span></span>                                 | <span data-ttu-id="108de-120">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="108de-120">Row definition</span></span>          | <span data-ttu-id="108de-121">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="108de-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="108de-122">Balancete Detalhado - Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="108de-123">Balancete - Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-123">Trial Balance - Default</span></span> | <span data-ttu-id="108de-124">Balancete Detalhado - Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="108de-125">Resumo do Balancete – Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="108de-126">Balancete - Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-126">Trial Balance - Default</span></span> | <span data-ttu-id="108de-127">Balancete do resumo - Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="108de-128">Resumo do Balancete Ano a Ano – Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="108de-129">Balancete - Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-129">Trial Balance - Default</span></span> | <span data-ttu-id="108de-130">Resumo do balancete ano a ano - Padrão</span><span class="sxs-lookup"><span data-stu-id="108de-130">Summary Trial Balance Year Over Year - Default</span></span> |

> [!NOTE] 
> <span data-ttu-id="108de-131">Ao executar o relatório **Balancete** nos relatórios financeiros, marque as caixas de seleção para **Exibir linhas sem valores** e **Exibe relatórios sem linhas ativas** nas guias **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="108de-131">When running the **Trial Balance** report in Financial reporting, be sure to select the check boxes for **Display rows with no amounts** and **Display reports with no active rows** on the **Settings** tab.</span></span>

### <a name="row-definition"></a><span data-ttu-id="108de-132">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="108de-132">Row definition</span></span>

<span data-ttu-id="108de-133">A definição de linha, balancete - padrão, contém uma única linha que puxa todas as contas principais.</span><span class="sxs-lookup"><span data-stu-id="108de-133">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="108de-134">Consequentemente, qualquer pessoa pode gerar o relatório sem fazer modificações.</span><span class="sxs-lookup"><span data-stu-id="108de-134">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="108de-135">Ao visualizar o relatório, você navega na linha única para ver os detalhes sobre cada conta.</span><span class="sxs-lookup"><span data-stu-id="108de-135">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="108de-136">É possível modificar a definição da linha para que inclua mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="108de-136">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="108de-137">Para modificar a definição da linha Balancete – Padrão para que inclua linhas para todas as contas, siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="108de-137">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="108de-138">Clique em **Editar**, e clique em **Inserir linhas nas dimensões**.</span><span class="sxs-lookup"><span data-stu-id="108de-138">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="108de-139">O comando **Inserir linhas para dimensões** permite escolher as dimensões desejadas em sua definição de linha.</span><span class="sxs-lookup"><span data-stu-id="108de-139">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="108de-140">Para esta definição da linha, você utilizará **Conta principal**.</span><span class="sxs-lookup"><span data-stu-id="108de-140">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="108de-141">Verifique se **Conta principal** contém todos os E comerciais (&) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="108de-141">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="108de-142">Agora, a definição da linha contém todas as contas principais para sua entidade legal padrão.</span><span class="sxs-lookup"><span data-stu-id="108de-142">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="108de-143">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="108de-143">Column definition</span></span>

<span data-ttu-id="108de-144">Cada relatório do balancete usa uma definição da coluna diferente.</span><span class="sxs-lookup"><span data-stu-id="108de-144">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="108de-145">Essas definições da coluna contêm diferentes tipos de colunas para fornecer níveis diferentes de detalhes e dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="108de-145">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="108de-146">**Balancete detalhado – Tipos de coluna padrão:**</span><span class="sxs-lookup"><span data-stu-id="108de-146">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="108de-147">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="108de-147">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="108de-148">**ACCT** – Códigos de conta</span><span class="sxs-lookup"><span data-stu-id="108de-148">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="108de-149">**ATTR (3)** – Atributos:</span><span class="sxs-lookup"><span data-stu-id="108de-149">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="108de-150">Data da Transação</span><span class="sxs-lookup"><span data-stu-id="108de-150">Transaction Date</span></span>
        -   <span data-ttu-id="108de-151">Comprovante</span><span class="sxs-lookup"><span data-stu-id="108de-151">Voucher</span></span>
        -   <span data-ttu-id="108de-152">Descrição do diário</span><span class="sxs-lookup"><span data-stu-id="108de-152">Journal Description</span></span>
    -   <span data-ttu-id="108de-153">**DF** – Dados financeiros que contém somente débitos</span><span class="sxs-lookup"><span data-stu-id="108de-153">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="108de-154">**DF** – Dados financeiros que contenham somente créditos</span><span class="sxs-lookup"><span data-stu-id="108de-154">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="108de-155">**CALC** – A diferença líquida</span><span class="sxs-lookup"><span data-stu-id="108de-155">**CALC** – The net difference</span></span>
-   <span data-ttu-id="108de-156">**Resumo do balancete – Tipos de coluna padrão:**</span><span class="sxs-lookup"><span data-stu-id="108de-156">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="108de-157">**ACCT** – Códigos de conta</span><span class="sxs-lookup"><span data-stu-id="108de-157">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="108de-158">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="108de-158">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="108de-159">**ATTR** – Atributo:</span><span class="sxs-lookup"><span data-stu-id="108de-159">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="108de-160">Comprovante</span><span class="sxs-lookup"><span data-stu-id="108de-160">Voucher</span></span>
    -   <span data-ttu-id="108de-161">**DF** – Dados financeiros do saldo</span><span class="sxs-lookup"><span data-stu-id="108de-161">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="108de-162">**DF** – Dados financeiros que contêm somente débitos</span><span class="sxs-lookup"><span data-stu-id="108de-162">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="108de-163">**DF** – Dados financeiros que contenham somente créditos</span><span class="sxs-lookup"><span data-stu-id="108de-163">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="108de-164">**CALC** – Diferença líquida</span><span class="sxs-lookup"><span data-stu-id="108de-164">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="108de-165">**CALC** – Saldo do fechamento</span><span class="sxs-lookup"><span data-stu-id="108de-165">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="108de-166">**Resumo do balancete ano a ano – Padrão:**</span><span class="sxs-lookup"><span data-stu-id="108de-166">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="108de-167">**ACCT** – Códigos de conta</span><span class="sxs-lookup"><span data-stu-id="108de-167">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="108de-168">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="108de-168">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="108de-169">**ATTR** – Atributo</span><span class="sxs-lookup"><span data-stu-id="108de-169">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="108de-170">Comprovante</span><span class="sxs-lookup"><span data-stu-id="108de-170">Voucher</span></span>
    -   <span data-ttu-id="108de-171">**DF** – Dados financeiros do saldo inicial para o ano atual</span><span class="sxs-lookup"><span data-stu-id="108de-171">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="108de-172">**DF** – Dados financeiros que contém somente os débitos para o ano atual</span><span class="sxs-lookup"><span data-stu-id="108de-172">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="108de-173">**DF** – Dados financeiros que contêm somente os créditos para o ano atual</span><span class="sxs-lookup"><span data-stu-id="108de-173">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="108de-174">**CALC** – Diferença líquida</span><span class="sxs-lookup"><span data-stu-id="108de-174">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="108de-175">**CALC** – Saldo do fechamento</span><span class="sxs-lookup"><span data-stu-id="108de-175">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="108de-176">**DF** – Dados financeiros que contêm somente os débitos para o ano anterior</span><span class="sxs-lookup"><span data-stu-id="108de-176">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="108de-177">**DF** – Dados financeiros que contêm somente os créditos do ano anterior</span><span class="sxs-lookup"><span data-stu-id="108de-177">**FD** – Financial data that contains only credits for the last year</span></span>

## <a name="additional-resources"></a><span data-ttu-id="108de-178">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="108de-178">Additional resources</span></span>

[<span data-ttu-id="108de-179">Visão geral de relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="108de-179">Financial reporting overview</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="108de-180">Exibir relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="108de-180">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="108de-181">Blog de Relatório Financeiro do Dynamics</span><span class="sxs-lookup"><span data-stu-id="108de-181">Dynamics Financial Reporting Blog</span></span>](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
