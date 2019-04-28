---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (14 de dezembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c2d209cac52665053b664a93bfb6c35e171b0948
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/12/2019
ms.locfileid: "949842"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-14-2018"></a><span data-ttu-id="f14bc-103">Novidades ou alterações no Dynamics 365 for Talent Core HR (14 de dezembro de 2018)</span><span class="sxs-lookup"><span data-stu-id="f14bc-103">What's new or changed in Dynamics 365 for Talent Core HR (December 14, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f14bc-104">**Compilação 8.1.2085**</span><span class="sxs-lookup"><span data-stu-id="f14bc-104">**Build 8.1.2085**</span></span>

<span data-ttu-id="f14bc-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="f14bc-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="f14bc-106">Alterações</span><span class="sxs-lookup"><span data-stu-id="f14bc-106">Changes</span></span>

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a><span data-ttu-id="f14bc-107">EUA – suporte à ACA (Lei de Serviços de Saúde Acessíveis) para os formulários 1095-B e 1095-C do ano fiscal 2018</span><span class="sxs-lookup"><span data-stu-id="f14bc-107">US - ACA (Affordable Care Act) support for tax year 2018 1095-B and 1095-C forms</span></span>

<span data-ttu-id="f14bc-108">Todos os anos, os ALEs (Applicable Large Employers) devem fornecer aos funcionários em tempo integral um formulário 1095-C.</span><span class="sxs-lookup"><span data-stu-id="f14bc-108">Each year, Applicable Large Employers (ALEs) must provide each full-time employees with a 1095-C.</span></span> <span data-ttu-id="f14bc-109">Além disso, se o empregador fornece cobertura autossegurada, ele deverá fornecer o 1095-C (se for um ALE) e um 1095-B (se for um empregador pequeno) a um funcionário (em tempo integral ou em meio período), coberto por um dos planos de saúde oferecidos por ele.</span><span class="sxs-lookup"><span data-stu-id="f14bc-109">In addition, if the employer provides self-insured coverage they must provide the 1095-C (if they are an ALE) and a 1095-B (if they are a small employer) to any employee, full-time or part-time, covered under one of their offered health plans.</span></span> <span data-ttu-id="f14bc-110">Este recurso fornece formulários imprimíveis para o 1095-C e 1095-B.</span><span class="sxs-lookup"><span data-stu-id="f14bc-110">This feature provides printable forms for both the 1095-C and 1095-B.</span></span>

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a><span data-ttu-id="f14bc-111">Durante a importação, o campo SubmittedByPersonId na HcmPerfJournalEntity é ignorado</span><span class="sxs-lookup"><span data-stu-id="f14bc-111">During import SubmittedByPersonId field on HcmPerfJournalEntity is ignored</span></span>

<span data-ttu-id="f14bc-112">Ao importar/exportar entradas do diário de desempenho, o campo **Enviado por** é ignorado.</span><span class="sxs-lookup"><span data-stu-id="f14bc-112">When importing/exporting performance journal entries, the **Submitted by** field is ignored.</span></span> <span data-ttu-id="f14bc-113">Com esta alteração, o valor **importado/exportado** refletirá o valor na tabela durante a exportação. Ao importar, o sistema será atualizado com o valor fornecido no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="f14bc-113">With this change, the value **imported/exported** will reflect the value in the table during the export, when importing the system will be updated with the value supplied in the import file.</span></span>

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a><span data-ttu-id="f14bc-114">A guia Análise no espaço de trabalho "Licença e ausência" exibe o erro "OpenConnectionError" para funções administrativas fora do sistema</span><span class="sxs-lookup"><span data-stu-id="f14bc-114">Analytics tab on 'Leave and absence' workspace displays "OpenConnectionError" error for non-system Admin roles</span></span>

<span data-ttu-id="f14bc-115">Com esta atualização, nenhum erro será exibido quando a guia **Análise** for aberta no espaço de trabalho **Licença e ausência** .</span><span class="sxs-lookup"><span data-stu-id="f14bc-115">With this update, no errors will be issued when opening the **Analytics** tab on the **Leave and Absence** workspace.</span></span>

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="f14bc-116">Há falha na obtenção do nó principal no autoatendimento para funcionários e na busca detalhada de Hierarquia de posições a partir do bloco.</span><span class="sxs-lookup"><span data-stu-id="f14bc-116">Employee self-service, Position Hierarchy drill-down from tile fails to get parent node</span></span>

<span data-ttu-id="f14bc-117">Uma alteração foi feita para corrigir o erro "Falha ao obter o nó principal" quando a hierarquia de posições for personalizada para aparecer em um espaço de trabalho existente e uma posição for selecionada na hierarquia.</span><span class="sxs-lookup"><span data-stu-id="f14bc-117">A change has been made to correct the error "Getting the parent node failed" when the position hierarchy has been personalized to appear on an existing workspace and a position is selected in the hierarchy.</span></span>  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a><span data-ttu-id="f14bc-118">É necessário ser Administrador do sistema para ver a guia Folha de pagamento na página Posição</span><span class="sxs-lookup"><span data-stu-id="f14bc-118">Must be System Admin to see the Payroll tab in the Position page</span></span>

<span data-ttu-id="f14bc-119">Uma alteração foi feita para incluir os elementos de segurança corretos no privilégio existente: "Manter detalhes da folha de pagamento e da posição do trabalhador".</span><span class="sxs-lookup"><span data-stu-id="f14bc-119">A change has been made to include the correct security elements in the existing privilege: "Maintain payroll worker and position detail".</span></span> <span data-ttu-id="f14bc-120">Com esta alteração, por padrão, o Administrador da Folha de pagamento terá acesso aos campos da Folha de pagamento na página Posição.</span><span class="sxs-lookup"><span data-stu-id="f14bc-120">With this change, by default, the Payroll Administrator will have access to the Payroll fields on the Position page.</span></span>

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a><span data-ttu-id="f14bc-121">Erro ao enviar a avaliação de desempenho para o gerente e o espaço reservado %Reviews.PerfPeriod% é usado nas instruções de envio</span><span class="sxs-lookup"><span data-stu-id="f14bc-121">Error when submitting performance review to manager and the %Reviews.PerfPeriod% placeholder is used in the Submission instructions</span></span>

<span data-ttu-id="f14bc-122">Uma alteração foi feita que corrige o erro "Referência nula” ao usar o espaço reservado %Reviews.PerfPeriod% nas instruções de Envio.</span><span class="sxs-lookup"><span data-stu-id="f14bc-122">A change has been made that corrects the "Null Reference" error when using the %Reviews.PerfPeriod% placeholder in the Submission instructions.</span></span>

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a><span data-ttu-id="f14bc-123">O relatório de força de trabalho do Power BI mostra o erro quando a data de aniversário de tempo de serviço do trabalhador é dia 29 de fevereiro</span><span class="sxs-lookup"><span data-stu-id="f14bc-123">Workforce Power BI report shows error when worker seniority date is a leap day</span></span>

<span data-ttu-id="f14bc-124">Com esta alteração, o dia 29 de fevereiro agora tem suporte no Power BI.</span><span class="sxs-lookup"><span data-stu-id="f14bc-124">With this change, leap days are now supported in Power BI.</span></span>

### <a name="integration-between-core-hr-and-attract"></a><span data-ttu-id="f14bc-125">Integração entre o Core HR e o Attract</span><span class="sxs-lookup"><span data-stu-id="f14bc-125">Integration between Core HR and Attract</span></span>

<span data-ttu-id="f14bc-126">Uma alteração foi feita para atualizar a integração entre o Core HR e o Attract relacionada aos candidatos a serem contratados.</span><span class="sxs-lookup"><span data-stu-id="f14bc-126">A change has been made to update the integration between Core HR and Attract related to candidates to hire.</span></span> <span data-ttu-id="f14bc-127">Para que os candidatos a serem contratados fiquem visíveis no espaço de trabalho **Gerenciamento de Pessoal**, são utilizadas as seguintes entidades do Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="f14bc-127">For candidates to hire to be visible in the **Personnel Management** workspace, the following Common Data Service entities are used:</span></span>

<span data-ttu-id="f14bc-128">Solicitação de emprego</span><span class="sxs-lookup"><span data-stu-id="f14bc-128">Job Application</span></span>
- <span data-ttu-id="f14bc-129">A razão do status deve ser definida como Oferta Aceita</span><span class="sxs-lookup"><span data-stu-id="f14bc-129">Status Reason needs to be set to Offer Accepted</span></span>
-   <span data-ttu-id="f14bc-130">Fornece o Candidato e a Oportunidades de Emprego</span><span class="sxs-lookup"><span data-stu-id="f14bc-130">Provides Candidate and Job Opening</span></span>

<span data-ttu-id="f14bc-131">Candidato</span><span class="sxs-lookup"><span data-stu-id="f14bc-131">Candidate</span></span>
-   <span data-ttu-id="f14bc-132">Fornece as Informações do Candidato</span><span class="sxs-lookup"><span data-stu-id="f14bc-132">Provides Candidate information</span></span>

<span data-ttu-id="f14bc-133">Oportunidade de Emprego</span><span class="sxs-lookup"><span data-stu-id="f14bc-133">Job Opening</span></span>
-   <span data-ttu-id="f14bc-134">Fornece a ID da Oportunidade de Emprego e os Participantes da Oportunidades de Emprego</span><span class="sxs-lookup"><span data-stu-id="f14bc-134">Provides Job Opening ID and Job Opening Participants</span></span>

<span data-ttu-id="f14bc-135">Participantes da Oportunidade de Emprego</span><span class="sxs-lookup"><span data-stu-id="f14bc-135">Job Opening Participants</span></span>
-   <span data-ttu-id="f14bc-136">Fornece o Gerente de Contratação</span><span class="sxs-lookup"><span data-stu-id="f14bc-136">Provides Hiring Manager</span></span>

<span data-ttu-id="f14bc-137">Quando um candidato é adicionado ao Gerenciamento de Pessoal, o candidato agora pode ser ignorado usando uma nova opção disponível no cartão do candidato.</span><span class="sxs-lookup"><span data-stu-id="f14bc-137">When a candidate is added to Personnel Management, the candidate can now also be dismissed using a new option available on the candidate card.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="f14bc-138">Em breve</span><span class="sxs-lookup"><span data-stu-id="f14bc-138">Coming soon</span></span>

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a><span data-ttu-id="f14bc-139">Licença e ausência: saldos futuros de licença e de previsão de licença</span><span class="sxs-lookup"><span data-stu-id="f14bc-139">Leave and absence: Future leave and forecasting leave balances</span></span>

<span data-ttu-id="f14bc-140">Com as alterações que estão sendo feitas para permitir que funcionários prevejam folgas e solicitem futuras folgas sem afetar seus saldos atuais de folga, a forma como os saldos de folga são exibidos também está sendo alterada.</span><span class="sxs-lookup"><span data-stu-id="f14bc-140">With the changes being made to allow for employees to forecast time off and request future time off requests without impacting their current time off balances, the way the time off balances are displayed is also changing.</span></span> 

<span data-ttu-id="f14bc-141">O saldo disponível atualmente exibido é a quantidade de folgas disponíveis para solicitações, incluindo os acúmulos até hoje e todas as solicitações de licença aprovadas.</span><span class="sxs-lookup"><span data-stu-id="f14bc-141">The available balance currently displayed is the amount of time off available for requests including accruals through today and all approved leave requests to the end of time.</span></span> 

<span data-ttu-id="f14bc-142">Quando a possibilidade de previsão for liberada, o saldo exibido será alterado para ser o saldo atual de folga, incluindo os acúmulos até hoje e as solicitações até hoje.</span><span class="sxs-lookup"><span data-stu-id="f14bc-142">When the ability to forecast is released, the balance displayed changes to  be the current balance of time off including accruals through today and requests through today.</span></span> <span data-ttu-id="f14bc-143">Os funcionários e gerentes verão esses saldos atualizados no autoatendimento para funcionários e gerentes no cartão **Folga** e na janela **Saldos de folga**.</span><span class="sxs-lookup"><span data-stu-id="f14bc-143">Employees and managers will see these updated balances in employee and manager self-service on the **Time off** card and in the **Time off balances** window.</span></span> <span data-ttu-id="f14bc-144">Os gerentes de RH verão esses saldos atualizados no espaço de trabalho **Pessoas** e na janela **Planos de licença atribuídos** do funcionário.</span><span class="sxs-lookup"><span data-stu-id="f14bc-144">HR managers will see these updated balances in the **People** workspace and in the employee’s **Assigned leave plans** window.</span></span>

## <a name="known-issue"></a><span data-ttu-id="f14bc-145">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="f14bc-145">Known issue</span></span>

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a><span data-ttu-id="f14bc-146">Erros de mapeamento na integração com o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f14bc-146">Mapping errors in the integration with Finance and Operations</span></span>

<span data-ttu-id="f14bc-147">Os problemas a seguir foram identificados no modelo atual de integração do Talent com o Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f14bc-147">The following issues have been identified in the current template for integrating Talent with Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="f14bc-148">Um novo modelo será publicado em breve e aplicado a todos os novos projetos de integração que forem criados.</span><span class="sxs-lookup"><span data-stu-id="f14bc-148">A new template will be published soon and will be applied to all new integration projects that are created.</span></span> <span data-ttu-id="f14bc-149">Para projetos de integração existentes, os mapeamentos de tarefas podem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="f14bc-149">For existing integration projects, the task mappings can be updated.</span></span> <span data-ttu-id="f14bc-150">Consulte a tabela a seguir para os mapeamentos atualizados.</span><span class="sxs-lookup"><span data-stu-id="f14bc-150">Refer to the following table for updated mappings.</span></span> 

>[!NOTE]
> <span data-ttu-id="f14bc-151">A tarefa Posições de trabalho para Atribuição de Trabalho Pai às Posições não integra dados.</span><span class="sxs-lookup"><span data-stu-id="f14bc-151">The Job Positions to Positions Parent Job Assignment task does not integrate data.</span></span> <span data-ttu-id="f14bc-152">Este é um problema que está sendo investigado no momento.</span><span class="sxs-lookup"><span data-stu-id="f14bc-152">This is an issue that is currently being researched.</span></span> <span data-ttu-id="f14bc-153">Não há uma solução alternativa no mapeamento atual.</span><span class="sxs-lookup"><span data-stu-id="f14bc-153">There is no workaround in the current mapping.</span></span> 

<span data-ttu-id="f14bc-154">A tarefa Departamentos para a Unidade operacional necessita dos seguintes mapeamentos atualizados.</span><span class="sxs-lookup"><span data-stu-id="f14bc-154">The Departments to Operating unit task needs the following mappings updated.</span></span>

| <span data-ttu-id="f14bc-155">Campo de origem existente</span><span class="sxs-lookup"><span data-stu-id="f14bc-155">Existing source field</span></span>          | <span data-ttu-id="f14bc-156">Novo campo de origem</span><span class="sxs-lookup"><span data-stu-id="f14bc-156">New source field</span></span> |
| -------------------------------|------------------|
| <span data-ttu-id="f14bc-157">cdm_description (Descrição)</span><span class="sxs-lookup"><span data-stu-id="f14bc-157">cdm_description (Description)</span></span>  | <span data-ttu-id="f14bc-158">cdm_name (Nome)</span><span class="sxs-lookup"><span data-stu-id="f14bc-158">cdm_name (Name)</span></span>  |

<span data-ttu-id="f14bc-159">Também é necessário acrescentar um mapeamento adicional</span><span class="sxs-lookup"><span data-stu-id="f14bc-159">An additional mapping also needs to be added.</span></span> <span data-ttu-id="f14bc-160">Selecione o último campo **Nenhum** para adicionar o mapeamento a seguir.</span><span class="sxs-lookup"><span data-stu-id="f14bc-160">Select the last **None** field to add the following mapping.</span></span>

| <span data-ttu-id="f14bc-161">Campo de origem</span><span class="sxs-lookup"><span data-stu-id="f14bc-161">Source field</span></span>                   | <span data-ttu-id="f14bc-162">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="f14bc-162">Destination field</span></span>    |
| -------------------------------|----------------------|
| <span data-ttu-id="f14bc-163">cdm_description (Descrição)</span><span class="sxs-lookup"><span data-stu-id="f14bc-163">cdm_description (Description)</span></span>  | <span data-ttu-id="f14bc-164">NAMEALIAS (NAMEALIAS)</span><span class="sxs-lookup"><span data-stu-id="f14bc-164">NAMEALIAS (NAMEALIAS)</span></span>|

<span data-ttu-id="f14bc-165">Os mapeamentos atualizados devem ser semelhantes à imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="f14bc-165">The updated mappings should look like the following image.</span></span>

![Tarefa Departamentos para a Unidade operacional](./media/DepartmentMapping.png)


<span data-ttu-id="f14bc-167">A tarefa Trabalhos para Detalhes do Trabalho necessita dos seguintes mapeamentos atualizados.</span><span class="sxs-lookup"><span data-stu-id="f14bc-167">The Jobs to Job Detail task needs the following mappings updated.</span></span>

| <span data-ttu-id="f14bc-168">Campo de origem existente</span><span class="sxs-lookup"><span data-stu-id="f14bc-168">Existing source field</span></span>          | <span data-ttu-id="f14bc-169">Novo campo de origem</span><span class="sxs-lookup"><span data-stu-id="f14bc-169">New source field</span></span>                   |
| -------------------------------|------------------------------------|
| <span data-ttu-id="f14bc-170">cdm_name (Nome)</span><span class="sxs-lookup"><span data-stu-id="f14bc-170">cdm_name (Name)</span></span>                | <span data-ttu-id="f14bc-171">cdm_description (Descrição)</span><span class="sxs-lookup"><span data-stu-id="f14bc-171">cdm_description (Description)</span></span>      |
| <span data-ttu-id="f14bc-172">cdm_name (Descrição)</span><span class="sxs-lookup"><span data-stu-id="f14bc-172">cdm_name (Description)</span></span>         | <span data-ttu-id="f14bc-173">cdm_jobdescription(Descrição do trabalho)</span><span class="sxs-lookup"><span data-stu-id="f14bc-173">cdm_jobdescription(Job Description)</span></span>|


<span data-ttu-id="f14bc-174">Os mapeamentos atualizados devem ser semelhantes à imagem abaixo.</span><span class="sxs-lookup"><span data-stu-id="f14bc-174">The updated mappings should look like the image below.</span></span>

![Trabalhos para Detalhes do Trabalho](./media/JobMapping.png)

<span data-ttu-id="f14bc-176">A tarefa Trabalhadores para o Trabalho necessita dos seguintes mapeamentos atualizados.</span><span class="sxs-lookup"><span data-stu-id="f14bc-176">The Workers to Work task needs the following mappings updated.</span></span>

| <span data-ttu-id="f14bc-177">Campo de origem existente</span><span class="sxs-lookup"><span data-stu-id="f14bc-177">Existing source field</span></span>                 | <span data-ttu-id="f14bc-178">Novo campo de origem</span><span class="sxs-lookup"><span data-stu-id="f14bc-178">New source field</span></span>                               |
| --------------------------------------|------------------------------------------------|
| <span data-ttu-id="f14bc-179">cdm_emailaddress1 (Endereço de email 1)</span><span class="sxs-lookup"><span data-stu-id="f14bc-179">cdm_emailaddress1 (Email Address 1)</span></span>   | <span data-ttu-id="f14bc-180">cdm_primaryemailaddress (Endereço de email principal)</span><span class="sxs-lookup"><span data-stu-id="f14bc-180">cdm_primaryemailaddress (Primary Email Address</span></span> |
| <span data-ttu-id="f14bc-181">cdm_telephone1 (Telefone 1)</span><span class="sxs-lookup"><span data-stu-id="f14bc-181">cdm_telephone1 (Telephone 1)</span></span>          | <span data-ttu-id="f14bc-182">cdm_primarytelephone (Telefone principal)</span><span class="sxs-lookup"><span data-stu-id="f14bc-182">cdm_primarytelephone (Primary Telephone)</span></span>       |

<span data-ttu-id="f14bc-183">A transformação do campo Sexo também deve ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="f14bc-183">The Gender field transform also needs to be updated.</span></span> <span data-ttu-id="f14bc-184">Selecione o tipo de mapa **fn** (função) para o Sexo e atualize os seguintes mapeamentos de valor.</span><span class="sxs-lookup"><span data-stu-id="f14bc-184">Select the **fn** (function) map type for Gender and update the following value mappings.</span></span>

| <span data-ttu-id="f14bc-185">Valor do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="f14bc-185">Common Data Service value</span></span>                   | <span data-ttu-id="f14bc-186">Valor do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f14bc-186">Finance and Operations value</span></span>                     |
| ----------------------------|--------------------------------------------------|
| <span data-ttu-id="f14bc-187">75440000</span><span class="sxs-lookup"><span data-stu-id="f14bc-187">75440000</span></span>                    | <span data-ttu-id="f14bc-188">Masculino</span><span class="sxs-lookup"><span data-stu-id="f14bc-188">Male</span></span>                                             |
| <span data-ttu-id="f14bc-189">75440001</span><span class="sxs-lookup"><span data-stu-id="f14bc-189">75440001</span></span>                    | <span data-ttu-id="f14bc-190">Feminino</span><span class="sxs-lookup"><span data-stu-id="f14bc-190">Female</span></span>                                           |
| <span data-ttu-id="f14bc-191">75440002</span><span class="sxs-lookup"><span data-stu-id="f14bc-191">75440002</span></span>                    | <span data-ttu-id="f14bc-192">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f14bc-192">None</span></span>                                             | 
| <span data-ttu-id="f14bc-193">75440003</span><span class="sxs-lookup"><span data-stu-id="f14bc-193">75440003</span></span>                    | <span data-ttu-id="f14bc-194">Não especificado</span><span class="sxs-lookup"><span data-stu-id="f14bc-194">NonSpecific</span></span>                                      |

<span data-ttu-id="f14bc-195">Os mapeamentos atualizados devem ser semelhantes às imagens a seguir.</span><span class="sxs-lookup"><span data-stu-id="f14bc-195">The updated mappings should look like the following images.</span></span>

![Tarefa Trabalhadores para o Trabalho](./media/WorkerMapping.png)

![Transformação do campo Sexo](./media/WorkerTransform.png)
