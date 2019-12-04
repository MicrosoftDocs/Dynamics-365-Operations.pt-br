---
title: Contratos do projeto
description: Este tópico fornece exemplos de contratos de projeto que você pode criar para vários tipos de projetos e de fontes de financiamento, e como você pode gerenciar contratos e clientes do projeto de fatura.
author: KimANelson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 854ddfe6db93b7e93a4ee640268a9c8f254f24e7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185557"
---
# <a name="project-contracts"></a><span data-ttu-id="e89b3-103">Contratos do projeto</span><span class="sxs-lookup"><span data-stu-id="e89b3-103">Project contracts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e89b3-104">Este artigo fornece exemplos de contratos de projeto que você pode criar para vários tipos de projetos e de fontes de financiamento, e como você pode gerenciar contratos e clientes do projeto de fatura.</span><span class="sxs-lookup"><span data-stu-id="e89b3-104">This article provides examples of the project contracts that you can create for various types of projects and funding sources, and how you can manage contracts and invoice project customers.</span></span>

<span data-ttu-id="e89b3-105">O tipo de projeto que você cria para um contrato de projeto determina o método de faturamento que é usado para os clientes de projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-105">The type of project that you create for a project contract determines the method that is used to invoice project customers.</span></span> <span data-ttu-id="e89b3-106">Você pode modificar um contrato de projeto e o projeto relacionado, mas não é possível alterar o tipo de projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-106">You can change a project contract and the related project, but you can't change the project type.</span></span> 

<span data-ttu-id="e89b3-107">Ao usar um contrato de projeto, você pode faturar um ou mais projetos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="e89b3-107">By using a project contract, you can invoice one or more projects at the same time.</span></span> <span data-ttu-id="e89b3-108">O contrato de projeto também ajuda a garantir um procedimento de faturamento consistente para cada subprojeto de uma estrutura de projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-108">The project contract also helps guarantee a consistent invoicing procedure for every subproject in a project structure.</span></span> 

<span data-ttu-id="e89b3-109">Cada projeto que será faturado deve estar associado a um contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-109">Every project that will be invoiced must be associated with a project contract.</span></span> <span data-ttu-id="e89b3-110">As configurações para um contrato de projeto se aplicam a todos os projetos e subprojetos associados ao contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-110">The settings for a project contract apply to all projects and subprojects that are associated with that project contract.</span></span> 

<span data-ttu-id="e89b3-111">Um contrato de projeto pode especificar uma ou mais origens de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-111">A project contract can specify one or more sources of funding.</span></span> <span data-ttu-id="e89b3-112">Portanto, é possível dividir a cobrança entre vários financiadores, configurar os limites de financiamento para que não seja cobrado mais do que um valor especificado das fontes de financiamento, e configurar regras de financiamento para cobrar despesas.</span><span class="sxs-lookup"><span data-stu-id="e89b3-112">Therefore, you can split the billing among multiple funders, set up funding limits so that funding sources are not billed more than a specified amount, and configure funding rules for charging expenditures.</span></span>

## <a name="funding-for-project-contracts"></a><span data-ttu-id="e89b3-113">Financiamento para contratos de projeto</span><span class="sxs-lookup"><span data-stu-id="e89b3-113">Funding for project contracts</span></span>
<span data-ttu-id="e89b3-114">Alguns contratos de projeto especificam que diversos participantes compartilhem a responsabilidade pelo financiamento dos custos do projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-114">Some project contracts specify that multiple parties share the responsibility for funding the project costs.</span></span> <span data-ttu-id="e89b3-115">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="e89b3-115">Here are some examples:</span></span>

-   <span data-ttu-id="e89b3-116">Um grande cliente que tem várias divisões solicita que o financiamento de um projeto seja dividido por divisão.</span><span class="sxs-lookup"><span data-stu-id="e89b3-116">A large customer that has multiple divisions requests that funding of a project be split by division.</span></span>
-   <span data-ttu-id="e89b3-117">A empresa compartilha os custos de um grande projeto com uma organização externa.</span><span class="sxs-lookup"><span data-stu-id="e89b3-117">Your company shares the costs of a large project with an external organization.</span></span>
-   <span data-ttu-id="e89b3-118">Um projeto de estrada é refinanciado por duas municipalidades.</span><span class="sxs-lookup"><span data-stu-id="e89b3-118">A  road project is co-funded by two municipalities.</span></span>
-   <span data-ttu-id="e89b3-119">Um projeto de ponte é patrocinado por um subsídio do governo e por uma empresa privada.</span><span class="sxs-lookup"><span data-stu-id="e89b3-119">A bridge project is funded by a government grant and a private corporation.</span></span>

<span data-ttu-id="e89b3-120">No Dynamics 365 Finance, você pode dividir a cobrança de uma única transação ou um projeto inteiro entre vários clientes, concessões, ou organizações.</span><span class="sxs-lookup"><span data-stu-id="e89b3-120">In Dynamics 365 Finance, you can split the billing for a single transaction or an entire project among multiple customers, grants, or organizations.</span></span> 

<span data-ttu-id="e89b3-121">Nos projetos que têm várias financiadoras, todos os participantes que contribuem com o financiamento de um projeto avançado de financiamento são chamadas fontes de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-121">In projects that have multiple funders, all parties that contribute to the funding of an advanced funding project are called funding sources.</span></span> <span data-ttu-id="e89b3-122">Depois que um cliente, organização ou concessão é definida como fonte de financiamento, poderá então ser atribuída a um ou mais regras de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-122">After a customer, organization, or grant is defined as a funding source, it can be assigned to one or more funding rules.</span></span> <span data-ttu-id="e89b3-123">As regras de financiamento contêm os critérios que determinam como os encargos são alocados para as diversas fontes de financiamento de um projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-123">Funding rules contain the criteria that determines how charges are allocated to the various funding sources for a project.</span></span> 

<span data-ttu-id="e89b3-124">Como os itens estocados, como aqueles que aparecem em requisições de compra e ordens de compra, não podem ser divididos, o valor de custo não pode ser dividido entre várias fontes de financiamento no momento da distribuição.</span><span class="sxs-lookup"><span data-stu-id="e89b3-124">Because stocked items, such as those that appear on purchase requisitions and purchase orders, can't be split, the cost amount can't be split among multiple funding sources at the time of distribution.</span></span> <span data-ttu-id="e89b3-125">Portanto, o valor da fonte de financiamento permanece em zero até a saída do estoque ser lançada.</span><span class="sxs-lookup"><span data-stu-id="e89b3-125">Therefore, the funding source value remains 0 (zero) until the inventory issue is posted.</span></span> <span data-ttu-id="e89b3-126">Quando a saída de estoque é lançada, o valor de custo é distribuído de acordo com as regras de distribuição da conta para o projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-126">When the inventory issue is posted, the cost amount is distributed according to the account distribution rules for the project.</span></span>

<span data-ttu-id="e89b3-127">Veja a seguir algumas etapas que você pode executar para facilitar a divisão da cobrança entre várias fontes de financiamento:</span><span class="sxs-lookup"><span data-stu-id="e89b3-127">Here are some steps that you can take to make it easier to split the billing among multiple funding sources:</span></span>

