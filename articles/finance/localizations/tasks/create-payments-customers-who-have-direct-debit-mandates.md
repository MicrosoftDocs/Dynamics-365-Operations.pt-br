---
title: Criar pagamentos para um cliente que tenha cartas de ordem de débito direto
description: Este procedimento exibe como gerar um arquivo de pagamento de débito direito de ISO20022 para clientes com débito direto configurado e fatura a ser paga.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ecc28cb11b8c34a438bb47b1cfa9a37e17297e421020b32030261af95b86a49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757925"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a>Criar pagamentos para um cliente que tenha cartas de ordem de débito direto

[!include [banner](../../includes/banner.md)]

Este procedimento exibe como gerar um arquivo de pagamento de débito direito de ISO20022 para clientes com débito direto configurado e fatura a ser paga. Criar e lançar uma nota fiscal é opcional. Em vez de uma nota fiscal para sê-lo paga pode selecionar uma carta de um ordem em diário antes de gerar um arquivo de pagamento, para oferecer um cenário de pagamento antecipado do cliente.



A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.



Este é o quinto dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico. Para concluir essa tarefa, você deverá concluir tarefas anteriores. Primeiro você deve importar as configurações de relatório eletrônico do pagamento, configurar o método dos pagamentos e definir as informações da empresa e do cliente. 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a>Lançar uma fatura de texto livre com informações de débito direto
1. Acesse Contas recebíveis > Faturas > Todas faturas de texto livre.
2. Clique em Novo.
3. No campo Conta de cliente, insira ou selecione um valor.
    * Por exemplo, selecione DE-010.  
4. No campo Condições de pagamento, insira ou selecione um valor.
    * Por exemplo. selecione Eletrônico.  
5. No campo Carta de ordem de débito direto, insira ou selecione um valor.
6. Clique em Adicionar nova linha.
7. No campo Descrição, digite um valor.
8. No campo Conta principal, especifique os valores desejados.
9. No campo Preço unitário, insira um número.
10. Clique em Lançar.
11. Clique em OK.

## <a name="create-a-payment"></a>Criar um pagamento
1. Acesse Contas a receber > Pagamentos > Diário de pagamentos.
2. Clique em Novo.
3. No campo Nome, insira ou selecione um valor.
4. Clique em Linhas.
5. Clique em Proposta de pagamento.
6. Clique em Criar proposta de pagamento.
7. Expanda os Registros para incluir a seção.
8. Clique em Filtro.
9. Na lista, selecione a linha para a tabela de transações de cliente e o método do pagamento.
    * Você pode aplicar os critérios para selecionar transações de cliente para pagar. Por exemplo, use eletrônico como método de pagamento para filtrar transações.  
10. No campo Critérios, insira ou selecione um valor.
11. Clique em OK.
12. Clique em OK.
13. Clique em Criar pagamentos.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]