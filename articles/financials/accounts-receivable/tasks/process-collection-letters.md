--- 
title: "Processar cartas de cobrança"
description: "Este procedimento mostra como criar, imprimir e lançar cartas de cobrança."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="process-collection-letters"></a>Processar cartas de cobrança

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar, imprimir e lançar cartas de cobrança. Esta tarefa usa a empresa de demonstração USMF.


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Configurar uma sequência de carta de cobrança no perfil de lançamento
1. Vá para Crédito e coleções > Configuração > Perfis de lançamento de cliente.
2. Clique em Editar.
    * Selecione uma sequência de carta de cobrança na lista suspensa. Se você não quiser gerar cartas de cobrança para transações usando este perfil de lançamento, deixe o campo em branco.  
    * A guia de restrição de tabela permite que você altere a forma que as cartas de cobrança são processadas. Se este campo estiver definido como Sim, as cartas de cobrança serão criadas para este perfil de lançamento.  
3. Feche a página.

## <a name="create-collection-letters"></a>Criar cartas de cobrança
1. Vá para Crédito e cobranças > Carta de cobrança > Criar cartas de cobrança.
    * Você deve selecionar os tipos de transação para os quais cobrará as cartas. Todas as transações abertas para esses tipos serão incluídas no cálculo.  
2. No campo Carta de coleção, selecione uma opção.
3. Insira a data da carta de cobrança.
    * Há duas opções de perfil de lançamento: Conta – use o perfil de lançamento que é atribuído à conta do cliente para cada nota de juros.   Seleção - use o perfil de lançamento selecionado no campo Perfil de lançamento.  
    * Selecione um perfil de lançamentos, se você modificou "Usar um perfil de lançamento de" para "Selecionar".  
4. Expanda os Registros para incluir a seção.
5. Clique em Filtro.
6. No campo Critérios, insira um ID do Cliente. Por exemplo, insira 'US-001'.
7. Clique em OK.
8. Clique em OK.

## <a name="print-collection-letters"></a>Imprimir cartas de cobrança
1. Vá para Crédito e cobranças > Carta de cobrança > Revisar e processar cartas de cobrança.
2. No campo Status, selecione 'Criado'.
3. No campo Impresso, selecione 'Não impresso'.
4. Clique em Imprimir.
5. Clique em Nota de carta de cobrança.
6. Expanda os Registros para incluir a seção.
7. Insira a data de fechamento para lançamentos
8. Clique em OK para imprimir a carta de cobrança.

## <a name="post-the-collection-letter"></a>Lança a carta de cobrança
1. Clique em Lançar.
2. Inserir a nova data de lançamento para a carta de cobrança.
3. Expanda os Registros para incluir a seção.
4. Clique em OK.
5. No campo Status, selecione 'Lançado'.
6. No campo Impresso, selecione uma opção.


