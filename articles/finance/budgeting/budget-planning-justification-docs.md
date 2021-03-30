---
title: Documentos de justificativa para planejamento de orçamento
description: Documentos de justificativa fornecem uma narrativa àqueles solicitando um orçamento para explicar por que um orçamento específico é necessário.
author: panolte
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8754c017a966cb1d11a72d6f8a80e1088aeb9100
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210304"
---
# <a name="budget-planning-justification-documents"></a><span data-ttu-id="78c01-103">Documentos de justificativa para planejamento de orçamento</span><span class="sxs-lookup"><span data-stu-id="78c01-103">Budget planning justification documents</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78c01-104">Documentos de justificativa fornecem uma narrativa àqueles solicitando um orçamento para explicar por que um orçamento específico é necessário.</span><span class="sxs-lookup"><span data-stu-id="78c01-104">Justification documents provide a narrative for those requesting a budget to explain why a specific budget is necessary.</span></span> 

<span data-ttu-id="78c01-105">Um modelo de plano de orçamento é criado pelo gerente de orçamento no Microsoft Word e atribuído ao processo de planejamento de orçamento atual.</span><span class="sxs-lookup"><span data-stu-id="78c01-105">A budget plan template is created by the budget manager in Microsoft Word and assigned to the current budget planning process.</span></span> <span data-ttu-id="78c01-106">Proprietários de orçamento podem então abrir o modelo e ter dados automaticamente preenchidos no Word com base em sua solicitação de orçamento.</span><span class="sxs-lookup"><span data-stu-id="78c01-106">Budget owners can then open the template and have data automatically populated in Word based on their budget request.</span></span> <span data-ttu-id="78c01-107">Eles podem adicionar mais texto ou dados antes de salvar ou anexar seu documento de justificativa personalizado ao seu plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="78c01-107">They can then add additional text or data prior to saving and attaching their personalized justification document to their budget plan.</span></span>

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a><span data-ttu-id="78c01-108">Configurar o Suplemento do Office do Microsoft Dynamics para Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="78c01-108">Set up Microsoft Dynamics Office Add-in for Microsoft Word</span></span>

1.  <span data-ttu-id="78c01-109">Abra um novo documento do Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="78c01-109">Open a new Microsoft Word document.</span></span>
2.  <span data-ttu-id="78c01-110">Clique em **Inserir** na faixa de opções e, depois, clique em **Armazenar**.</span><span class="sxs-lookup"><span data-stu-id="78c01-110">Click **Insert** on the ribbon, and click **Store**.</span></span>
3.  <span data-ttu-id="78c01-111">Procure o Suplemento do Office do Microsoft Dynamics e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="78c01-111">Search for Microsoft Dynamics Office Add-in and click **Add**.</span></span>
4.  <span data-ttu-id="78c01-112">No Word, no painel direito, clique em **Adicionar informações do servidor**.</span><span class="sxs-lookup"><span data-stu-id="78c01-112">In Word, in the right pane, click **Add server information**.</span></span>
5.  <span data-ttu-id="78c01-113">Digite ou cole a URL do servidor e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="78c01-113">Type or paste the server URL and click **OK**.</span></span>

##### <a name="define-the-justification-template-in-microsoft-word"></a><span data-ttu-id="78c01-114">Definir o modelo de justificativa no Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="78c01-114">Define the Justification template in Microsoft Word</span></span>

