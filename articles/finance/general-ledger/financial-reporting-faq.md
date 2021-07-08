---
title: Perguntas frequentes sobre relatórios financeiros
description: Este tópico fornece respostas a algumas perguntas frequentes sobre relatórios financeiros.
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
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266624"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="93f78-103">Perguntas frequentes sobre relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="93f78-103">Financial reporting FAQ</span></span>

<span data-ttu-id="93f78-104">Este tópico fornece respostas a perguntas frequentes sobre relatórios financeiros.</span><span class="sxs-lookup"><span data-stu-id="93f78-104">This topic provides answers to frequently asked questions about Financial reporting.</span></span>

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a><span data-ttu-id="93f78-105">Como posso restringir o acesso a um relatório usando a segurança em árvore?</span><span class="sxs-lookup"><span data-stu-id="93f78-105">How do I restrict access to a report by using tree security?</span></span>

<span data-ttu-id="93f78-106">O exemplo a seguir mostra como restringir o acesso a um relatório usando a segurança em árvore.</span><span class="sxs-lookup"><span data-stu-id="93f78-106">The following example shows how to restrict access to a report by using tree security.</span></span>

<span data-ttu-id="93f78-107">A empresa de demonstração USMF tem um relatório de **Balanço** ao qual nem todos os usuários do relatório financeiro devem ter acesso.</span><span class="sxs-lookup"><span data-stu-id="93f78-107">The USMF demo company has a **Balance sheet** report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="93f78-108">Você pode usar a segurança em árvore para restringir o acesso a um único relatório, de modo que somente usuários específicos possam acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="93f78-108">You can use tree security to restrict access to a single report so that only specific users can access it.</span></span>

1. <span data-ttu-id="93f78-109">Entre no Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="93f78-109">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="93f78-110">Selecione **Arquivo \> Novo \> Definição em árvore** para criar uma definição em árvore.</span><span class="sxs-lookup"><span data-stu-id="93f78-110">Select **File \> New \> Tree Definition** to create a new tree definition.</span></span>
3. <span data-ttu-id="93f78-111">Toque (ou clique) duas vezes na linha **Resumo** na coluna **Segurança da unidade**.</span><span class="sxs-lookup"><span data-stu-id="93f78-111">Double-tap (or double-click) the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="93f78-112">Selecione **Usuários e Grupos**.</span><span class="sxs-lookup"><span data-stu-id="93f78-112">Select **Users and Groups**.</span></span>
5. <span data-ttu-id="93f78-113">Selecione os usuários ou os grupos que precisam acessar o relatório.</span><span class="sxs-lookup"><span data-stu-id="93f78-113">Select the users or groups that require access to the report.</span></span>
6. <span data-ttu-id="93f78-114">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="93f78-114">Select **Save**.</span></span>
7. <span data-ttu-id="93f78-115">Na definição de relatório, adicione sua nova definição em árvore.</span><span class="sxs-lookup"><span data-stu-id="93f78-115">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="93f78-116">Na definição em árvore, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="93f78-116">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="93f78-117">Em **Seleção de unidade organizacional**, selecione **Incluir todas as unidades**.</span><span class="sxs-lookup"><span data-stu-id="93f78-117">Then, under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a><span data-ttu-id="93f78-118">Como posso identificar quais contas não correspondem aos meus saldos?</span><span class="sxs-lookup"><span data-stu-id="93f78-118">How do I identify which accounts don't match my balances?</span></span>

<span data-ttu-id="93f78-119">Se você tiver um relatório que não tem saldos correspondentes, use os procedimentos a seguir para identificar cada conta e variação.</span><span class="sxs-lookup"><span data-stu-id="93f78-119">If you have a report that doesn't have matching balances, use the following procedures to identify each account and variance.</span></span>

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="93f78-120">No Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="93f78-120">In Financial Reporter Report Designer</span></span>

1. <span data-ttu-id="93f78-121">Crie uma definição de linha.</span><span class="sxs-lookup"><span data-stu-id="93f78-121">Create a new row definition.</span></span>
2. <span data-ttu-id="93f78-122">Selecione **Editar \> Inserir Linhas de Dimensões**.</span><span class="sxs-lookup"><span data-stu-id="93f78-122">Select **Edit \> Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="93f78-123">Selecione **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="93f78-123">Select **MainAccount**.</span></span>
4. <span data-ttu-id="93f78-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="93f78-124">Select **OK**.</span></span>
5. <span data-ttu-id="93f78-125">Salve a definição de linha.</span><span class="sxs-lookup"><span data-stu-id="93f78-125">Save the row definition.</span></span>
6. <span data-ttu-id="93f78-126">Crie uma definição de coluna.</span><span class="sxs-lookup"><span data-stu-id="93f78-126">Create a new column definition.</span></span>
7. <span data-ttu-id="93f78-127">Crie uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="93f78-127">Create a new report definition.</span></span>
8. <span data-ttu-id="93f78-128">Selecione **Configurações** e desmarque esta opção.</span><span class="sxs-lookup"><span data-stu-id="93f78-128">Select **Settings** and unmark this option.</span></span>
9. <span data-ttu-id="93f78-129">Gere o relatório.</span><span class="sxs-lookup"><span data-stu-id="93f78-129">Generate the report.</span></span> 
10. <span data-ttu-id="93f78-130">Exporte o relatório para o Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="93f78-130">Export the report to Microsoft Excel.</span></span>

