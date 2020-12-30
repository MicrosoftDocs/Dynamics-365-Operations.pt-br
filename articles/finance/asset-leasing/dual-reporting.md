---
title: Relatórios duplos
description: Este tópico apresenta um exemplo que mostra como você pode cumprir os requisitos de relatório do Financial Reporting Standard (IFRS) e relatórios estatutários em arrendamento de ativos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 96e1d4d460aef2f74422d5e4bd4fc68255466455
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440537"
---
# <a name="dual-reporting"></a><span data-ttu-id="c0bd8-103">Relatórios duplos</span><span class="sxs-lookup"><span data-stu-id="c0bd8-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0bd8-104">Este tópico apresenta um exemplo que mostra como você pode cumprir os requisitos de relatório do Financial Reporting Standard (IFRS) e relatórios estatutários em arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="c0bd8-105">A familiaridade com lançamentos de camadas no Microsoft Dynamics 365 Finance é necessária e facilitará o entendimento do exemplo.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="c0bd8-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-106">Example</span></span>

<span data-ttu-id="c0bd8-107">O exemplo a seguir conta um arrendamento no relatório estatutário italiano usando o método de base de caixa e o modo de relatório do IFRS.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="c0bd8-108">A empresa deve estabelecer três registros para cumprir os requisitos legais da Itália e os requisitos do IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="c0bd8-109">Um registro é necessário para o IFRS 16, outro é necessário para os requisitos estatutários e outro é necessário para reverter automaticamente lançamentos estatutários.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="c0bd8-110">Os registros são configurados conforme mostrado nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="c0bd8-111">**Registro IFRS 16**</span><span class="sxs-lookup"><span data-stu-id="c0bd8-111">**IFRS 16 book**</span></span>

<span data-ttu-id="c0bd8-112">O livro IFRS 16 é configurado de forma que ele cumpra com o padrão de contabilidade IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="c0bd8-113">Todas as entradas lançadas neste manual serão lançadas em uma camada personalizada.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="c0bd8-114">Organização</span><span class="sxs-lookup"><span data-stu-id="c0bd8-114">Name</span></span>                                    | <span data-ttu-id="c0bd8-115">descrição</span><span class="sxs-lookup"><span data-stu-id="c0bd8-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="c0bd8-116">Tipo de livro</span><span class="sxs-lookup"><span data-stu-id="c0bd8-116">Book type</span></span>                               | <span data-ttu-id="c0bd8-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="c0bd8-117">IFRS 16</span></span>        |
| <span data-ttu-id="c0bd8-118">Descrição do registro</span><span class="sxs-lookup"><span data-stu-id="c0bd8-118">Book description</span></span>                        | <span data-ttu-id="c0bd8-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="c0bd8-119">IFRS 16</span></span>        |
| <span data-ttu-id="c0bd8-120">Nível de Lançamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-120">Posting Layer</span></span>                           | <span data-ttu-id="c0bd8-121">Camada personalizada 1</span><span class="sxs-lookup"><span data-stu-id="c0bd8-121">Custom layer 1</span></span> |
| <span data-ttu-id="c0bd8-122">Tipo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-122">Lease Type</span></span>                              | <span data-ttu-id="c0bd8-123">Finance</span><span class="sxs-lookup"><span data-stu-id="c0bd8-123">Finance</span></span>        |
| <span data-ttu-id="c0bd8-124">Estrutura contábil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-124">Accounting Framework</span></span>                    | <span data-ttu-id="c0bd8-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="c0bd8-125">IFRS 16</span></span>        |
| <span data-ttu-id="c0bd8-126">Configuração de prazo do arrendamento / vida útil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="c0bd8-127">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-127">0.00</span></span>           |
| <span data-ttu-id="c0bd8-128">Configuração de valor presente / valor justo do ativo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="c0bd8-129">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-129">0.00</span></span>           |
| <span data-ttu-id="c0bd8-130">Limite de curto prazo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-130">Short-term threshold</span></span>                    | <span data-ttu-id="c0bd8-131">12</span><span class="sxs-lookup"><span data-stu-id="c0bd8-131">12</span></span>             |
| <span data-ttu-id="c0bd8-132">Limite de valor baixo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-132">Low Value Threshold</span></span>                     | <span data-ttu-id="c0bd8-133">5.000,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-133">5,000.00</span></span>       |
| <span data-ttu-id="c0bd8-134">Pagar ao fornecedor</span><span class="sxs-lookup"><span data-stu-id="c0bd8-134">Pay to Vendor</span></span>                           | <span data-ttu-id="c0bd8-135">Não</span><span class="sxs-lookup"><span data-stu-id="c0bd8-135">No</span></span>             |

<span data-ttu-id="c0bd8-136">**Livro fiscal**</span><span class="sxs-lookup"><span data-stu-id="c0bd8-136">**Statutory book**</span></span>

<span data-ttu-id="c0bd8-137">O livro fiscal é um registro de base de caixa em que a empresa contará com as despesas de arrendamento como o valor de pagamento à vista pago mensalmente por aluguel.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="c0bd8-138">Esse registro não produzirá um ativo de direito de uso (ROU) ou uma responsabilidade de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="c0bd8-139">Organização</span><span class="sxs-lookup"><span data-stu-id="c0bd8-139">Name</span></span>                                    | <span data-ttu-id="c0bd8-140">descrição</span><span class="sxs-lookup"><span data-stu-id="c0bd8-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="c0bd8-141">Tipo de livro</span><span class="sxs-lookup"><span data-stu-id="c0bd8-141">Book type</span></span>                               | <span data-ttu-id="c0bd8-142">Fiscal</span><span class="sxs-lookup"><span data-stu-id="c0bd8-142">Statutory</span></span>   |
| <span data-ttu-id="c0bd8-143">Descrição do registro</span><span class="sxs-lookup"><span data-stu-id="c0bd8-143">Book description</span></span>                        | <span data-ttu-id="c0bd8-144">GAAP Local</span><span class="sxs-lookup"><span data-stu-id="c0bd8-144">Local GAAP</span></span>  |
| <span data-ttu-id="c0bd8-145">Nível de Lançamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-145">Posting Layer</span></span>                           | <span data-ttu-id="c0bd8-146">Atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-146">Current</span></span>     |
| <span data-ttu-id="c0bd8-147">Tipo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-147">Lease Type</span></span>                              | <span data-ttu-id="c0bd8-148">Automática</span><span class="sxs-lookup"><span data-stu-id="c0bd8-148">Automatic</span></span>   |
| <span data-ttu-id="c0bd8-149">Estrutura contábil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-149">Accounting Framework</span></span>                    | <span data-ttu-id="c0bd8-150">Base de pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="c0bd8-150">Cash basis</span></span>  |
| <span data-ttu-id="c0bd8-151">Configuração de prazo do arrendamento / vida útil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="c0bd8-152">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-152">0.00</span></span>        |
| <span data-ttu-id="c0bd8-153">Configuração de valor presente / valor justo do ativo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="c0bd8-154">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-154">0.00</span></span>        |
| <span data-ttu-id="c0bd8-155">Limite de curto prazo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-155">Short-term threshold</span></span>                    | <span data-ttu-id="c0bd8-156">0</span><span class="sxs-lookup"><span data-stu-id="c0bd8-156">0</span></span>           |
| <span data-ttu-id="c0bd8-157">Limite de valor baixo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-157">Low Value Threshold</span></span>                     | <span data-ttu-id="c0bd8-158">0</span><span class="sxs-lookup"><span data-stu-id="c0bd8-158">0</span></span>           |
| <span data-ttu-id="c0bd8-159">Pagar ao fornecedor</span><span class="sxs-lookup"><span data-stu-id="c0bd8-159">Pay to Vendor</span></span>                           | <span data-ttu-id="c0bd8-160">Não</span><span class="sxs-lookup"><span data-stu-id="c0bd8-160">No</span></span>          |

