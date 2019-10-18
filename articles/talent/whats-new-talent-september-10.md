---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (10 de setembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
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
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: 59cb0203422b7d81b5ca0077370fd9cbdb4a7f89
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010075"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-september-10-2018"></a><span data-ttu-id="cad5a-103">Novidades ou alterações no Dynamics 365 Talent: Core HR (10 de setembro de 2018)</span><span class="sxs-lookup"><span data-stu-id="cad5a-103">What's new or changed in Dynamics 365 Talent: Core HR (September 10, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cad5a-104">**Compilação 8.1.138.0**</span><span class="sxs-lookup"><span data-stu-id="cad5a-104">**Build 8.1.138.0**</span></span>

<span data-ttu-id="cad5a-105">Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="cad5a-105">This topic describes features that are either new or changed in Microsoft Dynamics 365 Talent: Core HR.</span></span>

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a><span data-ttu-id="cad5a-106">Permitir hora específica do dia em solicitações de folga (meios dias)</span><span class="sxs-lookup"><span data-stu-id="cad5a-106">Allow specific time of day on time-off requests (half days)</span></span>

<span data-ttu-id="cad5a-107">Se a licença e a ausência estão configuradas para que a folga seja enviada em dias, agora você também pode habilitar uma definição de meio dia.</span><span class="sxs-lookup"><span data-stu-id="cad5a-107">If leave and absence is set up so that time off is submitted in days, you can now also enable a half-day definition.</span></span> <span data-ttu-id="cad5a-108">Em seguida, quando os usuários enviarem solicitações de folga, eles poderão especificar se estão solicitando a primeira metade ou a segunda metade do dia de folga.</span><span class="sxs-lookup"><span data-stu-id="cad5a-108">Then, when users submit time-off requests, they can specify whether they are requesting the first half or the second half of the day off.</span></span>

<span data-ttu-id="cad5a-109">Por padrão, essa opção está desativada.</span><span class="sxs-lookup"><span data-stu-id="cad5a-109">By default, this option is turned off.</span></span> <span data-ttu-id="cad5a-110">Para que os funcionários solicitem a primeira metade ou a segunda metade do dia de folga, você deve ativar essa opção na área **Licença e ausência** dos parâmetros de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="cad5a-110">For employees to request the first half or second half of the day off, you must turn on this option in the **Leave and absence** area of Human resources parameters.</span></span>

<span data-ttu-id="cad5a-111">O privilégio de segurança para esse recurso é Manter parâmetros de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="cad5a-111">The security privilege for this feature is Maintain Human Resources Parameters.</span></span>

## <a name="validation-of-leave-and-absence-entries"></a><span data-ttu-id="cad5a-112">Validação de entradas de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="cad5a-112">Validation of leave and absence entries</span></span>

<span data-ttu-id="cad5a-113">Dependendo da maneira que a licença estiver configurada, os funcionários que tentarem enviar uma solicitação de folga maior do que o dia útil receberão uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="cad5a-113">Depending on how leave is configured, employees who try to submit a time-off request that is longer than their work day receive a warning message.</span></span> <span data-ttu-id="cad5a-114">Ou seja, eles são avisados se tentarem demorar mais de um dia inteiro de folga em qualquer data específica.</span><span class="sxs-lookup"><span data-stu-id="cad5a-114">In other words, they are warned if they try to take more than a full day off on any given date.</span></span>

<span data-ttu-id="cad5a-115">Essa validação está sempre ativada.</span><span class="sxs-lookup"><span data-stu-id="cad5a-115">This validation is always turned on.</span></span> <span data-ttu-id="cad5a-116">Sempre que esses funcionários excederem o limite do dia definido, eles receberão um aviso em sua solicitação de folga.</span><span class="sxs-lookup"><span data-stu-id="cad5a-116">Any time that employees exceed the day threshold that is defined, they receive a warning in their time-off request.</span></span>

## <a name="additional-fields-for-conditional-statements-in-workflows"></a><span data-ttu-id="cad5a-117">Campos adicionais para instruções condicionais em fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="cad5a-117">Additional fields for conditional statements in workflows</span></span>

<span data-ttu-id="cad5a-118">Foram adicionados campos adicionais a instruções condicionais e espaços reservados para vários fluxos de trabalho no Core HR.</span><span class="sxs-lookup"><span data-stu-id="cad5a-118">Additional fields have been added to conditional statements and placeholders for several workflows in Core HR.</span></span>

<span data-ttu-id="cad5a-119">Os seguintes campos foram adicionados aos fluxos de trabalho de remuneração, rescisão e transferência:</span><span class="sxs-lookup"><span data-stu-id="cad5a-119">The following fields have been added to the compensation, termination, and transfer workflows:</span></span>

- <span data-ttu-id="cad5a-120">EmploymentType</span><span class="sxs-lookup"><span data-stu-id="cad5a-120">EmploymentType</span></span>
- <span data-ttu-id="cad5a-121">LegalEntity</span><span class="sxs-lookup"><span data-stu-id="cad5a-121">LegalEntity</span></span>
- <span data-ttu-id="cad5a-122">AdjustedWorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="cad5a-122">AdjustedWorkerStartDate</span></span>
- <span data-ttu-id="cad5a-123">EmployerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="cad5a-123">EmployerNoticeAmount</span></span>
- <span data-ttu-id="cad5a-124">EmployerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="cad5a-124">EmployerUnitOfNotice</span></span>
- <span data-ttu-id="cad5a-125">TransitionDate</span><span class="sxs-lookup"><span data-stu-id="cad5a-125">TransitionDate</span></span>
- <span data-ttu-id="cad5a-126">WorkerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="cad5a-126">WorkerNoticeAmount</span></span>
- <span data-ttu-id="cad5a-127">WorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="cad5a-127">WorkerStartDate</span></span>
- <span data-ttu-id="cad5a-128">WorkerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="cad5a-128">WorkerUnitOfNotice</span></span>
- <span data-ttu-id="cad5a-129">ProbationEndDate</span><span class="sxs-lookup"><span data-stu-id="cad5a-129">ProbationEndDate</span></span>
- <span data-ttu-id="cad5a-130">Cargo</span><span class="sxs-lookup"><span data-stu-id="cad5a-130">Position</span></span>
- <span data-ttu-id="cad5a-131">Sindicato</span><span class="sxs-lookup"><span data-stu-id="cad5a-131">Union</span></span>
- <span data-ttu-id="cad5a-132">Departamento</span><span class="sxs-lookup"><span data-stu-id="cad5a-132">Department</span></span>
- <span data-ttu-id="cad5a-133">PositionType</span><span class="sxs-lookup"><span data-stu-id="cad5a-133">PositionType</span></span>
- <span data-ttu-id="cad5a-134">CompLocation</span><span class="sxs-lookup"><span data-stu-id="cad5a-134">CompLocation</span></span>
- <span data-ttu-id="cad5a-135">Cargo</span><span class="sxs-lookup"><span data-stu-id="cad5a-135">Title</span></span>
- <span data-ttu-id="cad5a-136">Trabalho</span><span class="sxs-lookup"><span data-stu-id="cad5a-136">Job</span></span>
- <span data-ttu-id="cad5a-137">JobType</span><span class="sxs-lookup"><span data-stu-id="cad5a-137">JobType</span></span>
- <span data-ttu-id="cad5a-138">JobFamily</span><span class="sxs-lookup"><span data-stu-id="cad5a-138">JobFamily</span></span>
- <span data-ttu-id="cad5a-139">JobFunction</span><span class="sxs-lookup"><span data-stu-id="cad5a-139">JobFunction</span></span>

<span data-ttu-id="cad5a-140">Os seguintes campos foram adicionados ao fluxo de trabalho de cargo:</span><span class="sxs-lookup"><span data-stu-id="cad5a-140">The following fields have been added to the position workflow:</span></span>

- <span data-ttu-id="cad5a-141">Cargo</span><span class="sxs-lookup"><span data-stu-id="cad5a-141">Position</span></span>
- <span data-ttu-id="cad5a-142">Sindicato</span><span class="sxs-lookup"><span data-stu-id="cad5a-142">Union</span></span>
- <span data-ttu-id="cad5a-143">Departamento</span><span class="sxs-lookup"><span data-stu-id="cad5a-143">Department</span></span>
- <span data-ttu-id="cad5a-144">PositionType</span><span class="sxs-lookup"><span data-stu-id="cad5a-144">PositionType</span></span>
- <span data-ttu-id="cad5a-145">CompLocation</span><span class="sxs-lookup"><span data-stu-id="cad5a-145">CompLocation</span></span>
- <span data-ttu-id="cad5a-146">Cargo</span><span class="sxs-lookup"><span data-stu-id="cad5a-146">Title</span></span>
- <span data-ttu-id="cad5a-147">Trabalho</span><span class="sxs-lookup"><span data-stu-id="cad5a-147">Job</span></span>
- <span data-ttu-id="cad5a-148">JobType</span><span class="sxs-lookup"><span data-stu-id="cad5a-148">JobType</span></span>
- <span data-ttu-id="cad5a-149">JobFamily</span><span class="sxs-lookup"><span data-stu-id="cad5a-149">JobFamily</span></span>
- <span data-ttu-id="cad5a-150">JobFunction</span><span class="sxs-lookup"><span data-stu-id="cad5a-150">JobFunction</span></span>

<span data-ttu-id="cad5a-151">Os campos em instruções condicionais e espaços reservados estão disponíveis a todos os usuários que têm acesso para configurar os fluxos de trabalho mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cad5a-151">Fields in conditional statements and placeholders are available to all users who have access to configure the previously mentioned workflows.</span></span>

## <a name="navigation-to-attract-from-personnel-management"></a><span data-ttu-id="cad5a-152">Navegação para o Attract no gerenciamento de equipes</span><span class="sxs-lookup"><span data-stu-id="cad5a-152">Navigation to Attract from personnel management</span></span>

<span data-ttu-id="cad5a-153">No gerenciamento de equipes, se o Attract não foi configurado, a seção **Candidatos a contratar** direcionará os usuários para a introdução ao Attract, em vez de mostrar a mensagem "Não encontramos nada para mostrar aqui".</span><span class="sxs-lookup"><span data-stu-id="cad5a-153">In personnel management, if Attract hasn't been set up, the **Candidates to hire** section directs users to get started with Attract instead of showing the message, "We didn't find anything to show here."</span></span>

## <a name="other-changes"></a><span data-ttu-id="cad5a-154">Outras alterações</span><span class="sxs-lookup"><span data-stu-id="cad5a-154">Other changes</span></span>

<span data-ttu-id="cad5a-155">Esta versão inclui várias correções de bug adicionais:</span><span class="sxs-lookup"><span data-stu-id="cad5a-155">This release includes several additional bug fixes:</span></span>

- <span data-ttu-id="cad5a-156">Quando um prestador de serviço é contratado, a guia **Remuneração** não deve estar disponível na página de solicitação/ação.</span><span class="sxs-lookup"><span data-stu-id="cad5a-156">When a contractor is hired, the **Compensation** tab should not be available on the request/action page.</span></span>
- <span data-ttu-id="cad5a-157">Durante o processo de rescisão de solicitação, você não pode prosseguir até que todos os campos obrigatórios contenham dados.</span><span class="sxs-lookup"><span data-stu-id="cad5a-157">During the request termination process, you can't continue until all required fields contain data.</span></span>
- <span data-ttu-id="cad5a-158">Problemas de exibição de data e ordem de classificação na análise do gerenciamento de equipes foram resolvidos.</span><span class="sxs-lookup"><span data-stu-id="cad5a-158">Sort order and date display issues on the Personnel management analytics have been addressed.</span></span>