### <a name="in-dynamics-365-finance"></a><span data-ttu-id="93f78-131">No Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="93f78-131">In Dynamics 365 Finance</span></span>

1. <span data-ttu-id="93f78-132">Vá para **Contabilidade \> Consultas e Relatórios \> Balancete**.</span><span class="sxs-lookup"><span data-stu-id="93f78-132">Go to **General ledger \> Inquiries and reports \> Trial balance**.</span></span>
2. <span data-ttu-id="93f78-133">Defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="93f78-133">Set the following fields:</span></span>

    - <span data-ttu-id="93f78-134">**Data de Início** – insira a data de início do ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="93f78-134">**From Date** – Enter the start date of the fiscal year.</span></span>
    - <span data-ttu-id="93f78-135">**Data de Término** – insira a data para a qual você está gerando o relatório.</span><span class="sxs-lookup"><span data-stu-id="93f78-135">**To Date** – Enter the date that you're generating the report for.</span></span>
    - <span data-ttu-id="93f78-136">**Dimensão Financeira** – defina este campo como **Conta principal definida**.</span><span class="sxs-lookup"><span data-stu-id="93f78-136">**Financial Dimension** – Set this field to **Main Account set**.</span></span>

3. <span data-ttu-id="93f78-137">Selecione **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="93f78-137">Select **Calculate**.</span></span>
4. <span data-ttu-id="93f78-138">Exporte o relatório para o Excel.</span><span class="sxs-lookup"><span data-stu-id="93f78-138">Export the report to Excel.</span></span>

<span data-ttu-id="93f78-139">Agora, você poderá copiar os dados do relatório do Excel do Financial Reporter para o relatório de **Balancete** a fim de comparar as colunas **Saldo de fechamento**.</span><span class="sxs-lookup"><span data-stu-id="93f78-139">You should now be able to copy the data from the Financial Reporter Excel report to the **Trial Balance** report, so that you can compare the **Closing Balance** columns.</span></span>

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a><span data-ttu-id="93f78-140">Ao criar um relatório no Report Designer ou gerar um relatório financeiro, recebo a seguinte mensagem: "Não foi possível concluir a operação devido a um problema na estrutura do provedor de dados".</span><span class="sxs-lookup"><span data-stu-id="93f78-140">When I design a report in Report Designer, or when I generate a financial report, I received the following message: "The operation could not be completed due to a problem in the data provider framework."</span></span> <span data-ttu-id="93f78-141">Como devo responder?</span><span class="sxs-lookup"><span data-stu-id="93f78-141">How should I respond?</span></span>

<span data-ttu-id="93f78-142">A mensagem indica que ocorreu um problema quando o sistema tentou recuperar metadados financeiros do data mart enquanto você estava usando relatórios financeiros.</span><span class="sxs-lookup"><span data-stu-id="93f78-142">The message indicates that an issue occurred when the system tried to retrieve financial metadata from the data mart while you were using Financial reporting.</span></span> <span data-ttu-id="93f78-143">Há duas maneiras de responder a esse problema:</span><span class="sxs-lookup"><span data-stu-id="93f78-143">There are two ways to respond to this issue:</span></span>

- <span data-ttu-id="93f78-144">Revise o status da integração dos dados em **Ferramentas \> Status da integração** no Report Designer.</span><span class="sxs-lookup"><span data-stu-id="93f78-144">Review the integration status of the data by going to **Tools \> Integration status** in Report Designer.</span></span> <span data-ttu-id="93f78-145">Se a integração estiver incompleta, aguarde sua conclusão.</span><span class="sxs-lookup"><span data-stu-id="93f78-145">If the integration is incomplete, wait for it to be completed.</span></span> <span data-ttu-id="93f78-146">Em seguida, repita o que você estava fazendo quando recebeu a mensagem.</span><span class="sxs-lookup"><span data-stu-id="93f78-146">Then retry what you were doing when you received the message.</span></span>
- <span data-ttu-id="93f78-147">Contate o suporte para identificar e solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="93f78-147">Contact Support to identify and work through the issue.</span></span> <span data-ttu-id="93f78-148">Pode haver dados inconsistentes no sistema.</span><span class="sxs-lookup"><span data-stu-id="93f78-148">There might be inconsistent data in the system.</span></span> <span data-ttu-id="93f78-149">Os engenheiros de suporte podem ajudar você a identificar esse problema no servidor e encontrar os dados específicos que podem exigir uma atualização.</span><span class="sxs-lookup"><span data-stu-id="93f78-149">Support engineers can help you identify that issue on the server and find the specific data that might require an update.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