<span data-ttu-id="c0bd8-161">**Livro de estorno fiscal**</span><span class="sxs-lookup"><span data-stu-id="c0bd8-161">**Statutory reversal book**</span></span>

<span data-ttu-id="c0bd8-162">O livro de estorno fiscal é configurado da mesma forma que o livro fiscal.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="c0bd8-163">Organização</span><span class="sxs-lookup"><span data-stu-id="c0bd8-163">Name</span></span>                                    | <span data-ttu-id="c0bd8-164">descrição</span><span class="sxs-lookup"><span data-stu-id="c0bd8-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="c0bd8-165">Tipo de livro</span><span class="sxs-lookup"><span data-stu-id="c0bd8-165">Book type</span></span>                               | <span data-ttu-id="c0bd8-166">Fiscal - Estorno</span><span class="sxs-lookup"><span data-stu-id="c0bd8-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="c0bd8-167">Descrição do registro</span><span class="sxs-lookup"><span data-stu-id="c0bd8-167">Book description</span></span>                        | <span data-ttu-id="c0bd8-168">Registro para reverter o livro fiscal</span><span class="sxs-lookup"><span data-stu-id="c0bd8-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="c0bd8-169">Nível de Lançamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-169">Posting Layer</span></span>                           | <span data-ttu-id="c0bd8-170">Camada personalizada 1</span><span class="sxs-lookup"><span data-stu-id="c0bd8-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="c0bd8-171">Tipo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-171">Lease Type</span></span>                              | <span data-ttu-id="c0bd8-172">Automática</span><span class="sxs-lookup"><span data-stu-id="c0bd8-172">Automatic</span></span>                      |
| <span data-ttu-id="c0bd8-173">Estrutura contábil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-173">Accounting Framework</span></span>                    | <span data-ttu-id="c0bd8-174">Base de pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="c0bd8-174">Cash basis</span></span>                     |
| <span data-ttu-id="c0bd8-175">Configuração de prazo do arrendamento / vida útil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="c0bd8-176">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-176">0.00</span></span>                           |
| <span data-ttu-id="c0bd8-177">Configuração de valor presente / valor justo do ativo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="c0bd8-178">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-178">0.00</span></span>                           |
| <span data-ttu-id="c0bd8-179">Limite de curto prazo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-179">Short-term threshold</span></span>                    | <span data-ttu-id="c0bd8-180">0</span><span class="sxs-lookup"><span data-stu-id="c0bd8-180">0</span></span>                              |
| <span data-ttu-id="c0bd8-181">Limite de valor baixo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-181">Low Value Threshold</span></span>                     | <span data-ttu-id="c0bd8-182">0</span><span class="sxs-lookup"><span data-stu-id="c0bd8-182">0</span></span>                              |
| <span data-ttu-id="c0bd8-183">Pagar ao fornecedor</span><span class="sxs-lookup"><span data-stu-id="c0bd8-183">Pay to Vendor</span></span>                           | <span data-ttu-id="c0bd8-184">Não</span><span class="sxs-lookup"><span data-stu-id="c0bd8-184">No</span></span>                             |

<span data-ttu-id="c0bd8-185">Neste exemplo, um arrendamento foi criado com as seguintes configurações nas guias **Geral** **Linhas de agendamento de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="c0bd8-186">**Guia Geral**</span><span class="sxs-lookup"><span data-stu-id="c0bd8-186">**General tab**</span></span>

| <span data-ttu-id="c0bd8-187">Campo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-187">Field</span></span>                      | <span data-ttu-id="c0bd8-188">Alíquota</span><span class="sxs-lookup"><span data-stu-id="c0bd8-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="c0bd8-189">Taxa incremental de empréstimo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-189">Incremental borrowing rate</span></span> | <span data-ttu-id="c0bd8-190">5%</span><span class="sxs-lookup"><span data-stu-id="c0bd8-190">5%</span></span>               |
| <span data-ttu-id="c0bd8-191">Data de início</span><span class="sxs-lookup"><span data-stu-id="c0bd8-191">Commencement date</span></span>          | <span data-ttu-id="c0bd8-192">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="c0bd8-192">1/1/2020</span></span>         |
| <span data-ttu-id="c0bd8-193">Grupo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-193">Lease group</span></span>                | <span data-ttu-id="c0bd8-194">Instalações</span><span class="sxs-lookup"><span data-stu-id="c0bd8-194">Buildings</span></span>        |
| <span data-ttu-id="c0bd8-195">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="c0bd8-195">Vendor</span></span>                     | <span data-ttu-id="c0bd8-196">1001</span><span class="sxs-lookup"><span data-stu-id="c0bd8-196">1001</span></span>             |
| <span data-ttu-id="c0bd8-197">Valor justo do ativo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-197">Fair value of the asset</span></span>    | <span data-ttu-id="c0bd8-198">245,000</span><span class="sxs-lookup"><span data-stu-id="c0bd8-198">245,000</span></span>          |
| <span data-ttu-id="c0bd8-199">Vida útil do ativo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-199">Asset useful life</span></span>          | <span data-ttu-id="c0bd8-200">120</span><span class="sxs-lookup"><span data-stu-id="c0bd8-200">120</span></span>              |
| <span data-ttu-id="c0bd8-201">Tipo de anuidade</span><span class="sxs-lookup"><span data-stu-id="c0bd8-201">Annuity type</span></span>               | <span data-ttu-id="c0bd8-202">Anuidade comum</span><span class="sxs-lookup"><span data-stu-id="c0bd8-202">Ordinary annuity</span></span> |
| <span data-ttu-id="c0bd8-203">Intervalo de composição</span><span class="sxs-lookup"><span data-stu-id="c0bd8-203">Compounding interval</span></span>       | <span data-ttu-id="c0bd8-204">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="c0bd8-204">Monthly</span></span>          |

