---
title: Relatórios duplos
description: Este tópico apresenta um exemplo que mostra como você pode cumprir os requisitos de relatório do Financial Reporting Standard (IFRS) e relatórios estatutários em arrendamento de ativos.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseBookMaster
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 86f42f8db707f3b8c62b9ec4c39ad6464f080748
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881147"
---
# <a name="dual-reporting"></a><span data-ttu-id="9087e-103">Relatórios duplos</span><span class="sxs-lookup"><span data-stu-id="9087e-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9087e-104">Este tópico apresenta um exemplo que mostra como você pode cumprir os requisitos de relatório do Financial Reporting Standard (IFRS) e relatórios estatutários em arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="9087e-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="9087e-105">A familiaridade com lançamentos de camadas no Microsoft Dynamics 365 Finance é necessária e facilitará o entendimento do exemplo.</span><span class="sxs-lookup"><span data-stu-id="9087e-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="9087e-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9087e-106">Example</span></span>

<span data-ttu-id="9087e-107">O exemplo a seguir conta um arrendamento no relatório estatutário italiano usando o método de base de caixa e o modo de relatório do IFRS.</span><span class="sxs-lookup"><span data-stu-id="9087e-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="9087e-108">A empresa deve estabelecer três registros para cumprir os requisitos legais da Itália e os requisitos do IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="9087e-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="9087e-109">Um registro é necessário para o IFRS 16, outro é necessário para os requisitos estatutários e outro é necessário para reverter automaticamente lançamentos estatutários.</span><span class="sxs-lookup"><span data-stu-id="9087e-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="9087e-110">Os registros são configurados conforme mostrado nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="9087e-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="9087e-111">**Registro IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="9087e-111">**IFRS 16 book**</span></span>

<span data-ttu-id="9087e-112">O livro IFRS 16 é configurado de forma que ele cumpra com o padrão de contabilidade IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="9087e-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="9087e-113">Todas as entradas lançadas neste manual serão lançadas em uma camada personalizada.</span><span class="sxs-lookup"><span data-stu-id="9087e-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="9087e-114">Organização</span><span class="sxs-lookup"><span data-stu-id="9087e-114">Name</span></span>                                    | <span data-ttu-id="9087e-115">descrição</span><span class="sxs-lookup"><span data-stu-id="9087e-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="9087e-116">Tipo de livro</span><span class="sxs-lookup"><span data-stu-id="9087e-116">Book type</span></span>                               | <span data-ttu-id="9087e-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="9087e-117">IFRS 16</span></span>        |
| <span data-ttu-id="9087e-118">Descrição do registro</span><span class="sxs-lookup"><span data-stu-id="9087e-118">Book description</span></span>                        | <span data-ttu-id="9087e-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="9087e-119">IFRS 16</span></span>        |
| <span data-ttu-id="9087e-120">Nível de Lançamento</span><span class="sxs-lookup"><span data-stu-id="9087e-120">Posting Layer</span></span>                           | <span data-ttu-id="9087e-121">Camada personalizada 1</span><span class="sxs-lookup"><span data-stu-id="9087e-121">Custom layer 1</span></span> |
| <span data-ttu-id="9087e-122">Tipo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="9087e-122">Lease Type</span></span>                              | <span data-ttu-id="9087e-123">Finance</span><span class="sxs-lookup"><span data-stu-id="9087e-123">Finance</span></span>        |
| <span data-ttu-id="9087e-124">Estrutura contábil</span><span class="sxs-lookup"><span data-stu-id="9087e-124">Accounting Framework</span></span>                    | <span data-ttu-id="9087e-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="9087e-125">IFRS 16</span></span>        |
| <span data-ttu-id="9087e-126">Configuração de prazo do arrendamento / vida útil</span><span class="sxs-lookup"><span data-stu-id="9087e-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="9087e-127">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-127">0.00</span></span>           |
| <span data-ttu-id="9087e-128">Configuração de valor presente / valor justo do ativo</span><span class="sxs-lookup"><span data-stu-id="9087e-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="9087e-129">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-129">0.00</span></span>           |
| <span data-ttu-id="9087e-130">Limite de curto prazo</span><span class="sxs-lookup"><span data-stu-id="9087e-130">Short-term threshold</span></span>                    | <span data-ttu-id="9087e-131">12</span><span class="sxs-lookup"><span data-stu-id="9087e-131">12</span></span>             |
| <span data-ttu-id="9087e-132">Limite de valor baixo</span><span class="sxs-lookup"><span data-stu-id="9087e-132">Low Value Threshold</span></span>                     | <span data-ttu-id="9087e-133">5.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-133">5,000.00</span></span>       |
| <span data-ttu-id="9087e-134">Pagar ao fornecedor</span><span class="sxs-lookup"><span data-stu-id="9087e-134">Pay to Vendor</span></span>                           | <span data-ttu-id="9087e-135">Não</span><span class="sxs-lookup"><span data-stu-id="9087e-135">No</span></span>             |

<span data-ttu-id="9087e-136">**Livro fiscal**</span><span class="sxs-lookup"><span data-stu-id="9087e-136">**Statutory book**</span></span>

<span data-ttu-id="9087e-137">O livro fiscal é um registro de base de caixa em que a empresa contará com as despesas de arrendamento como o valor de pagamento à vista pago mensalmente por aluguel.</span><span class="sxs-lookup"><span data-stu-id="9087e-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="9087e-138">Esse registro não produzirá um ativo de direito de uso (DDU) ou uma responsabilidade de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="9087e-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="9087e-139">Organização</span><span class="sxs-lookup"><span data-stu-id="9087e-139">Name</span></span>                                    | <span data-ttu-id="9087e-140">descrição</span><span class="sxs-lookup"><span data-stu-id="9087e-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="9087e-141">Tipo de livro</span><span class="sxs-lookup"><span data-stu-id="9087e-141">Book type</span></span>                               | <span data-ttu-id="9087e-142">Fiscal</span><span class="sxs-lookup"><span data-stu-id="9087e-142">Statutory</span></span>   |
| <span data-ttu-id="9087e-143">Descrição do registro</span><span class="sxs-lookup"><span data-stu-id="9087e-143">Book description</span></span>                        | <span data-ttu-id="9087e-144">GAAP Local</span><span class="sxs-lookup"><span data-stu-id="9087e-144">Local GAAP</span></span>  |
| <span data-ttu-id="9087e-145">Nível de Lançamento</span><span class="sxs-lookup"><span data-stu-id="9087e-145">Posting Layer</span></span>                           | <span data-ttu-id="9087e-146">Atual</span><span class="sxs-lookup"><span data-stu-id="9087e-146">Current</span></span>     |
| <span data-ttu-id="9087e-147">Tipo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="9087e-147">Lease Type</span></span>                              | <span data-ttu-id="9087e-148">Automática</span><span class="sxs-lookup"><span data-stu-id="9087e-148">Automatic</span></span>   |
| <span data-ttu-id="9087e-149">Estrutura contábil</span><span class="sxs-lookup"><span data-stu-id="9087e-149">Accounting Framework</span></span>                    | <span data-ttu-id="9087e-150">Base de pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="9087e-150">Cash basis</span></span>  |
| <span data-ttu-id="9087e-151">Configuração de prazo do arrendamento / vida útil</span><span class="sxs-lookup"><span data-stu-id="9087e-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="9087e-152">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-152">0.00</span></span>        |
| <span data-ttu-id="9087e-153">Configuração de valor presente / valor justo do ativo</span><span class="sxs-lookup"><span data-stu-id="9087e-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="9087e-154">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-154">0.00</span></span>        |
| <span data-ttu-id="9087e-155">Limite de curto prazo</span><span class="sxs-lookup"><span data-stu-id="9087e-155">Short-term threshold</span></span>                    | <span data-ttu-id="9087e-156">0</span><span class="sxs-lookup"><span data-stu-id="9087e-156">0</span></span>           |
| <span data-ttu-id="9087e-157">Limite de valor baixo</span><span class="sxs-lookup"><span data-stu-id="9087e-157">Low Value Threshold</span></span>                     | <span data-ttu-id="9087e-158">0</span><span class="sxs-lookup"><span data-stu-id="9087e-158">0</span></span>           |
| <span data-ttu-id="9087e-159">Pagar ao fornecedor</span><span class="sxs-lookup"><span data-stu-id="9087e-159">Pay to Vendor</span></span>                           | <span data-ttu-id="9087e-160">Não</span><span class="sxs-lookup"><span data-stu-id="9087e-160">No</span></span>          |

