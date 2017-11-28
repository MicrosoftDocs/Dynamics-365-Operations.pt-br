---
title: "Fechar a contabilidade no fim do período"
description: "Este tópico descreve as tarefas geralmente concluídas durante a realização de um fechamento periódico de contabilidade."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5643a06cb23eedd7c8676ad48be2ad2e78cdfc9b
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="close-the-general-ledger-at-period-end"></a>Fechar a contabilidade no fim do período

[!include[banner](../includes/banner.md)]


Este tópico descreve as tarefas geralmente concluídas durante a realização de um fechamento periódico de contabilidade. 

Na contabilidade, é possível concluir os procedimentos de fechamento por um período ou por um ano. Os processos de fechamento preparam o sistema para um novo período. Para preparar o sistema para um novo ano, você deve executar o processo do fechamento de final de ano. Cada organização possui processos e etapas diferentes que ela executa para o final de um período. Veja a seguir algumas etapas opcionais para o fim do período:

-   Conclua todas as tarefas para todos os outros módulos, como Contas a receber, Contas a pagar e Inventário.
-   Verifique se todo todos os diários foram lançados.
-   Execute a reavaliação de moeda estrangeira para gerar um lucro não realizado ou valores de perda.
-   Liquide transações para cada conta contábil.
-   Processe as alocações necessárias.
-   Lançar manualmente ajustes de fim de período.Realize ajustes manuais após o período.
-   Lance transações e revise o relatório **diário do razão**.
-   Realize a consolidação usando uma empresa de consolidação ou de relatórios financeiros.
-   Gere o demonstrativo financeiro do final do período usando o relatório financeiro.
-   Defina períodos do razão para **Em espera**, de modo que não haja novos lançamentos. Também é possível restringir um período para um grupo de usuários específico durante as atividades de fim de período, para um melhor controle. Não é recomendável definir períodos para **Fechado de forma permanente**, pois não é possível reabrir um período que foi fechado.

O espaço de trabalho financeiro de fechamento de período pode ser usado para organizar e controlar as tarefas necessárias para diversos processos de fechamento de período. 


Para obter mais informações, consulte os seguintes tópicos:
- [Espaço de trabalho de fechamento do período financeiro](financial-period-close-workspace.md) 
- [Fechamento do exercício](Year-end-close.md)  
- [Fechamento em massa do período financeiro](tasks/mass-financial-period-close.md)





