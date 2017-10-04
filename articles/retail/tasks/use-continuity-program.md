--- 
title: " Usar um programa de continuidade"
description: "Este procedimento aborda a venda de um programa de continuidade e o processamento relacionados às ordens de venda."
author: scott-tucker
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: bd584bbb49ea83c4debf11ad0169c346ef0f9637
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="use-a-continuity-program"></a> Usar um programa de continuidade

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento aborda a venda de um programa de continuidade e o processamento relacionados às ordens de venda. Para concluir o procedimento, o usuário precisa estar configurado como usuário de call center. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e comércio > Clientes > SAC.
2. No campo SearchText, digite "Karen" e depois pressione a tecla Tab.
    * A caixa de diálogo de pesquisa avançada deve aparecer. Caso isso não ocorra, clique em Pesquisa à direita desse campo.  
3. Na lista, marque a linha selecionada.
    * Deve haver apenas uma linha exibindo Karen Berg. Selecione a linha clicando na coluna de marca de seleção na extremidade esquerda da grade.  
4. Clique em Selecionar.
5. Clique em Nova ordem de venda.
    * É recomendável anotar o número da ordem de venda. Você precisará dele posteriormente neste procedimento.  
6. No campo Número de item, digite "88000" e depois pressione a tecla Tab.
    * Trata-se de um item de continuidade nos dados de demonstração da USRT.  
7. Clique em Concluir.
8. No campo Forma de pagamento, insira "Visa".
9. Clique em Adicionar cartão de crédito.
    * Insira as informações de cartão de crédito necessárias nesta página.  
10. Clique em OK.
11. Expandir a seção Pagamento.
    * Para enviar uma ordem de call center, os pagamentos precisam ser inseridos para a ordem.  
12. Clique em OK.
13. Clique em Enviar.
    * Você acabou de criar uma ordem de continuidade. Em seguida, você executará dois processos de lote que serão usados para processar as ordens de continuidade.  
14. Feche a página.
15. Vá para Varejo e comércio > Continuidade > Processar pagamentos de continuidade.
16. No campo Item de continuidade, digite "88000" e depois pressione a tecla Tab.
17. Clique em OK.
18. Vá para Varejo e comércio > Continuidade > Criar ordens filho de continuidade.
    * Esse processo criará ordens de venda com base nas configurações dos seus programas de continuidade.  
19. No campo Item de continuidade, digite "88000" e depois pressione a tecla Tab.
    * O item "88000" é um item de continuidade nos dados de demonstração da USRT.  
20. No campo Ordem de venda, insira ou selecione um valor.
    * Insira o número da ordem de venda que você anotou anteriormente no procedimento. Isso reduzirá o tempo de processamento ao mínimo para este procedimento. O campo Ordem de venda é opcional - você pode processar todas as ordens de qualquer programa.  
21. Clique em OK.

