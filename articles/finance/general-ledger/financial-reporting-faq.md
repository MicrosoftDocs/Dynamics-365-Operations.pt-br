---
title: Perguntas frequentes sobre relatórios financeiros
description: Este tópico lista perguntas relacionadas a relatórios financeiros de outros usuários.
author: jiwo
manager: tfehr
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2d49213ea18e09f04b026559bdca49fee1de0ef7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249292"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="89b9f-103">Perguntas frequentes sobre relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="89b9f-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="89b9f-104">Este tópico lista perguntas relacionadas a relatórios financeiros de outros usuários.</span><span class="sxs-lookup"><span data-stu-id="89b9f-104">This topic lists questions related to financial reporting that other users have had.</span></span> 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="89b9f-105">Como posso restringir o acesso a um relatório usando a segurança em árvore?</span><span class="sxs-lookup"><span data-stu-id="89b9f-105">How do I restrict access to a report using Tree security?</span></span>

<span data-ttu-id="89b9f-106">Cenário: a empresa de demonstração USMF tem um relatório de balanço e não quer que todos os usuários de relatórios financeiros sejam capazes de exibi-lo no D365.</span><span class="sxs-lookup"><span data-stu-id="89b9f-106">Scenario: The USMF demo company has a Balance sheet report that it doesn’t want all Financial reporting users to be able to view in D365.</span></span> <span data-ttu-id="89b9f-107">Solução: você pode usar a segurança em árvore para restringir o acesso a um único relatório. Assim, apenas determinados usuários podem acessar o relatório.</span><span class="sxs-lookup"><span data-stu-id="89b9f-107">Solution: You can utilize Tree security to restrict access to a single report so that only certain users can access the report.</span></span> 

1.  <span data-ttu-id="89b9f-108">Faça login no Report Designer do relator financeiro</span><span class="sxs-lookup"><span data-stu-id="89b9f-108">Log into Financial Reporter Report Designer</span></span>

2.  <span data-ttu-id="89b9f-109">Crie uma nova definição de árvore (Arquivo | Novo | Definição de árvore) a.</span><span class="sxs-lookup"><span data-stu-id="89b9f-109">Create a new Tree Definition (File | New | Tree Definition) a.</span></span>    <span data-ttu-id="89b9f-110">Clique duas vezes na linha **Resumo** na coluna **Segurança da unidade**.</span><span class="sxs-lookup"><span data-stu-id="89b9f-110">Double-click the **Summary** line in the **Unit Security** column.</span></span>
  <span data-ttu-id="89b9f-111">i.</span><span class="sxs-lookup"><span data-stu-id="89b9f-111">i.</span></span>    <span data-ttu-id="89b9f-112">Clique em Usuários e Grupos.</span><span class="sxs-lookup"><span data-stu-id="89b9f-112">Click Users and Groups.</span></span>  
          <span data-ttu-id="89b9f-113">1. Selecione os Usuários ou Grupo que deseja acessar este relatório.</span><span class="sxs-lookup"><span data-stu-id="89b9f-113">1.    Select the User(s) or Group that would like to access this report.</span></span> 
          
