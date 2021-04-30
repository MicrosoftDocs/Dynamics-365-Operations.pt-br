---
title: Novidades ou alterações no Dynamics 365 Human Resources (23 de julho de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 23 de julho de 2020.
author: andreabichsel
ms.date: 07/23/2020
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
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eb4ef2bf335e19d0d890465c851c46f66ef8bd8e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891856"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a><span data-ttu-id="09695-103">Novidades ou alterações no Dynamics 365 Human Resources (23 de julho de 2020)</span><span class="sxs-lookup"><span data-stu-id="09695-103">What's new or changed in Dynamics 365 Human Resources (July 23, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="09695-104">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="09695-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="09695-105">As alterações se aplicam ao número da compilação 8.1.3416.</span><span class="sxs-lookup"><span data-stu-id="09695-105">Changes apply to build number 8.1.3416.</span></span> <span data-ttu-id="09695-106">Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.</span><span class="sxs-lookup"><span data-stu-id="09695-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a><span data-ttu-id="09695-107">A exclusão de dimensões financeiras em uma posição não funciona como esperado (445476)</span><span class="sxs-lookup"><span data-stu-id="09695-107">Deleting Financial Dimensions on a Position doesn't work as expected (445476)</span></span>

<span data-ttu-id="09695-108">A remoção de dimensões de uma posição agora remove essas mesmas posições do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="09695-108">Removing dimensions from a position now removes those same positions from Dataverse.</span></span>

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a><span data-ttu-id="09695-109">Posições que não estão em hierarquias mostram posições inativas (397257)</span><span class="sxs-lookup"><span data-stu-id="09695-109">Positions not in hierarchy show inactive positions (397257)</span></span>

<span data-ttu-id="09695-110">Posições que estão inativas (têm uma duração expirada), não são mais exibidas na hierarquia de posição como **Posições que não estão na hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="09695-110">Positions that are inactive (have an expired duration), no longer display in the position hierarchy as **Positions not in hierarchy**.</span></span> 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a><span data-ttu-id="09695-111">A validação que ocorre entre LeaveEnrollmentEntity e HcmWorkerEntity na importação do Data Management Framework (DMF) causa cargas de dados lentos (442324)</span><span class="sxs-lookup"><span data-stu-id="09695-111">Validation occurring between LeaveEnrollmentEntity and HcmWorkerEntity on Data Management Framework (DMF) import causes slow data loads (442324)</span></span>

<span data-ttu-id="09695-112">As alterações nessa versão aumentam o desempenho do **LeaveEnrollmentEntity**.</span><span class="sxs-lookup"><span data-stu-id="09695-112">Changes in this release increase the performance of **LeaveEnrollmentEntity**.</span></span>

## <a name="unable-to-personalize-in-organization-administration-447490"></a><span data-ttu-id="09695-113">Não é possível personalizar na Administração da organização (447490)</span><span class="sxs-lookup"><span data-stu-id="09695-113">Unable to personalize in Organization administration (447490)</span></span>

<span data-ttu-id="09695-114">Com essa alteração, você agora pode personalizar os links na **Administração da organização**.</span><span class="sxs-lookup"><span data-stu-id="09695-114">With this change, you can now personalize the links in **Organization administration**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="09695-115">Em visualização</span><span class="sxs-lookup"><span data-stu-id="09695-115">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="09695-116">Campos obrigatórios</span><span class="sxs-lookup"><span data-stu-id="09695-116">Mandatory fields</span></span> 

<span data-ttu-id="09695-117">Agora você pode tornar campos obrigatórios usando recursos de personalização do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="09695-117">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="09695-118">Este recurso exige **Exibições salvas**.</span><span class="sxs-lookup"><span data-stu-id="09695-118">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="09695-119">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="09695-119">Human Resources application in Teams</span></span>

<span data-ttu-id="09695-120">Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="09695-120">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="09695-121">Eles podem interagir com um bot para criar solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="09695-121">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="09695-122">Para obter mais informações, consulte [aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="09695-122">For more information, see [Human Resources app in Teams](./hr-admin-teams-leave-app.md).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="09695-123">Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="09695-123">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="09695-124">Entidades de gerenciamento de benefícios estão sendo liberadas.</span><span class="sxs-lookup"><span data-stu-id="09695-124">Benefits management entities are releasing.</span></span> <span data-ttu-id="09695-125">As entidades DMF permitem que você importe e exporte dados para configurar facilmente o gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="09695-125">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="09695-126">Um modelo de gerenciamento de benefícios estará disponível para mover dados.</span><span class="sxs-lookup"><span data-stu-id="09695-126">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="09695-127">O modelo exporta e importa os dados sequencialmente para respeitar as dependências de dados.</span><span class="sxs-lookup"><span data-stu-id="09695-127">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="09695-128">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="09695-128">Buy and sell leave</span></span> 

<span data-ttu-id="09695-129">Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças.</span><span class="sxs-lookup"><span data-stu-id="09695-129">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="09695-130">Esse processo costuma ser gerenciado manualmente.</span><span class="sxs-lookup"><span data-stu-id="09695-130">This process is often managed manually.</span></span> <span data-ttu-id="09695-131">Esse recurso automatiza o gerenciamento de políticas e solicitações para o departamento de RH.</span><span class="sxs-lookup"><span data-stu-id="09695-131">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="09695-132">Ele simplifica o processo de gerenciamento de licenças e ajuda a eliminar erros.</span><span class="sxs-lookup"><span data-stu-id="09695-132">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="09695-133">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="09695-133">For more information, see:</span></span>

- [<span data-ttu-id="09695-134">Gerenciar políticas de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="09695-134">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="09695-135">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="09695-135">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="09695-136">Deixar o acúmulo para uma única empresa ou um plano</span><span class="sxs-lookup"><span data-stu-id="09695-136">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="09695-137">Os clientes podem processar acúmulos para uma única empresa ou um único plano de licença e de ausência.</span><span class="sxs-lookup"><span data-stu-id="09695-137">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="09695-138">Essa capacidade esclarece sobre o processo de competência para clientes com diferentes políticas de anos de licença ou acúmulo de licenças.</span><span class="sxs-lookup"><span data-stu-id="09695-138">This ability provides clarity for the accrual process for customers with different leave years or leaves accrual policies.</span></span> <span data-ttu-id="09695-139">Para obter mais informações, consulte [Acumular licenças por empresa ou por plano de licença](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="09695-139">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="09695-140">Adicionar anexos a solicitações de folga</span><span class="sxs-lookup"><span data-stu-id="09695-140">Add attachments to time-off requests</span></span>

<span data-ttu-id="09695-141">A capacidade de adicionar anexos a solicitações de licença aprovadas é crítica no ambiente de COVID-19 atual.</span><span class="sxs-lookup"><span data-stu-id="09695-141">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="09695-142">Os funcionários agora podem adicionar esses anexos.</span><span class="sxs-lookup"><span data-stu-id="09695-142">Employees can now add these attachments.</span></span> <span data-ttu-id="09695-143">Eles também estão mais informados sobre como as atualizações são feitas para deixar solicitações.</span><span class="sxs-lookup"><span data-stu-id="09695-143">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="09695-144">Para obter mais informações, consulte [Adicionar um anexo a uma solicitação existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="09695-144">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="09695-145">Adicionar código de motivo a suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="09695-145">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="09695-146">Os códigos de motivo foram adicionados à suspensão de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="09695-146">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="09695-147">Regras de postergação</span><span class="sxs-lookup"><span data-stu-id="09695-147">Carry forward rules</span></span> 

<span data-ttu-id="09695-148">Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos.</span><span class="sxs-lookup"><span data-stu-id="09695-148">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="09695-149">Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias.</span><span class="sxs-lookup"><span data-stu-id="09695-149">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="09695-150">Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="09695-150">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="09695-151">Suspender a acumulação de licenças para tipos de licença especificados</span><span class="sxs-lookup"><span data-stu-id="09695-151">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="09695-152">Você pode criar uma regra para suspender os acúmulos de licença para funcionários com solicitações de licença inseridas para licenças não pagas.</span><span class="sxs-lookup"><span data-stu-id="09695-152">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="09695-153">A licença não remunerada pode ser um tipo, mas não precisa ser.</span><span class="sxs-lookup"><span data-stu-id="09695-153">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="09695-154">Você pode suspender qualquer licença com base em outro tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="09695-154">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="09695-155">Entidade DMF disponível para suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="09695-155">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="09695-156">Uma entidade DMF disponível para suspensões de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="09695-156">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="09695-157">Em breve</span><span class="sxs-lookup"><span data-stu-id="09695-157">Coming soon</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="09695-158">Entidades de lista de verificação incluídas no Dataverse</span><span class="sxs-lookup"><span data-stu-id="09695-158">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="09695-159">Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="09695-159">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="09695-160">Alterações na plataforma</span><span class="sxs-lookup"><span data-stu-id="09695-160">Platform changes</span></span>

<span data-ttu-id="09695-161">Atualização da plataforma 10.0.12 (36)</span><span class="sxs-lookup"><span data-stu-id="09695-161">Platform update 10.0.12 (36)</span></span>

## <a name="see-also"></a><span data-ttu-id="09695-162">Consulte também</span><span class="sxs-lookup"><span data-stu-id="09695-162">See also</span></span>

[<span data-ttu-id="09695-163">Novidades ou alterações no Human Resources</span><span class="sxs-lookup"><span data-stu-id="09695-163">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="09695-164">Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="09695-164">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="09695-165">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="09695-165">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="09695-166">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="09695-166">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]