<span data-ttu-id="9087e-161">**Livro de estorno fiscal**</span><span class="sxs-lookup"><span data-stu-id="9087e-161">**Statutory reversal book**</span></span>

<span data-ttu-id="9087e-162">O livro de estorno fiscal é configurado da mesma forma que o livro fiscal.</span><span class="sxs-lookup"><span data-stu-id="9087e-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="9087e-163">Organização</span><span class="sxs-lookup"><span data-stu-id="9087e-163">Name</span></span>                                    | <span data-ttu-id="9087e-164">descrição</span><span class="sxs-lookup"><span data-stu-id="9087e-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="9087e-165">Tipo de livro</span><span class="sxs-lookup"><span data-stu-id="9087e-165">Book type</span></span>                               | <span data-ttu-id="9087e-166">Fiscal - Estorno</span><span class="sxs-lookup"><span data-stu-id="9087e-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="9087e-167">Descrição do registro</span><span class="sxs-lookup"><span data-stu-id="9087e-167">Book description</span></span>                        | <span data-ttu-id="9087e-168">Registro para reverter o livro fiscal</span><span class="sxs-lookup"><span data-stu-id="9087e-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="9087e-169">Nível de Lançamento</span><span class="sxs-lookup"><span data-stu-id="9087e-169">Posting Layer</span></span>                           | <span data-ttu-id="9087e-170">Camada personalizada 1</span><span class="sxs-lookup"><span data-stu-id="9087e-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="9087e-171">Tipo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="9087e-171">Lease Type</span></span>                              | <span data-ttu-id="9087e-172">Automática</span><span class="sxs-lookup"><span data-stu-id="9087e-172">Automatic</span></span>                      |
| <span data-ttu-id="9087e-173">Estrutura contábil</span><span class="sxs-lookup"><span data-stu-id="9087e-173">Accounting Framework</span></span>                    | <span data-ttu-id="9087e-174">Base de pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="9087e-174">Cash basis</span></span>                     |
| <span data-ttu-id="9087e-175">Configuração de prazo do arrendamento / vida útil</span><span class="sxs-lookup"><span data-stu-id="9087e-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="9087e-176">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-176">0.00</span></span>                           |
| <span data-ttu-id="9087e-177">Configuração de valor presente / valor justo do ativo</span><span class="sxs-lookup"><span data-stu-id="9087e-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="9087e-178">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-178">0.00</span></span>                           |
| <span data-ttu-id="9087e-179">Limite de curto prazo</span><span class="sxs-lookup"><span data-stu-id="9087e-179">Short-term threshold</span></span>                    | <span data-ttu-id="9087e-180">0</span><span class="sxs-lookup"><span data-stu-id="9087e-180">0</span></span>                              |
| <span data-ttu-id="9087e-181">Limite de valor baixo</span><span class="sxs-lookup"><span data-stu-id="9087e-181">Low Value Threshold</span></span>                     | <span data-ttu-id="9087e-182">0</span><span class="sxs-lookup"><span data-stu-id="9087e-182">0</span></span>                              |
| <span data-ttu-id="9087e-183">Pagar ao fornecedor</span><span class="sxs-lookup"><span data-stu-id="9087e-183">Pay to Vendor</span></span>                           | <span data-ttu-id="9087e-184">Não</span><span class="sxs-lookup"><span data-stu-id="9087e-184">No</span></span>                             |

<span data-ttu-id="9087e-185">Neste exemplo, um arrendamento foi criado com as seguintes configurações nas guias **Geral** **Linhas de agendamento de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="9087e-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="9087e-186">**Guia Geral**</span><span class="sxs-lookup"><span data-stu-id="9087e-186">**General tab**</span></span>

| <span data-ttu-id="9087e-187">Campo</span><span class="sxs-lookup"><span data-stu-id="9087e-187">Field</span></span>                      | <span data-ttu-id="9087e-188">Alíquota</span><span class="sxs-lookup"><span data-stu-id="9087e-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="9087e-189">Taxa incremental de empréstimo</span><span class="sxs-lookup"><span data-stu-id="9087e-189">Incremental borrowing rate</span></span> | <span data-ttu-id="9087e-190">5%</span><span class="sxs-lookup"><span data-stu-id="9087e-190">5%</span></span>               |
| <span data-ttu-id="9087e-191">Data de início</span><span class="sxs-lookup"><span data-stu-id="9087e-191">Commencement date</span></span>          | <span data-ttu-id="9087e-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="9087e-192">1/1/2020</span></span>         |
| <span data-ttu-id="9087e-193">Grupo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="9087e-193">Lease group</span></span>                | <span data-ttu-id="9087e-194">Instalações</span><span class="sxs-lookup"><span data-stu-id="9087e-194">Buildings</span></span>        |
| <span data-ttu-id="9087e-195">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="9087e-195">Vendor</span></span>                     | <span data-ttu-id="9087e-196">1001</span><span class="sxs-lookup"><span data-stu-id="9087e-196">1001</span></span>             |
| <span data-ttu-id="9087e-197">Valor justo do ativo</span><span class="sxs-lookup"><span data-stu-id="9087e-197">Fair value of the asset</span></span>    | <span data-ttu-id="9087e-198">245.000</span><span class="sxs-lookup"><span data-stu-id="9087e-198">245,000</span></span>          |
| <span data-ttu-id="9087e-199">Vida útil do ativo</span><span class="sxs-lookup"><span data-stu-id="9087e-199">Asset useful life</span></span>          | <span data-ttu-id="9087e-200">120</span><span class="sxs-lookup"><span data-stu-id="9087e-200">120</span></span>              |
| <span data-ttu-id="9087e-201">Tipo de anuidade</span><span class="sxs-lookup"><span data-stu-id="9087e-201">Annuity type</span></span>               | <span data-ttu-id="9087e-202">Anuidade comum</span><span class="sxs-lookup"><span data-stu-id="9087e-202">Ordinary annuity</span></span> |
| <span data-ttu-id="9087e-203">Intervalo de composição</span><span class="sxs-lookup"><span data-stu-id="9087e-203">Compounding interval</span></span>       | <span data-ttu-id="9087e-204">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="9087e-204">Monthly</span></span>          |

