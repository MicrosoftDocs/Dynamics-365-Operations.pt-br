---
title: Relatórios de despesas e vários aprovadores
description: Este tópico fornece informações sobre os relatórios de despesas que exigem aprovação por mais de uma pessoa.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d83a473e2e894856c12b36b4d005c6cb06b765a
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2019
ms.locfileid: "1795115"
---
# <a name="expense-reports-and-multiple-approvers"></a>Relatórios de despesas e vários aprovadores

[!include [banner](../includes/banner.md)]

Dependendo das políticas de aprovação de despesas da sua organização, talvez seja necessário que mais de uma pessoa aprove um relatório de despesas enviado por um funcionário. Ao configurar o processo de fluxo de trabalho para a aprovação do relatório de despesas, você poderá adicionar os elementos do fluxo de trabalho que incluem tarefas ou etapas para um ou mais aprovadores de relatório de despesas. Por exemplo, você pode exigir que todos os relatórios de despesas sejam aprovados primeiro pelo gerente do funcionário que enviou o relatório e, em seguida, pelo coordenador de contas a pagar.

Se você decidir exigir vários aprovadores do relatório de despesas, você pode adicionar os elementos do fluxo de trabalho em qualquer uma das seguintes maneiras:

- Adicionar um elemento de aprovação que tenha uma etapa. Por exemplo, a etapa pode exigir que um relatório de despesas seja atribuído a um grupo de usuários e que seja aprovado por 50% dos seus membros.
- Adicionar um elemento de aprovação que tenha várias etapas. Por exemplo, o elemento de aprovação pode ter as seguintes etapas:

    1. O gerente do funcionário que enviou o relatório de despesas aprová-lo.
    2. O funcionário de contas a pagar verificar os recibos e os itens do relatório de despesas.
    3. O proprietário de orçamento aprovar o relatório de despesas.

- Adicionar vários elementos de aprovação, cada um com uma etapa. Por exemplo, você pode adicionar um elemento de aprovação separado para cada uma das seguintes etapas:

    1. O gerente do funcionário aprovar o relatório de despesas.
    2. O proprietário de orçamento aprovar o relatório de despesas.
