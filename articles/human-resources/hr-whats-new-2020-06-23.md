---
title: Novidades ou alterações no Dynamics 365 Human Resources (25 de junho de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 23 de junho de 2020.
author: andreabichsel
ms.date: 06/25/2020
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
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 49853eaaf9d4e0fa44c22b3f0927ae4ab034cf8e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802302"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a><span data-ttu-id="a5971-103">Novidades ou alterações no Dynamics 365 Human Resources (23 de junho de 2020)</span><span class="sxs-lookup"><span data-stu-id="a5971-103">What's new or changed in Dynamics 365 Human Resources (June 23, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a5971-104">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a5971-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a5971-105">As alterações se aplicam ao número da compilação 8.1.3347.</span><span class="sxs-lookup"><span data-stu-id="a5971-105">Changes apply to build number 8.1.3347.</span></span> <span data-ttu-id="a5971-106">Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.</span><span class="sxs-lookup"><span data-stu-id="a5971-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a><span data-ttu-id="a5971-107">Quando o registro de um funcionário demitido expira, o tipo de licença, o saldo e o valor são desmarcados no formulário de registro de licença (444867)</span><span class="sxs-lookup"><span data-stu-id="a5971-107">When an enrollment is expired for a terminated employee, the leave type, balance, and amount are all cleared in the Leave enrollment form (444867)</span></span>

<span data-ttu-id="a5971-108">Agora os valores nos campos **Tipo de licença**, **Saldo** e **Valor** são mantidos em vez de serem apagados ao fazer essa seleção.</span><span class="sxs-lookup"><span data-stu-id="a5971-108">Values in the **Leave type**, **Balance**, and **Amount** are now maintained instead of cleared upon making this selection.</span></span>

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a><span data-ttu-id="a5971-109">Saldo previsto incorreto quando o novo recurso (Acumulado de licenças de uma única empresa ou de um único plano) está habilitado (456553)</span><span class="sxs-lookup"><span data-stu-id="a5971-109">Incorrect forecasted balance when new feature (Leave accrual for a single company or a single plan) is enabled (456553)</span></span>

<span data-ttu-id="a5971-110">Agora é exibido o saldo previsto correto quando o acumulado de licenças de uma única empresa ou de um único plano está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a5971-110">The correct forecasted balance now displays when the leave accrual for a single company or single plan has been enabled.</span></span>

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a><span data-ttu-id="a5971-111">Entidades com relações que resultam em propriedades de navegação duplicadas (456486)</span><span class="sxs-lookup"><span data-stu-id="a5971-111">Entities with relations that result in duplicate navigation properties (456486)</span></span>

<span data-ttu-id="a5971-112">Esta versão corrige um problema nas propriedades de navegação (relação) de várias entidades.</span><span class="sxs-lookup"><span data-stu-id="a5971-112">This release corrects an issue with the navigation properties (relation) of multiple entities.</span></span> <span data-ttu-id="a5971-113">Relações duplicadas são detectadas.</span><span class="sxs-lookup"><span data-stu-id="a5971-113">Duplicate relations are detected.</span></span> <span data-ttu-id="a5971-114">Esses cenários foram todos corrigidos.</span><span class="sxs-lookup"><span data-stu-id="a5971-114">These scenarios have all been corrected.</span></span>
 
## <a name="cross-company-comments-on-performance-review-455536"></a><span data-ttu-id="a5971-115">Comentários interempresariais na Avaliação de desempenho (455536)</span><span class="sxs-lookup"><span data-stu-id="a5971-115">Cross-company comments on Performance review (455536)</span></span>

<span data-ttu-id="a5971-116">Agora os comentários interempresariais estão visíveis nas avaliações de desempenho com esta correção.</span><span class="sxs-lookup"><span data-stu-id="a5971-116">Cross-company comments are now visible on performance reviews with this fix.</span></span> <span data-ttu-id="a5971-117">Esta alteração corrige a exibição de comentários do revisor inseridos em diferentes empresas para a mesma avaliação de desempenho.</span><span class="sxs-lookup"><span data-stu-id="a5971-117">This change corrects the view of reviewer comments that were entered in different companies for the same performance review.</span></span>
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a><span data-ttu-id="a5971-118">Inconsistência na exibição de dados de gerenciamento de remuneração (432562)</span><span class="sxs-lookup"><span data-stu-id="a5971-118">Inconsistency in showing compensation management data (432562)</span></span>

<span data-ttu-id="a5971-119">Agora uma exibição consistente dos dados de remuneração é mantida no autoatendimento para Gerentes.</span><span class="sxs-lookup"><span data-stu-id="a5971-119">A consistent view of compensation data is now maintained in Manager self service.</span></span> <span data-ttu-id="a5971-120">Agora, dependendo de como você navega até os **Detalhes de remuneração** de um trabalhador, os dados de remuneração são exibidos de maneira consistente para os gerentes.</span><span class="sxs-lookup"><span data-stu-id="a5971-120">Depending on how you navigate to a worker's **Compensation details**, compensation data now consistently displays to managers.</span></span>
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a><span data-ttu-id="a5971-121">A data de efetivação do plano de remuneração fixa tem como padrão a data de hoje (411994)</span><span class="sxs-lookup"><span data-stu-id="a5971-121">Fixed compensation plan's effective date defaults to today's date (411994)</span></span>

<span data-ttu-id="a5971-122">Agora a data de início da remuneração está baseada na data de início do cargo que está sendo atribuído ao funcionário.</span><span class="sxs-lookup"><span data-stu-id="a5971-122">The compensation start date is now based on the start date of the position being assigned to the employee.</span></span>

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a><span data-ttu-id="a5971-123">A opção Habilitar definição de meio dia do formulário de licença e ausência está desabilitada quando o formulário é aberto (452607)</span><span class="sxs-lookup"><span data-stu-id="a5971-123">Leave and absence form Enable half day definition is disabled when form opens (452607)</span></span>

<span data-ttu-id="a5971-124">Com essa alteração, a opção **Habilitar definição de meio dia** ficará habilitada até surgir novas transações de licença.</span><span class="sxs-lookup"><span data-stu-id="a5971-124">With this change, the **Enable half day definition** will be enabled until new leave transactions exist.</span></span> 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a><span data-ttu-id="a5971-125">Não é possível publicar em HcmDiscussionEntity via Excel; erro no campo TotalRatingScore (453899)</span><span class="sxs-lookup"><span data-stu-id="a5971-125">Unable to publish to HcmDiscussionEntity via Excel; TotalRatingScore field error (453899)</span></span>

<span data-ttu-id="a5971-126">Agora você pode atualizar o campo **TotalRatingScore** usando **HCMDiscussionEntity** no designer de pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="a5971-126">You can now update the **TotalRatingScore** field using **HCMDiscussionEntity** in the Excel workbook designer.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a5971-127">Em visualização</span><span class="sxs-lookup"><span data-stu-id="a5971-127">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="a5971-128">Log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="a5971-128">Database logging</span></span>

<span data-ttu-id="a5971-129">O de log de banco de dados permite determinar quais tabelas e campos devem ser monitorados.</span><span class="sxs-lookup"><span data-stu-id="a5971-129">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="a5971-130">Ele também permite que você determine os eventos que devem disparar o controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="a5971-130">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="a5971-131">Use os recursos de log de banco de dados para ver essas alterações ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="a5971-131">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="a5971-132">Para obter mais informações, consulte [Configurar e gerenciar o log de banco de dados](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="a5971-132">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="a5971-133">Campos obrigatórios</span><span class="sxs-lookup"><span data-stu-id="a5971-133">Mandatory fields</span></span> 

<span data-ttu-id="a5971-134">Agora você pode tornar campos obrigatórios usando recursos de personalização do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a5971-134">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="a5971-135">Este recurso exige **Exibições salvas**.</span><span class="sxs-lookup"><span data-stu-id="a5971-135">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="a5971-136">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="a5971-136">Human Resources application in Teams</span></span>

<span data-ttu-id="a5971-137">Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a5971-137">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="a5971-138">Eles podem interagir com um bot para criar solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="a5971-138">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="a5971-139">Para obter mais informações, consulte [aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="a5971-139">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="a5971-140">Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="a5971-140">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="a5971-141">Entidades de gerenciamento de benefícios estão sendo liberadas.</span><span class="sxs-lookup"><span data-stu-id="a5971-141">Benefits management entities are releasing.</span></span> <span data-ttu-id="a5971-142">As entidades DMF permitem que você importe e exporte dados para configurar facilmente o gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="a5971-142">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="a5971-143">Um modelo de gerenciamento de benefícios estará disponível para mover dados.</span><span class="sxs-lookup"><span data-stu-id="a5971-143">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="a5971-144">O modelo exporta e importa os dados sequencialmente para respeitar as dependências de dados.</span><span class="sxs-lookup"><span data-stu-id="a5971-144">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="a5971-145">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="a5971-145">Buy and sell leave</span></span> 

<span data-ttu-id="a5971-146">Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças.</span><span class="sxs-lookup"><span data-stu-id="a5971-146">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="a5971-147">Esse processo costuma ser gerenciado manualmente.</span><span class="sxs-lookup"><span data-stu-id="a5971-147">This process is often managed manually.</span></span> <span data-ttu-id="a5971-148">Esse recurso automatiza o gerenciamento de políticas e solicitações para o departamento de RH.</span><span class="sxs-lookup"><span data-stu-id="a5971-148">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="a5971-149">Ele simplifica o processo de gerenciamento de licenças e ajuda a eliminar erros.</span><span class="sxs-lookup"><span data-stu-id="a5971-149">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="a5971-150">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="a5971-150">For more information, see:</span></span>

- [<span data-ttu-id="a5971-151">Gerenciar políticas de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="a5971-151">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="a5971-152">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="a5971-152">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="a5971-153">Deixar o acúmulo para uma única empresa ou um plano</span><span class="sxs-lookup"><span data-stu-id="a5971-153">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="a5971-154">Os clientes podem processar acúmulos para uma única empresa ou um único plano de licença e de ausência.</span><span class="sxs-lookup"><span data-stu-id="a5971-154">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="a5971-155">Essa capacidade oferece esclarecimentos sobre o processo de acumulação para clientes com anos de licença diferentes ou para manter políticas de competência.</span><span class="sxs-lookup"><span data-stu-id="a5971-155">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="a5971-156">Para obter mais informações, consulte [Acumular licenças por empresa ou por plano de licença](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="a5971-156">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="a5971-157">Adicionar anexos a solicitações de folga</span><span class="sxs-lookup"><span data-stu-id="a5971-157">Add attachments to time off requests</span></span>

<span data-ttu-id="a5971-158">A capacidade de adicionar anexos a solicitações de licença aprovadas é crítica no ambiente de COVID-19 atual.</span><span class="sxs-lookup"><span data-stu-id="a5971-158">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="a5971-159">Os funcionários agora podem adicionar esses anexos.</span><span class="sxs-lookup"><span data-stu-id="a5971-159">Employees can now add these attachments.</span></span> <span data-ttu-id="a5971-160">Eles também estão mais informados sobre como as atualizações são feitas para deixar solicitações.</span><span class="sxs-lookup"><span data-stu-id="a5971-160">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="a5971-161">Para obter mais informações, consulte [Adicionar um anexo a uma solicitação existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="a5971-161">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="a5971-162">Adicionar código de motivo a suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="a5971-162">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="a5971-163">Os códigos de motivo foram adicionados à suspensão de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="a5971-163">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="a5971-164">Regras de postergação</span><span class="sxs-lookup"><span data-stu-id="a5971-164">Carry forward rules</span></span> 

<span data-ttu-id="a5971-165">Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos.</span><span class="sxs-lookup"><span data-stu-id="a5971-165">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="a5971-166">Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias.</span><span class="sxs-lookup"><span data-stu-id="a5971-166">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="a5971-167">Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="a5971-167">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="a5971-168">Suspender a acumulação de licenças para tipos de licença especificados</span><span class="sxs-lookup"><span data-stu-id="a5971-168">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="a5971-169">Você pode criar uma regra para suspender os acúmulos de licença para funcionários com solicitações de licença inseridas para licenças não pagas.</span><span class="sxs-lookup"><span data-stu-id="a5971-169">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="a5971-170">A licença não remunerada pode ser um tipo, mas não precisa ser.</span><span class="sxs-lookup"><span data-stu-id="a5971-170">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="a5971-171">Você pode suspender qualquer licença com base em outro tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="a5971-171">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="a5971-172">Entidade DMF disponível para suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="a5971-172">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="a5971-173">Uma entidade DMF disponível para suspensões de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="a5971-173">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="a5971-174">Em breve</span><span class="sxs-lookup"><span data-stu-id="a5971-174">Coming soon</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="a5971-175">Configurar o nome do autoatendimento para Funcionários</span><span class="sxs-lookup"><span data-stu-id="a5971-175">Configure the name of Employee self-service</span></span>

<span data-ttu-id="a5971-176">Haverá uma nova opção disponível nos **Parâmetros de Human Resources** para atualizar o nome do espaço de trabalho de autoatendimento para Funcionários para Autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="a5971-176">A new option will be available in **Human Resources parameters** to update the name of the Employee self service workspace to Self service.</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="a5971-177">Entidades de lista de verificação incluídas no Dataverse</span><span class="sxs-lookup"><span data-stu-id="a5971-177">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="a5971-178">Entidades de lista de verificação relativas a Integração, Remoção, Transferência e Processos empresariais estarão disponíveis em breve no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a5971-178">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon within Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5971-179">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a5971-179">See also</span></span>

[<span data-ttu-id="a5971-180">Novidades ou alterações no Human Resources</span><span class="sxs-lookup"><span data-stu-id="a5971-180">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="a5971-181">Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="a5971-181">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="a5971-182">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="a5971-182">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="a5971-183">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="a5971-183">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]