<span data-ttu-id="9087e-205">**Guia Linhas de agenda de pagamento**</span><span class="sxs-lookup"><span data-stu-id="9087e-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="9087e-206">Campo</span><span class="sxs-lookup"><span data-stu-id="9087e-206">Field</span></span>             | <span data-ttu-id="9087e-207">Alíquota</span><span class="sxs-lookup"><span data-stu-id="9087e-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="9087e-208">Data inicial</span><span class="sxs-lookup"><span data-stu-id="9087e-208">Start date</span></span>        | <span data-ttu-id="9087e-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="9087e-209">1/1/2020</span></span>   |
| <span data-ttu-id="9087e-210">Intervalo do período</span><span class="sxs-lookup"><span data-stu-id="9087e-210">Period interval</span></span>   | <span data-ttu-id="9087e-211">Meses</span><span class="sxs-lookup"><span data-stu-id="9087e-211">Months</span></span>     |
| <span data-ttu-id="9087e-212">Períodos</span><span class="sxs-lookup"><span data-stu-id="9087e-212">Periods</span></span>           | <span data-ttu-id="9087e-213">24</span><span class="sxs-lookup"><span data-stu-id="9087e-213">24</span></span>         |
| <span data-ttu-id="9087e-214">Data de término</span><span class="sxs-lookup"><span data-stu-id="9087e-214">End date</span></span>          | <span data-ttu-id="9087e-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="9087e-215">12/31/2020</span></span> |
| <span data-ttu-id="9087e-216">Frequência de pagamento</span><span class="sxs-lookup"><span data-stu-id="9087e-216">Payment frequency</span></span> | <span data-ttu-id="9087e-217">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="9087e-217">Monthly</span></span>    |
| <span data-ttu-id="9087e-218">Valor do pagamento</span><span class="sxs-lookup"><span data-stu-id="9087e-218">Payment amount</span></span>    | <span data-ttu-id="9087e-219">1.000</span><span class="sxs-lookup"><span data-stu-id="9087e-219">1,000</span></span>      |

