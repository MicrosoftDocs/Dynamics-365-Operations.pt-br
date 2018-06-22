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

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a>Sincronize categorias de despesa do projeto entre o Finance and Operations e o Project Service Automation

Este tópico descreve os modelos e as tarefas subjacentes usadas para sincronizar categorias de despesa do projeto entre o Microsoft Dynamics 365 for Finance and Operations e o Dynamics 365 for Project Service Automation.

> [!NOTE]
> A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Dynamics 365 for Finance and Operations versão 8.0.

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a>Fluxo de dados para o Project Service Automation e o Finance and Operations

A solução de integração do Project Service Automation e do Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations. Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre categorias de transações de despesa do projeto entre o Finance and Operations e o Project Service Automation.

Se as categorias de despesa do projeto forem dominadas no Finance and Operations, o fluxo de integração será primeiro do Finance and Operations para o Project Service Automation. Depois, as IDs de integração de categorias de despesa do projeto serão atualizadas através da sincronização do Project Service Automation para o Finance and Operations.

Se as categorias de despesa do projeto forem dominadas no Project Service Automation, o fluxo de integração será primeiro do Project Service Automation para o Finance and Operations. As categorias do projeto já devem estar configuradas no Finance and Operations antes da sincronização para o Project Service Automation. Sincronize do Project Service Automation para o Project Service Automation e, depois, novamente do Project Service Automation para o Finance and Operations. Isso garante que as categorias sejam vinculadas e que duplicatas não sejam criados.

> [!NOTE]
> Geralmente, as categorias de despesa do projeto serão dominadas no Finance and Operations. Se não for o seu caso ou se você já tiver categorias de despesa criadas no Project Service Automation, primeiro sincronize usando as categorias de transação de despesa do projeto (do PSA para o Fin and Ops) e, depois, sincronize usando categorias de transação de despesa do projeto (do Fin and Ops para o PSA). Você deve executar a sincronização do PSA para o Fin and Ops mais uma vez.

> Se a sincronização for primeiro a partir do Project Service Automation, as categorias de projeto já deverão estar configuradas no Finance and Operations. As categorias de projeto que precisem ser sincronizadas com as categorias de transações do Project Service Automation deverão ser configuradas como **Ativo em diários**.

A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.

[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)


## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.

O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Finance and Operations para o Project Service Automation:

-  **Nome do modelo na Integração de dados:** categorias de transação de despesa do projeto (do Fin and Ops para o PSA)
-  **Nome da tarefa no projeto:** categorias de sincronização para o PSA

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations               | Project Service Automation    |
|--------------------------------------|-------------------------------|
| Entidade de integração para categorias    | Categorias de transação        |

## <a name="entity-flow"></a>Fluxo de entidades

As categorias de despesa do projeto são gerenciadas no Finance and Operations e são sincronizadas para o Project Service Automation como categorias de transações.

## <a name="power-query"></a>Power Query

Você deve usar o Microsoft Power Query para definir o tipo de cobrança na categoria de transação ao sincronizar para o Project Service Automation. O modelo de categorias de transação de despesa do projeto (do Fin and Ops para o PSA) tem uma coluna padrão e o mapeamento já fornecido. Se você criar seu próprio modelo, deverá adicionar uma coluna condicional no Power Query.
- Abra o formulário avançado de filtragem e consulta a partir do mapeamento da tarefa de categorias de despesa do projeto.
- Selecione **Adicionar coluna condicional**.
- Atribua um nome à nova coluna, como BillingType.
- Insira a seguinte condição: se **CATEGORYID não for igual a nulo, ele será 19235001; caso contrário, ele será nulo**.
- Clique em **OK** na coluna.
- Verifique se esta nova coluna está mapeada na página de mapeamento.

A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Finance and Operations para o Project Service Automation.

[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)

O seguinte modelo e a tarefa subjacente são usados para sincronizar categorias de despesa do projeto do Project Service Automation para o Finance and Operations:

-**Nome do modelo na integração de dados:** categorias de transação de despesa do projeto (do PSA para o Fin and Ops) -**Nome da tarefa no projeto:** categorias de sincronização para o Fin and Ops

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation      | Finance and Operations             |
|---------------------------------|------------------------------------|
| Categorias de transação          | Entidade de integração para categorias  | 

## <a name="entity-flow"></a>Fluxo de entidades

As categorias de despesa do projeto são gerenciadas no Finance and Operations e são sincronizadas para o Project Service Automation como categorias de transações. A nova sincronização para o Finance and Operations atualiza a ID de integração do Project Service Automation na categoria de projeto do Finance and Operations.

A ilustração a seguir mostra um exemplo do mapeamento da tarefa de modelo na Integração de dados.

> [!NOTE]
> O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.

[![Mapeamento de modelo](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)

