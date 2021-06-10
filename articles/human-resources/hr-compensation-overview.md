---
title: Planos de remuneração
description: Os gerentes de remuneração e de benefícios que podem usar o gerenciamento de remuneração para manter e processar planos de compensação fixos e variáveis para os funcionários da organização.
author: andreabichsel
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b773b12b7eb3a8a59627d011f2469a98c5dde58a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058911"
---
# <a name="compensation-plans"></a><span data-ttu-id="3bbf4-103">Planos de remuneração</span><span class="sxs-lookup"><span data-stu-id="3bbf4-103">Compensation plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3bbf4-104">Os gerentes de remuneração e de benefícios que podem usar o gerenciamento de remuneração para manter e processar planos de compensação fixos e variáveis para os funcionários da organização.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-104">Compensation and Benefits Managers can use Compensation management to maintain and process fixed and variable compensation plans for the organization's employees.</span></span>

### <a name="introduction"></a><span data-ttu-id="3bbf4-105">Introdução</span><span class="sxs-lookup"><span data-stu-id="3bbf4-105">Introduction</span></span>

<span data-ttu-id="3bbf4-106">O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-106">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="3bbf4-107">Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-107">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="3bbf4-108">O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-108">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span> 

<span data-ttu-id="3bbf4-109">Os funcionários podem estar inscritos em um ou mais planos de ambos os tipos.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-109">Employees can be enrolled in one or more plans of both types.</span></span> <span data-ttu-id="3bbf4-110">Um funcionário deve atender aos requisitos a seguir para serem qualificados para a inscrição em um plano de remuneração:</span><span class="sxs-lookup"><span data-stu-id="3bbf4-110">An employee must meet the following requirements in order to be eligible for enrollment in a compensation plan:</span></span>
-   <span data-ttu-id="3bbf4-111">O funcionário deve ter uma atribuição de posição ativa.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-111">The employee must have an active position assignment.</span></span>
-   <span data-ttu-id="3bbf4-112">O funcionário deve atender aos critérios definidos pelas regras de qualificação para um plano de remuneração.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-112">The employee must meet the criteria that are defined by eligibility rules for a compensation plan.</span></span>

