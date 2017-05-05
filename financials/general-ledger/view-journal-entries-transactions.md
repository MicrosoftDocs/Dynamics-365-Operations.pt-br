---
title: "Visualizar entradas e transações de transações"
description: "Este artigo explica as várias formas com as quais você pode exibir entradas de diário e transações."
author: RobinARH
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: a6848ea9c05536ac18a038b1864c9ccb9408964c
ms.lasthandoff: 03/31/2017


---

# <a name="view-journal-entries-and-transactions"></a>Visualizar entradas e transações de transações

Este artigo explica as várias formas com as quais você pode exibir entradas de diário e transações. 

Os usuários que desejam exibir diários e transações têm várias formas de acessar os dados. Podem aproveitar as vantagens das páginas de consulta que oferecem a busca detalhada, ou podem usar várias opções do relatório na razão.

## <a name="voucher-transactions"></a>Comprovantes de transações
**Transações de comprovante** é uma página de consulta na qual você pode selecionar várias tabelas e campos para especificar critérios para o saldo ou a transação que está sendo pesquisando. Por exemplo, você pode exibir todas as transações para uma data ou uma conta específicas, ou todas as transações do tipo **Operação** que estão em um nível de lançamento específico. Por padrão, a página mostra o número do diário, o comprovante, a data e a conta principal, mas você pode adicionar tabelas, campos e os critérios para restringir a pesquisa.

## <a name="audit-trail"></a>Trilha de auditoria
**Trilha de auditoria** é uma página de consulta que mostra os tipos de transações e as descrições para as quais as transações foram criadas e quando elas foram criadas. Na página de consulta **Trilha de auditoria** você pode visualizar as transações do comprovante.

## <a name="financial-reports"></a>Relatórios financeiros
Você também pode explorar e analisar transações de contabilidade para executar relatórios financeiros. Como o design de relatórios financeiros pode ser baseado nas contas, em dimensões, categorias de conta ou uma combinação dos três, você pode exibir as transações ao fazer uma busca detalhada em várias formas. Caso você precise mais informações para transações de contabilidade, também é possível incluir propriedades de várias transações como parte do design do relatório. Além disso, se você desejar ver as transações que compõem um saldo da contabilidade, você pode fazer uma busca detalhada de transações de contas da mesma forma que na página de listagem **Balancete**.

## <a name="ledger-reports"></a>Relatórios do razão
Além dos relatórios financeiros, você pode usar os relatórios do razão a seguir para visualizar as transações do razão:

-   **Demonstrativo de dimensão** – Este relatório mostra as transações por dia e por conta e também as opções para mostrar transações por dimensão e período.
-   **Lista de transações do razão** – Este relatório mostra transações nas concorrências de transação, conta e relatórios de uma conta.
-   **Diário de impressão** – esse relatório mostra o resultado de um diário lançado. Você pode executar o relatório por número de lote de diário ou tipo de diário ou adicionar campos adicionais.
-   **Transações lançadas pelo diário** – Este relatório mostra as transações que foram lançadas em um diário, agrupadas por comprovante.
-   **Lista de transações por data** – Este relatório mostra todas as transações por data, com o número do diário, o comprovante e a conta contábil. Também mostra as transações da transação, na contabilidade e as moedas de relatório.
-   **Origem de transação** – Este relatório de transação mostra a conta por diário e por transação, conta e moeda do relatório. Também mostra cada linha do diário usado como uma compensação.


Para obter mais informações, consulte [Saldo da conta contábil](general-ledger-account-balances.md), [Gerenciador de fontes contábeis](\financials\accounts-payable\accounting-source-explorer) e [Relatórios financeiros](financial-reporting-getting-started.md)

