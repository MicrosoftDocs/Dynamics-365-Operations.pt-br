---
title: Fluxos de trabalho de Compras
description: "Algumas organizações exigem que as requisições de compra e as ordens de compra sejam aprovadas por um usuário diferente daquele que iniciou a transação. Para configurar um processo de aprovação, você pode criar um fluxo de trabalho."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 75daeed0d0e979165d3669e83e98cf278d7fb736
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="procurement-and-sourcing-workflows"></a>Fluxos de trabalho de compras

[!include [banner](../includes/banner.md)]

Algumas organizações exigem que as requisições de compra e as ordens de compra sejam aprovadas por um usuário diferente daquele que iniciou a transação. Para configurar um processo de aprovação, você pode criar um fluxo de trabalho.

Um fluxo de trabalho representa um processo comercial. Ele define como um documento flui pelo sistema e indica quem deve concluir uma tarefa ou aprovar um documento. O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:
-   **Processos consistentes** — você pode definir o processo de aprovação de documentos específicos, como requisições de compra e relatórios de despesas. O uso desse sistema ajuda a garantir que os documentos sejam processados e aprovados de maneira consistente e eficiente.
-   **Visibilidade do processo** — você pode rastrear o status, o histórico e as métricas de desempenho de uma instância específica do fluxo de trabalho. Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.
-   **Lista de trabalho centralizada** — os usuários podem exibir uma lista de trabalho centralizada para exibir as tarefas do fluxo de trabalho e as aprovações atribuídas a eles em todos os fluxos de trabalho de que participam. Isso está disponível na página Itens de trabalho.

## <a name="the-types-of-workflows-that-you-can-create"></a>Os tipos de fluxo de trabalho que você pode criar
Os tipos de fluxo de trabalho a seguir estão disponíveis para Compras.

|                                  |                                                               |
|----------------------------------|---------------------------------------------------------------|
| **Tipo**                         | **Use este tipo para**                                          |
| Revisão da requisição de compra      | Criar fluxos de trabalho de aprovação e revisão para requisições de compra.            |
| Revisão de linha de requisição de compra | Criar fluxos de trabalho de revisão e aprovação para linhas de requisição de compra.       |
| Fluxo de trabalho da ordem de compra          | Criar fluxos de trabalho de revisão e aprovação para ordens de compra.     |
| Fluxo de trabalho da linha da ordem de compra     | Criar fluxos de trabalho de revisão e aprovação para linhas de ordens de compra. |
| Fluxo de trabalho da solicitação de emprego adicionada pelo fornecedor  | Criar fluxos de trabalho da revisão e de aprovação para adicionar novos fornecedores por meio de solicitações de fornecedor. |

## <a name="creating-a-workflow"></a>Criação de um fluxo de trabalho
Para criar um fluxo de trabalho, vá para Compras &gt; Configuração &gt; Fluxos de trabalho de compras e crie um novo fluxo de trabalho ao selecionar o tipo de fluxo de trabalho que deseja criar.  

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



<a name="additional-resources"></a>Recursos adicionais
--------

[Definir fluxos de trabalho de processos de negócios para requisições de compra](https://mbs.microsoft.com/customersource/Global/AX/learning/documentation/white-papers/Defining_business_process_workflows_for_purchase_requisitions)

[Fluxo de trabalho de requisição de compra](purchase-requisitions-workflow.md)

[Integração de fornecedores](vendor-onboarding.md)


