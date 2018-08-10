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
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 07d8cf2f1c46b99dfcd1d7c3419fe835f37c5a02
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-depreciation-proposal"></a>Criar uma proposta de depreciação

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


