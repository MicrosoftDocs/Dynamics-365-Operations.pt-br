---
title: "Relatórios financeiros de balancete"
description: "Este artigo descreve os relatórios padrão para saldos de teste. Ele também descreve os blocos de construção que estão associados a esses relatórios e como você pode modificar os relatórios para atender às suas necessidades de negócios."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6d5674bed7167e002e7467e1e77d333fdf1b4f8d
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="trial-balance-financial-reports"></a><span data-ttu-id="b6f89-104">Relatórios financeiros de balancete</span><span class="sxs-lookup"><span data-stu-id="b6f89-104">Trial balance financial reports</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b6f89-105">Este artigo descreve os relatórios padrão para saldos de teste.</span><span class="sxs-lookup"><span data-stu-id="b6f89-105">This article describes the default reports for trial balances.</span></span> <span data-ttu-id="b6f89-106">Ele também descreve os blocos de construção que estão associados a esses relatórios e como você pode modificar os relatórios para atender às suas necessidades de negócios.</span><span class="sxs-lookup"><span data-stu-id="b6f89-106">It also describes the building blocks that are associated with these reports and how you can modify the reports to fit your business requirements.</span></span> 

<a name="default-trial-balance-reports"></a><span data-ttu-id="b6f89-107">Relatórios do balancete padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-107">Default trial balance reports</span></span>
-----------------------------

<span data-ttu-id="b6f89-108">Três relatórios do balancete estão disponíveis no relatório financeiro no Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="b6f89-108">Three trial balance reports are available in Financial reporting in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

| <span data-ttu-id="b6f89-109">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-109">Default report</span></span>                                 | <span data-ttu-id="b6f89-110">O que ele faz</span><span class="sxs-lookup"><span data-stu-id="b6f89-110">What it does</span></span>                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b6f89-111">Balancete Detalhado - Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-111">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="b6f89-112">Fornece informações de saldo para todas as contas e inclui saldos de débito e crédito e suas redes com a data de transação, comprovante e descrição do diário.</span><span class="sxs-lookup"><span data-stu-id="b6f89-112">Provides balance information for all accounts, and includes debit and credit balances, and the net of these, together with the transaction date, voucher, and journal description.</span></span>                  |
| <span data-ttu-id="b6f89-113">Resumo do Balancete – Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-113">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="b6f89-114">Fornece informações de saldo de todas as contas e inclui saldos de abertura e de fechamento e os saldos de débito e de crédito, com a diferença líquida.</span><span class="sxs-lookup"><span data-stu-id="b6f89-114">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference.</span></span>                                        |
| <span data-ttu-id="b6f89-115">Resumo do Balancete Ano a Ano – Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-115">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="b6f89-116">Fornece informações sobre saldo para todas as contas e inclui saldos de abertura e de fechamento e saldos de débito e crédito com a diferença líquida para o ano atual e o ano passado.</span><span class="sxs-lookup"><span data-stu-id="b6f89-116">Provides balance information for all accounts, and includes opening and closing balances, and debit and credit balances, together with their net difference for the current year and the past year.</span></span> |

## <a name="building-blocks"></a><span data-ttu-id="b6f89-117">Bloco de construção</span><span class="sxs-lookup"><span data-stu-id="b6f89-117">Building blocks</span></span>
<span data-ttu-id="b6f89-118">Os relatórios financeiros de balancete usam os seguintes blocos de construção.</span><span class="sxs-lookup"><span data-stu-id="b6f89-118">The trial balance financial reports use the following building blocks.</span></span>

| <span data-ttu-id="b6f89-119">Relatório padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-119">Default report</span></span>                                 | <span data-ttu-id="b6f89-120">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="b6f89-120">Row definition</span></span>          | <span data-ttu-id="b6f89-121">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="b6f89-121">Column definition</span></span>                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| <span data-ttu-id="b6f89-122">Balancete Detalhado - Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-122">Detailed Trial Balance - Default</span></span>               | <span data-ttu-id="b6f89-123">Balancete - Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-123">Trial Balance - Default</span></span> | <span data-ttu-id="b6f89-124">Balancete Detalhado - Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-124">Detailed Trial Balance - Default</span></span>               |
| <span data-ttu-id="b6f89-125">Resumo do Balancete – Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-125">Summary Trial Balance – Default</span></span>                | <span data-ttu-id="b6f89-126">Balancete - Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-126">Trial Balance - Default</span></span> | <span data-ttu-id="b6f89-127">Balancete do resumo - Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-127">Summary Trial Balance - Default</span></span>                |
| <span data-ttu-id="b6f89-128">Resumo do Balancete Ano a Ano – Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-128">Summary Trial Balance Year Over Year – Default</span></span> | <span data-ttu-id="b6f89-129">Balancete - Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-129">Trial Balance - Default</span></span> | <span data-ttu-id="b6f89-130">Resumo do balancete ano a ano - Padrão</span><span class="sxs-lookup"><span data-stu-id="b6f89-130">Summary Trial Balance Year Over Year - Default</span></span> |

