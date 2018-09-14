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

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Sincronize categorias de despesa do projeto entre o Finance and Operations e o Project Service Automation

[!include[banner](../includes/banner.md)]

Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar categorias de despesa do projeto entre o Microsoft Dynamics 365 for Finance and Operations e o Microsoft Dynamics 365 for Project Service Automation.

> [!NOTE]
> - A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Microsoft Dynamics 365 for Finance and Operations versão 8.0.
> - A integração de valores reais está disponível no Microsoft Dynamics 365 for Finance and Operations versão 8.0.1 ou posterior.
> - Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e números reais e para configurar o bloqueio de funcionalidade. Se você precisar redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Fluxo de dados para o Project Service Automation e o Finance and Operations

A solução de integração do Project Service Automation e do Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations. Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre categorias de transações de despesa do projeto entre o Finance and Operations e o Project Service Automation.

Se as categorias de despesa do projeto forem dominadas no Finance and Operations, o fluxo de integração será primeiro do Finance and Operations para o Project Service Automation. As IDs de integração das categorias de despesas do projeto são atualizados por meio da sincronização do Project Service Automation para o Finance and Operations.

Se as categorias de despesa do projeto forem dominadas no Project Service Automation, o fluxo de integração será primeiro do Project Service Automation para o Finance and Operations. As categorias do projeto já devem estar configuradas no Finance and Operations antes da sincronização para o Project Service Automation. Sincronize do Project Service Automation para o Project Service Automation e, depois, novamente do Project Service Automation para o Finance and Operations. Dessa forma, você ajuda a garantir que as categorias estejam vinculadas e que nenhuma duplicata seja criada.

> [!NOTE]
> Geralmente, as categorias de despesa do projeto são dominadas no Finance and Operations. Entretanto, se elas não forem dominadas no Finance and Operations ou se já tiverem sido criadas no Project Service Automation, você deverá primeiro sincronizar por meio do modelo de categorias de transação de despesas do projeto (do PSA para o Fin and Ops). Depois sincronize usando o modelo de categorias de transação de despesas do projeto (do Fin and Ops para o PSA). Você deverá executar a sincronização do Project Service Automation para o Finance and Operations mais uma vez.
>
> Se sincronizar primeiro a partir do Project Service Automation, os seguintes requisitos devem ser atendidos no Finance and Operations antes que a sincronização seja executada:
>
> - A categoria compartilhada que corresponde à categoria do projeto configurada no Project Service Automation deve existir e estar habilitada para **Projeto** e **Despesa**.
> - Para cada entidade legal do Finance and Operations que deve ser integrada, as seguintes categorias de projeto devem existir:
>
>     - A **Categoria do projeto** existe. 
>     - A opção **Usar em Despesa** está habilitada.
>     - A opção **Ativo em diários** está habilitada.
>     - O **Tipo de transação** é definido como **Despesa**.

A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.

[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a>A sincronização da categoria de despesas do projeto, do Finance and Operations para o Project Service Automation

### <a name="template-and-task"></a>Modelo e tarefa

Para acessar o modelo, no centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.

O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Finance and Operations para o Project Service Automation:

- **Nome do modelo na Integração de dados:** categorias de transação de despesa do projeto (do Fin and Ops para o PSA)
- **Nome da tarefa no projeto:** categorias de sincronização para o PSA

### <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations            | Project Service Automation |
|-----------------------------------|----------------------------|
| Entidade de integração para categorias | Categorias de transação     |

### <a name="entity-flow"></a>Fluxo de entidades

As categorias de despesa do projeto são gerenciadas no Finance and Operations e são sincronizadas para o Project Service Automation como categorias de transações.

### <a name="power-query"></a>Power Query

Ao sincronizar com o Project Service Automation, você deve usar o Microsoft Power Query para Excel para definir o tipo de cobrança na categoria de transação. O modelo de categorias de transação de despesa do projeto (do Fin and Ops para o PSA) fornece uma coluna padrão e o mapeamento. Se você criar seu próprio modelo, deverá adicionar uma coluna condicional no Power Query. Execute as etapas a seguir.

1. Clique na seta para abrir o mapeamento da tarefa de categorias de despesas do projeto no modelo de categorias de transação de despesas do projeto (do Fin and Ops para o PSA).
2. Clique no link **Filtragem e consulta avançada** para abrir o Power Query.
2. Selecione **Adicionar coluna condicional**.
3. Insira um nome para a nova coluna, como **BillingType**.
4. Insira a seguinte condição: **se CATEGORYID não for igual a nulo, ele será 19235001; caso contrário, ele será nulo**.
5. Clique em **OK** na coluna.
6. Verifique se esta nova coluna está mapeada na página de mapeamento.

A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Finance and Operations para o Project Service Automation.

[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a>A sincronização da categoria de despesas do projeto, do Project Service Automation para o Finance and Operations

### <a name="template-and-task"></a>Modelo e tarefa

O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Project Service Automation para o Finance and Operations:

- **Nome do modelo na Integração de dados:** categorias de transação de despesa do projeto (do PSA para o Fin and Ops)
- **Nome da tarefa no projeto:** categorias de sincronização para o Fin and Ops

### <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation | Finance and Operations            |
|----------------------------|-----------------------------------|
| Categorias de transação     | Entidade de integração para categorias |

### <a name="entity-flow"></a>Fluxo de entidades

As categorias de despesa do projeto são gerenciadas no Finance and Operations e são sincronizadas para o Project Service Automation como categorias de transações. A nova sincronização para o Finance and Operations atualiza a categoria de projeto do Finance and Operations com a ID de integração do Project Service Automation.

### <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados.

> [!NOTE]
> O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.

[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)
