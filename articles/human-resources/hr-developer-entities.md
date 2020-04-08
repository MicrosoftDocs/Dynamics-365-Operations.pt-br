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
ms.openlocfilehash: c8e0288da16829c04a9b97c0a52caa8bd27cddf8
ms.sourcegitcommit: fde8045ea49d0cf26d5e7ac5a0da5c0d3d69d5bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2020
ms.locfileid: "3166489"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="48fbf-103">Entidades do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="48fbf-103">Common Data Service entities</span></span>

<span data-ttu-id="48fbf-104">O Microsoft Dynamics 365 Human Resources usa o Common Data Service para habilitar cenários de integração e extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="48fbf-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="48fbf-105">Para obter mais informações sobre o Common Data Service, consulte [O que é o Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="48fbf-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="48fbf-106">As entidades a seguir do Human Resources estão disponíveis no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="48fbf-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="48fbf-107">Entidades de benefícios</span><span class="sxs-lookup"><span data-stu-id="48fbf-107">Benefit entities</span></span>

| <span data-ttu-id="48fbf-108">Nome</span><span class="sxs-lookup"><span data-stu-id="48fbf-108">Name</span></span> | <span data-ttu-id="48fbf-109">Entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="48fbf-110">Frequência de Cálculo do Benefício</span><span class="sxs-lookup"><span data-stu-id="48fbf-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="48fbf-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="48fbf-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="48fbf-112">Período de Pagamento da Frequência de Cálculo de Benefícios</span><span class="sxs-lookup"><span data-stu-id="48fbf-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="48fbf-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="48fbf-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="48fbf-114">Taxa de Cálculo de Benefícios</span><span class="sxs-lookup"><span data-stu-id="48fbf-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="48fbf-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="48fbf-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="48fbf-116">Detalhes da Taxa de Cálculo de Benefícios</span><span class="sxs-lookup"><span data-stu-id="48fbf-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="48fbf-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="48fbf-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="48fbf-118">Opção de Benefícios</span><span class="sxs-lookup"><span data-stu-id="48fbf-118">Benefit Option</span></span> | <span data-ttu-id="48fbf-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="48fbf-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="48fbf-120">Plano de Benefícios</span><span class="sxs-lookup"><span data-stu-id="48fbf-120">Benefit Plan</span></span> | <span data-ttu-id="48fbf-121">cdm_benefitplan (Não habilitado para suporte a campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="48fbf-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="48fbf-122">Tipo de Benefício</span><span class="sxs-lookup"><span data-stu-id="48fbf-122">Benefit Type</span></span> | <span data-ttu-id="48fbf-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="48fbf-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="48fbf-124">Entidades de tarefas do processo de negócios</span><span class="sxs-lookup"><span data-stu-id="48fbf-124">Business process tasks entities</span></span>

| <span data-ttu-id="48fbf-125">Nome</span><span class="sxs-lookup"><span data-stu-id="48fbf-125">Name</span></span> | <span data-ttu-id="48fbf-126">Entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="48fbf-127">Calendário de Processo de Negócios</span><span class="sxs-lookup"><span data-stu-id="48fbf-127">Business Process Calendar</span></span> | <span data-ttu-id="48fbf-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="48fbf-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="48fbf-129">Atribuição de Grupo de Processos de Negócios</span><span class="sxs-lookup"><span data-stu-id="48fbf-129">Business Process Group Assignment</span></span> | <span data-ttu-id="48fbf-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="48fbf-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="48fbf-131">Grupo de Tarefas da Biblioteca de Processos de Negócios</span><span class="sxs-lookup"><span data-stu-id="48fbf-131">Business Process Library Task Group</span></span> | <span data-ttu-id="48fbf-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="48fbf-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="48fbf-133">Estágio do Processo de Negócios</span><span class="sxs-lookup"><span data-stu-id="48fbf-133">Business Process Stage</span></span> | <span data-ttu-id="48fbf-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="48fbf-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="48fbf-135">Cabeçalho do Modelo de Lista de Verificação</span><span class="sxs-lookup"><span data-stu-id="48fbf-135">Checklist Template Header</span></span> | <span data-ttu-id="48fbf-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="48fbf-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="48fbf-137">Tarefa do Modelo de Lista de Verificação</span><span class="sxs-lookup"><span data-stu-id="48fbf-137">Checklist Template Task</span></span> | <span data-ttu-id="48fbf-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="48fbf-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="48fbf-139">Entidades de remuneração</span><span class="sxs-lookup"><span data-stu-id="48fbf-139">Compensation entities</span></span>

| <span data-ttu-id="48fbf-140">Nome</span><span class="sxs-lookup"><span data-stu-id="48fbf-140">Name</span></span> | <span data-ttu-id="48fbf-141">Entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="48fbf-142">Plano de Remuneração Fixa</span><span class="sxs-lookup"><span data-stu-id="48fbf-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="48fbf-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="48fbf-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="48fbf-144">Grade de Remuneração</span><span class="sxs-lookup"><span data-stu-id="48fbf-144">Compensation Grid</span></span> | <span data-ttu-id="48fbf-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="48fbf-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="48fbf-146">Nível de Remuneração</span><span class="sxs-lookup"><span data-stu-id="48fbf-146">Compensation Level</span></span> | <span data-ttu-id="48fbf-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="48fbf-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="48fbf-148">Frequência de Pagamento de Remuneração</span><span class="sxs-lookup"><span data-stu-id="48fbf-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="48fbf-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="48fbf-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="48fbf-150">Configuração de Ponto de Referência de Remuneração</span><span class="sxs-lookup"><span data-stu-id="48fbf-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="48fbf-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="48fbf-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="48fbf-152">Linha da Configuração de Ponto de Referência de Remuneração</span><span class="sxs-lookup"><span data-stu-id="48fbf-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="48fbf-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="48fbf-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="48fbf-154">Região de Remuneração</span><span class="sxs-lookup"><span data-stu-id="48fbf-154">Compensation Region</span></span> | <span data-ttu-id="48fbf-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="48fbf-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="48fbf-156">Estrutura de Remuneração</span><span class="sxs-lookup"><span data-stu-id="48fbf-156">Compensation Structure</span></span> | <span data-ttu-id="48fbf-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="48fbf-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="48fbf-158">Plano de Remuneração Variável</span><span class="sxs-lookup"><span data-stu-id="48fbf-158">Compensation Variable Plan</span></span> | <span data-ttu-id="48fbf-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="48fbf-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="48fbf-160">Nível do Plano de Remuneração Variável</span><span class="sxs-lookup"><span data-stu-id="48fbf-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="48fbf-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="48fbf-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="48fbf-162">Tipo de Plano de Remuneração Variável</span><span class="sxs-lookup"><span data-stu-id="48fbf-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="48fbf-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="48fbf-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="48fbf-164">Evento de Remuneração Fixa</span><span class="sxs-lookup"><span data-stu-id="48fbf-164">Fixed Compensation Event</span></span> | <span data-ttu-id="48fbf-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="48fbf-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="48fbf-166">Regra de Benefício Proporcional Diferido</span><span class="sxs-lookup"><span data-stu-id="48fbf-166">Vesting Rule</span></span> | <span data-ttu-id="48fbf-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="48fbf-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="48fbf-168">Remuneração Fixa do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="48fbf-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="48fbf-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="48fbf-170">Entidades da organização</span><span class="sxs-lookup"><span data-stu-id="48fbf-170">Organization entities</span></span>

| <span data-ttu-id="48fbf-171">Nome</span><span class="sxs-lookup"><span data-stu-id="48fbf-171">Name</span></span> | <span data-ttu-id="48fbf-172">Entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="48fbf-173">Departamento</span><span class="sxs-lookup"><span data-stu-id="48fbf-173">Department</span></span> | <span data-ttu-id="48fbf-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="48fbf-174">cdm_department</span></span> |
| <span data-ttu-id="48fbf-175">Emprego</span><span class="sxs-lookup"><span data-stu-id="48fbf-175">Employment</span></span> | <span data-ttu-id="48fbf-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="48fbf-176">cdm_employment</span></span> |
| <span data-ttu-id="48fbf-177">Empresa</span><span class="sxs-lookup"><span data-stu-id="48fbf-177">Company</span></span> | <span data-ttu-id="48fbf-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="48fbf-178">cdm_company</span></span> |
| <span data-ttu-id="48fbf-179">Cargo</span><span class="sxs-lookup"><span data-stu-id="48fbf-179">Job</span></span> | <span data-ttu-id="48fbf-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="48fbf-180">cdm_job</span></span> |
| <span data-ttu-id="48fbf-181">Função de Trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-181">Job Function</span></span> | <span data-ttu-id="48fbf-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="48fbf-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="48fbf-183">Posição de Trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-183">Job Position</span></span> | <span data-ttu-id="48fbf-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="48fbf-184">cdm_jobposition</span></span> |
| <span data-ttu-id="48fbf-185">Tipo de Posição</span><span class="sxs-lookup"><span data-stu-id="48fbf-185">Position Type</span></span> | <span data-ttu-id="48fbf-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="48fbf-186">cdm_positiontype</span></span> |
| <span data-ttu-id="48fbf-187">Atribuição do Trabalhador da Posição</span><span class="sxs-lookup"><span data-stu-id="48fbf-187">Position Worker Assignment</span></span> | <span data-ttu-id="48fbf-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="48fbf-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="48fbf-189">Dimensão da Posição de Trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-189">Job Position Dimension</span></span> | <span data-ttu-id="48fbf-190">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="48fbf-190">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="48fbf-191">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-191">Job Type</span></span> | <span data-ttu-id="48fbf-192">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="48fbf-192">cdm_jobtype</span></span> |
| <span data-ttu-id="48fbf-193">Idioma</span><span class="sxs-lookup"><span data-stu-id="48fbf-193">Language</span></span> | <span data-ttu-id="48fbf-194">cdm_language</span><span class="sxs-lookup"><span data-stu-id="48fbf-194">cdm_language</span></span> |
| <span data-ttu-id="48fbf-195">Cargo</span><span class="sxs-lookup"><span data-stu-id="48fbf-195">Title</span></span> | <span data-ttu-id="48fbf-196">cdm_title</span><span class="sxs-lookup"><span data-stu-id="48fbf-196">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="48fbf-197">As dimensões financeiras para **Tipo de posição**, **Atribuição do trabalhador da posição** e **Emprego** fornecem integração de uma direção a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="48fbf-197">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Common Data Service.</span></span> <span data-ttu-id="48fbf-198">As atualizações de dimensões financeiras não são sincronizadas atualmente de Common Data Service a Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="48fbf-198">Financial dimensions updates currently can't synchronize from Common Data Service to Human Resources.</span></span> 

## <a name="leave-and-absence-entities"></a><span data-ttu-id="48fbf-199">Entidades de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="48fbf-199">Leave and absence entities</span></span>

| <span data-ttu-id="48fbf-200">Nome</span><span class="sxs-lookup"><span data-stu-id="48fbf-200">Name</span></span> | <span data-ttu-id="48fbf-201">Entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-201">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="48fbf-202">Transação Bancária de Licença</span><span class="sxs-lookup"><span data-stu-id="48fbf-202">Leave Bank Transaction</span></span> | <span data-ttu-id="48fbf-203">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="48fbf-203">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="48fbf-204">Registro da Licença</span><span class="sxs-lookup"><span data-stu-id="48fbf-204">Leave Enrollment</span></span> | <span data-ttu-id="48fbf-205">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="48fbf-205">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="48fbf-206">Plano de Licença</span><span class="sxs-lookup"><span data-stu-id="48fbf-206">Leave Plan</span></span> | <span data-ttu-id="48fbf-207">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="48fbf-207">cdm_leaveplan</span></span> |
| <span data-ttu-id="48fbf-208">Solicitação de Licença</span><span class="sxs-lookup"><span data-stu-id="48fbf-208">Leave Request</span></span> | <span data-ttu-id="48fbf-209">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="48fbf-209">cdm_leaverequest</span></span> |
| <span data-ttu-id="48fbf-210">Detalhes da Solicitação da Licença</span><span class="sxs-lookup"><span data-stu-id="48fbf-210">Leave Request Detail</span></span> | <span data-ttu-id="48fbf-211">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="48fbf-211">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="48fbf-212">Tipo de Licença</span><span class="sxs-lookup"><span data-stu-id="48fbf-212">Leave Type</span></span> | <span data-ttu-id="48fbf-213">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="48fbf-213">cdm_leavetype</span></span> |
| <span data-ttu-id="48fbf-214">Código de Motivo do Tipo de Licença</span><span class="sxs-lookup"><span data-stu-id="48fbf-214">Leave Type Reason Code</span></span> | <span data-ttu-id="48fbf-215">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="48fbf-215">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="48fbf-216">Folha de pagamento das entidades</span><span class="sxs-lookup"><span data-stu-id="48fbf-216">Payroll entities</span></span>

| <span data-ttu-id="48fbf-217">Nome</span><span class="sxs-lookup"><span data-stu-id="48fbf-217">Name</span></span> | <span data-ttu-id="48fbf-218">Entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-218">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="48fbf-219">Ciclo de Pagamento</span><span class="sxs-lookup"><span data-stu-id="48fbf-219">Pay Cycle</span></span> | <span data-ttu-id="48fbf-220">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="48fbf-220">cdm_paycycle</span></span> |
| <span data-ttu-id="48fbf-221">Período de Pagamento</span><span class="sxs-lookup"><span data-stu-id="48fbf-221">Pay Period</span></span> | <span data-ttu-id="48fbf-222">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="48fbf-222">cdm_payperiod</span></span> |
| <span data-ttu-id="48fbf-223">Código de Ganhos da Folha de Pagamento</span><span class="sxs-lookup"><span data-stu-id="48fbf-223">Payroll Earning Code</span></span> | <span data-ttu-id="48fbf-224">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="48fbf-224">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="48fbf-225">Pagamento em Conta Bancária</span><span class="sxs-lookup"><span data-stu-id="48fbf-225">Bank Account Disbursement</span></span> | <span data-ttu-id="48fbf-226">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="48fbf-226">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="48fbf-227">Região Fiscal</span><span class="sxs-lookup"><span data-stu-id="48fbf-227">Tax Region</span></span> | <span data-ttu-id="48fbf-228">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="48fbf-228">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="48fbf-229">Entidades do trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-229">Worker entities</span></span>

| <span data-ttu-id="48fbf-230">Nome</span><span class="sxs-lookup"><span data-stu-id="48fbf-230">Name</span></span> | <span data-ttu-id="48fbf-231">Entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-231">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="48fbf-232">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-232">Worker</span></span> | <span data-ttu-id="48fbf-233">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="48fbf-233">cdm_worker</span></span> |
| <span data-ttu-id="48fbf-234">Endereço do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-234">Worker Address</span></span> | <span data-ttu-id="48fbf-235">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="48fbf-235">cdm_workeraddress</span></span> |
| <span data-ttu-id="48fbf-236">Informações Pessoais do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-236">Worker Personal Detail</span></span> | <span data-ttu-id="48fbf-237">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="48fbf-237">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="48fbf-238">Número de Identificação do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-238">Worker Person Identification Number</span></span> | <span data-ttu-id="48fbf-239">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="48fbf-239">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="48fbf-240">Tipo de Identificação do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-240">Worker Person Identification Type</span></span> | <span data-ttu-id="48fbf-241">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="48fbf-241">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="48fbf-242">Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-242">Work Calendar</span></span> | <span data-ttu-id="48fbf-243">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="48fbf-243">cdm_workcalendar</span></span> |
| <span data-ttu-id="48fbf-244">Dia do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-244">Work Calendar Day</span></span> | <span data-ttu-id="48fbf-245">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="48fbf-245">cdm_workcalendarday</span></span> |
| <span data-ttu-id="48fbf-246">Feriado do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-246">Work Calendar Holiday</span></span> |<span data-ttu-id="48fbf-247">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="48fbf-247">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="48fbf-248">Linha de Feriados do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-248">Work Calendar Holiday Line</span></span> | <span data-ttu-id="48fbf-249">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="48fbf-249">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="48fbf-250">Intervalo do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-250">Work Calendar Time Interval</span></span> | <span data-ttu-id="48fbf-251">cdm_workcalendartimeinterval (Não habilitado para suporte a campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="48fbf-251">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="48fbf-252">Conta Bancária do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-252">Worker Bank Account</span></span> | <span data-ttu-id="48fbf-253">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="48fbf-253">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="48fbf-254">Entidades de configuração do trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-254">Worker setup entities</span></span>

| <span data-ttu-id="48fbf-255">Nome</span><span class="sxs-lookup"><span data-stu-id="48fbf-255">Name</span></span> | <span data-ttu-id="48fbf-256">Entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-256">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="48fbf-257">Situação Militar</span><span class="sxs-lookup"><span data-stu-id="48fbf-257">Veteran Status</span></span> | <span data-ttu-id="48fbf-258">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="48fbf-258">cdm_veteranstatus</span></span> |
| <span data-ttu-id="48fbf-259">Origem Étnica</span><span class="sxs-lookup"><span data-stu-id="48fbf-259">Ethnic Origin</span></span> | <span data-ttu-id="48fbf-260">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="48fbf-260">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="48fbf-261">Código de Motivo</span><span class="sxs-lookup"><span data-stu-id="48fbf-261">Reason Code</span></span> | <span data-ttu-id="48fbf-262">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="48fbf-262">cdm_reasoncode</span></span> |
| <span data-ttu-id="48fbf-263">Agência Emissora da Identificação da Pessoa</span><span class="sxs-lookup"><span data-stu-id="48fbf-263">Person Identification Issuing Agency</span></span> | <span data-ttu-id="48fbf-264">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="48fbf-264">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="48fbf-265">Entidades de competência</span><span class="sxs-lookup"><span data-stu-id="48fbf-265">Competency entities</span></span>

| <span data-ttu-id="48fbf-266">Nome</span><span class="sxs-lookup"><span data-stu-id="48fbf-266">Name</span></span> | <span data-ttu-id="48fbf-267">Entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-267">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="48fbf-268">Tipo de Habilidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-268">Skill Type</span></span> | <span data-ttu-id="48fbf-269">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="48fbf-269">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="48fbf-270">Modelos do relacionamento de entidade</span><span class="sxs-lookup"><span data-stu-id="48fbf-270">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="48fbf-271">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="48fbf-271">Worker</span></span>

![Trabalhador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="48fbf-273">Trabalho e Cargo</span><span class="sxs-lookup"><span data-stu-id="48fbf-273">Job and Job Position</span></span>

![Trabalho e Cargo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="48fbf-275">Benefícios</span><span class="sxs-lookup"><span data-stu-id="48fbf-275">Benefits</span></span>

![Benefícios](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="48fbf-277">Remuneração</span><span class="sxs-lookup"><span data-stu-id="48fbf-277">Compensation</span></span>

![Remuneração](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="48fbf-279">Deixar</span><span class="sxs-lookup"><span data-stu-id="48fbf-279">Leave</span></span>

![Deixar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="48fbf-281">Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="48fbf-281">Work Calendar</span></span>

![Calendário de Trabalho](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="48fbf-283">Consulte também</span><span class="sxs-lookup"><span data-stu-id="48fbf-283">See also</span></span>

[<span data-ttu-id="48fbf-284">Escolher uma tecnologia de integração de dados</span><span class="sxs-lookup"><span data-stu-id="48fbf-284">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="48fbf-285">Configurar integração do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="48fbf-285">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)