<span data-ttu-id="9087e-220">Para considerar esse arrendamento em duas estruturas, use um nível de lançamento atual e um nível de lançamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="9087e-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="9087e-221">A tabela a seguir mostra um exemplo de cada entrada de diário que represente razoavelmente as finanças sob cada padrão de relatório.</span><span class="sxs-lookup"><span data-stu-id="9087e-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="9087e-222">Posteriormente, é fornecida uma descrição detalhada de cada entrada de diário para o primeiro mês do arrendamento.</span><span class="sxs-lookup"><span data-stu-id="9087e-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="9087e-223">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="9087e-224">descrição</span><span class="sxs-lookup"><span data-stu-id="9087e-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="9087e-225">Livro fiscal (nível atual)</span><span class="sxs-lookup"><span data-stu-id="9087e-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="9087e-226">Total do nível atual</span><span class="sxs-lookup"><span data-stu-id="9087e-226">Current layer total</span></span></th>
<th><span data-ttu-id="9087e-227">Registro de estorno (nível personalizado)</span><span class="sxs-lookup"><span data-stu-id="9087e-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="9087e-228">Registro IFRS 16 (nível personalizado)</span><span class="sxs-lookup"><span data-stu-id="9087e-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="9087e-229">Nível atual + total do nível personalizado</span><span class="sxs-lookup"><span data-stu-id="9087e-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="9087e-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="9087e-230">JE-100</span></span></th>
<th><span data-ttu-id="9087e-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="9087e-231">JE-110</span></span></th>
<th><span data-ttu-id="9087e-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="9087e-232">JE-120</span></span></th>
<th><span data-ttu-id="9087e-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="9087e-233">JE-130</span></span></th>
<th><span data-ttu-id="9087e-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="9087e-234">JE-140</span></span></th>
<th><span data-ttu-id="9087e-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="9087e-235">JE-150</span></span></th>
<th><span data-ttu-id="9087e-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="9087e-236">JE-160</span></span></th>
<th><span data-ttu-id="9087e-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="9087e-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="9087e-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9087e-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9087e-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9087e-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9087e-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9087e-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9087e-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9087e-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9087e-246">1</span><span class="sxs-lookup"><span data-stu-id="9087e-246">1</span></span></td>
<td><span data-ttu-id="9087e-247">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="9087e-247">Lease expense</span></span></td>
<td><span data-ttu-id="9087e-248">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-249">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-249">1,000.00</span></span></td>
<td><span data-ttu-id="9087e-250">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-251">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-252">2</span><span class="sxs-lookup"><span data-stu-id="9087e-252">2</span></span></td>
<td><span data-ttu-id="9087e-253">Tarifa bancária</span><span class="sxs-lookup"><span data-stu-id="9087e-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-254">3,00</span><span class="sxs-lookup"><span data-stu-id="9087e-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-255">3,00</span><span class="sxs-lookup"><span data-stu-id="9087e-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-256">3,00</span><span class="sxs-lookup"><span data-stu-id="9087e-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-257">3</span><span class="sxs-lookup"><span data-stu-id="9087e-257">3</span></span></td>
<td><span data-ttu-id="9087e-258">Despesa IVA</span><span class="sxs-lookup"><span data-stu-id="9087e-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-259">5,00</span><span class="sxs-lookup"><span data-stu-id="9087e-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-260">5,00</span><span class="sxs-lookup"><span data-stu-id="9087e-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-261">5,00</span><span class="sxs-lookup"><span data-stu-id="9087e-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-262">4</span><span class="sxs-lookup"><span data-stu-id="9087e-262">4</span></span></td>
<td><span data-ttu-id="9087e-263">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="9087e-263">Clearing account</span></span></td>
<td><span data-ttu-id="9087e-264">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-264">-1,000.00</span></span></td>
<td><span data-ttu-id="9087e-265">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-266">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-266">0.00</span></span></td>
<td><span data-ttu-id="9087e-267">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-268">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-269">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-270">5</span><span class="sxs-lookup"><span data-stu-id="9087e-270">5</span></span></td>
<td><span data-ttu-id="9087e-271">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="9087e-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-272">-1,008.00</span></span></td>
<td><span data-ttu-id="9087e-273">1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-273">1,008.00</span></span></td>
<td><span data-ttu-id="9087e-274">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-275">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-276">6</span><span class="sxs-lookup"><span data-stu-id="9087e-276">6</span></span></td>
<td><span data-ttu-id="9087e-277">Ativo DDU</span><span class="sxs-lookup"><span data-stu-id="9087e-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-278">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-279">22.794,00</span><span class="sxs-lookup"><span data-stu-id="9087e-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-280">22.793,90</span><span class="sxs-lookup"><span data-stu-id="9087e-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-281">7</span><span class="sxs-lookup"><span data-stu-id="9087e-281">7</span></span></td>
<td><span data-ttu-id="9087e-282">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="9087e-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-283">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="9087e-284">-22,794.00</span></span></td>
<td><span data-ttu-id="9087e-285">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-285">1,000.00</span></span></td>
<td><span data-ttu-id="9087e-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="9087e-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="9087e-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-288">8</span><span class="sxs-lookup"><span data-stu-id="9087e-288">8</span></span></td>
<td><span data-ttu-id="9087e-289">Despesa de Juros</span><span class="sxs-lookup"><span data-stu-id="9087e-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-290">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-291">94,97</span><span class="sxs-lookup"><span data-stu-id="9087e-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-292">94,97</span><span class="sxs-lookup"><span data-stu-id="9087e-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-293">9</span><span class="sxs-lookup"><span data-stu-id="9087e-293">9</span></span></td>
<td><span data-ttu-id="9087e-294">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="9087e-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-295">-1,008.00</span></span></td>
<td><span data-ttu-id="9087e-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-298">10</span><span class="sxs-lookup"><span data-stu-id="9087e-298">10</span></span></td>
<td><span data-ttu-id="9087e-299">Despesa de Depreciação</span><span class="sxs-lookup"><span data-stu-id="9087e-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-300">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-301">949,75</span><span class="sxs-lookup"><span data-stu-id="9087e-301">949.75</span></span></td>
<td><span data-ttu-id="9087e-302">949,75</span><span class="sxs-lookup"><span data-stu-id="9087e-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-303">11</span><span class="sxs-lookup"><span data-stu-id="9087e-303">11</span></span></td>
<td><span data-ttu-id="9087e-304">Depreciação Acumulada</span><span class="sxs-lookup"><span data-stu-id="9087e-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-305">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="9087e-306">-949.75</span></span></td>
<td><span data-ttu-id="9087e-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="9087e-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9087e-308">Como mostra a tabela acima, é necessário reportar três registros em relatórios fiscais e em relatórios IFRS.</span><span class="sxs-lookup"><span data-stu-id="9087e-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="9087e-309">O livro fiscal registra o pagamento do arrendamento de acordo com as regras para a contabilidade de base de caixa no nível atual.</span><span class="sxs-lookup"><span data-stu-id="9087e-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="9087e-310">O registro de estorno fiscal inverte as entradas do diário fiscal.</span><span class="sxs-lookup"><span data-stu-id="9087e-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="9087e-311">O registro IFRS 16 cria as entradas de diário requeridas pelo IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="9087e-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="9087e-312">É necessário inserir um arrendamento somente uma vez.</span><span class="sxs-lookup"><span data-stu-id="9087e-312">You must enter a lease only one time.</span></span> <span data-ttu-id="9087e-313">Em seguida, você poderá abrir a página **Registros** para ver todos os registros associados ao arrendamento.</span><span class="sxs-lookup"><span data-stu-id="9087e-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="9087e-314">Quando você cria os registros, todos os três devem ser associados ao mesmo registro de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="9087e-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="9087e-315">A primeira entrada de diário registra a despesa de arrendamento mediante o livro fiscal.</span><span class="sxs-lookup"><span data-stu-id="9087e-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="9087e-316">Você pode criar os pagamentos em um lote ou selecionando o plano de pagamento no livro fiscal.</span><span class="sxs-lookup"><span data-stu-id="9087e-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="9087e-317">Neste exemplo, a entrada de diário a seguir é criada para o livro fiscal no plano de pagamento.</span><span class="sxs-lookup"><span data-stu-id="9087e-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="9087e-318">Pagamento de arrendamento – 31/1/2020 – JE 100</span><span class="sxs-lookup"><span data-stu-id="9087e-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="9087e-319">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="9087e-319">Account type</span></span> | <span data-ttu-id="9087e-320">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-320">Account number</span></span> | <span data-ttu-id="9087e-321">Camada</span><span class="sxs-lookup"><span data-stu-id="9087e-321">Layer</span></span>   | <span data-ttu-id="9087e-322">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-322">Account description</span></span> | <span data-ttu-id="9087e-323">Débito</span><span class="sxs-lookup"><span data-stu-id="9087e-323">Debit</span></span>    | <span data-ttu-id="9087e-324">Crédito</span><span class="sxs-lookup"><span data-stu-id="9087e-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="9087e-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-325">Ledger</span></span>       | <span data-ttu-id="9087e-326">1</span><span class="sxs-lookup"><span data-stu-id="9087e-326">1</span></span>              | <span data-ttu-id="9087e-327">Atual</span><span class="sxs-lookup"><span data-stu-id="9087e-327">Current</span></span> | <span data-ttu-id="9087e-328">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="9087e-328">Lease expense</span></span>       | <span data-ttu-id="9087e-329">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-329">1,000.00</span></span> |          |
| <span data-ttu-id="9087e-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-330">Ledger</span></span>       | <span data-ttu-id="9087e-331">4</span><span class="sxs-lookup"><span data-stu-id="9087e-331">4</span></span>              | <span data-ttu-id="9087e-332">Atual</span><span class="sxs-lookup"><span data-stu-id="9087e-332">Current</span></span> | <span data-ttu-id="9087e-333">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="9087e-333">Clearing account</span></span>    |          | <span data-ttu-id="9087e-334">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-334">1,000.00</span></span> |

