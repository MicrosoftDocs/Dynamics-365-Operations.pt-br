---
title: "Documentos de justificativa para planejamento de orçamento"
description: "Documentos de justificativa fornecem uma narrativa àqueles solicitando um orçamento para explicar por que um orçamento específico é necessário."
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: b38050e8a792622b772882ec4a0cddce8661a720
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="budget-planning-justification-documents"></a><span data-ttu-id="2c9e2-103">Documentos de justificativa para planejamento de orçamento</span><span class="sxs-lookup"><span data-stu-id="2c9e2-103">Budget planning justification documents</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="2c9e2-104">Documentos de justificativa fornecem uma narrativa àqueles solicitando um orçamento para explicar por que um orçamento específico é necessário.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-104">Justification documents provide a narrative for those requesting a budget to explain why a specific budget is necessary.</span></span> 

<span data-ttu-id="2c9e2-105">O modelo de plano de orçamento é criado pelo gerente de orçamento no Microsoft Word e atribuído ao processo de planejamento de orçamento atual.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-105">A budget plan template is created by the budget manager in Microsoft Word and assigned to the current budget planning process.</span></span> <span data-ttu-id="2c9e2-106">Proprietários de orçamento podem então abrir o modelo e ter dados automaticamente preenchidos no Word com base em sua solicitação de orçamento.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-106">Budget owners can then open the template and have data automatically populated in Word based on their budget request.</span></span> <span data-ttu-id="2c9e2-107">Eles podem adicionar mais texto ou dados antes de salvar ou anexar seu documento de justificativa personalizado ao seu plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-107">They can then add additional text or data prior to saving and attaching their personalized justification document to their budget plan.</span></span>

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a><span data-ttu-id="2c9e2-108">Configurar o Suplemento do Microsoft Dynamics Office para Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="2c9e2-108">Set up Microsoft Dynamics Office Add-in for Microsoft Word</span></span>

1.  <span data-ttu-id="2c9e2-109">Abra um novo documento do Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-109">Open a new Microsoft Word document.</span></span>
2.  <span data-ttu-id="2c9e2-110">Clique em **Inserir** na faixa de opções e, depois, clique em **Armazenar**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-110">Click **Insert** on the ribbon, and click **Store**.</span></span>
3.  <span data-ttu-id="2c9e2-111">Procure o Suplemento do Microsoft Dynamics Office e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-111">Search for Microsoft Dynamics Office Add-in and click **Add**.</span></span>
4.  <span data-ttu-id="2c9e2-112">No Word, no painel direito, clique em **Adicionar informações do servidor**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-112">In Word, in the right pane, click **Add server information**.</span></span>
5.  <span data-ttu-id="2c9e2-113">Digite ou cole a URL do servidor e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-113">Type or paste the server URL and click **OK**.</span></span>

##### <a name="define-the-justification-template-in-microsoft-word"></a><span data-ttu-id="2c9e2-114">Definir o modelo de justificativa no Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="2c9e2-114">Define the Justification template in Microsoft Word</span></span>

