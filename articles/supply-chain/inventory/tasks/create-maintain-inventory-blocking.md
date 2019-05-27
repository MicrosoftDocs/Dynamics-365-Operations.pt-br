---
title: Criar e manter um bloqueio de estoque
description: Este procedimento mostra como evitar que o estoque físico disponível seja reservado para outros documentos de origem de saída usando o bloqueio de estoque.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09789dc0b89f8bd36cca9b3e5be366bf17246243
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549762"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Criar e manter um bloqueio de estoque

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como evitar que o estoque físico disponível seja reservado para outros documentos de origem de saída usando o bloqueio de estoque. Você pode executar o procedimento na empresa USMF de dados de demonstração usando os valores de exemplo mostrados. Você precisa ter um item do estoque físico disponível antes de iniciar este procedimento.


## <a name="create-an-inventory-blocking"></a>Criar um bloqueio de estoque
1. Vá para Gerenciamento de estoque > Tarefas periódicas > Bloqueio de estoque.
2. Clique em Novo.
3. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
4. Na lista, selecione o item que deseja escolher. 
    * Selecione um número de item com estoque físico disponível que você deseja bloquear. Se você estiver usando USMF, você pode o item M9201.  
5. No campo Quantidade, insira um número.
    * Se você estiver usando o item M9201, você precisará selecionar menos de 200.  
6. Ative a expansão da seção Dimensões de estoque.
7. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
8. Na lista, localize e selecione o PDV desejado.
    * Se você estiver usando o item M9201, você pode selecionar o depósito 51.  
9. Clique em Salvar.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Atualizar as condições de bloqueio de estoque
1. No campo Quantidade, insira um número.
    * Atualize o campo de quantidade em estoque para refletir a quantidade para bloquear.  
2. No campo Data estimada, insira uma data.
    * Você pode desejar indicar quando o estoque bloqueado deve ficar disponível para reserva atribuindo uma data esperada. Se a opção esperada de recebimentos é marcada para o bloqueio de estoque, como é por padrão ao criar manualmente um bloqueio, essa data será exibida na transação esperada.  
3. Clique em Salvar.

## <a name="remove-the-inventory-blocking"></a>Remover o bloqueio de estoque
1. Clique em Excluir.
2. Clique em Sim.
3. Feche a página.