-   <span data-ttu-id="e89b3-128">Especificar se todas as transações que são inseridas para um projeto usam a mesma moeda de venda que o contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-128">Specify that all transactions that are entered for a project use the same sales currency as the project contract.</span></span>
-   <span data-ttu-id="e89b3-129">Configurar os limites de financiamento de forma que uma fonte de financiamento não seja faturada além do valor especificado para um projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-129">Set up funding limits, so that a funding source isn't invoiced more than a specified amount toward a project.</span></span>
-   <span data-ttu-id="e89b3-130">Configurar as regras de financiamento e os limites de financiamento para cada trabalhador, item, categoria, grupo de categorias e tipo de transação (ou para todos os tipos de transação).</span><span class="sxs-lookup"><span data-stu-id="e89b3-130">Configure funding rules and funding limits for each worker, item, category, category group, and transaction type (or for all transaction types).</span></span>
-   <span data-ttu-id="e89b3-131">Escolher as datas inicial e final opcionais para definir o período de tempo que cada regra de financiamento ficará válida.</span><span class="sxs-lookup"><span data-stu-id="e89b3-131">Select optional start and end dates to define the period when each funding rule is valid.</span></span>
-   <span data-ttu-id="e89b3-132">Especificar a porcentagem que cada fonte de financiamento ficará responsável.</span><span class="sxs-lookup"><span data-stu-id="e89b3-132">Specify the percentage that each funding source is responsible for.</span></span>
-   <span data-ttu-id="e89b3-133">Especificar a fonte de financiamento responsável pelas diferenças de arredondamento causadas pelos cálculos de alocação de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-133">Specify which funding source is responsible for rounding differences that are caused by funding allocation calculations.</span></span>
-   <span data-ttu-id="e89b3-134">Configurar as regras que determinam como os custos do projeto serão faturados para clientes externos e cobrados de organizações internas.</span><span class="sxs-lookup"><span data-stu-id="e89b3-134">Set up rules that determine how project costs are invoiced to external customers and charged to internal organizations.</span></span>
-   <span data-ttu-id="e89b3-135">Registrar transações em uma conta de financiamento em espera até que o financiamento adicional possa ser obtido ou até você decidir carregar internamente o custo.</span><span class="sxs-lookup"><span data-stu-id="e89b3-135">Record transactions in an on-hold funding account until additional funding can be obtained, or until you decide to bear the costs internally.</span></span>

<span data-ttu-id="e89b3-136">Para determinar o grupo de impostos para associar uma transação, o projeto é pesquisado por uma atribuição do grupo de impostos.</span><span class="sxs-lookup"><span data-stu-id="e89b3-136">To determine which tax group to associate with a transaction, the project is searched for a tax group assignment.</span></span> <span data-ttu-id="e89b3-137">Se nenhuma atribuição do grupo de impostos foi feita no nível do projeto, o contrato de projeto é pesquisado.</span><span class="sxs-lookup"><span data-stu-id="e89b3-137">If no tax group assignment has been made at the project level, the project contract is searched.</span></span>

### <a name="example-multiple-funding-sources-simple"></a><span data-ttu-id="e89b3-138">Exemplo: diversas fontes de financiamento (simples)</span><span class="sxs-lookup"><span data-stu-id="e89b3-138">Example: Multiple funding sources (simple)</span></span>

<span data-ttu-id="e89b3-139">A tabela a seguir fornece cenários para gerenciar a alocação de financiamento entre várias fontes de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-139">The following table provides scenarios for managing funding allocation among multiple funding sources.</span></span> <span data-ttu-id="e89b3-140">Estes cenários baseiam-se nas seguintes suposições:</span><span class="sxs-lookup"><span data-stu-id="e89b3-140">These scenarios are based on the following assumptions:</span></span>

