---
title: Corrigir informações de rastreamento de estoque
description: Este procedimento apresenta o processo de criação e lançamento de um diário de transferência de estoque para corrigir informações de rastreamento de estoque.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69921651ecd0969e9cdd3cdd3740db212a1953e1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573792"
---
# <a name="correct-inventory-tracking-information"></a>Corrigir informações de rastreamento de estoque

[!include [banner](../../includes/banner.md)]

Este procedimento apresenta o processo de criação e lançamento de um diário de transferência de estoque para corrigir informações de rastreamento de estoque. Neste exemplo, vamos atualizar as informações de um item controlado por lote alterando um lote registrado incorretamente em outro lote. Você pode ver todo esse procedimento na empresa de dados de demonstração USPI, ou usando seus próprios dados. Se você usar seus próprios dados, precisará ter um item habilitado por lote, e não deve ser controlado por localização. Você também precisa ter um nome do diário de estoque configurado para transferências de estoque. Essas tarefas normalmente seriam realizadas por um funcionário do depósito.


## <a name="create-an-inventory-transfer-journal"></a>Criar um diário de transferência de estoque
1. Acesse Transferência.
2. Clique em Novo.
3. No campo Nome, insira ou selecione um valor.
4. Clique em OK.

## <a name="create-journal-lines"></a>Criar linhas de diário
1. Clique em Novo.
2. No campo Número do item, insira ou selecione um valor.
    * Se você estiver usando o USPI, selecione o item M5003.  
3. No campo Quantidade, insira um número.
4. Clique na guia Dimensões de estoque.
5. No campo Número do lote, insira ou selecione um valor.
6. No campo Local, insira ou selecione um valor.
7. No campo Depósito, insira ou selecione um valor.
8. No campo Número do lote, insira ou selecione um valor.

## <a name="post-the-journal"></a>Lançar o diário
1. Clique em Lançar.
2. Clique em OK.

## <a name="check-tracing-information"></a>Verifique as informações de rastreamento
1. Clique em Estoque.
2. Clique em Rastrear.
3. Clique em OK.
    * Usando estas informações você pode rastrear novamente qual lote você corrigiu do estoque.  Você também pode usar a página de rastreamento do item para consultar essas informações.  
4. Feche a página.

## <a name="check-inventory-transactions"></a>Verifique as transações de estoque
1. Clique em Estoque.
2. Clique em Transações.
    * Aqui é possível ver as transações que foram criadas quando você lançou seu diário.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]