## <a name="compensation-setup"></a><span data-ttu-id="3bbf4-113">Configuração da remuneração</span><span class="sxs-lookup"><span data-stu-id="3bbf4-113">Compensation setup</span></span>
<span data-ttu-id="3bbf4-114">A tabela a seguir lista os componentes do processo de remuneração que podem integrais ao configurar os planos de remuneração de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-114">The following table lists components of the compensation process that can be integral in setting up your company's compensation plans.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="3bbf4-115">Componente</span><span class="sxs-lookup"><span data-stu-id="3bbf4-115">Component</span></span></th>
<th><span data-ttu-id="3bbf4-116">Mais informações...</span><span class="sxs-lookup"><span data-stu-id="3bbf4-116">More information…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3bbf4-117">Ações de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="3bbf4-117">Fixed compensation actions</span></span></td>
<td><span data-ttu-id="3bbf4-118">As ações de remuneração fixa têm duas finalidades:</span><span class="sxs-lookup"><span data-stu-id="3bbf4-118">Fixed compensation actions accomplish two purposes:</span></span>
<ul>
<li><span data-ttu-id="3bbf4-119">As ações podem especificar o tipo de informação que deve ser registrada quando a remuneração de um funcionário é alterada.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-119">Actions can specify the kind of information that must be recorded when an employee’s compensation changes.</span></span> <span data-ttu-id="3bbf4-120">Por exemplo, você pode exigir que o motivo para uma alteração, como uma promoção ou um rebaixamento, seja registrado.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-120">For example, you can require that the reason a change, such as a promotion or a demotion be recorded.</span></span></li>
<li><span data-ttu-id="3bbf4-121">Ações que podem garantir que o cálculo seja aplicado quando os planos de remuneração fixa são processados.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-121">Actions can ensure that a calculation is applied when fixed compensation plans are processed.</span></span>  <span data-ttu-id="3bbf4-122">Por exemplo, ações do tipo Capital próprio irão comparar o pagamento dos funcionários com o ponto de referência mínimo deles e garantirão que estejam recebendo pelo menos o mínimo.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-122">For example, actions of type Equity will compare the employees pay to the minimum reference point for the level on the employee&#39;s and ensure the employee is getting paid at least the minimum.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3bbf4-123">Níveis</span><span class="sxs-lookup"><span data-stu-id="3bbf4-123">Levels</span></span></td>
<td><span data-ttu-id="3bbf4-124">Os níveis são associados ao trabalho e às posições relacionadas a uma referência de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-124">Levels are associated with jobs and any positions that are related to a job reference.</span></span> <span data-ttu-id="3bbf4-125">Você pode criar níveis distintos para os três tipos de planos de remuneração: pontuação, faixa e etapa.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-125">You can create discrete levels for the three types of compensation plans: Grade, Band, and Step.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3bbf4-126">Matriz de utilização da faixa salarial</span><span class="sxs-lookup"><span data-stu-id="3bbf4-126">Range utilization matrix</span></span></td>
<td><span data-ttu-id="3bbf4-127">A matriz de utilização de faixa salarial ajuda você a fazer a transição de funcionários para o ponto de controle de suas funções.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-127">A range utilization matrix helps you transition employees to the control point for their jobs.</span></span> <span data-ttu-id="3bbf4-128">Você também pode usar a utilização da faixa salarial para controlar o capital próprio da taxa de pagamento da empresa sem considerar o desempenho individual de um funcionário ou o desempenho geral da empresa.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-128">You can also use range utilization to control pay rate equity in the company without regard to an individual employee&#39;s performance or the overall performance of the company.</span></span> <span data-ttu-id="3bbf4-129">Por exemplo, os funcionários que recebem salários mais baixos da faixa obtêm percentuais maiores de aumento que os funcionários que recebem salários maiores.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-129">For example, employees who are paid lower in their range get higher percentage increases than employees who are paid higher in the range.</span></span> <span data-ttu-id="3bbf4-130">Assim, você pode compensar as diferenças de capital próprio sistematicamente.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-130">In this manner, you can systematically offset equity differences.</span></span> <span data-ttu-id="3bbf4-131">A utilização da faixa salarial é calculada da seguinte maneira: (Taxa de pagamento fixo - mínimo da faixa) ÷ (máximo da faixa - mínimo da faixa).</span><span class="sxs-lookup"><span data-stu-id="3bbf4-131">The range utilization is calculated as follows: (Fixed Pay Rate - Range Minimum) ÷ (Range Maximum - Range Minimum).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3bbf4-132">Configurações de pontos de referência</span><span class="sxs-lookup"><span data-stu-id="3bbf4-132">Reference point setups</span></span></td>
<td><span data-ttu-id="3bbf4-133">A configuração do ponto de referência inclui um conjunto de pontos de referência que representam faixas de uma matriz.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-133">A reference point setup includes a set of reference points that represent ranges in a matrix.</span></span> <span data-ttu-id="3bbf4-134">Cada faixa pode ser associada a uma taxa de pagamento.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-134">Each range can be associated with a pay rate.</span></span> <span data-ttu-id="3bbf4-135">Por exemplo, os planos de classificação normalmente terão pontos de referência de mínimo, médio e máximo.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-135">For example, grade plans will often have reference points of Minimum, Midpoint, and Maximum.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3bbf4-136">Matriz de remuneração</span><span class="sxs-lookup"><span data-stu-id="3bbf4-136">Compensation matrix</span></span></td>
<td><span data-ttu-id="3bbf4-137">Uma matriz de remuneração consiste em um conjunto de pontos de referência e níveis usados para criar uma estrutura de remuneração.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-137">A compensation matrix is the set of reference points and levels that you use to create a compensation structure.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3bbf4-138">Estrutura de remuneração</span><span class="sxs-lookup"><span data-stu-id="3bbf4-138">Compensation structure</span></span></td>
<td><span data-ttu-id="3bbf4-139">Uma estrutura de remuneração é uma matriz de remuneração que tem taxas de pagamento associadas aos pontos de referência para cada nível.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-139">A compensation structure is a compensation matrix that has pay rates associated with the reference points for each level.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3bbf4-140">Regras de qualificação</span><span class="sxs-lookup"><span data-stu-id="3bbf4-140">Eligibility rules</span></span></td>
<td><span data-ttu-id="3bbf4-141">As regras de qualificação são usadas para identificar funcionários em tarefas específicas, funções, tipos de trabalho, departamentos, associações sindicais ou em regiões de remuneração cobertas por planos de remuneração específicos.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-141">Eligibility rules are used to identify employees in specific jobs, job functions, job types, departments, labor unions, or compensation regions that are covered by specific compensation plans.</span></span> <span data-ttu-id="3bbf4-142">Você deve criar regras de qualificação para planos de remuneração variável e fixa para inserir os funcionários no plano.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-142">You must create eligibility rules for both variable and fixed compensation plans in order to enroll employees in the plan.</span></span> <span data-ttu-id="3bbf4-143">Depois de ter especificado as regras de qualificação para um plano de remuneração, você pode definir os níveis que devem ser aplicados às funções cobertas pelo plano.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-143">After eligibility rules are specified for a compensation plan, you can define the levels that should apply to the jobs that are covered by the plan.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3bbf4-144">Frequências de pagamento</span><span class="sxs-lookup"><span data-stu-id="3bbf4-144">Pay frequencies</span></span></td>
<td><span data-ttu-id="3bbf4-145">As frequências de pagamento são usadas para definir o período de tempo durante o qual a remuneração é especificada.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-145">Pay frequencies are used to define the time period for which the compensation is specified.</span></span>  <span data-ttu-id="3bbf4-146">Por exemplo, a ajuda da frequência de pagamento ajuda você a compreender se o valor de remuneração é especificado como um salário anual versos taxa de pagamento por hora.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-146">For example, the pay frequency helps you understand if the compensation amount is specified as an annual salary versus an hourly pay rate.</span></span> <span data-ttu-id="3bbf4-147">As frequências de pagamento também são usadas para configurar fatores de conversão para converter valores de remuneração de frequências de pagamento por hora, mensal, semanal, quinzenal para uma frequência de pagamento anual.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-147">Pay frequencies are also used to set up conversion factors to convert compensation amounts from monthly, weekly, biweekly and hourly pay frequencies to an annual pay frequency.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3bbf4-148">Regiões de remuneração</span><span class="sxs-lookup"><span data-stu-id="3bbf4-148">Compensation regions</span></span></td>
<td><span data-ttu-id="3bbf4-149">As regiões de remuneração são usadas para especificar a remuneração do funcionário com base na localização do local de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-149">Compensation regions are used to specify employee compensation based on the location of the workplace.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3bbf4-150">Ponto de controle</span><span class="sxs-lookup"><span data-stu-id="3bbf4-150">Control point</span></span></td>
<td><span data-ttu-id="3bbf4-151">O ponto de controle define o que você considera ser a taxa de pagamento ideal para todos os funcionários em um nível de remuneração.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-151">The control point defines what you consider to be the ideal pay rate for all employees at a compensation level.</span></span> <span data-ttu-id="3bbf4-152">Para estruturas de plano graduais, os pontos de controle são, em geral, o ponto intermediário das faixas.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-152">For grade plan structures, control points are typically the midpoint of the ranges.</span></span> <span data-ttu-id="3bbf4-153">As estruturas de faixa raramente usam pontos de controle.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-153">Band structures rarely use control points.</span></span> <span data-ttu-id="3bbf4-154">Você pode especificar o ponto de controle para um plano de remuneração fixa no formulário Planos de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-154">You can specify the control point for a fixed compensation plan in the Fixed compensation plans form.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3bbf4-155">Funções de trabalho</span><span class="sxs-lookup"><span data-stu-id="3bbf4-155">Job functions</span></span></td>
<td><span data-ttu-id="3bbf4-156">As funções de trabalho são usadas para classificar e filtrar os planos de remuneração para trabalhos específicos.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-156">Job functions are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3bbf4-157">Tipos de trabalho</span><span class="sxs-lookup"><span data-stu-id="3bbf4-157">Job types</span></span></td>
<td><span data-ttu-id="3bbf4-158">Os tipos de trabalho são usados para classificar e filtrar os planos de remuneração para trabalhos específicos.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-158">Job types are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3bbf4-159">Tipos de remuneração variável</span><span class="sxs-lookup"><span data-stu-id="3bbf4-159">Variable compensation types</span></span></td>
<td><span data-ttu-id="3bbf4-160">Tipos de remuneração variáveis, como ações ou bônus em dinheiro, são aplicados em planos de remuneração variáveis.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-160">Variable compensation types, such as stock awards or cash award bonuses, are set up in variable compensation plans.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3bbf4-161">Grades de remuneração</span><span class="sxs-lookup"><span data-stu-id="3bbf4-161">Compensation grids</span></span></td>
<td><span data-ttu-id="3bbf4-162">As grades de remuneração contêm a estrutura de remuneração.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-162">Compensation grids contain the compensation structure.</span></span>  <span data-ttu-id="3bbf4-163">As grades de remuneração podem ser usadas por um ou mais planos de remuneração.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-163">Compensation grids can be used by one or more compensation plans.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3bbf4-164">Planos de desempenho</span><span class="sxs-lookup"><span data-stu-id="3bbf4-164">Performance plans</span></span></td>
<td><span data-ttu-id="3bbf4-165">Os planos de desempenho são usados para associar o desempenho a uma matriz de alocação, para que você possa usar o plano em uma estratégia de pagamento por desempenho.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-165">Performance plans are used to associate performance with an allocation matrix, so that you can use the plan in a pay-for-performance strategy.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3bbf4-166">Avaliações de desempenho</span><span class="sxs-lookup"><span data-stu-id="3bbf4-166">Performance ratings</span></span></td>
<td><span data-ttu-id="3bbf4-167">As avaliações de desempenho são usadas em planos de desempenho para determinar o valor de um prêmio por mérito ou por desempenho.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-167">Performance ratings are used in performance plans to determine the amount of a merit award or performance award.</span></span></td>
</tr>
</tbody>
</table>