<span data-ttu-id="c0bd8-205">**Guia Linhas de agenda de pagamento**</span><span class="sxs-lookup"><span data-stu-id="c0bd8-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="c0bd8-206">Campo</span><span class="sxs-lookup"><span data-stu-id="c0bd8-206">Field</span></span>             | <span data-ttu-id="c0bd8-207">Alíquota</span><span class="sxs-lookup"><span data-stu-id="c0bd8-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="c0bd8-208">Data inicial</span><span class="sxs-lookup"><span data-stu-id="c0bd8-208">Start date</span></span>        | <span data-ttu-id="c0bd8-209">1/1/2020</span><span class="sxs-lookup"><span data-stu-id="c0bd8-209">1/1/2020</span></span>   |
| <span data-ttu-id="c0bd8-210">Intervalo do período</span><span class="sxs-lookup"><span data-stu-id="c0bd8-210">Period interval</span></span>   | <span data-ttu-id="c0bd8-211">Meses</span><span class="sxs-lookup"><span data-stu-id="c0bd8-211">Months</span></span>     |
| <span data-ttu-id="c0bd8-212">Períodos</span><span class="sxs-lookup"><span data-stu-id="c0bd8-212">Periods</span></span>           | <span data-ttu-id="c0bd8-213">24</span><span class="sxs-lookup"><span data-stu-id="c0bd8-213">24</span></span>         |
| <span data-ttu-id="c0bd8-214">Data de término</span><span class="sxs-lookup"><span data-stu-id="c0bd8-214">End date</span></span>          | <span data-ttu-id="c0bd8-215">31/12/2020</span><span class="sxs-lookup"><span data-stu-id="c0bd8-215">12/31/2020</span></span> |
| <span data-ttu-id="c0bd8-216">Frequência de pagamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-216">Payment frequency</span></span> | <span data-ttu-id="c0bd8-217">Mensalmente</span><span class="sxs-lookup"><span data-stu-id="c0bd8-217">Monthly</span></span>    |
| <span data-ttu-id="c0bd8-218">Valor do pagamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-218">Payment amount</span></span>    | <span data-ttu-id="c0bd8-219">1.000</span><span class="sxs-lookup"><span data-stu-id="c0bd8-219">1,000</span></span>      |

