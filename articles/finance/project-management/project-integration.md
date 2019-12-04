---
title: Integração do cliente do Microsoft Project
description: Planejar e manter uma agenda de projeto pode ser complexo, por isso os gerentes de projeto precisam usar ferramentas que os ajudem a gerenciar essa tarefa. A integração com o Cliente do Microsoft Project fornece suporte para abrir e gerenciar a estrutura de detalhamento de trabalho de um projeto.
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 610990612d5fb38025bf39cc648d0c9572da37b6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174747"
---
# <a name="microsoft-project-client-integration"></a><span data-ttu-id="a8457-104">Integração do cliente do Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="a8457-104">Microsoft Project client integration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8457-105">Planejar e manter uma agenda de projeto pode ser complexo, por isso os gerentes de projeto precisam usar ferramentas que os ajudem a gerenciar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="a8457-105">Planning and maintaining a project schedule can be complex, so project managers need to use tools that help them manage this task.</span></span> <span data-ttu-id="a8457-106">A integração com o Cliente do Microsoft Project fornece suporte para abrir e gerenciar a estrutura de detalhamento de trabalho de um projeto.</span><span class="sxs-lookup"><span data-stu-id="a8457-106">Integration with Microsoft Project Client provides support to open and manage a project work breakdown structure.</span></span> <span data-ttu-id="a8457-107">O gerente do projeto pode publicar as alterações na estrutura de detalhamento de trabalho do projeto do Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="a8457-107">The project manager can publish any changes back to the Dynamics 365 Finance project work breakdown structure.</span></span>

> [!NOTE]
> <span data-ttu-id="a8457-108">Se estiver usando a atualização de julho (versão 10.0.4), você deverá instalar o KB 4054797 e o 4055884.</span><span class="sxs-lookup"><span data-stu-id="a8457-108">If you are using the July update (version 10.0.4), you must install KB 4054797 and 4055884.</span></span>

## <a name="configure-the-microsoft-project-client-add-in"></a><span data-ttu-id="a8457-109">Configurar o suplemento do Cliente do Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="a8457-109">Configure the Microsoft Project Client add-in</span></span>
<span data-ttu-id="a8457-110">Para habilitar a integração com o Cliente do Microsoft Project, um suplemento do Microsoft Dynamics 365 deve ser instalado no aplicativo do cliente do Microsoft Project do usuário.</span><span class="sxs-lookup"><span data-stu-id="a8457-110">To enable the integration with Microsoft Project Client, a Microsoft Dynamics 365 add-in is required to be installed in the user’s client Microsoft Project application.</span></span> <span data-ttu-id="a8457-111">Isso é feito abrindo o **Espaço de trabalho de gerenciamento de projeto**.</span><span class="sxs-lookup"><span data-stu-id="a8457-111">This is done by opening the **Project management workspace**.</span></span>

<span data-ttu-id="a8457-112">•   Clique em **Configurar o suplemento do cliente do projeto** na seção **Links** > **Configuração** do espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a8457-112">•   Click **Configure project client add-in** from the **Links** > **Setup** section of the workspace.</span></span>

<span data-ttu-id="a8457-113">•   Clique em **Abrir**, em seguida, clique em **Executar** quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="a8457-113">•   Click **Open**, then click **Run** when prompted.</span></span>

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a><span data-ttu-id="a8457-114">Abrir e editar uma estrutura de detalhamento de trabalho de rascunho existente no Cliente do Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="a8457-114">Open and edit an existing draft work breakdown structure in Microsoft Project Client</span></span>
<span data-ttu-id="a8457-115">Se um projeto no Dynamics 365 Finance já tiver uma estrutura de detalhamento de trabalho criada, ela poderá ser aberta no aplicativo Microsoft Project Client se estiver em um status de rascunho.</span><span class="sxs-lookup"><span data-stu-id="a8457-115">If a project in Dynamics 365 Finance already has a work breakdown structure created, the work breakdown structure can be opened in the Microsoft Project Client application if the work breakdown structure is in a draft status.</span></span> <span data-ttu-id="a8457-116">Para abrir a partir da página **Projeto**, clique no link **Abrir no Microsoft Project** da guia **Plano**. Essa página também pode ser aberta no aplicativo do Cliente do Microsoft Project clicando em **Abrir** na guia **Microsoft Dynamics 365**. Selecione a **Entidade legal** e o **Projeto** na lista.</span><span class="sxs-lookup"><span data-stu-id="a8457-116">To open from the **Project** page, click **Open in Microsoft Project** link from the **Plan** tab. This page can also be opened from within the Microsoft Project Client application by clicking **Open** in the **Microsoft Dynamics 365** tab. Select the **Legal entity** and **Project** from the list.</span></span>