-   <span data-ttu-id="e89b3-141">As configurações de prioridade são fatoradas na alocação de fundos antes que outros critérios da regra de financiamento sejam aplicados.</span><span class="sxs-lookup"><span data-stu-id="e89b3-141">Priority settings are factored into the allocation of funds before other funding rule criteria are applied.</span></span>
-   <span data-ttu-id="e89b3-142">Nenhum intervalo de datas foi especificado para definir o período d quando a regra de financiamento é válida.</span><span class="sxs-lookup"><span data-stu-id="e89b3-142">No date range has been specified to define the period d when the funding rule is valid.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e89b3-143"><strong>Cenário</strong></span><span class="sxs-lookup"><span data-stu-id="e89b3-143"><strong>Scenario</strong></span></span></td>
<td><span data-ttu-id="e89b3-144"><strong>Fonte de financiamento </strong></span><span class="sxs-lookup"><span data-stu-id="e89b3-144"><strong>Funding source</strong></span></span></td>
<td><span data-ttu-id="e89b3-145"><strong>Porcentagem de alocação </strong></span><span class="sxs-lookup"><span data-stu-id="e89b3-145"><strong>Allocation percentage</strong></span></span></td>
<td><span data-ttu-id="e89b3-146"><strong>Prioridade de alocação </strong></span><span class="sxs-lookup"><span data-stu-id="e89b3-146"><strong>Allocation priority</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e89b3-147">Você deseja alocar custos para uma fonte de financiamento até que os fundos sejam esgotados, alocar custos para uma segunda fonte de financiamento até que os fundos sejam esgotados e, por fim, alocar os custos restantes para uma terceira fonte de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-147">You want to allocate costs to one funding source until its funds are exhausted, allocate costs to a second funding source until its funds are exhausted, and finally allocate the remaining costs to a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="e89b3-148">Fonte de financiamento 1</span><span class="sxs-lookup"><span data-stu-id="e89b3-148">Funding　source　1</span></span></li>
<li><span data-ttu-id="e89b3-149">Fonte de financiamento 2</span><span class="sxs-lookup"><span data-stu-id="e89b3-149">Funding　source　2</span></span></li>
<li><span data-ttu-id="e89b3-150">Fonte de financiamento 3</span><span class="sxs-lookup"><span data-stu-id="e89b3-150">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e89b3-151">100%</span><span class="sxs-lookup"><span data-stu-id="e89b3-151">100%</span></span></li>
<li><span data-ttu-id="e89b3-152">100%</span><span class="sxs-lookup"><span data-stu-id="e89b3-152">100%</span></span></li>
<li><span data-ttu-id="e89b3-153">100%</span><span class="sxs-lookup"><span data-stu-id="e89b3-153">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e89b3-154">1</span><span class="sxs-lookup"><span data-stu-id="e89b3-154">1</span></span></li>
<li><span data-ttu-id="e89b3-155">2</span><span class="sxs-lookup"><span data-stu-id="e89b3-155">2</span></span></li>
<li><span data-ttu-id="e89b3-156">3</span><span class="sxs-lookup"><span data-stu-id="e89b3-156">3</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e89b3-157">Você deseja alocar 75% dos custos para uma fonte de financiamento e 25% para uma segunda fonte de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-157">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="e89b3-158">Quando qualquer uma dessas fontes de financiamento for esgotada, você desejará pagar os custos restantes de uma terceira fonte de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-158">When either of those funding sources is exhausted, you want to pay the remaining costs from a third funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="e89b3-159">Fonte de financiamento 1</span><span class="sxs-lookup"><span data-stu-id="e89b3-159">Funding　source　1</span></span></li>
<li><span data-ttu-id="e89b3-160">Fonte de financiamento 2</span><span class="sxs-lookup"><span data-stu-id="e89b3-160">Funding　source　2</span></span></li>
<li><span data-ttu-id="e89b3-161">Fonte de financiamento 3</span><span class="sxs-lookup"><span data-stu-id="e89b3-161">Funding　source　3</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e89b3-162">75%</span><span class="sxs-lookup"><span data-stu-id="e89b3-162">75%</span></span></li>
<li><span data-ttu-id="e89b3-163">25%</span><span class="sxs-lookup"><span data-stu-id="e89b3-163">25%</span></span></li>
<li><span data-ttu-id="e89b3-164">100%</span><span class="sxs-lookup"><span data-stu-id="e89b3-164">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e89b3-165">1</span><span class="sxs-lookup"><span data-stu-id="e89b3-165">1</span></span></li>
<li><span data-ttu-id="e89b3-166">1</span><span class="sxs-lookup"><span data-stu-id="e89b3-166">1</span></span></li>
<li><span data-ttu-id="e89b3-167">2</span><span class="sxs-lookup"><span data-stu-id="e89b3-167">2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e89b3-168">Você deseja alocar 75% dos custos para uma fonte de financiamento e 25% para uma segunda fonte de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-168">You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source.</span></span> <span data-ttu-id="e89b3-169">Quando qualquer uma das fontes de financiamento for esgotada, você desejará dividir os custos restantes entre uma terceira e quarta fonte de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-169">When either of those funding sources is exhausted, you want to split the remaining costs between a third funding source and a fourth funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="e89b3-170">Fonte de financiamento 1</span><span class="sxs-lookup"><span data-stu-id="e89b3-170">Funding　source　1</span></span></li>
<li><span data-ttu-id="e89b3-171">Fonte de financiamento 2</span><span class="sxs-lookup"><span data-stu-id="e89b3-171">Funding　source　2</span></span></li>
<li><span data-ttu-id="e89b3-172">Fonte de financiamento 3</span><span class="sxs-lookup"><span data-stu-id="e89b3-172">Funding　source　3</span></span></li>
<li><span data-ttu-id="e89b3-173">Fonte de financiamento 4</span><span class="sxs-lookup"><span data-stu-id="e89b3-173">Funding　source　4</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e89b3-174">75%</span><span class="sxs-lookup"><span data-stu-id="e89b3-174">75%</span></span></li>
<li><span data-ttu-id="e89b3-175">25%</span><span class="sxs-lookup"><span data-stu-id="e89b3-175">25%</span></span></li>
<li><span data-ttu-id="e89b3-176">50%</span><span class="sxs-lookup"><span data-stu-id="e89b3-176">50%</span></span></li>
<li><span data-ttu-id="e89b3-177">50%</span><span class="sxs-lookup"><span data-stu-id="e89b3-177">50%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e89b3-178">1</span><span class="sxs-lookup"><span data-stu-id="e89b3-178">1</span></span></li>
<li><span data-ttu-id="e89b3-179">1</span><span class="sxs-lookup"><span data-stu-id="e89b3-179">1</span></span></li>
<li><span data-ttu-id="e89b3-180">2</span><span class="sxs-lookup"><span data-stu-id="e89b3-180">2</span></span></li>
<li><span data-ttu-id="e89b3-181">2</span><span class="sxs-lookup"><span data-stu-id="e89b3-181">2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e89b3-182">Você deseja alocar os primeiros 25% dos custos a uma fonte de financiamento e o restante a uma segunda fonte.</span><span class="sxs-lookup"><span data-stu-id="e89b3-182">You want to allocate the first 25 percent of costs to one funding source and the rest to a second funding source.</span></span></td>
<td><ul>
<li><span data-ttu-id="e89b3-183">Fonte de financiamento 1</span><span class="sxs-lookup"><span data-stu-id="e89b3-183">Funding　source　1</span></span></li>
<li><span data-ttu-id="e89b3-184">Fonte de financiamento 2</span><span class="sxs-lookup"><span data-stu-id="e89b3-184">Funding　source　2</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e89b3-185">25%</span><span class="sxs-lookup"><span data-stu-id="e89b3-185">25%</span></span></li>
<li><span data-ttu-id="e89b3-186">100%</span><span class="sxs-lookup"><span data-stu-id="e89b3-186">100%</span></span></li>
</ul></td>
<td><ul>
<li><span data-ttu-id="e89b3-187">1</span><span class="sxs-lookup"><span data-stu-id="e89b3-187">1</span></span></li>
<li><span data-ttu-id="e89b3-188">2</span><span class="sxs-lookup"><span data-stu-id="e89b3-188">2</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a><span data-ttu-id="e89b3-189">Exemplo: Diversas fontes de financiamento (complexo)</span><span class="sxs-lookup"><span data-stu-id="e89b3-189">Example: Multiple funding sources (complex)</span></span>

<span data-ttu-id="e89b3-190">Há três fontes de financiamento que você deseja usar na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="e89b3-190">You have three funding sources that you want to use in the following order:</span></span>

1.  <span data-ttu-id="e89b3-191">Usar a fonte de financiamento 2 e a fonte de financiamento 3 igualmente até que a fonte de financiamento 2 seja esgotada.</span><span class="sxs-lookup"><span data-stu-id="e89b3-191">Use funding source 2 and funding source 3 equally until funding source 2 is exhausted.</span></span>
2.  <span data-ttu-id="e89b3-192">Continuar usando a fonte de financiamento 3 até que seja esgotada.</span><span class="sxs-lookup"><span data-stu-id="e89b3-192">Continue to use funding source 3 until it is exhausted.</span></span>
3.  <span data-ttu-id="e89b3-193">Usar a fonte de financiamento 1 depois que a fonte de financiamento 3 for esgotada.</span><span class="sxs-lookup"><span data-stu-id="e89b3-193">Use funding source 1 after funding source 3 is exhausted.</span></span>

<span data-ttu-id="e89b3-194">Para atingir esse meta, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="e89b3-194">To accomplish this goal, you must do the following:</span></span>

-   <span data-ttu-id="e89b3-195">Configure os limites de financiamento para a fonte de financiamento 2 e a fonte de financiamento 3 para seus respectivos valores.</span><span class="sxs-lookup"><span data-stu-id="e89b3-195">Set up funding limits for funding source 2 and funding source 3, for their respective amounts.</span></span>
-   <span data-ttu-id="e89b3-196">Crie as seguintes regras de financiamento:</span><span class="sxs-lookup"><span data-stu-id="e89b3-196">Create the following funding rules:</span></span>
    -   <span data-ttu-id="e89b3-197">Regra 1 (Prioridade 1): alocar 50% das transações para a fonte de financiamento 2 e 50% para a fonte de financiamento 3.</span><span class="sxs-lookup"><span data-stu-id="e89b3-197">Rule 1 (Priority 1): Allocate 50 percent of transactions to funding source 2 and 50 percent to funding source 3.</span></span>
    -   <span data-ttu-id="e89b3-198">Regra 2 (Prioridade 2): alocar 100% das transações para a fonte de financiamento 3.</span><span class="sxs-lookup"><span data-stu-id="e89b3-198">Rule 2 (Priority 2): Allocate 100 percent of transactions to funding source 3.</span></span>
    -   <span data-ttu-id="e89b3-199">Regra 3 (Prioridade 3): alocar 100% das transações para a fonte de financiamento 1.</span><span class="sxs-lookup"><span data-stu-id="e89b3-199">Rule 3 (Priority 3): Allocate 100 percent of transactions to funding source 1.</span></span>

