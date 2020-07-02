---
title: Novidades ou alterações no Dynamics 365 Human Resources (11 de junho de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 6/16/2020
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
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39f18dc92fb01f9a0437f4166c0f08f8d6b1b81b
ms.sourcegitcommit: 218e22014a964b8b52fc0152e355b07b0b84ae2c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "3456611"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a><span data-ttu-id="3cb11-103">Novidades ou alterações no Dynamics 365 Human Resources (11 de junho de 2020)</span><span class="sxs-lookup"><span data-stu-id="3cb11-103">What's new or changed in Dynamics 365 Human Resources (June 11, 2020)</span></span>

<span data-ttu-id="3cb11-104">Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3cb11-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="3cb11-105">As alterações se aplicam ao número da compilação 8.1.3316.</span><span class="sxs-lookup"><span data-stu-id="3cb11-105">Changes apply to build number 8.1.3316.</span></span> <span data-ttu-id="3cb11-106">Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.</span><span class="sxs-lookup"><span data-stu-id="3cb11-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a><span data-ttu-id="3cb11-107">O formulário de funcionário simplificado às vezes faz com que os botões fechar (X) do formulário filho parem de funcionar (442369)</span><span class="sxs-lookup"><span data-stu-id="3cb11-107">Streamlined employee form sometimes causes child form close (X) buttons to stop working (442369)</span></span>

<span data-ttu-id="3cb11-108">Com o formulário **Trabalhador** habilitado, o botão fechar (**X**) ocasionalmente não funcionava em formulários filhos.</span><span class="sxs-lookup"><span data-stu-id="3cb11-108">When the new **Worker** form was enabled, the close (**X**) button occasionally didn't work on child forms.</span></span> <span data-ttu-id="3cb11-109">Esse problema era intermitente.</span><span class="sxs-lookup"><span data-stu-id="3cb11-109">This problem was intermittent.</span></span> <span data-ttu-id="3cb11-110">Você pode fechar o formulário depois de sair e voltar para ele.</span><span class="sxs-lookup"><span data-stu-id="3cb11-110">You could close the form after leaving and coming back to it.</span></span> <span data-ttu-id="3cb11-111">Por exemplo, você pode selecionar um item de menu à esquerda, e navegar novamente para o formulário **Trabalhador** e fechá-lo.</span><span class="sxs-lookup"><span data-stu-id="3cb11-111">For example, you could select a menu item on the left, and navigate back to the **Worker** form, and then close it.</span></span> <span data-ttu-id="3cb11-112">A versão desta semana corrige esse problema.</span><span class="sxs-lookup"><span data-stu-id="3cb11-112">This week's release fixes this problem.</span></span> 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a><span data-ttu-id="3cb11-113">A entidade Pessoa de contato pessoal do trabalhador não exporta contatos pessoais com um tipo de relacionamento pai</span><span class="sxs-lookup"><span data-stu-id="3cb11-113">The Worker personal contact person entity doesn't export personal contacts with a parent relationship type</span></span>

<span data-ttu-id="3cb11-114">Com esta versão, a entidade **Pessoa de contato pessoal do trabalhador** exporta todos os tipos de relacionamento.</span><span class="sxs-lookup"><span data-stu-id="3cb11-114">With this release, the **Worker personal contact person** entity exports all relationship types.</span></span>

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a><span data-ttu-id="3cb11-115">HcmPositionWorkerAssignmentV2Entity deve fazer parte do pacote de integração da folha de pagamento Ceridian por padrão (448506)</span><span class="sxs-lookup"><span data-stu-id="3cb11-115">The HcmPositionWorkerAssignmentV2Entity should be part of the Ceridian payroll integration package by default (448506)</span></span>

<span data-ttu-id="3cb11-116">Com essa alteração, **HcmPositionWorkerAssignmentV2Entity** é incluído no pacote de integração da folha de pagamento Ceridian.</span><span class="sxs-lookup"><span data-stu-id="3cb11-116">With this change, the **HcmPositionWorkerAssignmentV2Entity** is included in the Ceridian payroll integration package.</span></span>

## <a name="in-preview"></a><span data-ttu-id="3cb11-117">Em visualização</span><span class="sxs-lookup"><span data-stu-id="3cb11-117">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="3cb11-118">Log de banco de dados</span><span class="sxs-lookup"><span data-stu-id="3cb11-118">Database logging</span></span>

<span data-ttu-id="3cb11-119">O recurso de log de banco de dados permite determinar as tabelas e os campos que devem ser monitorados.</span><span class="sxs-lookup"><span data-stu-id="3cb11-119">The database logging feature allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="3cb11-120">Ele também permite que você determine os eventos que devem disparar o controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="3cb11-120">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="3cb11-121">Use os recursos de log de banco de dados para ver essas alterações ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="3cb11-121">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="3cb11-122">Para obter mais informações, consulte [Configurar e gerenciar o log de banco de dados](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="3cb11-122">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="3cb11-123">Aplicativo Human Resources no Teams</span><span class="sxs-lookup"><span data-stu-id="3cb11-123">Human Resources application in Teams</span></span>

<span data-ttu-id="3cb11-124">Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3cb11-124">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="3cb11-125">Eles podem interagir com um bot para criar solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="3cb11-125">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="3cb11-126">Para obter mais informações, consulte [aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="3cb11-126">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="3cb11-127">Entidades da estrutura de gerenciamento de dados (DMF) para gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="3cb11-127">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="3cb11-128">Entidades de gerenciamento de benefícios estão sendo liberadas.</span><span class="sxs-lookup"><span data-stu-id="3cb11-128">Benefits management entities are releasing.</span></span> <span data-ttu-id="3cb11-129">As entidades DMF permitem que você importe e exporte dados para configurar facilmente o gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="3cb11-129">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="3cb11-130">Um modelo de gerenciamento de benefícios estará disponível para mover dados.</span><span class="sxs-lookup"><span data-stu-id="3cb11-130">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="3cb11-131">O modelo exporta e importa os dados sequencialmente para respeitar as dependências de dados.</span><span class="sxs-lookup"><span data-stu-id="3cb11-131">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="3cb11-132">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="3cb11-132">Buy and sell leave</span></span> 

<span data-ttu-id="3cb11-133">Algumas organizações fornecem um benefício que permite que os funcionários comprem ou vendam licenças.</span><span class="sxs-lookup"><span data-stu-id="3cb11-133">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="3cb11-134">Esse processo costuma ser gerenciado manualmente.</span><span class="sxs-lookup"><span data-stu-id="3cb11-134">This process is often managed manually.</span></span> <span data-ttu-id="3cb11-135">Esse recurso automatiza o gerenciamento de políticas e solicitações para o departamento de RH.</span><span class="sxs-lookup"><span data-stu-id="3cb11-135">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="3cb11-136">Ele simplifica o processo de gerenciamento de licenças e ajuda a eliminar erros.</span><span class="sxs-lookup"><span data-stu-id="3cb11-136">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="3cb11-137">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="3cb11-137">For more information, see:</span></span>

- [<span data-ttu-id="3cb11-138">Gerenciar políticas de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="3cb11-138">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="3cb11-139">Comprar e vender licenças</span><span class="sxs-lookup"><span data-stu-id="3cb11-139">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="3cb11-140">Deixar o acúmulo para uma única empresa ou um plano</span><span class="sxs-lookup"><span data-stu-id="3cb11-140">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="3cb11-141">Os clientes podem processar acúmulos para uma única empresa ou um único plano de licença e de ausência.</span><span class="sxs-lookup"><span data-stu-id="3cb11-141">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="3cb11-142">Essa capacidade oferece esclarecimentos sobre o processo de acumulação para clientes com anos de licença diferentes ou para manter políticas de competência.</span><span class="sxs-lookup"><span data-stu-id="3cb11-142">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="3cb11-143">Para obter mais informações, consulte [Acumular licenças por empresa ou por plano de licença](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="3cb11-143">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="3cb11-144">Adicionar anexos a solicitações de folga</span><span class="sxs-lookup"><span data-stu-id="3cb11-144">Add attachments to time off requests</span></span>

<span data-ttu-id="3cb11-145">A capacidade de adicionar anexos a solicitações de licença aprovadas é crítica no ambiente de COVID-19 atual.</span><span class="sxs-lookup"><span data-stu-id="3cb11-145">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="3cb11-146">Os funcionários agora podem adicionar esses anexos.</span><span class="sxs-lookup"><span data-stu-id="3cb11-146">Employees can now add these attachments.</span></span> <span data-ttu-id="3cb11-147">Eles também estão mais informados sobre como as atualizações são feitas para deixar solicitações.</span><span class="sxs-lookup"><span data-stu-id="3cb11-147">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="3cb11-148">Para obter mais informações, consulte [Adicionar um anexo a uma solicitação existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="3cb11-148">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="3cb11-149">Adicionar código de motivo a suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="3cb11-149">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="3cb11-150">Os códigos de motivo foram adicionados à suspensão de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="3cb11-150">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="3cb11-151">Regras de postergação</span><span class="sxs-lookup"><span data-stu-id="3cb11-151">Carry forward rules</span></span> 

<span data-ttu-id="3cb11-152">Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos.</span><span class="sxs-lookup"><span data-stu-id="3cb11-152">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="3cb11-153">Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias.</span><span class="sxs-lookup"><span data-stu-id="3cb11-153">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="3cb11-154">Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="3cb11-154">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="3cb11-155">Suspender a acumulação de licenças para tipos de licença especificados</span><span class="sxs-lookup"><span data-stu-id="3cb11-155">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="3cb11-156">Você pode criar uma regra para suspender os acúmulos de licença para funcionários com solicitações de licença inseridas para licenças não pagas.</span><span class="sxs-lookup"><span data-stu-id="3cb11-156">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="3cb11-157">A licença não remunerada pode ser um tipo, mas não precisa ser.</span><span class="sxs-lookup"><span data-stu-id="3cb11-157">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="3cb11-158">Você pode suspender qualquer licença com base em outro tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="3cb11-158">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="3cb11-159">Entidade DMF disponível para suspensões de acúmulos</span><span class="sxs-lookup"><span data-stu-id="3cb11-159">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="3cb11-160">Uma entidade DMF disponível para suspensões de acúmulos.</span><span class="sxs-lookup"><span data-stu-id="3cb11-160">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="3cb11-161">Em breve</span><span class="sxs-lookup"><span data-stu-id="3cb11-161">Coming soon</span></span>

## <a name="new-platform-capabilities"></a><span data-ttu-id="3cb11-162">Novos recursos da plataforma</span><span class="sxs-lookup"><span data-stu-id="3cb11-162">New platform capabilities</span></span> 

<span data-ttu-id="3cb11-163">Você poderá tornar os campos obrigatórios usando a personalização.</span><span class="sxs-lookup"><span data-stu-id="3cb11-163">You'll be able to make fields mandatory by using personalization.</span></span> <span data-ttu-id="3cb11-164">Este recurso exigirá que você habilite **Exibições salvas**.</span><span class="sxs-lookup"><span data-stu-id="3cb11-164">This feature will require you to enable **Saved views**.</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="3cb11-165">Configurar o nome do autoatendimento para Funcionários</span><span class="sxs-lookup"><span data-stu-id="3cb11-165">Configure the name of Employee self-service</span></span>

<span data-ttu-id="3cb11-166">Uma nova opção estará disponível nos parâmetros de Recursos Humanos para atualizar o nome do espaço de trabalho de autoatendimento para Funcionários para Autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="3cb11-166">A new option will be available in Human Resources parameters to update the name of the Employee self service workspace to Self service.</span></span> 