<span data-ttu-id="c0bd8-220">Para considerar esse arrendamento em duas estruturas, use um nível de lançamento atual e um nível de lançamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="c0bd8-221">A tabela a seguir mostra um exemplo de cada entrada de diário que represente razoavelmente as finanças sob cada padrão de relatório.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="c0bd8-222">Posteriormente, é fornecida uma descrição detalhada de cada entrada de diário para o primeiro mês do arrendamento.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="c0bd8-223">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="c0bd8-224">descrição</span><span class="sxs-lookup"><span data-stu-id="c0bd8-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="c0bd8-225">Livro fiscal (nível atual)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="c0bd8-226">Total do nível atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-226">Current layer total</span></span></th>
<th><span data-ttu-id="c0bd8-227">Registro de estorno (nível personalizado)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="c0bd8-228">Registro IFRS 16 (nível personalizado)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="c0bd8-229">Nível atual + total do nível personalizado</span><span class="sxs-lookup"><span data-stu-id="c0bd8-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c0bd8-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="c0bd8-230">JE-100</span></span></th>
<th><span data-ttu-id="c0bd8-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="c0bd8-231">JE-110</span></span></th>
<th><span data-ttu-id="c0bd8-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="c0bd8-232">JE-120</span></span></th>
<th><span data-ttu-id="c0bd8-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="c0bd8-233">JE-130</span></span></th>
<th><span data-ttu-id="c0bd8-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="c0bd8-234">JE-140</span></span></th>
<th><span data-ttu-id="c0bd8-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="c0bd8-235">JE-150</span></span></th>
<th><span data-ttu-id="c0bd8-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="c0bd8-236">JE-160</span></span></th>
<th><span data-ttu-id="c0bd8-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="c0bd8-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c0bd8-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="c0bd8-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="c0bd8-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="c0bd8-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="c0bd8-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="c0bd8-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="c0bd8-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="c0bd8-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0bd8-246">1</span><span class="sxs-lookup"><span data-stu-id="c0bd8-246">1</span></span></td>
<td><span data-ttu-id="c0bd8-247">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-247">Lease expense</span></span></td>
<td><span data-ttu-id="c0bd8-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-249">1,000.00</span></span></td>
<td><span data-ttu-id="c0bd8-250">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-251">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-252">2</span><span class="sxs-lookup"><span data-stu-id="c0bd8-252">2</span></span></td>
<td><span data-ttu-id="c0bd8-253">Tarifa bancária</span><span class="sxs-lookup"><span data-stu-id="c0bd8-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-254">3.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-255">3.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-256">3.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-257">3</span><span class="sxs-lookup"><span data-stu-id="c0bd8-257">3</span></span></td>
<td><span data-ttu-id="c0bd8-258">Despesa IVA</span><span class="sxs-lookup"><span data-stu-id="c0bd8-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-259">5.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-260">5.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-261">5.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-262">4</span><span class="sxs-lookup"><span data-stu-id="c0bd8-262">4</span></span></td>
<td><span data-ttu-id="c0bd8-263">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-263">Clearing account</span></span></td>
<td><span data-ttu-id="c0bd8-264">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-264">-1,000.00</span></span></td>
<td><span data-ttu-id="c0bd8-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-266">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-266">0.00</span></span></td>
<td><span data-ttu-id="c0bd8-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-268">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-269">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-270">5</span><span class="sxs-lookup"><span data-stu-id="c0bd8-270">5</span></span></td>
<td><span data-ttu-id="c0bd8-271">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="c0bd8-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-272">-1,008.00</span></span></td>
<td><span data-ttu-id="c0bd8-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-273">1,008.00</span></span></td>
<td><span data-ttu-id="c0bd8-274">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-275">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-276">6</span><span class="sxs-lookup"><span data-stu-id="c0bd8-276">6</span></span></td>
<td><span data-ttu-id="c0bd8-277">Ativo de ROU</span><span class="sxs-lookup"><span data-stu-id="c0bd8-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-278">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="c0bd8-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-281">7</span><span class="sxs-lookup"><span data-stu-id="c0bd8-281">7</span></span></td>
<td><span data-ttu-id="c0bd8-282">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-283">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-284">-22,794.00</span></span></td>
<td><span data-ttu-id="c0bd8-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-285">1,000.00</span></span></td>
<td><span data-ttu-id="c0bd8-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="c0bd8-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="c0bd8-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-288">8</span><span class="sxs-lookup"><span data-stu-id="c0bd8-288">8</span></span></td>
<td><span data-ttu-id="c0bd8-289">Despesa de Juros</span><span class="sxs-lookup"><span data-stu-id="c0bd8-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-290">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-291">94.97</span><span class="sxs-lookup"><span data-stu-id="c0bd8-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-292">94.97</span><span class="sxs-lookup"><span data-stu-id="c0bd8-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-293">9</span><span class="sxs-lookup"><span data-stu-id="c0bd8-293">9</span></span></td>
<td><span data-ttu-id="c0bd8-294">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="c0bd8-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-295">-1,008.00</span></span></td>
<td><span data-ttu-id="c0bd8-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-298">10</span><span class="sxs-lookup"><span data-stu-id="c0bd8-298">10</span></span></td>
<td><span data-ttu-id="c0bd8-299">Despesa de Depreciação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-300">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-301">949,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-301">949.75</span></span></td>
<td><span data-ttu-id="c0bd8-302">949,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-303">11</span><span class="sxs-lookup"><span data-stu-id="c0bd8-303">11</span></span></td>
<td><span data-ttu-id="c0bd8-304">Depreciação Acumulada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-305">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-306">-949.75</span></span></td>
<td><span data-ttu-id="c0bd8-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0bd8-308">Como mostra a tabela acima, é necessário reportar três registros em relatórios fiscais e em relatórios IFRS.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="c0bd8-309">O livro fiscal registra o pagamento do arrendamento de acordo com as regras para a contabilidade de base de caixa no nível atual.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="c0bd8-310">O registro de estorno fiscal inverte as entradas do diário fiscal.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="c0bd8-311">O registro IFRS 16 cria as entradas de diário requeridas pelo IFRS 16.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="c0bd8-312">É necessário inserir um arrendamento somente uma vez.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-312">You must enter a lease only one time.</span></span> <span data-ttu-id="c0bd8-313">Em seguida, você poderá abrir a página **Registros** para ver todos os registros associados ao arrendamento.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="c0bd8-314">Quando você cria os registros, todos os três devem ser associados ao mesmo registro de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="c0bd8-315">A primeira entrada de diário registra a despesa de arrendamento mediante o livro fiscal.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="c0bd8-316">Você pode criar os pagamentos em um lote ou selecionando o plano de pagamento no livro fiscal.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="c0bd8-317">Neste exemplo, a entrada de diário a seguir é criada para o livro fiscal no plano de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="c0bd8-318">Pagamento de arrendamento – 31/1/2020 – JE 100</span><span class="sxs-lookup"><span data-stu-id="c0bd8-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="c0bd8-319">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-319">Account type</span></span> | <span data-ttu-id="c0bd8-320">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-320">Account number</span></span> | <span data-ttu-id="c0bd8-321">Camada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-321">Layer</span></span>   | <span data-ttu-id="c0bd8-322">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-322">Account description</span></span> | <span data-ttu-id="c0bd8-323">Débito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-323">Debit</span></span>    | <span data-ttu-id="c0bd8-324">Crédito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="c0bd8-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-325">Ledger</span></span>       | <span data-ttu-id="c0bd8-326">1</span><span class="sxs-lookup"><span data-stu-id="c0bd8-326">1</span></span>              | <span data-ttu-id="c0bd8-327">Atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-327">Current</span></span> | <span data-ttu-id="c0bd8-328">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-328">Lease expense</span></span>       | <span data-ttu-id="c0bd8-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-329">1,000.00</span></span> |          |
| <span data-ttu-id="c0bd8-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-330">Ledger</span></span>       | <span data-ttu-id="c0bd8-331">4</span><span class="sxs-lookup"><span data-stu-id="c0bd8-331">4</span></span>              | <span data-ttu-id="c0bd8-332">Atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-332">Current</span></span> | <span data-ttu-id="c0bd8-333">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-333">Clearing account</span></span>    |          | <span data-ttu-id="c0bd8-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-334">1,000.00</span></span> |