<span data-ttu-id="e89b3-200">Essa configuração verifica as transações em relação às regras e aos limites para determinar se alguma delas se aplica à transação.</span><span class="sxs-lookup"><span data-stu-id="e89b3-200">This setup works because transactions are checked against rules and limits to determine whether any of them apply to the transaction.</span></span> <span data-ttu-id="e89b3-201">Se nenhuma regra ou limite específico se aplicar à transação, será aplicada a regra Todas as transações.</span><span class="sxs-lookup"><span data-stu-id="e89b3-201">If no specific rules or limits apply to the transaction, the All transactions rule applies.</span></span> <span data-ttu-id="e89b3-202">A regra Todas as transações corresponde a todas as transações.</span><span class="sxs-lookup"><span data-stu-id="e89b3-202">The All transactions rule matches all transactions.</span></span> 

<span data-ttu-id="e89b3-203">Se o sistema localizar uma regra que corresponda a uma transação, a porcentagem que foi alocada nessa regra será aplicada primeiro, mas somente depois que as correspondências forem verificadas em relação aos limites que foram configurados.</span><span class="sxs-lookup"><span data-stu-id="e89b3-203">If a rule is found that matches a transaction, the percentage that has been allocated in that rule is applied first, but only after the matches are checked against any limits that have been set up.</span></span> <span data-ttu-id="e89b3-204">Se um limite for correspondido e os fundos de uma fonte de financiamento forem esgotados, a regra de financiamento associada ao limite de financiamento será desconsiderada e o programa verificará a próxima regra que se aplica.</span><span class="sxs-lookup"><span data-stu-id="e89b3-204">If a limit has been met, and a funding source’s funds are exhausted, the funding rule that is associated with the funding limit is disregarded, and the program checks for the next rule that applies.</span></span> 

<span data-ttu-id="e89b3-205">Em alguns casos, somente parte de uma transação poderá ser alocada sob uma regra.</span><span class="sxs-lookup"><span data-stu-id="e89b3-205">In some cases, only part of a transaction can be allocated under a rule.</span></span> <span data-ttu-id="e89b3-206">Isso pode acontecer porque um limite é atingido quando a transação é alocada.</span><span class="sxs-lookup"><span data-stu-id="e89b3-206">This might happen because a limit is reached when the transaction is allocated.</span></span> <span data-ttu-id="e89b3-207">Nesse caso, somente um determinado valor é alocado de acordo com a regra, como 50% para cada fonte de financiamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-207">In this case, only a certain amount is allocated according to that rule, such as 50 percent to each funding source.</span></span> <span data-ttu-id="e89b3-208">Esse é o caso na regra 1, descrita mais acima nesta seção.</span><span class="sxs-lookup"><span data-stu-id="e89b3-208">This is the case in rule 1, which is described earlier in this section.</span></span> <span data-ttu-id="e89b3-209">O restante é alocado de acordo com a próxima regra na sequência.</span><span class="sxs-lookup"><span data-stu-id="e89b3-209">The remainder is allocated according to the next rule in the sequence.</span></span> 