1.  <span data-ttu-id="78c01-115">Clique em **Design** no Suplemento do Office do Microsoft Dynamics depois de ter feito logon.</span><span class="sxs-lookup"><span data-stu-id="78c01-115">Click **Design** in the Microsoft Dynamics Office Add-in after you’ve logged in.</span></span>
2.  <span data-ttu-id="78c01-116">Para informações de cabeçalho, use o botão **Adicionar campos**.</span><span class="sxs-lookup"><span data-stu-id="78c01-116">For header information, use the **Add fields** button.</span></span>
3.  <span data-ttu-id="78c01-117">Selecione a fonte de dados da entidade de BudgetPlanJustification e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="78c01-117">Select the entity data source of BudgetPlanJustification, and click **Next**.</span></span> <span data-ttu-id="78c01-118">**Observação:** essa entidade é necessária para qualquer documento.</span><span class="sxs-lookup"><span data-stu-id="78c01-118">**Note:** This entity is required for any justification document.</span></span> <span data-ttu-id="78c01-119">É possível usar outras entidades, mas ocorrerá uma falha ao carregar novamente no Microsoft Dynamics 365 Finance se essa entidade não estiver incluída.</span><span class="sxs-lookup"><span data-stu-id="78c01-119">Other entities can be used but the upload back to Microsoft Dynamics 365 Finance will fail if this entity isn’t included.</span></span>
4.  <span data-ttu-id="78c01-120">Adicione as etiquetas e valores BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter e DocumentNumber no documento do Word.</span><span class="sxs-lookup"><span data-stu-id="78c01-120">Add the BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter, and DocumentNumber labels and values in the Word document.</span></span> <span data-ttu-id="78c01-121">**Observação:** é possível usar suas próprias etiquetas, em vez de etiquetas padrão, se necessário.</span><span class="sxs-lookup"><span data-stu-id="78c01-121">**Note:** You can use your own custom labels, rather than the standard labels, if needed.</span></span>
5.  <span data-ttu-id="78c01-122">Clique em **Concluído** para concluir a seção de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="78c01-122">Click **Done** to complete the header section.</span></span>
6.  <span data-ttu-id="78c01-123">Para detalhes de nível de linha dos valores de plano de orçamento, clique em **Adicionar tabela**.</span><span class="sxs-lookup"><span data-stu-id="78c01-123">For line level detail of budget plan amounts, click **Add table**.</span></span>
7.  <span data-ttu-id="78c01-124">Selecione novamente a fonte de dados da entidade de BudgetPlanJustification e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="78c01-124">Again, select the entity data source of BudgetPlanJustification, and click **Next**.</span></span>
8.  <span data-ttu-id="78c01-125">Adicione campos para EffectiveDate, ScenarioName, AccountDisplayValue e AccountingCurrencyExpenseAmount.</span><span class="sxs-lookup"><span data-stu-id="78c01-125">Add fields for EffectiveDate, ScenarioName, AccountDisplayValue, and AccountingCurrencyExpenseAmount.</span></span> <span data-ttu-id="78c01-126">**Observação:** se comentários estiverem disponíveis para adição nas linhas de plano de orçamento individuais, eles podem ser adicionados à tabela aqui.</span><span class="sxs-lookup"><span data-stu-id="78c01-126">**Note:** If comments are available to add within individual budget plan lines, those can be added to the table here.</span></span>
9.  <span data-ttu-id="78c01-127">Adicione qualquer instrução adicional para fornecer ao usuário final e realize qualquer formatação ou estilização no documento.</span><span class="sxs-lookup"><span data-stu-id="78c01-127">Add any additional instructions to provide to the end user, and perform any necessary formatting or styling to the document.</span></span>
10. <span data-ttu-id="78c01-128">Salve o documento no seu computador local e feche o arquivo antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="78c01-128">Save the document to your local computer and close the file before continuing.</span></span>

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a><span data-ttu-id="78c01-129">Configurar o processo de planejamento de orçamento para usar o modelo de justificativa</span><span class="sxs-lookup"><span data-stu-id="78c01-129">Set up the Budget planning process to use the Justification template</span></span>

1.  <span data-ttu-id="78c01-130">Vá para **Orçamento** &gt; **Configuração** &gt; **Planejamento de orçamento** &gt; **Modelos de documento de justificativa**.</span><span class="sxs-lookup"><span data-stu-id="78c01-130">Go to **Budgeting** &gt; **Setup** &gt; **Budget planning** &gt; **Justification document templates**.</span></span>
2.  <span data-ttu-id="78c01-131">Clique em **Novo** e acesse o documento recém-criado do Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="78c01-131">Click **New** and browse to your newly created Microsoft Word document.</span></span>
3.  <span data-ttu-id="78c01-132">Insira nome e descrição de exibição de modelo.</span><span class="sxs-lookup"><span data-stu-id="78c01-132">Enter a template display name and description.</span></span> <span data-ttu-id="78c01-133">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="78c01-133">Click **OK**.</span></span>
4.  <span data-ttu-id="78c01-134">Vá para **Orçamento** &gt; **Configuração** &gt; **Planejamento do** **orçamento** &gt; **Processo de planejamento de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="78c01-134">Go to **Budgeting** &gt; **Setup** &gt; **Budget** **planning** &gt; **Budget planning process**.</span></span>
5.  <span data-ttu-id="78c01-135">Selecione o processo no qual o modelo de justificativa deve ser usado e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="78c01-135">Select the process where the justification template should be used, and click **Edit**.</span></span>
6.  <span data-ttu-id="78c01-136">No campo **Modelo de documento de justificativa**, selecione o modelo apropriado e salve-o.</span><span class="sxs-lookup"><span data-stu-id="78c01-136">In the **Justification document template** field, select the appropriate template and save.</span></span>

##### <a name="edit-and-save-personalized-justification-documents"></a><span data-ttu-id="78c01-137">Editar e salvar documentos de justificativa personalizados</span><span class="sxs-lookup"><span data-stu-id="78c01-137">Edit and save personalized justification documents</span></span>

1.  <span data-ttu-id="78c01-138">Crie um novo plano de orçamento ou abra um plano de orçamento existente.</span><span class="sxs-lookup"><span data-stu-id="78c01-138">Create a new budget plan or open an existing budget plan.</span></span>
2.  <span data-ttu-id="78c01-139">No menu suspenso **Justificativa**, selecione **Criar nova justificativa**.</span><span class="sxs-lookup"><span data-stu-id="78c01-139">In the **Justification** drop-down menu, select **Create new justification**.</span></span>
3.  <span data-ttu-id="78c01-140">Após preencher os detalhes, selecione para carregar os documentos personalizados no menu suspenso **Justificativa**.</span><span class="sxs-lookup"><span data-stu-id="78c01-140">After filling in the details, select to upload the personalized document from the **Justification** drop-down menu.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]