<span data-ttu-id="c0bd8-335">Um auxiliar de contas a pagar usa a funcionalidade padrão do Dynamics 365 para criar uma fatura a pagar para o arrendamento fora do Arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="c0bd8-336">No entanto, em vez de selecionar **Despesa de arrendamento** como a conta de débito, o auxiliar de contas a pagar seleciona uma conta de compensação para gerar a entrada a seguir.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="c0bd8-337">Processo de AP - 31/1/2020 – JE 110</span><span class="sxs-lookup"><span data-stu-id="c0bd8-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="c0bd8-338">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-338">Account type</span></span> | <span data-ttu-id="c0bd8-339">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-339">Account number</span></span> | <span data-ttu-id="c0bd8-340">Camada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-340">Layer</span></span>   | <span data-ttu-id="c0bd8-341">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-341">Account description</span></span> | <span data-ttu-id="c0bd8-342">Débito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-342">Debit</span></span>    | <span data-ttu-id="c0bd8-343">Crédito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="c0bd8-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-344">Ledger</span></span>       | <span data-ttu-id="c0bd8-345">4</span><span class="sxs-lookup"><span data-stu-id="c0bd8-345">4</span></span>              | <span data-ttu-id="c0bd8-346">Atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-346">Current</span></span> | <span data-ttu-id="c0bd8-347">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-347">Clearing account</span></span>    | <span data-ttu-id="c0bd8-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-348">1,000.00</span></span> |          |
| <span data-ttu-id="c0bd8-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-349">Ledger</span></span>       | <span data-ttu-id="c0bd8-350">2</span><span class="sxs-lookup"><span data-stu-id="c0bd8-350">2</span></span>              | <span data-ttu-id="c0bd8-351">Atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-351">Current</span></span> | <span data-ttu-id="c0bd8-352">Tarifa bancária</span><span class="sxs-lookup"><span data-stu-id="c0bd8-352">Bank fee</span></span>            | <span data-ttu-id="c0bd8-353">3.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-353">3.00</span></span>     |          |
| <span data-ttu-id="c0bd8-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-354">Ledger</span></span>       | <span data-ttu-id="c0bd8-355">3</span><span class="sxs-lookup"><span data-stu-id="c0bd8-355">3</span></span>              | <span data-ttu-id="c0bd8-356">Atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-356">Current</span></span> | <span data-ttu-id="c0bd8-357">Despesa IVA</span><span class="sxs-lookup"><span data-stu-id="c0bd8-357">VAT expense</span></span>         | <span data-ttu-id="c0bd8-358">5.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-358">5.00</span></span>     |          |
| <span data-ttu-id="c0bd8-359">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="c0bd8-359">Vendor</span></span>       | <span data-ttu-id="c0bd8-360">5</span><span class="sxs-lookup"><span data-stu-id="c0bd8-360">5</span></span>              | <span data-ttu-id="c0bd8-361">Atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-361">Current</span></span> | <span data-ttu-id="c0bd8-362">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="c0bd8-362">Accounts payable</span></span>    |          | <span data-ttu-id="c0bd8-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-363">1,008.00</span></span> |

<span data-ttu-id="c0bd8-364">Quando a instrução for emitida para o fornecedor, você seguirá o processo de pagamento regular.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="c0bd8-365">Durante esse processo, a entrada de diário a seguir é gerada.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="c0bd8-366">Pagamento à vista – 31/1/2020 – JE 120</span><span class="sxs-lookup"><span data-stu-id="c0bd8-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="c0bd8-367">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-367">Account type</span></span> | <span data-ttu-id="c0bd8-368">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-368">Account number</span></span> | <span data-ttu-id="c0bd8-369">Camada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-369">Layer</span></span>   | <span data-ttu-id="c0bd8-370">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-370">Account description</span></span> | <span data-ttu-id="c0bd8-371">Débito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-371">Debit</span></span>    | <span data-ttu-id="c0bd8-372">Crédito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="c0bd8-373">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="c0bd8-373">Vendor</span></span>       | <span data-ttu-id="c0bd8-374">5</span><span class="sxs-lookup"><span data-stu-id="c0bd8-374">5</span></span>              | <span data-ttu-id="c0bd8-375">Atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-375">Current</span></span> | <span data-ttu-id="c0bd8-376">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="c0bd8-376">Accounts Payable</span></span>    | <span data-ttu-id="c0bd8-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-377">1,008.00</span></span> |          |
| <span data-ttu-id="c0bd8-378">Banco</span><span class="sxs-lookup"><span data-stu-id="c0bd8-378">Bank</span></span>         | <span data-ttu-id="c0bd8-379">9</span><span class="sxs-lookup"><span data-stu-id="c0bd8-379">9</span></span>              | <span data-ttu-id="c0bd8-380">Atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-380">Current</span></span> | <span data-ttu-id="c0bd8-381">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="c0bd8-381">Cash</span></span>                |          | <span data-ttu-id="c0bd8-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-382">1,008.00</span></span> |

