---
title: Usando programas de continuidade
description: Este procedimento aborda a venda de um programa de continuidade e o processamento relacionados às ordens de venda.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1de6d2cd88ba31f526621497d6fab36db631933e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232632"
---
# <a name="using-continuity-program"></a>Usando programas de continuidade

[!include [banner](../includes/banner.md)]

Este procedimento aborda a venda de um programa de continuidade e o processamento relacionados às ordens de venda. Para concluir o procedimento, o usuário precisa estar configurado como usuário de call center. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e Comércio > Clientes > SAC.
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
15. Vá para Varejo e Comércio > Continuidade > Processar pagamentos de continuidade.
16. No campo Item de continuidade, digite "88000" e depois pressione a tecla Tab.
17. Clique em OK.
18. Vá para Varejo e Comércio > Continuidade > Criar ordens filho de continuidade.
    * Esse processo criará ordens de venda com base nas configurações dos seus programas de continuidade.  
19. No campo Item de continuidade, digite "88000" e depois pressione a tecla Tab.
    * O item "88000" é um item de continuidade nos dados de demonstração da USRT.  
20. No campo Ordem de venda, insira ou selecione um valor.
    * Insira o número da ordem de venda que você anotou anteriormente no procedimento. Isso reduzirá o tempo de processamento ao mínimo para este procedimento. O campo Ordem de venda é opcional - você pode processar todas as ordens de qualquer programa.  
21. Clique em OK.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]