> [!NOTE]
> <span data-ttu-id="a8457-117">Se estiver usando o Internet Explorer como navegador, você precisará clicar em **Salvar** para abrir manualmente do local onde o arquivo foi baixado.</span><span class="sxs-lookup"><span data-stu-id="a8457-117">If you're using Internet Explorer as your browser, you will need to click **Save** to manually open from the location that the file is downloaded to.</span></span> <span data-ttu-id="a8457-118">Ou clicar em **Salvar e abrir** para abrir o arquivo no Cliente do Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="a8457-118">Or, click **Save and open** to open the file in Microsoft Project Client.</span></span> <span data-ttu-id="a8457-119">Não renomeie o arquivo ao salvar.</span><span class="sxs-lookup"><span data-stu-id="a8457-119">Do not rename the file name when saving.</span></span>

<span data-ttu-id="a8457-120">Antes de fazer quaisquer edições no arquivo usando o Microsoft Project Client, você precisará fazer o check-out. Clique em **Check-out** na guia **Microsoft Dynamics 365**. Isso impedirá que outros usuários editem a estrutura de detalhamento de trabalho no Finance ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a8457-120">Before making any edits to the file using Microsoft Project Client, you need to check it out. Click **Check out** in the **Microsoft Dynamics 365** tab. This will prevent other users from editing the work breakdown structure from within Finance at the same time.</span></span> <span data-ttu-id="a8457-121">Para publicar a estrutura de detalhamento de trabalho após concluir alguma edição, clique em **Check-in** na guia **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="a8457-121">To publish the work breakdown structure after completing any edits, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

<span data-ttu-id="a8457-122">Se uma equipe de projeto já tiver sido adicionada ao projeto em Finance, a lista de recursos será preenchida com os membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="a8457-122">If a project team has already been added to the project in Finance, the resource list will be populated with the team members.</span></span> <span data-ttu-id="a8457-123">Se uma equipe de projeto ainda não tiver sido adicionada ao projeto, você pode selecionar recursos e criar a equipe no Cliente do Microsoft Project clicando no botão **Recursos** na guia **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="a8457-123">If a project team has not yet been added to the project, you can select resources and build the team within Microsoft Project Client by clicking the **Resources** button on the **Microsoft Dynamics 365** tab.</span></span> 

<span data-ttu-id="a8457-124">Os seguintes dados serão sincronizados com o Finance como parte do processo de check-in:</span><span class="sxs-lookup"><span data-stu-id="a8457-124">The following data will be synced back to Finance as part of the check-in process:</span></span>

<span data-ttu-id="a8457-125">•   Nome da tarefa</span><span class="sxs-lookup"><span data-stu-id="a8457-125">•   Task name</span></span>

<span data-ttu-id="a8457-126">•   Data de início</span><span class="sxs-lookup"><span data-stu-id="a8457-126">•   Start date</span></span>

<span data-ttu-id="a8457-127">•   Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="a8457-127">•   Finish date</span></span>

<span data-ttu-id="a8457-128">•   Predecessores</span><span class="sxs-lookup"><span data-stu-id="a8457-128">•   Predecessors</span></span>

<span data-ttu-id="a8457-129">•   Nomes de recurso</span><span class="sxs-lookup"><span data-stu-id="a8457-129">•   Resource names</span></span>

<span data-ttu-id="a8457-130">•   Categoria</span><span class="sxs-lookup"><span data-stu-id="a8457-130">•   Category</span></span>

<span data-ttu-id="a8457-131">•   Categoria de recurso</span><span class="sxs-lookup"><span data-stu-id="a8457-131">•   Resource category</span></span>

<span data-ttu-id="a8457-132">•   Horas de trabalho</span><span class="sxs-lookup"><span data-stu-id="a8457-132">•   Work hours</span></span>

<span data-ttu-id="a8457-133">•   Observações</span><span class="sxs-lookup"><span data-stu-id="a8457-133">•   Notes</span></span>

<span data-ttu-id="a8457-134">•   Prioridade</span><span class="sxs-lookup"><span data-stu-id="a8457-134">•   Priority</span></span>

> [!NOTE]
> <span data-ttu-id="a8457-135">Se você adicionar outras colunas ao seu arquivo do Cliente do Microsoft Project, elas não serão salvas no arquivo e não serão exibidas quando o arquivo for aberto novamente.</span><span class="sxs-lookup"><span data-stu-id="a8457-135">If you add any other columns to your Microsoft Project Client file, they will not be saved to the file and will not be displayed when the file is opened again.</span></span>

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="a8457-136">Criar a estrutura de detalhamento de trabalho para um projeto existente usando o Cliente do Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="a8457-136">Create the work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="a8457-137">Para criar uma nova estrutura de detalhamento de trabalho usando o Cliente do Microsoft Project, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a8457-137">To create a new work breakdown structure using Microsoft Project Client, follow these steps:</span></span>


