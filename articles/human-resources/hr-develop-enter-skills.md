---
title: Inserir habilidades
description: Trabalhadores e gerentes podem inserir habilidades no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 5a65f1884ea87bbf2519cc94e4c52a40ac1a91bd
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193968"
---
# <a name="enter-skills"></a><span data-ttu-id="ac416-103">Inserir habilidades</span><span class="sxs-lookup"><span data-stu-id="ac416-103">Enter skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ac416-104">Você pode inserir habilidades alvo ou habilidades reais para trabalhadores, candidatos ou contatos no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ac416-104">You can enter target skills or actual skills for workers, applicants, or contacts in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="ac416-105">Uma habilidade alvo é uma habilidade que uma pessoa planeja obter.</span><span class="sxs-lookup"><span data-stu-id="ac416-105">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="ac416-106">Uma habilidade real é uma habilidade que uma pessoa tem atualmente.</span><span class="sxs-lookup"><span data-stu-id="ac416-106">An actual skill is a skill that a person currently has.</span></span>

## <a name="create-a-workflow-to-auto-approve-skills"></a><span data-ttu-id="ac416-107">Criar um fluxo de trabalho para aprovar habilidades automaticamente</span><span class="sxs-lookup"><span data-stu-id="ac416-107">Create a workflow to auto-approve skills</span></span>

<span data-ttu-id="ac416-108">Para inserir habilidades sem exigir aprovação, você deve criar um fluxo de trabalho para aprovar habilidades automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ac416-108">To enter skills without requiring approval, you must create a workflow to auto-approve skills.</span></span>

> [!NOTE]
> <span data-ttu-id="ac416-109">As habilidades inseridas pelos trabalhadores sempre exigem aprovação do gerente.</span><span class="sxs-lookup"><span data-stu-id="ac416-109">Skills entered by workers always require manager approval.</span></span> <span data-ttu-id="ac416-110">Esse fluxo de trabalho aprova automaticamente as habilidades inseridas por gerentes em nome de seus trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="ac416-110">This workflow only auto-approves skills entered by managers on behalf of their workers.</span></span>

1. <span data-ttu-id="ac416-111">No espaço de trabalho **Gerenciamento de pessoal**, selecione **Links**.</span><span class="sxs-lookup"><span data-stu-id="ac416-111">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="ac416-112">Em **Configuração**, selecione **Fluxos de trabalho de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="ac416-112">Under **Setup**, select **Human resources workflows**.</span></span>

3. <span data-ttu-id="ac416-113">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ac416-113">Select **New**.</span></span>