## <a name="process-events"></a><span data-ttu-id="3bbf4-168">Eventos de processo</span><span class="sxs-lookup"><span data-stu-id="3bbf4-168">Process events</span></span>
<span data-ttu-id="3bbf4-169">Um evento de processo calcula as informações de remuneração de um determinado período para todos os funcionários que estão inscritos em um ou mais planos de remuneração fixa ou variável.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-169">A process event calculates compensation information for a specific period for all employees who are enrolled in one or more fixed or variable compensation plans.</span></span> <span data-ttu-id="3bbf4-170">Você pode executar um evento de processo repetidamente para testar ou atualizar os resultados de remuneração calculados.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-170">You can run a process event repeatedly to test or update calculated compensation results.</span></span>

<a name="compensation-events"></a><span data-ttu-id="3bbf4-171">Eventos de remuneração</span><span class="sxs-lookup"><span data-stu-id="3bbf4-171">Compensation events</span></span>
-------------------

<span data-ttu-id="3bbf4-172">Toda vez que um processo de evento é executado, um evento de remuneração é criado.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-172">Each time a process event is run, a compensation event is created.</span></span>  <span data-ttu-id="3bbf4-173">Quando os cálculos estão corretos, você pode carregar o evento de remuneração para atualizar os registros de remuneração para os funcionários afetados pelo evento de processo.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-173">Compensation events contain the results of the compensation process for each employee included in that process event.</span></span>  <span data-ttu-id="3bbf4-174">Quando os cálculos estão corretos, você pode carregar o evento de remuneração para atualizar os registros de remuneração para os funcionários afetados pelo evento de processo.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-174">When the calculations are correct, you can load the compensation event to update the compensation records for the employees who are affected by the process event.</span></span>

## <a name="recommendations"></a><span data-ttu-id="3bbf4-175">Recomendações</span><span class="sxs-lookup"><span data-stu-id="3bbf4-175">Recommendations</span></span>
<span data-ttu-id="3bbf4-176">Depois de executar um evento de processo, você pode recomendar ajustes no aumento de um funcionário por mérito ou no valor do prêmio, com base nas diretrizes calculadas do evento de processo.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-176">After you run a process event, you can recommend adjustments to an employee’s merit increase or award amount, based on the calculated guidelines of the process event.</span></span> <span data-ttu-id="3bbf4-177">Para fazer recomendações para funcionários, você deve habilitar as recomendações quando configurar planos de remuneração ou quando configurar o evento de processo.</span><span class="sxs-lookup"><span data-stu-id="3bbf4-177">To make recommendations for employees, you must enable recommendations when you set up compensation plans or when you set up the process event.</span></span>





[!INCLUDE[footer-include](../includes/footer-banner.md)]