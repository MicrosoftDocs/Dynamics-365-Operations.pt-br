---
title: Sincronizar estimativas de projeto diretamente do Project Service Automation para o Finance and Operations.
description: Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar estimativas de tempo de projeto e estimativas de despesas de projetos diretamente do Microsoft Dynamics 365 Project Service Automation para o Dynamics 365 Finance.
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
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 3b885610ac9ca8645358ba8ab6d46ab82143a534
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250475"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="ec6b7-103">Sincronizar estimativas de projeto diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-103">Synchronize project estimates directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ec6b7-104">Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar estimativas de tempo de projeto e estimativas de despesas de projetos diretamente do Dynamics 365 Project Service Automation para o Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-104">This topic describes the templates and underlying tasks that are used to synchronize project hour estimates and project expense estimates directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="ec6b7-105">A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis na versão 8.0.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in version 8.0.</span></span>
> - <span data-ttu-id="ec6b7-106">A integração de valores reais está disponível na versão 8.0.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-106">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="ec6b7-107">Fluxo de dados do Project Service Automation para o Finance</span><span class="sxs-lookup"><span data-stu-id="ec6b7-107">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="ec6b7-108">A solução de integração do Project Service Automation para o Finance utiliza o recurso Integração de Dados para sincronizar dados nas instâncias do Project Service Automation e do Finance.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-108">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="ec6b7-109">Os modelos de integração disponíveis com o recurso Integração de Dados permitem o fluxo de dados sobre estimativas de tempo do projeto e estimativas de despesas do projeto do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-109">The integration templates that are available with the Data integration feature enable the flow of data about project hour estimates and project expense estimates from Project Service Automation to Finance.</span></span>

<span data-ttu-id="ec6b7-110">A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-110">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="ec6b7-111">[![Fluxo de dados da integração do Project Service Automation com o Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="ec6b7-111">[![Data flow for Project Service Automation integration with Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)</span></span>

## <a name="project-hour-estimates"></a><span data-ttu-id="ec6b7-112">Estimativas de tempo do projeto</span><span class="sxs-lookup"><span data-stu-id="ec6b7-112">Project hour estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="ec6b7-113">Modelo e tarefas</span><span class="sxs-lookup"><span data-stu-id="ec6b7-113">Template and tasks</span></span>

<span data-ttu-id="ec6b7-114">Para acessar os modelos disponíveis, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-114">To access the available templates, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="ec6b7-115">O seguinte modelo e as tarefas subjacentes são usados para sincronizar estimativas de tempo do projeto do Project Service Automation para o Finance:</span><span class="sxs-lookup"><span data-stu-id="ec6b7-115">The following template and underlying tasks are used to synchronize project hour estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="ec6b7-116">**Nome do modelo na Integração de dados:** estimativas de tempo do projeto (PSA para Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ec6b7-116">**Name of the template in Data integration:** Project hour estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="ec6b7-117">**Nome das tarefas no projeto:**</span><span class="sxs-lookup"><span data-stu-id="ec6b7-117">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="ec6b7-118">Relacionamentos de transações</span><span class="sxs-lookup"><span data-stu-id="ec6b7-118">Transaction relationships</span></span>
    - <span data-ttu-id="ec6b7-119">Estimativas de despesas</span><span class="sxs-lookup"><span data-stu-id="ec6b7-119">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="ec6b7-120">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="ec6b7-120">Entity set</span></span>

| <span data-ttu-id="ec6b7-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="ec6b7-121">Project Service Automation</span></span> | <span data-ttu-id="ec6b7-122">Finanças</span><span class="sxs-lookup"><span data-stu-id="ec6b7-122">Finance</span></span>                                       |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="ec6b7-123">Tarefas de projetos</span><span class="sxs-lookup"><span data-stu-id="ec6b7-123">Project tasks</span></span>              | <span data-ttu-id="ec6b7-124">Entidade de integração para horas previstas do projeto</span><span class="sxs-lookup"><span data-stu-id="ec6b7-124">Integration entity for project hour estimates</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="ec6b7-125">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="ec6b7-125">Entity flow</span></span>

<span data-ttu-id="ec6b7-126">As estimativas de tempo do projeto são gerenciadas no Project Service Automation e são sincronizadas com o Finance como previsões de tempo.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-126">Project hour estimates are managed in Project Service Automation, and they are synchronized to Finance as project hour forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="ec6b7-127">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ec6b7-127">Prerequisites</span></span>

<span data-ttu-id="ec6b7-128">Antes da sincronização de estimativas de tempo do projeto, você deve sincronizar as categorias projetos, tarefas do projeto e transação de despesa do projeto.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-128">Before synchronization of project hour estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="ec6b7-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="ec6b7-129">Power Query</span></span>

