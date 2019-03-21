---
title: Novidades ou alterações no Dynamics 365 for Talent (5 de março de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e6b490a696dc0a00c47e56f57373f330d0e53dde
ms.sourcegitcommit: 479b8cda7e411830bf1f579fab3692c980dcf850
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2019
ms.locfileid: "782785"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-5-2019"></a><span data-ttu-id="73155-103">Novidades ou alterações no Dynamics 365 for Talent (5 de março de 2019)</span><span class="sxs-lookup"><span data-stu-id="73155-103">What's new or changed in Dynamics 365 for Talent (March 5, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="73155-104">Este tópico descreve os recursos novos ou alterados no Talent</span><span class="sxs-lookup"><span data-stu-id="73155-104">This topic describes features that are either new or changed in Talent</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="73155-105">Alterações no Attract</span><span class="sxs-lookup"><span data-stu-id="73155-105">Changes in Attract</span></span>

### <a name="extending-option-sets-in-attract"></a><span data-ttu-id="73155-106">Extensão dos conjuntos de opção no Attract</span><span class="sxs-lookup"><span data-stu-id="73155-106">Extending option sets in Attract</span></span>

<span data-ttu-id="73155-107">Em Attract, há vários campos que são conjuntos de opção dentro do Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="73155-107">In Attract, there are multiple fields that are option sets within the Common Data Service (CDS).</span></span> <span data-ttu-id="73155-108">Novas funcionalidades foram apresentadas para estender os conjuntos de opção, começando com os campos Motivo de **Rejeição**, **Tipo de emprego** e **Tipo de senioridade**.</span><span class="sxs-lookup"><span data-stu-id="73155-108">New capabilities have been introduced to extend the option sets, beginning with the **Rejection** reason field, **Employment type** field, and **Seniority type** field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73155-109">A postagem de trabalho na funcionalidade do LinkedIn requer o uso de campos **Tipo de emprego** e **Tipo de senioridade** na página **Detalhes de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="73155-109">The job posting to LinkedIn functionality requires the use of the **Employment type** and **Seniority type** fields on the **Job details** page.</span></span> <span data-ttu-id="73155-110">Os valores padrão nesses campos são compatíveis com LinkedIn e são exibidos quando o trabalho é postado.</span><span class="sxs-lookup"><span data-stu-id="73155-110">The default values in these fields are supported by LinkedIn and are displayed when the job is posted.</span></span> <span data-ttu-id="73155-111">Se estiver postando trabalhos no LinkedIn e modificar os valores de conjunto de opção existentes para esses campos, o trabalho será postado, mas o LinkedIn não exibirá os valores **Tipo de trabalho** e **Tipo de senioridade** personalizados.</span><span class="sxs-lookup"><span data-stu-id="73155-111">If you are posting jobs to LinkedIn and you modify the existing option set values for these fields, the job will still post, but LinkedIn will not display the custom **Employment type** and **Seniority type** values.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="73155-112">Alterações de Integração</span><span class="sxs-lookup"><span data-stu-id="73155-112">Changes in Onboarding</span></span>

### <a name="private-preview-for-onboard-teams"></a><span data-ttu-id="73155-113">Visualização privada de equipes de integração</span><span class="sxs-lookup"><span data-stu-id="73155-113">Private preview for Onboard teams</span></span>
<span data-ttu-id="73155-114">Agora você pode facilmente compartilhar e colaborar em modelos entre toda a organização.</span><span class="sxs-lookup"><span data-stu-id="73155-114">You can now easily share and collaborate on templates across your entire organization.</span></span> <span data-ttu-id="73155-115">Para obter mais informações, consulte [Compartilhar melhores práticas entre sua organização usando Equipes de integração](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span><span class="sxs-lookup"><span data-stu-id="73155-115">For more information, see [Share best practices across your organization using Onboard Teams](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).</span></span>

### <a name="private-preview-for-assignee-placeholders"></a><span data-ttu-id="73155-116">Visualização privada dos espaços reservados do destinatário</span><span class="sxs-lookup"><span data-stu-id="73155-116">Private preview for assignee placeholders</span></span>
<span data-ttu-id="73155-117">Você pode enriquecer seus modelos atribuindo atividades a funções em vez de indivíduos.</span><span class="sxs-lookup"><span data-stu-id="73155-117">You can enrich your templates by assigning activities to roles instead of individuals.</span></span> <span data-ttu-id="73155-118">Funções são atribuídas a pessoas no momento da criação da guia.</span><span class="sxs-lookup"><span data-stu-id="73155-118">Roles are then assigned to individuals at the time of guide creation.</span></span> <span data-ttu-id="73155-119">Para obter mais informações, consulte [Simplificar administração de guia atribuindo atividades a funções](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span><span class="sxs-lookup"><span data-stu-id="73155-119">For more information, see [Streamline guide administration by assigning activities to roles](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="73155-120">Alterações no Core HR</span><span class="sxs-lookup"><span data-stu-id="73155-120">Changes in Core HR</span></span>
<span data-ttu-id="73155-121">**Compilação 8.1.2178**</span><span class="sxs-lookup"><span data-stu-id="73155-121">**Build 8.1.2178**</span></span>

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a><span data-ttu-id="73155-122">Configure fluxos de trabalho para aprovar automaticamente ou seguir fluxos de trabalho quando um RH ou gerente de linha enviar ou atualizar solicitações de folgas</span><span class="sxs-lookup"><span data-stu-id="73155-122">Configure workflow to auto-approve or follow workflow when an HR or line manager submits or updates time off requests</span></span>
<span data-ttu-id="73155-123">Novas condições de fluxo de trabalho foram adicionadas para permitir que solicitações sejam aprovadas automaticamente se enviadas por um gerente de funcionário ou por um RH.</span><span class="sxs-lookup"><span data-stu-id="73155-123">New workflow conditions have been added to allow for leave requests to be automatically approved if submitted by an employee’s manager or by HR.</span></span> <span data-ttu-id="73155-124">Uma forma de obter essa aprovação automática em um fluxo de trabalho é habilitar uma ação automática na aprovação do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="73155-124">One way to achieve this auto-approval on a workflow is to enable an automatic action on the workflow approval.</span></span>

<span data-ttu-id="73155-125">As condições que foram adicionadas incluem:</span><span class="sxs-lookup"><span data-stu-id="73155-125">The conditions that have been added include:</span></span>

- <span data-ttu-id="73155-126">Enviado por - Usado para avaliar o ID de usuário do sistema do usuário que enviou a solicitação para fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="73155-126">Submitted by - Used to evaluate the system user ID of the user who submitted the request to workflow.</span></span>
- <span data-ttu-id="73155-127">Enviado em nome de - Usado para avaliar se a solicitação foi enviada em nome de um trabalhador associado à solicitação.</span><span class="sxs-lookup"><span data-stu-id="73155-127">Submitted on behalf of - Used to evaluate if the leave request was submitted on behalf of the worker associated to the request.</span></span>
- <span data-ttu-id="73155-128">Enviado por recursos humanos - Usado para avaliar se o usuário do sistema que enviou a solicitação para o fluxo de trabalho está em uma função de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="73155-128">Submitted by human resources - Used to evaluate if the system user who submitted the request to workflow is in a Human Resources role.</span></span>
- <span data-ttu-id="73155-129">Enviado pelo gerente - Usado para avaliar se o usuário que enviou a solicitação para o fluxo de trabalho é um gerente de hierarquia de linha do trabalhador associado à solicitação.</span><span class="sxs-lookup"><span data-stu-id="73155-129">Submitted by manager - Used to evaluate if the user who submitted the leave request to workflow is a line hierarchy manager of the worker associated to the request.</span></span>

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a><span data-ttu-id="73155-130">Habilitar remuneração fixa de funcionário para atribuições de cargo futuras</span><span class="sxs-lookup"><span data-stu-id="73155-130">Enable employee fixed compensation for future position assignments</span></span>
<span data-ttu-id="73155-131">É normal que funcionários entrem em uma organização com uma data de início futura.</span><span class="sxs-lookup"><span data-stu-id="73155-131">It is typical for employees to join an organization with a future start date.</span></span> <span data-ttu-id="73155-132">Esta alteração permite a definição de remuneração fixa para funcionários com atribuições de cargo futuras.</span><span class="sxs-lookup"><span data-stu-id="73155-132">This change enables defining fixed compensation for employees with future position assignments.</span></span>

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a><span data-ttu-id="73155-133">Campos de posição de folha de pagamento estão em branco ao editar o cargo</span><span class="sxs-lookup"><span data-stu-id="73155-133">Position Payroll fields are blank when editing the position</span></span>
<span data-ttu-id="73155-134">Com esta alteração, ao solicitar alterações a posições existentes, os campos de folha de pagamento agora mudarão para padrão com valores atuais.</span><span class="sxs-lookup"><span data-stu-id="73155-134">With this change, when requesting changes to existing positions, the payroll fields will now default to the current values.</span></span>

### <a name="other-miscellaneous-bug-fixes"></a><span data-ttu-id="73155-135">Outras correções de bugs diversos</span><span class="sxs-lookup"><span data-stu-id="73155-135">Other miscellaneous bug fixes</span></span>
<span data-ttu-id="73155-136">Outras correções de bugs diversos estão incluídas nesta versão.</span><span class="sxs-lookup"><span data-stu-id="73155-136">Other minor bug fixes are included with this release.</span></span>

### <a name="upgrade-to-cds-for-apps"></a><span data-ttu-id="73155-137">Atualizar para o CDS para aplicativos</span><span class="sxs-lookup"><span data-stu-id="73155-137">Upgrade to CDS for Apps</span></span>
<span data-ttu-id="73155-138">Os prazos finais para atualizar para CDS de Aplicativos estão se aproximando rapidamente.</span><span class="sxs-lookup"><span data-stu-id="73155-138">Deadlines to upgrade to CDS for Apps are quickly approaching.</span></span> <span data-ttu-id="73155-139">Entre na central de administração do PowerApps para determinar se sua base de dados precisa ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="73155-139">Sign in to the PowerApps Admin center to determine if your database needs to be upgraded.</span></span> <span data-ttu-id="73155-140">Para obter mais informações sobre os prazos finais e etapas necessárias para atualização, consulte [Atualizar para Common Data Service para Aplicativos](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).</span><span class="sxs-lookup"><span data-stu-id="73155-140">For more information about deadlines and necessary steps to upgrade, see [Upgrade to Common Data Service for Apps](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).</span></span>

## <a name="coming-soon"></a><span data-ttu-id="73155-141">Em breve</span><span class="sxs-lookup"><span data-stu-id="73155-141">Coming soon</span></span>

###  <a name="advanced-compensation-security-fixed-and-variable"></a><span data-ttu-id="73155-142">Segurança de compensação avançada (fixa e variável)</span><span class="sxs-lookup"><span data-stu-id="73155-142">Advanced compensation security (fixed and variable)</span></span>
<span data-ttu-id="73155-143">Em muitas organizações, gerentes de compensação e benefícios só podem acessar certos registros de compensação, como registros de funcionários executivos ou regionais.</span><span class="sxs-lookup"><span data-stu-id="73155-143">In many organizations, compensation and benefits managers can only access certain compensation records, such as records for executives or regional-based employees.</span></span> <span data-ttu-id="73155-144">Com esta alteração, você pode gerenciar e manter os planos de compensação para populações de funcionário diferentes na organização.</span><span class="sxs-lookup"><span data-stu-id="73155-144">With this change, you can manage and maintain the compensation plans for different employee populations in the organization.</span></span> <span data-ttu-id="73155-145">Planos fixos e variáveis podem receber funções de segurança, que determinarão o acesso de planos e os dados de funcionário relacionados aos planos, como salário ou registros de bônus.</span><span class="sxs-lookup"><span data-stu-id="73155-145">Fixed and variable plans can be assigned security roles, which will determine the access to the plans and the employee data related to the plans, such as salary or bonus records.</span></span> <span data-ttu-id="73155-146">Apenas as funções com acesso determinado poderão processar compensação para esses funcionários.</span><span class="sxs-lookup"><span data-stu-id="73155-146">Only the roles with the given access will be able to process compensation for those employees.</span></span>

###  <a name="platform-update-24"></a><span data-ttu-id="73155-147">Update 24 para plataforma</span><span class="sxs-lookup"><span data-stu-id="73155-147">Platform update 24</span></span>
<span data-ttu-id="73155-148">Para obter detalhes adicionais sobre a atualização da Plataforma 24, consulte [O que há de novo ou o que mudou na atualização da Plataforma 24 do Finance and Operations (março de 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span><span class="sxs-lookup"><span data-stu-id="73155-148">For additional details about Platform update 24, see [What's new or changed in Finance and Operations platform update 24 (March 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).</span></span>
