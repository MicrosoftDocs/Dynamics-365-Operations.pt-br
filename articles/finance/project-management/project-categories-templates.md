---
title: Sincronize categorias de despesa do projeto entre o Finance and Operations e o Project Service Automation
description: Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar categorias de despesa do projeto entre o Microsoft Dynamics 365 Finance e o Dynamics 365 Project Service Automation.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 7b0b3721c3b0755218c834d2bf77ec976be3bdcc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770303"
---
# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="766ee-103">Sincronize categorias de despesa do projeto entre o Finance and Operations e o Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="766ee-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="766ee-104">Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar categorias de despesa do projeto entre o Dynamics 365 Finance e o Dynamics 365 Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="766ee-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Dynamics 365 Finance and Dynamics 365 Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="766ee-105">A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis na versão 8.0.</span><span class="sxs-lookup"><span data-stu-id="766ee-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="766ee-106">A integração de valores reais está disponível na versão 8.0.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="766ee-106">Actuals integration is available in version 8.0.1 or later.</span></span>
> - <span data-ttu-id="766ee-107">Se estiver usando o Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e valores reais. Também poderá usá-los para configurar o bloqueio de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="766ee-107">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="766ee-108">Se você precisar redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="766ee-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance"></a><span data-ttu-id="766ee-109">Fluxo de dados do Project Service Automation para o Finance</span><span class="sxs-lookup"><span data-stu-id="766ee-109">Data flow for Project Service Automation and Finance</span></span>

<span data-ttu-id="766ee-110">A solução de integração do Project Service Automation para o Finance utiliza o recurso Integração de Dados para sincronizar dados nas instâncias do Project Service Automation e do Finance.</span><span class="sxs-lookup"><span data-stu-id="766ee-110">The Project Service Automation and Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="766ee-111">Os modelos de integração disponíveis com o recurso Integração de Dados permitem o fluxo de dados sobre categorias de transações de despesa do projeto entre o Finance e o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="766ee-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Project Service Automation.</span></span>

<span data-ttu-id="766ee-112">Se as categorias de despesa do projeto forem dominadas no Finance, o fluxo de integração será primeiro do Finance para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="766ee-112">If the project expense categories are mastered in Finance, the integration flow is first from Finance to Project Service Automation.</span></span> <span data-ttu-id="766ee-113">As IDs de integração das categorias de despesas do projeto são atualizadas por meio da sincronização do Project Service Automation com o Finance.</span><span class="sxs-lookup"><span data-stu-id="766ee-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance.</span></span>

