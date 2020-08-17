---
title: Novidades ou alterações no Dynamics 365 Human Resources (23 de julho de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2020
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
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dd71ab5c48be1bec5ce2272bbff37ab10a4aed67
ms.sourcegitcommit: 81296c49be9953aa01e15527c34d0ef13b4622a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614401"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a><span data-ttu-id="178aa-103">Novidades ou alterações no Dynamics 365 Human Resources (23 de julho de 2020)</span><span class="sxs-lookup"><span data-stu-id="178aa-103">What's new or changed in Dynamics 365 Human Resources (July 23, 2020)</span></span>

<span data-ttu-id="178aa-104">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="178aa-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="178aa-105">As alterações se aplicam ao número da compilação 8.1.3416.</span><span class="sxs-lookup"><span data-stu-id="178aa-105">Changes apply to build number 8.1.3416.</span></span> <span data-ttu-id="178aa-106">Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.</span><span class="sxs-lookup"><span data-stu-id="178aa-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a><span data-ttu-id="178aa-107">A exclusão de dimensões financeiras em uma posição não funciona como esperado (445476)</span><span class="sxs-lookup"><span data-stu-id="178aa-107">Deleting Financial Dimensions on a Position doesn't work as expected (445476)</span></span>

<span data-ttu-id="178aa-108">A remoção de dimensões de uma posição agora remove essas mesmas posições do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="178aa-108">Removing dimensions from a position now removes those same positions from Common Data Service.</span></span>

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a><span data-ttu-id="178aa-109">Posições que não estão em hierarquias mostram posições inativas (397257)</span><span class="sxs-lookup"><span data-stu-id="178aa-109">Positions not in hierarchy show inactive positions (397257)</span></span>

<span data-ttu-id="178aa-110">Posições que estão inativas (têm uma duração expirada), não são mais exibidas na hierarquia de posição como **Posições que não estão na hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="178aa-110">Positions that are inactive (have an expired duration), no longer display in the position hierarchy as **Positions not in hierarchy**.</span></span> 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a><span data-ttu-id="178aa-111">A validação que ocorre entre LeaveEnrollmentEntity e HcmWorkerEntity na importação do Data Management Framework (DMF) causa cargas de dados lentos (442324)</span><span class="sxs-lookup"><span data-stu-id="178aa-111">Validation occurring between LeaveEnrollmentEntity and HcmWorkerEntity on Data Management Framework (DMF) import causes slow data loads (442324)</span></span>

<span data-ttu-id="178aa-112">As alterações nessa versão aumentam o desempenho do **LeaveEnrollmentEntity**.</span><span class="sxs-lookup"><span data-stu-id="178aa-112">Changes in this release increase the performance of **LeaveEnrollmentEntity**.</span></span>

## <a name="unable-to-personalize-in-organization-administration-447490"></a><span data-ttu-id="178aa-113">Não é possível personalizar na Administração da organização (447490)</span><span class="sxs-lookup"><span data-stu-id="178aa-113">Unable to personalize in Organization administration (447490)</span></span>

<span data-ttu-id="178aa-114">Com essa alteração, você agora pode personalizar os links na **Administração da organização**.</span><span class="sxs-lookup"><span data-stu-id="178aa-114">With this change, you can now personalize the links in **Organization administration**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="178aa-115">Em visualização</span><span class="sxs-lookup"><span data-stu-id="178aa-115">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="178aa-116">Campos obrigatórios</span><span class="sxs-lookup"><span data-stu-id="178aa-116">Mandatory fields</span></span> 

<span data-ttu-id="178aa-117">Agora você pode tornar campos obrigatórios usando recursos de personalização do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="178aa-117">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="178aa-118">Este recurso exige **Exibições salvas**.</span><span class="sxs-lookup"><span data-stu-id="178aa-118">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="178aa-119">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="178aa-119">Human Resources application in Teams</span></span>

<span data-ttu-id="178aa-120">Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="178aa-120">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="178aa-121">Eles podem interagir com um bot para criar solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="178aa-121">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="178aa-122">Para obter mais informações, consulte [aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="178aa-122">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="178aa-123">Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="178aa-123">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="178aa-124">Entidades de gerenciamento de benefícios estão sendo liberadas.</span><span class="sxs-lookup"><span data-stu-id="178aa-124">Benefits management entities are releasing.</span></span> <span data-ttu-id="178aa-125">As entidades DMF permitem que você importe e exporte dados para configurar facilmente o gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="178aa-125">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="178aa-126">Um modelo de gerenciamento de benefícios estará disponível para mover dados.</span><span class="sxs-lookup"><span data-stu-id="178aa-126">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="178aa-127">O modelo exporta e importa os dados sequencialmente para respeitar as dependências de dados.</span><span class="sxs-lookup"><span data-stu-id="178aa-127">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="178aa-128">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="178aa-128">Buy and sell leave</span></span> 

<span data-ttu-id="178aa-129">Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças.</span><span class="sxs-lookup"><span data-stu-id="178aa-129">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="178aa-130">Esse processo costuma ser gerenciado manualmente.</span><span class="sxs-lookup"><span data-stu-id="178aa-130">This process is often managed manually.</span></span> <span data-ttu-id="178aa-131">Esse recurso automatiza o gerenciamento de políticas e solicitações para o departamento de RH.</span><span class="sxs-lookup"><span data-stu-id="178aa-131">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="178aa-132">Ele simplifica o processo de gerenciamento de licenças e ajuda a eliminar erros.</span><span class="sxs-lookup"><span data-stu-id="178aa-132">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="178aa-133">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="178aa-133">For more information, see:</span></span>

- [<span data-ttu-id="178aa-134">Gerenciar políticas de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="178aa-134">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="178aa-135">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="178aa-135">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="178aa-136">Deixar o acúmulo para uma única empresa ou um plano</span><span class="sxs-lookup"><span data-stu-id="178aa-136">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="178aa-137">Os clientes podem processar acúmulos para uma única empresa ou um único plano de licença e de ausência.</span><span class="sxs-lookup"><span data-stu-id="178aa-137">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="178aa-138">Essa capacidade esclarece sobre o processo de competência para clientes com diferentes políticas de anos de licença ou acúmulo de licenças.</span><span class="sxs-lookup"><span data-stu-id="178aa-138">This ability provides clarity for the accrual process for customers with different leave years or leaves accrual policies.</span></span> <span data-ttu-id="178aa-139">Para obter mais informações, consulte [Acumular licenças por empresa ou por plano de licença](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="178aa-139">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="178aa-140">Adicionar anexos a solicitações de folga</span><span class="sxs-lookup"><span data-stu-id="178aa-140">Add attachments to time-off requests</span></span>

<span data-ttu-id="178aa-141">A capacidade de adicionar anexos a solicitações de licença aprovadas é crítica no ambiente de COVID-19 atual.</span><span class="sxs-lookup"><span data-stu-id="178aa-141">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="178aa-142">Os funcionários agora podem adicionar esses anexos.</span><span class="sxs-lookup"><span data-stu-id="178aa-142">Employees can now add these attachments.</span></span> <span data-ttu-id="178aa-143">Eles também estão mais informados sobre como as atualizações são feitas para deixar solicitações.</span><span class="sxs-lookup"><span data-stu-id="178aa-143">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="178aa-144">Para obter mais informações, consulte [Adicionar um anexo a uma solicitação existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="178aa-144">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="178aa-145">Adicionar código de motivo a suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="178aa-145">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="178aa-146">Os códigos de motivo foram adicionados à suspensão de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="178aa-146">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="178aa-147">Regras de postergação</span><span class="sxs-lookup"><span data-stu-id="178aa-147">Carry forward rules</span></span> 

<span data-ttu-id="178aa-148">Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos.</span><span class="sxs-lookup"><span data-stu-id="178aa-148">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="178aa-149">Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias.</span><span class="sxs-lookup"><span data-stu-id="178aa-149">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="178aa-150">Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="178aa-150">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="178aa-151">Suspender a acumulação de licenças para tipos de licença especificados</span><span class="sxs-lookup"><span data-stu-id="178aa-151">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="178aa-152">Você pode criar uma regra para suspender os acúmulos de licença para funcionários com solicitações de licença inseridas para licenças não pagas.</span><span class="sxs-lookup"><span data-stu-id="178aa-152">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="178aa-153">A licença não remunerada pode ser um tipo, mas não precisa ser.</span><span class="sxs-lookup"><span data-stu-id="178aa-153">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="178aa-154">Você pode suspender qualquer licença com base em outro tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="178aa-154">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="178aa-155">Entidade DMF disponível para suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="178aa-155">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="178aa-156">Uma entidade DMF disponível para suspensões de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="178aa-156">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="178aa-157">Em breve</span><span class="sxs-lookup"><span data-stu-id="178aa-157">Coming soon</span></span>

## <a name="checklist-entities-included-in-common-data-service"></a><span data-ttu-id="178aa-158">Entidades de lista de verificação incluídas no Common Data Service</span><span class="sxs-lookup"><span data-stu-id="178aa-158">Checklist entities included in Common Data Service</span></span>

<span data-ttu-id="178aa-159">Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="178aa-159">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Common Data Service.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="178aa-160">Alterações na plataforma</span><span class="sxs-lookup"><span data-stu-id="178aa-160">Platform changes</span></span>

<span data-ttu-id="178aa-161">Atualização da plataforma 10.0.12 (36)</span><span class="sxs-lookup"><span data-stu-id="178aa-161">Platform update 10.0.12 (36)</span></span>

## <a name="see-also"></a><span data-ttu-id="178aa-162">Consulte também</span><span class="sxs-lookup"><span data-stu-id="178aa-162">See also</span></span>

[<span data-ttu-id="178aa-163">Novidades ou alterações no Human Resources</span><span class="sxs-lookup"><span data-stu-id="178aa-163">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="178aa-164">Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="178aa-164">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="178aa-165">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="178aa-165">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="178aa-166">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="178aa-166">Manage features</span></span>](hr-admin-manage-features.md)
