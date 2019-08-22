---
title: Sincronizar estimativas de projeto diretamente do Project Service Automation para o Finance and Operations.
description: Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar estimativas de tempo de projeto e estimativas de despesas de projetos diretamente do Microsoft Dynamics 365 for Project Service Automation para o Microsoft Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: 6bdf139ddd0faa7ba2c9c14b93286eff0ef757fe
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845994"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a>Sincronizar estimativas de projeto diretamente do Project Service Automation para o Finance and Operations.

[!include[banner](../includes/banner.md)]

Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar estimativas de tempo de projeto e estimativas de despesas de projetos diretamente do Microsoft Dynamics 365 for Project Service Automation para o Dynamics 365 for Finance and Operations.

> [!NOTE]
> - A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Microsoft Dynamics 365 for Finance and Operations versão 8.0.
> - A integração de valores reais está disponível no Microsoft Dynamics 365 for Finance and Operations versão 8.0.1 ou posterior.
> - Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e números reais e para configurar o bloqueio de funcionalidade. Se você precisar redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Fluxo de dados do Project Service Automation para o Finance and Operations

A solução de integração do Project Service Automation para o Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations. Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre estimativas de tempo do projeto e estimativas de despesas do projeto do Project Service Automation para o Finance and Operations.

A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.

[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)

## <a name="project-hour-estimates"></a>Estimativas de tempo do projeto

### <a name="template-and-tasks"></a>Modelo e tarefas

Para acessar os modelos disponíveis, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.

O seguinte modelo e as tarefas subjacentes são usados para sincronizar estimativas de tempo do projeto do Project Service Automation para o Finance and Operations:

- **Nome do modelo na Integração de dados:** estimativas de tempo do projeto (PSA para Fin and Ops)
- **Nome das tarefas no projeto:**

    - Relacionamentos de transações
    - Estimativas de despesas

### <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finance and Operations                        |
|----------------------------|-----------------------------------------------|
| Tarefas de projetos              | Entidade de integração para horas previstas do projeto |

### <a name="entity-flow"></a>Fluxo de entidades

As estimativas de tempo do projeto são gerenciadas no Project Service Automation e são sincronizadas para o Finance and Operations como previsões de tempo.

### <a name="prerequisites"></a>Pré-requisitos

Antes da sincronização de estimativas de tempo do projeto, você deve sincronizar as categorias projetos, tarefas do projeto e transação de despesa do projeto.

### <a name="power-query"></a>Power Query

No modelo de estimativas de tempo, você deve usar o Microsoft Power Query para Excel para concluir estas tarefas:

- Defina a ID de modelo de previsão padrão que será usada quando a integração criar novas previsões de tempo.
- Filtre todos os registros específicos do recurso na tarefa que falhará a integração em previsões de tempo.
- Filtre as linhas de categoria de transação vazias. A falha para concluir essa tarefa pode resultar em previsões de tempo incorretas.

#### <a name="set-the-default-forecast-model-id"></a>Definir a ID do modelo de previsão padrão

Para atualizar a ID do modelo de previsão padrão no modelo, clique na seta **Mapa** para abrir o mapeamento. Em seguida, selecione o link **Filtragem e consulta avançada**.

- Se você estiver usando o modelo padrão de estimativas de tempo do Project (PSA para Fin and Ops), selecione **Condição inserida** na lista de **Etapas aplicadas**. Na entrada **Função**, substitua **O\_forecast** pelo nome da ID do modelo de previsão que deve ser usado com a integração. O modelo padrão tem uma ID do modelo de previsão dos dados de demonstração.
- Se você estiver criando um novo modelo, adicione essa coluna. No Power Query, selecione **Adicionar coluna condicional** e atribua um nome à nova coluna, como **ModelID**. Insira a condição da coluna em que se a tarefa do projeto não for nula, \<insira a ID do modelo de previsão\>; caso contrário, o valor será nulo.

#### <a name="filter-out-resource-specific-records"></a>Filtrar registros específicos de recurso

O modelo de estimativas de tempo do projeto (PSA para Fin and Ops) tem um filtro padrão que remove todos os registros específicos do recurso. Se você criar seu próprio modelo, adicione esse filtro. Selecione o link **Filtragem e consulta avançada** para filtrar a coluna **msdyn\_islinetask** para que apenas registros **False** sejam incluídos.

#### <a name="filter-out-empty-transaction-category-rows"></a>Filtre as linhas de categoria de transação vazias

Você deve adicionar um filtro para remover as linhas com categorias de transação vazias. Essa tarefa será necessária, independentemente de você estar usando o modelo padrão ou estiver criando seu próprio modelo. Esse filtro removerá todas as linhas resumidas do Project Service Automation que possam gerar as previsões de tempo incorretas no Finance and Operations. Selecione o link **Filtragem e consulta avançada** para filtrar os registros nulos na coluna **msdyn\_transactioncategory\_value**.

