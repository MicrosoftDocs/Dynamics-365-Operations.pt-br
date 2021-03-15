---
title: Visão geral do sistema de fluxo de trabalho
description: Este tópico descreve o sistema de fluxo de trabalho.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 660e01618eea66bc611dd51818694d36993ba9ea
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796987"
---
# <a name="workflow-system-overview"></a>Visão geral do sistema de fluxo de trabalho

[!include [banner](../includes/banner.md)]

Este tópico descreve o sistema de fluxo de trabalho.

## <a name="what-is-workflow"></a>O que é um fluxo de trabalho?

O termo *fluxo de trabalho* pode ser definido de duas maneiras: como um sistema e como um processo comercial.

### <a name="workflow-is-a-system"></a>O fluxo de trabalho é um sistema

O fluxo de trabalho é um sistema executado no Microsoft Dynamics AX Application Object Server (AOS). O sistema de fluxo de trabalho fornece uma funcionalidade que você pode usar para criar fluxos de trabalho individuais ou processos comerciais.

### <a name="workflow-is-a-business-process"></a>O fluxo de trabalho é um processo comercial

Um fluxo de trabalho representa um processo comercial. Ele define como um documento flui, ou se move, pelo sistema, mostrando quem deve concluir uma tarefa, tomar uma decisão ou aprovar um documento. Por exemplo, a ilustração a seguir mostra um fluxo de trabalho para relatórios de despesas.

![Fluxo de trabalho com elementos que são atribuídos a usuários](./media/workflow_user.gif)

Para entender melhor esse fluxo de trabalho, suponha que Samuel envie um relatório de despesas no valor de US$ 7.000. Nesse cenário, Ivan deve revisar os recibos que Samuel direcionou a ele. Depois, Francisco e Suzana devem aprovar o relatório de despesas. Agora suponha que Samuel envie um relatório de despesas no valor de US$ 11.000. Nesse cenário, Ivan deve revisar os recibos e Francisco, Suzana e Ana devem aprovar o relatório de despesas.

## <a name="benefits-of-using-the-workflow-system"></a>Benefícios de usar o sistema de fluxo de trabalho

O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:

- **Processos consistentes** – você pode definir como documentos específicos, como requisições de compra e relatórios de despesas, são processados. Ao usar esse sistema, você garante que os documentos sejam processados e aprovados de maneira consistente e eficiente.
- **Visibilidade do processo** – você pode rastrear o status, o histórico e as métricas de desempenho de instâncias do fluxo de trabalho. Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.
- **Lista de trabalho centralizada** – os usuários podem exibir uma lista de trabalho centralizada que exibe as tarefas e aprovações de fluxo de trabalho que são atribuídas a elas.


## <a name="workflow-content"></a>Contexto do fluxo de trabalho

+ [Arquitetura do sistema de fluxo de trabalho](workflow-system-architecture.md)
+ [Elementos de fluxo de trabalho](workflow-elements.md)
+ [Ações nos processos de aprovação do fluxo de trabalho](workflow-actions.md)
+ [Visão geral de criação de fluxos de trabalho](create-workflow.md)
+ [Configurar propriedades do fluxo de trabalho](configure-workflow-properties.md)
+ [Configurar tarefas manuais em um fluxo de trabalho](configure-manual-task-workflow.md)
+ [Configurar tarefas automatizadas em um fluxo de trabalho](configure-automated-task-workflow.md)
+ [Configurar processos de aprovação em um fluxo de trabalho](configure-approval-process-workflow.md)
+ [Configurar etapas de aprovação em um fluxo de trabalho](configure-approval-step-workflow.md)
+ [Configurar decisões manuais em um fluxo de trabalho](configure-manual-decision-workflow.md)
+ [Configurar decisões condicionais em um fluxo de trabalho](configure-conditional-decision-workflow.md)
+ [Configurar atividades paralelas em um fluxo de trabalho](configure-parallel-activity-workflow.md)
+ [Configurar ramificações paralelas em um fluxo de trabalho](configure-parallel-branch-workflow.md)
+ [Configurar fluxos de trabalho de item de linha](configure-line-item-workflow.md)
+ [Perguntas frequentes sobre fluxo de trabalho](workflow-FAQ.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]