---
title: Criar uma proposta de depreciação
description: Este artigo descreve como as propostas de depreciação em lote funcionam e explica como propor a depreciação para ativos fixos.
author: abruer
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1f39a1412c6f96fe0a8261602a88a6a3c3cd6b8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858486"
---
# <a name="create-a-depreciation-proposal"></a>Criar uma proposta de depreciação

[!include [banner](../../includes/banner.md)]

Este artigo descreve como as propostas de depreciação em lote funcionam e explica como propor a depreciação para ativos fixos. A empresa usa essa tarefa de demonstração de USMF e a função de contador.


## <a name="create-a-depreciation-proposal"></a>Criar uma proposta de depreciação
1. No Painel de Navegação, Acesse **Ativos fixos > Entradas de diário > Criar proposta de depreciação**.
2. No campo **Nome do diário**, selecione uma opção no menu suspenso.
3. No campo **Data final**, insira uma data.

    - Selecione a opção **Resumir depreciação** para resumir as depreciações mensais em uma linha do diário.  
    - Por exemplo, se o valor "Até" for 31 de março de 2015, a seguinte descrição será gerada: "Depreciação desde 31 de janeiro de 2015." O campo **Data** nas linhas de diário propostas é então definido para 31 de março de 2015.  
    - A proposta de depreciação pode ser filtrada por ativo, por grupo de ativos, ou por outros critérios usando a opção **Filtrar**.  
    - Ao usar o formulário **Criar propostas de aquisição ou depreciação para ativos fixos**, é possível propor a depreciação em lotes. Isso é recomendado para as propostas maiores que usarão mais recursos do sistema. Se você selecionar a opção de lote, você ainda poderá concluir outras tarefas durante esse período. Ao propor a depreciação dessa forma, a depreciação é calculada para os modelos de depreciação para ativos fixos.  

4. Selecione **Criar diário**.

## <a name="review-depreciation-entries"></a>Entradas de depreciação de revisão
1. No Painel de navegação, Acesse **Módulos > Ativos fixos > Entradas de diário > Diário de ativos fixos**.
2. Na lista, localize e selecione o registro desejado.
3. Selecione **Linhas**.
4. Selecione **Lançar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
