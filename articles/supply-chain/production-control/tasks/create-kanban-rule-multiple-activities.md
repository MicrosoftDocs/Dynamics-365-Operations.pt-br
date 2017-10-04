--- 
title: "Criar uma regra kanban para atividades múltiplas"
description: "Este procedimento mostra como criar uma regra kanban que inclua atividades múltiplas de um fluxo da produção."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 5b4c6f919072dd6497b0eab548077f68fc46dbf5
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-kanban-rule-for-multiple-activities"></a>Criar uma regra kanban para atividades múltiplas

[!include[task guide banner](../../includes/task-guide-banner.md)]

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

