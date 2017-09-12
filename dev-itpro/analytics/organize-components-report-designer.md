---
title: "Organizar componentes do relatório no designer de relatórios"
description: "Depois que você tiver desenvolvido blocos de construção e relatórios gerados, é útil organizar esses objetos para que fiquem mais fácil para os usuários a localizar. Este artigo explica como organizar objetos no report designer, blocos de construção e relatórios existentes."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: fade9e2acdb94daa6a908d949c578fd7ed439882
ms.contentlocale: pt-br
ms.lasthandoff: 07/18/2017

---

# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="59d41-104">Organizar componentes do relatório no designer de relatórios</span><span class="sxs-lookup"><span data-stu-id="59d41-104">Organize report components in report designer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="59d41-105">Depois que você tiver desenvolvido blocos de construção e relatórios gerados, é útil organizar esses objetos para que fiquem mais fácil para os usuários a localizar.</span><span class="sxs-lookup"><span data-stu-id="59d41-105">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="59d41-106">Este artigo explica como organizar objetos no report designer, blocos de construção e relatórios existentes.</span><span class="sxs-lookup"><span data-stu-id="59d41-106">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="59d41-107">Você pode renomear pastas, relatórios, blocos de construção e outros objetos no designer de relatórios para ajudar a organizar seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="59d41-107">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="59d41-108">Dependendo do tipo de objeto que você renomear, talvez seja necessário atualizar associações a esse objeto.</span><span class="sxs-lookup"><span data-stu-id="59d41-108">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="59d41-109">Renomear uma pasta ou um bloco de construção no Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="59d41-109">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="59d41-110">No Designer de Relatórios, você pode renomear pastas, definições de relatório, definições de linha, definições de coluna e definições de árvore de relatórios.</span><span class="sxs-lookup"><span data-stu-id="59d41-110">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span> <span data-ttu-id="59d41-111">**Observação:** quando você renomeia um bloco de construção, você deve atualizar as definições de relatórios que usam o bloco de construção.</span><span class="sxs-lookup"><span data-stu-id="59d41-111">**Note:** When you rename a building block, you must update any reporting definitions that use the building block.</span></span> <span data-ttu-id="59d41-112">Caso contrário, não é possível gerar um novo relatório.</span><span class="sxs-lookup"><span data-stu-id="59d41-112">Otherwise, a new report can't be generated.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="59d41-113">Renomear uma pasta ou um bloco de construção no Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="59d41-113">Rename a folder or building block in Report Designer</span></span>

1.  <span data-ttu-id="59d41-114">No Designer de Relatórios, use o painel de navegação para localizar a pasta ou ou o objeto a ser renomeado.</span><span class="sxs-lookup"><span data-stu-id="59d41-114">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2.  <span data-ttu-id="59d41-115">Clique com o botão direito do mouse na pasta ou objeto, e clique em **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="59d41-115">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="59d41-116">O campo **Nome** no painel de navegação torna-se disponível.</span><span class="sxs-lookup"><span data-stu-id="59d41-116">The **Name** field in the navigation pane becomes available.</span></span>
3.  <span data-ttu-id="59d41-117">Digite um novo nome e pressione Inserir.</span><span class="sxs-lookup"><span data-stu-id="59d41-117">Type a new name, and then press Enter.</span></span>
4.  <span data-ttu-id="59d41-118">Se o bloco de construção for uma definição de linha, uma definição de coluna ou uma definição de árvore de relatórios, atualize outros blocos de construção associados a ele.</span><span class="sxs-lookup"><span data-stu-id="59d41-118">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="59d41-119">Clique com o botão direito do mouse no bloco de construção que você renomeou na etapa 3, selecione **Associações** e selecione um item na lista para a atualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="59d41-119">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5.  <span data-ttu-id="59d41-120">Repita a etapa 4 até que todos os itens associados sejam atualizados.</span><span class="sxs-lookup"><span data-stu-id="59d41-120">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="59d41-121">Criar e gerenciar grupos de relatórios</span><span class="sxs-lookup"><span data-stu-id="59d41-121">Create and manage report groups</span></span>
<span data-ttu-id="59d41-122">você pode agrupar definições de relatório para gerar vários relatórios ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="59d41-122">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="59d41-123">Para criar, modificar, excluir e gerar grupos de relatório, você deve ter a função de designer ou administrador.</span><span class="sxs-lookup"><span data-stu-id="59d41-123">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="59d41-124">Os usuários com a função de gerador podem gerar grupos de relatórios, e também podem modificar as definições de relatório do usuário para grupos de relatórios.</span><span class="sxs-lookup"><span data-stu-id="59d41-124">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="59d41-125">Criar um grupo de relatórios</span><span class="sxs-lookup"><span data-stu-id="59d41-125">Create a report group</span></span>

