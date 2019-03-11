---
title: Pagamentos centralizados para Contas a receber
description: As organizações que incluem várias entidades legais podem criar e gerenciar pagamentos usando uma entidade legal única que trate todos os pagamentos. Consequentemente, a mesma transação não precisa ser inserida em várias entidade legais. Este artigo fornece exemplos que mostram como a postagem de pagamentos centralizados é feita em vários cenários.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e9eb935d32e61b2cf0ec8710f6c2cfb18ecfe034
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "330738"
---
# <a name="centralized-payments-for-accounts-receivable"></a>Pagamentos centralizados para Contas a receber

[!include [banner](../includes/banner.md)]

As organizações que incluem várias entidades legais podem criar e gerenciar pagamentos usando uma entidade legal única que trate todos os pagamentos. Consequentemente, a mesma transação não precisa ser inserida em várias entidade legais. Este artigo fornece exemplos que mostram como a postagem de pagamentos centralizados é feita em vários cenários.

As organizações que incluem várias entidades legais podem criar e gerenciar pagamentos usando uma entidade legal que trate todos os pagamentos. Consequentemente, a mesma transação não precisa ser inserida em várias entidade legais. Além disso, a organização economiza tempo, pois os processos para propostas de pagamento, liquidações e transações de edição abertas e fechadas para os pagamentos centralizados são simplificados. 

Em uma organização de pagamentos centralizados, existem muitas entidades legais para operações, e cada entidade operante gerencia as próprias informações de faturas a receber. Os pagamentos para todas as entidades legais operantes são recebidos por uma única entidade legal, conhecida como entidade legal de pagamento. Durante o processo de liquidação, as transações a vencer ou vencidas aplicáveis são geradas. Você pode especificar qual entidade legal da organização recebe as transações de ganho ou perda realizada e como são tratadas as transações com desconto à vista relacionadas a um pagamento centralizado. 

Os exemplos a seguir ilustram como o lançamento é tratado em vários cenários. Esta configuração é presumida para todos esses exemplos:

-   As entidades legais são Fabrikam, Fabrikam Leste e Fabrikam Oeste. Os pagamentos de clientes são inseridos na Fabrikam.
-   O campo **Lançar desconto à vista** na página **Contabilidade intercompanhia** é definido como **Entidade legal da fatura**.
-   O campo **Lançar ganho ou perda de câmbio de moeda** na página **Contabilidade intercompanhia** é definido como **Entidade legal do pagamento**.
-   O cliente Northwind Traders é configurado como um cliente em cada entidade legal. Os clientes das diversas entidades legais são identificados como o mesmo cliente porque compartilham a mesma ID de catálogo de endereços global.

| ID do catálogo de endereços | Conta de cliente | Nome              | Pessoas Jurídicas de Direito Privado  |
|-----------------|------------------|-------------------|---------------|
| 4050            | 4000             | Northwind Traders | Fabrikam      |
| 4050            | 4000             | Northwind Traders | Fabrikam Leste |
| 4050            | 10.000            | Northwind Traders | Fabrikam Oeste |

## <a name="example-1-customer-payment-of-invoice-from-another-legal-entity"></a>Exemplo 1: Pagamento da fatura ao cliente de outra entidade legal
A Fabrikam recebe um pagamento de 600,00 na conta de cliente da Fabrikam 4000, a Northwind Traders. O pagamento é liquidado com uma nota fiscal em aberto para a conta de cliente 4000 na Fabrikam Leste.

### <a name="invoice-is-posted-in-fabrikam-east-for-customer-4000"></a>A nota fiscal é lançada na Fabrikam Leste para o cliente 4000

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Contas a receber (Fabrikam Leste) | 600,00       |               |
| Vendas (Fabrikam Leste)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>O pagamento é recebido e lançado na Fabrikam para o cliente 4000