<span data-ttu-id="ec6b7-130">No modelo de estimativas de tempo, você deve usar o Microsoft Power Query para Excel para concluir estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="ec6b7-130">In the project hour estimates template, you must use Microsoft Power Query for Excel to complete these tasks:</span></span>

- <span data-ttu-id="ec6b7-131">Defina a ID de modelo de previsão padrão que será usada quando a integração criar novas previsões de tempo.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-131">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="ec6b7-132">Filtre todos os registros específicos do recurso na tarefa que falhará a integração em previsões de tempo.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-132">Filter out any resource-specific records in the task that will fail the integration into hour forecasts.</span></span>
- <span data-ttu-id="ec6b7-133">Filtre as linhas de categoria de transação vazias.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-133">Filter out any empty transaction category rows.</span></span> <span data-ttu-id="ec6b7-134">A falha para concluir essa tarefa pode resultar em previsões de tempo incorretas.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-134">Failure to complete this task might result in incorrect hour forecasts.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="ec6b7-135">Definir a ID do modelo de previsão padrão</span><span class="sxs-lookup"><span data-stu-id="ec6b7-135">Set the default forecast model ID</span></span>

<span data-ttu-id="ec6b7-136">Para atualizar a ID do modelo de previsão padrão no modelo, clique na seta **Mapa** para abrir o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-136">To update the default forecast model ID in the template, click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="ec6b7-137">Em seguida, selecione o link **Filtragem e consulta avançada**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-137">Then select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="ec6b7-138">Se você estiver usando o modelo padrão de estimativas de tempo do Project (PSA para Fin and Ops), selecione **Condição inserida** na lista de **Etapas aplicadas**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-138">If you're using the default Project hour estimates (PSA to Fin and Ops) template, select the **Inserted Condition** in the list of **Applied Steps**.</span></span> <span data-ttu-id="ec6b7-139">Na entrada **Função**, substitua **O\_forecast** pelo nome da ID do modelo de previsão que deve ser usado com a integração.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-139">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="ec6b7-140">O modelo padrão tem uma ID do modelo de previsão dos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-140">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="ec6b7-141">Se você estiver criando um novo modelo, adicione essa coluna.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-141">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="ec6b7-142">No Power Query, selecione **Adicionar coluna condicional** e atribua um nome à nova coluna, como **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-142">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="ec6b7-143">Insira a condição da coluna em que se a tarefa do projeto não for nula, \<insira a ID do modelo de previsão\>; caso contrário, o valor será nulo.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-143">Enter the condition for the column, where, if Project task is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="filter-out-resource-specific-records"></a><span data-ttu-id="ec6b7-144">Filtrar registros específicos de recurso</span><span class="sxs-lookup"><span data-stu-id="ec6b7-144">Filter out resource-specific records</span></span>

<span data-ttu-id="ec6b7-145">O modelo de estimativas de tempo do projeto (PSA para Fin and Ops) tem um filtro padrão que remove todos os registros específicos do recurso.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-145">The Project hour estimates (PSA to Fin and Ops) template has a default filter that removes any resource-specific records.</span></span> <span data-ttu-id="ec6b7-146">Se você criar seu próprio modelo, adicione esse filtro.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-146">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="ec6b7-147">Selecione o link **Filtragem e consulta avançada** para filtrar a coluna **msdyn\_islinetask** para que apenas registros **False** sejam incluídos.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-147">Select the **Advanced Query and Filtering** link to filter on the **msdyn\_islinetask** column so that only **False** records are included.</span></span>

#### <a name="filter-out-empty-transaction-category-rows"></a><span data-ttu-id="ec6b7-148">Filtre as linhas de categoria de transação vazias</span><span class="sxs-lookup"><span data-stu-id="ec6b7-148">Filter out empty transaction category rows</span></span>

<span data-ttu-id="ec6b7-149">Você deve adicionar um filtro para remover as linhas com categorias de transação vazias.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-149">You must add a filter to remove any rows that have empty transaction categories.</span></span> <span data-ttu-id="ec6b7-150">Essa tarefa será necessária, independentemente de você estar usando o modelo padrão ou estiver criando seu próprio modelo.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-150">This task is required, regardless of whether you're using the default template or creating your own template.</span></span> <span data-ttu-id="ec6b7-151">Esse filtro removerá todas as linhas de resumo do Project Service Automation que possam gerar as previsões de tempo incorretas no Finance.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-151">This filter removes any summary rows from Project Service Automation that might cause the hour forecasts in Finance to be incorrect.</span></span> <span data-ttu-id="ec6b7-152">Selecione o link **Filtragem e consulta avançada** para filtrar os registros nulos na coluna **msdyn\_transactioncategory\_value**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-152">Select **Advanced Query and Filtering** link to filter out null records in the **msdyn\_transactioncategory\_value** column.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="ec6b7-153">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="ec6b7-153">Template mapping in Data integration</span></span>

