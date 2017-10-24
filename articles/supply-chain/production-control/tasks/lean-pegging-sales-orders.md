--- 
title: "Vinculação leve de ordens de venda"
description: "Esse procedimento se concentra em validar a árvore de vinculação de uma linha de venda na qual o item é gerado com kanbans."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3aa8cd2c0be56875904158f041cf120c466d9e9a
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="lean-pegging-from-sales-orders"></a>Vinculação leve de ordens de venda

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esse procedimento se concentra em validar a árvore de vinculação de uma linha de venda na qual o item é gerado com kanbans. Após validar a árvore de vinculação, todos os trabalhos kanban são planejados. Isso é útil para os cenários de ordem nos quais o tomador da ordem precisa garantir que possa iniciar a produção imediatamente. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento se destina ao tomador de ordem avançada que trabalha em uma empresa de lean manufacturing.


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a>Crie uma ordem de venda para um item controlado por kanban
1. Ir para Todas as ordens de venda.
2. Clique em Novo.
3. No campo Conta de cliente, insira ou selecione um valor.
    * Usar US-001.  
4. Clique em OK.
5. No campo Número do item, digite 'L0001'.
6. Defina a quantidade como '30'.
    * É importante que a quantidade seja maior do que 24 para disparar a regra kanban de evento.  

## <a name="open-a-pegging-tree"></a>Abra uma árvore de vinculação 
1. Clique em Produtos e fornecimento.
2. Clique em Exibir árvore de vinculação.
    * Observe que a árvore de vinculação mostra todos os níveis de vinculação necessários para a linha da ordem de venda. Nesse caso, há dois níveis de kanbans e todos os componentes necessários.  

## <a name="plan-the-pegging-tree"></a>Planeje a árvore de vinculação
1. Na árvore, selecione a linha de venda 000832\Kanban 000558'.
2. Expanda a seção trabalhos Kanban.
    * Observe que o status do trabalho para o trabalho kanban é Não planejado.  
3. Clique em Planejar toda a árvore de vinculação.
    * Isso planejará todos os trabalhos kanban na árvore de vinculação, alterando o status do trabalho de não planejado para planejado.  
4. Atualize a página.
    * Observe que o status do trabalho kanban foi alterado de Não planejado para Planejado.  
5. Na árvore, selecione 'Linha de venda 000832\Kanban 000558\Saída para L0001\Kanban 000559'.
    * O trabalho para o segundo kanban também é planejado porque a árvore inteira de vinculação é planejada. Observe que o status do trabalho kanban é alterado de Não planejado para Planejado.  


