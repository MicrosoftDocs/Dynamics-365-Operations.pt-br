---
title: Como sincronizar categorias de despesa do projeto a partir do Project Service Automation
description: "Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar categorias de despesa do projeto entre o Microsoft Dynamics 365 for Finance and Operations e o Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: pt-br
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="93c92-103">Sincronize categorias de despesa do projeto entre o Finance and Operations e o Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="93c92-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

<span data-ttu-id="93c92-104">Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar categorias de despesa do projeto entre o Microsoft Dynamics 365 for Finance and Operations e o Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c92-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> <span data-ttu-id="93c92-105">A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Dynamics 365 for Finance and Operations versão 8.0.</span><span class="sxs-lookup"><span data-stu-id="93c92-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="93c92-106">Fluxo de dados para o Project Service Automation e o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="93c92-106">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="93c92-107">A solução de integração do Project Service Automation e do Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93c92-107">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="93c92-108">Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre categorias de transações de despesa do projeto entre o Finance and Operations e o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c92-108">The integration templates that are available with the Data integration feature enables the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="93c92-109">Se as categorias de despesa do projeto forem dominadas no Finance and Operations, o fluxo de integração será primeiro do Finance and Operations para o Project Service Automation. Depois, as IDs de integração de categorias de despesa do projeto serão atualizadas através da sincronização do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93c92-109">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation, and then updating the project expense categories integration IDs by synchronizing from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="93c92-110">Se as categorias de despesa do projeto forem dominadas no Project Service Automation, o fluxo de integração será primeiro do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93c92-110">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="93c92-111">As categorias do projeto já devem estar configuradas no Finance and Operations antes da sincronização para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c92-111">The project categories must already be configured in Finance and Operations prior to the synchronization from Project Service Automation.</span></span> <span data-ttu-id="93c92-112">Sincronize do Project Service Automation para o Project Service Automation e, depois, novamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93c92-112">Then synchronize from Finance and Operations back to Project Service Automation and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="93c92-113">Isso garante que as categorias sejam vinculadas e que duplicatas não sejam criados.</span><span class="sxs-lookup"><span data-stu-id="93c92-113">This ensures the categories are linked and duplicates are not created.</span></span>

> [!NOTE]
> <span data-ttu-id="93c92-114">Geralmente, as categorias de despesa do projeto serão dominadas no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93c92-114">Typically, the project expense categories will be mastered in Finance and Operations.</span></span> <span data-ttu-id="93c92-115">Se não for o seu caso ou se você já tiver categorias de despesa criadas no Project Service Automation, primeiro sincronize usando as categorias de transação de despesa do projeto (do PSA para o Fin and Ops) e, depois, sincronize usando categorias de transação de despesa do projeto (do Fin and Ops para o PSA).</span><span class="sxs-lookup"><span data-stu-id="93c92-115">If that is not your situation, or you already have expense categories created in Project Service Automation, you must first sync using the Project expense transaction categories (PSA to Fin and Ops) and then sync using Project expense transaction categories (Fin and Ops to PSA).</span></span> <span data-ttu-id="93c92-116">Você deve executar a sincronização do PSA para o Fin and Ops mais uma vez.</span><span class="sxs-lookup"><span data-stu-id="93c92-116">You should then run the sync from PSA to Fin and Ops one more time.</span></span>

> <span data-ttu-id="93c92-117">Se a sincronização for primeiro a partir do Project Service Automation, as categorias de projeto já deverão estar configuradas no Finance and Operations. As categorias de projeto que precisem ser sincronizadas com as categorias de transações do Project Service Automation deverão ser configuradas como **Ativo em diários**.</span><span class="sxs-lookup"><span data-stu-id="93c92-117">If synchronizing first from Project Service Automation, the project categories must already be set up in Finance and Operations and any project categories that need to be synched with the Project Service Automation transaction categories must be set up to be **Active in journals**.</span></span>

<span data-ttu-id="93c92-118">A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93c92-118">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="93c92-119">[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="93c92-119">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="93c92-120">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="93c92-120">Templates and tasks</span></span>

<span data-ttu-id="93c92-121">Para acessar os modelos disponíveis, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="93c92-121">To access available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="93c92-122">O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Finance and Operations para o Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="93c92-122">The following template and underlying task is used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

-  <span data-ttu-id="93c92-123">**Nome do modelo na Integração de dados:** categorias de transação de despesa do projeto (do Fin and Ops para o PSA)</span><span class="sxs-lookup"><span data-stu-id="93c92-123">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
-  <span data-ttu-id="93c92-124">**Nome da tarefa no projeto:** categorias de sincronização para o PSA</span><span class="sxs-lookup"><span data-stu-id="93c92-124">**Name of the task in the project:** Sync categories to PSA</span></span>

## <a name="entity-set"></a><span data-ttu-id="93c92-125">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="93c92-125">Entity set</span></span>

| <span data-ttu-id="93c92-126">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="93c92-126">Finance and Operations</span></span>               | <span data-ttu-id="93c92-127">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="93c92-127">Project Service Automation</span></span>    |
|--------------------------------------|-------------------------------|
| <span data-ttu-id="93c92-128">Entidade de integração para categorias</span><span class="sxs-lookup"><span data-stu-id="93c92-128">Integration entity for categories</span></span>    | <span data-ttu-id="93c92-129">Categorias de transação</span><span class="sxs-lookup"><span data-stu-id="93c92-129">Transaction categories</span></span>        |