<span data-ttu-id="89b9f-114">[![tela do usuário](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span><span class="sxs-lookup"><span data-stu-id="89b9f-114">[![user screen](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span></span>

<span data-ttu-id="89b9f-115">[![tela de segurança](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span><span class="sxs-lookup"><span data-stu-id="89b9f-115">[![security screen](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span></span>

  <span data-ttu-id="89b9f-116">b.</span><span class="sxs-lookup"><span data-stu-id="89b9f-116">b.</span></span>    <span data-ttu-id="89b9f-117">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="89b9f-117">Click **Save**.</span></span>
  
<span data-ttu-id="89b9f-118">[![botão salvar](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span><span class="sxs-lookup"><span data-stu-id="89b9f-118">[![save button](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span></span>

3.  <span data-ttu-id="89b9f-119">Na Definição de Relatório, adicione sua nova Definição em Árvore</span><span class="sxs-lookup"><span data-stu-id="89b9f-119">In your Report Definition add your new Tree Definition</span></span>

<span data-ttu-id="89b9f-120">[![formulário definição em árvore](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span><span class="sxs-lookup"><span data-stu-id="89b9f-120">[![tree definition form](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span></span>

<span data-ttu-id="89b9f-121">A.</span><span class="sxs-lookup"><span data-stu-id="89b9f-121">A.</span></span>  <span data-ttu-id="89b9f-122">Em Definição em Árvore, clique em Configuração e, em "Seleção da unidade organizacional", marque "Incluir todas as unidades"</span><span class="sxs-lookup"><span data-stu-id="89b9f-122">While in the Tree Definition click on Setting and under “Reporting unit selection” check “Include all units”</span></span>

<span data-ttu-id="89b9f-123">[![formulário de seleção da unidade organizacional](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span><span class="sxs-lookup"><span data-stu-id="89b9f-123">[![reporting unit selection form](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span></span>

<span data-ttu-id="89b9f-124">**Antes:** [![captura de tela do "antes"](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span><span class="sxs-lookup"><span data-stu-id="89b9f-124">**Before:** [![before screenshot](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span></span>

<span data-ttu-id="89b9f-125">**Depois:** [![captura de tela do "depois"](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span><span class="sxs-lookup"><span data-stu-id="89b9f-125">**After:** [![after screenshot](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span></span>

<span data-ttu-id="89b9f-126">Observação: o motivo para a mensagem acima é que meu usuário não tem acesso a este relatório depois da aplicação da Segurança da unidade</span><span class="sxs-lookup"><span data-stu-id="89b9f-126">Note: Reason for the above message is my user does not have access to that report after applying Unit Security</span></span>



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a><span data-ttu-id="89b9f-127">Como determino quais contas não correspondem aos meus saldos no D365?</span><span class="sxs-lookup"><span data-stu-id="89b9f-127">How do I determine which account(s) do not matching my balances in D365?</span></span>

<span data-ttu-id="89b9f-128">Veja aqui algumas etapas que podem ser executadas para identificar as contas e as variações quando você tem um relatório que não corresponde ao que esperava no D365.</span><span class="sxs-lookup"><span data-stu-id="89b9f-128">When you have a report that doesn't match what you would expect in D365, here are some steps you could take to identify those accounts and the variances.</span></span> 

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="89b9f-129">No Report Designer do relator financeiro</span><span class="sxs-lookup"><span data-stu-id="89b9f-129">In Financial Reporter Report Designer</span></span>

1.  <span data-ttu-id="89b9f-130">Crie uma Definição de Linha a.</span><span class="sxs-lookup"><span data-stu-id="89b9f-130">Create a new Row Definition a.</span></span>    <span data-ttu-id="89b9f-131">Clique em Editar | Inserir Linhas de Dimensões i.</span><span class="sxs-lookup"><span data-stu-id="89b9f-131">Click Edit | Insert Rows from Dimensions i.</span></span>  <span data-ttu-id="89b9f-132">Selecione MainAccount [![Selecionar conta principal_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span><span class="sxs-lookup"><span data-stu-id="89b9f-132">Select MainAccount [![Select Main screen_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span></span>
    
    <span data-ttu-id="89b9f-133">ii.</span><span class="sxs-lookup"><span data-stu-id="89b9f-133">ii.</span></span> <span data-ttu-id="89b9f-134">Clique em OK b.</span><span class="sxs-lookup"><span data-stu-id="89b9f-134">Click Ok b.</span></span>    <span data-ttu-id="89b9f-135">Salve a Definição de Linha</span><span class="sxs-lookup"><span data-stu-id="89b9f-135">Save the Row Definition</span></span>

2.  <span data-ttu-id="89b9f-136">Crie uma nova Definição de Coluna     [![Criar uma nova definição de coluna](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span><span class="sxs-lookup"><span data-stu-id="89b9f-136">Create a new Column Definition     [![Create a new column definition](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span></span>

3.  <span data-ttu-id="89b9f-137">Crie uma nova Definição de Relatório a.</span><span class="sxs-lookup"><span data-stu-id="89b9f-137">Create a new Report Definition a.</span></span>    <span data-ttu-id="89b9f-138">Clique em Configurações e desmarque o [![formulário Configurações](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span><span class="sxs-lookup"><span data-stu-id="89b9f-138">Click Settings and uncheck [![Settings form](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span></span>
   
4.  <span data-ttu-id="89b9f-139">Gere o relatório.</span><span class="sxs-lookup"><span data-stu-id="89b9f-139">Generate the Report.</span></span> 

5.  <span data-ttu-id="89b9f-140">Exporte o relatório para o Excel.</span><span class="sxs-lookup"><span data-stu-id="89b9f-140">Export the Report to Excel.</span></span>

### <a name="in-d365"></a><span data-ttu-id="89b9f-141">No D365:</span><span class="sxs-lookup"><span data-stu-id="89b9f-141">In D365:</span></span> 
1.  <span data-ttu-id="89b9f-142">Clique Contabilidade | Consultas e Relatórios | Balancete a.</span><span class="sxs-lookup"><span data-stu-id="89b9f-142">Click General Ledger | Inquiries and Reports | Trial Balance a.</span></span>    <span data-ttu-id="89b9f-143">Parâmetros i.</span><span class="sxs-lookup"><span data-stu-id="89b9f-143">Parameters i.</span></span>  <span data-ttu-id="89b9f-144">Data inicial: início do ano fiscal ii.</span><span class="sxs-lookup"><span data-stu-id="89b9f-144">From Date: Start of Fiscal Year ii.</span></span> <span data-ttu-id="89b9f-145">Data final: data para a qual o relatório foi gerado iii.</span><span class="sxs-lookup"><span data-stu-id="89b9f-145">To Date: Date you generated the report for iii.</span></span>    <span data-ttu-id="89b9f-146">Conjunto de dimensões financeiras "Conjunto de contas principais" [![formulário Conta Principal](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span><span class="sxs-lookup"><span data-stu-id="89b9f-146">Financial Dimension Set “Main Account set” [![Main Account Form](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span></span>
      
  <span data-ttu-id="89b9f-147">b.</span><span class="sxs-lookup"><span data-stu-id="89b9f-147">b.</span></span>    <span data-ttu-id="89b9f-148">Clique em Calcular</span><span class="sxs-lookup"><span data-stu-id="89b9f-148">Click Calculate</span></span>

2.  <span data-ttu-id="89b9f-149">Exporte o relatório para o Excel</span><span class="sxs-lookup"><span data-stu-id="89b9f-149">Export the report to Excel</span></span>

<span data-ttu-id="89b9f-150">Agora, você poderá copiar os dados do relatório do Excel de FR e para o relatório Balancete do D365 e comparar as colunas "Saldo de fechamento".</span><span class="sxs-lookup"><span data-stu-id="89b9f-150">You should now be able to copy the data from the FR Excel Report and to the D365 Trial Balance report and compare the “Closing Balance” columns.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]