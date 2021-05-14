---
title: Perguntas frequentes sobre relatórios financeiros
description: Este tópico lista perguntas relacionadas a relatórios financeiros de outros usuários.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923016"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="3086a-103">Perguntas frequentes sobre relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="3086a-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="3086a-104">Este tópico fornece respostas a perguntas frequentes sobre relatórios financeiros.</span><span class="sxs-lookup"><span data-stu-id="3086a-104">This topic provides answers to frequently asked questions about financial reporting.</span></span> 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="3086a-105">Como posso restringir o acesso a um relatório usando a segurança em árvore?</span><span class="sxs-lookup"><span data-stu-id="3086a-105">How do I restrict access to a report using tree security?</span></span>

<span data-ttu-id="3086a-106">O exemplo a seguir mostra como restringir o acesso a um relatório usando a segurança em árvore.</span><span class="sxs-lookup"><span data-stu-id="3086a-106">The following example shows how to restrict access to a report using tree security.</span></span>

<span data-ttu-id="3086a-107">A empresa de demonstração USMF tem um relatório de balanço ao qual nem todos os usuários do relatório financeiro devem ter acesso.</span><span class="sxs-lookup"><span data-stu-id="3086a-107">The USMF demo company has a Balance sheet report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="3086a-108">Você pode usar a segurança em árvore para restringir o acesso a um único relatório. Assim, apenas determinados usuários podem acessar o relatório.</span><span class="sxs-lookup"><span data-stu-id="3086a-108">To restrict access, you can use tree security to restrict access to a single report so that only certain users can access the report.</span></span> <span data-ttu-id="3086a-109">Siga estas etapas para restringir o acesso:</span><span class="sxs-lookup"><span data-stu-id="3086a-109">Follow these steps to restrict access:</span></span> 

1. <span data-ttu-id="3086a-110">Entre no Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="3086a-110">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="3086a-111">Crie uma definição em árvore.</span><span class="sxs-lookup"><span data-stu-id="3086a-111">Create a new tree definition.</span></span> <span data-ttu-id="3086a-112">Vá para **Arquivo > Novo > Definição em Árvore**.</span><span class="sxs-lookup"><span data-stu-id="3086a-112">Go to **File > New > Tree Definition**.</span></span>
3. <span data-ttu-id="3086a-113">Clique duas vezes na linha **Resumo** na coluna **Segurança da unidade**.</span><span class="sxs-lookup"><span data-stu-id="3086a-113">Double-click the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="3086a-114">Selecione **Usuários e Grupos**.</span><span class="sxs-lookup"><span data-stu-id="3086a-114">Select **Users and Groups**.</span></span>  
5. <span data-ttu-id="3086a-115">Selecione os usuários ou os grupos que precisam acessar este relatório.</span><span class="sxs-lookup"><span data-stu-id="3086a-115">Select the users or groups that need access to this report.</span></span> 
6. <span data-ttu-id="3086a-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3086a-116">Select **Save**.</span></span>
7. <span data-ttu-id="3086a-117">Na definição de relatório, adicione sua nova definição em árvore.</span><span class="sxs-lookup"><span data-stu-id="3086a-117">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="3086a-118">Na definição em árvore, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="3086a-118">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="3086a-119">Em **Seleção de unidade organizacional**, selecione **Incluir todas as unidades**.</span><span class="sxs-lookup"><span data-stu-id="3086a-119">Under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a><span data-ttu-id="3086a-120">Como posso identificar quais contas não correspondem aos meus saldos?</span><span class="sxs-lookup"><span data-stu-id="3086a-120">How do I identify which accounts do not match my balances?</span></span>

<span data-ttu-id="3086a-121">Veja aqui algumas etapas que podem ser executadas para identificar as contas e as variações se você tiver um relatório que não possui saldos correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3086a-121">If you have a report that doesn't have matching balances, here are some steps you can take to identify each of the accounts and variances.</span></span> 

<span data-ttu-id="3086a-122">**Financial Reporter Report Designer**</span><span class="sxs-lookup"><span data-stu-id="3086a-122">**Financial Reporter Report Designer**</span></span>
1. <span data-ttu-id="3086a-123">No Financial Reporter Report Designer, crie uma definição de linha.</span><span class="sxs-lookup"><span data-stu-id="3086a-123">In Financial Reporter Report Designer, create a new row definition.</span></span> 
2. <span data-ttu-id="3086a-124">Selecione **Editar > Inserir Linhas de Dimensões**.</span><span class="sxs-lookup"><span data-stu-id="3086a-124">Select **Edit > Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="3086a-125">Selecione **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="3086a-125">Select **MainAccount**.</span></span>  
4. <span data-ttu-id="3086a-126">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3086a-126">Select **OK**.</span></span>
5. <span data-ttu-id="3086a-127">Salve a definição de linha.</span><span class="sxs-lookup"><span data-stu-id="3086a-127">Save the row definition.</span></span>
6. <span data-ttu-id="3086a-128">Crie uma definição de coluna</span><span class="sxs-lookup"><span data-stu-id="3086a-128">Create a new column definition</span></span>
7. <span data-ttu-id="3086a-129">Crie uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="3086a-129">Create a new report definition.</span></span>
8. <span data-ttu-id="3086a-130">Selecione **Configurações** e desmarque esta opção.</span><span class="sxs-lookup"><span data-stu-id="3086a-130">Select **Settings** and unmark this option.</span></span>  
9. <span data-ttu-id="3086a-131">Gere o relatório.</span><span class="sxs-lookup"><span data-stu-id="3086a-131">Generate the report.</span></span> 
10. <span data-ttu-id="3086a-132">Exporte o relatório para o Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="3086a-132">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="3086a-133">**Dynamics 365 Finance**</span><span class="sxs-lookup"><span data-stu-id="3086a-133">**Dynamics 365 Finance**</span></span> 
1. <span data-ttu-id="3086a-134">No Dynamics 365 Finance, vá para **Contabilidade > Consultas e Relatórios > Balancete**.</span><span class="sxs-lookup"><span data-stu-id="3086a-134">In Dynamics 365 Finance, go to **General Ledger > Inquiries and Reports > Trial Balance**.</span></span>
2. <span data-ttu-id="3086a-135">Defina os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="3086a-135">Set the following parameters:</span></span>
   - <span data-ttu-id="3086a-136">**Data de Início** – insira o início do ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="3086a-136">**From Date** - Enter the start of the fiscal year.</span></span>
   - <span data-ttu-id="3086a-137">**Data de Término** – insira a data para a qual você está gerando o relatório.</span><span class="sxs-lookup"><span data-stu-id="3086a-137">**To Date** - Enter the date you are generating the report for.</span></span>
   - <span data-ttu-id="3086a-138">**Dimensão Financeira** – defina este campo como **Conta principal definida**.</span><span class="sxs-lookup"><span data-stu-id="3086a-138">**Financial Dimension** - Set this field to **Main Account set**.</span></span>
 3. <span data-ttu-id="3086a-139">Selecione **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="3086a-139">Select **Calculate**.</span></span>
 4. <span data-ttu-id="3086a-140">Exporte o relatório para o Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="3086a-140">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="3086a-141">Agora, você poderá copiar os dados do relatório do Excel do Relator Financeiro para o relatório Balancete a fim de comparar as colunas **Saldo de fechamento**.</span><span class="sxs-lookup"><span data-stu-id="3086a-141">You should now be able to copy the data from the Financial Reporter Excel report to the Trial Balance report, so you can compare the **Closing Balance** columns.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]