<span data-ttu-id="9087e-335">Um auxiliar de contas a pagar usa a funcionalidade padrão do Dynamics 365 para criar uma fatura a pagar para o arrendamento fora do Arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="9087e-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="9087e-336">No entanto, em vez de selecionar **Despesa de arrendamento** como a conta de débito, o auxiliar de contas a pagar seleciona uma conta de compensação para gerar a entrada a seguir.</span><span class="sxs-lookup"><span data-stu-id="9087e-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="9087e-337">Processo de AP - 31/1/2020 – JE 110</span><span class="sxs-lookup"><span data-stu-id="9087e-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="9087e-338">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="9087e-338">Account type</span></span> | <span data-ttu-id="9087e-339">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-339">Account number</span></span> | <span data-ttu-id="9087e-340">Camada</span><span class="sxs-lookup"><span data-stu-id="9087e-340">Layer</span></span>   | <span data-ttu-id="9087e-341">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-341">Account description</span></span> | <span data-ttu-id="9087e-342">Débito</span><span class="sxs-lookup"><span data-stu-id="9087e-342">Debit</span></span>    | <span data-ttu-id="9087e-343">Crédito</span><span class="sxs-lookup"><span data-stu-id="9087e-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="9087e-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-344">Ledger</span></span>       | <span data-ttu-id="9087e-345">4</span><span class="sxs-lookup"><span data-stu-id="9087e-345">4</span></span>              | <span data-ttu-id="9087e-346">Atual</span><span class="sxs-lookup"><span data-stu-id="9087e-346">Current</span></span> | <span data-ttu-id="9087e-347">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="9087e-347">Clearing account</span></span>    | <span data-ttu-id="9087e-348">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-348">1,000.00</span></span> |          |
| <span data-ttu-id="9087e-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-349">Ledger</span></span>       | <span data-ttu-id="9087e-350">2</span><span class="sxs-lookup"><span data-stu-id="9087e-350">2</span></span>              | <span data-ttu-id="9087e-351">Atual</span><span class="sxs-lookup"><span data-stu-id="9087e-351">Current</span></span> | <span data-ttu-id="9087e-352">Tarifa bancária</span><span class="sxs-lookup"><span data-stu-id="9087e-352">Bank fee</span></span>            | <span data-ttu-id="9087e-353">3,00</span><span class="sxs-lookup"><span data-stu-id="9087e-353">3.00</span></span>     |          |
| <span data-ttu-id="9087e-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-354">Ledger</span></span>       | <span data-ttu-id="9087e-355">3</span><span class="sxs-lookup"><span data-stu-id="9087e-355">3</span></span>              | <span data-ttu-id="9087e-356">Atual</span><span class="sxs-lookup"><span data-stu-id="9087e-356">Current</span></span> | <span data-ttu-id="9087e-357">Despesa IVA</span><span class="sxs-lookup"><span data-stu-id="9087e-357">VAT expense</span></span>         | <span data-ttu-id="9087e-358">5,00</span><span class="sxs-lookup"><span data-stu-id="9087e-358">5.00</span></span>     |          |
| <span data-ttu-id="9087e-359">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="9087e-359">Vendor</span></span>       | <span data-ttu-id="9087e-360">5</span><span class="sxs-lookup"><span data-stu-id="9087e-360">5</span></span>              | <span data-ttu-id="9087e-361">Atual</span><span class="sxs-lookup"><span data-stu-id="9087e-361">Current</span></span> | <span data-ttu-id="9087e-362">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="9087e-362">Accounts payable</span></span>    |          | <span data-ttu-id="9087e-363">1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-363">1,008.00</span></span> |

<span data-ttu-id="9087e-364">Quando a instrução for emitida para o fornecedor, você seguirá o processo de pagamento regular.</span><span class="sxs-lookup"><span data-stu-id="9087e-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="9087e-365">Durante esse processo, a entrada de diário a seguir é gerada.</span><span class="sxs-lookup"><span data-stu-id="9087e-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="9087e-366">Pagamento à vista – 31/1/2020 – JE 120</span><span class="sxs-lookup"><span data-stu-id="9087e-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="9087e-367">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="9087e-367">Account type</span></span> | <span data-ttu-id="9087e-368">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-368">Account number</span></span> | <span data-ttu-id="9087e-369">Camada</span><span class="sxs-lookup"><span data-stu-id="9087e-369">Layer</span></span>   | <span data-ttu-id="9087e-370">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-370">Account description</span></span> | <span data-ttu-id="9087e-371">Débito</span><span class="sxs-lookup"><span data-stu-id="9087e-371">Debit</span></span>    | <span data-ttu-id="9087e-372">Crédito</span><span class="sxs-lookup"><span data-stu-id="9087e-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="9087e-373">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="9087e-373">Vendor</span></span>       | <span data-ttu-id="9087e-374">5</span><span class="sxs-lookup"><span data-stu-id="9087e-374">5</span></span>              | <span data-ttu-id="9087e-375">Atual</span><span class="sxs-lookup"><span data-stu-id="9087e-375">Current</span></span> | <span data-ttu-id="9087e-376">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="9087e-376">Accounts Payable</span></span>    | <span data-ttu-id="9087e-377">1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-377">1,008.00</span></span> |          |
| <span data-ttu-id="9087e-378">Banco</span><span class="sxs-lookup"><span data-stu-id="9087e-378">Bank</span></span>         | <span data-ttu-id="9087e-379">9</span><span class="sxs-lookup"><span data-stu-id="9087e-379">9</span></span>              | <span data-ttu-id="9087e-380">Atual</span><span class="sxs-lookup"><span data-stu-id="9087e-380">Current</span></span> | <span data-ttu-id="9087e-381">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="9087e-381">Cash</span></span>                |          | <span data-ttu-id="9087e-382">1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-382">1,008.00</span></span> |

