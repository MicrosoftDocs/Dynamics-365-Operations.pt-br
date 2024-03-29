---
title: Fechar a contabilidade ao final do período
description: Este artigo descreve as tarefas geralmente concluídas durante a realização de um fechamento periódico de contabilidade.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42a5df1cd1a73462c93012b26f9b9b5c1631f2ce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878031"
---
# <a name="close-the-general-ledger-at-period-end"></a>Fechar a contabilidade ao final do período

[!include [banner](../includes/banner.md)]

Este artigo descreve as tarefas geralmente concluídas durante a realização de um fechamento periódico de contabilidade. 

Na contabilidade, é possível concluir os procedimentos de fechamento por um período ou por um ano. Os processos de fechamento preparam o sistema para um novo período. Para se preparar para um novo ano, você deve executar o processo do fechamento de final de ano. Cada organização possui processos e etapas diferentes que ela executa para o final de um período. Veja a seguir algumas etapas opcionais para o fim do período:

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

O espaço de trabalho de **fechamento de período financeiro** pode ser usado para organizar e controlar as tarefas necessárias para diversos processos de fechamento de período. 


Para obter mais informações, consulte os seguintes tópicos:
- [Espaço de trabalho de fechamento do período financeiro](financial-period-close-workspace.md) 
- [​Fechamento do exercício​](Year-end-close.md)  
- [Fechamento em massa do período financeiro](tasks/mass-financial-period-close.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