### <a name="row-definition"></a><span data-ttu-id="b6f89-131">Definição de linha</span><span class="sxs-lookup"><span data-stu-id="b6f89-131">Row definition</span></span>

<span data-ttu-id="b6f89-132">A definição de linha, balancete - padrão, contém uma única linha que puxa todas as contas principais.</span><span class="sxs-lookup"><span data-stu-id="b6f89-132">The row definition, Trial Balance – Default, contains a single row that pulls in all main accounts.</span></span> <span data-ttu-id="b6f89-133">Consequentemente, qualquer pessoa pode gerar o relatório sem fazer modificações.</span><span class="sxs-lookup"><span data-stu-id="b6f89-133">Therefore, anyone can generate the report without having to make any modifications.</span></span> <span data-ttu-id="b6f89-134">Ao visualizar o relatório, você navega na linha única para ver os detalhes sobre cada conta.</span><span class="sxs-lookup"><span data-stu-id="b6f89-134">When you view the report, you drill into the single row to see details about each account.</span></span> <span data-ttu-id="b6f89-135">É possível modificar a definição da linha para que inclua mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b6f89-135">You can modify the row definition so that it includes more detail.</span></span> <span data-ttu-id="b6f89-136">Para modificar a definição da linha Balancete – Padrão para que inclua linhas para todas as contas, siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="b6f89-136">To modify the Trial Balance – Default row definition so that it includes rows for all accounts, follow these steps.</span></span>

1.  <span data-ttu-id="b6f89-137">Clique em **Editar**, e clique em **Inserir linhas nas dimensões**.</span><span class="sxs-lookup"><span data-stu-id="b6f89-137">Click **Edit**, and then click **Insert Rows from Dimensions**.</span></span> <span data-ttu-id="b6f89-138">O comando **Inserir linhas para dimensões** permite escolher as dimensões desejadas em sua definição de linha.</span><span class="sxs-lookup"><span data-stu-id="b6f89-138">The **Insert Rows from Dimensions** command lets you choose the dimensions that you want to have in your row definition.</span></span> <span data-ttu-id="b6f89-139">Para esta definição da linha, você utilizará **Conta principal**.</span><span class="sxs-lookup"><span data-stu-id="b6f89-139">For this row definition, you're going to use **Main Account**.</span></span>
2.  <span data-ttu-id="b6f89-140">Verifique se **Conta principal** contém todos os E comerciais (&) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6f89-140">Make sure that **Main Account** contains all ampersands (&), and then click **OK**.</span></span>

<span data-ttu-id="b6f89-141">Agora, a definição da linha contém todas as contas principais para sua entidade legal padrão.</span><span class="sxs-lookup"><span data-stu-id="b6f89-141">The row definition now contains all the main accounts for your default legal entity.</span></span>

### <a name="column-definition"></a><span data-ttu-id="b6f89-142">Definição de coluna</span><span class="sxs-lookup"><span data-stu-id="b6f89-142">Column definition</span></span>

<span data-ttu-id="b6f89-143">Cada relatório do balancete usa uma definição da coluna diferente.</span><span class="sxs-lookup"><span data-stu-id="b6f89-143">Each trial balance report uses a different column definition.</span></span> <span data-ttu-id="b6f89-144">Essas definições da coluna contêm diferentes tipos de colunas para fornecer níveis diferentes de detalhes e dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="b6f89-144">These column definitions contain different types of columns to provide different levels of detail and financial data.</span></span>

-   <span data-ttu-id="b6f89-145">**Balancete detalhado – Tipos de coluna padrão:**</span><span class="sxs-lookup"><span data-stu-id="b6f89-145">**Detailed Trial Balance – Default column types:**</span></span>
    -   <span data-ttu-id="b6f89-146">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="b6f89-146">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="b6f89-147">**ACCT** – Códigos de conta</span><span class="sxs-lookup"><span data-stu-id="b6f89-147">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="b6f89-148">**ATTR (3)** – Atributos:</span><span class="sxs-lookup"><span data-stu-id="b6f89-148">**ATTR (3)** – Attributes:</span></span>
        -   <span data-ttu-id="b6f89-149">Data da Transação</span><span class="sxs-lookup"><span data-stu-id="b6f89-149">Transaction Date</span></span>
        -   <span data-ttu-id="b6f89-150">Comprovante</span><span class="sxs-lookup"><span data-stu-id="b6f89-150">Voucher</span></span>
        -   <span data-ttu-id="b6f89-151">Descrição do diário</span><span class="sxs-lookup"><span data-stu-id="b6f89-151">Journal Description</span></span>
    -   <span data-ttu-id="b6f89-152">**DF** – Dados financeiros que contém somente débitos</span><span class="sxs-lookup"><span data-stu-id="b6f89-152">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="b6f89-153">**DF** – Dados financeiros que contenham somente créditos</span><span class="sxs-lookup"><span data-stu-id="b6f89-153">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="b6f89-154">**CALC** – A diferença líquida</span><span class="sxs-lookup"><span data-stu-id="b6f89-154">**CALC** – The net difference</span></span>
