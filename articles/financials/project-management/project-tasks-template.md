---
title: Como sincronizar tarefas do projeto a partir do Project Service Automation
description: "Este tópico descreve o modelo e a tarefa subjacente usada para sincronizar tarefas do projeto diretamente do Microsoft Dynamics 365 for Project Service Automation para o Dynamics 365 for Finance and Operations."
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
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: pt-br
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a>Sincronizar tarefas de projeto do Project Service Automation diretamente para atividades de projeto do Finance and Operations.

Este tópico descreve o modelo e a tarefa subjacente usada para sincronizar tarefas do projeto diretamente do Microsoft Dynamics 365 for Project Service Automation para o Dynamics 365 for Finance and Operations.

> [!NOTE]
> A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Dynamics 365 for Finance and Operations versão 8.0.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Fluxo de dados do Project Service Automation para o Finance and Operations

A solução de integração do Project Service Automation para o Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations. O modelo de integração disponível com o recurso Integração de dados permite o fluxo de dados sobre tarefas de projeto do Project Service Automation para o Finance and Operations.

A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.

[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)

## <a name="template-and-task"></a>Modelo e tarefa

Para acessar o modelo, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.

O seguinte modelo e a tarefa subjacente são usados para sincronizar tarefas do projeto do Project Service Automation para o Finance and Operations:

-**Nome do modelo na Integração de dados:** tarefas do projeto (PSA para Fin and Ops) -**Nome da tarefa no projeto:** tarefas do projeto

Antes da sincronização de tarefas do projeto, você deve sincronizar contratos do projeto e projetos.

## <a name="entity-set"></a>Conjunto de entidades

|Project Service Automation               | Finance and Operations                |
|-----------------------------------------|---------------------------------------|
| Tarefas de projetos                           | Entidade de integração para a tarefa do projeto.   |

## <a name="entity-flow"></a>Fluxo de entidades

As tarefas de projeto são gerenciadas no Project Service Automation e são sincronizados para o Finance and Operations como atividades do projeto.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

Antes da sincronização de tarefas do projeto, você deve sincronizar contratos do projeto e projetos.

## <a name="power-query"></a>Power Query

Você deverá usar o Microsoft Power Query para filtrar dados se estas condições forem atendidas:

- Você tem registros específicos do recurso em uma tarefa de projeto.

Se você precisar usar o Power Query, consulte as seguintes diretrizes:

- O modelo Tarefas de projeto (PSA para Fin and Ops) tem um filtro padrão para excluir os registros específicos de recurso de uma tarefa de projeto. Basta definir o filtro **IsLineTask** como **False**. Se você criar seu próprio modelo, adicione esse filtro.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra um exemplo de mapeamentos de tarefas de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.

[![Mapeamento de modelo](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)


