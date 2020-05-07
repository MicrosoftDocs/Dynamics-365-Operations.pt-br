---
title: Criar contratos avançados para cobrança com base no progresso
description: Este tópico explica como criar contratos de projeto para que você possa gerar notas fiscais para clientes com base em uma porcentagem de trabalho concluído.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282811"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a><span data-ttu-id="e7f04-103">Criar contratos avançados para cobrança com base no progresso</span><span class="sxs-lookup"><span data-stu-id="e7f04-103">Create advanced contracts for billing based on progress</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7f04-104">Este tópico explica como criar contratos de projeto para que você possa criar notas fiscais para clientes com base em uma porcentagem de trabalho concluído.</span><span class="sxs-lookup"><span data-stu-id="e7f04-104">This topic explains how to create project contracts so that you can create invoices for customers, based on a percentage of completed work.</span></span> <span data-ttu-id="e7f04-105">Os valores de fatura são calculados automaticamente para as categorias de orçamento do trabalho que você configurou para um projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-105">Invoice amounts are automatically calculated for the budget categories of work that you set up for a project.</span></span> <span data-ttu-id="e7f04-106">A hora da fatura é configurada quando você negocia o contrato do projeto com o cliente.</span><span class="sxs-lookup"><span data-stu-id="e7f04-106">The invoice timing is set when you negotiate the project contract with the customer.</span></span>

<span data-ttu-id="e7f04-107">Use os procedimentos neste tópico para configurar um contrato, um projeto associado e as regras de cobrança que calculam os valores da fatura para as categorias de orçamento do trabalho configuradas para o projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-107">Use the procedures in this topic to set up a contract, an associated project, and the billing rules that calculate invoice amounts for the budget categories of work that you set up for the project.</span></span>

<span data-ttu-id="e7f04-108">Após criar o contrato e o projeto, você poderá configurar os detalhes do projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-108">After you've created the contract and the project, you can set up the details of the project.</span></span> <span data-ttu-id="e7f04-109">Por exemplo, você pode definir as atividades e atribuir trabalhadores ao projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-109">For example, you can define activities and assign workers to the project.</span></span>

## <a name="example"></a><span data-ttu-id="e7f04-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e7f04-110">Example</span></span>

<span data-ttu-id="e7f04-111">Sua organização é uma empresa de desenvolvimento de software.</span><span class="sxs-lookup"><span data-stu-id="e7f04-111">Your organization is a software development firm.</span></span> <span data-ttu-id="e7f04-112">Você concorda em desenvolver um pacote de contabilidade de folha de pagamento para um cliente por uma tarifa total de US$ 20.000.</span><span class="sxs-lookup"><span data-stu-id="e7f04-112">You agree to develop a payroll accounting package for a customer for a total fee of 20,000 US dollars (USD).</span></span> <span data-ttu-id="e7f04-113">A organização concorda em enviar uma fatura para o cliente ao concluir porcentagens específicas do projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-113">Your organization agrees to invoice the customer as you complete specific percentages of the project.</span></span> <span data-ttu-id="e7f04-114">Configure as seguintes categorias de projeto para o trabalho, de forma que possa usá-las no processo de cobrança:</span><span class="sxs-lookup"><span data-stu-id="e7f04-114">You set up the following project categories for the work, so that you can use them in the billing process:</span></span>

- <span data-ttu-id="e7f04-115">Consultoria</span><span class="sxs-lookup"><span data-stu-id="e7f04-115">Consulting</span></span>
- <span data-ttu-id="e7f04-116">Design</span><span class="sxs-lookup"><span data-stu-id="e7f04-116">Design</span></span>
- <span data-ttu-id="e7f04-117">Instalação</span><span class="sxs-lookup"><span data-stu-id="e7f04-117">Installation</span></span>

<span data-ttu-id="e7f04-118">Você também configura regras de cobrança que calculam automaticamente os valores da fatura pelo percentual de trabalho do projeto que é concluído em cada categoria.</span><span class="sxs-lookup"><span data-stu-id="e7f04-118">You also set up billing rules that automatically calculate the invoice amounts for the percentage of project work that is completed in each category.</span></span>

<span data-ttu-id="e7f04-119">O gerente de orçamento cria um orçamento para as categorias de projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-119">The budget manager creates a budget for the project categories.</span></span> <span data-ttu-id="e7f04-120">O valor do trabalho de concluído é calculado automaticamente como uma porcentagem de trabalho real comparado com os valores orçados.</span><span class="sxs-lookup"><span data-stu-id="e7f04-120">The amount of completed work is automatically calculated as a percentage of actual work in comparison to the budgeted amounts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7f04-121">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e7f04-121">Prerequisites</span></span>

<span data-ttu-id="e7f04-122">Antes de criar um projeto que use regras de cobrança, você deve configurar as sequências numéricas para regras de cobrança e um diário de taxas usado para lançar cobranças de andamento.</span><span class="sxs-lookup"><span data-stu-id="e7f04-122">Before you create a project that uses billing rules, you must set up the number sequences for billing rules and a fee journal that is used to post progress billings.</span></span>

