---
title: Configurar fluxos de trabalho para despesa
description: "Você pode configurar um processo de fluxo de trabalho que é usado para revisar e aprovar documentos viagem e despesas."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: cf35406b43c1ec40a7c248b970559b65fcd8a6c6
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-workflows-for-expense"></a>Configurar fluxos de trabalho para despesa

[!include [banner](../includes/banner.md)]

 Você pode configurar um processo de fluxo de trabalho que é usado para revisar e aprovar documentos viagem e despesas. Os documentos para os quais os fluxos de trabalho podem ser definidos incluem os relatórios de despesas, requisições de viagem e solicitações de adiantamento de dinheiro.

Um fluxo de trabalho representa um processo comercial. Ele define como um documento flui pelo sistema e indica quem deve concluir uma tarefa ou aprovar um documento. O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:

-   **Processos consistentes** — você pode definir o processo de aprovação de documentos específicos, como requisições de compra e relatórios de despesas. O uso desse sistema ajuda a garantir que os documentos sejam processados e aprovados de maneira consistente e eficiente.

-   Visibilidade do processo — você pode rastrear o status, o histórico e as métricas de desempenho de uma instância específica do fluxo de trabalho. Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.

-   Lista de trabalho centralizada — os usuários podem exibir uma lista de trabalho centralizada para ver as tarefas do Fluxo de Trabalho e as aprovações atribuídas a elas. 

**Os tipos de fluxo de trabalho que você pode criar**

A tabela a seguir lista os tipos de fluxos de trabalho que podem ser criados em **Despesa**.


|              <strong>Tipo</strong>              |                   <strong>Use este tipo para</strong>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <strong>Relatório de Despesas</strong>         |            Criar fluxos de trabalho de aprovação para relatórios de despesas.             |
|  <strong>Lançamento automático de relatório de despesas</strong>   |        Criar fluxos de trabalho de lançamento automático para relatórios de despesas.        |
|       <strong>Item de linha de despesa</strong>        |     Criar fluxos de trabalho de aprovação para itens de linha em relatórios de despesa.      |
| <strong>Lançamento automático de itens de linha de despesa</strong> | Criar fluxos de trabalho de lançamento automático para itens de linha em relatórios de despesa. |
|       <strong>Requisição de viagem</strong>       |          Criar fluxos de trabalho de aprovação para requisições de viagem.           |
|      <strong>Solicitação de adiantamento de dinheiro</strong>      |         Criar fluxos de trabalho de aprovação das solicitações de adiantamento em dinheiro.          |
|        <strong>Restituição de imposto IVA</strong>        | Criar fluxos de trabalho de aprovação para a recuperação de imposto sobre valor agregado (VAT).  |