<span data-ttu-id="e89b3-210">A tabela a seguir examina esse cenário detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="e89b3-210">The following table examines this scenario in more detail.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="e89b3-211"><strong>Foco </strong></span><span class="sxs-lookup"><span data-stu-id="e89b3-211"><strong>Focus</strong></span></span></td>
<td><span data-ttu-id="e89b3-212"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="e89b3-212"><strong>Details</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e89b3-213">Regras de financiamento</span><span class="sxs-lookup"><span data-stu-id="e89b3-213">Funding rules</span></span></td>
<td><ul>
<li><span data-ttu-id="e89b3-214">Regra 1 (Prioridade 1): Todas as transações.</span><span class="sxs-lookup"><span data-stu-id="e89b3-214">Rule 1 (Priority 1): All transactions.</span></span> <span data-ttu-id="e89b3-215">Alocar 50% para a fonte de financiamento 2 e 50% para a fonte de financiamento 3.</span><span class="sxs-lookup"><span data-stu-id="e89b3-215">Allocate funding source 2 at 50% and funding source 3 at 50%.</span></span></li>
<li><span data-ttu-id="e89b3-216">Regra 2 (Prioridade 2): Todas as transações.</span><span class="sxs-lookup"><span data-stu-id="e89b3-216">Rule 2 (Priority 2): All transactions.</span></span> <span data-ttu-id="e89b3-217">Alocar 100% para a fonte de financiamento 3.</span><span class="sxs-lookup"><span data-stu-id="e89b3-217">Allocate funding source 3 at 100%.</span></span></li>
<li><span data-ttu-id="e89b3-218">Regra 3 (Prioridade 2): Todas as transações.</span><span class="sxs-lookup"><span data-stu-id="e89b3-218">Rule 3 (Priority 2): All transactions.</span></span> <span data-ttu-id="e89b3-219">Alocar 100% para a fonte de financiamento 1.</span><span class="sxs-lookup"><span data-stu-id="e89b3-219">Allocate funding source 1 at 100%.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e89b3-220">Limites de financiamento</span><span class="sxs-lookup"><span data-stu-id="e89b3-220">Funding limits</span></span></td>
<td><ul>
<li><span data-ttu-id="e89b3-221">Limite da fonte de financiamento 1 = 10.000,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-221">Funding source 1 limit = 10,000.00</span></span></li>
<li><span data-ttu-id="e89b3-222">Limite da fonte de financiamento 2 = 500,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-222">Funding source 2 limit = 500.00</span></span></li>
<li><span data-ttu-id="e89b3-223">Limite da fonte de financiamento 3 = 750,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-223">Funding source 3 limit = 750.00</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e89b3-224">Transação 1</span><span class="sxs-lookup"><span data-stu-id="e89b3-224">Transaction 1</span></span></td>
<td><span data-ttu-id="e89b3-225"><strong>Valor da transação:</strong> 100.00<strong>Financiamento:</strong> A transação é paga somente de acordo com a regra 1, porque a transação é totalmente paga depois que a regra 1 é aplicada.</span><span class="sxs-lookup"><span data-stu-id="e89b3-225"><strong>Transaction amount:</strong> 100.00<strong>Funding:</strong> The transaction is paid according to rule 1 only, because the transaction is fully paid after rule 1 is applied.</span></span> <span data-ttu-id="e89b3-226">A transação é financiada igualmente entre a fonte de financiamento 2 e a fonte de financiamento 3.</span><span class="sxs-lookup"><span data-stu-id="e89b3-226">The transaction is funded equally between funding source 2 and funding source 3.</span></span>
<ul>
<li><span data-ttu-id="e89b3-227">Fonte de financiamento 2: 50,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-227">Funding source 2: 50.00</span></span></li>
<li><span data-ttu-id="e89b3-228">Fonte de financiamento 3: 50,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-228">Funding source 3: 50.00</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="e89b3-229">Transação 2</span><span class="sxs-lookup"><span data-stu-id="e89b3-229">Transaction 2</span></span></td>
<td><span data-ttu-id="e89b3-230"><strong>Valor da transação:</strong> 5.000,00<strong>Financiamento:</strong> A transação é paga de acordo com as três regras.</span><span class="sxs-lookup"><span data-stu-id="e89b3-230"><strong>Transaction amount:</strong> 5,000.00<strong>Funding:</strong> The transaction is paid according to all three rules.</span></span> <span data-ttu-id="e89b3-231"><strong>Regra 1</strong>
</span><span class="sxs-lookup"><span data-stu-id="e89b3-231"><strong>Rule 1</strong>
</span></span><ul>
<li><span data-ttu-id="e89b3-232">Fonte de financiamento 2: 450,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-232">Funding source 2: 450.00</span></span></li>
<li><span data-ttu-id="e89b3-233">Fonte de financiamento 3: 450,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-233">Funding source 3: 450.00</span></span></li>
</ul><span data-ttu-id="e89b3-234">
<strong>Regra 2</strong>
</span><span class="sxs-lookup"><span data-stu-id="e89b3-234">
<strong>Rule 2</strong>
</span></span><ul>
<li><span data-ttu-id="e89b3-235">Fonte de financiamento 3: 250,00 (= 750,00 – 50,00 – 450,00)</span><span class="sxs-lookup"><span data-stu-id="e89b3-235">Funding source 3: 250.00 (= 750.00 – 50.00 – 450.00)</span></span></li>
</ul><span data-ttu-id="e89b3-236">
<strong>Regra 3</strong>
</span><span class="sxs-lookup"><span data-stu-id="e89b3-236">
<strong>Rule 3</strong>
</span></span><ul>
<li><span data-ttu-id="e89b3-237">Fonte de financiamento 1: 3.850,00 (= 5.000,00 – 450,00 – 450,00 – 250,00)</span><span class="sxs-lookup"><span data-stu-id="e89b3-237">Funding source 1: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e89b3-238">Total de fundos distribuído para cada fonte de financiamento</span><span class="sxs-lookup"><span data-stu-id="e89b3-238">Total funds that are distributed for each funding source</span></span></td>
<td><ul>
<li><span data-ttu-id="e89b3-239">Fonte de financiamento 1: 3.850,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-239">Funding source 1: 3,850.00</span></span></li>
<li><span data-ttu-id="e89b3-240">Fonte de financiamento 2: 500,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-240">Funding source 2: 500.00</span></span></li>
<li><span data-ttu-id="e89b3-241">Fonte de financiamento 3: 750,00</span><span class="sxs-lookup"><span data-stu-id="e89b3-241">Funding source 3: 750.00</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a><span data-ttu-id="e89b3-242">Regras de cobrança</span><span class="sxs-lookup"><span data-stu-id="e89b3-242">Billing rules</span></span>
<span data-ttu-id="e89b3-243">Ao negociar o contrato do projeto com um cliente, você define como e quando você pode faturar o cliente pelo trabalho no projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-243">When you negotiate a project contract with a customer, you define how and when you can invoice the customer for work on a project.</span></span> <span data-ttu-id="e89b3-244">Depois que você configurar o contrato de projeto e o projeto, você pode configurar regras de cobrança para o projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-244">After you set up the project contract and the project, you can set up billing rules for the project.</span></span> <span data-ttu-id="e89b3-245">As regras de cobrança são baseadas em termos do projeto que são especificados no contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-245">Billing rules are based on the project terms that are specified in the project contract.</span></span> <span data-ttu-id="e89b3-246">As regras de cobrança que podem ser criadas dependem das condições no contrato de projeto e do tipo de projeto, como tempo e material ou preço fixo, que você associa à regra de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e89b3-246">The billing rules that you can create depend on the terms of the project contract and the project type, such as Time and material or Fixed-price, that you associate with the billing rule.</span></span> <span data-ttu-id="e89b3-247">Você pode criar mais de uma regra de cobrança para um contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-247">You can create more than one billing rule for a project contract.</span></span> <span data-ttu-id="e89b3-248">Também é possível atribuir uma regra de cobrança para vários projetos associados ao mesmo contrato de projeto e que têm condições semelhantes de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e89b3-248">You can also assign a billing rule to multiple projects that are associated with the same project contract and have similar billing terms.</span></span> 

<span data-ttu-id="e89b3-249">Você pode configurar os seguintes tipos de regra de cobrança:</span><span class="sxs-lookup"><span data-stu-id="e89b3-249">You can set up the following types of billing rules:</span></span>

-   <span data-ttu-id="e89b3-250">**Unidade de entrega** – Faturar um cliente ao concluir uma unidade de entrega.</span><span class="sxs-lookup"><span data-stu-id="e89b3-250">**Unit of delivery** – Invoice a customer when you complete a unit of delivery.</span></span> <span data-ttu-id="e89b3-251">Você define as unidades de entrega no contrato.</span><span class="sxs-lookup"><span data-stu-id="e89b3-251">You define the units of delivery in the contract.</span></span>
-   <span data-ttu-id="e89b3-252">**Progresso** – Faturar um cliente ao concluir uma porcentagem especificada do projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-252">**Progress** – Invoice a customer when you complete a specified percentage of the project.</span></span> <span data-ttu-id="e89b3-253">Você pode configurar uma regra de cobrança para calcular automaticamente a porcentagem de trabalho concluída ou calcular manualmente a porcentagem trabalho concluída e o valor para faturar o cliente.</span><span class="sxs-lookup"><span data-stu-id="e89b3-253">You can set up a billing rule to automatically calculate the percentage of work completed, or you can manually calculate the percentage of work completed and the amount to invoice the customer.</span></span>
-   <span data-ttu-id="e89b3-254">**Etapa** – Faturar um cliente pelo valor total de uma etapa de projeto quando a etapa for atingida.</span><span class="sxs-lookup"><span data-stu-id="e89b3-254">**Milestone** – Invoice a customer for the full amount of a project milestone when the milestone is reached.</span></span>
-   <span data-ttu-id="e89b3-255">**Taxa** – Faturar um cliente pelos seus serviços mais uma taxa de gerenciamento, normalmente uma porcentagem do custo dos serviços.</span><span class="sxs-lookup"><span data-stu-id="e89b3-255">**Fee** – Invoice a customer for your services plus a management fee, which is typically a percentage of the cost of services.</span></span>
-   <span data-ttu-id="e89b3-256">**Tempo e material** – Faturar um cliente pelo valor de tempo e de materiais usados em um projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-256">**Time and material** – Invoice a customer for the value of time and materials that are used on a project.</span></span>

