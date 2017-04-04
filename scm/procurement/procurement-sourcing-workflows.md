---
title: Fluxos de trabalho de Compras
description: "Algumas organizações exigem que as requisições de compra e as ordens de compra sejam aprovadas por um usuário diferente daquele que iniciou a transação. Para configurar um processo de aprovação, você pode criar um fluxo de trabalho."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 27c211e6ded17e085559add916c28a48c40e5b8e
ms.lasthandoff: 03/31/2017


---

# <a name="procurement-and-sourcing-workflows"></a>Fluxos de trabalho de compras

Algumas organizações exigem que as requisições de compra e as ordens de compra sejam aprovadas por um usuário diferente daquele que iniciou a transação. Para configurar um processo de aprovação, você pode criar um fluxo de trabalho.

Um fluxo de trabalho representa um processo comercial. Ele define como um documento flui pelo sistema e indica quem deve concluir uma tarefa ou aprovar um documento. O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:
-   **Processos consistentes** — você pode definir o processo de aprovação de documentos específicos, como requisições de compra e relatórios de despesas. O uso desse sistema ajuda a garantir que os documentos sejam processados e aprovados de maneira consistente e eficiente.
-   **Visibilidade do processo** — você pode rastrear o status, o histórico e as métricas de desempenho de uma instância específica do fluxo de trabalho. Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.
-   ** A lista de trabalho centralizada — ** usuários pode exibir uma lista de trabalho centralizada para ver as tarefas e as aprovações de fluxo de trabalho atribuídos a eles em todos os fluxos de trabalho que participam em. Isso está disponível na página de itens de trabalho.

## <a name="the-types-of-workflows-that-you-can-create"></a>Os tipos de fluxo de trabalho que você pode criar
Os tipos de fluxo de trabalho a seguir estão disponíveis para Compras.

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| **Tipo**                         | **Use este tipo para**                                          |
| Revisão da requisição de compra      | Criar fluxos de trabalho de revisão para requisições de compra.            |
| Revisão de linha de requisição de compra | Criar fluxos de trabalho de revisão para linhas de requisição de compra.       |
| Fluxo de trabalho da ordem de compra          | Criar fluxos de trabalho de revisão e aprovação para ordens de compra.     |
| Fluxo de trabalho da linha da ordem de compra     | Criar fluxos de trabalho de revisão e aprovação para linhas de ordens de compra. |

## <a name="creating-a-workflow"></a>Criação de um fluxo de trabalho
Para criar um fluxo de trabalho, vá a fluxos de trabalho de compras e &gt; a fonte &gt; de aquisição e da fonte e criar um novo fluxo de trabalho se o tipo de fluxo de trabalho que deseja criar.  

Na tela do fluxo de trabalho, você pode arrastar elementos de fluxo de trabalho para o designer e vincular os elementos a um fluxo. Os elementos de fluxo de trabalho devem ser configurados. Para os elementos do fluxo de trabalho de aprovação e de tarefa, você pode configurar qual participante deverá executar a ação.
Tipos de participantes
----------------------

Você pode atribuir uma etapa de aprovação aos grupos de participantes a seguir.

| Grupo de usuários    | Descrição                                                               |
|---------------|---------------------------------------------------------------------------|
| Participante   | Atribuir a etapa de aprovação aos membros de um grupo ou de uma função.                   |
| Hierarquia     | Atribuir a etapa de aprovação aos usuários em uma hierarquia organizacional específica. |
| Usuário de fluxo de trabalho | Atribuir a etapa de aprovação aos usuários desse fluxo de trabalho.                       |
| Fila         | Atribua a etapa de aprovação em uma fila de itens de trabalho.                            |
| Usuário          | Atribua a etapa de aprovação a usuários específicos.                               |



<a name="see-also"></a>Consulte também
--------

[Definir fluxos de trabalho de processos de negócios para requisições de compra](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[Purchase requisition workflow](purchase-requisitions-workflow.md)


