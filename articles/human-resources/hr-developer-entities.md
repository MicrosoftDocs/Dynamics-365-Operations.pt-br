---
title: Entidades do Common Data Service
description: O Microsoft Dynamics 365 Human Resources usa o Common Data Service para habilitar cenários de integração e extensibilidade.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6879a45dd1fcc1ba718747aaaf0d7936c2eac49f
ms.sourcegitcommit: 3cad15f8ecc257d3a45c1bc1fada7c094ff4bcec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087337"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="5df07-103">Entidades do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="5df07-103">Common Data Service entities</span></span>

<span data-ttu-id="5df07-104">O Microsoft Dynamics 365 Human Resources usa o Common Data Service para habilitar cenários de integração e extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="5df07-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="5df07-105">Para obter mais informações sobre o Common Data Service, consulte [O que é o Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="5df07-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="5df07-106">As entidades a seguir do Human Resources estão disponíveis no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5df07-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="5df07-107">Entidades de benefícios</span><span class="sxs-lookup"><span data-stu-id="5df07-107">Benefit entities</span></span>

| <span data-ttu-id="5df07-108">Nome</span><span class="sxs-lookup"><span data-stu-id="5df07-108">Name</span></span> | <span data-ttu-id="5df07-109">Entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="5df07-110">Frequência de Cálculo do Benefício</span><span class="sxs-lookup"><span data-stu-id="5df07-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="5df07-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="5df07-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="5df07-112">Período de Pagamento da Frequência de Cálculo de Benefícios</span><span class="sxs-lookup"><span data-stu-id="5df07-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="5df07-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="5df07-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="5df07-114">Taxa de Cálculo de Benefícios</span><span class="sxs-lookup"><span data-stu-id="5df07-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="5df07-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="5df07-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="5df07-116">Detalhes da Taxa de Cálculo de Benefícios</span><span class="sxs-lookup"><span data-stu-id="5df07-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="5df07-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="5df07-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="5df07-118">Opção de Benefícios</span><span class="sxs-lookup"><span data-stu-id="5df07-118">Benefit Option</span></span> | <span data-ttu-id="5df07-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="5df07-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="5df07-120">Plano de Benefícios</span><span class="sxs-lookup"><span data-stu-id="5df07-120">Benefit Plan</span></span> | <span data-ttu-id="5df07-121">cdm_benefitplan (Não habilitado para suporte a campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="5df07-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="5df07-122">Tipo de Benefício</span><span class="sxs-lookup"><span data-stu-id="5df07-122">Benefit Type</span></span> | <span data-ttu-id="5df07-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="5df07-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="5df07-124">Entidades de tarefas do processo de negócios</span><span class="sxs-lookup"><span data-stu-id="5df07-124">Business process tasks entities</span></span>

| <span data-ttu-id="5df07-125">Nome</span><span class="sxs-lookup"><span data-stu-id="5df07-125">Name</span></span> | <span data-ttu-id="5df07-126">Entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="5df07-127">Calendário de Processo de Negócios</span><span class="sxs-lookup"><span data-stu-id="5df07-127">Business Process Calendar</span></span> | <span data-ttu-id="5df07-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="5df07-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="5df07-129">Atribuição de Grupo de Processos de Negócios</span><span class="sxs-lookup"><span data-stu-id="5df07-129">Business Process Group Assignment</span></span> | <span data-ttu-id="5df07-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="5df07-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="5df07-131">Grupo de Tarefas da Biblioteca de Processos de Negócios</span><span class="sxs-lookup"><span data-stu-id="5df07-131">Business Process Library Task Group</span></span> | <span data-ttu-id="5df07-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="5df07-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="5df07-133">Estágio do Processo de Negócios</span><span class="sxs-lookup"><span data-stu-id="5df07-133">Business Process Stage</span></span> | <span data-ttu-id="5df07-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="5df07-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="5df07-135">Cabeçalho do Modelo de Lista de Verificação</span><span class="sxs-lookup"><span data-stu-id="5df07-135">Checklist Template Header</span></span> | <span data-ttu-id="5df07-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="5df07-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="5df07-137">Tarefa do Modelo de Lista de Verificação</span><span class="sxs-lookup"><span data-stu-id="5df07-137">Checklist Template Task</span></span> | <span data-ttu-id="5df07-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="5df07-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="5df07-139">Entidades de remuneração</span><span class="sxs-lookup"><span data-stu-id="5df07-139">Compensation entities</span></span>

| <span data-ttu-id="5df07-140">Nome</span><span class="sxs-lookup"><span data-stu-id="5df07-140">Name</span></span> | <span data-ttu-id="5df07-141">Entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="5df07-142">Plano de Remuneração Fixa</span><span class="sxs-lookup"><span data-stu-id="5df07-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="5df07-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="5df07-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="5df07-144">Grade de Remuneração</span><span class="sxs-lookup"><span data-stu-id="5df07-144">Compensation Grid</span></span> | <span data-ttu-id="5df07-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="5df07-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="5df07-146">Nível de Remuneração</span><span class="sxs-lookup"><span data-stu-id="5df07-146">Compensation Level</span></span> | <span data-ttu-id="5df07-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="5df07-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="5df07-148">Frequência de Pagamento de Remuneração</span><span class="sxs-lookup"><span data-stu-id="5df07-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="5df07-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="5df07-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="5df07-150">Configuração de Ponto de Referência de Remuneração</span><span class="sxs-lookup"><span data-stu-id="5df07-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="5df07-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="5df07-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="5df07-152">Linha da Configuração de Ponto de Referência de Remuneração</span><span class="sxs-lookup"><span data-stu-id="5df07-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="5df07-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="5df07-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="5df07-154">Região de Remuneração</span><span class="sxs-lookup"><span data-stu-id="5df07-154">Compensation Region</span></span> | <span data-ttu-id="5df07-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="5df07-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="5df07-156">Estrutura de Remuneração</span><span class="sxs-lookup"><span data-stu-id="5df07-156">Compensation Structure</span></span> | <span data-ttu-id="5df07-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="5df07-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="5df07-158">Plano de Remuneração Variável</span><span class="sxs-lookup"><span data-stu-id="5df07-158">Compensation Variable Plan</span></span> | <span data-ttu-id="5df07-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="5df07-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="5df07-160">Nível do Plano de Remuneração Variável</span><span class="sxs-lookup"><span data-stu-id="5df07-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="5df07-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="5df07-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="5df07-162">Tipo de Plano de Remuneração Variável</span><span class="sxs-lookup"><span data-stu-id="5df07-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="5df07-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="5df07-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="5df07-164">Evento de Remuneração Fixa</span><span class="sxs-lookup"><span data-stu-id="5df07-164">Fixed Compensation Event</span></span> | <span data-ttu-id="5df07-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="5df07-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="5df07-166">Regra de Benefício Proporcional Diferido</span><span class="sxs-lookup"><span data-stu-id="5df07-166">Vesting Rule</span></span> | <span data-ttu-id="5df07-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="5df07-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="5df07-168">Remuneração Fixa do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="5df07-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="5df07-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="5df07-170">Entidades da organização</span><span class="sxs-lookup"><span data-stu-id="5df07-170">Organization entities</span></span>

| <span data-ttu-id="5df07-171">Nome</span><span class="sxs-lookup"><span data-stu-id="5df07-171">Name</span></span> | <span data-ttu-id="5df07-172">Entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="5df07-173">Departamento</span><span class="sxs-lookup"><span data-stu-id="5df07-173">Department</span></span> | <span data-ttu-id="5df07-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="5df07-174">cdm_department</span></span> |
| <span data-ttu-id="5df07-175">Emprego</span><span class="sxs-lookup"><span data-stu-id="5df07-175">Employment</span></span> | <span data-ttu-id="5df07-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="5df07-176">cdm_employment</span></span> |
| <span data-ttu-id="5df07-177">Empresa</span><span class="sxs-lookup"><span data-stu-id="5df07-177">Company</span></span> | <span data-ttu-id="5df07-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="5df07-178">cdm_company</span></span> |
| <span data-ttu-id="5df07-179">Cargo</span><span class="sxs-lookup"><span data-stu-id="5df07-179">Job</span></span> | <span data-ttu-id="5df07-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="5df07-180">cdm_job</span></span> |
| <span data-ttu-id="5df07-181">Função de Trabalho</span><span class="sxs-lookup"><span data-stu-id="5df07-181">Job Function</span></span> | <span data-ttu-id="5df07-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="5df07-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="5df07-183">Posição de Trabalho</span><span class="sxs-lookup"><span data-stu-id="5df07-183">Job Position</span></span> | <span data-ttu-id="5df07-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="5df07-184">cdm_jobposition</span></span> |
| <span data-ttu-id="5df07-185">Tipo de Posição</span><span class="sxs-lookup"><span data-stu-id="5df07-185">Position Type</span></span> | <span data-ttu-id="5df07-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="5df07-186">cdm_positiontype</span></span> |
| <span data-ttu-id="5df07-187">Atribuição do Trabalhador da Posição</span><span class="sxs-lookup"><span data-stu-id="5df07-187">Position Worker Assignment</span></span> | <span data-ttu-id="5df07-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="5df07-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="5df07-189">Tipo de Trabalho</span><span class="sxs-lookup"><span data-stu-id="5df07-189">Job Type</span></span> | <span data-ttu-id="5df07-190">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="5df07-190">cdm_jobtype</span></span> |
| <span data-ttu-id="5df07-191">Idioma</span><span class="sxs-lookup"><span data-stu-id="5df07-191">Language</span></span> | <span data-ttu-id="5df07-192">cdm_language</span><span class="sxs-lookup"><span data-stu-id="5df07-192">cdm_language</span></span> |

## <a name="leave-and-absence-entities"></a><span data-ttu-id="5df07-193">Entidades de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="5df07-193">Leave and absence entities</span></span>

| <span data-ttu-id="5df07-194">Nome</span><span class="sxs-lookup"><span data-stu-id="5df07-194">Name</span></span> | <span data-ttu-id="5df07-195">Entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-195">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="5df07-196">Transação Bancária da Licença</span><span class="sxs-lookup"><span data-stu-id="5df07-196">Leave Bank Transaction</span></span> | <span data-ttu-id="5df07-197">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="5df07-197">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="5df07-198">Registro da Licença</span><span class="sxs-lookup"><span data-stu-id="5df07-198">Leave Enrollment</span></span> | <span data-ttu-id="5df07-199">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="5df07-199">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="5df07-200">Plano de Licença</span><span class="sxs-lookup"><span data-stu-id="5df07-200">Leave Plan</span></span> | <span data-ttu-id="5df07-201">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="5df07-201">cdm_leaveplan</span></span> |
| <span data-ttu-id="5df07-202">Solicitação de Licença</span><span class="sxs-lookup"><span data-stu-id="5df07-202">Leave Request</span></span> | <span data-ttu-id="5df07-203">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="5df07-203">cdm_leaverequest</span></span> |
| <span data-ttu-id="5df07-204">Detalhes da Solicitação da Licença</span><span class="sxs-lookup"><span data-stu-id="5df07-204">Leave Request Detail</span></span> | <span data-ttu-id="5df07-205">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="5df07-205">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="5df07-206">Tipo de Licença</span><span class="sxs-lookup"><span data-stu-id="5df07-206">Leave Type</span></span> | <span data-ttu-id="5df07-207">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="5df07-207">cdm_leavetype</span></span> |
| <span data-ttu-id="5df07-208">Código de Motivo do Tipo de Licença</span><span class="sxs-lookup"><span data-stu-id="5df07-208">Leave Type Reason Code</span></span> | <span data-ttu-id="5df07-209">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="5df07-209">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="5df07-210">Folha de pagamento das entidades</span><span class="sxs-lookup"><span data-stu-id="5df07-210">Payroll entities</span></span>

| <span data-ttu-id="5df07-211">Nome</span><span class="sxs-lookup"><span data-stu-id="5df07-211">Name</span></span> | <span data-ttu-id="5df07-212">Entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-212">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="5df07-213">Ciclo de Pagamento</span><span class="sxs-lookup"><span data-stu-id="5df07-213">Pay Cycle</span></span> | <span data-ttu-id="5df07-214">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="5df07-214">cdm_paycycle</span></span> |
| <span data-ttu-id="5df07-215">Período de Pagamento</span><span class="sxs-lookup"><span data-stu-id="5df07-215">Pay Period</span></span> | <span data-ttu-id="5df07-216">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="5df07-216">cdm_payperiod</span></span> |
| <span data-ttu-id="5df07-217">Código de Ganhos da Folha de Pagamento</span><span class="sxs-lookup"><span data-stu-id="5df07-217">Payroll Earning Code</span></span> | <span data-ttu-id="5df07-218">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="5df07-218">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="5df07-219">Pagamento em Conta Bancária</span><span class="sxs-lookup"><span data-stu-id="5df07-219">Bank Account Disbursement</span></span> | <span data-ttu-id="5df07-220">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="5df07-220">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="5df07-221">Região Fiscal</span><span class="sxs-lookup"><span data-stu-id="5df07-221">Tax Region</span></span> | <span data-ttu-id="5df07-222">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="5df07-222">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="5df07-223">Entidades do trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-223">Worker entities</span></span>

| <span data-ttu-id="5df07-224">Nome</span><span class="sxs-lookup"><span data-stu-id="5df07-224">Name</span></span> | <span data-ttu-id="5df07-225">Entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-225">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="5df07-226">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-226">Worker</span></span> | <span data-ttu-id="5df07-227">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="5df07-227">cdm_worker</span></span> |
| <span data-ttu-id="5df07-228">Endereço do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-228">Worker Address</span></span> | <span data-ttu-id="5df07-229">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="5df07-229">cdm_workeraddress</span></span> |
| <span data-ttu-id="5df07-230">Informações Pessoais do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-230">Worker Personal Detail</span></span> | <span data-ttu-id="5df07-231">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="5df07-231">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="5df07-232">Número de Identificação do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-232">Worker Person Identification Number</span></span> | <span data-ttu-id="5df07-233">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="5df07-233">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="5df07-234">Tipo de Identificação do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-234">Worker Person Identification Type</span></span> | <span data-ttu-id="5df07-235">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="5df07-235">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="5df07-236">Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="5df07-236">Work Calendar</span></span> | <span data-ttu-id="5df07-237">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="5df07-237">cdm_workcalendar</span></span> |
| <span data-ttu-id="5df07-238">Dia do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="5df07-238">Work Calendar Day</span></span> | <span data-ttu-id="5df07-239">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="5df07-239">cdm_workcalendarday</span></span> |
| <span data-ttu-id="5df07-240">Feriado do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="5df07-240">Work Calendar Holiday</span></span> |<span data-ttu-id="5df07-241">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="5df07-241">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="5df07-242">Linha de Feriados do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="5df07-242">Work Calendar Holiday Line</span></span> | <span data-ttu-id="5df07-243">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="5df07-243">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="5df07-244">Intervalo do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="5df07-244">Work Calendar Time Interval</span></span> | <span data-ttu-id="5df07-245">cdm_workcalendartimeinterval (Não habilitado para suporte a campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="5df07-245">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="5df07-246">Conta Bancária do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-246">Worker Bank Account</span></span> | <span data-ttu-id="5df07-247">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="5df07-247">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="5df07-248">Entidades de configuração do trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-248">Worker setup entities</span></span>

| <span data-ttu-id="5df07-249">Nome</span><span class="sxs-lookup"><span data-stu-id="5df07-249">Name</span></span> | <span data-ttu-id="5df07-250">Entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-250">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="5df07-251">Situação Militar</span><span class="sxs-lookup"><span data-stu-id="5df07-251">Veteran Status</span></span> | <span data-ttu-id="5df07-252">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="5df07-252">cdm_veteranstatus</span></span> |
| <span data-ttu-id="5df07-253">Origem Étnica</span><span class="sxs-lookup"><span data-stu-id="5df07-253">Ethnic Origin</span></span> | <span data-ttu-id="5df07-254">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="5df07-254">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="5df07-255">Código de Motivo</span><span class="sxs-lookup"><span data-stu-id="5df07-255">Reason Code</span></span> | <span data-ttu-id="5df07-256">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="5df07-256">cdm_reasoncode</span></span> |
| <span data-ttu-id="5df07-257">Agência Emissora da Identificação da Pessoa</span><span class="sxs-lookup"><span data-stu-id="5df07-257">Person Identification Issuing Agency</span></span> | <span data-ttu-id="5df07-258">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="5df07-258">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="5df07-259">Entidades de competência</span><span class="sxs-lookup"><span data-stu-id="5df07-259">Competency entities</span></span>

| <span data-ttu-id="5df07-260">Nome</span><span class="sxs-lookup"><span data-stu-id="5df07-260">Name</span></span> | <span data-ttu-id="5df07-261">Entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-261">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="5df07-262">Tipo de Habilidade</span><span class="sxs-lookup"><span data-stu-id="5df07-262">Skill Type</span></span> | <span data-ttu-id="5df07-263">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="5df07-263">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="5df07-264">Modelos do relacionamento de entidade</span><span class="sxs-lookup"><span data-stu-id="5df07-264">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="5df07-265">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="5df07-265">Worker</span></span>

![Trabalhador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="5df07-267">Trabalho e Cargo</span><span class="sxs-lookup"><span data-stu-id="5df07-267">Job and Job Position</span></span>

![Trabalho e Cargo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="5df07-269">Benefícios</span><span class="sxs-lookup"><span data-stu-id="5df07-269">Benefits</span></span>

![Benefícios](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="5df07-271">Remuneração</span><span class="sxs-lookup"><span data-stu-id="5df07-271">Compensation</span></span>

![Remuneração](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="5df07-273">Deixar</span><span class="sxs-lookup"><span data-stu-id="5df07-273">Leave</span></span>

![Deixar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="5df07-275">Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="5df07-275">Work Calendar</span></span>

![Calendário de Trabalho](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="5df07-277">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5df07-277">See also</span></span>

[<span data-ttu-id="5df07-278">Escolher uma tecnologia de integração de dados</span><span class="sxs-lookup"><span data-stu-id="5df07-278">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="5df07-279">Configurar integração do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="5df07-279">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)