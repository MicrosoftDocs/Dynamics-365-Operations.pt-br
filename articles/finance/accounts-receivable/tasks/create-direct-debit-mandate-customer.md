---
title: Criar um mandato de débito direto para um cliente
description: Essa guia de tarefa demonstra como criar uma carta da ordem de débito direto e usá-la em uma nota fiscal.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f746da0bcf2b1e0cb09af6b5e2ea61938213c924
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991033"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Criar um mandato de débito direto para um cliente

[!include [banner](../../includes/banner.md)]

Essa guia de tarefa demonstra como criar uma carta da ordem de débito direto e usá-la em uma nota fiscal.


## <a name="create-a-bank-account"></a>Criar uma conta bancária
1. No **Painel de Navegação**, vá para **Módulos > Contas a receber > Clientes > Todos os clientes**.
2. Na lista, selecione um registro. Por exemplo, selecione US-001
3. No Painel de Ações, clique em **Cliente**.
4. Clique em **Contas bancárias**.
5. Clique em **Novo**.
6. No campo **Conta bancária**, digite um valor.
7. No campo **Nome**, digite um valor.
8. No campo **IBAN**, digite um valor.
9. No campo **Moeda**, digite um valor.
10. Clique em **Salvar**.
11. Feche a página.
12. No **Painel de Navegação**, vá para **Módulos > Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias**.
13. Na lista, localize e selecione o registro desejado.
14. Na lista, clique no link na linha selecionada.
15. Clique em **Editar**.
16. Expanda a Guia Rápida **Identificação adicional**.
17. No campo **ID do Débito Direto**, digite um valor.
18. No campo **IBAN**, digite um valor.
19. Feche a página.
20. Feche a página.

## <a name="define-the-electronic-payment-method"></a>Definir o método de pagamento eletrônico
1. No **Painel de Navegação**, vá para **Módulos > Contas a receber > Configuração de pagamentos > Formas de pagamento**.
2. Clique em **Novo**.
3. No campo **Método de pagamento**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. No campo **Tipo de liquidação**, insira "Pagamento eletrônico". O tipo de pagamento para um método de carta da ordem de débito direto do pagamento deve ser pagamento eletrônico.
6. Selecione Sim no campo **Solicitação obrigatório**.
7. Feche a página.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Adicionar um mandato de ordem de débito ao cliente.
1. No **Painel de Navegação**, vá para **Módulos > Contas a receber > Clientes > Todos os clientes**.
2. Na lista, selecione um registro. Por exemplo, selecione US-001
3. Clique em **Editar**.
4. Expanda a Guia Rápida **Padrões de pagamento**.
5. No campo **Método de pagamento**, insira ou selecione um valor.
6. Expanda a Guia Rápida **Padrões de pagamento**.
7. Expanda a Guia Rápida **Cartas de ordem de débito direto**.
8. Clique em **Adicionar**.
9. No campo **Conta bancária**, insira ou selecione um valor.
10. No campo **Conta bancária do credor**, insira ou selecione um valor.
11. No campo **Frequência de pagamento**, insira o número de pagamentos que você espera para processar esta carta da ordem.
12. Clique em **OK**.
13. Clique em **Imprimir**.
14. Clique em **Relatório da carta de ordem**.
15. Feche a página.
16. Clique em **Editar**.
17. No campo **Data de assinatura**, insira uma data.
18. Clique em **Sim**.
19. Insira o local em que a carta de ordem foi assinada.
20. Clique em **OK**.
21. Feche a página.

## <a name="create-a-free-text-invoice-with-mandate"></a>Criar uma fatura de texto livre com mandato
1. No **Painel de Navegação**, vá para **Módulos > Contas a receber > Faturas > Todas as faturas de texto livre**.
2. Clique em **Novo**.
3. Selecione o cliente para o qual você adicionou a carta da ordem.
4. No campo **Carta de ordem de débito direto**, insira ou selecione um valor.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]