1. <span data-ttu-id="e7f04-123">Vá para **Gerenciamento e contabilidade de projeto** \> **Configuração** \> **Parâmetros de gerenciamento e contabilidade de projetos**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-123">Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>
2. <span data-ttu-id="e7f04-124">Na página **Parâmetros de gerenciamento e contabilidade de projetos**, na guia **Sequências numéricas**, configure a sequência numérica que você deseja usar ao criar regras de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e7f04-124">On the **Project management and accounting parameters** page, on the **Number sequences** tab, set up the number sequence that you want to use when billing rules are created.</span></span>
3. <span data-ttu-id="e7f04-125">Vá para **Gerenciamento e contabilidade de projetos** \> **Diários** \> **Taxa**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-125">Go to **Project management and accounting** \> **Journals** \> **Fee**.</span></span>
4. <span data-ttu-id="e7f04-126">Na página **Diário de taxas**, selecione **Novo** e insira o nome do diário.</span><span class="sxs-lookup"><span data-stu-id="e7f04-126">On the **Fee journal** page, select **New**, and enter the journal name.</span></span>

## <a name="create-a-contract-for-progress-billings"></a><span data-ttu-id="e7f04-127">Criar um contrato de cobrança parciais</span><span class="sxs-lookup"><span data-stu-id="e7f04-127">Create a contract for progress billings</span></span>

<span data-ttu-id="e7f04-128">Use este procedimento para criar um contrato de projeto para um projeto de preço fixo.</span><span class="sxs-lookup"><span data-stu-id="e7f04-128">Use this procedure to create a project contract for a fixed-price project.</span></span> <span data-ttu-id="e7f04-129">Você cria uma fatura do projeto quando o trabalho concluído no projeto atinge uma porcentagem específica.</span><span class="sxs-lookup"><span data-stu-id="e7f04-129">You create a project invoice when the work that is completed on the project reaches a specified percentage.</span></span>

1. <span data-ttu-id="e7f04-130">Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Contratos do projeto**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-130">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="e7f04-131">Na página **Contratos do projeto**, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-131">On the **Project contracts** page, select **New**.</span></span>
3. <span data-ttu-id="e7f04-132">Na caixa de diálogo **Novo contrato de projeto**, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="e7f04-132">In the **New project contract** dialog box, set the following fields:</span></span>

    - <span data-ttu-id="e7f04-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e7f04-133">**Name**</span></span>
    - <span data-ttu-id="e7f04-134">**Tipo de financiamento**</span><span class="sxs-lookup"><span data-stu-id="e7f04-134">**Funding type**</span></span>
    - <span data-ttu-id="e7f04-135">**Fonte de financiamento**</span><span class="sxs-lookup"><span data-stu-id="e7f04-135">**Funding source**</span></span>
    - <span data-ttu-id="e7f04-136">**Moeda de venda** – Por padrão, essa moeda é usada para todas as faturas de cliente associadas ao contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-136">**Sales currency** – By default, this currency is used for customer invoices that are associated with the project contract.</span></span> <span data-ttu-id="e7f04-137">No entanto, é possível modificar a moeda de venda para uma fatura de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="e7f04-137">However, you can change the sales currency on a specific customer invoice.</span></span>

4. <span data-ttu-id="e7f04-138">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-138">Select **OK**.</span></span> <span data-ttu-id="e7f04-139">As informações são copiadas para o cabeçalho da página **Contratos do projeto**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-139">The information is copied to the header of the **Project contracts** page.</span></span>
5. <span data-ttu-id="e7f04-140">Na página **Contratos do projeto**, preencha o restante das informações necessárias para o projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-140">On the **Project contracts** page, fill in the rest of the required information for the project.</span></span>

## <a name="create-a-project-for-progress-billings"></a><span data-ttu-id="e7f04-141">Criar um projeto para cobrança parciais</span><span class="sxs-lookup"><span data-stu-id="e7f04-141">Create a project for progress billings</span></span>

<span data-ttu-id="e7f04-142">Siga estas etapas para criar um projeto e quaisquer subprojetos associados a um contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-142">Follow these steps to create a project and any subprojects that are associated with a project contract.</span></span>

1. <span data-ttu-id="e7f04-143">Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-143">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="e7f04-144">Na página **Todos os projetos** , selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-144">On the **All projects** page, select **New**.</span></span>
3. <span data-ttu-id="e7f04-145">Na caixa de diálogo **Novo projeto**, no campo **Tipo de projeto**, selecione **Hora e material**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-145">In the **New project** dialog box, in the **Project type** field, select **Time and material**.</span></span>
4. <span data-ttu-id="e7f04-146">Selecione um grupo de projetos.</span><span class="sxs-lookup"><span data-stu-id="e7f04-146">Select a project group.</span></span> <span data-ttu-id="e7f04-147">Um grupo de projetos define as informações de lançamento para os projetos atribuídos ao grupo.</span><span class="sxs-lookup"><span data-stu-id="e7f04-147">A project group defines the posting information for the projects that are assigned to the group.</span></span>
5. <span data-ttu-id="e7f04-148">Selecione **Criar projeto**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-148">Select **Create project**.</span></span>
6. <span data-ttu-id="e7f04-149">Depois de criar o projeto, defina a fase do projeto para **Em andamento**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-149">After the project is created, set the project stage to **In process**.</span></span>

