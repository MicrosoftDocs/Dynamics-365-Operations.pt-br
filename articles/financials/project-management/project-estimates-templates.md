---
title: "Sincronizar estimativas de projeto do Project Service Automation diretamente para previsões de projeto do Finance and Operations."
description: "Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar estimativas de tempo de projeto e estimativas de despesas de projetos diretamente do Microsoft Dynamics 365 for Project Service Automation para o Dynamics 365 for Finance and Operations."
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
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 90501f40da0fdc66ad087b3bd746c908cc25711b
ms.contentlocale: pt-br
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-estimates-from-project-service-automation-directly-to-project-forecasts-in-finance-and-operations"></a>Sincronizar estimativas de projeto do Project Service Automation diretamente para previsões de projeto do Finance and Operations.

Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar estimativas de tempo de projeto e estimativas de despesas de projetos diretamente do Microsoft Dynamics 365 for Project Service Automation para o Dynamics 365 for Finance and Operations.

> [!NOTE]
> A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Dynamics 365 for Finance and Operations versão 8.0.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Fluxo de dados do Project Service Automation para o Finance and Operations

A solução de integração do Project Service Automation para o Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations. Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre estimativas de tempo do projeto e estimativas de despesas do projeto do Project Service Automation para o Finance and Operations.

A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.

[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)


## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.

O seguinte modelo e as tarefas subjacentes são usados para sincronizar estimativas de tempo do projeto do Project Service Automation para o Finance and Operations:

-  **Nome do modelo na Integração de dados:** estimativas de tempo do projeto (PSA para Fin and Ops)

-  **Nome das tarefas no projeto:** 
    - Relacionamentos de transações 
    - Estimativas de despesas

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation      | Finance and Operations                          |
|---------------------------------|-------------------------------------------------|
| Tarefas de projetos                   | Entidade de integração para horas previstas do projeto   |

## <a name="entity-flow"></a>Fluxo de entidades

As estimativas de tempo do projeto são gerenciadas no Project Service Automation e são sincronizadas para o Finance and Operations como previsões de tempo.

## <a name="preconditions"></a>Precondições

Antes da sincronização de estimativas de tempo do projeto, você deve sincronizar as categorias projetos, tarefas do projeto e transação de despesa do projeto.

## <a name="power-query"></a>Power Query

Você deve usar o Microsoft Power Query no modelo de estimativas de tempo do projeto para:
- Defina a **ID de modelo de previsão** que será usada quando a integração criar novas previsões de tempo.
- Filtre todos os registros específicos do recurso na tarefa que falhará a integração em previsões de tempo
- Filtre as linhas de categoria de transação vazias. A falha nessa ação pode resultar em previsões de tempo incorretas.

### <a name="forecast-model-id"></a>ID do modelo de previsão
Para atualizar a ID do modelo de previsão padrão no modelo, clique na seta **Mapa** para abrir o mapeamento. Selecione para abrir a Filtragem e consulta avançada.
- Se você estiver usando o modelo padrão de estimativas de tempo do Microsoft Project (PSA para Fin and Ops), selecione **Condição inserida** na seção **Etapas aplicadas**. Na entrada **Função**, substitua **O_forecast** pelo nome da **ID do modelo de previsão** que deve ser usado com a integração. O modelo padrão tem uma ID do modelo de previsão dos dados de demonstração.
- Se você estiver criando um novo modelo, adicione essa coluna. Selecione **Adicionar Coluna Condicional** e atribua um nome à coluna, como ModelID. Insira a condição da coluna em que, se a tarefa do projeto não for nula, <enter the forecast model ID>; caso contrário, o valor será nulo.

### <a name="filter-out-resource-specific-records"></a>Filtre registros específicos de recurso
O modelo de estimativas de tempo do projeto (PSA para Fin and Ops) tem um filtro padrão que remove todos os registros específicos do recurso. Se você criar seu próprio modelo, adicione esse filtro. No formulário Filtragem e consulta avançada, selecione para filtrar na coluna **msdyn_islinetask** para incluir somente registros **False**.

### <a name="filter-out-empty-transaction-category-rows"></a>Filtre as linhas de categoria de transação vazias
Você deve adicionar um filtro para remover as linhas com categorias de transação vazias. Isso será necessário se você estiver usando o modelo padrão ou estiver criando seu próprio modelo. Esse filtro removerá todas as linhas resumidas originadas do Project Service Automation que possam gerar as previsões de tempo incorretas no Finance and Operations. No formulário Filtragem e consulta avançada, selecione para filtrar os registros nulos na coluna **msdyn_transactioncategory_value**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.