## <a name="entity-flow"></a><span data-ttu-id="93c92-130">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="93c92-130">Entity flow</span></span>

<span data-ttu-id="93c92-131">As categorias de despesa do projeto são gerenciadas no Finance and Operations e são sincronizadas para o Project Service Automation como categorias de transações.</span><span class="sxs-lookup"><span data-stu-id="93c92-131">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="93c92-132">Power Query</span><span class="sxs-lookup"><span data-stu-id="93c92-132">Power Query</span></span>

<span data-ttu-id="93c92-133">Você deve usar o Microsoft Power Query para definir o tipo de cobrança na categoria de transação ao sincronizar para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c92-133">You must use Microsoft Power Query to set the billing type on the transaction category when synchronizing to Project Service Automation.</span></span> <span data-ttu-id="93c92-134">O modelo de categorias de transação de despesa do projeto (do Fin and Ops para o PSA) tem uma coluna padrão e o mapeamento já fornecido.</span><span class="sxs-lookup"><span data-stu-id="93c92-134">The Project expense transaction categories (Fin and Ops to PSA) template has a default column and mapping already provided.</span></span> <span data-ttu-id="93c92-135">Se você criar seu próprio modelo, deverá adicionar uma coluna condicional no Power Query.</span><span class="sxs-lookup"><span data-stu-id="93c92-135">If you create your own template, you must add a conditional column in Power Query.</span></span>
- <span data-ttu-id="93c92-136">Abra o formulário avançado de filtragem e consulta a partir do mapeamento da tarefa de categorias de despesa do projeto.</span><span class="sxs-lookup"><span data-stu-id="93c92-136">Open the Advance Query and Filtering form from within the mapping of project expense categories task.</span></span>
- <span data-ttu-id="93c92-137">Selecione **Adicionar coluna condicional**.</span><span class="sxs-lookup"><span data-stu-id="93c92-137">Select **Add Conditional Column**.</span></span>
- <span data-ttu-id="93c92-138">Atribua um nome à nova coluna, como BillingType.</span><span class="sxs-lookup"><span data-stu-id="93c92-138">Give the new column a name, such as BillingType.</span></span>
- <span data-ttu-id="93c92-139">Insira a seguinte condição: se **CATEGORYID não for igual a nulo, ele será 19235001; caso contrário, ele será nulo**.</span><span class="sxs-lookup"><span data-stu-id="93c92-139">Enter the following condition: if **CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
- <span data-ttu-id="93c92-140">Clique em **OK** na coluna.</span><span class="sxs-lookup"><span data-stu-id="93c92-140">Click **OK** on the column.</span></span>
- <span data-ttu-id="93c92-141">Verifique se esta nova coluna está mapeada na página de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="93c92-141">Be sure to map this new column in the mapping page.</span></span>

<span data-ttu-id="93c92-142">A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="93c92-142">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="93c92-143">O mapeamento mostra as informações de campo que serão sincronizadas do Finance and Operations para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="93c92-143">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="93c92-144">[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="93c92-144">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

<span data-ttu-id="93c92-145">O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Project Service Automation para o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="93c92-145">The following template and underlying task is used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="93c92-146">-**Nome do modelo na integração de dados:** categorias de transação de despesa do projeto (do PSA para o Fin and Ops) -**Nome da tarefa no projeto:** categorias de sincronização para o Fin and Ops</span><span class="sxs-lookup"><span data-stu-id="93c92-146">-**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops) -**Name of the task in the project:** Sync categories to Fin Ops</span></span>

## <a name="entity-set"></a><span data-ttu-id="93c92-147">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="93c92-147">Entity set</span></span>

| <span data-ttu-id="93c92-148">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="93c92-148">Project Service Automation</span></span>      | <span data-ttu-id="93c92-149">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="93c92-149">Finance and Operations</span></span>             |
|---------------------------------|------------------------------------|
| <span data-ttu-id="93c92-150">Categorias de transação</span><span class="sxs-lookup"><span data-stu-id="93c92-150">Transaction categories</span></span>          | <span data-ttu-id="93c92-151">Entidade de integração para categorias</span><span class="sxs-lookup"><span data-stu-id="93c92-151">Integration entity for categories</span></span>  | 

## <a name="entity-flow"></a><span data-ttu-id="93c92-152">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="93c92-152">Entity flow</span></span>

<span data-ttu-id="93c92-153">As categorias de despesa do projeto são gerenciadas no Finance and Operations e são sincronizadas para o Project Service Automation como categorias de transações.</span><span class="sxs-lookup"><span data-stu-id="93c92-153">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="93c92-154">A nova sincronização para o Finance and Operations atualiza a ID de integração do Project Service Automation na categoria de projeto do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93c92-154">The synchronization back to Finance and Operations updates the integration ID from Project Service Automation on the Finance and Operations project category.</span></span>

<span data-ttu-id="93c92-155">A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="93c92-155">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="93c92-156">O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="93c92-156">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="93c92-157">[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="93c92-157">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