## <a name="create-a-budget-for-a-project"></a><span data-ttu-id="e7f04-150">Crie um orçamento para um projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-150">Create a budget for a project</span></span>

<span data-ttu-id="e7f04-151">As categorias de orçamento são usadas para calcular automaticamente os valores para faturar pelo percentual de trabalho que foi concluído para cada categoria.</span><span class="sxs-lookup"><span data-stu-id="e7f04-151">Budget categories are used to automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="e7f04-152">Siga estas etapas para criar categorias de orçamento para os custos previstos.</span><span class="sxs-lookup"><span data-stu-id="e7f04-152">Follow these steps to create budget categories for the estimated costs.</span></span>

1. <span data-ttu-id="e7f04-153">Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-153">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="e7f04-154">Na página **Todos os projetos**, selecione e abra o projeto desejado.</span><span class="sxs-lookup"><span data-stu-id="e7f04-154">On the **All projects** page, select and open the project that you want.</span></span>
3. <span data-ttu-id="e7f04-155">Na página **Projetos**, no Painel de Ações, na guia **Plano**, no grupo **Orçamento**, selecione **Orçamento do projeto**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-155">On the **Projects** page, on the Action Pane, on the **Plan** tab, in the **Budget** group, select **Project budget**.</span></span>
4. <span data-ttu-id="e7f04-156">Na página **Orçamento do projeto**, insira um custo estimado para cada categoria no projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-156">On the **Project budget** page, enter an estimated cost for each category in the project.</span></span>

## <a name="create-billing-rules-for-progress-billings"></a><span data-ttu-id="e7f04-157">Criar regras de cobrança para cobrança parciais</span><span class="sxs-lookup"><span data-stu-id="e7f04-157">Create billing rules for progress billings</span></span>

1. <span data-ttu-id="e7f04-158">Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Contratos do projeto**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-158">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="e7f04-159">Na página **Contratos do projeto**, selecione e abra um contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-159">On the **Project contracts** page, select and open a project contract.</span></span>
3. <span data-ttu-id="e7f04-160">Na página contrato de projeto, na Guia Rápida **Regras de cobrança**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-160">On the project contract page, on the **Billing rules** FastTab, select **Add**.</span></span>
4. <span data-ttu-id="e7f04-161">Na página **Regra de cobrança**, no campo **Tipo de linha**, selecione **Em andamento**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-161">On the **Billing rule** page, in the **Line type** field, select **Progress**.</span></span>
5. <span data-ttu-id="e7f04-162">Na Guia Rápida **Detalhes da linha de regra de cobrança**, no campo **Valor de contrato**, insira o valor total do contrato.</span><span class="sxs-lookup"><span data-stu-id="e7f04-162">On the **Billing rule line details** FastTab, in the **Contract value** field, enter the total value of the contract.</span></span>
6. <span data-ttu-id="e7f04-163">No campo **Categoria**, selecione a categoria na qual lançar a transação de taxa.</span><span class="sxs-lookup"><span data-stu-id="e7f04-163">In the **Category** field, select the category to post the fee transaction to.</span></span>
7. <span data-ttu-id="e7f04-164">No campo **Projeto**, selecione o projeto que usa essa regra de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e7f04-164">In the **Project** field, select the project that uses this billing rule.</span></span>
8. <span data-ttu-id="e7f04-165">Opcional: Atribuir a regra de cobrança a projetos adicionais.</span><span class="sxs-lookup"><span data-stu-id="e7f04-165">Optional: Assign the billing rule to additional projects.</span></span> <span data-ttu-id="e7f04-166">Na Guia Rápida **Projeto**, na seção **Projetos disponíveis**, selecione um projeto e, em seguida, selecione o botão de seta para a direita para adicionar o projeto à seção **Projetos selecionados**.</span><span class="sxs-lookup"><span data-stu-id="e7f04-166">On the **Project** FastTab, in the **Available projects** section, select a project, and then select the right arrow button to add the project to the **Selected projects** section.</span></span>
9. <span data-ttu-id="e7f04-167">Opcional: Calcular a o valor da porcentagem que o cliente retém dos pagamentos em uma fatura.</span><span class="sxs-lookup"><span data-stu-id="e7f04-167">Optional: Calculate the percentage amount that the customer withholds from payments on an invoice.</span></span> <span data-ttu-id="e7f04-168">Na Guia Rápida **Termos de retenção de pagamento**, selecione a fonte de financiamento e, em seguida, no campo **Porcentagem de retenção**, insira a porcentagem de retenção.</span><span class="sxs-lookup"><span data-stu-id="e7f04-168">On the **Payment retention terms** FastTab, select the funding source, and then, in the **Retention percentage** field, enter the retention percentage.</span></span>
10. <span data-ttu-id="e7f04-169">Repita essas etapas para criar regras adicionais de cobrança para o contrato de projeto.</span><span class="sxs-lookup"><span data-stu-id="e7f04-169">Repeat these steps to create additional billing rules for the project contract.</span></span>