| Conta                        | Valor do débito | Valor do crédito |
|--------------------------------|--------------|---------------|
| Pagamento à vista (Fabrikam)                | 600,00       |               |
| Contas a receber (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Leste

**Lançamento da Fabrikam**

| Conta                         | Valor do débito | Valor do crédito |
|---------------------------------|--------------|---------------|
| Contas a receber (Fabrikam)  | 600,00       |               |
| Devido à Fabrikam Leste (Fabrikam) |              | 600,00        |

**Lançamento da Fabrikam Leste**

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Devido pela Fabrikam (Fabrikam Leste)   | 600,00       |               |
| Contas a receber (Fabrikam Leste) |              | 600,00        |

## <a name="example-2-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Exemplo 2: Pagamento da fatura ao cliente de outra entidade legal com desconto à vista
A Fabrikam recebe um pagamento de 580,00 na conta de cliente da Fabrikam 4000, a Northwind Traders. A Fabrikam Leste tem uma nota fiscal em aberto para o cliente 4000. A nota fiscal tem um desconto à vista de 20,00 disponível. O pagamento é liquidado com faturas em aberto da Fabrikam Leste. O desconto à vista é lançado para a entidade legal da fatura, a Fabrikam leste.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>A fatura é lançada na Fabrikam Leste para o cliente 4000 da Fabrikam Leste

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Contas a receber (Fabrikam Leste) | 600,00       |               |
| Vendas (Fabrikam Leste)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>O pagamento é recebido e lançado na Fabrikam para o cliente 4000 da Fabrikam

| Conta                        | Valor do débito | Valor do crédito |
|--------------------------------|--------------|---------------|
| Pagamento à vista (Fabrikam)                | 600,00       |               |
| Contas a receber (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Leste

**Lançamento da Fabrikam**

| Conta                         | Valor do débito | Valor do crédito |
|---------------------------------|--------------|---------------|
| Contas a receber (Fabrikam)  | 580,00       |               |
| Devido à Fabrikam Leste (Fabrikam) |              | 580,00        |

**Lançamento da Fabrikam Leste**

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Devido pela Fabrikam (Fabrikam Leste)   | 580,00       |               |
| Contas a receber (Fabrikam Leste) |              | 580,00        |
| Desconto à vista (Fabrikam Leste)       | 20,00        |               |
| Contas a receber (Fabrikam Leste) |              | 20.00         |

## <a name="example-3-customer-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-gain"></a>Exemplo 3: Pagamento de fatura ao cliente de outra entidade legal com ganho de taxa cambial realizado
A Fabrikam recebe um pagamento de 600,00 euros (EUR) para o cliente 4000 da Fabrikam a Northwind Traders. O pagamento é liquidado com uma fatura em aberto para o cliente 4000 na Fabrikam Leste. Uma transação de ganho cambial é gerada durante o processo de liquidação.

-   Taxa de câmbio de EUR para dólares americanos (USD) a partir da data da fatura: 1,2062
-   Taxa de câmbio de EUR para USD na data da fatura: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>A nota fiscal é lançada na Fabrikam Leste para o cliente 4000 da Fabrikam Leste

| Conta                             | Valor do débito            | Valor do crédito           |
|-------------------------------------|-------------------------|-------------------------|
| Contas a receber (Fabrikam Leste) | 600,00 EUR / 723,72 BRL |                         |
| Vendas (Fabrikam Leste)               |                         | 600,00 EUR / 723,72 BRL |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>O pagamento é recebido e lançado na Fabrikam para o cliente 4000 da Fabrikam

| Conta                        | Valor do débito            | Valor do crédito           |
|--------------------------------|-------------------------|-------------------------|
| Pagamento à vista (Fabrikam)                | 600,00 EUR / 736,62 BRL |                         |
| Contas a receber (Fabrikam) |                         | 600,00 EUR / 736,62 BRL |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Leste

**Lançamento da Fabrikam**

| Conta                         | Valor do débito            | Valor do crédito           |
|---------------------------------|-------------------------|-------------------------|
| Contas a receber (Fabrikam)  | 600,00 EUR / 736,62 BRL |                         |
| Devido à Fabrikam Leste (Fabrikam) |                         | 600,00 EUR / 736,62 BRL |
| Devido à Fabrikam Leste (Fabrikam) | 0,00 EUR / 12,90 BRL    |                         |
| Ganho realizado (Fabrikam)        |                         | 0,00 EUR / 12,90 BRL    |

**Lançamento da Fabrikam Leste**

| Conta                             | Valor do débito            | Valor do crédito           |
|-------------------------------------|-------------------------|-------------------------|
| Devido pela Fabrikam (Fabrikam Leste)   | 600,00 EUR / 736,62 BRL |                         |
| Contas a receber (Fabrikam Leste) |                         | 600,00 EUR / 736,62 BRL |
| Contas a receber (Fabrikam Leste) | 0,00 EUR / 12,90 BRL    |                         |
| Devido pela Fabrikam (Fabrikam Leste)   |                         | 0,00 EUR / 12,90 BRL    |

## <a name="example-4-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-gain"></a>Exemplo 4: Pagamento da fatura ao cliente de outra entidade legal com desconto à vista e ganho cambial realizado
A Fabrikam lança um pagamento para o cliente 4000 da Fabrikam, a Northwind Traders, para uma fatura em aberto na Fabrikam Leste. A fatura tem um desconto à vista disponível e uma transação de imposto é gerada. O pagamento é liquidado com a fatura em aberto da Fabrikam Leste. Uma transação de ganho cambial é gerada durante o processo de liquidação. O desconto à vista é lançado para a entidade legal da fatura (Fabrikam Leste) e o ganho cambial é lançado para a entidade legal de pagamento (Fabrikam).

-   Taxa de câmbio de EUR para USD na data da fatura: 1,2062
-   Taxa de câmbio de EUR para USD na data da fatura: 1,2277

### <a name="free-text-invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-customer-4000"></a>A nota fiscal de texto livre é lançada e uma transação de imposto é gerada na Fabrikam Leste para o cliente 4000

| Conta                             | Valor do débito            | Valor do crédito           |
|-------------------------------------|-------------------------|-------------------------|
| Contas a receber (Fabrikam Leste) | 638,22 EUR / 769,82 BRL |                         |
| Vendas (Fabrikam Leste)               |                         | 600,00 EUR / 723,72 BRL |
| Imposto sobre vendas (Fabrikam Leste)           |                         | 38,22 EUR / 46,10 BRL   |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>O pagamento é recebido e lançado na Fabrikam para o cliente 4000

| Conta                        | Valor do débito            | Valor do crédito           |
|--------------------------------|-------------------------|-------------------------|
| Pagamento à vista (Fabrikam)                | 626,22 EUR / 768,81 BRL |                         |
| Contas a receber (Fabrikam) |                         | 626,22 EUR / 768,81 BRL |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Leste

**Lançamento da Fabrikam**

| Conta                         | Valor do débito            | Valor do crédito           |
|---------------------------------|-------------------------|-------------------------|
| Contas a receber (Fabrikam)  | 626,22 EUR / 768,81 BRL |                         |
| Devido à Fabrikam Leste (Fabrikam) |                         | 626,22 EUR / 768,81 BRL |
| Devido à Fabrikam Leste (Fabrikam) | 0,00 EUR / 13,46 BRL    |                         |
| Ganho realizado (Fabrikam)        |                         | 0,00 EUR / 13,46 BRL    |

**Lançamento da Fabrikam Leste**

| Conta                             | Valor do débito            | Valor do crédito           |
|-------------------------------------|-------------------------|-------------------------|
| Devido pela Fabrikam (Fabrikam Leste)   | 626,22 EUR / 768,81 BRL |                         |
| Contas a receber (Fabrikam Leste) |                         | 626,22 EUR / 768,81 BRL |
| Contas a receber (Fabrikam Leste)  | 0,00 EUR / 13,46 BRL    |                         |
| Devido pela Fabrikam (Fabrikam Leste)   |                         | 0,00 EUR / 13,46 BRL    |
| Desconto à vista (Fabrikam Leste)       | 12,00 EUR / 14,47 BRL   |                         |
| Contas a receber (Fabrikam Leste) |                         | 12,00 EUR / 14,47 BRL   |

## <a name="example-5-customer-credit-note-with-primary-payment"></a>Exemplo 5: nota de crédito do cliente com pagamento principal
A Fabrikam recebe um pagamento de 75,00 do cliente 4000, a Northwind Traders. O pagamento é liquidado com uma nota fiscal em aberto para o cliente 10000 da Fabrikam Oeste e uma nota de crédito aberta para o cliente 4000 da Fabrikam Leste. O pagamento não é selecionado como pagamento principal na página **Liquidar transações**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>A fatura é lançada na Fabrikam Oeste para o cliente 10000

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Contas a receber (Fabrikam Oeste) | 100,00       |               |
| Vendas (Fabrikam Oeste)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Uma nota de crédito é lançada na Fabrikam Leste para o cliente 4000

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Devoluções de vendas (Fabrikam Leste)       | 25,00        |               |
| Contas a receber (Fabrikam Leste) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>O pagamento é lançado na Fabrikam para o cliente 4000

| Conta                        | Valor do débito | Valor do crédito |
|--------------------------------|--------------|---------------|
| Pagamento à vista (Fabrikam)                | 75,00        |               |
| Contas a receber (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Oeste e a nota de crédito da Fabrikam Leste

**Lançamento da Fabrikam**

| Conta                           | Valor do débito | Valor do crédito |
|-----------------------------------|--------------|---------------|
| Devido pela Fabrikam Leste (Fabrikam) | 25,00        |               |
| Contas a receber (Fabrikam)    |              | 25,00         |
| Contas a receber (Fabrikam)    | 100,00       |               |
| Devido à Fabrikam Oeste (Fabrikam)   |              | 100,00        |

**Lançamento da Fabrikam Leste**

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Contas a receber (Fabrikam Leste) | 25,00        |               |
| Devido à Fabrikam (Fabrikam Leste)     |              | 25,00         |

**Lançamento da Fabrikam Oeste**

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Devido pela Fabrikam (Fabrikam Oeste)   | 100,00       |               |
| Contas a receber (Fabrikam Oeste) |              | 100,00        |

## <a name="example-6-customer-credit-note-without-primary-payment"></a>Exemplo 6: nota de crédito do cliente sem pagamento principal
A Fabrikam recebe um pagamento de 75,00 do cliente 4000, a Northwind Traders. O pagamento é liquidado com uma nota fiscal em aberto para o cliente 10000 da Fabrikam Oeste e uma nota de crédito aberta para o cliente 4000 da Fabrikam Leste. O pagamento não é selecionado como pagamento principal na página **Liquidar transações**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>A fatura é lançada na Fabrikam Oeste para o cliente 10000

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Contas a receber (Fabrikam Oeste) | 100,00       |               |
| Vendas (Fabrikam Oeste)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Uma nota de crédito é lançada na Fabrikam Leste para o cliente 4000

| Conta                             | Valor do débito | Valor do crédito |
|-------------------------------------|--------------|---------------|
| Devoluções de vendas (Fabrikam Leste)       | 25,00        |               |
| Contas a receber (Fabrikam Leste) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>O pagamento é lançado na Fabrikam para o cliente 4000

| Conta                        | Valor do débito | Valor do crédito |
|--------------------------------|--------------|---------------|
| Pagamento à vista (Fabrikam)                | 75,00        |               |
| Contas a receber (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Oeste e a nota de crédito da Fabrikam Leste

**Lançamento da Fabrikam**

| Conta                         | Valor do débito | Valor do crédito |
|---------------------------------|--------------|---------------|
| Contas a receber (Fabrikam)  | 75,00        |               |
| Devido à Fabrikam Oeste (Fabrikam) |              | 75,00         |

**Lançamento da Fabrikam Leste**

| Conta                              | Valor do débito | Valor do crédito |
|--------------------------------------|--------------|---------------|
| Contas a receber (Fabrikam Leste)  | 25,00        |               |
| Devido à Fabrikam Oeste (Fabrikam Leste) |              | 25,00         |

**Lançamento da Fabrikam Oeste**

| Conta                                | Valor do débito | Valor do crédito |
|----------------------------------------|--------------|---------------|
| Devido pela Fabrikam (Fabrikam Oeste)      | 75,00        |               |
| Contas a receber (Fabrikam Oeste)    |              | 75,00         |
| Devido pela Fabrikam Leste (Fabrikam Oeste) | 25,00        |               |
| Contas a receber (Fabrikam Oeste)    |              | 25,00         |





