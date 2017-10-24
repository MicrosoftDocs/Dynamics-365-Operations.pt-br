---
title: "Modelos de planejamento de orçamento para Excel"
description: "Este tópico descreve como criar modelos do Microsoft Excel que podem ser usados com planos de orçamento."
author: ryansandness
manager: AnnBe
ms.date: 07/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7cec40859a8c68cb8a9751c5531c67cef7706258
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="budget-planning-templates-for-excel"></a><span data-ttu-id="26ee7-103">Modelos de planejamento de orçamento para Excel</span><span class="sxs-lookup"><span data-stu-id="26ee7-103">Budget planning templates for Excel</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="26ee7-104">Este tópico descreve como criar modelos do Microsoft Excel que podem ser usados com planos de orçamento.</span><span class="sxs-lookup"><span data-stu-id="26ee7-104">This topic describes how to create Microsoft Excel templates that can be used with budget plans.</span></span>

<span data-ttu-id="26ee7-105">Este tópico mostra como criar modelos do Excel que serão usados com planos de orçamento por meio do conjunto de dados de demonstração padrão e do logon de usuário Administrador.</span><span class="sxs-lookup"><span data-stu-id="26ee7-105">This topic shows how to create Excel templates that will be used with budget plans using the standard demo data set and the Admin user login.</span></span> <span data-ttu-id="26ee7-106">Para obter mais informações sobre planejamento de orçamento, consulte [Visão geral do planejamento de orçamento.](budget-planning-overview-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="26ee7-106">For more information about budget planning, see [Budget planning overview.](budget-planning-overview-configuration.md)</span></span> <span data-ttu-id="26ee7-107">Você também pode acompanhar o tutorial [Planejamento de orçamento 101](budget-plan.md) para aprender princípios básicos de configuração e uso de módulos.</span><span class="sxs-lookup"><span data-stu-id="26ee7-107">You can also follow the [Budget planning 101](budget-plan.md) tutorial to learn basic module configuration and usage principles.</span></span>

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a><span data-ttu-id="26ee7-108">Gerar uma planilha usando o layout de documento de plano de orçamento</span><span class="sxs-lookup"><span data-stu-id="26ee7-108">Generate a worksheet using budget plan document layout</span></span>

<span data-ttu-id="26ee7-109">Documentos de plano de orçamento podem ser exibidos e editados com um ou vários layouts.</span><span class="sxs-lookup"><span data-stu-id="26ee7-109">Budget plan documents can be viewed and edited using one or more layouts.</span></span> <span data-ttu-id="26ee7-110">Cada layout pode ter um modelo de documento de plano de orçamento associado para exibir e editar os dados do plano de orçamento em uma planilha do Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-110">Each layout can have an associated budget plan document template to view and edit the budget plan data in an Excel worksheet.</span></span> <span data-ttu-id="26ee7-111">Neste tópico, um modelo de documento de plano de orçamento será gerado por meio de uma configuração de layout existente.</span><span class="sxs-lookup"><span data-stu-id="26ee7-111">In this topic, a budget plan document template will be generated using an existing layout configuration.</span></span> 

1. <span data-ttu-id="26ee7-112">Abra a **Lista de planos de orçamento** (**Orçamento** &gt; **Planos de orçamento**).</span><span class="sxs-lookup"><span data-stu-id="26ee7-112">Open the **Budget plans list** (**Budgeting** &gt; **Budget plans**).</span></span> 
2. <span data-ttu-id="26ee7-113">Clique em **Novo** para criar um novo documento de plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="26ee7-113">Click **New** to create a new budget plan document.</span></span> 

  <span data-ttu-id="26ee7-114">[![Lista de planos de orçamento](./media/bpt11-1024x552.png)](./media/bpt11.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-114">[![Budget plans list](./media/bpt11-1024x552.png)](./media/bpt11.png)</span></span> 

3. <span data-ttu-id="26ee7-115">Use a opção de linha **Adicionar** para adicionar linhas.</span><span class="sxs-lookup"><span data-stu-id="26ee7-115">Use the **Add** line option to add lines.</span></span> <span data-ttu-id="26ee7-116">Clique em **Layouts** para exibir a configuração de layout do documento de plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="26ee7-116">Click **Layouts** to view the budget plan document layout configuration.</span></span> 

  <span data-ttu-id="26ee7-117">[![Adição de planos de orçamento](./media/bpt2-1024x274.png)](./media/bpt2.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-117">[![Budget plans add](./media/bpt2-1024x274.png)](./media/bpt2.png)</span></span> 

<span data-ttu-id="26ee7-118">Você pode revisar a configuração do layout e ajustá-la quando necessário.</span><span class="sxs-lookup"><span data-stu-id="26ee7-118">You can review the layout configuration and adjust it as needed.</span></span> 
1. <span data-ttu-id="26ee7-119">Vá para **Modelo** &gt; **Gerar** para criar um arquivo do Excel para esse layout.</span><span class="sxs-lookup"><span data-stu-id="26ee7-119">Go to **Template** &gt; **Generate** to create an Excel file for this layout.</span></span> 
2. <span data-ttu-id="26ee7-120">Após a criação do modelo, vá para **Modelo** &gt; **Exibir** para abrir ou revisar o modelo de documento de plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="26ee7-120">After the template is generated, go to **Template** &gt; **View** to open and review the budget plan document template.</span></span> <span data-ttu-id="26ee7-121">É possível salvar o arquivo do Excel na sua unidade local.</span><span class="sxs-lookup"><span data-stu-id="26ee7-121">You can save the Excel file to your local drive.</span></span> 

<span data-ttu-id="26ee7-122">[![Salvar como](./media/bpt3-1024x545.png)](./media/bpt3.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-122">[![Save as](./media/bpt3-1024x545.png)](./media/bpt3.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="26ee7-123">O layout de documento do plano do orçamento não pode ser editado depois que um modelo do Excel é associado a ele.</span><span class="sxs-lookup"><span data-stu-id="26ee7-123">The Budget plan document layout cannot be edited after an Excel template is associated with it.</span></span> <span data-ttu-id="26ee7-124">Para alterar o layout, exclua o arquivo do modelo do Excel associado e gere-o novamente.</span><span class="sxs-lookup"><span data-stu-id="26ee7-124">To modify the layout, delete the associated Excel template file and regenerate it.</span></span> <span data-ttu-id="26ee7-125">Isso é necessário para manter os campos no layout e na planilha sincronizados.</span><span class="sxs-lookup"><span data-stu-id="26ee7-125">This is required to keep the fields in the layout and the worksheet synchronized.</span></span> 

<span data-ttu-id="26ee7-126">O modelo do Excel conterá todos os elementos do layout do documento de plano de orçamento, no qual a coluna **Disponível em planilha** é definida como Verdadeira.</span><span class="sxs-lookup"><span data-stu-id="26ee7-126">The Excel template will contain all of the elements from the budget plan document layout, where the **Available in Worksheet** column is set to True.</span></span> <span data-ttu-id="26ee7-127">Não é possível sobrepor elementos no modelo do Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-127">Overlapping elements are not allowed in the Excel template.</span></span> <span data-ttu-id="26ee7-128">Por exemplo, se o layout contiver as colunas Solicitação Q1, Solicitação Q2, Solicitação Q3 e Solicitação Q4 e uma coluna com o total de solicitações representando a soma de todas as 4 colunas trimestrais, apenas as colunas trimestrais ou a coluna com o total estarão disponíveis para serem usadas no modelo do Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-128">For example, if the layout contains Request Q1, Request Q2, Request Q3, and Request Q4 columns, and a total request column that represents a sum of all 4 quarterly columns, only the quarterly columns or total column is available to be used in the Excel template.</span></span> <span data-ttu-id="26ee7-129">O arquivo do Excel pode atualizar a sobreposição de colunas durante a atualização, já que os dados na tabela poderiam ficar desatualizados e se tornar imprecisos.</span><span class="sxs-lookup"><span data-stu-id="26ee7-129">The Excel file cannot update overlapping columns during the update because data in the table could become out of date and inaccurate.</span></span>

<span data-ttu-id="26ee7-130">[![Exemplo](./media/bpt4-1024x615.png)](./media/bpt4.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-130">[![Example](./media/bpt4-1024x615.png)](./media/bpt4.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="26ee7-131">Para evitar possíveis problemas com a exibição e edição de dados de plano de orçamento usando o Excel, o mesmo usuário deve estar conectado tanto ao Microsoft Dynamics 365 for Finance and Operations, edição Enterprise quanto ao Microsoft Dynamics Office Add-in Data Connector.</span><span class="sxs-lookup"><span data-stu-id="26ee7-131">To avoid potential issues with viewing and editing budget plan data using Excel, the same user should be logged into both Microsoft Dynamics 365 for Finance and Operations, Enterprise edition and the Microsoft Dynamics Office Add-in Data Connector.</span></span>

## <a name="add-a-header-to-budget-plan-document-template"></a><span data-ttu-id="26ee7-132">Adicionar um cabeçalho ao modelo de documento de plano de orçamento</span><span class="sxs-lookup"><span data-stu-id="26ee7-132">Add a header to budget plan document template</span></span>
<span data-ttu-id="26ee7-133">Para adicionar informações de cabeçalho, selecione a linha superior no arquivo do Excel e insira linhas vazias.</span><span class="sxs-lookup"><span data-stu-id="26ee7-133">To add header information, select the top row in the Excel file and insert empty rows.</span></span> <span data-ttu-id="26ee7-134">Clique em **Design** no **Conector de Dados** para adicionar campos de cabeçalho ao arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-134">Click **Design** in the **Data Connector** to add header fields to the Excel file.</span></span>

<span data-ttu-id="26ee7-135">[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-135">[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png)</span></span> 

<span data-ttu-id="26ee7-136">Na guia **Design**, clique nos campos **Adicionar** e, em seguida, selecione **BudgetPlanHeader** como a fonte de dados da entidade.</span><span class="sxs-lookup"><span data-stu-id="26ee7-136">In the **Design** tab, click **Add** fields, and then select **BudgetPlanHeader** as the entity data source.</span></span>

<span data-ttu-id="26ee7-137">[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-137">[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)</span></span>

<span data-ttu-id="26ee7-138">Aponte o cursor para o local desejado no arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-138">Point the cursor to the desired location in the Excel file.</span></span> <span data-ttu-id="26ee7-139">Clique em **Adicionar etiqueta** para adicionar a etiqueta do campo ao local selecionado.</span><span class="sxs-lookup"><span data-stu-id="26ee7-139">Click **Add label** to add the field label to the selected location.</span></span> <span data-ttu-id="26ee7-140">Selecione **Adicionar Valor** para adicionar o campo de valor ao local selecionado.</span><span class="sxs-lookup"><span data-stu-id="26ee7-140">Select **Add Value** to add the value field to the selected place.</span></span> <span data-ttu-id="26ee7-141">Clique em **Concluído** para fechar o designer.</span><span class="sxs-lookup"><span data-stu-id="26ee7-141">Click **Done** to close the designer.</span></span>

## <a name="bpt7mediabpt7pngmediabpt7png"></a><span data-ttu-id="26ee7-142">[![bpt7](./media/bpt7.png)](./media/bpt7.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-142">[![bpt7](./media/bpt7.png)](./media/bpt7.png)</span></span>

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a><span data-ttu-id="26ee7-143">Adicionar uma coluna calculada à tabela do modelo de documento de plano de orçamento</span><span class="sxs-lookup"><span data-stu-id="26ee7-143">Add a calculated column to budget plan document template table</span></span>
--------------------------------------------------------------

<span data-ttu-id="26ee7-144">Em seguida, colunas calculadas serão adicionadas ao modelo de documento de plano de orçamento gerado.</span><span class="sxs-lookup"><span data-stu-id="26ee7-144">Next, calculated columns will be added to generated budget plan document template.</span></span> <span data-ttu-id="26ee7-145">Uma coluna **Total de Solicitações**, que resume as colunas Solicitação Q1: Solicitação Q4, e uma coluna **Ajuste**, que recalcula a coluna **Total de Solicitações** por um fator predefinido.</span><span class="sxs-lookup"><span data-stu-id="26ee7-145">A **Total request** column, which summarizes Request Q1: Request Q4 columns, and an **Adjustment** column, which recalculates the **Total Request** column by a predefined factor.</span></span>

<span data-ttu-id="26ee7-146">Clique em **Design** no **Conector de Dados** para adicionar colunas à tabela.</span><span class="sxs-lookup"><span data-stu-id="26ee7-146">Click **Design** in the **Data connector** to add columns to the table.</span></span> <span data-ttu-id="26ee7-147">Clique em **Editar** ao lado da fonte de dados **BudgetPlanWorksheet** para iniciar a adição das colunas.</span><span class="sxs-lookup"><span data-stu-id="26ee7-147">Click **Edit** next to **BudgetPlanWorksheet** data source to start adding columns.</span></span>

<span data-ttu-id="26ee7-148">[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-148">[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png)</span></span> 

<span data-ttu-id="26ee7-149">O grupo de campos selecionado exibe a coluna que está disponível no modelo.</span><span class="sxs-lookup"><span data-stu-id="26ee7-149">The selected field group displays the columns that are available in the template.</span></span> <span data-ttu-id="26ee7-150">Clique em **Fórmula** para adicionar uma nova coluna.</span><span class="sxs-lookup"><span data-stu-id="26ee7-150">Click **Formula** to add a new column.</span></span> <span data-ttu-id="26ee7-151">Nomeie a nova coluna e depois cole a fórmula no campo **Fórmula**.</span><span class="sxs-lookup"><span data-stu-id="26ee7-151">Name the new column and then paste the formula into the **Formula** field.</span></span> <span data-ttu-id="26ee7-152">Clique em **Atualizar** para inserir a coluna.</span><span class="sxs-lookup"><span data-stu-id="26ee7-152">Click **Update** to insert the column.</span></span>

<span data-ttu-id="26ee7-153">[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-153">[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="26ee7-154">Para definir a fórmula, crie a fórmula na planilha e depois copie-a na janela **Design**.</span><span class="sxs-lookup"><span data-stu-id="26ee7-154">To define the formula, create the formula in the spreadsheet, and then copy it to the **Design** window.</span></span> <span data-ttu-id="26ee7-155">Uma tabela vinculada do Finance and Operations geralmente será nomeada como "AXTable1".</span><span class="sxs-lookup"><span data-stu-id="26ee7-155">A Finance and Operations bound table will typically be named "AXTable1".</span></span> <span data-ttu-id="26ee7-156">Por exemplo, para resumir as colunas Solicitação Q1 : Solicitação Q4 na planilha, a fórmula = AxTable1\[Solicitação Q1\]+AxTable1\[Solicitação Q2\]+AxTable1\[Solicitação Q3\]+AxTable1\[Solicitação Q4\].</span><span class="sxs-lookup"><span data-stu-id="26ee7-156">For example, to summarize Request Q1 : Request Q4 columns in the spreadsheet, the formula = AxTable1\[Request Q1\]+AxTable1\[Request Q2\]+AxTable1\[Request Q3\]+AxTable1\[Request Q4\].</span></span>

<span data-ttu-id="26ee7-157">Repita essas etapas para inserir a coluna **Ajuste**.</span><span class="sxs-lookup"><span data-stu-id="26ee7-157">Repeat these steps to insert the **Adjustment** column.</span></span> <span data-ttu-id="26ee7-158">Use a fórmula = AxTable1\[Total da solicitações\]\*$I$1 para essa coluna.</span><span class="sxs-lookup"><span data-stu-id="26ee7-158">Use formula = AxTable1\[Total request\]\*$I$1 for this column.</span></span> <span data-ttu-id="26ee7-159">Isso usará o valor na célula I1 e multiplicará os valores na coluna **Total de solicitações** para calcular os valores de ajuste.</span><span class="sxs-lookup"><span data-stu-id="26ee7-159">This will take the value in cell I1 and multiply the values in the **Total request** column to calculate adjustment amounts.</span></span>

<span data-ttu-id="26ee7-160">Salve e feche o arquivo do Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-160">Save and close the Excel file.</span></span> <span data-ttu-id="26ee7-161">Retorne ao Finance and Operations e, em **Layouts**, clique em **Modelo &gt; Carregar** para carregar o modelo do Excel salvo que será usado no plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="26ee7-161">Return to Finance and Operations, and in **Layouts**, click **Template &gt; Upload** to upload the saved Excel template to be used for the budget plan.</span></span> 

<span data-ttu-id="26ee7-162">[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-162">[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png)</span></span> 

<span data-ttu-id="26ee7-163">Feche o controle deslizante **Layouts**.</span><span class="sxs-lookup"><span data-stu-id="26ee7-163">Close the **Layouts** slider.</span></span> <span data-ttu-id="26ee7-164">No documento **Plano de orçamento**, clique em **Planilha** para exibir e editar o documento no Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-164">In **Budget plan** document, click **Worksheet** to view and edit the document in Excel.</span></span> <span data-ttu-id="26ee7-165">Observe que o modelo do Excel ajustado foi usado para criar essa planilha de plano de orçamento e as colunas calculadas são atualizadas por meio de fórmulas que foram definidas nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="26ee7-165">Note that the adjusted Excel template was used to create this budget plan worksheet and calculated columns are updated using the formulas that were defined in the previous steps.</span></span> 

<span data-ttu-id="26ee7-166">[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-166">[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)</span></span>

## <a name="tips--tricks-for-creating-budget-plan-templates"></a><span data-ttu-id="26ee7-167">Dicas e truques para criar modelos de plano de orçamento</span><span class="sxs-lookup"><span data-stu-id="26ee7-167">Tips & tricks for creating budget plan templates</span></span>
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a><span data-ttu-id="26ee7-168">Posso adicionar e usar fontes de dados adicionais em um modelo de plano de orçamento?</span><span class="sxs-lookup"><span data-stu-id="26ee7-168">Can I add and use additional data sources to a budget plan template?</span></span>

<span data-ttu-id="26ee7-169">Sim, você pode usar o menu **Design** para adicionar mais entidades às mesmas ou a outras planilhas no modelo do Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-169">Yes, you can use the **Design** menu to add additional entities to the same or other sheets in the Excel template.</span></span> <span data-ttu-id="26ee7-170">Por exemplo, você pode adicionar as fontes de dados **BudgetPlanProposedProject** para criar e manter uma lista de projetos propostos ao trabalhar com dados de plano de orçamento no Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-170">For example, you can add the **BudgetPlanProposedProject** data source to create and maintain a list of proposed projects at the same time when working with budget plan data in Excel.</span></span> <span data-ttu-id="26ee7-171">Observe que a inclusão de alto volume de fontes de dados pode ter impacto sobre o desempenho da pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="26ee7-171">Note that including high-volume data sources might impact performance of the Excel workbook.</span></span> 

<span data-ttu-id="26ee7-172">Você pode usar a opção **Filtro** no **Conector de Dados** para adicionar os filtros desejados a fontes de dados adicionais.</span><span class="sxs-lookup"><span data-stu-id="26ee7-172">You can use the **Filter** option in the **Data Connector** to add desired filters to additional data sources.</span></span>

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a><span data-ttu-id="26ee7-173">Posso ocultar a opção Design no Conector de Dados para outros usuários?</span><span class="sxs-lookup"><span data-stu-id="26ee7-173">Can I hide the Design option in the Data connector for other users?</span></span>

<span data-ttu-id="26ee7-174">Sim, abra as opções **Conector de Dados** para ocultar a opção **Design** de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="26ee7-174">Yes, open the **Data Connector** options to hide the **Design** option from other users.</span></span>

<span data-ttu-id="26ee7-175">[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-175">[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)</span></span>

<span data-ttu-id="26ee7-176">Expanda as **Opções de conector de dados** e desmarque a caixa de seleção **Habilitar design**.</span><span class="sxs-lookup"><span data-stu-id="26ee7-176">Expand **Data connector options** and clear the **Enable design** check box.</span></span> <span data-ttu-id="26ee7-177">Isso ocultará a opção **Design** do **Conector de Dados**.</span><span class="sxs-lookup"><span data-stu-id="26ee7-177">This will hide the **Design** option from the **Data connector**.</span></span>

<span data-ttu-id="26ee7-178">[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-178">[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)</span></span>

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a><span data-ttu-id="26ee7-179">Posso impedir que usuários fechem acidentalmente o Conector de Dados ao trabalhar com dados?</span><span class="sxs-lookup"><span data-stu-id="26ee7-179">Can I prevent users from accidently closing the Data connector while working with data?</span></span>

<span data-ttu-id="26ee7-180">Recomendamos o bloqueio do modelo para impedir que usuários o fechem.</span><span class="sxs-lookup"><span data-stu-id="26ee7-180">We recommend locking the template to prevent users from closing it.</span></span> <span data-ttu-id="26ee7-181">Para ativar o bloqueio, clique no **Conector de Dados**, no canto superior direito no qual aparece uma seta.</span><span class="sxs-lookup"><span data-stu-id="26ee7-181">To turn on the lock, click the **Data connector**, in the top right corner an arrow appears.</span></span> 

<span data-ttu-id="26ee7-182">[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-182">[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png)</span></span> 

<span data-ttu-id="26ee7-183">Clique na seta para obter um menu adicional.</span><span class="sxs-lookup"><span data-stu-id="26ee7-183">Click the arrow for an additional menu.</span></span> <span data-ttu-id="26ee7-184">Selecione **Bloqueio**.</span><span class="sxs-lookup"><span data-stu-id="26ee7-184">Select **Lock**.</span></span>

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a><span data-ttu-id="26ee7-185">[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-185">[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)</span></span>

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a><span data-ttu-id="26ee7-186">Posso usar outros recursos do Excel, como formatação de células, formatação condicional e gráficos com meus modelos de plano de orçamento?</span><span class="sxs-lookup"><span data-stu-id="26ee7-186">Can I use other Excel features, like cell formatting, colors, conditional formatting, and charts with my budget plan templates?</span></span>

<span data-ttu-id="26ee7-187">Sim, a maior parte dos recursos padrão do Excel funcionará nos modelos de plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="26ee7-187">Yes, most of the standard Excel capabilities will work in budget plan templates.</span></span> <span data-ttu-id="26ee7-188">Recomendamos o uso da codificação por cor para que os usuários diferenciem entre colunas somente leitura e editáveis.</span><span class="sxs-lookup"><span data-stu-id="26ee7-188">We recommend using color-coding for users to distinguish between read-only and editable columns.</span></span> <span data-ttu-id="26ee7-189">A formatação condicional pode ser usada para destacar áreas problemáticas do orçamento.</span><span class="sxs-lookup"><span data-stu-id="26ee7-189">Conditional formatting can be used to highlight problematic areas of the budget.</span></span> <span data-ttu-id="26ee7-190">Os totais de coluna podem facilmente ser apresentados por meio de fórmulas padrão do Excel acima da tabela.</span><span class="sxs-lookup"><span data-stu-id="26ee7-190">Column totals can easily be presented by using standard Excel formulas above the table.</span></span>

<span data-ttu-id="26ee7-191">Você também pode criar e usar tabelas e gráficos dinâmicos para mais agrupamentos e visualizações de dados de orçamento.</span><span class="sxs-lookup"><span data-stu-id="26ee7-191">You can also create and use pivot tables and charts for additional groupings and visualizations of budget data.</span></span> <span data-ttu-id="26ee7-192">Na guia **Dados**, no grupo **Conexões**, clique em **Atualizar Tudo** e depois clique em **Propriedades da Conexão**.</span><span class="sxs-lookup"><span data-stu-id="26ee7-192">On the **Data** tab, in the **Connections** group, click **Refresh All**, and then click **Connection Properties**.</span></span> <span data-ttu-id="26ee7-193">Clique na guia **Uso**. Em **Atualizar**, marque a caixa de seleção **Atualizar dados ao abrir o arquivo**.</span><span class="sxs-lookup"><span data-stu-id="26ee7-193">Click the **Usage** tab. Under **Refresh**, select the **Refresh data when opening the file** check box.</span></span> 

<span data-ttu-id="26ee7-194">[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)</span><span class="sxs-lookup"><span data-stu-id="26ee7-194">[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)</span></span>




