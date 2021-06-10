---
title: Configurar habilidades
description: Você pode rastrear as habilidades de seu trabalhador no Dynamics 365 Human Resources. Você também pode especificar as habilidades necessárias para um trabalho específico.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 816822d1f3d365b4c5571c13e9f596e1c5d5e59c
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076550"
---
# <a name="configure-skills"></a><span data-ttu-id="0af44-104">Configurar habilidades</span><span class="sxs-lookup"><span data-stu-id="0af44-104">Configure skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0af44-105">Você pode rastrear as habilidades de seu trabalhador no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0af44-105">You can track your worker's skills in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="0af44-106">Você também pode especificar as habilidades necessárias para um trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="0af44-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="0af44-107">Os exemplos das habilidades que você pode rastrear incluem:</span><span class="sxs-lookup"><span data-stu-id="0af44-107">Examples of skills you can track include:</span></span>

- <span data-ttu-id="0af44-108">Supervisão – capacidade de supervisionar o trabalho de terceiros.</span><span class="sxs-lookup"><span data-stu-id="0af44-108">Supervisory – Ability to supervise the work of others.</span></span>
- <span data-ttu-id="0af44-109">Liderança – capacidade de liderar funcionários e setores empresariais.</span><span class="sxs-lookup"><span data-stu-id="0af44-109">Leadership – Ability to lead employees and business domains.</span></span>
- <span data-ttu-id="0af44-110">Planejamento - capacidade de antever o futuro, formular instruções de visões e acompanhá-las.</span><span class="sxs-lookup"><span data-stu-id="0af44-110">Planning – Ability to look ahead, to form vision statements, and to see them through.</span></span>
- <span data-ttu-id="0af44-111">HTML – Capacidade de gravar o código HTML.</span><span class="sxs-lookup"><span data-stu-id="0af44-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="0af44-112">Se você ainda não configurou os tipos de habilidades e os modelos de classificação, será necessário adicionar algum antes de criar habilidades.</span><span class="sxs-lookup"><span data-stu-id="0af44-112">If you haven't already set up skill types and rating models, you'll need to add some before creating skills.</span></span>

<span data-ttu-id="0af44-113">As seguintes pessoas podem inserir habilidades para um trabalhador:</span><span class="sxs-lookup"><span data-stu-id="0af44-113">The following people can enter skills for a worker:</span></span>

- <span data-ttu-id="0af44-114">Os trabalhadores podem inserir habilidades para si mesmos no Autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="0af44-114">Workers can enter skills for themselves in Employee self-service.</span></span> <span data-ttu-id="0af44-115">Essas habilidades exigem aprovação do gerente.</span><span class="sxs-lookup"><span data-stu-id="0af44-115">These skills require manager approval.</span></span>
- <span data-ttu-id="0af44-116">Os gerentes podem inserir habilidades para seus trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="0af44-116">Managers can enter skills for their workers.</span></span> <span data-ttu-id="0af44-117">Você pode criar um fluxo de trabalho que aprova essas habilidades automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0af44-117">You can create a workflow that auto-approves these skills.</span></span>

## <a name="create-a-skill-type"></a><span data-ttu-id="0af44-118">Criar um tipo de habilidade</span><span class="sxs-lookup"><span data-stu-id="0af44-118">Create a skill type</span></span>

<span data-ttu-id="0af44-119">Os tipos de habilidades são categorias sob as quais as habilidades individuais se encaixam, como Administração ou Vendas.</span><span class="sxs-lookup"><span data-stu-id="0af44-119">Skill types are categories that individual skills fall under, such as Administration or Sales.</span></span>

1. <span data-ttu-id="0af44-120">No espaço de trabalho **Desenvolvimento do funcionário**, selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="0af44-120">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="0af44-121">Em **Configuração de competência**, selecione **Tipos de habilidades**.</span><span class="sxs-lookup"><span data-stu-id="0af44-121">Under **Competency setup**, select **Skill types**.</span></span>

3. <span data-ttu-id="0af44-122">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0af44-122">Select **New**.</span></span>

4. <span data-ttu-id="0af44-123">Complete os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="0af44-123">Complete the following fields:</span></span>

   - <span data-ttu-id="0af44-124">**Tipo de habilidade**: informe um nome para o tipo de habilidade.</span><span class="sxs-lookup"><span data-stu-id="0af44-124">**Skill type**: Enter a name for the skill type.</span></span>
   - <span data-ttu-id="0af44-125">**Descrição**: informe uma descrição para o tipo de habilidade.</span><span class="sxs-lookup"><span data-stu-id="0af44-125">**Description**: Enter a description for the skill type.</span></span>

5. <span data-ttu-id="0af44-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0af44-126">Select **Save**.</span></span>

## <a name="create-a-rating-model"></a><span data-ttu-id="0af44-127">Criar um modelo de classificação</span><span class="sxs-lookup"><span data-stu-id="0af44-127">Create a rating model</span></span>

<span data-ttu-id="0af44-128">Os modelos de classificação ajudam a avaliar o nível real de habilidades de uma pessoa, o nível que ela deveria atingir ou o nível de habilidades necessário para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="0af44-128">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill required for a job.</span></span> <span data-ttu-id="0af44-129">Cada nível em um modelo de classificação é atribuído um fator.</span><span class="sxs-lookup"><span data-stu-id="0af44-129">Each level in a rating model is assigned a factor.</span></span>

1. <span data-ttu-id="0af44-130">No espaço de trabalho **Desenvolvimento do funcionário**, selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="0af44-130">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="0af44-131">Em **Configuração de competência**, selecione **Modelos de classificação**.</span><span class="sxs-lookup"><span data-stu-id="0af44-131">Under **Competency setup**, select **Rating models**.</span></span>

