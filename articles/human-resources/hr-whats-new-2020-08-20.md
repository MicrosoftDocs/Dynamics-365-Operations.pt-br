---
title: Novidades ou alterações no Dynamics 365 Human Resources (20 de agosto 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 20 de agosto de 2020.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 95ffe90795b9781408607257f3f63bf68c489b56
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891808"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a><span data-ttu-id="45232-103">Novidades ou alterações no Dynamics 365 Human Resources (20 de agosto 2020)</span><span class="sxs-lookup"><span data-stu-id="45232-103">What's new or changed in Dynamics 365 Human Resources (August 20, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="45232-104">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="45232-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="45232-105">As alterações se aplicam ao número da compilação 8.1.3478.</span><span class="sxs-lookup"><span data-stu-id="45232-105">Changes apply to build number 8.1.3478.</span></span> <span data-ttu-id="45232-106">Os números entre parênteses em alguns cabeçalhos referem-se aos números de suporte do Lifecycle Services (LCS) para referência.</span><span class="sxs-lookup"><span data-stu-id="45232-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a><span data-ttu-id="45232-107">Mostrar informações de licença futura e pendente para cartões no espaço de trabalho Pessoas</span><span class="sxs-lookup"><span data-stu-id="45232-107">Show upcoming and pending leave of absence information to cards in People workspace</span></span>

<span data-ttu-id="45232-108">As opções de solicitação de licença pendentes e futuras agora estão disponíveis nos cartões de licença e ausência no espaço de trabalho **Pessoas**.</span><span class="sxs-lookup"><span data-stu-id="45232-108">Pending and upcoming leave request options are now available on the Leave and absence cards in the **People** workspace.</span></span>

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a><span data-ttu-id="45232-109">O campo particular não é Sim por padrão para a função Funcionário no Autoatendimento para funcionários (477106)</span><span class="sxs-lookup"><span data-stu-id="45232-109">Private field isn't Yes by default for Employee role in Employee self service (477106)</span></span>

<span data-ttu-id="45232-110">O campo **Privado** agora é padronizado como **Sim** quando os funcionários adicionam novos registros de endereço usando a página **Informações pessoais** no Autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="45232-110">The **Private** field now defaults to **Yes** when employees add new address records through the **Personal information** page in Employee self service.</span></span> 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a><span data-ttu-id="45232-111">A guia rápida Candidatos a serem contratados no Gerenciamento de pessoal mostra uma contagem incorreta de candidatos (470110)</span><span class="sxs-lookup"><span data-stu-id="45232-111">Candidates to hire FastTab in Personnel management shows an incorrect count of candidates (470110)</span></span>

<span data-ttu-id="45232-112">A página **Gerenciamento de pessoal** agora exibe com precisão o número de candidatos a serem contratados.</span><span class="sxs-lookup"><span data-stu-id="45232-112">The **Personnel management** page now accurately displays the number of candidates to hire.</span></span> 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a><span data-ttu-id="45232-113">Não é possível inserir doença para funcionário demitido quando a competência estiver definida como zero (446195)</span><span class="sxs-lookup"><span data-stu-id="45232-113">Can’t enter sickness for terminated employee when accrual is set to zero (446195)</span></span>

<span data-ttu-id="45232-114">As transações de licença agora são permitidas no futuro para funcionários que foram demitidos e a acumulação é definida como zero.</span><span class="sxs-lookup"><span data-stu-id="45232-114">Leave transactions are now allowed for employees that have been terminated in the future and the accrual is set to zero.</span></span> <span data-ttu-id="45232-115">As transações de licença podem ser inseridas até a data de demissão do funcionário.</span><span class="sxs-lookup"><span data-stu-id="45232-115">Leave transactions can be entered up to the termination date of the employee.</span></span> 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a><span data-ttu-id="45232-116">A adição de campos personalizados ao formulário do novo trabalhador desativa os campos no painel de ação para Gerenciar licença (473314)</span><span class="sxs-lookup"><span data-stu-id="45232-116">Adding custom fields to the new Worker form disables the fields in the action pane for Manage leave (473314)</span></span>

<span data-ttu-id="45232-117">As opções do painel de ação no novo formulário do **Trabalhador** em **Gerenciar licença** não será desativada se os campos personalizados forem adicionados ao formulário do novo **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="45232-117">Action pane options on the new **Worker** form in **Manage leave** will no longer be disabled if custom fields have been added to the new **Worker** form.</span></span>

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a><span data-ttu-id="45232-118">Tornar o campo de comentário da Licença obrigatório permite que uma solicitação de licença seja enviada quando nenhum comentário for inserido (473543)</span><span class="sxs-lookup"><span data-stu-id="45232-118">Making the Leave comment field mandatory allows a leave request to be submitted when no comment is entered (473543)</span></span>

<span data-ttu-id="45232-119">Os campos de comentário agora podem ser obrigatórios e as solicitações de licença honram essa configuração.</span><span class="sxs-lookup"><span data-stu-id="45232-119">Comment fields can now be mandatory, and leave requests honor this setting.</span></span> <span data-ttu-id="45232-120">Os campos obrigatórios são um recurso de visualização.</span><span class="sxs-lookup"><span data-stu-id="45232-120">Mandatory fields is a preview feature.</span></span>

### <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="45232-121">Entidade DMF disponível para suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="45232-121">DMF entity available for accrual suspensions</span></span>

<span data-ttu-id="45232-122">Uma entidade DMF disponível para suspensões de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="45232-122">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="in-preview"></a><span data-ttu-id="45232-123">Em visualização</span><span class="sxs-lookup"><span data-stu-id="45232-123">In preview</span></span>

### <a name="mandatory-fields"></a><span data-ttu-id="45232-124">Campos obrigatórios</span><span class="sxs-lookup"><span data-stu-id="45232-124">Mandatory fields</span></span>

<span data-ttu-id="45232-125">Você pode tornar campos obrigatórios usando recursos de personalização de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="45232-125">You can make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="45232-126">Este recurso exige **Exibições salvas**.</span><span class="sxs-lookup"><span data-stu-id="45232-126">This feature requires **Saved views**.</span></span> <span data-ttu-id="45232-127">Para obter mais informações sobre exibições salvas, consulte:</span><span class="sxs-lookup"><span data-stu-id="45232-127">For more information about saved views, see:</span></span>

- <span data-ttu-id="45232-128">[Exibições salvas - disponibilidade geral](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) no plano do Dynamics 365 versão 2020 onda 2</span><span class="sxs-lookup"><span data-stu-id="45232-128">[Saved views - general availability](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) in the Dynamics 365 2020 release wave 2 plan</span></span>
- [<span data-ttu-id="45232-129">Criar formulários que utilizam totalmente as exibições salvas</span><span class="sxs-lookup"><span data-stu-id="45232-129">Build forms that fully utilize saved views</span></span>](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a><span data-ttu-id="45232-130">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="45232-130">Human Resources application in Teams</span></span>

<span data-ttu-id="45232-131">Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="45232-131">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="45232-132">Eles podem interagir com um bot para criar solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="45232-132">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="45232-133">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="45232-133">For more information, see:</span></span>

- <span data-ttu-id="45232-134">[Licença e ausência do funcionário no Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) no plano do Dynamics 365 versão 2020 onda 1</span><span class="sxs-lookup"><span data-stu-id="45232-134">[Employee leave and absence experience in Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 1 plan</span></span>
- [<span data-ttu-id="45232-135">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="45232-135">Human Resources app in Teams</span></span>](./hr-admin-teams-leave-app.md)

## <a name="coming-soon"></a><span data-ttu-id="45232-136">Em breve</span><span class="sxs-lookup"><span data-stu-id="45232-136">Coming soon</span></span>

### <a name="human-resources-app-in-teams-preview-features"></a><span data-ttu-id="45232-137">Aplicativo Recursos Humanos nos recursos de visualização do Teams</span><span class="sxs-lookup"><span data-stu-id="45232-137">Human Resources app in Teams preview features</span></span>
 
-  <span data-ttu-id="45232-138">**Notificações**: os remetentes e aprovadores de solicitações de folga serão notificados no aplicativo de Recursos Humanos no Teams.</span><span class="sxs-lookup"><span data-stu-id="45232-138">**Notifications**: Submitters and approvers of time-off requests will be notified in the Human Resources app in Teams.</span></span> <span data-ttu-id="45232-139">Os aprovadores poderão aprovar ou negar solicitações de folga, e os remetentes serão notificados, caso a solicitação tenha sido aprovada ou negada.</span><span class="sxs-lookup"><span data-stu-id="45232-139">Approvers will be able to approve or deny time-off requests, and submitters will be notified if the request was approved or denied.</span></span>
 
- <span data-ttu-id="45232-140">**Calendário de folga do gerente**: Os gerentes poderão ver o tempo de folga aprovado e pendente para seus subordinados direto em um modo de exibição de calendário.</span><span class="sxs-lookup"><span data-stu-id="45232-140">**Manager time-off calendar**: Managers will be able to see approved and pending time off for their direct reports in a calendar view.</span></span> <span data-ttu-id="45232-141">Esta exibição fornece uma compreensão fácil de quando os membros da equipe estão ausente do trabalho.</span><span class="sxs-lookup"><span data-stu-id="45232-141">This view provides an easy understanding of when their team members are away from work.</span></span>

### <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="45232-142">Entidades de lista de verificação incluídas no Dataverse</span><span class="sxs-lookup"><span data-stu-id="45232-142">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="45232-143">Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="45232-143">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="known-issues"></a><span data-ttu-id="45232-144">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="45232-144">Known issues</span></span>

<span data-ttu-id="45232-145">O espaço de trabalho **Gerenciamento de recursos** pode estar exibindo recursos que estão desabilitados como recursos de visualização quando estão geralmente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="45232-145">The **Feature management** workspace may be displaying features that are disabled as preview features when they are generally available.</span></span> <span data-ttu-id="45232-146">A seguir, é exibida uma lista de recursos geralmente disponíveis que mostram um status incorreto.</span><span class="sxs-lookup"><span data-stu-id="45232-146">Below is a list of generally available features that show an incorrect status.</span></span> 

- <span data-ttu-id="45232-147">Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="45232-147">Benefits management</span></span>
- <span data-ttu-id="45232-148">Gerenciamento de casos</span><span class="sxs-lookup"><span data-stu-id="45232-148">Case management</span></span>
- <span data-ttu-id="45232-149">Log de banco de dados (auditoria)</span><span class="sxs-lookup"><span data-stu-id="45232-149">Database logging (Auditing)</span></span>
- <span data-ttu-id="45232-150">Acúmulo de licenças para uma única empresa ou um único plano</span><span class="sxs-lookup"><span data-stu-id="45232-150">Leave accrual for a single company or a single plan</span></span>
- <span data-ttu-id="45232-151">Suspensão de acúmulo de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="45232-151">Leave and absence accrual suspension</span></span>
- <span data-ttu-id="45232-152">Código de motivo de ajuste de saldo e comentário</span><span class="sxs-lookup"><span data-stu-id="45232-152">Balance adjustment reason code and comment</span></span>
- <span data-ttu-id="45232-153">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="45232-153">Buy and sell leave</span></span>
- <span data-ttu-id="45232-154">Calendário de licenças e ausências</span><span class="sxs-lookup"><span data-stu-id="45232-154">Leave and absence calendar</span></span>
- <span data-ttu-id="45232-155">Regras de postergação de licença</span><span class="sxs-lookup"><span data-stu-id="45232-155">Leave carry-forward rules</span></span>
- <span data-ttu-id="45232-156">Auditoria de acúmulo de licenças</span><span class="sxs-lookup"><span data-stu-id="45232-156">Leave accrual auditing</span></span>
- <span data-ttu-id="45232-157">Exclusão de acúmulo de licenças</span><span class="sxs-lookup"><span data-stu-id="45232-157">Leave accrual deletion</span></span>
- <span data-ttu-id="45232-158">Arredondamento do acúmulo de licenças</span><span class="sxs-lookup"><span data-stu-id="45232-158">Leave accrual rounding</span></span>
- <span data-ttu-id="45232-159">Configurar vários tipos de licença em um único plano de licença</span><span class="sxs-lookup"><span data-stu-id="45232-159">Configure multiple leave types on a single leave plan</span></span>
- <span data-ttu-id="45232-160">Atualizar aprimoramentos de folgas</span><span class="sxs-lookup"><span data-stu-id="45232-160">Update time-off enhancements</span></span>
- <span data-ttu-id="45232-161">Usar o FTE de um funcionário para acúmulos</span><span class="sxs-lookup"><span data-stu-id="45232-161">Use an employee's FTE for accruals</span></span>
- <span data-ttu-id="45232-162">Exibição da remuneração interempresarial</span><span class="sxs-lookup"><span data-stu-id="45232-162">Cross company compensation view</span></span>
- <span data-ttu-id="45232-163">Imprima avaliações de desempenho</span><span class="sxs-lookup"><span data-stu-id="45232-163">Print performance reviews</span></span>
- <span data-ttu-id="45232-164">Correções de feriados do acúmulo de licenças</span><span class="sxs-lookup"><span data-stu-id="45232-164">Leave accrual holiday corrections</span></span>

### <a name="benefit-plan-employee-entity"></a><span data-ttu-id="45232-165">Entidade Funcionário do plano de benefícios</span><span class="sxs-lookup"><span data-stu-id="45232-165">Benefit plan employee entity</span></span> 

<span data-ttu-id="45232-166">Recentemente descobrimos dois problemas com relação à entidade **BenefitsPlanEmployee**.</span><span class="sxs-lookup"><span data-stu-id="45232-166">We have recently discovered two issues regarding the **BenefitsPlanEmployee** entity.</span></span> <span data-ttu-id="45232-167">Ao importar as inscrições do trabalhador, o **Código de cobertura** e o **Código do tipo de plano** estão sendo definidos incorretamente.</span><span class="sxs-lookup"><span data-stu-id="45232-167">When importing worker enrollments, the **Coverage code** and the **Plan type code** are being set incorrectly.</span></span> <span data-ttu-id="45232-168">Esse problema faz com que os planos de benefícios do funcionário sejam exibidos incorretamente no formulário **Plano de benefícios do trabalhador** e no formulário **Abrir a inscrição** no Autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="45232-168">This issue causes employee benefit plans to display incorrectly in the **Worker benefits plan** form and in the **Open enrollment** form in Employee self service.</span></span> <span data-ttu-id="45232-169">Esse problema também pode afetar a capacidade do funcionário de selecionar planos no Autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="45232-169">This issue can also impact the employee's ability to select plans in Employee self service.</span></span> <span data-ttu-id="45232-170">No momento, não há uma solução alternativa.</span><span class="sxs-lookup"><span data-stu-id="45232-170">Currently there isn't a workaround.</span></span> <span data-ttu-id="45232-171">Estamos tratando isso como uma correção de alta prioridade e implantarei a correção em nossa próxima versão.</span><span class="sxs-lookup"><span data-stu-id="45232-171">We're treating this as a high-priority fix and will roll out the fix with our next release.</span></span>

## <a name="see-also"></a><span data-ttu-id="45232-172">Consulte também</span><span class="sxs-lookup"><span data-stu-id="45232-172">See also</span></span>

[<span data-ttu-id="45232-173">Novidades ou alterações no Human Resources</span><span class="sxs-lookup"><span data-stu-id="45232-173">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="45232-174">Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="45232-174">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="45232-175">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="45232-175">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="45232-176">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="45232-176">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]