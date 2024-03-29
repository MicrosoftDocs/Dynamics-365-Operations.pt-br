---
title: Configurar clientes e contas bancárias de cliente para débitos diretos de ISO20022
description: Essa tarefa orienta como configurar uma conta bancária do cliente e uma carta de ordem de débito direto do cliente que são necessárias para gerar o arquivo de pagamento do cliente, como o débito direto ISO20022.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 595e89faa1e24ca937d399994e15ce53e3f5308b1c6fd7f43e4e831e70c15ad8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736858"
---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a>Configurar clientes e contas bancárias de cliente para débitos diretos de ISO20022

[!include [banner](../../includes/banner.md)]

Essa tarefa orienta como configurar uma conta bancária do cliente e uma carta de ordem de débito direto do cliente que são necessárias para gerar o arquivo de pagamento do cliente, como o débito direto ISO20022. Dependendo dos formatos de pagamento de cliente que estiverem configurados, podem ser necessárias informações adicionais de um cliente ou de uma conta bancária do cliente que não estão cobertas neste procedimento. 

Esta tarefa foi criada usando a empresa DEMF de dados de demonstração com uma entidade legal primária na Alemanha.



Este é o quarto dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.


## <a name="set-up-a-customer-bank-account"></a>Configurar uma conta bancária de cliente
1. Ir para Contas recebíveis > Clientes > Todos os clientes.
2. Use o Filtro Rápido para localizar registros. Por exemplo, no campo Conta, filtre com um valor de 'DE-010'.
3. Na lista, clique no link na linha selecionada.
4. No Painel de Ação, clique em Cliente.
5. Clique em Contas bancárias.
6. Clique em Novo.
7. No campo Conta bancária, digite um valor.
8. No campo Nome, digite um valor.
    * Por exemplo, insira "EUR bank".  
9. No campo Grupos de banco, insira ou selecione um valor.
10. No campo IBAN, digite um valor.
    * Por exemplo, insira "DE36200400000628808808".  
11. No campo Código SWIFT, digite um valor.
    * Por exemplo, insira 'COBADEFFXXX'.  Observe que o SWIFT\BIC não é obrigatório para vários formatos de pagamento, no entanto, é recomendável registrá-lo em uma conta bancária.  
12. Clique em Salvar.
13. Feche a página.
14. Clique em Editar.
15. Expanda a seção de padrões de pagamento.
16. No campo Conta bancária, insira ou selecione um valor.

## <a name="add-a-direct-debit-mandate"></a>Adicionar uma carta de ordem de débito direto
1. Expanda a seção de cartas da ordem de débito direto.
2. Clique em Adicionar.
3. No campo Conta bancária do credor, insira ou selecione um valor.
    * Por exemplo, selecione DEMF OPER.  
4. No campo Data de assinatura, insira uma data.
5. Clique em Sim para confirmar a atualização de data.
6. No campo Local de assinatura, insira ou selecione um valor.
7. No campo Número esperado de pagamentos, insira um número.
8. Clique em OK.
9. Clique em Salvar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]