<span data-ttu-id="9087e-383">Nessa situação, você cumpriu a conformidade total desse arrendamento mediante os requisitos de relatórios estatutários e pode gerar um balancete usando o nível atual.</span><span class="sxs-lookup"><span data-stu-id="9087e-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="9087e-384">O sistema retorna um balancete que tem os seguintes números.</span><span class="sxs-lookup"><span data-stu-id="9087e-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="9087e-385">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="9087e-386">Descrição</span><span class="sxs-lookup"><span data-stu-id="9087e-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="9087e-387">Livro fiscal (nível atual)</span><span class="sxs-lookup"><span data-stu-id="9087e-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="9087e-388">Total do nível atual</span><span class="sxs-lookup"><span data-stu-id="9087e-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="9087e-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="9087e-389">JE-100</span></span></th>
<th><span data-ttu-id="9087e-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="9087e-390">JE-110</span></span></th>
<th><span data-ttu-id="9087e-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="9087e-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="9087e-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9087e-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="9087e-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="9087e-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="9087e-395">1</span><span class="sxs-lookup"><span data-stu-id="9087e-395">1</span></span></td>
<td><span data-ttu-id="9087e-396">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="9087e-396">Lease expense</span></span></td>
<td><span data-ttu-id="9087e-397">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-398">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-399">2</span><span class="sxs-lookup"><span data-stu-id="9087e-399">2</span></span></td>
<td><span data-ttu-id="9087e-400">Tarifa bancária</span><span class="sxs-lookup"><span data-stu-id="9087e-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-401">3,00</span><span class="sxs-lookup"><span data-stu-id="9087e-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-402">3,00</span><span class="sxs-lookup"><span data-stu-id="9087e-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-403">3</span><span class="sxs-lookup"><span data-stu-id="9087e-403">3</span></span></td>
<td><span data-ttu-id="9087e-404">Despesa IVA</span><span class="sxs-lookup"><span data-stu-id="9087e-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-405">5,00</span><span class="sxs-lookup"><span data-stu-id="9087e-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-406">5,00</span><span class="sxs-lookup"><span data-stu-id="9087e-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-407">4</span><span class="sxs-lookup"><span data-stu-id="9087e-407">4</span></span></td>
<td><span data-ttu-id="9087e-408">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="9087e-408">Clearing account</span></span></td>
<td><span data-ttu-id="9087e-409">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-409">-1,000.00</span></span></td>
<td><span data-ttu-id="9087e-410">1.000.00</span><span class="sxs-lookup"><span data-stu-id="9087e-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-411">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-412">5</span><span class="sxs-lookup"><span data-stu-id="9087e-412">5</span></span></td>
<td><span data-ttu-id="9087e-413">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="9087e-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="9087e-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-414">-1,008.00</span></span></td>
<td><span data-ttu-id="9087e-415">1.008.00</span><span class="sxs-lookup"><span data-stu-id="9087e-415">1,008.00</span></span></td>
<td><span data-ttu-id="9087e-416">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-417">6</span><span class="sxs-lookup"><span data-stu-id="9087e-417">6</span></span></td>
<td><span data-ttu-id="9087e-418">Ativo DDU</span><span class="sxs-lookup"><span data-stu-id="9087e-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-419">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-420">7</span><span class="sxs-lookup"><span data-stu-id="9087e-420">7</span></span></td>
<td><span data-ttu-id="9087e-421">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="9087e-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-422">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-423">8</span><span class="sxs-lookup"><span data-stu-id="9087e-423">8</span></span></td>
<td><span data-ttu-id="9087e-424">Despesa de Juros</span><span class="sxs-lookup"><span data-stu-id="9087e-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-425">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-426">9</span><span class="sxs-lookup"><span data-stu-id="9087e-426">9</span></span></td>
<td><span data-ttu-id="9087e-427">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="9087e-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-428">-1,008.00</span></span></td>
<td><span data-ttu-id="9087e-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="9087e-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-430">10</span><span class="sxs-lookup"><span data-stu-id="9087e-430">10</span></span></td>
<td><span data-ttu-id="9087e-431">Despesa de Depreciação</span><span class="sxs-lookup"><span data-stu-id="9087e-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-432">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9087e-433">11</span><span class="sxs-lookup"><span data-stu-id="9087e-433">11</span></span></td>
<td><span data-ttu-id="9087e-434">Depreciação Acumulada</span><span class="sxs-lookup"><span data-stu-id="9087e-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="9087e-435">0,00</span><span class="sxs-lookup"><span data-stu-id="9087e-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9087e-436">Se você quiser usar os números do IFRS 16 para executar o mesmo balancete, as entradas do diário contábil fiscal devem ser revertidas, e as entradas de diário de IFRS 16 devem ser lançadas.</span><span class="sxs-lookup"><span data-stu-id="9087e-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="9087e-437">Para reverter as entradas de diário estatutário, este exemplo inclui um registro de estorno estatutário que tem a mesma configuração que o livro fiscal, mas um perfil de lançamentos oposto.</span><span class="sxs-lookup"><span data-stu-id="9087e-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="9087e-438">Por exemplo, o livro fiscal *debitou* uma conta de despesas de arrendamento, mas o livro de estorno *creditará* essa conta.</span><span class="sxs-lookup"><span data-stu-id="9087e-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="9087e-439">Esses relacionamentos são facilmente definidos nas contas de lançamento de arrendamento de ativos na página **Parâmetros de arrendamento de ativos** (**Arrendamento de ativos \> Configuração \> Parâmetros de arrendamento de ativos**).</span><span class="sxs-lookup"><span data-stu-id="9087e-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="9087e-440">Quando o mesmo processo usado para o livro fiscal é usado para o livro de estorno, a entrada de diário a seguir é criada.</span><span class="sxs-lookup"><span data-stu-id="9087e-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="9087e-441">A diferença é que o registro de estorno lista as entradas invertidas do registro fiscal.</span><span class="sxs-lookup"><span data-stu-id="9087e-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="9087e-442">As entradas de estorno também são feitas no nível personalizado.</span><span class="sxs-lookup"><span data-stu-id="9087e-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="9087e-443">Quando um balancete é executado no nível atual, as entradas do diário de estorno não são incluídas.</span><span class="sxs-lookup"><span data-stu-id="9087e-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="9087e-444">Pagamento de arrendamento – 31/1/2020 – JE 130</span><span class="sxs-lookup"><span data-stu-id="9087e-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="9087e-445">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="9087e-445">Account type</span></span> | <span data-ttu-id="9087e-446">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-446">Account number</span></span> | <span data-ttu-id="9087e-447">Camada</span><span class="sxs-lookup"><span data-stu-id="9087e-447">Layer</span></span>  | <span data-ttu-id="9087e-448">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-448">Account description</span></span> | <span data-ttu-id="9087e-449">Débito</span><span class="sxs-lookup"><span data-stu-id="9087e-449">Debit</span></span>    | <span data-ttu-id="9087e-450">Crédito</span><span class="sxs-lookup"><span data-stu-id="9087e-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="9087e-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-451">Ledger</span></span>       | <span data-ttu-id="9087e-452">4</span><span class="sxs-lookup"><span data-stu-id="9087e-452">4</span></span>              | <span data-ttu-id="9087e-453">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-453">Custom</span></span> | <span data-ttu-id="9087e-454">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="9087e-454">Clearing account</span></span>    | <span data-ttu-id="9087e-455">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-455">1,000.00</span></span> |          |
| <span data-ttu-id="9087e-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-456">Ledger</span></span>       | <span data-ttu-id="9087e-457">1</span><span class="sxs-lookup"><span data-stu-id="9087e-457">1</span></span>              | <span data-ttu-id="9087e-458">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-458">Custom</span></span> | <span data-ttu-id="9087e-459">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="9087e-459">Lease expense</span></span>       |          | <span data-ttu-id="9087e-460">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-460">1,000.00</span></span> |

<span data-ttu-id="9087e-461">Agora que você eliminou as entradas fiscais de diário, todas as entradas de diário que o IFRS 16 requer no registro IFRS 16 são registradas.</span><span class="sxs-lookup"><span data-stu-id="9087e-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="9087e-462">Essas entradas incluem o reconhecimento inicial do ativo DDU e a responsabilidade, bem como o registro de juros e depreciação.</span><span class="sxs-lookup"><span data-stu-id="9087e-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="9087e-463">Reconhecimento inicial – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="9087e-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="9087e-464">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="9087e-464">Account type</span></span> | <span data-ttu-id="9087e-465">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-465">Account number</span></span> | <span data-ttu-id="9087e-466">Camada</span><span class="sxs-lookup"><span data-stu-id="9087e-466">Layer</span></span>  | <span data-ttu-id="9087e-467">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-467">Account description</span></span>      | <span data-ttu-id="9087e-468">Débito</span><span class="sxs-lookup"><span data-stu-id="9087e-468">Debit</span></span>     | <span data-ttu-id="9087e-469">Crédito</span><span class="sxs-lookup"><span data-stu-id="9087e-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="9087e-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-470">Ledger</span></span>       | <span data-ttu-id="9087e-471">6</span><span class="sxs-lookup"><span data-stu-id="9087e-471">6</span></span>              | <span data-ttu-id="9087e-472">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-472">Custom</span></span> | <span data-ttu-id="9087e-473">Ativo DDU</span><span class="sxs-lookup"><span data-stu-id="9087e-473">ROU Asset</span></span>                | <span data-ttu-id="9087e-474">22.793,90</span><span class="sxs-lookup"><span data-stu-id="9087e-474">22,793.90</span></span> |           |
| <span data-ttu-id="9087e-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-475">Ledger</span></span>       | <span data-ttu-id="9087e-476">7</span><span class="sxs-lookup"><span data-stu-id="9087e-476">7</span></span>              | <span data-ttu-id="9087e-477">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-477">Custom</span></span> | <span data-ttu-id="9087e-478">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="9087e-478">Finance lease obligation</span></span> |           | <span data-ttu-id="9087e-479">22.793,90</span><span class="sxs-lookup"><span data-stu-id="9087e-479">22,793.90</span></span> |

