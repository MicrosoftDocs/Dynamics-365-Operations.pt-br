---
title: Criar um diário de baixa para um cliente
description: Esta guia de tarefa mostrará como configurar parâmetros de baixas contábeis e dar baixa em transações da página das coleções, a página inicial das notas fiscais de clientes, e a página do cliente.
author: ShivamPandey-msft
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 857d3a224f35c4eeedbf4913aea14011091d5466
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823110"
---
# <a name="create-a-write-off-journal-for-a-customer"></a>Criar um diário de baixa para um cliente

[!include [banner](../../includes/banner.md)]

Esta guia de tarefa mostrará como configurar parâmetros de baixas contábeis e dar baixa em transações da página das coleções, a página inicial das notas fiscais de clientes, e a página do cliente. Esta tarefa usa a empresa de demonstração USMF.


## <a name="set-up-the-write-off-parameters"></a>Configurar os parâmetros de dar baixa
1. Vá para **Painel de Navegação > Módulos > Crédito e coleções > Configuração > Parâmetros de contas a receber**.
2. Clique na guia **Coleções**.
3. Expanda ou recolha a seção **Dar baixa**.
    - O **diário de valores** é o diário geral que reterá as transações de baixa que você criar.  
    - Você pode anexar um código de motivo para cada amortização. Você pode sobrepor este padrão no momento de dar baixa.  
    - Defina **Separar imposto** como Sim se desejar separar os impostos sobre vendas da transação original na amortização.  
4. Feche a página.
5. Vá para **Crédito e cobranças > Configuração > Perfis de lançamentos de cliente**. A amortização de conta será usada como o ajuste da conta de despesas de reserva ou no diário geral.
6. Feche a página.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Dar baixa de um saldo do cliente de página de saldos antiga
1. Vá para **Crédito e coleções > Cobranças > Saldos antigos**.
2. Marque a linha do cliente que deseja dar baixa. Por exemplo, marcar a linha com Vidoeiro de empresa nela.
3. No **Painel de Ações**, clique em **Cobrar**.
4. Clique em **Dar baixa**.
5. Clique em **OK**.
6. Feche a página.
7. Vá até **Painel de Navegação > Módulos > Contabilidade > Entradas de diário > Diários gerais**.
8. Selecione o número do lote do diário para o diário que contém a amortização. Uma linha é criada para reverter o saldo do cliente. Uma ou mais linhas são criadas para lançar a amortização na conta de valores.  
9. Feche a página.
10. Feche a página.

## <a name="write-off-transactions-from-the-collections-form"></a>Dar baixa nas transações do formulário das coleções.
1. Vá para **Crédito e coleções > Cobranças > Saldos antigos**.
2. Selecione o nome do cliente que tem as transações que deseja dar baixa. Por exemplo, selecione Vendas por atacado da cavidade (US-004).
3. Marcar a linha como a primeira transação.
4. Marcar a linha como a segunda transação.
5. Clique em **Dar baixa**.
6. No campo **Comentário do motivo**, insira "Débitos ruins".
7. Clique em **OK**.
8. Feche a página.
9. Feche a página.
10. Vá para **Contabilidade > Entradas de diários > Diários gerais**.
11. Selecione o número do lote do diário para o diário que contém a amortização. Uma linha é criada para reverter o saldo do cliente. Uma ou mais linhas são criadas para lançar a amortização na conta de valores.  
12. Feche a página.
13. Feche a página.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Dar baixa em uma nota fiscal da página de notas fiscais de clientes em Aberto
1. Vá para **Painel de Navegação > Módulos > Contas a receber > Faturas > Faturas abertas do cliente**.
2. Marcar a linha de uma fatura. Por exemplo, marcar a linha de CIV-000667.
3. No **Painel de Ações**, clique em **Fatura**.
4. Clique em **Dar baixa**.
5. Clique em **OK**.
6. Feche a página.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Dar baixa no saldo de um cliente na página do cliente
1. Vá para **Contas recebíveis > Clientes > Todos os clientes**.
2. Selecione uma conta de cliente. Por exemplo, selecione US-001 (Contoso Retail de São Diego).
3. No **Painel de Ações**, clique em **Cobrar**.
4. Clique em **Dar baixa**.
5. Clique em **OK**.
6. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]