<span data-ttu-id="e89b3-257">Para todos os tipos de regras de cobrança, você pode especificar uma porcentagem de retenção que é deduzida de uma fatura de cliente enquanto um projeto alcança uma fase combinada.</span><span class="sxs-lookup"><span data-stu-id="e89b3-257">For all types of billing rules, you can specify a retention percentage that is deducted from customer invoices until a project reaches an agreed-upon stage.</span></span> <span data-ttu-id="e89b3-258">A porcentagem da retenção de pagamento é especificada no contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-258">The payment retention percentage is specified in the project contract.</span></span> <span data-ttu-id="e89b3-259">O valor é calculado com base em e subtraído do valor total das linhas em uma fatura do cliente.</span><span class="sxs-lookup"><span data-stu-id="e89b3-259">The amount is calculated based on, and subtracted from, the total value of the lines in a customer invoice.</span></span> 

<span data-ttu-id="e89b3-260">Para as regras de cobrança **Tempo e material** e **Andamento**, você pode atribuir categorias passíveis de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e89b3-260">For **Time and material** and **Progress** billing rules, you can assign chargeable categories.</span></span> <span data-ttu-id="e89b3-261">As categorias passíveis de cobrança indicam as transações que devem ser incluídas nas faturas do cliente.</span><span class="sxs-lookup"><span data-stu-id="e89b3-261">Chargeable categories indicate the transactions that should be included in customer invoices.</span></span> 

<span data-ttu-id="e89b3-262">Quando você estiver pronto para faturar o cliente, o valor da fatura do projeto será calculado com base nas regras de cobrança, e uma proposta de fatura de projeto será gerada.</span><span class="sxs-lookup"><span data-stu-id="e89b3-262">When you are ready to invoice the customer, the amount to invoice for the project is calculated based on the billing rules, and a project invoice proposal is generated.</span></span> 

<span data-ttu-id="e89b3-263">As seções a seguir fornecem exemplos que ilustram como configurar e gerenciar regras de cobrança para um projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-263">The following sections provide examples that show how to set up and manage billing rules for a project.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a><span data-ttu-id="e89b3-264">Exemplo: Criar uma regra de cobrança com base no número de unidades entregues</span><span class="sxs-lookup"><span data-stu-id="e89b3-264">Example: Create a billing rule that is based on the number of units delivered</span></span>

<span data-ttu-id="e89b3-265">Sua empresa participa de um contrato para fornecer um total de cinco sessões de treinamento aos funcionários de um cliente ao custo de 10.000 por sessão de treinamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-265">Your organization enters into an agreement to provide a total of five training sessions to a customer’s employees at a cost of 10,000 per training session.</span></span> <span data-ttu-id="e89b3-266">Você fatura o cliente ao final de cada sessão de treinamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-266">You invoice the customer after each training session.</span></span> 

<span data-ttu-id="e89b3-267">Ao configurar as regras de cobrança do contrato, use os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e89b3-267">When you set up the billing rules for the contract, you use the following values:</span></span>

-   <span data-ttu-id="e89b3-268">A unidade de entrega é uma sessão de treinamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-268">The unit of delivery is one training session.</span></span>
-   <span data-ttu-id="e89b3-269">O preço unitário é de 10.000 por sessão de treinamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-269">The unit price is 10,000 per training session.</span></span>
-   <span data-ttu-id="e89b3-270">O número total de unidades é cinco sessões de treinamento.</span><span class="sxs-lookup"><span data-stu-id="e89b3-270">The total number of units is five training sessions.</span></span>

<span data-ttu-id="e89b3-271">Quando você concluir uma sessão de treinamento, poderá criar uma fatura de 10.000 para a primeira unidade entregue, e enviar a fatura ao cliente.</span><span class="sxs-lookup"><span data-stu-id="e89b3-271">When you have completed one training session, you can create an invoice for 10,000, for the first unit that was delivered, and send the invoice to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a><span data-ttu-id="e89b3-272">Exemplo: Criar uma regra de cobrança com base em uma porcentagem especificada de conclusão do projeto (calculada manualmente)</span><span class="sxs-lookup"><span data-stu-id="e89b3-272">Example: Create a billing rule that is based on a specified percentage of project completion (manual calculation)</span></span>

<span data-ttu-id="e89b3-273">Sua organização, uma empresa de consultoria de software, fecha um contrato com um cliente para desenvolver parte de um produto que o cliente está desenvolvendo.</span><span class="sxs-lookup"><span data-stu-id="e89b3-273">Your organization, a software consulting firm, enters into an agreement with a customer to develop part of a product that the customer is developing.</span></span> <span data-ttu-id="e89b3-274">Sua organização concorda em entregar o código do software por um período de seis meses.</span><span class="sxs-lookup"><span data-stu-id="e89b3-274">Your organization agrees to deliver the software code over a period of six months.</span></span> <span data-ttu-id="e89b3-275">O cliente concorda em pagar à sua organização um total de R$ 100.000 pelo trabalho.</span><span class="sxs-lookup"><span data-stu-id="e89b3-275">The customer agrees to pay your organization a total of 100,000 for the work.</span></span> <span data-ttu-id="e89b3-276">Você cria uma regra de cobrança para faturar o cliente com base em uma porcentagem de trabalho concluído no projeto, conforme especificado no contrato.</span><span class="sxs-lookup"><span data-stu-id="e89b3-276">You create a billing rule to invoice the customer based on the percentage of work that is completed on the project, as specified in the contract.</span></span>

-   <span data-ttu-id="e89b3-277">No final do primeiro mês, você se reunirá com o cliente para determinar a porcentagem de trabalho concluído.</span><span class="sxs-lookup"><span data-stu-id="e89b3-277">At the end of the first month, you meet with the customer to determine the percentage of work completed.</span></span> <span data-ttu-id="e89b3-278">Após você e o cliente revisarem o projeto, vocês decidem que o projeto está 15 por cento concluído.</span><span class="sxs-lookup"><span data-stu-id="e89b3-278">After you and the customer review the project, you decide that the project is 15 percent completed.</span></span>
-   <span data-ttu-id="e89b3-279">Você cria uma fatura no valor de R$ 15.000 (15% de R$ 100.000) e a envia para o cliente.</span><span class="sxs-lookup"><span data-stu-id="e89b3-279">You create an invoice for 15,000 (15 percent of 100,000) and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a><span data-ttu-id="e89b3-280">Exemplo: Criar uma regra de cobrança com base em uma porcentagem especificada de conclusão do projeto (calculada automaticamente)</span><span class="sxs-lookup"><span data-stu-id="e89b3-280">Example: Create a billing rule that is based on a specified percentage of project completion (automatic calculation)</span></span>