4. <span data-ttu-id="ac416-114">No painel **Criar fluxo de trabalho**, selecione **Habilidades do trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="ac416-114">In the **Create workflow** pane, select **Worker skills**.</span></span>

   <span data-ttu-id="ac416-115">[![Selecionar fluxo de trabalho de habilidades do Trabalhador](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span><span class="sxs-lookup"><span data-stu-id="ac416-115">[![Select Worker skills workflow](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span></span>

5. <span data-ttu-id="ac416-116">Na caixa de diálogo **Abrir este arquivo?**, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="ac416-116">In the **Open this file?** dialogue, select **Open**.</span></span> <span data-ttu-id="ac416-117">Quando solicitado, insira as credenciais.</span><span class="sxs-lookup"><span data-stu-id="ac416-117">When prompted, enter your credentials.</span></span>

6. <span data-ttu-id="ac416-118">No editor de fluxo de trabalho, selecione o elemento do fluxo de trabalho **Aprovar habilidades** e arraste-o para a tela.</span><span class="sxs-lookup"><span data-stu-id="ac416-118">In the workflow editor, select the **Approve skills** workflow element and drag it onto the canvas.</span></span>

   <span data-ttu-id="ac416-119">[![Selecionar elemento de fluxo de trabalho Aprovar habilidades](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span><span class="sxs-lookup"><span data-stu-id="ac416-119">[![Select Approve skills workflow element](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span></span>

7. <span data-ttu-id="ac416-120">Conecte o elemento **Iniciar** ao elemento **Aprovar habilidades 1** e, em seguida, conecte o elemento **Aprovar habilidades 1** ao elemento **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ac416-120">Connect the **Start** element to the **Approve skills 1** element, and then connect the **Approve skills 1** element to the **End** element.</span></span> <span data-ttu-id="ac416-121">Talvez seja necessário rolar para baixo para ver o elemento **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ac416-121">You might need to scroll down to see the **End** element.</span></span> <span data-ttu-id="ac416-122">Você pode arrastá-lo para mais perto dos outros elementos.</span><span class="sxs-lookup"><span data-stu-id="ac416-122">You can drag it closer to the other elements.</span></span>

   <span data-ttu-id="ac416-123">[![Conectar elementos de fluxo de trabalho](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span><span class="sxs-lookup"><span data-stu-id="ac416-123">[![Connect workflow elements](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span></span>

8. <span data-ttu-id="ac416-124">Clique duas vezes no elemento de fluxo de trabalho **Aprovar habilidades 1** e clique com o botão direito do mouse no elemento **Etapa 1**.</span><span class="sxs-lookup"><span data-stu-id="ac416-124">Double-click the **Approve skills 1** workflow element, and then right-click the **Step 1** element.</span></span> <span data-ttu-id="ac416-125">Clique com o botão direito do mouse no elemento **Etapa 1** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ac416-125">Right-click the **Step 1** element, and then select **Properties**.</span></span>

9. <span data-ttu-id="ac416-126">Na janela **Propriedades**, selecione **Condição** na barra de navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="ac416-126">In the **Properties** window, select **Condition** on the left-hand nav bar.</span></span>

10. <span data-ttu-id="ac416-127">Selecione **Executar esta etapa somente quando a seguinte condição for atendida**.</span><span class="sxs-lookup"><span data-stu-id="ac416-127">Select **Run this step only when the following condition is met**.</span></span>

11. <span data-ttu-id="ac416-128">Selecione **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="ac416-128">Select **Add condition**.</span></span> <span data-ttu-id="ac416-129">Depois de **Onde**, selecione **Habilidades de autoatendimento para funcionários** e depois selecione **Habilidades de autoatendimento para funcionários - Pessoa**.</span><span class="sxs-lookup"><span data-stu-id="ac416-129">After **Where**, select **Employee self service skills**, and then select **Employee self service skills.Person**.</span></span> <span data-ttu-id="ac416-130">Depois de **é**, selecione **campo** e selecione **Relacionamento de Usuário para pessoa - Pessoa**.</span><span class="sxs-lookup"><span data-stu-id="ac416-130">After **is**, select **field**, and then select **User to person relationship.Person**.</span></span>

    <span data-ttu-id="ac416-131">[![Especificar condição](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span><span class="sxs-lookup"><span data-stu-id="ac416-131">[![Specify condition](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span></span>

12. <span data-ttu-id="ac416-132">Selecione **Atribuição** na barra de navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="ac416-132">Select **Assignment** on the left-hand nav bar.</span></span>

13. <span data-ttu-id="ac416-133">Na guia **Tipo de atribuição**, selecione **Hierarquia**.</span><span class="sxs-lookup"><span data-stu-id="ac416-133">On the **Assignment type** tab, select **Hierarchy**.</span></span>

14. <span data-ttu-id="ac416-134">Na guia **Seleção de hierarquia**, no campo **Tipo de hierarquia:**, selecione **Hierarquia gerencial**.</span><span class="sxs-lookup"><span data-stu-id="ac416-134">On the **Hierarchy selection** tab, in the **Hierarchy type:** field, select **Managerial hierarchy**.</span></span>

    <span data-ttu-id="ac416-135">[![Especificar hierarquia administrativa](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span><span class="sxs-lookup"><span data-stu-id="ac416-135">[![Specify managerial hierarchy](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span></span>

15. <span data-ttu-id="ac416-136">Selecione **Fechar**, escolha **Fluxo de trabalho** na trilha de navegação da tela e selecione **Salvar e fechar**.</span><span class="sxs-lookup"><span data-stu-id="ac416-136">Select **Close**, select **Workflow** in the canvas breadcrumb, and then select **Save and close**.</span></span>

<span data-ttu-id="ac416-137">Para obter mais informações sobre como criar fluxos de trabalho, consulte [Visão geral do sistema de fluxo de trabalho](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="ac416-137">For more information about creating workflows, see [Workflow system overview](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).</span></span>

## <a name="enter-skills-for-a-worker"></a><span data-ttu-id="ac416-138">Inserir habilidades para um trabalhador</span><span class="sxs-lookup"><span data-stu-id="ac416-138">Enter skills for a worker</span></span>

1. <span data-ttu-id="ac416-139">Selecione um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="ac416-139">Select a worker.</span></span>

2. <span data-ttu-id="ac416-140">Na barra de ação da página **Trabalhador**, selecione **Pessoa** e depois **Habilidades**.</span><span class="sxs-lookup"><span data-stu-id="ac416-140">In the action bar of the **Worker** page, select **Person**, and then select **Skills**.</span></span>

3. <span data-ttu-id="ac416-141">Na página **Habilidades**, preencha os seguintes campos para cada habilidade:</span><span class="sxs-lookup"><span data-stu-id="ac416-141">On the **Skills** page, complete the following fields for each skill:</span></span>

   - <span data-ttu-id="ac416-142">**Habilidade**: selecione uma habilidade.</span><span class="sxs-lookup"><span data-stu-id="ac416-142">**Skill**: Select a skill.</span></span>
   - <span data-ttu-id="ac416-143">**Tipo de nível**: selecione **Real** para uma habilidade que o trabalhador já tenha ou selecione **Alvo** para uma habilidade em que o trabalhador está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="ac416-143">**Level type**: Select **Actual** for a skill the worker already has, or select **Target** for a skill the worker is working toward.</span></span>
   - <span data-ttu-id="ac416-144">**Nível**: selecione um nível para a habilidade do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="ac416-144">**Level**: Select a level for the worker's skill.</span></span>
   - <span data-ttu-id="ac416-145">**Data do nível**: selecione uma data na ferramenta do calendário.</span><span class="sxs-lookup"><span data-stu-id="ac416-145">**Level date**: Select a date in the calendar tool.</span></span>
   - <span data-ttu-id="ac416-146">**Examinador**: se apropriado, selecione um examinador na lista.</span><span class="sxs-lookup"><span data-stu-id="ac416-146">**Examiner**: If appropriate, select an examiner from the list.</span></span> <span data-ttu-id="ac416-147">Você pode filtrar sua pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ac416-147">You can filter your search.</span></span>
   - <span data-ttu-id="ac416-148">**Anos de experiência**: insira anos de experiência.</span><span class="sxs-lookup"><span data-stu-id="ac416-148">**Years of experience**: Enter years of experience.</span></span>
   - <span data-ttu-id="ac416-149">**Verificado**: se a habilidade for verificada, marque a caixa.</span><span class="sxs-lookup"><span data-stu-id="ac416-149">**Verified**: If the skill is verified, check the box.</span></span>
   - <span data-ttu-id="ac416-150">**Verificado por**: insira o nome do verificador.</span><span class="sxs-lookup"><span data-stu-id="ac416-150">**Verified by**: Enter the name of the verifier.</span></span>

4. <span data-ttu-id="ac416-151">Quando tiver concluído a inserção de habilidades, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ac416-151">When you're done entering skills, select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac416-152">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ac416-152">See also</span></span>

[<span data-ttu-id="ac416-153">Configurar habilidades</span><span class="sxs-lookup"><span data-stu-id="ac416-153">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="ac416-154">Mapear habilidades</span><span class="sxs-lookup"><span data-stu-id="ac416-154">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]