<span data-ttu-id="c0bd8-383">Nessa situação, você cumpriu a conformidade total desse arrendamento mediante os requisitos de relatórios estatutários e pode gerar um balancete usando o nível atual.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="c0bd8-384">O sistema retorna um balancete que tem os seguintes números.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="c0bd8-385">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="c0bd8-386">descrição</span><span class="sxs-lookup"><span data-stu-id="c0bd8-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="c0bd8-387">Livro fiscal (nível atual)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="c0bd8-388">Total do nível atual</span><span class="sxs-lookup"><span data-stu-id="c0bd8-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c0bd8-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="c0bd8-389">JE-100</span></span></th>
<th><span data-ttu-id="c0bd8-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="c0bd8-390">JE-110</span></span></th>
<th><span data-ttu-id="c0bd8-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="c0bd8-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c0bd8-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="c0bd8-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="c0bd8-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0bd8-395">1</span><span class="sxs-lookup"><span data-stu-id="c0bd8-395">1</span></span></td>
<td><span data-ttu-id="c0bd8-396">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-396">Lease expense</span></span></td>
<td><span data-ttu-id="c0bd8-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-399">2</span><span class="sxs-lookup"><span data-stu-id="c0bd8-399">2</span></span></td>
<td><span data-ttu-id="c0bd8-400">Tarifa bancária</span><span class="sxs-lookup"><span data-stu-id="c0bd8-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-401">3.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-402">3.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-403">3</span><span class="sxs-lookup"><span data-stu-id="c0bd8-403">3</span></span></td>
<td><span data-ttu-id="c0bd8-404">Despesa IVA</span><span class="sxs-lookup"><span data-stu-id="c0bd8-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-405">5.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-406">5.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-407">4</span><span class="sxs-lookup"><span data-stu-id="c0bd8-407">4</span></span></td>
<td><span data-ttu-id="c0bd8-408">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-408">Clearing account</span></span></td>
<td><span data-ttu-id="c0bd8-409">-1.000,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-409">-1,000.00</span></span></td>
<td><span data-ttu-id="c0bd8-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-411">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-412">5</span><span class="sxs-lookup"><span data-stu-id="c0bd8-412">5</span></span></td>
<td><span data-ttu-id="c0bd8-413">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="c0bd8-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="c0bd8-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-414">-1,008.00</span></span></td>
<td><span data-ttu-id="c0bd8-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-415">1,008.00</span></span></td>
<td><span data-ttu-id="c0bd8-416">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-417">6</span><span class="sxs-lookup"><span data-stu-id="c0bd8-417">6</span></span></td>
<td><span data-ttu-id="c0bd8-418">Ativo de ROU</span><span class="sxs-lookup"><span data-stu-id="c0bd8-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-419">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-420">7</span><span class="sxs-lookup"><span data-stu-id="c0bd8-420">7</span></span></td>
<td><span data-ttu-id="c0bd8-421">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-422">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-423">8</span><span class="sxs-lookup"><span data-stu-id="c0bd8-423">8</span></span></td>
<td><span data-ttu-id="c0bd8-424">Despesa de Juros</span><span class="sxs-lookup"><span data-stu-id="c0bd8-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-425">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-426">9</span><span class="sxs-lookup"><span data-stu-id="c0bd8-426">9</span></span></td>
<td><span data-ttu-id="c0bd8-427">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="c0bd8-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-428">-1,008.00</span></span></td>
<td><span data-ttu-id="c0bd8-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-430">10</span><span class="sxs-lookup"><span data-stu-id="c0bd8-430">10</span></span></td>
<td><span data-ttu-id="c0bd8-431">Despesa de Depreciação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-432">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0bd8-433">11</span><span class="sxs-lookup"><span data-stu-id="c0bd8-433">11</span></span></td>
<td><span data-ttu-id="c0bd8-434">Depreciação Acumulada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="c0bd8-435">0,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0bd8-436">Se você quiser usar os números do IFRS 16 para executar o mesmo balancete, as entradas do diário contábil fiscal devem ser revertidas, e as entradas de diário de IFRS 16 devem ser lançadas.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="c0bd8-437">Para reverter as entradas de diário estatutário, este exemplo inclui um registro de estorno estatutário que tem a mesma configuração que o livro fiscal, mas um perfil de lançamentos oposto.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="c0bd8-438">Por exemplo, o livro fiscal *debitou* uma conta de despesas de arrendamento, mas o livro de estorno *creditará* essa conta.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="c0bd8-439">Esses relacionamentos são facilmente definidos nas contas de lançamento de arrendamento de ativos na página **Parâmetros de arrendamento de ativos** (**Arrendamento de ativos \> Configuração \> Parâmetros de arrendamento de ativos**).</span><span class="sxs-lookup"><span data-stu-id="c0bd8-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="c0bd8-440">Quando o mesmo processo usado para o livro fiscal é usado para o livro de estorno, a entrada de diário a seguir é criada.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="c0bd8-441">A diferença é que o registro de estorno lista as entradas invertidas do registro fiscal.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="c0bd8-442">As entradas de estorno também são feitas no nível personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="c0bd8-443">Quando um balancete é executado no nível atual, as entradas do diário de estorno não são incluídas.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="c0bd8-444">Pagamento de arrendamento – 31/1/2020 – JE 130</span><span class="sxs-lookup"><span data-stu-id="c0bd8-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="c0bd8-445">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-445">Account type</span></span> | <span data-ttu-id="c0bd8-446">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-446">Account number</span></span> | <span data-ttu-id="c0bd8-447">Camada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-447">Layer</span></span>  | <span data-ttu-id="c0bd8-448">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-448">Account description</span></span> | <span data-ttu-id="c0bd8-449">Débito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-449">Debit</span></span>    | <span data-ttu-id="c0bd8-450">Crédito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="c0bd8-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-451">Ledger</span></span>       | <span data-ttu-id="c0bd8-452">4</span><span class="sxs-lookup"><span data-stu-id="c0bd8-452">4</span></span>              | <span data-ttu-id="c0bd8-453">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-453">Custom</span></span> | <span data-ttu-id="c0bd8-454">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-454">Clearing account</span></span>    | <span data-ttu-id="c0bd8-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-455">1,000.00</span></span> |          |
| <span data-ttu-id="c0bd8-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-456">Ledger</span></span>       | <span data-ttu-id="c0bd8-457">1</span><span class="sxs-lookup"><span data-stu-id="c0bd8-457">1</span></span>              | <span data-ttu-id="c0bd8-458">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-458">Custom</span></span> | <span data-ttu-id="c0bd8-459">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-459">Lease expense</span></span>       |          | <span data-ttu-id="c0bd8-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-460">1,000.00</span></span> |

<span data-ttu-id="c0bd8-461">Agora que você eliminou as entradas fiscais de diário, todas as entradas de diário que o IFRS 16 requer no registro IFRS 16 são registradas.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="c0bd8-462">Essas entradas incluem o reconhecimento inicial do ativo DDU e a responsabilidade, bem como o registro de juros e depreciação.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="c0bd8-463">Reconhecimento inicial – 1/1/2020 – JE 140</span><span class="sxs-lookup"><span data-stu-id="c0bd8-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="c0bd8-464">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-464">Account type</span></span> | <span data-ttu-id="c0bd8-465">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-465">Account number</span></span> | <span data-ttu-id="c0bd8-466">Camada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-466">Layer</span></span>  | <span data-ttu-id="c0bd8-467">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-467">Account description</span></span>      | <span data-ttu-id="c0bd8-468">Débito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-468">Debit</span></span>     | <span data-ttu-id="c0bd8-469">Crédito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="c0bd8-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-470">Ledger</span></span>       | <span data-ttu-id="c0bd8-471">6</span><span class="sxs-lookup"><span data-stu-id="c0bd8-471">6</span></span>              | <span data-ttu-id="c0bd8-472">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-472">Custom</span></span> | <span data-ttu-id="c0bd8-473">Ativo DDU</span><span class="sxs-lookup"><span data-stu-id="c0bd8-473">ROU Asset</span></span>                | <span data-ttu-id="c0bd8-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="c0bd8-474">22,793.90</span></span> |           |
| <span data-ttu-id="c0bd8-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-475">Ledger</span></span>       | <span data-ttu-id="c0bd8-476">7</span><span class="sxs-lookup"><span data-stu-id="c0bd8-476">7</span></span>              | <span data-ttu-id="c0bd8-477">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-477">Custom</span></span> | <span data-ttu-id="c0bd8-478">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-478">Finance lease obligation</span></span> |           | <span data-ttu-id="c0bd8-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="c0bd8-479">22,793.90</span></span> |