1.  <span data-ttu-id="a8457-138">Abra o Cliente do Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="a8457-138">Open Microsoft Project Client.</span></span>

2.  <span data-ttu-id="a8457-139">Na guia **Microsoft Dynamics 365**, clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a8457-139">On the **Microsoft Dynamics 365** tab, click **Open**.</span></span>

3.  <span data-ttu-id="a8457-140">Selecione a **Entidade legal** do projeto.</span><span class="sxs-lookup"><span data-stu-id="a8457-140">Select the **Legal entity** for the project.</span></span>

4.  <span data-ttu-id="a8457-141">Selecione o **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a8457-141">Select the **Project**.</span></span>

5.  <span data-ttu-id="a8457-142">Clique em **Check-out** na guia **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="a8457-142">Click **Check out** on the **Microsoft Dynamics 365** tab.</span></span>

6.  <span data-ttu-id="a8457-143">Quando estiver pronto para publicar no Finance, clique em **Check-in** na guia **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="a8457-143">When ready to publish to Finance, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="a8457-144">Substitua a estrutura de detalhamento de trabalho existente para um projeto existente usando o Cliente do Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="a8457-144">Replace the existing work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="a8457-145">Para criar uma nova estrutura de detalhamento de trabalho usando o Cliente do Microsoft Project e substituir uma estrutura de detalhamento de trabalho existente para um projeto existente, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a8457-145">To create a new work breakdown structure using Microsoft Project Client and replace an existing work breakdown structure for an existing project, follow these steps:</span></span>

1.  <span data-ttu-id="a8457-146">Abra o Cliente do Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="a8457-146">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="a8457-147">Crie a agenda no Cliente do Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="a8457-147">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="a8457-148">Na guia **Microsoft Dynamics 365**, clique em **Salvar alterações** > **Substituir projeto existente**.</span><span class="sxs-lookup"><span data-stu-id="a8457-148">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Replace existing project**.</span></span>

4.  <span data-ttu-id="a8457-149">Selecione a **Entidade legal** do projeto.</span><span class="sxs-lookup"><span data-stu-id="a8457-149">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="a8457-150">Selecione o **Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a8457-150">Select the **Project**.</span></span>

6.  <span data-ttu-id="a8457-151">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8457-151">Click **OK**.</span></span>

## <a name="create-a-new-project-from-within-microsoft-project-client"></a><span data-ttu-id="a8457-152">Criar um novo projeto no Cliente do Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="a8457-152">Create a new project from within Microsoft Project Client</span></span>


1.  <span data-ttu-id="a8457-153">Abra o Cliente do Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="a8457-153">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="a8457-154">Crie a agenda no Cliente do Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="a8457-154">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="a8457-155">Na guia **Microsoft Dynamics 365**, clique em **Salvar alterações** > **Salvar no novo Projeto**.</span><span class="sxs-lookup"><span data-stu-id="a8457-155">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Save to new Project**.</span></span>

4.  <span data-ttu-id="a8457-156">Selecione a **Entidade legal** do projeto.</span><span class="sxs-lookup"><span data-stu-id="a8457-156">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="a8457-157">Insira a **ID do projeto**, se necessário.</span><span class="sxs-lookup"><span data-stu-id="a8457-157">Enter the **Project ID**, if necessary.</span></span>

6.  <span data-ttu-id="a8457-158">Insira o **Nome do projeto**.</span><span class="sxs-lookup"><span data-stu-id="a8457-158">Enter the **Project name**.</span></span>

7.  <span data-ttu-id="a8457-159">Selecione o **Tipo de projeto**, o **Grupo de projetos** e a **ID do contrato de projeto**.</span><span class="sxs-lookup"><span data-stu-id="a8457-159">Select the **Project type**, **Project group** and the **Project contract ID**.</span></span> <span data-ttu-id="a8457-160">Como alternativa, você pode criar um novo contrato de projeto clicando em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a8457-160">Alternatively, you can create a new project contract by clicking **New**.</span></span>

8.  <span data-ttu-id="a8457-161">Selecione o **Calendário** a ser usado para os recursos.</span><span class="sxs-lookup"><span data-stu-id="a8457-161">Select the **Calendar** to be used for resourcing.</span></span>

11. <span data-ttu-id="a8457-162">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8457-162">Click **OK**.</span></span>