<span data-ttu-id="9087e-480">O pagamento do arrendamento é lançado como os outros pagamentos de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="9087e-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="9087e-481">O motivo de usar a conta de compensação é garantir que o dinheiro seja creditado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="9087e-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="9087e-482">Pagamento de arrendamento – 31/1/2020 – JE 150</span><span class="sxs-lookup"><span data-stu-id="9087e-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="9087e-483">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="9087e-483">Account type</span></span> | <span data-ttu-id="9087e-484">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-484">Account number</span></span> | <span data-ttu-id="9087e-485">Camada</span><span class="sxs-lookup"><span data-stu-id="9087e-485">Layer</span></span>  | <span data-ttu-id="9087e-486">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-486">Account description</span></span>      | <span data-ttu-id="9087e-487">Débito</span><span class="sxs-lookup"><span data-stu-id="9087e-487">Debit</span></span>    | <span data-ttu-id="9087e-488">Crédito</span><span class="sxs-lookup"><span data-stu-id="9087e-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="9087e-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-489">Ledger</span></span>       | <span data-ttu-id="9087e-490">7</span><span class="sxs-lookup"><span data-stu-id="9087e-490">7</span></span>              | <span data-ttu-id="9087e-491">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-491">Custom</span></span> | <span data-ttu-id="9087e-492">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="9087e-492">Finance lease obligation</span></span> | <span data-ttu-id="9087e-493">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-493">1,000.00</span></span> |          |
| <span data-ttu-id="9087e-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-494">Ledger</span></span>       | <span data-ttu-id="9087e-495">4</span><span class="sxs-lookup"><span data-stu-id="9087e-495">4</span></span>              | <span data-ttu-id="9087e-496">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-496">Custom</span></span> | <span data-ttu-id="9087e-497">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="9087e-497">Clearing account</span></span>         |          | <span data-ttu-id="9087e-498">1.000,00</span><span class="sxs-lookup"><span data-stu-id="9087e-498">1,000.00</span></span> |

<span data-ttu-id="9087e-499">A entrada do diário de despesas de juros é gerada a partir do agendamento de amortização de passivo.</span><span class="sxs-lookup"><span data-stu-id="9087e-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="9087e-500">Despesa de Juros – 31/1/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="9087e-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="9087e-501">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="9087e-501">Account type</span></span> | <span data-ttu-id="9087e-502">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-502">Account number</span></span> | <span data-ttu-id="9087e-503">Camada</span><span class="sxs-lookup"><span data-stu-id="9087e-503">Layer</span></span>  | <span data-ttu-id="9087e-504">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-504">Account description</span></span>      | <span data-ttu-id="9087e-505">Débito</span><span class="sxs-lookup"><span data-stu-id="9087e-505">Debit</span></span> | <span data-ttu-id="9087e-506">Crédito</span><span class="sxs-lookup"><span data-stu-id="9087e-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="9087e-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-507">Ledger</span></span>       | <span data-ttu-id="9087e-508">8</span><span class="sxs-lookup"><span data-stu-id="9087e-508">8</span></span>              | <span data-ttu-id="9087e-509">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-509">Custom</span></span> | <span data-ttu-id="9087e-510">Despesa de Juros</span><span class="sxs-lookup"><span data-stu-id="9087e-510">Interest expense</span></span>         | <span data-ttu-id="9087e-511">94,97</span><span class="sxs-lookup"><span data-stu-id="9087e-511">94.97</span></span> |        |
| <span data-ttu-id="9087e-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-512">Ledger</span></span>       | <span data-ttu-id="9087e-513">7</span><span class="sxs-lookup"><span data-stu-id="9087e-513">7</span></span>              | <span data-ttu-id="9087e-514">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-514">Custom</span></span> | <span data-ttu-id="9087e-515">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="9087e-515">Finance lease obligation</span></span> |       | <span data-ttu-id="9087e-516">94,97</span><span class="sxs-lookup"><span data-stu-id="9087e-516">94.97</span></span>  |

<span data-ttu-id="9087e-517">A entrada do diário de despesas de depreciação é gerada a partir do agendamento de depreciação de ativos.</span><span class="sxs-lookup"><span data-stu-id="9087e-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="9087e-518">Despesa de depreciação – 31/1/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="9087e-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="9087e-519">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="9087e-519">Account type</span></span> | <span data-ttu-id="9087e-520">Número da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-520">Account number</span></span> | <span data-ttu-id="9087e-521">Camada</span><span class="sxs-lookup"><span data-stu-id="9087e-521">Layer</span></span>  | <span data-ttu-id="9087e-522">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="9087e-522">Account description</span></span>      | <span data-ttu-id="9087e-523">Débito</span><span class="sxs-lookup"><span data-stu-id="9087e-523">Debit</span></span>  | <span data-ttu-id="9087e-524">Crédito</span><span class="sxs-lookup"><span data-stu-id="9087e-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="9087e-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-525">Ledger</span></span>       | <span data-ttu-id="9087e-526">10</span><span class="sxs-lookup"><span data-stu-id="9087e-526">10</span></span>             | <span data-ttu-id="9087e-527">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-527">Custom</span></span> | <span data-ttu-id="9087e-528">Despesa de Depreciação</span><span class="sxs-lookup"><span data-stu-id="9087e-528">Depreciation expense</span></span>     | <span data-ttu-id="9087e-529">949,75</span><span class="sxs-lookup"><span data-stu-id="9087e-529">949.75</span></span> |        |
| <span data-ttu-id="9087e-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="9087e-530">Ledger</span></span>       | <span data-ttu-id="9087e-531">11</span><span class="sxs-lookup"><span data-stu-id="9087e-531">11</span></span>             | <span data-ttu-id="9087e-532">Personalizada</span><span class="sxs-lookup"><span data-stu-id="9087e-532">Custom</span></span> | <span data-ttu-id="9087e-533">Depreciação Acumulada</span><span class="sxs-lookup"><span data-stu-id="9087e-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="9087e-534">949,75</span><span class="sxs-lookup"><span data-stu-id="9087e-534">949.75</span></span> |