### <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.

[![Mapeamento de modelo](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

## <a name="project-expense-estimates"></a>Estimativas de despesa de projeto

### <a name="template-and-tasks"></a>Modelo e tarefas

O seguinte modelo e as tarefas subjacentes são usados para sincronizar estimativas de despesa do projeto do Project Service Automation para o Finance and Operations:

- **Nome do modelo na Integração de dados:** estimativas de despesa do projeto (PSA para Fin and Ops)
- **Nome das tarefas no projeto:**

    - Relacionamentos de transações 
    - Estimativas de despesas

### <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finance and Operations                                   |
|----------------------------|----------------------------------------------------------|
| Conexões com transações    | Entidade de integração para relacionamentos de transações do projeto |
| Linhas de estimativa             | Entidade de integração para previsões de despesa do projeto         |

### <a name="entity-flow"></a>Fluxo de entidades

As estimativas de despesa do projeto são gerenciadas no Project Service Automation e são sincronizadas para o Finance and Operations como previsões de despesa.

### <a name="prerequisites"></a>Pré-requisitos

Antes da sincronização de estimativas de despesa do projeto, você deve sincronizar as categorias projetos, tarefas do projeto e transação de despesa do projeto.

### <a name="power-query"></a>Power Query

No modelo de estimativas de despesa do projeto, você deve usar o Power Query para concluir estas tarefas:

- Filtre para incluir somente registros de linhas de estimativa de despesas.
- Defina a ID de modelo de previsão padrão que será usada quando a integração criar novas previsões de tempo.
- Transformar os tipos de cobrança.
- Transformar os tipos de transação.

#### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtrar para incluir somente linhas de estimativa de despesas

O modelo de estimativas de despesa do projeto (PSA para Fin and Ops) tem um filtro padrão que inclui linhas de despesa apenas na integração. Se você criar seu próprio modelo, adicione esse filtro. Selecione a tarefa **Relacionamentos de transação** e clique na seta **Mapa** para abrir o mapeamento. Selecione o link **Filtragem e consulta avançada**. Filtra a coluna **msdyn\_transactiontype1** para que ela inclua apenas **msdyn\_estimateline**.

#### <a name="set-the-default-forecast-model-id"></a>Definir a ID do modelo de previsão padrão

Para atualizar a ID do modelo de previsão padrão no modelo, selecione a tarefa **Estimativas de despesas** e depois clique na seta **Mapa** para abrir o mapeamento. Selecione o link **Filtragem e consulta avançada**.

- Se você estiver usando o modelo de estimativas de despesa do Project padrão (do PSA para o Fin and Ops), no Power Query, selecione a primeira **Condição inserida** na seção **Etapas aplicadas**. Na entrada **Função**, substitua **O\_forecast** pelo nome da ID do modelo de previsão que deve ser usado com a integração. O modelo padrão tem uma ID do modelo de previsão dos dados de demonstração.
- Se você estiver criando um novo modelo, adicione essa coluna. No Power Query, selecione **Adicionar coluna condicional** e atribua um nome à nova coluna, como **ModelID**. Insira a condição da coluna em que se a ID da linha de estimativa não for nula, \<insira a ID do modelo de previsão\>; caso contrário, o valor será nulo.

#### <a name="transform-the-billing-types"></a>Transformar os tipos de cobrança

O modelo de estimativa de despesa do projeto (PSA para Fin and Ops) inclui uma coluna condicional adicionada que é usada para transformar os tipos de cobrança recebidos do Project Service Automation durante a integração. Se você criar seu próprio modelo, adicione essa coluna condicional. Selecione o link **Filtragem e consulta avançada** e depois selecione **Adicionar coluna condicional**. Insira um nome para a nova coluna, como **BillingType**. Depois insira a seguinte condição:

If **msdyn\_billingtype** = 192350000, then **NonChargeable**  
else if **msdyn\_billingtype** = 192350001, then **Chargeable**  
else if **msdyn\_billingtype** = 192350002, then **Complimentary**  
else **NotAvailable**

#### <a name="transform-the-transaction-types"></a>Transformar os tipos de transação

O modelo de estimativa de despesa do projeto (PSA para Fin and Ops) inclui uma coluna condicional adicionada que é usada para transformar os tipos de transação recebidos do Project Service Automation durante a integração. Se você criar seu próprio modelo, adicione essa coluna condicional. Selecione o link **Filtragem e consulta avançada** e depois selecione **Adicionar coluna condicional**. Insira um nome para a nova coluna, como **TransactionType**. Depois insira a seguinte condição:

If **msdyn\_transactiontypecode** = 192350000, then **Cost**  
else if **msdyn\_transactiontypecode** = 192350005, then **Sales**  
else **null**

### <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra exemplos de mapeamentos da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.

[![Mapeamento de modelo](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mapeamento de modelo](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)