1.  <span data-ttu-id="59d41-126">No Designer de Relatórios, clique em **Grupos de Relatórios** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="59d41-126">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="59d41-127">No menu **Arquivo**, clique em **Novo** &gt; **Definição de grupo de relatório** para abrir um novo grupo de relatório na janela de visualização.</span><span class="sxs-lookup"><span data-stu-id="59d41-127">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="59d41-128">Como alternativa, clique no botão **Grupo de relatório** ![Grupo de relatório](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Grupo de relatório") na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="59d41-128">Alternatively, click the **Report Group** button ![Report Group](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Report Group") on the toolbar.</span></span>
3.  <span data-ttu-id="59d41-129">Clique na guia **Grupo de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="59d41-129">Click the **Report Group** tab.</span></span> <span data-ttu-id="59d41-130">Para substituir as informações nas definições de relatório individuais para a geração deste relatório, marque a caixa de seleção **Substituir a empresa, os detalhes e as configurações de data das definições de relatório individuais**.</span><span class="sxs-lookup"><span data-stu-id="59d41-130">To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="59d41-131">As informações de nome da empresa, nível de detalhe, configurações provisórias e data são preenchidas automaticamente, mas você ainda pode fazer atualizações.</span><span class="sxs-lookup"><span data-stu-id="59d41-131">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4.  <span data-ttu-id="59d41-132">Marque a caixa de seleção **Incluir todas as moedas de relatório** se desejar que os vários relatórios gerados exibam essas moedas.</span><span class="sxs-lookup"><span data-stu-id="59d41-132">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="59d41-133">Você pode acessar diversas exibições clicando no botão **Moeda** no Visualizador Web quando você exibir o relatório.</span><span class="sxs-lookup"><span data-stu-id="59d41-133">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5.  <span data-ttu-id="59d41-134">No campo **Relatórios no grupo**, clique em **Adicionar** para selecionar os relatórios a serem incluídos no grupo Relatório.</span><span class="sxs-lookup"><span data-stu-id="59d41-134">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="59d41-135">Para selecionar vários relatórios na caixa de diálogo **Adicionar**, mantenha pressionada a tecla CTRL enquanto seleciona relatórios.</span><span class="sxs-lookup"><span data-stu-id="59d41-135">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="59d41-136">Quando terminar de selecionar os relatórios, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="59d41-136">When you've finished selecting reports, click **OK**.</span></span>
6.  <span data-ttu-id="59d41-137">Clique em **Arquivo** &gt; **Salvar** para salvar o novo grupo de relatório.</span><span class="sxs-lookup"><span data-stu-id="59d41-137">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="59d41-138">Modificar um grupo de relatório</span><span class="sxs-lookup"><span data-stu-id="59d41-138">Modify a report group</span></span>

1.  <span data-ttu-id="59d41-139">No Designer de Relatórios, clique em **Grupos de Relatórios** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="59d41-139">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="59d41-140">Clique duas vezes no grupo de relatórios a ser modificado.</span><span class="sxs-lookup"><span data-stu-id="59d41-140">Double-click the report group to modify.</span></span>
3.  <span data-ttu-id="59d41-141">Clique na guia **Grupo de Relatório** e faça as alterações desejadas.</span><span class="sxs-lookup"><span data-stu-id="59d41-141">On the **Report Group** tab, make the changes that you want.</span></span>
4.  <span data-ttu-id="59d41-142">No menu **Arquivo**, clique em **Salvar** para salvar o grupo de relatório modificado. Como alternativa, clique no botão **Salvar** ![Salvar](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Salvar") na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="59d41-142">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Save") on the toolbar.</span></span>