<span data-ttu-id="e89b3-281">Sua organização, uma empresa de programação de software, aceita desenvolver um pacote de contabilidade de folha de pagamento para um cliente por 30.000.</span><span class="sxs-lookup"><span data-stu-id="e89b3-281">Your organization, a software development firm, agrees to develop a payroll accounting package for a customer for 30,000.</span></span> <span data-ttu-id="e89b3-282">O cliente concorda em pagar sua organização com base na porcentagem de trabalho concluído.</span><span class="sxs-lookup"><span data-stu-id="e89b3-282">The customer agrees to pay your organization based on the percentage of work completed.</span></span> <span data-ttu-id="e89b3-283">Você estima que os custos do projeto serão de 20.000.</span><span class="sxs-lookup"><span data-stu-id="e89b3-283">You estimate that the project costs are 20,000.</span></span> <span data-ttu-id="e89b3-284">O contrato de projeto especifica as categorias de trabalho que você usa no processo de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e89b3-284">The project contract specifies the categories of work that you use in the billing process.</span></span> <span data-ttu-id="e89b3-285">Você configura regras de cobrança que calculam automaticamente os valores da fatura pelo percentual de trabalho que é concluído em cada categoria.</span><span class="sxs-lookup"><span data-stu-id="e89b3-285">You set up billing rules that automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="e89b3-286">Você configura um orçamento para cada categoria:</span><span class="sxs-lookup"><span data-stu-id="e89b3-286">You set up a budget for each category:</span></span>

-   <span data-ttu-id="e89b3-287">**Desenvolvimento** – Custo de 15.000 e receita de 20.000</span><span class="sxs-lookup"><span data-stu-id="e89b3-287">**Development** – Cost of 15,000 and revenue of 20,000</span></span>
-   <span data-ttu-id="e89b3-288">**Instalação** – Custo de 5.000 e receita de 10.000.</span><span class="sxs-lookup"><span data-stu-id="e89b3-288">**Installation** – Cost of 5,000 and revenue of 10,000</span></span>

<span data-ttu-id="e89b3-289">Quando você cria uma fatura de cliente pela primeira vez, o valor da fatura é calculado automaticamente com base nas seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="e89b3-289">When you create a customer invoice for the first time, the invoice amount is automatically calculated based on the following information:</span></span>

-   <span data-ttu-id="e89b3-290">Depois de um mês, o trabalhador no projeto envia uma folha de ponto para o projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-290">After a month, the worker on the project submits a timesheet for the project.</span></span> <span data-ttu-id="e89b3-291">O custo das horas do trabalhador é de 5.000 pelo desenvolvimento e de 1.000 pela instalação.</span><span class="sxs-lookup"><span data-stu-id="e89b3-291">The cost of the worker’s hours is 5,000 for development and 1,000 for installation.</span></span> <span data-ttu-id="e89b3-292">O trabalho de desenvolvimento está 33 por cento concluído (5.000 custo real/15.000 custo do orçamento) e o trabalho de instalação está 20 por cento concluído (1.000 custo real/5.000 custo do orçamento).</span><span class="sxs-lookup"><span data-stu-id="e89b3-292">The development work is 33 percent completed (5,000 actual cost/15,000 budget cost), and the installation work is 20 percent completed (1,000 actual cost/5,000 budget cost).</span></span>
-   <span data-ttu-id="e89b3-293">O valor da fatura de 8.667 é calculado automaticamente (33 por cento de 20.000 mais 20 por cento mais de 10.000).</span><span class="sxs-lookup"><span data-stu-id="e89b3-293">The invoice amount of 8,667 is automatically calculated (33 percent of 20,000 + 20 percent of 10,000).</span></span>
-   <span data-ttu-id="e89b3-294">Você cria uma fatura no valor de 8.667 e a envia para o cliente.</span><span class="sxs-lookup"><span data-stu-id="e89b3-294">You create an invoice for 8,667 and send it to the customer.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a><span data-ttu-id="e89b3-295">Exemplo: Criar uma regra de cobrança com base nas etapas combinadas</span><span class="sxs-lookup"><span data-stu-id="e89b3-295">Example: Create a billing rule that is based on agreed-upon milestones</span></span>

<span data-ttu-id="e89b3-296">Sua organização, uma empresa de consultoria gerencial, aceita conduzir uma pesquisa de mercado para um produto de consumo que o cliente planeja vender.</span><span class="sxs-lookup"><span data-stu-id="e89b3-296">Your organization, a management consulting firm, agrees to conduct market research for a consumer product that the customer plans to sell.</span></span> <span data-ttu-id="e89b3-297">O cliente concorda em usar seus serviços por um período de três meses, iniciando em março e concorda em pagar à sua organização 50.000.</span><span class="sxs-lookup"><span data-stu-id="e89b3-297">The customer agrees to use your services for a period of three months, starting in March, and agrees to pay your organization 50,000.</span></span> <span data-ttu-id="e89b3-298">O projeto tem três etapas:</span><span class="sxs-lookup"><span data-stu-id="e89b3-298">The project has three milestones:</span></span>

-   <span data-ttu-id="e89b3-299">Etapa 1: coletar dados de consumo - 31 de março</span><span class="sxs-lookup"><span data-stu-id="e89b3-299">Milestone 1: Collect consumer data – March 31</span></span>
-   <span data-ttu-id="e89b3-300">Etapa 2: analisar os dados de consumo - 30 de abril</span><span class="sxs-lookup"><span data-stu-id="e89b3-300">Milestone 2: Analyze consumer data – April 30</span></span>
-   <span data-ttu-id="e89b3-301">Etapa 3: apresentar uma proposta de viabilidade do produto - 31 de maio</span><span class="sxs-lookup"><span data-stu-id="e89b3-301">Milestone 3: Present a product viability proposal – May 31</span></span>

<span data-ttu-id="e89b3-302">O cliente concorda em pagar à sua organização 10.000 pela primeira etapa, 20.000 pela segunda e 20.000 pela terceira.</span><span class="sxs-lookup"><span data-stu-id="e89b3-302">The customer agrees to pay your organization 10,000 for the first milestone, 20,000 for the second milestone, and 20,000 for the third milestone.</span></span> 

<span data-ttu-id="e89b3-303">Quando você configura o contrato de projeto, você concorda em cobrar o cliente com base na etapa concluída.</span><span class="sxs-lookup"><span data-stu-id="e89b3-303">When you set up the project contract, you agree to bill the customer based on the milestone that has been completed.</span></span> <span data-ttu-id="e89b3-304">A configuração da regra de cobrança inclui as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e89b3-304">The billing rule setup includes the following steps:</span></span>

-   <span data-ttu-id="e89b3-305">Defina as etapas do projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-305">Define the project milestones.</span></span>
-   <span data-ttu-id="e89b3-306">Defina o valor a ser faturado ao cliente quando cada etapa for concluída.</span><span class="sxs-lookup"><span data-stu-id="e89b3-306">Define the amount to invoice the customer when each milestone is completed.</span></span>

<span data-ttu-id="e89b3-307">Quando a primeira etapa for concluída em 31 de março, marque a etapa como concluída e, em seguida, crie uma fatura no valor de 10.000,00 para ser enviada ao cliente.</span><span class="sxs-lookup"><span data-stu-id="e89b3-307">When the first milestone is completed on March 31, you mark the milestone as completed, and then create an invoice for 10,000 and send it to the customer.</span></span> <span data-ttu-id="e89b3-308">Não é possível criar uma fatura para uma etapa até que você marque a etapa como concluída.</span><span class="sxs-lookup"><span data-stu-id="e89b3-308">You can’t create an invoice for a milestone until you have marked the milestone as completed.</span></span>

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a><span data-ttu-id="e89b3-309">Exemplo: Criar uma regra de cobrança com base nos serviços, mais uma taxa de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="e89b3-309">Example: Create a billing rule that is based on services plus a management fee</span></span>

