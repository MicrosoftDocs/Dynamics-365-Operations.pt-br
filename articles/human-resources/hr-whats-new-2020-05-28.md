---
title: Novidades ou alterações no Dynamics 365 Human Resources (28 de maio de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 28 de maio de 2020.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 00a5881ea88749c8553e4c810fb57070f217b01c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417329"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a><span data-ttu-id="1af20-103">Novidades ou alterações no Dynamics 365 Human Resources (28 de maio de 2020)</span><span class="sxs-lookup"><span data-stu-id="1af20-103">What's new or changed in Dynamics 365 Human Resources (May 28, 2020)</span></span>

<span data-ttu-id="1af20-104">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1af20-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="1af20-105">As alterações se aplicam ao número da compilação 8.1.3287.</span><span class="sxs-lookup"><span data-stu-id="1af20-105">Changes apply to build number 8.1.3287.</span></span> <span data-ttu-id="1af20-106">Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.</span><span class="sxs-lookup"><span data-stu-id="1af20-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a><span data-ttu-id="1af20-107">A entidade LeaveRequest não funciona ao habilitar vários tipos por plano de licença (447498)</span><span class="sxs-lookup"><span data-stu-id="1af20-107">LeaveRequest entity doesn't work when you enable multiple types per leave plan (447498)</span></span>

<span data-ttu-id="1af20-108">Com essa alteração, a **LeaveEnrollmentV2Entity** agora está disponível para corrigir o erro que ocorre quando você habilita vários tipos de licença.</span><span class="sxs-lookup"><span data-stu-id="1af20-108">With this change, the **LeaveEnrollmentV2Entity** is now available to correct the error that occurs when you enable multiple leave types.</span></span>

## <a name="batch-contention-reduction-feature-preview-446619"></a><span data-ttu-id="1af20-109">Recurso de redução de contenção de lotes (versão prévia) (446619)</span><span class="sxs-lookup"><span data-stu-id="1af20-109">Batch contention reduction feature (preview) (446619)</span></span>

<span data-ttu-id="1af20-110">Ao habilitar esse recurso, você pode esperar uma redução no bloqueio em tabelas de estrutura de lotes ao selecionar tarefas e concluir trabalhos.</span><span class="sxs-lookup"><span data-stu-id="1af20-110">When you enable this feature, you can expect a reduction in blocking on batch framework tables while selecting tasks and finishing jobs.</span></span>

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a><span data-ttu-id="1af20-111">UpdateConflict ao salvar o trabalhador impede a edição de um registro em Pessoas (427915)</span><span class="sxs-lookup"><span data-stu-id="1af20-111">UpdateConflict while saving worker prevents editing a record in People (427915)</span></span>

<span data-ttu-id="1af20-112">Essa alteração corrige um erro ao adicionar um novo funcionário, atualizar as informações de endereço e alterar a preferência do idioma.</span><span class="sxs-lookup"><span data-stu-id="1af20-112">This change corrects an error when adding a new worker, updating address information, and changing language preference.</span></span> <span data-ttu-id="1af20-113">Neste cenário único, um erro foi exibido indicando que não foi possível atualizar o registro.</span><span class="sxs-lookup"><span data-stu-id="1af20-113">In this unique scenario, an error displayed indicating the record couldn't be updated.</span></span> 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a><span data-ttu-id="1af20-114">Não é possível adicionar um anexo a uma solicitação de licença aprovada para reenvio (425407)</span><span class="sxs-lookup"><span data-stu-id="1af20-114">Unable to add an attachment to an approved leave request to resubmit (425407)</span></span>

<span data-ttu-id="1af20-115">Essa alteração agora permite anexos a solicitações de licença aprovadas.</span><span class="sxs-lookup"><span data-stu-id="1af20-115">This change now allows attachments to approved leave requests.</span></span>

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a><span data-ttu-id="1af20-116">O usuário pode inserir remuneração para um funcionário em um formulário de entidade legal diferente (409529)</span><span class="sxs-lookup"><span data-stu-id="1af20-116">User can enter compensation for an employee in a different legal entity form (409529)</span></span>

<span data-ttu-id="1af20-117">Essa alteração desativa as opções de remuneração para impedir a entrada inadvertida de registros de remuneração da entidade legal errada.</span><span class="sxs-lookup"><span data-stu-id="1af20-117">This change disables compensation options to prevent inadvertent entry of compensation records for the wrong legal entity.</span></span>

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a><span data-ttu-id="1af20-118">Erro ao transferir um funcionário e a data de atribuição da posição do trabalhador é anterior à duração da posição (429402)</span><span class="sxs-lookup"><span data-stu-id="1af20-118">Error when you transfer an employee and the Worker position assignment date is before the position duration (429402)</span></span>

<span data-ttu-id="1af20-119">As mensagens de erro ao transferir um funcionário neste cenário foram atualizadas para descrever melhor as alterações necessárias para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="1af20-119">Error messages when transferring an employee in this scenario have been updated to better describe the changes needed to correct the problem.</span></span>

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a><span data-ttu-id="1af20-120">Recursos de anexos da inscrição de benefícios de Autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="1af20-120">Attachments capabilities in Employee self service benefits enrollment</span></span>
 
<span data-ttu-id="1af20-121">Agora você pode adicionar anexos durante o processo de inscrição de benefícios para cada plano em que o funcionário se inscreva.</span><span class="sxs-lookup"><span data-stu-id="1af20-121">Now you can add attachments during the benefits enrollment process for each plan that the employee's enrolling in.</span></span> <span data-ttu-id="1af20-122">Em seguida, você poderá exibir os anexos no formulário **Benefício do trabalhador inscrito**.</span><span class="sxs-lookup"><span data-stu-id="1af20-122">You can then view the attachments within the **Worker enrolled benefit** form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="1af20-123">Em visualização</span><span class="sxs-lookup"><span data-stu-id="1af20-123">In preview</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="1af20-124">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="1af20-124">Human Resources application in Teams</span></span>

<span data-ttu-id="1af20-125">Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1af20-125">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="1af20-126">Eles podem interagir com um bot para criar solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="1af20-126">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="1af20-127">Para obter mais informações, consulte [aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="1af20-127">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="leave-suspension"></a><span data-ttu-id="1af20-128">Sair da suspensão</span><span class="sxs-lookup"><span data-stu-id="1af20-128">Leave suspension</span></span>

<span data-ttu-id="1af20-129">Você pode suspender a licença e a ausência em Human Resources para um funcionário.</span><span class="sxs-lookup"><span data-stu-id="1af20-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="1af20-130">Suspender licença interrompe a acumulação de licenças de licença para os tipos de licença selecionados.</span><span class="sxs-lookup"><span data-stu-id="1af20-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="1af20-131">Se a suspensão ocorrer depois de um acúmulo ter sido processado, a suspensão da licença criará um ajuste rateado para o saldo de licença do funcionário.</span><span class="sxs-lookup"><span data-stu-id="1af20-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="1af20-132">Para obter mais informações, consulte [Suspender licença](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="1af20-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="1af20-133">Atualizar a experiência do usuário para indicar que a acumulação foi suspensa (429550)</span><span class="sxs-lookup"><span data-stu-id="1af20-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="1af20-134">Agora, a experiência do usuário indica que a acumulação foi suspensa para um plano.</span><span class="sxs-lookup"><span data-stu-id="1af20-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="1af20-135">Em breve</span><span class="sxs-lookup"><span data-stu-id="1af20-135">Coming soon</span></span>

## <a name="database-logging-in-preview-in-june"></a><span data-ttu-id="1af20-136">Log do banco de dados (na visualização em junho)</span><span class="sxs-lookup"><span data-stu-id="1af20-136">Database logging (in preview in June)</span></span>

<span data-ttu-id="1af20-137">O recurso de log de banco de dados permite determinar a tabela e os campos que devem ser monitorados.</span><span class="sxs-lookup"><span data-stu-id="1af20-137">The database logging feature allows you to determine which table and fields should be monitored.</span></span> <span data-ttu-id="1af20-138">Ele também permite que você determine os eventos que devem disparar o controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="1af20-138">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="1af20-139">Os recursos de consulta estão disponíveis para ver essas alterações ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="1af20-139">Inquiry capabilities are available to see these changes over time.</span></span>

## <a name="buy-and-sell-leave-in-preview-june-1"></a><span data-ttu-id="1af20-140">Licença de compra e venda (na visualização de 1º de junho)</span><span class="sxs-lookup"><span data-stu-id="1af20-140">Buy and sell leave (in preview June 1)</span></span>

<span data-ttu-id="1af20-141">Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças.</span><span class="sxs-lookup"><span data-stu-id="1af20-141">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="1af20-142">Esse processo costuma ser gerenciado manualmente.</span><span class="sxs-lookup"><span data-stu-id="1af20-142">This process is often managed manually.</span></span> <span data-ttu-id="1af20-143">Esse recurso oferece uma forma mais automatizada de gerenciar políticas e solicitações para o departamento de RH, além de ajudar a eliminar erros e simplificar o processo de gerenciamento de licenças.</span><span class="sxs-lookup"><span data-stu-id="1af20-143">This feature provides a more automated way to manage policies and requests for the HR department, and it helps eliminate mistakes while streamlining the leave management process.</span></span> <span data-ttu-id="1af20-144">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="1af20-144">For more information, see:</span></span>

- [<span data-ttu-id="1af20-145">Gerenciar políticas de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="1af20-145">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="1af20-146">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="1af20-146">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="1af20-147">Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="1af20-147">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="1af20-148">Entidades de gerenciamento de benefícios estão sendo liberadas.</span><span class="sxs-lookup"><span data-stu-id="1af20-148">Benefits management entities are releasing.</span></span> <span data-ttu-id="1af20-149">As entidades DMF permitem importar e exportar dados para configurar facilmente o gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="1af20-149">DMF entities allow importing and exporting data to easily configure benefits management.</span></span> <span data-ttu-id="1af20-150">Um modelo de gerenciamento de benefícios também estará disponível para mover dados.</span><span class="sxs-lookup"><span data-stu-id="1af20-150">A Benefits management template will also be available to move data.</span></span> <span data-ttu-id="1af20-151">O modelo exporta e importa os dados de uma forma sequencial para respeitar as dependências de dados.</span><span class="sxs-lookup"><span data-stu-id="1af20-151">The template exports and imports the data in a sequential manner to respect data dependencies.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a><span data-ttu-id="1af20-152">Adicionar código de motivo a suspensões de acúmulos (1º de junho)</span><span class="sxs-lookup"><span data-stu-id="1af20-152">Add reason code to accrual suspensions (June 1)</span></span>

<span data-ttu-id="1af20-153">Os códigos de motivo foram adicionados à suspensão de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="1af20-153">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules-june-1"></a><span data-ttu-id="1af20-154">Regras de postergação (1º de junho)</span><span class="sxs-lookup"><span data-stu-id="1af20-154">Carry forward rules (June 1)</span></span>

<span data-ttu-id="1af20-155">Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos.</span><span class="sxs-lookup"><span data-stu-id="1af20-155">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="1af20-156">Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias.</span><span class="sxs-lookup"><span data-stu-id="1af20-156">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="1af20-157">Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="1af20-157">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a><span data-ttu-id="1af20-158">Suspender a acumulação de licenças para tipos de licença especificados (1º de junho)</span><span class="sxs-lookup"><span data-stu-id="1af20-158">Suspend leave accrual for specified leave types (June 1)</span></span>

<span data-ttu-id="1af20-159">Nesta versão, o HR pode criar uma regra para suspender as competências de licença para funcionários com solicitações de licença inseridas para licenças não pagas.</span><span class="sxs-lookup"><span data-stu-id="1af20-159">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="1af20-160">A licença não remunerada pode ser um tipo, mas não precisa ser.</span><span class="sxs-lookup"><span data-stu-id="1af20-160">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="1af20-161">Você pode suspender qualquer licença com base em outro tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="1af20-161">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a><span data-ttu-id="1af20-162">Entidade DMF disponível para suspensões de acúmulos (1º de junho)</span><span class="sxs-lookup"><span data-stu-id="1af20-162">DMF entity available for accrual suspensions (June 1)</span></span>

<span data-ttu-id="1af20-163">Uma entidade DMF disponível para suspensões de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="1af20-163">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="see-also"></a><span data-ttu-id="1af20-164">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1af20-164">See also</span></span>

[<span data-ttu-id="1af20-165">Novidades ou alterações no Human Resources</span><span class="sxs-lookup"><span data-stu-id="1af20-165">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="1af20-166">Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="1af20-166">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="1af20-167">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="1af20-167">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="1af20-168">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="1af20-168">Manage features</span></span>](hr-admin-manage-features.md)