<span data-ttu-id="766ee-114">Se as categorias de despesa do projeto forem dominadas no Project Service Automation, o fluxo de integração será primeiro do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="766ee-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance.</span></span> <span data-ttu-id="766ee-115">As categorias do projeto já devem estar configuradas no Finance antes da sincronização com o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="766ee-115">The project categories must already be configured in Finance before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="766ee-116">Sincronize do Project Service Automation para o Project Service Automation e, depois, novamente do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="766ee-116">Then synchronize from Finance back to Project Service Automation, and then from Project Service Automation to Finance again.</span></span> <span data-ttu-id="766ee-117">Dessa forma, você ajuda a garantir que as categorias estejam vinculadas e que nenhuma duplicata seja criada.</span><span class="sxs-lookup"><span data-stu-id="766ee-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="766ee-118">Geralmente, as categorias de despesa do projeto são dominadas no Finance.</span><span class="sxs-lookup"><span data-stu-id="766ee-118">Typically, the project expense categories are mastered in Finance.</span></span> <span data-ttu-id="766ee-119">Entretanto, se elas não forem ou se já tiverem sido criadas no Project Service Automation, você deverá primeiro sincronizar por meio do modelo de categorias de transação de despesas do projeto (do PSA para o Fin and Ops).</span><span class="sxs-lookup"><span data-stu-id="766ee-119">However, if they aren't, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="766ee-120">Depois sincronize usando o modelo de categorias de transação de despesas do projeto (do Fin and Ops para o PSA).</span><span class="sxs-lookup"><span data-stu-id="766ee-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="766ee-121">Você deverá executar a sincronização do Project Service Automation com o Finance mais uma vez.</span><span class="sxs-lookup"><span data-stu-id="766ee-121">You should then run the synchronization from Project Service Automation to Finance one more time.</span></span>
>
> <span data-ttu-id="766ee-122">Se sincronizar primeiro do Project Service Automation, os seguintes requisitos devem ser atendidos no Finance antes que a sincronização seja executada:</span><span class="sxs-lookup"><span data-stu-id="766ee-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance before the synchronization is run:</span></span>
>
> - <span data-ttu-id="766ee-123">A categoria compartilhada que corresponde à categoria do projeto configurada no Project Service Automation deve existir e estar habilitada para **Projeto** e **Despesa**.</span><span class="sxs-lookup"><span data-stu-id="766ee-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="766ee-124">Para cada entidade legal do Finance que deve ser integrada, as seguintes categorias de projeto devem existir:</span><span class="sxs-lookup"><span data-stu-id="766ee-124">For each Finance legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="766ee-125">A **Categoria do projeto** existe.</span><span class="sxs-lookup"><span data-stu-id="766ee-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="766ee-126">A opção **Usar em Despesa** está habilitada.</span><span class="sxs-lookup"><span data-stu-id="766ee-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="766ee-127">A opção **Ativo em diários** está habilitada.</span><span class="sxs-lookup"><span data-stu-id="766ee-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="766ee-128">O **Tipo de transação** é definido como **Despesa**.</span><span class="sxs-lookup"><span data-stu-id="766ee-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="766ee-129">A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance.</span><span class="sxs-lookup"><span data-stu-id="766ee-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="766ee-130">[![Fluxo de dados da integração do Project Service Automation com o Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="766ee-130">[![Data flow for Project Service Automation integration with Finance](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-to-project-service-automation"></a><span data-ttu-id="766ee-131">A sincronização da categoria de despesas do projeto do Finance para o Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="766ee-131">Project expense category synchronization from Finance to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="766ee-132">Modelo e tarefa</span><span class="sxs-lookup"><span data-stu-id="766ee-132">Template and task</span></span>

<span data-ttu-id="766ee-133">Para acessar o modelo, no Centro de administração do Microsoft Power Apps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="766ee-133">To access the template, in the Microsoft Power Apps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="766ee-134">O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Finance para o Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="766ee-134">The following template and underlying task are used to synchronize project expense categories from Finance to Project Service Automation:</span></span>

- <span data-ttu-id="766ee-135">**Nome do modelo na Integração de dados:** categorias de transação de despesa do projeto (do Fin and Ops para o PSA)</span><span class="sxs-lookup"><span data-stu-id="766ee-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="766ee-136">**Nome da tarefa no projeto:** categorias de sincronização para o PSA</span><span class="sxs-lookup"><span data-stu-id="766ee-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="766ee-137">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="766ee-137">Entity set</span></span>

| <span data-ttu-id="766ee-138">Finanças</span><span class="sxs-lookup"><span data-stu-id="766ee-138">Finance</span></span>                           | <span data-ttu-id="766ee-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="766ee-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="766ee-140">Entidade de integração para categorias</span><span class="sxs-lookup"><span data-stu-id="766ee-140">Integration entity for categories</span></span> | <span data-ttu-id="766ee-141">Categorias de transação</span><span class="sxs-lookup"><span data-stu-id="766ee-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="766ee-142">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="766ee-142">Entity flow</span></span>

<span data-ttu-id="766ee-143">As categorias de despesa do projeto são gerenciadas no Finance e são sincronizadas com o Project Service Automation como categorias de transações.</span><span class="sxs-lookup"><span data-stu-id="766ee-143">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="766ee-144">Power Query</span><span class="sxs-lookup"><span data-stu-id="766ee-144">Power Query</span></span>

<span data-ttu-id="766ee-145">Ao sincronizar com o Project Service Automation, você deve usar o Microsoft Power Query para Excel para definir o tipo de cobrança na categoria de transação.</span><span class="sxs-lookup"><span data-stu-id="766ee-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="766ee-146">O modelo de categorias de transação de despesa do projeto (do Fin and Ops para o PSA) fornece uma coluna padrão e o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="766ee-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="766ee-147">Se você criar seu próprio modelo, deverá adicionar uma coluna condicional no Power Query.</span><span class="sxs-lookup"><span data-stu-id="766ee-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="766ee-148">Execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="766ee-148">Follow these steps.</span></span>

1. <span data-ttu-id="766ee-149">Clique na seta para abrir o mapeamento da tarefa de categorias de despesas do projeto no modelo de categorias de transação de despesas do projeto (do Fin and Ops para o PSA).</span><span class="sxs-lookup"><span data-stu-id="766ee-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="766ee-150">Clique no link **Filtragem e consulta avançada** para abrir o Power Query.</span><span class="sxs-lookup"><span data-stu-id="766ee-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="766ee-151">Selecione **Adicionar coluna condicional**.</span><span class="sxs-lookup"><span data-stu-id="766ee-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="766ee-152">Insira um nome para a nova coluna, como **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="766ee-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="766ee-153">Insira a seguinte condição: **se CATEGORYID não for igual a nulo, ele será 19235001; caso contrário, ele será nulo**.</span><span class="sxs-lookup"><span data-stu-id="766ee-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="766ee-154">Clique em **OK** na coluna.</span><span class="sxs-lookup"><span data-stu-id="766ee-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="766ee-155">Verifique se esta nova coluna está mapeada na página de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="766ee-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="766ee-156">A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="766ee-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="766ee-157">O mapeamento mostra as informações de campo que serão sincronizadas do Finance para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="766ee-157">The mapping shows the field information that will be synchronized from Finance to Project Service Automation.</span></span>

<span data-ttu-id="766ee-158">[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="766ee-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance"></a><span data-ttu-id="766ee-159">A sincronização da categoria de despesas do projeto do Project Service Automation para o Finance</span><span class="sxs-lookup"><span data-stu-id="766ee-159">Project expense category synchronization from Project Service Automation to Finance</span></span>

### <a name="template-and-task"></a><span data-ttu-id="766ee-160">Modelo e tarefa</span><span class="sxs-lookup"><span data-stu-id="766ee-160">Template and task</span></span>

<span data-ttu-id="766ee-161">O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Project Service Automation para o Finance:</span><span class="sxs-lookup"><span data-stu-id="766ee-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="766ee-162">**Nome do modelo na Integração de dados:** categorias de transação de despesa do projeto (do PSA para o Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="766ee-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="766ee-163">**Nome da tarefa no projeto:** categorias de sincronização para o Fin and Ops</span><span class="sxs-lookup"><span data-stu-id="766ee-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="766ee-164">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="766ee-164">Entity set</span></span>

| <span data-ttu-id="766ee-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="766ee-165">Project Service Automation</span></span> | <span data-ttu-id="766ee-166">Finanças</span><span class="sxs-lookup"><span data-stu-id="766ee-166">Finance</span></span>                           |
|----------------------------|-----------------------------------|
| <span data-ttu-id="766ee-167">Categorias de transação</span><span class="sxs-lookup"><span data-stu-id="766ee-167">Transaction categories</span></span>     | <span data-ttu-id="766ee-168">Entidade de integração para categorias</span><span class="sxs-lookup"><span data-stu-id="766ee-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="766ee-169">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="766ee-169">Entity flow</span></span>

<span data-ttu-id="766ee-170">As categorias de despesa do projeto são gerenciadas no Finance e são sincronizadas com o Project Service Automation como categorias de transações.</span><span class="sxs-lookup"><span data-stu-id="766ee-170">Project expense categories are managed in Finance, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="766ee-171">A nova sincronização para o Finance atualiza a categoria de projeto do Finance com a ID de integração do Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="766ee-171">The synchronization back to Finance updates the project category in Finance with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="766ee-172">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="766ee-172">Template mapping in Data integration</span></span>

<span data-ttu-id="766ee-173">A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="766ee-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="766ee-174">O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="766ee-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="766ee-175">[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="766ee-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>