<span data-ttu-id="ec6b7-154">A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-154">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="ec6b7-155">O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-155">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="ec6b7-156">[![Mapeamento de modelo](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="ec6b7-156">[![Template mapping](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)</span></span>

## <a name="project-expense-estimates"></a><span data-ttu-id="ec6b7-157">Estimativas de despesa de projeto</span><span class="sxs-lookup"><span data-stu-id="ec6b7-157">Project expense estimates</span></span>

### <a name="template-and-tasks"></a><span data-ttu-id="ec6b7-158">Modelo e tarefas</span><span class="sxs-lookup"><span data-stu-id="ec6b7-158">Template and tasks</span></span>

<span data-ttu-id="ec6b7-159">O seguinte modelo e as tarefas subjacentes são usados para sincronizar estimativas de despesas do projeto do Project Service Automation para o Finance:</span><span class="sxs-lookup"><span data-stu-id="ec6b7-159">The following template and underlying tasks are used to synchronize project expense estimates from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="ec6b7-160">**Nome do modelo na Integração de dados:** estimativas de despesa do projeto (PSA para Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ec6b7-160">**Name of the template in Data integration:** Project expense estimates (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="ec6b7-161">**Nome das tarefas no projeto:**</span><span class="sxs-lookup"><span data-stu-id="ec6b7-161">**Name of the tasks in the project:**</span></span>

    - <span data-ttu-id="ec6b7-162">Relacionamentos de transações</span><span class="sxs-lookup"><span data-stu-id="ec6b7-162">Transaction relationships</span></span> 
    - <span data-ttu-id="ec6b7-163">Estimativas de despesas</span><span class="sxs-lookup"><span data-stu-id="ec6b7-163">Expense estimates</span></span>

### <a name="entity-set"></a><span data-ttu-id="ec6b7-164">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="ec6b7-164">Entity set</span></span>

| <span data-ttu-id="ec6b7-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="ec6b7-165">Project Service Automation</span></span> | <span data-ttu-id="ec6b7-166">Finanças</span><span class="sxs-lookup"><span data-stu-id="ec6b7-166">Finance</span></span>                                                  |
|----------------------------|----------------------------------------------------------|
| <span data-ttu-id="ec6b7-167">Conexões com transações</span><span class="sxs-lookup"><span data-stu-id="ec6b7-167">Transaction Connections</span></span>    | <span data-ttu-id="ec6b7-168">Entidade de integração para relacionamentos de transações do projeto</span><span class="sxs-lookup"><span data-stu-id="ec6b7-168">Integration entity for project transaction relationships</span></span> |
| <span data-ttu-id="ec6b7-169">Linhas de estimativa</span><span class="sxs-lookup"><span data-stu-id="ec6b7-169">Estimate Lines</span></span>             | <span data-ttu-id="ec6b7-170">Entidade de integração para previsões de despesa do projeto</span><span class="sxs-lookup"><span data-stu-id="ec6b7-170">Integration entity for project expense estimates</span></span>         |

### <a name="entity-flow"></a><span data-ttu-id="ec6b7-171">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="ec6b7-171">Entity flow</span></span>

<span data-ttu-id="ec6b7-172">As estimativas de despesa do projeto são gerenciadas no Project Service Automation e são sincronizadas com o Finance como previsões de despesa.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-172">Project expense estimates are managed in Project Service Automation, and they are synchronized to Finance as project expense forecasts.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="ec6b7-173">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ec6b7-173">Prerequisites</span></span>

<span data-ttu-id="ec6b7-174">Antes da sincronização de estimativas de despesa do projeto, você deve sincronizar as categorias projetos, tarefas do projeto e transação de despesa do projeto.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-174">Before synchronization of project expense estimates can occur, you must synchronize projects, project tasks, and project expense transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="ec6b7-175">Power Query</span><span class="sxs-lookup"><span data-stu-id="ec6b7-175">Power Query</span></span>

<span data-ttu-id="ec6b7-176">No modelo de estimativas de despesa do projeto, você deve usar o Power Query para concluir estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="ec6b7-176">In the project expense estimates template, you must use Power Query to complete the following tasks:</span></span>

- <span data-ttu-id="ec6b7-177">Filtre para incluir somente registros de linhas de estimativa de despesas.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-177">Filter to include only expense estimate line records.</span></span>
- <span data-ttu-id="ec6b7-178">Defina a ID de modelo de previsão padrão que será usada quando a integração criar novas previsões de tempo.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-178">Set the default forecast model ID that will be used when the integration creates new hour forecasts.</span></span>
- <span data-ttu-id="ec6b7-179">Transformar os tipos de cobrança.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-179">Transform the billing types.</span></span>
- <span data-ttu-id="ec6b7-180">Transformar os tipos de transação.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-180">Transform the transaction types.</span></span>

#### <a name="filter-to-include-only-expense-estimate-lines"></a><span data-ttu-id="ec6b7-181">Filtrar para incluir somente linhas de estimativa de despesas</span><span class="sxs-lookup"><span data-stu-id="ec6b7-181">Filter to include only expense estimate lines</span></span>

<span data-ttu-id="ec6b7-182">O modelo de estimativas de despesa do projeto (PSA para Fin and Ops) tem um filtro padrão que inclui linhas de despesa apenas na integração.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-182">The Project expense estimates (PSA to Fin and Ops) template has a default filter that includes only expense lines in the integration.</span></span> <span data-ttu-id="ec6b7-183">Se você criar seu próprio modelo, adicione esse filtro.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-183">If you create your own template, you must add this filter.</span></span> <span data-ttu-id="ec6b7-184">Selecione a tarefa **Relacionamentos de transação** e clique na seta **Mapa** para abrir o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-184">Select the **Transaction relationships** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="ec6b7-185">Selecione o link **Filtragem e consulta avançada**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-185">Select the **Advanced Query and Filtering** link.</span></span> <span data-ttu-id="ec6b7-186">Filtra a coluna **msdyn\_transactiontype1** para que ela inclua apenas **msdyn\_estimateline**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-186">Filter the **msdyn\_transactiontype1** column so that it includes only **msdyn\_estimateline**.</span></span>

#### <a name="set-the-default-forecast-model-id"></a><span data-ttu-id="ec6b7-187">Definir a ID do modelo de previsão padrão</span><span class="sxs-lookup"><span data-stu-id="ec6b7-187">Set the default forecast model ID</span></span>

<span data-ttu-id="ec6b7-188">Para atualizar a ID do modelo de previsão padrão no modelo, selecione a tarefa **Estimativas de despesas** e depois clique na seta **Mapa** para abrir o mapeamento.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-188">To update the default forecast model ID in the template, select the **Expense estimates** task, and then click the **Map** arrow to open the mapping.</span></span> <span data-ttu-id="ec6b7-189">Selecione o link **Filtragem e consulta avançada**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-189">Select the **Advanced Query and Filtering** link.</span></span>

- <span data-ttu-id="ec6b7-190">Se você estiver usando o modelo de estimativas de despesa do Project padrão (do PSA para o Fin and Ops), no Power Query, selecione a primeira **Condição inserida** na seção **Etapas aplicadas**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-190">If you're using the default Project expense estimates (PSA to Fin and Ops) template, in Power Query, select the first **Inserted Condition** from the **Applied Steps** section.</span></span> <span data-ttu-id="ec6b7-191">Na entrada **Função**, substitua **O\_forecast** pelo nome da ID do modelo de previsão que deve ser usado com a integração.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-191">In the **Function** entry, replace **O\_forecast** with the name of the forecast model ID that should be used with the integration.</span></span> <span data-ttu-id="ec6b7-192">O modelo padrão tem uma ID do modelo de previsão dos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-192">The default template has a forecast model ID from the demo data.</span></span>
- <span data-ttu-id="ec6b7-193">Se você estiver criando um novo modelo, adicione essa coluna.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-193">If you're creating a new template, you must add this column.</span></span> <span data-ttu-id="ec6b7-194">No Power Query, selecione **Adicionar coluna condicional** e atribua um nome à nova coluna, como **ModelID**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-194">In Power Query, select **Add Conditional Column**, and enter a name for the new column, such as **ModelID**.</span></span> <span data-ttu-id="ec6b7-195">Insira a condição da coluna em que se a ID da linha de estimativa não for nula, \<insira a ID do modelo de previsão\>; caso contrário, o valor será nulo.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-195">Enter the condition for the column, where, if Estimate line ID is not null, then \<enter the forecast model ID\>; else null.</span></span>

#### <a name="transform-the-billing-types"></a><span data-ttu-id="ec6b7-196">Transformar os tipos de cobrança</span><span class="sxs-lookup"><span data-stu-id="ec6b7-196">Transform the billing types</span></span>

<span data-ttu-id="ec6b7-197">O modelo de estimativa de despesa do projeto (PSA para Fin and Ops) inclui uma coluna condicional adicionada que é usada para transformar os tipos de cobrança recebidos do Project Service Automation durante a integração.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-197">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the billing types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="ec6b7-198">Se você criar seu próprio modelo, adicione essa coluna condicional.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-198">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="ec6b7-199">Selecione o link **Filtragem e consulta avançada** e depois selecione **Adicionar coluna condicional**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-199">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="ec6b7-200">Insira um nome para a nova coluna, como **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-200">Enter a name for the new column, such as **BillingType**.</span></span> <span data-ttu-id="ec6b7-201">Depois insira a seguinte condição:</span><span class="sxs-lookup"><span data-stu-id="ec6b7-201">Then enter the following condition:</span></span>

<span data-ttu-id="ec6b7-202">If **msdyn\_billingtype** = 192350000, then **NonChargeable**</span><span class="sxs-lookup"><span data-stu-id="ec6b7-202">If **msdyn\_billingtype** = 192350000, then **NonChargeable**</span></span>  
<span data-ttu-id="ec6b7-203">else if **msdyn\_billingtype** = 192350001, then **Chargeable**</span><span class="sxs-lookup"><span data-stu-id="ec6b7-203">else if **msdyn\_billingtype** = 192350001, then **Chargeable**</span></span>  
<span data-ttu-id="ec6b7-204">else if **msdyn\_billingtype** = 192350002, then **Complimentary**</span><span class="sxs-lookup"><span data-stu-id="ec6b7-204">else if **msdyn\_billingtype** = 192350002, then **Complimentary**</span></span>  
<span data-ttu-id="ec6b7-205">else **NotAvailable**</span><span class="sxs-lookup"><span data-stu-id="ec6b7-205">else **NotAvailable**</span></span>

#### <a name="transform-the-transaction-types"></a><span data-ttu-id="ec6b7-206">Transformar os tipos de transação</span><span class="sxs-lookup"><span data-stu-id="ec6b7-206">Transform the transaction types</span></span>

<span data-ttu-id="ec6b7-207">O modelo de estimativa de despesa do projeto (PSA para Fin and Ops) inclui uma coluna condicional adicionada que é usada para transformar os tipos de transação recebidos do Project Service Automation durante a integração.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-207">The Project expense estimates (PSA to Fin and Ops) template includes a conditional column that is used to transform the transaction types that are received from Project Service Automation during the integration.</span></span> <span data-ttu-id="ec6b7-208">Se você criar seu próprio modelo, adicione essa coluna condicional.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-208">If you create your own template, you must add this conditional column.</span></span> <span data-ttu-id="ec6b7-209">Selecione o link **Filtragem e consulta avançada** e depois selecione **Adicionar coluna condicional**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-209">Select the **Advanced Query and Filtering** link and then select **Add Conditional Column**.</span></span> <span data-ttu-id="ec6b7-210">Insira um nome para a nova coluna, como **TransactionType**.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-210">Enter a name for the new column, such as **TransactionType**.</span></span> <span data-ttu-id="ec6b7-211">Depois insira a seguinte condição:</span><span class="sxs-lookup"><span data-stu-id="ec6b7-211">Then enter the following condition:</span></span>

<span data-ttu-id="ec6b7-212">If **msdyn\_transactiontypecode** = 192350000, then **Cost**</span><span class="sxs-lookup"><span data-stu-id="ec6b7-212">If **msdyn\_transactiontypecode** = 192350000, then **Cost**</span></span>  
<span data-ttu-id="ec6b7-213">else if **msdyn\_transactiontypecode** = 192350005, then **Sales**</span><span class="sxs-lookup"><span data-stu-id="ec6b7-213">else if **msdyn\_transactiontypecode** = 192350005, then **Sales**</span></span>  
<span data-ttu-id="ec6b7-214">else **null**</span><span class="sxs-lookup"><span data-stu-id="ec6b7-214">else **null**</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="ec6b7-215">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="ec6b7-215">Template mapping in Data integration</span></span>

<span data-ttu-id="ec6b7-216">A ilustração a seguir mostra exemplos de mapeamentos da tarefa de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-216">The following illustrations show examples of the template task mappings in Data integration.</span></span> <span data-ttu-id="ec6b7-217">O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="ec6b7-217">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="ec6b7-218">[![Mapeamento de modelo](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="ec6b7-218">[![Template mapping](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)</span></span>

<span data-ttu-id="ec6b7-219">[![Mapeamento de modelo](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="ec6b7-219">[![Template mapping](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)</span></span>
