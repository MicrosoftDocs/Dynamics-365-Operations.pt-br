---
title: Tabelas do Dataverse
description: O Microsoft Dynamics 365 Human Resources usa o Dataverse para habilitar cenários de integração e extensibilidade.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8ddb74a2f0b6265c5be3c13a009211455ea862da
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893391"
---
# <a name="dataverse-tables"></a><span data-ttu-id="08b4a-103">Tabelas do Dataverse</span><span class="sxs-lookup"><span data-stu-id="08b4a-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="08b4a-104">O Microsoft Dynamics 365 Human Resources usa o Dataverse para habilitar cenários de integração e extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="08b4a-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="08b4a-105">Entidades do Human Resources correspondem a tabelas do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="08b4a-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="08b4a-106">Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="08b4a-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="08b4a-107">As tabelas do Dataverse a seguir estão disponíveis com base em entidades do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="08b4a-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="08b4a-108">Tabelas de benefícios</span><span class="sxs-lookup"><span data-stu-id="08b4a-108">Benefit tables</span></span>

| <span data-ttu-id="08b4a-109">Nome</span><span class="sxs-lookup"><span data-stu-id="08b4a-109">Name</span></span> | <span data-ttu-id="08b4a-110">Tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="08b4a-111">Frequência de Cálculo do Benefício</span><span class="sxs-lookup"><span data-stu-id="08b4a-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="08b4a-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="08b4a-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="08b4a-113">Período de Pagamento da Frequência de Cálculo de Benefícios</span><span class="sxs-lookup"><span data-stu-id="08b4a-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="08b4a-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="08b4a-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="08b4a-115">Taxa de Cálculo de Benefícios</span><span class="sxs-lookup"><span data-stu-id="08b4a-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="08b4a-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="08b4a-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="08b4a-117">Detalhes da Taxa de Cálculo de Benefícios</span><span class="sxs-lookup"><span data-stu-id="08b4a-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="08b4a-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="08b4a-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="08b4a-119">Opção de Benefícios</span><span class="sxs-lookup"><span data-stu-id="08b4a-119">Benefit Option</span></span> | <span data-ttu-id="08b4a-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="08b4a-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="08b4a-121">Plano de Benefícios</span><span class="sxs-lookup"><span data-stu-id="08b4a-121">Benefit Plan</span></span> | <span data-ttu-id="08b4a-122">cdm_benefitplan (Não habilitado para suporte a campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="08b4a-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="08b4a-123">Tipo de Benefício</span><span class="sxs-lookup"><span data-stu-id="08b4a-123">Benefit Type</span></span> | <span data-ttu-id="08b4a-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="08b4a-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="08b4a-125">Tabelas de tarefas do processo empresarial</span><span class="sxs-lookup"><span data-stu-id="08b4a-125">Business process tasks tables</span></span>

| <span data-ttu-id="08b4a-126">Organização</span><span class="sxs-lookup"><span data-stu-id="08b4a-126">Name</span></span> | <span data-ttu-id="08b4a-127">Tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="08b4a-128">Calendário de Processo de Negócios</span><span class="sxs-lookup"><span data-stu-id="08b4a-128">Business Process Calendar</span></span> | <span data-ttu-id="08b4a-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="08b4a-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="08b4a-130">Atribuição de Grupo de Processos de Negócios</span><span class="sxs-lookup"><span data-stu-id="08b4a-130">Business Process Group Assignment</span></span> | <span data-ttu-id="08b4a-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="08b4a-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="08b4a-132">Grupo de Tarefas da Biblioteca de Processos de Negócios</span><span class="sxs-lookup"><span data-stu-id="08b4a-132">Business Process Library Task Group</span></span> | <span data-ttu-id="08b4a-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="08b4a-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="08b4a-134">Estágio do Processo de Negócios</span><span class="sxs-lookup"><span data-stu-id="08b4a-134">Business Process Stage</span></span> | <span data-ttu-id="08b4a-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="08b4a-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="08b4a-136">Cabeçalho do Modelo de Lista de Verificação</span><span class="sxs-lookup"><span data-stu-id="08b4a-136">Checklist Template Header</span></span> | <span data-ttu-id="08b4a-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="08b4a-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="08b4a-138">Tarefa do Modelo de Lista de Verificação</span><span class="sxs-lookup"><span data-stu-id="08b4a-138">Checklist Template Task</span></span> | <span data-ttu-id="08b4a-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="08b4a-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="08b4a-140">Tabelas de remuneração</span><span class="sxs-lookup"><span data-stu-id="08b4a-140">Compensation tables</span></span>

| <span data-ttu-id="08b4a-141">Organização</span><span class="sxs-lookup"><span data-stu-id="08b4a-141">Name</span></span> | <span data-ttu-id="08b4a-142">Tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="08b4a-143">Plano de Remuneração Fixa</span><span class="sxs-lookup"><span data-stu-id="08b4a-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="08b4a-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="08b4a-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="08b4a-145">Grade de Remuneração</span><span class="sxs-lookup"><span data-stu-id="08b4a-145">Compensation Grid</span></span> | <span data-ttu-id="08b4a-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="08b4a-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="08b4a-147">Nível de Remuneração</span><span class="sxs-lookup"><span data-stu-id="08b4a-147">Compensation Level</span></span> | <span data-ttu-id="08b4a-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="08b4a-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="08b4a-149">Frequência de Pagamento de Remuneração</span><span class="sxs-lookup"><span data-stu-id="08b4a-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="08b4a-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="08b4a-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="08b4a-151">Configuração de Ponto de Referência de Remuneração</span><span class="sxs-lookup"><span data-stu-id="08b4a-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="08b4a-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="08b4a-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="08b4a-153">Linha da Configuração de Ponto de Referência de Remuneração</span><span class="sxs-lookup"><span data-stu-id="08b4a-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="08b4a-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="08b4a-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="08b4a-155">Região de Remuneração</span><span class="sxs-lookup"><span data-stu-id="08b4a-155">Compensation Region</span></span> | <span data-ttu-id="08b4a-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="08b4a-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="08b4a-157">Estrutura de Remuneração</span><span class="sxs-lookup"><span data-stu-id="08b4a-157">Compensation Structure</span></span> | <span data-ttu-id="08b4a-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="08b4a-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="08b4a-159">Plano de Remuneração Variável</span><span class="sxs-lookup"><span data-stu-id="08b4a-159">Compensation Variable Plan</span></span> | <span data-ttu-id="08b4a-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="08b4a-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="08b4a-161">Nível do Plano de Remuneração Variável</span><span class="sxs-lookup"><span data-stu-id="08b4a-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="08b4a-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="08b4a-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="08b4a-163">Tipo de Plano de Remuneração Variável</span><span class="sxs-lookup"><span data-stu-id="08b4a-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="08b4a-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="08b4a-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="08b4a-165">Evento de Remuneração Fixa</span><span class="sxs-lookup"><span data-stu-id="08b4a-165">Fixed Compensation Event</span></span> | <span data-ttu-id="08b4a-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="08b4a-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="08b4a-167">Regra de Benefício Proporcional Diferido</span><span class="sxs-lookup"><span data-stu-id="08b4a-167">Vesting Rule</span></span> | <span data-ttu-id="08b4a-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="08b4a-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="08b4a-169">Remuneração Fixa do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="08b4a-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="08b4a-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="08b4a-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="08b4a-171">Tabelas da organização</span><span class="sxs-lookup"><span data-stu-id="08b4a-171">Organization tables</span></span>

| <span data-ttu-id="08b4a-172">Organização</span><span class="sxs-lookup"><span data-stu-id="08b4a-172">Name</span></span> | <span data-ttu-id="08b4a-173">Tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="08b4a-174">Departamento</span><span class="sxs-lookup"><span data-stu-id="08b4a-174">Department</span></span> | <span data-ttu-id="08b4a-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="08b4a-175">cdm_department</span></span> |
| <span data-ttu-id="08b4a-176">Emprego</span><span class="sxs-lookup"><span data-stu-id="08b4a-176">Employment</span></span> | <span data-ttu-id="08b4a-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="08b4a-177">cdm_employment</span></span> |
| <span data-ttu-id="08b4a-178">Empresa</span><span class="sxs-lookup"><span data-stu-id="08b4a-178">Company</span></span> | <span data-ttu-id="08b4a-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="08b4a-179">cdm_company</span></span> |
| <span data-ttu-id="08b4a-180">Cargo</span><span class="sxs-lookup"><span data-stu-id="08b4a-180">Job</span></span> | <span data-ttu-id="08b4a-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="08b4a-181">cdm_job</span></span> |
| <span data-ttu-id="08b4a-182">Função de Trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-182">Job Function</span></span> | <span data-ttu-id="08b4a-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="08b4a-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="08b4a-184">Posição de Trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-184">Job Position</span></span> | <span data-ttu-id="08b4a-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="08b4a-185">cdm_jobposition</span></span> |
| <span data-ttu-id="08b4a-186">Tipo de Posição</span><span class="sxs-lookup"><span data-stu-id="08b4a-186">Position Type</span></span> | <span data-ttu-id="08b4a-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="08b4a-187">cdm_positiontype</span></span> |
| <span data-ttu-id="08b4a-188">Atribuição do Trabalhador da Posição</span><span class="sxs-lookup"><span data-stu-id="08b4a-188">Position Worker Assignment</span></span> | <span data-ttu-id="08b4a-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="08b4a-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="08b4a-190">Dimensão da Posição de Trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-190">Job Position Dimension</span></span> | <span data-ttu-id="08b4a-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="08b4a-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="08b4a-192">Tipo de trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-192">Job Type</span></span> | <span data-ttu-id="08b4a-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="08b4a-193">cdm_jobtype</span></span> |
| <span data-ttu-id="08b4a-194">Idioma</span><span class="sxs-lookup"><span data-stu-id="08b4a-194">Language</span></span> | <span data-ttu-id="08b4a-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="08b4a-195">cdm_language</span></span> |
| <span data-ttu-id="08b4a-196">Cargo</span><span class="sxs-lookup"><span data-stu-id="08b4a-196">Title</span></span> | <span data-ttu-id="08b4a-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="08b4a-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="08b4a-198">As dimensões financeiras para **Tipo de posição**, **Atribuição do trabalhador da posição** e **Emprego** fornecem integração de uma direção a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="08b4a-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="08b4a-199">As atualizações de dimensões financeiras não são sincronizadas atualmente de Dataverse a Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="08b4a-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="08b4a-200">Tabelas de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="08b4a-200">Leave and absence tables</span></span>

| <span data-ttu-id="08b4a-201">Organização</span><span class="sxs-lookup"><span data-stu-id="08b4a-201">Name</span></span> | <span data-ttu-id="08b4a-202">Tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="08b4a-203">Transação Bancária de Licença</span><span class="sxs-lookup"><span data-stu-id="08b4a-203">Leave Bank Transaction</span></span> | <span data-ttu-id="08b4a-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="08b4a-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="08b4a-205">Inscrição para Licença</span><span class="sxs-lookup"><span data-stu-id="08b4a-205">Leave Enrollment</span></span> | <span data-ttu-id="08b4a-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="08b4a-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="08b4a-207">Plano de Licença</span><span class="sxs-lookup"><span data-stu-id="08b4a-207">Leave Plan</span></span> | <span data-ttu-id="08b4a-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="08b4a-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="08b4a-209">Solicitação de Licença</span><span class="sxs-lookup"><span data-stu-id="08b4a-209">Leave Request</span></span> | <span data-ttu-id="08b4a-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="08b4a-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="08b4a-211">Detalhes da Solicitação da Licença</span><span class="sxs-lookup"><span data-stu-id="08b4a-211">Leave Request Detail</span></span> | <span data-ttu-id="08b4a-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="08b4a-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="08b4a-213">Tipo de Licença</span><span class="sxs-lookup"><span data-stu-id="08b4a-213">Leave Type</span></span> | <span data-ttu-id="08b4a-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="08b4a-214">cdm_leavetype</span></span> |
| <span data-ttu-id="08b4a-215">Código de Motivo do Tipo de Licença</span><span class="sxs-lookup"><span data-stu-id="08b4a-215">Leave Type Reason Code</span></span> | <span data-ttu-id="08b4a-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="08b4a-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="08b4a-217">Tabelas de folha de pagamento</span><span class="sxs-lookup"><span data-stu-id="08b4a-217">Payroll tables</span></span>

| <span data-ttu-id="08b4a-218">Organização</span><span class="sxs-lookup"><span data-stu-id="08b4a-218">Name</span></span> | <span data-ttu-id="08b4a-219">Tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="08b4a-220">Ciclo de Pagamento</span><span class="sxs-lookup"><span data-stu-id="08b4a-220">Pay Cycle</span></span> | <span data-ttu-id="08b4a-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="08b4a-221">cdm_paycycle</span></span> |
| <span data-ttu-id="08b4a-222">Período de Pagamento</span><span class="sxs-lookup"><span data-stu-id="08b4a-222">Pay Period</span></span> | <span data-ttu-id="08b4a-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="08b4a-223">cdm_payperiod</span></span> |
| <span data-ttu-id="08b4a-224">Código de Ganhos de Folha de Pagamento</span><span class="sxs-lookup"><span data-stu-id="08b4a-224">Payroll Earning Code</span></span> | <span data-ttu-id="08b4a-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="08b4a-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="08b4a-226">Pagamento em Conta Bancária</span><span class="sxs-lookup"><span data-stu-id="08b4a-226">Bank Account Disbursement</span></span> | <span data-ttu-id="08b4a-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="08b4a-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="08b4a-228">Região Fiscal</span><span class="sxs-lookup"><span data-stu-id="08b4a-228">Tax Region</span></span> | <span data-ttu-id="08b4a-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="08b4a-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="08b4a-230">Tabelas de trabalhadores</span><span class="sxs-lookup"><span data-stu-id="08b4a-230">Worker tables</span></span>

| <span data-ttu-id="08b4a-231">Organização</span><span class="sxs-lookup"><span data-stu-id="08b4a-231">Name</span></span> | <span data-ttu-id="08b4a-232">Tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="08b4a-233">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="08b4a-233">Worker</span></span> | <span data-ttu-id="08b4a-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="08b4a-234">cdm_worker</span></span> |
| <span data-ttu-id="08b4a-235">Endereço do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="08b4a-235">Worker Address</span></span> | <span data-ttu-id="08b4a-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="08b4a-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="08b4a-237">Informações Pessoais do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="08b4a-237">Worker Personal Detail</span></span> | <span data-ttu-id="08b4a-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="08b4a-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="08b4a-239">Número de Identificação do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="08b4a-239">Worker Person Identification Number</span></span> | <span data-ttu-id="08b4a-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="08b4a-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="08b4a-241">Tipo de Identificação do Trabalhador</span><span class="sxs-lookup"><span data-stu-id="08b4a-241">Worker Person Identification Type</span></span> | <span data-ttu-id="08b4a-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="08b4a-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="08b4a-243">Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-243">Work Calendar</span></span> | <span data-ttu-id="08b4a-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="08b4a-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="08b4a-245">Dia do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-245">Work Calendar Day</span></span> | <span data-ttu-id="08b4a-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="08b4a-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="08b4a-247">Feriado do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-247">Work Calendar Holiday</span></span> |<span data-ttu-id="08b4a-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="08b4a-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="08b4a-249">Linha de Feriados do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="08b4a-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="08b4a-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="08b4a-251">Intervalo do Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="08b4a-252">cdm_workcalendartimeinterval (Não habilitado para suporte a campos personalizados)</span><span class="sxs-lookup"><span data-stu-id="08b4a-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="08b4a-253">Conta Bancária de Trabalhador</span><span class="sxs-lookup"><span data-stu-id="08b4a-253">Worker Bank Account</span></span> | <span data-ttu-id="08b4a-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="08b4a-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="08b4a-255">Tabelas de configuração de trabalhador</span><span class="sxs-lookup"><span data-stu-id="08b4a-255">Worker setup tables</span></span>

| <span data-ttu-id="08b4a-256">Nome</span><span class="sxs-lookup"><span data-stu-id="08b4a-256">Name</span></span> | <span data-ttu-id="08b4a-257">Tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="08b4a-258">Situação Militar</span><span class="sxs-lookup"><span data-stu-id="08b4a-258">Veteran Status</span></span> | <span data-ttu-id="08b4a-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="08b4a-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="08b4a-260">Origem Étnica</span><span class="sxs-lookup"><span data-stu-id="08b4a-260">Ethnic Origin</span></span> | <span data-ttu-id="08b4a-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="08b4a-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="08b4a-262">Código de Motivo</span><span class="sxs-lookup"><span data-stu-id="08b4a-262">Reason Code</span></span> | <span data-ttu-id="08b4a-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="08b4a-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="08b4a-264">Agência Emissora de Identificação Pessoal</span><span class="sxs-lookup"><span data-stu-id="08b4a-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="08b4a-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="08b4a-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="08b4a-266">Tabelas de competência</span><span class="sxs-lookup"><span data-stu-id="08b4a-266">Competency tables</span></span>

| <span data-ttu-id="08b4a-267">Nome</span><span class="sxs-lookup"><span data-stu-id="08b4a-267">Name</span></span> | <span data-ttu-id="08b4a-268">Tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="08b4a-269">Tipo de Habilidade</span><span class="sxs-lookup"><span data-stu-id="08b4a-269">Skill Type</span></span> | <span data-ttu-id="08b4a-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="08b4a-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="08b4a-271">Modelos de relacionamento de tabela</span><span class="sxs-lookup"><span data-stu-id="08b4a-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="08b4a-272">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="08b4a-272">Worker</span></span>

![Trabalhador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="08b4a-274">Trabalho e Cargo</span><span class="sxs-lookup"><span data-stu-id="08b4a-274">Job and Job Position</span></span>

![Trabalho e Cargo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="08b4a-276">Benefícios</span><span class="sxs-lookup"><span data-stu-id="08b4a-276">Benefits</span></span>

![Benefícios](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="08b4a-278">Remuneração</span><span class="sxs-lookup"><span data-stu-id="08b4a-278">Compensation</span></span>

![Remuneração](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="08b4a-280">Deixar</span><span class="sxs-lookup"><span data-stu-id="08b4a-280">Leave</span></span>

![Deixar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="08b4a-282">Calendário de Trabalho</span><span class="sxs-lookup"><span data-stu-id="08b4a-282">Work Calendar</span></span>

![Calendário de Trabalho](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="08b4a-284">Consulte também</span><span class="sxs-lookup"><span data-stu-id="08b4a-284">See also</span></span>

[<span data-ttu-id="08b4a-285">Escolher uma tecnologia de integração de dados</span><span class="sxs-lookup"><span data-stu-id="08b4a-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="08b4a-286">Configurar integração do Dataverse</span><span class="sxs-lookup"><span data-stu-id="08b4a-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="08b4a-287">Configurar tabelas virtuais do Dataverse</span><span class="sxs-lookup"><span data-stu-id="08b4a-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="08b4a-288">Perguntas frequentes de tabelas virtuais do Human Resources</span><span class="sxs-lookup"><span data-stu-id="08b4a-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="08b4a-289">O que é o Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="08b4a-289">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="08b4a-290">Atualizações de terminologia</span><span class="sxs-lookup"><span data-stu-id="08b4a-290">Terminology updates</span></span>](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]