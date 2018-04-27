--- 
title: "Visão geral de pagamentos do cliente"
description: "Este guia de tarefas apresenta vários métodos utilizados para inserir pagamentos de clientes."
author: kweekley
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 621ad64c06a6cebff90e888ac89bba922052cf35
ms.openlocfilehash: de2526d5c674de9505174d3f40f9ae597b8a0a6b
ms.contentlocale: pt-br
ms.lasthandoff: 10/26/2017

---
# <a name="customer-payment-overview"></a>Visão geral de pagamentos do cliente

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este guia de tarefas apresenta vários métodos utilizados para inserir pagamentos de clientes. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contas a receber > Pagamentos > Diário de pagamentos.
2. Clique em Novo.
3. Selecione o diário de pagamentos onde os pagamentos do cliente serão salvos.
4. Selecione ou insira manualmente o diário.
5. Clique em Inserir pagamentos de cliente.
    * Inserir pagamentos de cliente é usado para registrar um pagamento de cliente por vez. Você insere as informações de pagamento na parte superior e, em seguida, pode marcar as faturas que foram pagas por este pagamento, todas da mesma página.  
6. Insira o cliente do qual o pagamento foi recebido.
    * Se você não sabe qual é o cliente mas tem informações de uma transação que foi paga, pode usar o campo Transação para inserir o pagamento. Insira ou selecione a fatura no campo Transação. O cliente será inserido automaticamente depois que você selecionar a transação.  
7. No campo Referência de pagamento, insira uma referência de pagamento.
    * A referência do pagamento pode ser o número do cheque do cliente ou uma referência do pagamento eletrônico do cliente. A referência do pagamento é necessária somente se você marcar para incluir o pagamento em uma guia de depósito.  
8. Selecione se o pagamento será incluído em uma guia de depósito. 
9. Insira o valor do pagamento do cliente.
    * O valor do pagamento não será inserido automaticamente. Ele deve ser inserido manualmente.  
10. Marque as faturas que foram pagas pelo cliente.
    * Se este for um pagamento antecipado, não é necessário marcar nenhuma fatura para liquidação. O pagamento ainda pode ser salvo e lançado. A liquidação de uma fatura pode ocorrer posteriormente.  
11. Insira o valor do pagamento que deve ser liquidado à fatura marcada. 
    * Este campo pode ser usado quando o pagamento for para um pagamento parcial. Se você não inserir um valor, o valor a ser liquidado será definido automaticamente para você.  
12. Clique em Salvar no diário.
    * Antes de salvar o pagamento no diário, verifique se a contrapartida está definida. Se você usar Salvar no diário, o pagamento será salvo e movido para o diário. Você pode, em seguida, continuar inserindo o próximo pagamento.  
13. Feche a página.
14. Clique em Linhas.
    * Quando você abrir Linhas, verá todos os pagamentos que foram registrados na página Inserir pagamentos de cliente e salvos no diário. Você também pode usar essa página para inserir novos pagamentos de cliente ou editar os pagamentos de cliente existentes antes que eles sejam lançados.  
15. Clique em Novo para criar um outro pagamento. 
16. Selecione o cliente do qual o pagamento foi recebido.
    * Se você não sabe qual é o cliente mas tem as informações de uma fatura paga por este pagamento, use o campo Fatura para inserir manualmente ou selecionar a fatura. O cliente será definido como o padrão após a seleção da fatura.  
17. Clique em Liquidar transações para marcar as faturas que foram pagas.
    * Não é necessário liquidar o pagamento de nenhuma fatura. Se este for um pagamento antecipado ou se você não souber qual fatura foi paga, você poderá inserir e lançar o pagamento. O pagamento pode ser liquidado em uma fatura posteriormente.  
18. Marque as faturas pagas por este pagamento. 
19. Insira o valor do pagamento que será liquidado à fatura.
20. Clique em OK.
21. No campo Referência de pagamento, insira uma referência de pagamento. .
    * A referência do pagamento é necessária somente se você marcar para incluir o pagamento em uma guia de depósito.  
22. Lance os pagamentos do cliente. 


