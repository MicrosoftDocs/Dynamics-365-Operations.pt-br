---
title: Visão geral de pagamentos de cliente
description: Este procedimento orienta por vários métodos utilizados para inserir pagamentos de clientes.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7b90b7f200133cfb0d30b335aca20c328856fba5
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778113"
---
# <a name="customer-payment-overview"></a>Visão geral de pagamentos de cliente

[!include [banner](../../includes/banner.md)]

Este procedimento orienta por vários métodos utilizados para inserir pagamentos de clientes. Esta tarefa usa a empresa de demonstração USMF.

1. Acesse **Painel de Navegação > Módulos > Contas a receber > Pagamentos > Diário de pagamentos**.
2. Clique em **Novo**.
3. Selecione o diário de pagamentos onde os pagamentos do cliente serão salvos.
4. Selecione ou insira manualmente o diário.
5. No **Painel de Ação**, clique em **Inserir pagamentos de cliente**. Inserir pagamentos de cliente é usado para registrar um pagamento de cliente por vez. Você insere as informações de pagamento na parte superior e, em seguida, pode marcar as faturas que foram pagas por este pagamento, todas da mesma página.  
6. Insira o cliente do qual o pagamento foi recebido. Se você não sabe qual é o cliente mas tem informações de uma transação que foi paga, pode usar o campo **Transação** para inserir o pagamento. Insira ou selecione a fatura no campo **Transação**. O cliente será inserido automaticamente depois que você selecionar a transação.
7. No campo **Referência de pagamento**, insira uma referência de pagamento. A referência do pagamento pode ser o número do cheque do cliente ou uma referência do pagamento eletrônico do cliente. A referência do pagamento é necessária somente se você marcar para incluir o pagamento em uma guia de depósito.  
8. No campo **Guia de depósito**, selecione se o pagamento será incluído em uma guia de depósito. 
9. No campo **Valor**, insira o valor do pagamento do cliente. O valor do pagamento não será inserido automaticamente. Ele deve ser inserido manualmente. 
10. Marque as faturas que foram pagas pelo cliente. Se este for um pagamento antecipado, não é necessário marcar nenhuma fatura para liquidação. O pagamento ainda pode ser salvo e lançado. A liquidação de uma fatura pode ocorrer posteriormente.
11. Insira o valor do pagamento que deve ser liquidado à fatura marcada. Este campo pode ser usado quando o pagamento for para um pagamento parcial. Se você não inserir um valor, o valor a ser liquidado será definido automaticamente para você.
12. Clique em **Salvar no diário**. Antes de salvar o pagamento no diário, verifique se a contrapartida está definida. Se você usar **Salvar no diário**, o pagamento será salvo e movido para o diário. Você pode, em seguida, continuar inserindo o próximo pagamento.
13. Feche a página.
14. No **Painel de ação**, clique em **Linhas**. Quando você abrir **Linhas**, verá todos os pagamentos registrados na página **Inserir pagamentos de cliente** e salvos no diário. Você também pode usar essa página para inserir novos pagamentos de cliente ou editar os pagamentos de cliente existentes antes que eles sejam lançados.
15. Clique em **Novo** para criar um outro pagamento. 
16. Selecione o cliente do qual o pagamento foi recebido. Se você não sabe qual é o cliente mas tem as informações de uma fatura paga por este pagamento, use o campo **Fatura** para inserir manualmente ou selecionar a fatura. O cliente será definido como o padrão após a seleção da fatura.  
17. Clique em **Liquidar transações** para marcar as faturas que foram pagas. Não é necessário liquidar o pagamento de nenhuma fatura. Se este for um pagamento antecipado ou se você não souber qual fatura foi paga, você poderá inserir e lançar o pagamento. O pagamento pode ser liquidado em uma fatura posteriormente.  
18. Marque as faturas pagas por este pagamento. 
19. No campo **Valor**, insira o valor do pagamento que será liquidado para a fatura.
20. Clique em **OK**.
21. No campo **Referência de pagamento**, insira uma referência de pagamento. A referência do pagamento é necessária somente se você marcar para incluir o pagamento em uma guia de depósito.  
22. No **Painel de Ação**, clique em **Lançar** para lançar os pagamentos do cliente. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