<span data-ttu-id="9087e-535">Depois que todas essas entradas de diário forem criadas e lançadas, você verá os seguintes valores de "nível 1 personalizado".</span><span class="sxs-lookup"><span data-stu-id="9087e-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="9087e-536">Observe que a última coluna inclui a tarifa bancária, a despesa de imposto sobre valor agregado (IVA) e a redução de pagamento à vista do nível anterior, mas ela não inclui as entradas de diário de relatório estatutário.</span><span class="sxs-lookup"><span data-stu-id="9087e-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="9087e-537">Portanto, você realmente obtém recursos de relatório duplo.</span><span class="sxs-lookup"><span data-stu-id="9087e-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="9087e-538">Neste ponto, a empresa precisa apenas executar seu balancete e combinar o nível atual e o nível personalizado para criar um balancete de IFRS.</span><span class="sxs-lookup"><span data-stu-id="9087e-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="9087e-539">Nº de conta</span><span class="sxs-lookup"><span data-stu-id="9087e-539">Account No</span></span> | <span data-ttu-id="9087e-540">descrição</span><span class="sxs-lookup"><span data-stu-id="9087e-540">Description</span></span>              | <span data-ttu-id="9087e-541">Livro fiscal\-Nível atual\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9087e-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="9087e-542">Livro fiscal\-Nível atual\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9087e-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="9087e-543">Livro fiscal\-Nível atual\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9087e-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="9087e-544">Nível atual \- Totais</span><span class="sxs-lookup"><span data-stu-id="9087e-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="9087e-545">Registro de estorno\-Nível atual\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9087e-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="9087e-546">Registro IFRS 16\-Nível atual\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9087e-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="9087e-547">Registro IFRS 16\-Nível atual\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9087e-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="9087e-548">Registro IFRS 16\-Nível atual\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9087e-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="9087e-549">Registro IFRS 16\-Nível atual\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="9087e-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="9087e-550">Nível personalizado \+ Nível atual \- Totais</span><span class="sxs-lookup"><span data-stu-id="9087e-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="9087e-551">1</span><span class="sxs-lookup"><span data-stu-id="9087e-551">1</span></span>          | <span data-ttu-id="9087e-552">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="9087e-552">Lease expense</span></span>            | <span data-ttu-id="9087e-553">1.000\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="9087e-554">1.000\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-554">1,000\.00</span></span>               |   | <span data-ttu-id="9087e-555">\-1.000</span><span class="sxs-lookup"><span data-stu-id="9087e-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="9087e-556">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-556">0\.00</span></span>                                   |
| <span data-ttu-id="9087e-557">2</span><span class="sxs-lookup"><span data-stu-id="9087e-557">2</span></span>          | <span data-ttu-id="9087e-558">Tarifa bancária</span><span class="sxs-lookup"><span data-stu-id="9087e-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="9087e-559">3\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="9087e-560">3\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="9087e-561">3\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-561">3\.00</span></span>                                   |
| <span data-ttu-id="9087e-562">3</span><span class="sxs-lookup"><span data-stu-id="9087e-562">3</span></span>          | <span data-ttu-id="9087e-563">Despesa de IVA</span><span class="sxs-lookup"><span data-stu-id="9087e-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="9087e-564">5\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="9087e-565">5\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="9087e-566">5\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-566">5\.00</span></span>                                   |
| <span data-ttu-id="9087e-567">4</span><span class="sxs-lookup"><span data-stu-id="9087e-567">4</span></span>          | <span data-ttu-id="9087e-568">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="9087e-568">Clearing account</span></span>         | <span data-ttu-id="9087e-569">\-1.000\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="9087e-570">1.000\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="9087e-571">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-571">0\.00</span></span>                   |   | <span data-ttu-id="9087e-572">1.000</span><span class="sxs-lookup"><span data-stu-id="9087e-572">1,000</span></span>                                           |                                                | <span data-ttu-id="9087e-573">\-1.000</span><span class="sxs-lookup"><span data-stu-id="9087e-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="9087e-574">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-574">0\.00</span></span>                                   |
| <span data-ttu-id="9087e-575">5</span><span class="sxs-lookup"><span data-stu-id="9087e-575">5</span></span>          | <span data-ttu-id="9087e-576">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="9087e-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="9087e-577">\-1.008\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="9087e-578">1.008\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-578">1,008\.00</span></span>                                         | <span data-ttu-id="9087e-579">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="9087e-580">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-580">0\.00</span></span>                                   |
| <span data-ttu-id="9087e-581">6</span><span class="sxs-lookup"><span data-stu-id="9087e-581">6</span></span>          | <span data-ttu-id="9087e-582">Ativo DDU</span><span class="sxs-lookup"><span data-stu-id="9087e-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="9087e-583">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="9087e-584">22.794</span><span class="sxs-lookup"><span data-stu-id="9087e-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="9087e-585">22.793\,90</span><span class="sxs-lookup"><span data-stu-id="9087e-585">22,793\.90</span></span>                              |
| <span data-ttu-id="9087e-586">7</span><span class="sxs-lookup"><span data-stu-id="9087e-586">7</span></span>          | <span data-ttu-id="9087e-587">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="9087e-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="9087e-588">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="9087e-589">\-22.794</span><span class="sxs-lookup"><span data-stu-id="9087e-589">\-22,794</span></span>                                       | <span data-ttu-id="9087e-590">1.000</span><span class="sxs-lookup"><span data-stu-id="9087e-590">1,000</span></span>                                          | <span data-ttu-id="9087e-591">\-94\,97</span><span class="sxs-lookup"><span data-stu-id="9087e-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="9087e-592">\-21.888\,87</span><span class="sxs-lookup"><span data-stu-id="9087e-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="9087e-593">8</span><span class="sxs-lookup"><span data-stu-id="9087e-593">8</span></span>          | <span data-ttu-id="9087e-594">Despesa de Juros</span><span class="sxs-lookup"><span data-stu-id="9087e-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="9087e-595">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="9087e-596">94\,97</span><span class="sxs-lookup"><span data-stu-id="9087e-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="9087e-597">94\,97</span><span class="sxs-lookup"><span data-stu-id="9087e-597">94\.97</span></span>                                  |
| <span data-ttu-id="9087e-598">9</span><span class="sxs-lookup"><span data-stu-id="9087e-598">9</span></span>          | <span data-ttu-id="9087e-599">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="9087e-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="9087e-600">\-1.008\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="9087e-601">\-1.008\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="9087e-602">\-1.008\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="9087e-603">10</span><span class="sxs-lookup"><span data-stu-id="9087e-603">10</span></span>         | <span data-ttu-id="9087e-604">Despesa de Depreciação</span><span class="sxs-lookup"><span data-stu-id="9087e-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="9087e-605">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="9087e-606">949\,75</span><span class="sxs-lookup"><span data-stu-id="9087e-606">949\.75</span></span>                                        | <span data-ttu-id="9087e-607">949\,75</span><span class="sxs-lookup"><span data-stu-id="9087e-607">949\.75</span></span>                                 |
| <span data-ttu-id="9087e-608">11</span><span class="sxs-lookup"><span data-stu-id="9087e-608">11</span></span>         | <span data-ttu-id="9087e-609">Depreciação Acumulada</span><span class="sxs-lookup"><span data-stu-id="9087e-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="9087e-610">0\,00</span><span class="sxs-lookup"><span data-stu-id="9087e-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="9087e-611">\-949\,75</span><span class="sxs-lookup"><span data-stu-id="9087e-611">\-949\.75</span></span>                                      | <span data-ttu-id="9087e-612">\-949\,75</span><span class="sxs-lookup"><span data-stu-id="9087e-612">\-949\.75</span></span>                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