[![Mapeamento de modelo](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

O seguinte modelo e a tarefa subjacente são usados para sincronizar estimativas de despesa do projeto do Project Service Automation para o Finance and Operations:

-  **Nome do modelo na Integração de dados:** estimativas de despesa do projeto (PSA para Fin and Ops)
-  **Nome das tarefas no projeto:** 
     - Relacionamentos de transações 
     - Estimativas de despesas

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation      | Finance and Operations                                     |
|---------------------------------|------------------------------------------------------------|
| Conexões com transações         | Entidade de integração para relacionamentos de transações do projeto.   |
| Linhas de estimativa                  | Entidade de integração para estimativas de despesa do projeto.           |

## <a name="entity-flow"></a>Fluxo de entidades

As estimativas de despesa do projeto são gerenciadas no Project Service Automation e são sincronizadas para o Finance and Operations como previsões de despesa.

## <a name="prerequisites"></a>Pré-requisitos

Antes da sincronização de estimativas de despesa do projeto, você deve sincronizar as categorias projetos, tarefas do projeto e transação de despesa do projeto.

## <a name="power-query"></a>Power Query

Você deve usar o Microsoft Power Query no modelo de estimativas de despesa do projeto para:
- Filtrar para incluir somente registros de linhas de estimativa de despesas
- Defina a **ID de modelo de previsão** que será usada quando a integração criar novas previsões de tempo.
- Transformar os tipos de cobrança.
- Transformar os tipos de transação.

### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtrar para incluir somente linhas de estimativa de despesas
O modelo de estimativas de despesa do projeto (PSA para Fin and Ops) tem um filtro padrão para incluir linhas de despesa apenas na integração. Se você criar seu próprio modelo, adicione esse filtro. Selecione a tarefa Relacionamentos de transação e clique na seta **Mapa**. Selecione **Filtragem e consulta avançada**. Filtre a coluna **msdyn_transactiontype1** para incluir apenas **msdyn_estimateline**.

### <a name="forecast-model-id"></a>ID do modelo de previsão
Para atualizar a ID do modelo de previsão padrão no modelo, para a tarefa Estimativas de despesas, clique na seta **Mapa** para abrir o mapeamento. Selecione para abrir a Filtragem e consulta avançada.
- Se você estiver usando o modelo padrão de estimativas de despesas do Microsoft Project (PSA para Fin and Ops), selecione a primeira **Condição inserida** na seção **Etapas aplicadas**. Na entrada **Função**, substitua **O_forecast** pelo nome da **ID do modelo de previsão** que deve ser usado com a integração. O modelo padrão tem uma ID do modelo de previsão dos dados de demonstração.
- Se você estiver criando um novo modelo, adicione essa coluna. Selecione **Adicionar Coluna Condicional** e atribua um nome à coluna, como ModelID. Insira a condição da coluna em que se a ID da linha de estimativa não for nula, < insira a ID do modelo de previsão >; caso contrário, o valor será nulo.

### <a name="transform-the-billing-types"></a>Transformar os tipos de cobrança
O modelo de estimativa de despesa do projeto (PSA para Fin and Ops) tem uma coluna condicional adicionada para transformar os tipos de cobrança recebidos do Project Service Automation durante a integração.
- Se você criar seu próprio modelo, adicione essa coluna condicional. No formulário Filtragem e consulta avançada, selecione **Adicionar Coluna Condicional**. Atribua um nome à coluna, como "BillingType". Esta é a condição a ser inserida:

    If **msdyn_billingtype** = 192350000, then **NonChargeable** else if **msdyn_billingtype** = 192350001, then **Chargeable** else if **msdyn_billingtype** = 192350002, then **Complimentary** else **NotAvailable**

### <a name="transform-the-transaction-types"></a>Transformar os tipos de transação
O modelo de estimativa de despesa do projeto (PSA para Fin and Ops) tem uma coluna condicional adicionada para transformar os tipos de transação recebidos do Project Service Automation durante a integração.
- Se você criar seu próprio modelo, adicione essa coluna condicional. No formulário Filtragem e consulta avançada, selecione **Adicionar Coluna Condicional**. Atribua um nome à coluna, como "TransactionType". Esta é a condição a ser inserida: If **msdyn_transactiontypecode** = 192350000, then **Cost** else if **msdyn_transactiontypecode** = 192350005, then **Sales** else **null**

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra exemplos de mapeamentos da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.

[![Mapeamento de modelo](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mapeamento de modelo](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)