<span data-ttu-id="c0bd8-480">O pagamento do arrendamento é lançado como os outros pagamentos de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="c0bd8-481">O motivo de usar a conta de compensação é garantir que o dinheiro seja creditado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="c0bd8-482">Pagamento de arrendamento – 31/1/2020 – JE 150</span><span class="sxs-lookup"><span data-stu-id="c0bd8-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="c0bd8-483">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-483">Account type</span></span> | <span data-ttu-id="c0bd8-484">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-484">Account number</span></span> | <span data-ttu-id="c0bd8-485">Camada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-485">Layer</span></span>  | <span data-ttu-id="c0bd8-486">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-486">Account description</span></span>      | <span data-ttu-id="c0bd8-487">Débito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-487">Debit</span></span>    | <span data-ttu-id="c0bd8-488">Crédito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="c0bd8-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-489">Ledger</span></span>       | <span data-ttu-id="c0bd8-490">7</span><span class="sxs-lookup"><span data-stu-id="c0bd8-490">7</span></span>              | <span data-ttu-id="c0bd8-491">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-491">Custom</span></span> | <span data-ttu-id="c0bd8-492">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-492">Finance lease obligation</span></span> | <span data-ttu-id="c0bd8-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-493">1,000.00</span></span> |          |
| <span data-ttu-id="c0bd8-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-494">Ledger</span></span>       | <span data-ttu-id="c0bd8-495">4</span><span class="sxs-lookup"><span data-stu-id="c0bd8-495">4</span></span>              | <span data-ttu-id="c0bd8-496">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-496">Custom</span></span> | <span data-ttu-id="c0bd8-497">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-497">Clearing account</span></span>         |          | <span data-ttu-id="c0bd8-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-498">1,000.00</span></span> |

<span data-ttu-id="c0bd8-499">A entrada do diário de despesas de juros é gerada a partir do agendamento de amortização de passivo.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="c0bd8-500">Despesa de Juros – 31/1/2020 – JE 160</span><span class="sxs-lookup"><span data-stu-id="c0bd8-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="c0bd8-501">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-501">Account type</span></span> | <span data-ttu-id="c0bd8-502">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-502">Account number</span></span> | <span data-ttu-id="c0bd8-503">Camada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-503">Layer</span></span>  | <span data-ttu-id="c0bd8-504">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-504">Account description</span></span>      | <span data-ttu-id="c0bd8-505">Débito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-505">Debit</span></span> | <span data-ttu-id="c0bd8-506">Crédito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="c0bd8-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-507">Ledger</span></span>       | <span data-ttu-id="c0bd8-508">8</span><span class="sxs-lookup"><span data-stu-id="c0bd8-508">8</span></span>              | <span data-ttu-id="c0bd8-509">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-509">Custom</span></span> | <span data-ttu-id="c0bd8-510">Despesa de Juros</span><span class="sxs-lookup"><span data-stu-id="c0bd8-510">Interest expense</span></span>         | <span data-ttu-id="c0bd8-511">94.97</span><span class="sxs-lookup"><span data-stu-id="c0bd8-511">94.97</span></span> |        |
| <span data-ttu-id="c0bd8-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-512">Ledger</span></span>       | <span data-ttu-id="c0bd8-513">7</span><span class="sxs-lookup"><span data-stu-id="c0bd8-513">7</span></span>              | <span data-ttu-id="c0bd8-514">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-514">Custom</span></span> | <span data-ttu-id="c0bd8-515">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-515">Finance lease obligation</span></span> |       | <span data-ttu-id="c0bd8-516">94.97</span><span class="sxs-lookup"><span data-stu-id="c0bd8-516">94.97</span></span>  |

<span data-ttu-id="c0bd8-517">A entrada do diário de despesas de depreciação é gerada a partir do agendamento de depreciação de ativos.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="c0bd8-518">Despesa de depreciação – 31/1/2020 – JE 170</span><span class="sxs-lookup"><span data-stu-id="c0bd8-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="c0bd8-519">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-519">Account type</span></span> | <span data-ttu-id="c0bd8-520">Número da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-520">Account number</span></span> | <span data-ttu-id="c0bd8-521">Camada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-521">Layer</span></span>  | <span data-ttu-id="c0bd8-522">Descrição da conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-522">Account description</span></span>      | <span data-ttu-id="c0bd8-523">Débito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-523">Debit</span></span>  | <span data-ttu-id="c0bd8-524">Crédito</span><span class="sxs-lookup"><span data-stu-id="c0bd8-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="c0bd8-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-525">Ledger</span></span>       | <span data-ttu-id="c0bd8-526">10</span><span class="sxs-lookup"><span data-stu-id="c0bd8-526">10</span></span>             | <span data-ttu-id="c0bd8-527">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-527">Custom</span></span> | <span data-ttu-id="c0bd8-528">Despesa de Depreciação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-528">Depreciation expense</span></span>     | <span data-ttu-id="c0bd8-529">949,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-529">949.75</span></span> |        |
| <span data-ttu-id="c0bd8-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="c0bd8-530">Ledger</span></span>       | <span data-ttu-id="c0bd8-531">11</span><span class="sxs-lookup"><span data-stu-id="c0bd8-531">11</span></span>             | <span data-ttu-id="c0bd8-532">Personalizada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-532">Custom</span></span> | <span data-ttu-id="c0bd8-533">Depreciação Acumulada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="c0bd8-534">949,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-534">949.75</span></span> |