3. <span data-ttu-id="0af44-132">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0af44-132">Select **New**.</span></span>

4. <span data-ttu-id="0af44-133">Complete os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="0af44-133">Complete the following fields:</span></span>

   - <span data-ttu-id="0af44-134">**Classificação**: insira um nome para o modelo de classificação, por exemplo, **Habilidades**.</span><span class="sxs-lookup"><span data-stu-id="0af44-134">**Rating**: Enter a name for the rating model, such as **Skills**.</span></span>
   - <span data-ttu-id="0af44-135">**Descrição**: insira uma descrição para o modelo de classificação, como **Classificações de habilidade**.</span><span class="sxs-lookup"><span data-stu-id="0af44-135">**Description**: Enter a description for the rating model, such as **Skill ratings**.</span></span>

5. <span data-ttu-id="0af44-136">Na seção **Níveis**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0af44-136">In the **Levels** section, select **New**.</span></span> <span data-ttu-id="0af44-137">Para cada nível a ser adicionado, preencha os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="0af44-137">For each level you want to add, complete the following fields:</span></span>

   - <span data-ttu-id="0af44-138">**Nível**: informe um nome para o nível.</span><span class="sxs-lookup"><span data-stu-id="0af44-138">**Level**: Enter a name for the level.</span></span>
   - <span data-ttu-id="0af44-139">**Descrição**: insira uma descrição para o nível.</span><span class="sxs-lookup"><span data-stu-id="0af44-139">**Description**: Enter a description for the level.</span></span>
   - <span data-ttu-id="0af44-140">**Fator**: insira um valor de fator de 0-9.</span><span class="sxs-lookup"><span data-stu-id="0af44-140">**Factor**: Enter a factor value from 0-9.</span></span> <span data-ttu-id="0af44-141">Os fatores ajudam a normalizar as pontuações das habilidades que usam diferentes modelos de avaliação.</span><span class="sxs-lookup"><span data-stu-id="0af44-141">Factors help normalize the scores of skills that use different rating models.</span></span> <span data-ttu-id="0af44-142">Cada nível deve ter um fator exclusivo.</span><span class="sxs-lookup"><span data-stu-id="0af44-142">Each level must have a unique factor.</span></span> <span data-ttu-id="0af44-143">Os níveis com valores de fator mais altos têm mais peso em um modelo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="0af44-143">Levels with higher factor values carry more weight in a rating model.</span></span>

   <span data-ttu-id="0af44-144">Continue adicionando níveis, conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="0af44-144">Continue adding levels as necessary.</span></span> <span data-ttu-id="0af44-145">É possível inserir até 10 níveis para cada modelo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="0af44-145">You can enter up to 10 levels for each rating model.</span></span>

6. <span data-ttu-id="0af44-146">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0af44-146">Select **Save**.</span></span>

## <a name="create-a-skill"></a><span data-ttu-id="0af44-147">Criar uma habilidade</span><span class="sxs-lookup"><span data-stu-id="0af44-147">Create a skill</span></span>

<span data-ttu-id="0af44-148">Antes de atribuir uma habilidade ou criar uma pesquisa de mapeamento de habilidades ou perfil de habilidades, você deve inserir informações sobre as habilidades na página **Habilidades**.</span><span class="sxs-lookup"><span data-stu-id="0af44-148">Before you can assign a skill, or create a skill-mapping search or skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="0af44-149">Para cada habilidade, você pode selecionar um tipo de habilidade e um modelo de classificação.</span><span class="sxs-lookup"><span data-stu-id="0af44-149">For each skill, you can select a skill type and a rating model.</span></span>

1. <span data-ttu-id="0af44-150">No espaço de trabalho **Desenvolvimento do funcionário**, selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="0af44-150">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="0af44-151">Em **Configuração de competência**, selecione **Habilidades**.</span><span class="sxs-lookup"><span data-stu-id="0af44-151">Under **Competency setup**, select **Skills**.</span></span>

3. <span data-ttu-id="0af44-152">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0af44-152">Select **New**.</span></span>

4. <span data-ttu-id="0af44-153">Complete os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="0af44-153">Complete the following fields:</span></span>

   - <span data-ttu-id="0af44-154">**Habilidade**: informe um nome para a habilidade.</span><span class="sxs-lookup"><span data-stu-id="0af44-154">**Skill**: Enter a name for the skill.</span></span>
   - <span data-ttu-id="0af44-155">**Descrição**: informe uma descrição para a habilidade.</span><span class="sxs-lookup"><span data-stu-id="0af44-155">**Description**: Enter a description for the skill.</span></span>
   - <span data-ttu-id="0af44-156">**Classificação**: selecione o modelo de classificação que você deseja usar para esta habilidade.</span><span class="sxs-lookup"><span data-stu-id="0af44-156">**Rating**: Select the rating model you want to use for this skill.</span></span>
   - <span data-ttu-id="0af44-157">**Tipo de habilidade**: selecione na lista de tipos de habilidades.</span><span class="sxs-lookup"><span data-stu-id="0af44-157">**Skill type**: Select from the list of skill types.</span></span>

5. <span data-ttu-id="0af44-158">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0af44-158">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0af44-159">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0af44-159">See also</span></span>

[<span data-ttu-id="0af44-160">Inserir habilidades</span><span class="sxs-lookup"><span data-stu-id="0af44-160">Enter skills</span></span>](hr-develop-enter-skills.md)<br>
[<span data-ttu-id="0af44-161">Mapear habilidades</span><span class="sxs-lookup"><span data-stu-id="0af44-161">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]