1.  <span data-ttu-id="2c9e2-115">Clique em **Design** no Suplemento do Microsoft Dynamics Office depois de ter feito logon.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-115">Click **Design** in the Microsoft Dynamics Office Add-in after you’ve logged in.</span></span>
2.  <span data-ttu-id="2c9e2-116">Para informações de cabeçalho, use o botão **Adicionar campos**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-116">For header information, use the **Add fields** button.</span></span>
3.  <span data-ttu-id="2c9e2-117">Selecione a fonte de dados da entidade de BudgetPlanJustification e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-117">Select the entity data source of BudgetPlanJustification, and click **Next**.</span></span> <span data-ttu-id="2c9e2-118">**Observação:** essa entidade é necessária para qualquer documento.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-118">**Note:** This entity is required for any justification document.</span></span> <span data-ttu-id="2c9e2-119">Outras entidades podem ser usadas, mas o carregamento de volta ao Microsoft Dynamics 365 for Finance and Operations falhará se essa entidade não estiver incluída.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-119">Other entities can be used but the upload back to Microsoft Dynamics 365 for Finance and Operations will fail if this entity isn’t included.</span></span>
4.  <span data-ttu-id="2c9e2-120">Adicione as etiquetas e valores BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter e DocumentNumber no documento do Word.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-120">Add the BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter, and DocumentNumber labels and values in the Word document.</span></span> <span data-ttu-id="2c9e2-121">**Observação:** é possível usar suas próprias etiquetas, em vez de etiquetas padrão, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-121">**Note:** You can use your own custom labels, rather than the standard labels, if needed.</span></span>
5.  <span data-ttu-id="2c9e2-122">Clique em **Concluído** para concluir a seção de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-122">Click **Done** to complete the header section.</span></span>
6.  <span data-ttu-id="2c9e2-123">Para detalhes de nível de linha dos valores de plano de orçamento, clique em **Adicionar tabela**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-123">For line level detail of budget plan amounts, click **Add table**.</span></span>
7.  <span data-ttu-id="2c9e2-124">Selecione novamente a fonte de dados da entidade de BudgetPlanJustification e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-124">Again, select the entity data source of BudgetPlanJustification, and click **Next**.</span></span>
8.  <span data-ttu-id="2c9e2-125">Adicione campos para EffectiveDate, ScenarioName, AccountDisplayValue e AccountingCurrencyExpenseAmount.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-125">Add fields for EffectiveDate, ScenarioName, AccountDisplayValue, and AccountingCurrencyExpenseAmount.</span></span> <span data-ttu-id="2c9e2-126">**Observação:** se comentários estiverem disponíveis para adição nas linhas de plano de orçamento individuais, eles podem ser adicionados à tabela aqui.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-126">**Note:** If comments are available to add within individual budget plan lines, those can be added to the table here.</span></span>
9.  <span data-ttu-id="2c9e2-127">Adicione qualquer instrução adicional para fornecer ao usuário final e realize qualquer formatação ou estilização no documento.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-127">Add any additional instructions to provide to the end user, and perform any necessary formatting or styling to the document.</span></span>
10. <span data-ttu-id="2c9e2-128">Salve o documento no seu computador local e feche o arquivo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-128">Save the document to your local computer and close the file before continuing.</span></span>

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a><span data-ttu-id="2c9e2-129">Configurar o processo de planejamento de orçamento para usar o modelo de justificativa</span><span class="sxs-lookup"><span data-stu-id="2c9e2-129">Set up the Budget planning process to use the Justification template</span></span>

1.  <span data-ttu-id="2c9e2-130">No Finance and Operations, vá para **Orçamento** &gt; **Configuração** &gt; **Planejamento de orçamento** &gt; **Modelos de documento de justificativa**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-130">In Finance and Operations, go to **Budgeting** &gt; **Setup** &gt; **Budget planning** &gt; **Justification document templates**.</span></span>
2.  <span data-ttu-id="2c9e2-131">Clique em **Novo** e acesse seu documento recém-criado do Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-131">Click **New** and browse to your newly created Microsoft Word document.</span></span>
3.  <span data-ttu-id="2c9e2-132">Insira nome e descrição de exibição de modelo.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-132">Enter a template display name and description.</span></span> <span data-ttu-id="2c9e2-133">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-133">Click **OK**.</span></span>
4.  <span data-ttu-id="2c9e2-134">Vá para **Orçamento** &gt; **Configuração** &gt; **Planejamento do** **orçamento** &gt; **Processo de planejamento de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-134">Go to **Budgeting** &gt; **Setup** &gt; **Budget** **planning** &gt; **Budget planning process**.</span></span>
5.  <span data-ttu-id="2c9e2-135">Selecione o processo no qual o modelo de justificativa deve ser usado e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-135">Select the process where the justification template should be used, and click **Edit**.</span></span>
6.  <span data-ttu-id="2c9e2-136">No campo **Modelo de documento de justificativa**, selecione o modelo apropriado e salve-o.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-136">In the **Justification document template** field, select the appropriate template and save.</span></span>

##### <a name="edit-and-save-personalized-justification-documents"></a><span data-ttu-id="2c9e2-137">Editar e salvar documentos de justificativa personalizados</span><span class="sxs-lookup"><span data-stu-id="2c9e2-137">Edit and save personalized justification documents</span></span>

1.  <span data-ttu-id="2c9e2-138">No Finance and Operations, crie um novo plano de orçamento ou abra um plano de orçamento existente.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-138">In Finance and Operations, create a new budget plan or open an existing budget plan.</span></span>
2.  <span data-ttu-id="2c9e2-139">No menu suspenso **Justificativa**, selecione **Criar nova justificativa**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-139">In the **Justification** drop-down menu, select **Create new justification**.</span></span>
3.  <span data-ttu-id="2c9e2-140">Após preencher os detalhes, selecione para carregar os documentos personalizados no menu suspenso **Justificativa**.</span><span class="sxs-lookup"><span data-stu-id="2c9e2-140">After filling in the details, select to upload the personalized document from the **Justification** drop-down menu.</span></span>