-   <span data-ttu-id="b6f89-155">**Resumo do balancete – Tipos de coluna padrão:**</span><span class="sxs-lookup"><span data-stu-id="b6f89-155">**Summary Trial Balance – Default columns types:**</span></span>
    -   <span data-ttu-id="b6f89-156">**ACCT** – Códigos de conta</span><span class="sxs-lookup"><span data-stu-id="b6f89-156">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="b6f89-157">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="b6f89-157">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="b6f89-158">**ATTR** – Atributo:</span><span class="sxs-lookup"><span data-stu-id="b6f89-158">**ATTR** – An attribute:</span></span>
        -   <span data-ttu-id="b6f89-159">Comprovante</span><span class="sxs-lookup"><span data-stu-id="b6f89-159">Voucher</span></span>
    -   <span data-ttu-id="b6f89-160">**DF** – Dados financeiros do saldo</span><span class="sxs-lookup"><span data-stu-id="b6f89-160">**FD** – The beginning balance financial data</span></span>
    -   <span data-ttu-id="b6f89-161">**DF** – Dados financeiros que contêm somente débitos</span><span class="sxs-lookup"><span data-stu-id="b6f89-161">**FD** – Financial data that contains only debits</span></span>
    -   <span data-ttu-id="b6f89-162">**DF** – Dados financeiros que contenham somente créditos</span><span class="sxs-lookup"><span data-stu-id="b6f89-162">**FD** – Financial data that contains only credits</span></span>
    -   <span data-ttu-id="b6f89-163">**CALC** – Diferença líquida</span><span class="sxs-lookup"><span data-stu-id="b6f89-163">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="b6f89-164">**CALC** – Saldo do fechamento</span><span class="sxs-lookup"><span data-stu-id="b6f89-164">**CALC** – The closing balance</span></span>
-   <span data-ttu-id="b6f89-165">**Resumo do balancete ano a ano – Padrão:**</span><span class="sxs-lookup"><span data-stu-id="b6f89-165">**Summary Trial Balance Year Over Year – Default:**</span></span>
    -   <span data-ttu-id="b6f89-166">**ACCT** – Códigos de conta</span><span class="sxs-lookup"><span data-stu-id="b6f89-166">**ACCT** – Account codes</span></span>
    -   <span data-ttu-id="b6f89-167">**DESC** – A descrição da definição da linha</span><span class="sxs-lookup"><span data-stu-id="b6f89-167">**DESC** – The description from the row definition</span></span>
    -   <span data-ttu-id="b6f89-168">**ATTR** – Atributo</span><span class="sxs-lookup"><span data-stu-id="b6f89-168">**ATTR** – An attribute</span></span>
        -   <span data-ttu-id="b6f89-169">Comprovante</span><span class="sxs-lookup"><span data-stu-id="b6f89-169">Voucher</span></span>
    -   <span data-ttu-id="b6f89-170">**DF** – Dados financeiros do saldo inicial para o ano atual</span><span class="sxs-lookup"><span data-stu-id="b6f89-170">**FD** – The beginning balance financial data for the current year</span></span>
    -   <span data-ttu-id="b6f89-171">**DF** – Dados financeiros que contém somente os débitos para o ano atual</span><span class="sxs-lookup"><span data-stu-id="b6f89-171">**FD** – Financial data that contains only debits for the current year</span></span>
    -   <span data-ttu-id="b6f89-172">**DF** – Dados financeiros que contêm somente os créditos para o ano atual</span><span class="sxs-lookup"><span data-stu-id="b6f89-172">**FD** – Financial data that contains only credits for the current year</span></span>
    -   <span data-ttu-id="b6f89-173">**CALC** – Diferença líquida</span><span class="sxs-lookup"><span data-stu-id="b6f89-173">**CALC** – The net difference</span></span>
    -   <span data-ttu-id="b6f89-174">**CALC** – Saldo do fechamento</span><span class="sxs-lookup"><span data-stu-id="b6f89-174">**CALC** – The closing balance</span></span>
    -   <span data-ttu-id="b6f89-175">**DF** – Dados financeiros que contêm somente os débitos para o ano anterior</span><span class="sxs-lookup"><span data-stu-id="b6f89-175">**FD** – Financial data that contains only debits for the last year</span></span>
    -   <span data-ttu-id="b6f89-176">**DF** – Dados financeiros que contêm somente os créditos do ano anterior</span><span class="sxs-lookup"><span data-stu-id="b6f89-176">**FD** – Financial data that contains only credits for the last year</span></span>

 

<a name="see-also"></a><span data-ttu-id="b6f89-177">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b6f89-177">See also</span></span>
--------

[<span data-ttu-id="b6f89-178">Relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="b6f89-178">Financial reporting</span></span>](financial-reporting-getting-started.md)

[<span data-ttu-id="b6f89-179">Exibir relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="b6f89-179">View financial reports</span></span>](view-financial-reports.md)

[<span data-ttu-id="b6f89-180">Blog de Relatório Financeiro do Dynamics</span><span class="sxs-lookup"><span data-stu-id="b6f89-180">Dynamics Financial Reporting Blog</span></span>](http://blogs.msdn.com/b/dynamics_financial_reporting/)




