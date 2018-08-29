---
title: Sincronize categorias de despesa do projeto entre o Finance and Operations e o Project Service Automation
description: "Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar categorias de despesa do projeto entre o Microsoft Dynamics 365 for Finance and Operations e o Microsoft Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="05859-103">Sincronize categorias de despesa do projeto entre o Finance and Operations e o Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="05859-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="05859-104">Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar categorias de despesa do projeto entre o Microsoft Dynamics 365 for Finance and Operations e o Microsoft Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="05859-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="05859-105">A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Microsoft Dynamics 365 for Finance and Operations versão 8.0.</span><span class="sxs-lookup"><span data-stu-id="05859-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in Microsoft Dynamics 365 for Finance and Operations version 8.0.</span></span>
> - <span data-ttu-id="05859-106">A integração de valores reais está disponível no Microsoft Dynamics 365 for Finance and Operations versão 8.0.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="05859-106">Actuals integration is available in Microsoft Dynamics 365 for Finance and Operations version 8.0.1 or later.</span></span>
> - <span data-ttu-id="05859-107">Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e números reais e para configurar o bloqueio de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="05859-107">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="05859-108">Se você precisar redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="05859-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="05859-109">Fluxo de dados para o Project Service Automation e o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="05859-109">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="05859-110">A solução de integração do Project Service Automation e do Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="05859-110">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="05859-111">Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre categorias de transações de despesa do projeto entre o Finance and Operations e o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="05859-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="05859-112">Se as categorias de despesa do projeto forem dominadas no Finance and Operations, o fluxo de integração será primeiro do Finance and Operations para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="05859-112">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation.</span></span> <span data-ttu-id="05859-113">As IDs de integração das categorias de despesas do projeto são atualizados por meio da sincronização do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="05859-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="05859-114">Se as categorias de despesa do projeto forem dominadas no Project Service Automation, o fluxo de integração será primeiro do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="05859-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="05859-115">As categorias do projeto já devem estar configuradas no Finance and Operations antes da sincronização para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="05859-115">The project categories must already be configured in Finance and Operations before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="05859-116">Sincronize do Project Service Automation para o Project Service Automation e, depois, novamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="05859-116">Then synchronize from Finance and Operations back to Project Service Automation, and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="05859-117">Dessa forma, você ajuda a garantir que as categorias estejam vinculadas e que nenhuma duplicata seja criada.</span><span class="sxs-lookup"><span data-stu-id="05859-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="05859-118">Geralmente, as categorias de despesa do projeto são dominadas no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="05859-118">Typically, the project expense categories are mastered in Finance and Operations.</span></span> <span data-ttu-id="05859-119">Entretanto, se elas não forem dominadas no Finance and Operations ou se já tiverem sido criadas no Project Service Automation, você deverá primeiro sincronizar por meio do modelo de categorias de transação de despesas do projeto (do PSA para o Fin and Ops).</span><span class="sxs-lookup"><span data-stu-id="05859-119">However, if they aren't mastered in Finance and Operations, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="05859-120">Depois sincronize usando o modelo de categorias de transação de despesas do projeto (do Fin and Ops para o PSA).</span><span class="sxs-lookup"><span data-stu-id="05859-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="05859-121">Você deverá executar a sincronização do Project Service Automation para o Finance and Operations mais uma vez.</span><span class="sxs-lookup"><span data-stu-id="05859-121">You should then run the synchronization from Project Service Automation to Finance and Operations one more time.</span></span>
>
> <span data-ttu-id="05859-122">Se sincronizar primeiro a partir do Project Service Automation, os seguintes requisitos devem ser atendidos no Finance and Operations antes que a sincronização seja executada:</span><span class="sxs-lookup"><span data-stu-id="05859-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance and Operations before the synchronization is run:</span></span>
>
> - <span data-ttu-id="05859-123">A categoria compartilhada que corresponde à categoria do projeto configurada no Project Service Automation deve existir e estar habilitada para **Projeto** e **Despesa**.</span><span class="sxs-lookup"><span data-stu-id="05859-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="05859-124">Para cada entidade legal do Finance and Operations que deve ser integrada, as seguintes categorias de projeto devem existir:</span><span class="sxs-lookup"><span data-stu-id="05859-124">For each Finance and Operations legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="05859-125">A **Categoria do projeto** existe.</span><span class="sxs-lookup"><span data-stu-id="05859-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="05859-126">A opção **Usar em Despesa** está habilitada.</span><span class="sxs-lookup"><span data-stu-id="05859-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="05859-127">A opção **Ativo em diários** está habilitada.</span><span class="sxs-lookup"><span data-stu-id="05859-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="05859-128">O **Tipo de transação** é definido como **Despesa**.</span><span class="sxs-lookup"><span data-stu-id="05859-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="05859-129">A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="05859-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="05859-130">[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="05859-130">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a><span data-ttu-id="05859-131">A sincronização da categoria de despesas do projeto, do Finance and Operations para o Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="05859-131">Project expense category synchronization from Finance and Operations to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="05859-132">Modelo e tarefa</span><span class="sxs-lookup"><span data-stu-id="05859-132">Template and task</span></span>

<span data-ttu-id="05859-133">Para acessar o modelo, no centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="05859-133">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="05859-134">O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Finance and Operations para o Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="05859-134">The following template and underlying task are used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

- <span data-ttu-id="05859-135">**Nome do modelo na Integração de dados:** categorias de transação de despesa do projeto (do Fin and Ops para o PSA)</span><span class="sxs-lookup"><span data-stu-id="05859-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="05859-136">**Nome da tarefa no projeto:** categorias de sincronização para o PSA</span><span class="sxs-lookup"><span data-stu-id="05859-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="05859-137">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="05859-137">Entity set</span></span>

| <span data-ttu-id="05859-138">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="05859-138">Finance and Operations</span></span>            | <span data-ttu-id="05859-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="05859-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="05859-140">Entidade de integração para categorias</span><span class="sxs-lookup"><span data-stu-id="05859-140">Integration entity for categories</span></span> | <span data-ttu-id="05859-141">Categorias de transação</span><span class="sxs-lookup"><span data-stu-id="05859-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="05859-142">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="05859-142">Entity flow</span></span>

<span data-ttu-id="05859-143">As categorias de despesa do projeto são gerenciadas no Finance and Operations e são sincronizadas para o Project Service Automation como categorias de transações.</span><span class="sxs-lookup"><span data-stu-id="05859-143">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="05859-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="05859-144">Power Query</span></span>

<span data-ttu-id="05859-145">Ao sincronizar com o Project Service Automation, você deve usar o Microsoft Power Query para Excel para definir o tipo de cobrança na categoria de transação.</span><span class="sxs-lookup"><span data-stu-id="05859-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="05859-146">O modelo de categorias de transação de despesa do projeto (do Fin and Ops para o PSA) fornece uma coluna padrão e o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="05859-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="05859-147">Se você criar seu próprio modelo, deverá adicionar uma coluna condicional no Power Query.</span><span class="sxs-lookup"><span data-stu-id="05859-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="05859-148">Execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="05859-148">Follow these steps.</span></span>

1. <span data-ttu-id="05859-149">Clique na seta para abrir o mapeamento da tarefa de categorias de despesas do projeto no modelo de categorias de transação de despesas do projeto (do Fin and Ops para o PSA).</span><span class="sxs-lookup"><span data-stu-id="05859-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="05859-150">Clique no link **Filtragem e consulta avançada** para abrir o Power Query.</span><span class="sxs-lookup"><span data-stu-id="05859-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="05859-151">Selecione **Adicionar coluna condicional**.</span><span class="sxs-lookup"><span data-stu-id="05859-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="05859-152">Insira um nome para a nova coluna, como **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="05859-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="05859-153">Insira a seguinte condição: **se CATEGORYID não for igual a nulo, ele será 19235001; caso contrário, ele será nulo**.</span><span class="sxs-lookup"><span data-stu-id="05859-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="05859-154">Clique em **OK** na coluna.</span><span class="sxs-lookup"><span data-stu-id="05859-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="05859-155">Verifique se esta nova coluna está mapeada na página de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="05859-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="05859-156">A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="05859-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="05859-157">O mapeamento mostra as informações de campo que serão sincronizadas do Finance and Operations para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="05859-157">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="05859-158">[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="05859-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="05859-159">A sincronização da categoria de despesas do projeto, do Project Service Automation para o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="05859-159">Project expense category synchronization from Project Service Automation to Finance and Operations</span></span>

### <a name="template-and-task"></a><span data-ttu-id="05859-160">Modelo e tarefa</span><span class="sxs-lookup"><span data-stu-id="05859-160">Template and task</span></span>

<span data-ttu-id="05859-161">O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Project Service Automation para o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="05859-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

- <span data-ttu-id="05859-162">**Nome do modelo na Integração de dados:** categorias de transação de despesa do projeto (do PSA para o Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="05859-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="05859-163">**Nome da tarefa no projeto:** categorias de sincronização para o Fin and Ops</span><span class="sxs-lookup"><span data-stu-id="05859-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="05859-164">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="05859-164">Entity set</span></span>

| <span data-ttu-id="05859-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="05859-165">Project Service Automation</span></span> | <span data-ttu-id="05859-166">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="05859-166">Finance and Operations</span></span>            |
|----------------------------|-----------------------------------|
| <span data-ttu-id="05859-167">Categorias de transação</span><span class="sxs-lookup"><span data-stu-id="05859-167">Transaction categories</span></span>     | <span data-ttu-id="05859-168">Entidade de integração para categorias</span><span class="sxs-lookup"><span data-stu-id="05859-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="05859-169">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="05859-169">Entity flow</span></span>

<span data-ttu-id="05859-170">As categorias de despesa do projeto são gerenciadas no Finance and Operations e são sincronizadas para o Project Service Automation como categorias de transações.</span><span class="sxs-lookup"><span data-stu-id="05859-170">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="05859-171">A nova sincronização para o Finance and Operations atualiza a categoria de projeto do Finance and Operations com a ID de integração do Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="05859-171">The synchronization back to Finance and Operations updates the project category in Finance and Operations with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="05859-172">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="05859-172">Template mapping in Data integration</span></span>

<span data-ttu-id="05859-173">A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="05859-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="05859-174">O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="05859-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="05859-175">[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="05859-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

