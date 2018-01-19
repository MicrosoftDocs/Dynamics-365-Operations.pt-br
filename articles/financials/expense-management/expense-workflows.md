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
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 19d725f15f00afce1a2ae4b336226f1dafa94b41
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-workflows-for-expense"></a>Configurar fluxos de trabalho para despesa

[!include[banner](../includes/banner.md)] Você pode configurar um processo de fluxo de trabalho que é usado para revisar e aprovar documentos viagem e despesas. Os documentos para os quais os fluxos de trabalho podem ser definidos incluem os relatórios de despesas, requisições de viagem e solicitações de adiantamento de dinheiro.

Um fluxo de trabalho representa um processo comercial. Ele define como um documento flui pelo sistema e indica quem deve concluir uma tarefa ou aprovar um documento. O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:

-   **Processos consistentes** — você pode definir o processo de aprovação de documentos específicos, como requisições de compra e relatórios de despesas. O uso desse sistema ajuda a garantir que os documentos sejam processados e aprovados de maneira consistente e eficiente.

-   Visibilidade do processo — você pode rastrear o status, o histórico e as métricas de desempenho de uma instância específica do fluxo de trabalho. Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.

-   Lista de trabalho centralizada — os usuários podem exibir uma lista de trabalho centralizada para ver as tarefas do Fluxo de Trabalho e as aprovações atribuídas a elas. 

**Os tipos de fluxo de trabalho que você pode criar**

A tabela a seguir lista os tipos de fluxos de trabalho que podem ser criados em **Despesa**.

| **Tipo**                           | **Use este tipo para**                                                 |     
|------------------------------------|----------------------------------------------------------------------|
| **Relatório de Despesas**                 | Criar fluxos de trabalho de aprovação para relatórios de despesas.                       |      
| **Lançamento automático de relatório de despesas**    | Criar fluxos de trabalho de lançamento automático para relatórios de despesas.              |     
| **Item de linha de despesa**              | Criar fluxos de trabalho de aprovação para itens de linha em relatórios de despesa.         |     
| **Lançamento automático de itens de linha de despesa** | Criar fluxos de trabalho de lançamento automático para itens de linha em relatórios de despesa.|
| **Requisição de viagem**             | Criar fluxos de trabalho de aprovação para requisições de viagem.                   |    
| **Solicitação de adiantamento de dinheiro**           | Criar fluxos de trabalho de aprovação das solicitações de adiantamento em dinheiro.                 |     
| **Restituição de imposto IVA**               | Criar fluxos de trabalho de aprovação para a recuperação de imposto sobre valor agregado (VAT). |       