<span data-ttu-id="c0bd8-535">Depois que todas essas entradas de diário forem criadas e lançadas, você verá os seguintes valores de "nível 1 personalizado".</span><span class="sxs-lookup"><span data-stu-id="c0bd8-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="c0bd8-536">Observe que a última coluna inclui a tarifa bancária, a despesa de imposto sobre valor agregado (IVA) e a redução de pagamento à vista do nível anterior, mas ela não inclui as entradas de diário de relatório estatutário.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="c0bd8-537">Portanto, você realmente obtém recursos de relatório duplo.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="c0bd8-538">Neste ponto, a empresa precisa apenas executar seu balancete e combinar o nível atual e o nível personalizado para criar um balancete de IFRS.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="c0bd8-539">Nº de conta</span><span class="sxs-lookup"><span data-stu-id="c0bd8-539">Account No</span></span> | <span data-ttu-id="c0bd8-540">descrição</span><span class="sxs-lookup"><span data-stu-id="c0bd8-540">Description</span></span>              | <span data-ttu-id="c0bd8-541">Livro fiscal\-Nível atual\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="c0bd8-542">Livro fiscal\-Nível atual\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="c0bd8-543">Livro fiscal\-Nível atual\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="c0bd8-544">Nível atual \- Totais</span><span class="sxs-lookup"><span data-stu-id="c0bd8-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="c0bd8-545">Registro de estorno\-Nível atual\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="c0bd8-546">Registro IFRS 16\-Nível atual\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="c0bd8-547">Registro IFRS 16\-Nível atual\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="c0bd8-548">Registro IFRS 16\-Nível atual\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="c0bd8-549">Registro IFRS 16\-Nível atual\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="c0bd8-550">Nível personalizado \+ Nível atual \- Totais</span><span class="sxs-lookup"><span data-stu-id="c0bd8-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="c0bd8-551">1</span><span class="sxs-lookup"><span data-stu-id="c0bd8-551">1</span></span>          | <span data-ttu-id="c0bd8-552">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="c0bd8-552">Lease expense</span></span>            | <span data-ttu-id="c0bd8-553">1,000\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="c0bd8-554">1,000\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-554">1,000\.00</span></span>               |   | <span data-ttu-id="c0bd8-555">\-1.000</span><span class="sxs-lookup"><span data-stu-id="c0bd8-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="c0bd8-556">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-556">0\.00</span></span>                                   |
| <span data-ttu-id="c0bd8-557">2</span><span class="sxs-lookup"><span data-stu-id="c0bd8-557">2</span></span>          | <span data-ttu-id="c0bd8-558">Tarifa bancária</span><span class="sxs-lookup"><span data-stu-id="c0bd8-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="c0bd8-559">3\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="c0bd8-560">3\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="c0bd8-561">3\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-561">3\.00</span></span>                                   |
| <span data-ttu-id="c0bd8-562">3</span><span class="sxs-lookup"><span data-stu-id="c0bd8-562">3</span></span>          | <span data-ttu-id="c0bd8-563">Despesa de IVA</span><span class="sxs-lookup"><span data-stu-id="c0bd8-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="c0bd8-564">5\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="c0bd8-565">5\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="c0bd8-566">5\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-566">5\.00</span></span>                                   |
| <span data-ttu-id="c0bd8-567">4</span><span class="sxs-lookup"><span data-stu-id="c0bd8-567">4</span></span>          | <span data-ttu-id="c0bd8-568">Conta de compensação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-568">Clearing account</span></span>         | <span data-ttu-id="c0bd8-569">\-1.000\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="c0bd8-570">1,000\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="c0bd8-571">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-571">0\.00</span></span>                   |   | <span data-ttu-id="c0bd8-572">1.000</span><span class="sxs-lookup"><span data-stu-id="c0bd8-572">1,000</span></span>                                           |                                                | <span data-ttu-id="c0bd8-573">\-1.000</span><span class="sxs-lookup"><span data-stu-id="c0bd8-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="c0bd8-574">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-574">0\.00</span></span>                                   |
| <span data-ttu-id="c0bd8-575">5</span><span class="sxs-lookup"><span data-stu-id="c0bd8-575">5</span></span>          | <span data-ttu-id="c0bd8-576">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="c0bd8-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="c0bd8-577">\-1.008\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="c0bd8-578">1,008\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-578">1,008\.00</span></span>                                         | <span data-ttu-id="c0bd8-579">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="c0bd8-580">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-580">0\.00</span></span>                                   |
| <span data-ttu-id="c0bd8-581">6</span><span class="sxs-lookup"><span data-stu-id="c0bd8-581">6</span></span>          | <span data-ttu-id="c0bd8-582">Ativo DDU</span><span class="sxs-lookup"><span data-stu-id="c0bd8-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="c0bd8-583">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="c0bd8-584">22.794</span><span class="sxs-lookup"><span data-stu-id="c0bd8-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="c0bd8-585">22.793\,90</span><span class="sxs-lookup"><span data-stu-id="c0bd8-585">22,793\.90</span></span>                              |
| <span data-ttu-id="c0bd8-586">7</span><span class="sxs-lookup"><span data-stu-id="c0bd8-586">7</span></span>          | <span data-ttu-id="c0bd8-587">Obrigação de arrendamento mercantil</span><span class="sxs-lookup"><span data-stu-id="c0bd8-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="c0bd8-588">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="c0bd8-589">\-22.794</span><span class="sxs-lookup"><span data-stu-id="c0bd8-589">\-22,794</span></span>                                       | <span data-ttu-id="c0bd8-590">1.000</span><span class="sxs-lookup"><span data-stu-id="c0bd8-590">1,000</span></span>                                          | <span data-ttu-id="c0bd8-591">\-94\,97</span><span class="sxs-lookup"><span data-stu-id="c0bd8-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="c0bd8-592">\-21.888\,87</span><span class="sxs-lookup"><span data-stu-id="c0bd8-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="c0bd8-593">8</span><span class="sxs-lookup"><span data-stu-id="c0bd8-593">8</span></span>          | <span data-ttu-id="c0bd8-594">Despesa de Juros</span><span class="sxs-lookup"><span data-stu-id="c0bd8-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="c0bd8-595">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="c0bd8-596">94\,97</span><span class="sxs-lookup"><span data-stu-id="c0bd8-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="c0bd8-597">94\,97</span><span class="sxs-lookup"><span data-stu-id="c0bd8-597">94\.97</span></span>                                  |
| <span data-ttu-id="c0bd8-598">9</span><span class="sxs-lookup"><span data-stu-id="c0bd8-598">9</span></span>          | <span data-ttu-id="c0bd8-599">Pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="c0bd8-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="c0bd8-600">\-1.008\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="c0bd8-601">\-1.008\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="c0bd8-602">\-1.008\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="c0bd8-603">10</span><span class="sxs-lookup"><span data-stu-id="c0bd8-603">10</span></span>         | <span data-ttu-id="c0bd8-604">Despesa de Depreciação</span><span class="sxs-lookup"><span data-stu-id="c0bd8-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="c0bd8-605">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="c0bd8-606">949\,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-606">949\.75</span></span>                                        | <span data-ttu-id="c0bd8-607">949\,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-607">949\.75</span></span>                                 |
| <span data-ttu-id="c0bd8-608">11</span><span class="sxs-lookup"><span data-stu-id="c0bd8-608">11</span></span>         | <span data-ttu-id="c0bd8-609">Depreciação Acumulada</span><span class="sxs-lookup"><span data-stu-id="c0bd8-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="c0bd8-610">0\,00</span><span class="sxs-lookup"><span data-stu-id="c0bd8-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="c0bd8-611">\-949\,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-611">\-949\.75</span></span>                                      | <span data-ttu-id="c0bd8-612">\-949\,75</span><span class="sxs-lookup"><span data-stu-id="c0bd8-612">\-949\.75</span></span>                               |


