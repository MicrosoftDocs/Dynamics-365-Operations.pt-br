---
title: Criar uma regra kanban para atividades múltiplas
description: Este procedimento mostra como criar uma regra kanban que inclua atividades múltiplas de um fluxo da produção.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 828b01fbb3b94b1fcb9fe8a565b1191a4f4bf630
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829105"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>Criar uma regra kanban para atividades múltiplas

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar uma regra kanban que inclua atividades múltiplas de um fluxo da produção. A empresa de dados demo usada para criar esta tarefa é USMF. Esta tarefa destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado em um ambiente de lean.


## <a name="create-a-new-kanban-rule"></a>Criar uma nova regra kanban
1. Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.
2. Clique em Novo.
3. No campo Estratégia de reabastecimento, selecione 'Programado'.
4. No campo Primeira atividade do plano, insira ou selecione um valor.
    * Selecione SpeakerAssemblyAndPolish.  
5. Selecione a caixa de verificação múltipla das atividades.
    * O objetivo é incluir mais que uma atividade na regra kanban. Você escolhe um trajeto no fluxo da produção quando você seleciona a última atividade do plano.  
6. No campo Última atividade do plano, insira ou selecione um valor.
    * Selecione SpeakerTestAndPackaging. Depois que você seleciona o valor, uma página abre automaticamente. Selecione o fluxo kanban SpeakerAssemblyAndPolish > SpeakerTestAndPackaging. Clique em OK.  
7. Expanda a seção Detalhes.
8. No campo Produto, insira ou selecione um valor.
    * Selecione o item L0006.  

## <a name="create-kanban-and-view-jobs"></a>Criar um kanban e ver trabalhos
1. Expanda a seção kanbans.
2. Clique em Adicionar.
3. No campo Número de novos kanbans, insira '1'.
    * Isso criará um kanban.  
4. Defina Quantidade de produto para '3'.
    * Kanban processará 3 produtos.  
5. No campo Data/hora de vencimento, insira uma data e hora.
    * Você pode inserir Hoje.  
6. Clique em Criar.
7. Clique em Detalhes.
    * Observe que o kanban tem dois trabalhos do processo do fluxo da produção. O primeiro é SpeakerAssemblyAndPolish, e o segundo é SpeakerTestAndPackaging.  
    * Esta é a última etapa!  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]