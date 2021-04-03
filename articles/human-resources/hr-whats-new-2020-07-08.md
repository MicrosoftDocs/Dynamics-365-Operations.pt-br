---
title: Novidades ou alterações no Dynamics 365 Human Resources (08 de julho de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 8 de julho de 2020.
author: andreabichsel
manager: tfehr
ms.date: 07/08/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9715f332088b7b5340f4252af5f789d226d90ff2
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463589"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a><span data-ttu-id="a8c83-103">Novidades ou alterações no Dynamics 365 Human Resources (8 de julho de 2020)</span><span class="sxs-lookup"><span data-stu-id="a8c83-103">What's new or changed in Dynamics 365 Human Resources (July 8, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a8c83-104">Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a8c83-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a8c83-105">As alterações se aplicam ao número da compilação 8.1.3382.</span><span class="sxs-lookup"><span data-stu-id="a8c83-105">Changes apply to build number 8.1.3382.</span></span> <span data-ttu-id="a8c83-106">Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.</span><span class="sxs-lookup"><span data-stu-id="a8c83-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="database-logging"></a><span data-ttu-id="a8c83-107">Log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="a8c83-107">Database logging</span></span>

<span data-ttu-id="a8c83-108">O de log de banco de dados permite determinar quais tabelas e campos devem ser monitorados.</span><span class="sxs-lookup"><span data-stu-id="a8c83-108">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="a8c83-109">Ele também permite que você determine os eventos que devem disparar o controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="a8c83-109">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="a8c83-110">Use os recursos de log de banco de dados para ver essas alterações ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="a8c83-110">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="a8c83-111">Para obter mais informações, consulte [Configurar e gerenciar o log de banco de dados](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="a8c83-111">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="a8c83-112">Configurar o nome do Autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="a8c83-112">Configure the name of Employee self service</span></span>

<span data-ttu-id="a8c83-113">Em **Parâmetros do Human Resources**, agora é possível alterar o nome do espaço de trabalho **Autoatendimento para funcionários** para **Autoatendimento**.</span><span class="sxs-lookup"><span data-stu-id="a8c83-113">In **Human Resources parameters**, you can now change the name of the **Employee self service** workspace to **Self service**.</span></span> <span data-ttu-id="a8c83-114">Para obter mais informações, consulte [Alterar o nome do espaço de trabalho Autoatendimento para funcionários](hr-employee-self-service-workspace-name.md)</span><span class="sxs-lookup"><span data-stu-id="a8c83-114">For more information, see [Change Employee self service workspace name](hr-employee-self-service-workspace-name.md)</span></span>

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a><span data-ttu-id="a8c83-115">Acesso para inscrição aberta do gerenciamento de benefícios fora do período</span><span class="sxs-lookup"><span data-stu-id="a8c83-115">Benefits management open enrollment access outside of period</span></span>

<span data-ttu-id="a8c83-116">Esta versão corrige um bug em que os funcionários podiam acessar a inscrição aberta para benefícios fora do período de inscrição ou sem um evento de vida.</span><span class="sxs-lookup"><span data-stu-id="a8c83-116">This release fixes a bug where employees could access benefits open enrollment outside of the enrollment period or without a life event.</span></span> <span data-ttu-id="a8c83-117">Como resultado, se você precisar demonstrar a inscrição aberta no Autoatendimento para funcionários, deverá ajustar as datas de inscrição aberta para hoje (ou antes disso) para torná-la acessível.</span><span class="sxs-lookup"><span data-stu-id="a8c83-117">As a result, if you need to demo open enrollment in Employee self service, you must adjust the open enrollment dates to today (or earlier) to make it accessible.</span></span> <span data-ttu-id="a8c83-118">Você pode alterar essa configuração em **Gerenciamento de benefícios > Regras e períodos de opções**.</span><span class="sxs-lookup"><span data-stu-id="a8c83-118">You can change this setting under **Benefits management > Rules and options periods**.</span></span>

## <a name="email-employee-enrollment-confirmation"></a><span data-ttu-id="a8c83-119">Confirmação de inscrição de funcionário por email</span><span class="sxs-lookup"><span data-stu-id="a8c83-119">Email employee enrollment confirmation</span></span>

<span data-ttu-id="a8c83-120">Agora, você pode enviar emails aos funcionários depois que eles concluem a seleção de benefícios.</span><span class="sxs-lookup"><span data-stu-id="a8c83-120">You can now send emails to employees after they complete their benefits selection.</span></span> <span data-ttu-id="a8c83-121">Você pode enviar uma mensagem padrão ou usar um modelo de email da organização.</span><span class="sxs-lookup"><span data-stu-id="a8c83-121">You can either send a default message or use an organization email template.</span></span> <span data-ttu-id="a8c83-122">Essas configurações estão em **Parâmetros do Human Resources > Gerenciamento de benefícios**.</span><span class="sxs-lookup"><span data-stu-id="a8c83-122">These settings are under **Human resource parameters > Benefits management**.</span></span>

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a><span data-ttu-id="a8c83-123">Licença cancelada ainda aparece na próxima folga no espaço de trabalho Pessoas (441358)</span><span class="sxs-lookup"><span data-stu-id="a8c83-123">Canceled leave still appears in upcoming time off on People workspace (441358)</span></span>

<span data-ttu-id="a8c83-124">A licença cancelada não é mais exibida como próxima folga nos cartões de licença do espaço de trabalho **Pessoas**.</span><span class="sxs-lookup"><span data-stu-id="a8c83-124">Canceled leave no longer displays as upcoming time off on the leave cards in the **People** workspace.</span></span>

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a><span data-ttu-id="a8c83-125">Não é possível usar a propriedade de entidade de departamento na entidade PositionV2 (456486)</span><span class="sxs-lookup"><span data-stu-id="a8c83-125">Unable to use the department entity property in the PositionV2 entity (456486)</span></span>

<span data-ttu-id="a8c83-126">Agora você pode adicionar um departamento sem criar uma relação duplicada.</span><span class="sxs-lookup"><span data-stu-id="a8c83-126">You can now add a department without creating a duplicate relation.</span></span>

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a><span data-ttu-id="a8c83-127">PayrollWorkerEnrolledBenefitDetailEntity deve usar somente o campo calculado para planos de aposentadoria (459779)</span><span class="sxs-lookup"><span data-stu-id="a8c83-127">PayrollWorkerEnrolledBenefitDetailEntity should only use calculated field for retirement plans (459779)</span></span>

<span data-ttu-id="a8c83-128">Ao exportar a entidade **PayrollWorkerEnrolledBenefitDetailEntity**, a exportação determina se ela deve usar um campo calculado com base em uma tabela de taxas ou usar o campo **ContributionAmountCur** na tabela de backup.</span><span class="sxs-lookup"><span data-stu-id="a8c83-128">When exporting the **PayrollWorkerEnrolledBenefitDetailEntity** entity, the export determines whether it should use a calculated field based on a rate table or use the **ContributionAmountCur** field on the backing table.</span></span> <span data-ttu-id="a8c83-129">A lógica usada pela entidade de dados usa a tabela de taxas nas situações em que o aplicativo normalmente não usa.</span><span class="sxs-lookup"><span data-stu-id="a8c83-129">The logic used by the data entity uses the rate table in situations where the application normally doesn't.</span></span> <span data-ttu-id="a8c83-130">Essa lógica faz com que as exportações da entidade retornem um valor zero para essa coluna, porque não há uma tabela de taxas de cálculo e o produto não permite que o cliente especifique uma.</span><span class="sxs-lookup"><span data-stu-id="a8c83-130">This logic causes the entity exports to return a zero value for this column, because there's no calculation rate table and the product doesn't allow the customer to specify one.</span></span>
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a><span data-ttu-id="a8c83-131">Traduções confusas no idioma tcheco em Gerenciamento de pessoal e Autoatendimento para funcionários (400276)</span><span class="sxs-lookup"><span data-stu-id="a8c83-131">Confusing translations in Czech language in Personnel management and Employee self service (400276)</span></span>

<span data-ttu-id="a8c83-132">Esta versão corrige as traduções de **Diretório da empresa**, **Próximo curso registrado**, **Trabalho** e **Posição**.</span><span class="sxs-lookup"><span data-stu-id="a8c83-132">This release corrects the translations for **Company directory**, **Next registered course**, **Job**, and **Position**.</span></span>
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a><span data-ttu-id="a8c83-133">A tabela WorkCalendarEmployment não tem os campos de sistema criados e modificados habilitados (460171)</span><span class="sxs-lookup"><span data-stu-id="a8c83-133">The WorkCalendarEmployment table doesn't have the created and modified system fields enabled (460171)</span></span>

<span data-ttu-id="a8c83-134">Os campos do sistema criados e modificados agora estão habilitados na tabela **WorkCalendarEmployment** do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a8c83-134">Created and modified system fields are now enabled on the **WorkCalendarEmployment** table in Human Resources.</span></span>
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a><span data-ttu-id="a8c83-135">Exceção de referência nula para Contratar e adicionar detalhes de futuro funcionário (455475)</span><span class="sxs-lookup"><span data-stu-id="a8c83-135">Null reference exception for Hire and add details for future employee (455475)</span></span>

<span data-ttu-id="a8c83-136">Esta versão corrige um erro (referência nula) em uma entrada de funcionário simplificada quando você contrata um funcionário usando a opção **Contratar e adicionar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a8c83-136">This release corrects an error (null reference) in streamlined employee entry when you hire an employee using the option to **Hire and add details**.</span></span>

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a><span data-ttu-id="a8c83-137">Alterações feitas na entidade Trabalhador do Dataverse não são refletidas no Human Resources (455652)</span><span class="sxs-lookup"><span data-stu-id="a8c83-137">Changes made in the Dataverse Worker entity don't reflect in Human Resources (455652)</span></span>

<span data-ttu-id="a8c83-138">Agora, as alterações feitas nos seguintes campos da entidade **Trabalhador** do Dataverse serão mostradas no Human Resources:</span><span class="sxs-lookup"><span data-stu-id="a8c83-138">Changes made to the following fields in the **Worker** entity in Dataverse will now show up in Human Resources:</span></span>

- <span data-ttu-id="a8c83-139">**Trabalha de casa**</span><span class="sxs-lookup"><span data-stu-id="a8c83-139">**Works from home**</span></span>
- <span data-ttu-id="a8c83-140">**Aniversário de tempo de serviço**</span><span class="sxs-lookup"><span data-stu-id="a8c83-140">**Seniority date**</span></span>
- <span data-ttu-id="a8c83-141">**Data do aniversário de tempo de serviço**</span><span class="sxs-lookup"><span data-stu-id="a8c83-141">**Anniversary date**</span></span>
- <span data-ttu-id="a8c83-142">**Data original da contratação**</span><span class="sxs-lookup"><span data-stu-id="a8c83-142">**Original hire date**</span></span>

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a><span data-ttu-id="a8c83-143">O nível salarial correto não está padronizado com base no trabalho atribuído à posição (394136)</span><span class="sxs-lookup"><span data-stu-id="a8c83-143">Correct compensation level doesn't default based on the job assigned to the position (394136)</span></span>

<span data-ttu-id="a8c83-144">Com esta alteração, o nível salarial correto foi padronizado com base nos registros de **Data de efetivação** para **Detalhes da posição** e **Data de início** de **Atribuição do plano de remuneração**.</span><span class="sxs-lookup"><span data-stu-id="a8c83-144">With this change, the correct compensation level defaults based on the **Date effective** records for the **Position details** and the **Start date** of the **Compensation plan assignment**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a8c83-145">Em visualização</span><span class="sxs-lookup"><span data-stu-id="a8c83-145">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="a8c83-146">Campos obrigatórios</span><span class="sxs-lookup"><span data-stu-id="a8c83-146">Mandatory fields</span></span> 

<span data-ttu-id="a8c83-147">Agora você pode tornar campos obrigatórios usando recursos de personalização do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a8c83-147">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="a8c83-148">Este recurso exige **Exibições salvas**.</span><span class="sxs-lookup"><span data-stu-id="a8c83-148">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="a8c83-149">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="a8c83-149">Human Resources application in Teams</span></span>

<span data-ttu-id="a8c83-150">Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a8c83-150">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="a8c83-151">Eles podem interagir com um bot para criar solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="a8c83-151">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="a8c83-152">Para obter mais informações, consulte [aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="a8c83-152">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="a8c83-153">Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="a8c83-153">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="a8c83-154">Entidades de gerenciamento de benefícios estão sendo liberadas.</span><span class="sxs-lookup"><span data-stu-id="a8c83-154">Benefits management entities are releasing.</span></span> <span data-ttu-id="a8c83-155">As entidades DMF permitem que você importe e exporte dados para configurar facilmente o gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="a8c83-155">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="a8c83-156">Um modelo de gerenciamento de benefícios estará disponível para mover dados.</span><span class="sxs-lookup"><span data-stu-id="a8c83-156">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="a8c83-157">O modelo exporta e importa os dados sequencialmente para respeitar as dependências de dados.</span><span class="sxs-lookup"><span data-stu-id="a8c83-157">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="a8c83-158">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="a8c83-158">Buy and sell leave</span></span> 

<span data-ttu-id="a8c83-159">Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças.</span><span class="sxs-lookup"><span data-stu-id="a8c83-159">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="a8c83-160">Esse processo costuma ser gerenciado manualmente.</span><span class="sxs-lookup"><span data-stu-id="a8c83-160">This process is often managed manually.</span></span> <span data-ttu-id="a8c83-161">Esse recurso automatiza o gerenciamento de políticas e solicitações para o departamento de RH.</span><span class="sxs-lookup"><span data-stu-id="a8c83-161">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="a8c83-162">Ele simplifica o processo de gerenciamento de licenças e ajuda a eliminar erros.</span><span class="sxs-lookup"><span data-stu-id="a8c83-162">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="a8c83-163">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="a8c83-163">For more information, see:</span></span>

- [<span data-ttu-id="a8c83-164">Gerenciar políticas de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="a8c83-164">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="a8c83-165">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="a8c83-165">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="a8c83-166">Deixar o acúmulo para uma única empresa ou um plano</span><span class="sxs-lookup"><span data-stu-id="a8c83-166">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="a8c83-167">Os clientes podem processar acúmulos para uma única empresa ou um único plano de licença e de ausência.</span><span class="sxs-lookup"><span data-stu-id="a8c83-167">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="a8c83-168">Essa capacidade esclarece sobre o processo de competência para clientes com diferentes políticas de anos de licença ou acúmulo de licenças.</span><span class="sxs-lookup"><span data-stu-id="a8c83-168">This ability provides clarity for the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="a8c83-169">Para obter mais informações, consulte [Acumular licenças por empresa ou por plano de licença](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="a8c83-169">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="a8c83-170">Adicionar anexos a solicitações de folga</span><span class="sxs-lookup"><span data-stu-id="a8c83-170">Add attachments to time-off requests</span></span>

<span data-ttu-id="a8c83-171">A capacidade de adicionar anexos a solicitações de licença aprovadas é crítica no ambiente de COVID-19 atual.</span><span class="sxs-lookup"><span data-stu-id="a8c83-171">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="a8c83-172">Os funcionários agora podem adicionar esses anexos.</span><span class="sxs-lookup"><span data-stu-id="a8c83-172">Employees can now add these attachments.</span></span> <span data-ttu-id="a8c83-173">Eles também estão mais informados sobre como as atualizações são feitas para deixar solicitações.</span><span class="sxs-lookup"><span data-stu-id="a8c83-173">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="a8c83-174">Para obter mais informações, consulte [Adicionar um anexo a uma solicitação existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="a8c83-174">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="a8c83-175">Adicionar código de motivo a suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="a8c83-175">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="a8c83-176">Os códigos de motivo foram adicionados à suspensão de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="a8c83-176">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="a8c83-177">Regras de postergação</span><span class="sxs-lookup"><span data-stu-id="a8c83-177">Carry forward rules</span></span> 

<span data-ttu-id="a8c83-178">Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos.</span><span class="sxs-lookup"><span data-stu-id="a8c83-178">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="a8c83-179">Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias.</span><span class="sxs-lookup"><span data-stu-id="a8c83-179">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="a8c83-180">Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="a8c83-180">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="a8c83-181">Suspender a acumulação de licenças para tipos de licença especificados</span><span class="sxs-lookup"><span data-stu-id="a8c83-181">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="a8c83-182">Você pode criar uma regra para suspender os acúmulos de licença para funcionários com solicitações de licença inseridas para licenças não pagas.</span><span class="sxs-lookup"><span data-stu-id="a8c83-182">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="a8c83-183">A licença não remunerada pode ser um tipo, mas não precisa ser.</span><span class="sxs-lookup"><span data-stu-id="a8c83-183">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="a8c83-184">Você pode suspender qualquer licença com base em outro tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="a8c83-184">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="a8c83-185">Entidade DMF disponível para suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="a8c83-185">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="a8c83-186">Uma entidade DMF disponível para suspensões de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="a8c83-186">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="a8c83-187">Em breve</span><span class="sxs-lookup"><span data-stu-id="a8c83-187">Coming soon</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="a8c83-188">Entidades de lista de verificação incluídas no Dataverse</span><span class="sxs-lookup"><span data-stu-id="a8c83-188">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="a8c83-189">Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a8c83-189">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8c83-190">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a8c83-190">See also</span></span>

[<span data-ttu-id="a8c83-191">Novidades ou alterações no Human Resources</span><span class="sxs-lookup"><span data-stu-id="a8c83-191">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="a8c83-192">Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources</span><span class="sxs-lookup"><span data-stu-id="a8c83-192">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="a8c83-193">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="a8c83-193">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="a8c83-194">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="a8c83-194">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]