<span data-ttu-id="59d41-143">**Nota:** Se você agendou relatórios a serem gerados em intervalos definidos, pode substituir essas configurações e gerar logo um relatório.</span><span class="sxs-lookup"><span data-stu-id="59d41-143">**Note:** If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="59d41-144">Gerar um relatório do grupo de relatório</span><span class="sxs-lookup"><span data-stu-id="59d41-144">Generate a report group report</span></span>

1.  <span data-ttu-id="59d41-145">No Designer de Relatórios, clique em **Grupos de Relatórios** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="59d41-145">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="59d41-146">Abra o grupo de relatórios a ser gerado.</span><span class="sxs-lookup"><span data-stu-id="59d41-146">Open the report group to generate.</span></span>
3.  <span data-ttu-id="59d41-147">Clique no botão **Gerar relatório** ![Gerar relatório](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Gerar relatório") para gerar relatórios.</span><span class="sxs-lookup"><span data-stu-id="59d41-147">Click the **Generate Report** button ![Generate Report](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="59d41-148">Excluir um grupo de relatório</span><span class="sxs-lookup"><span data-stu-id="59d41-148">Delete a report group</span></span>

1.  <span data-ttu-id="59d41-149">No Designer de Relatórios, clique em **Grupos de Relatórios** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="59d41-149">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="59d41-150">Clique com o botão direito do mouse no grupo de relatórios e selecione **Excluir** para excluir.</span><span class="sxs-lookup"><span data-stu-id="59d41-150">Right-click the report group to delete, and then select **Delete**.</span></span>
3.  <span data-ttu-id="59d41-151">Quando uma mensagem de confirmação aparecer, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="59d41-151">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="59d41-152">Controles de guia do grupo de relatórios</span><span class="sxs-lookup"><span data-stu-id="59d41-152">Report Group tab controls</span></span>
<span data-ttu-id="59d41-153">A tabela a seguir descreve os controles na guia **Grupo de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="59d41-153">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59d41-154">Controle</span><span class="sxs-lookup"><span data-stu-id="59d41-154">Control</span></span></th>
<th><span data-ttu-id="59d41-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="59d41-155">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="59d41-156">Substituir a empresa, os detalhes e as configurações de data das definições de relatório individuais</span><span class="sxs-lookup"><span data-stu-id="59d41-156">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="59d41-157">Marque esta caixa de seleção para substituir definições de relatório individuais dos relatórios nesse grupo de relatórios para a geração apenas desses relatórios.</span><span class="sxs-lookup"><span data-stu-id="59d41-157">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59d41-158">Nome da empresa</span><span class="sxs-lookup"><span data-stu-id="59d41-158">Company name</span></span></td>
<td><span data-ttu-id="59d41-159">Selecione a empresa a ser usada para os relatórios.</span><span class="sxs-lookup"><span data-stu-id="59d41-159">Select the company to use for the reports.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="59d41-160">Nível de detalhe</span><span class="sxs-lookup"><span data-stu-id="59d41-160">Detail level</span></span></td>
<td><span data-ttu-id="59d41-161">Especifique o nível de detalhamento que os relatórios incluem.</span><span class="sxs-lookup"><span data-stu-id="59d41-161">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="59d41-162"><strong>Financeiro</strong>− Um relatório de resumo de alto nível.</span><span class="sxs-lookup"><span data-stu-id="59d41-162"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="59d41-163">Você não pode fazer uma busca detalhada em contas e dimensões, exceto naquelas contas e dimensões que foram adicionadas pela árvore do relatório.</span><span class="sxs-lookup"><span data-stu-id="59d41-163">You can't drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="59d41-164"><strong>Financeiro &amp; Conta</strong> − Um relatório que contém detalhes de resumo e conta de alto nível.</span><span class="sxs-lookup"><span data-stu-id="59d41-164"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="59d41-165"><strong>Financeiro, Conta &amp; Transação</strong> − Um relatório que contém detalhes de resumo e transação de alto nível.</span><span class="sxs-lookup"><span data-stu-id="59d41-165"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59d41-166">Provisional</span><span class="sxs-lookup"><span data-stu-id="59d41-166">Provisional</span></span></td>
<td><span data-ttu-id="59d41-167">Especifique os tipos de atividade que os relatórios incluem.</span><span class="sxs-lookup"><span data-stu-id="59d41-167">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="59d41-168"><strong>Atividade lançada somente</strong> − Inclui somente as transações e os saldos que são lançados em seus dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="59d41-168"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="59d41-169"><strong>Atividade lançada e não lançada</strong> − Inclui todas as transações e os saldos que são inseridos e lançados em seus dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="59d41-169"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="59d41-170"><strong>Atividade somente não lançada</strong> − Inclui somente as transações que são inseridas, mas ainda não lançadas, em seus dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="59d41-170"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="59d41-171">Incluir todas as moedas de relatório</span><span class="sxs-lookup"><span data-stu-id="59d41-171">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="59d41-172">Se as moedas de relatório adicionais estiverem configuradas no sistema ERP do Microsoft Dynamics, elas serão listadas aqui.</span><span class="sxs-lookup"><span data-stu-id="59d41-172">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="59d41-173">Selecione esta caixa de seleção para que os relatórios adicionais sejam gerados nas moedas indicadas.</span><span class="sxs-lookup"><span data-stu-id="59d41-173">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="59d41-174">Para exibir esses relatórios no Visualizador da Web, clique no botão <strong>Moeda</strong>, e então selecione a moeda.</span><span class="sxs-lookup"><span data-stu-id="59d41-174">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59d41-175">Informações de data não salvas com a definição de relatório</span><span class="sxs-lookup"><span data-stu-id="59d41-175">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="59d41-176">Período base</span><span class="sxs-lookup"><span data-stu-id="59d41-176">Base period</span></span></li>
<li><span data-ttu-id="59d41-177">Ano base</span><span class="sxs-lookup"><span data-stu-id="59d41-177">Base year</span></span></li>
<li><span data-ttu-id="59d41-178">Período coberto</span><span class="sxs-lookup"><span data-stu-id="59d41-178">Period covered</span></span></li>
</ul>
<span data-ttu-id="59d41-179">Somente as configurações do Período Base Padrão são salvas com a definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="59d41-179">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="59d41-180">Informações de data salvas com a definição de relatório</span><span class="sxs-lookup"><span data-stu-id="59d41-180">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="59d41-181">Data do relatório</span><span class="sxs-lookup"><span data-stu-id="59d41-181">Report date</span></span></li>
<li><span data-ttu-id="59d41-182">Período base padrão</span><span class="sxs-lookup"><span data-stu-id="59d41-182">Default base period</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="59d41-183">Relatórios em grupo</span><span class="sxs-lookup"><span data-stu-id="59d41-183">Reports in group</span></span></td>
<td><span data-ttu-id="59d41-184">Adicionar, remover e reordenar relatórios no grupo de relatório.</span><span class="sxs-lookup"><span data-stu-id="59d41-184">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="59d41-185">Para adicionar definições de relatório no grupo de relatórios, clique duas vezes no grupo de relatórios para abri-lo, e clique em <strong>Adicionar</strong>.</span><span class="sxs-lookup"><span data-stu-id="59d41-185">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="59d41-186">Selecione os relatórios para incluir no grupo de relatórios e clique em <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="59d41-186">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="59d41-187">Para remover um relatório do grupo de relatório, selecione-o e clique em <strong>Remover</strong>.</span><span class="sxs-lookup"><span data-stu-id="59d41-187">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="59d41-188">Para mudar a ordem em que os relatórios são gerados, selecione um relatório na lista e clique em <strong>Mover para cima</strong> ou <strong>Mover para baixo</strong>.</span><span class="sxs-lookup"><span data-stu-id="59d41-188">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="59d41-189">Consulte também</span><span class="sxs-lookup"><span data-stu-id="59d41-189">See also</span></span>
--------

[<span data-ttu-id="59d41-190">Relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="59d41-190">Financial reporting</span></span>](financial-reporting-intro.md)




