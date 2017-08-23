--- 
title: "Criar uma proposta de depreciação"
description: "Este procedimento descreve como as propostas de depreciação em lote funcionam e explica como propor a depreciação para ativos fixos."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ffc358fa7db0ae40fb39d3acdfee7783949f0e1f
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-depreciation-proposal"></a>Criar uma proposta de depreciação

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento descreve como as propostas de depreciação em lote funcionam e explica como propor a depreciação para ativos fixos. A empresa usa essa tarefa de demonstração de USMF e a função de contador.


## <a name="create-depreciation-proposal"></a>Criar proposta de depreciação
1. Ir para Ativos fixos > Entradas de diário > Criar proposta de depreciação.
2. No campo Nome do diário, clique no botão suspenso para abrir a pesquisa.
3. Na lista, clique no link na linha selecionada.
4. No campo Até, insira uma data.
    * Selecione a opção Resumir depreciação para resumir as depreciações mensais em uma linha do diário.  
    * Por exemplo, se o valor "Até" for 31 de março de 2015, a seguinte descrição será gerada: "Depreciação desde 31 de janeiro de 2015." O campo Data nas linhas de diário propostas é então definido para 31 de março de 2015.  
    * A proposta de depreciação pode ser filtrada por ativo, por grupo de ativos, ou por outros critérios usando a opção de filtragem.  
    * Quando você usa a aquisição de criação ou as propostas de depreciação para formulário de ativos fixos, você pode propor a depreciação em lotes. Isso é recomendado para as propostas maiores que usarão mais recursos do sistema. Se você selecionar a opção de lote, você ainda poderá concluir outras tarefas durante esse período. Ao propor a depreciação dessa forma, a depreciação é calculada para os modelos de depreciação para ativos fixos.  
5. Clique em Criar diário.

## <a name="review-depreciation-entries"></a>Entradas de depreciação de revisão
1. Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.
2. Na lista, localize e selecione o PDV desejado.
3. Clique em Linhas.
4. Clique em Lançar.