<span data-ttu-id="e89b3-310">Sua organização, uma empresa de consultoria de gerenciamento, aceita conduzir uma pesquisa de mercado para avaliar a viabilidade de um produto que o cliente, uma empresa de varejo, está desenvolvendo.</span><span class="sxs-lookup"><span data-stu-id="e89b3-310">Your organization, a management consulting firm, agrees to conduct market research to evaluate the viability of a product that the customer, a retail company, is developing.</span></span> <span data-ttu-id="e89b3-311">Os termos do contrato especificam que você fornecerá os serviços de seus três principais consultores de gerenciamento, que irão conduzir a pesquisa com base em tempo e material.</span><span class="sxs-lookup"><span data-stu-id="e89b3-311">The terms of the agreement specify that you will provide the services of your top three management consultants, who will conduct the research on a time-and-materials basis.</span></span> <span data-ttu-id="e89b3-312">O cliente concorda em pagar 100 por hora mais uma taxa de gerenciamento de 10 por cento para as horas de consultoria que são cobradas no projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-312">The customer agrees to pay 100 per hour, plus a 10 percent management fee for the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="e89b3-313">Quando você configurar o contrato de projeto, crie uma regra de cobrança para adicionar uma taxa de gerenciamento de 10% às horas de consultoria cobradas no projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-313">When you set up the project contract, create a billing rule to add a 10 percent management fee to the consulting hours that are charged to the project.</span></span> 

<span data-ttu-id="e89b3-314">Quando você cria uma fatura para o cliente, uma taxa de gerenciamento de 10% é cobrada, mais o custo das horas de consultoria.</span><span class="sxs-lookup"><span data-stu-id="e89b3-314">When you create an invoice for the customer, the customer is billed a 10 percent management fee plus the cost of the consulting hours.</span></span> <span data-ttu-id="e89b3-315">Por exemplo, se os três consultores trabalharam um total de 200 horas no projeto, uma fatura será criada no valor de 22.000, usando o seguinte cálculo:</span><span class="sxs-lookup"><span data-stu-id="e89b3-315">For example, if the three consultants worked a total of 200 hours on the project, an invoice for 22,000 is created based on the following calculation:</span></span>

-   <span data-ttu-id="e89b3-316">200 horas à 100 por hora = 20.000</span><span class="sxs-lookup"><span data-stu-id="e89b3-316">200 hours at 100 per hour = 20,000</span></span>
-   <span data-ttu-id="e89b3-317">taxa de gerenciamento de 10 por cento = 2.000</span><span class="sxs-lookup"><span data-stu-id="e89b3-317">10 percent management fee = 2,000</span></span>
-   <span data-ttu-id="e89b3-318">Valor total da fatura = 22.000</span><span class="sxs-lookup"><span data-stu-id="e89b3-318">Total invoice amount = 22,000</span></span>

<span data-ttu-id="e89b3-319">Se as taxas forem passíveis de imposto a um cliente, e você selecionar um grupo de impostos sobre vendas no contrato de projeto, o grupo de impostos sobre vendas será inserido automaticamente em uma regra de cobrança para taxas.</span><span class="sxs-lookup"><span data-stu-id="e89b3-319">If fees are taxable to a customer, and you select a sales tax group in the project contract, the sales tax group is automatically entered in a billing rule for fees.</span></span>

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a><span data-ttu-id="e89b3-320">Exemplo: Criar uma regra de cobrança para o valor do tempo e de materiais</span><span class="sxs-lookup"><span data-stu-id="e89b3-320">Example: Create a billing rule for the value of time and materials</span></span>

<span data-ttu-id="e89b3-321">Sua organização, uma empresa de consultoria de software, concorda em fornecer cinco consultores técnicos para trabalhar em um projeto de desenvolvimento de software para um cliente pelos próximos seis meses.</span><span class="sxs-lookup"><span data-stu-id="e89b3-321">Your organization, a software consulting firm, agrees to provide five technical consultants to work on a software development project for a customer for the next six months.</span></span> <span data-ttu-id="e89b3-322">O cliente concorda em pagar 150 por cada hora de consultoria e o custo dos materiais de escritório.</span><span class="sxs-lookup"><span data-stu-id="e89b3-322">The customer agrees to pay 150 for each consulting hour, plus the cost of office supplies.</span></span> <span data-ttu-id="e89b3-323">Sua organização envia uma fatura para o cliente no final de cada mês.</span><span class="sxs-lookup"><span data-stu-id="e89b3-323">Your organization sends an invoice to the customer at the end of each month.</span></span> 

<span data-ttu-id="e89b3-324">Quando você configura o contrato de projeto, você concorda em cobrar o cliente mensalmente pelo tempo e material usados no projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-324">When you set up the project contract, you agree to bill the customer each month for time and materials on the project.</span></span> <span data-ttu-id="e89b3-325">Você cria uma regra de cobrança que inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="e89b3-325">You create a billing rule that includes the following information:</span></span>

-   <span data-ttu-id="e89b3-326">O período de contrato é de seis meses.</span><span class="sxs-lookup"><span data-stu-id="e89b3-326">The contract period is six months.</span></span>
-   <span data-ttu-id="e89b3-327">O tempo de consultoria é calculado a uma taxa de 150 por hora.</span><span class="sxs-lookup"><span data-stu-id="e89b3-327">Consulting time is calculated at a rate of 150 per hour.</span></span>
-   <span data-ttu-id="e89b3-328">Os materiais de escritório são faturados pelo custo e não devem exceder o valor de 10.000 para o projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-328">Office supplies are invoiced at cost, and the total cost for the project must not exceed 10,000.</span></span>
-   <span data-ttu-id="e89b3-329">Você cria uma fatura de cliente no final de cada mês do calendário durante o projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-329">You create a customer invoice at the end of each calendar month during the project.</span></span>

<span data-ttu-id="e89b3-330">Durante o primeiro mês, um total de 800 horas são registradas pelos consultores no projeto.</span><span class="sxs-lookup"><span data-stu-id="e89b3-330">During the first month, a total of 800 hours are recorded by the consultants on the project.</span></span> <span data-ttu-id="e89b3-331">O custo dos materiais de escritório cobrados no projeto é de 2.000.</span><span class="sxs-lookup"><span data-stu-id="e89b3-331">The cost of office supplies that are charged to the project is 2,000.</span></span> <span data-ttu-id="e89b3-332">Sendo assim, no final do mês, você cria uma fatura para 122.000, calculado como 800 horas a 150 por hora mais 2.000 para suprimentos de escritório.</span><span class="sxs-lookup"><span data-stu-id="e89b3-332">Therefore, at the end of the month, you create an invoice for 122,000, which is calculated as 800 hours at 150 per hour, plus 2,000 for office supplies.</span></span>


