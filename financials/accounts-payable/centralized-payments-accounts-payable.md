---
title: Pagamentos centralizados para Contas a pagar
description: "As organizações que incluem várias entidades legais podem criar e gerenciar pagamentos usando uma entidade legal única que trate todos os pagamentos. Consequentemente, os mesmos pagamentos não precisam ser inseridos para várias entidade legais. Este artigo fornece exemplos que mostram como a postagem de pagamentos centralizados é feita em vários cenários."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14341
ms.assetid: 7bd02e32-2416-4ac6-8a60-85525267fdb7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: e7cc68b1b40b6a0361d7c215af466ae5a17a2aaa
ms.lasthandoff: 03/31/2017


---

# <a name="centralized-payments-for-accounts-payable"></a>Pagamentos centralizados para Contas a pagar

As organizações que incluem várias entidades legais podem criar e gerenciar pagamentos usando uma entidade legal única que trate todos os pagamentos. Consequentemente, os mesmos pagamentos não precisam ser inseridos para várias entidade legais. Este artigo fornece exemplos que mostram como a postagem de pagamentos centralizados é feita em vários cenários.

As organizações que incluem várias entidades legais podem criar e gerenciar pagamentos usando uma entidade legal que trate todos os pagamentos. Consequentemente, os mesmos pagamentos não precisam ser inseridos para várias entidade legais. Além disso, a organização economiza tempo, já que o processo de pagamento é simplificado.

Em uma organização de pagamentos centralizados, existem muitos entidade legal para operações, e cada entidade legal operacional gerencia as próprias faturas de fornecedor. Os pagamentos para todas as entidades legais operacionais são gerados de uma única entidade legal, conhecida como a entidade legal do pagamento. Durante o processo de liquidação, as transações a vencer ou vencidas aplicáveis são geradas. Você pode especificar qual entidade legal dentro da organização receberá as transações de ganho ou perda realizada e como são tratadas as transações com desconto à vista relacionadas a pagamentos de empresa cruzada. 

Os exemplos a seguir ilustram como o lançamento é tratado em vários cenários. Esta configuração é presumida para todos esses exemplos:

-   As entidades legais são Fabrikam, Fabrikam Leste e Fabrikam Oeste. Os pagamentos são feitos da Fabrikam.
-   O campo **Lançar desconto à vista** na página **Contabilidade intercompanhia** é definido como **Entidade legal da fatura**.
-   O campo **Lançar ganho ou perda de câmbio de moeda** na página **Contabilidade intercompanhia** é definido como **Entidade legal do pagamento**.
-   O fornecedor Fourth coffee é configurado como um fornecedor em cada entidade legal. Os fornecedores das diversas entidades legais são identificados como o mesmo fornecedor porque compartilham a mesma ID de catálogo de endereços global.

| ID de diretório | Conta de fornecedor | Nome          | Pessoas Jurídicas de Direito Privado  |
|--------------|----------------|---------------|---------------|
| 1050         | 3004           | Fourth Coffee | Fabrikam      |
| 1050         | 100            | Fourth Coffee | Fabrikam Leste |
| 1050         | 3004           | Fourth Coffee | Fabrikam Oeste |

## <a name="example-1-vendor-payment-of-invoice-from-another-legal-entity"></a>Exemplo 1: pagamento de fatura do fornecedor de outra entidade legal
A Fabrikam Leste tem uma fatura em aberto para a conta de fornecedor 100, Fourth Coffee. A Fabrikam insere e lança um pagamento para a conta de fornecedor 3004, Fourth Coffee. O pagamento é liquidado com a nota fiscal em aberto.

### <a name="invoice-is-posted-in-fabrikam-east-for-vendor-100"></a>A nota fiscal é lançada na Fabrikam Leste para o fornecedor 100

| Conta                          | Valor do débito | Valor do crédito |
|----------------------------------|--------------|---------------|
| Despesa (Fabrikam Leste)          | 600,00       |               |
| Contas a pagar (Fabrikam Leste) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>O pagamento é gerado e lançado na Fabrikam para o fornecedor 3004

| Conta                     | Valor do débito | Valor do crédito |
|-----------------------------|--------------|---------------|
| Contas a pagar (Fabrikam) | 600,00       |               |
| Pagamento à vista (Fabrikam)             |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Leste

**Fabrikam posting**

| Conta                           | Valor do débito | Valor do crédito |
|-----------------------------------|--------------|---------------|
| Devido pela Fabrikam Leste (Fabrikam) | 600,00       |               |
| Contas a pagar (Fabrikam)       |              | 600,00        |

**Fabrikam East posting**

| Conta                          | Valor do débito | Valor do crédito |
|----------------------------------|--------------|---------------|
| Contas a pagar (Fabrikam Leste) | 600,00       |               |
| Devido à Fabrikam (Fabrikam Leste)  |              | 600,00        |

## <a name="example-2-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Exemplo 2: pagamento de fatura do fornecedor de outra entidade legal com desconto à vista
A Fabrikam Leste tem uma fatura em aberto para o fornecedor 100, Fourth Coffee. A nota fiscal tem um desconto à vista de 20,00 disponível. A Fabrikam insere e lança um pagamento de 580,00 para o fornecedor 3004 da Fabrikam, Fourth Coffee. O pagamento é liquidado com faturas em aberto da Fabrikam Leste. O desconto à vista é lançado para a entidade legal da fatura, a Fabrikam leste.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>A fatura é lançada na Fabrikam Leste para o fornecedor 100 da Fabrikam Leste

| Conta                          | Valor do débito | Valor do crédito |
|----------------------------------|--------------|---------------|
| Despesa (Fabrikam Leste)          | 600,00       |               |
| Contas a pagar (Fabrikam Leste) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>O pagamento é gerado e lançado na Fabrikam para o fornecedor 3004 da Fabrikam

| Conta                     | Valor do débito | Valor do crédito |
|-----------------------------|--------------|---------------|
| Contas a pagar (Fabrikam) | 580,00       |               |
| Pagamento à vista (Fabrikam)             |              | 580,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Leste

**Fabrikam posting**

| Conta                           | Valor do débito | Valor do crédito |
|-----------------------------------|--------------|---------------|
| Devido pela Fabrikam Leste (Fabrikam) | 580,00       |               |
| Contas a pagar (Fabrikam)       |              | 580,00        |

**Fabrikam East posting**

| Conta                          | Valor do débito | Valor do crédito |
|----------------------------------|--------------|---------------|
| Contas a pagar (Fabrikam Leste) | 580,00       |               |
| Devido à Fabrikam (Fabrikam Leste)  |              | 580,00        |
| Contas a pagar (Fabrikam Leste) | 20,00        |               |
| Desconto à vista (Fabrikam Leste)    |              | 20.00         |

## <a name="example-3-vendor-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-loss"></a>Exemplo 3: pagamento de fatura do fornecedor de outra entidade legal com perda cambial realizada
A Fabrikam Leste tem uma fatura em aberto para o fornecedor 100, Fourth Coffee. A Fabrikam insere e lança um pagamento para o fornecedor 3004 da Fabrikam, Fourth Coffee. O pagamento é liquidado com a nota fiscal em aberto da Fabrikam Leste. Uma transação de perdas cambiais é gerada durante o processo de liquidação.

-   Taxa de câmbio de euros (EUR) para dólares americanos (USD) a partir da data da fatura: 1,2062
-   Taxa de câmbio de EUR para USD na data da fatura: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>A nota fiscal é lançada na Fabrikam Leste para o fornecedor 100 da Fabrikam Leste

| Conta                          | Valor do débito            | Valor do crédito           |
|----------------------------------|-------------------------|-------------------------|
| Despesa (Fabrikam Leste)          | 600,00 EUR / 723,72 BRL |                         |
| Contas a pagar (Fabrikam Leste) |                         | 600,00 EUR / 723,72 BRL |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>O pagamento é gerado e lançado na Fabrikam para o fornecedor 3004 da Fabrikam

| Conta                     | Valor do débito            | Valor do crédito           |
|-----------------------------|-------------------------|-------------------------|
| Contas a pagar (Fabrikam) | 600,00 EUR / 736,62 BRL |                         |
| Pagamento à vista (Fabrikam)             |                         | 600,00 EUR / 736,62 BRL |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Leste

**Fabrikam posting**

| Conta                           | Valor do débito            | Valor do crédito           |
|-----------------------------------|-------------------------|-------------------------|
| Devido pela Fabrikam Leste (Fabrikam) | 600,00 EUR / 736,62 BRL |                         |
| Contas a pagar (Fabrikam)       |                         | 600,00 EUR / 736,62 BRL |
| Perda realizada (Fabrikam)          | 0,00 EUR / 12,90 BRL    |                         |
| Devido pela Fabrikam Leste (Fabrikam) |                         | 0,00 EUR / 12,90 BRL    |

**Fabrikam East posting**

| Conta                          | Valor do débito            | Valor do crédito           |
|----------------------------------|-------------------------|-------------------------|
| Contas a pagar (Fabrikam Leste) | 600,00 EUR / 736,62 BRL |                         |
| Devido à Fabrikam (Fabrikam Leste)  |                         | 600,00 EUR / 736,62 BRL |
| Devido à Fabrikam (Fabrikam Leste)  | 0,00 EUR / 12,90 BRL    |                         |
| Contas a pagar (Fabrikam Leste) |                         | 0,00 EUR / 12,90 BRL    |

## <a name="example-4-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-loss"></a>Exemplo 4: pagamento de fatura do fornecedor de outra entidade legal com desconto à vista e perda cambial realizada
A Fabrikam Leste tem uma fatura em aberto para o fornecedor 100, Fourth Coffee. A fatura tem um desconto à vista disponível e uma transação de imposto é gerada. A Fabrikam lança um pagamento para o fornecedor 3004 da Fabrikam, Fourth Coffee. O pagamento é liquidado com a nota fiscal em aberto da Fabrikam Leste. Uma transação de perdas cambiais é gerada durante o processo de liquidação. O desconto à vista é lançado para a entidade legal de faturamento (Fabrikam Leste) e a perda cambial é lançada para a entidade legal para pagamentos (Fabrikam).

-   Taxa de câmbio de EUR para USD na data da fatura: 1,2062
-   Taxa de câmbio de EUR para USD na data da fatura: 1,2277

### <a name="invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-vendor-100"></a>A nota fiscal é lançada e uma transação de imposto é gerada na Fabrikam Leste para o fornecedor 100

| Conta                          | Valor do débito            | Valor do crédito           |
|----------------------------------|-------------------------|-------------------------|
| Despesa (Fabrikam Leste)          | 564,07 EUR / 680,38 BRL |                         |
| Imposto sobre vendas (Fabrikam Leste)        | 35,93 EUR / 43,34 BRL   |                         |
| Contas a pagar (Fabrikam Leste) |                         | 600,00 EUR / 723,72 BRL |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>O pagamento é gerado e lançado na Fabrikam para o fornecedor 3004

| Conta                     | Valor do débito            | Valor do crédito           |
|-----------------------------|-------------------------|-------------------------|
| Contas a pagar (Fabrikam) | 588,72 EUR / 722,77 BRL |                         |
| Pagamento à vista (Fabrikam Leste)        |                         | 588,72 EUR / 722,77 BRL |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Leste

**Fabrikam posting**

| Conta                           | Valor do débito            | Valor do crédito           |
|-----------------------------------|-------------------------|-------------------------|
| Devido pela Fabrikam Leste (Fabrikam) | 588,72 EUR / 722,77 BRL |                         |
| Contas a pagar (Fabrikam)       |                         | 588,72 EUR / 722,77 BRL |
| Perda realizada (Fabrikam)          | 0,00 EUR / 12,66 BRL    |                         |
| Devido pela Fabrikam Leste (Fabrikam) |                         | 0,00 EUR / 12,66 BRL    |

**Fabrikam East posting**

| Conta                          | Valor do débito            | Valor do crédito           |
|----------------------------------|-------------------------|-------------------------|
| Contas a pagar (Fabrikam Leste) | 588,72 EUR / 722,77 BRL |                         |
| Devido à Fabrikam (Fabrikam Leste)  |                         | 588,72 EUR / 722,77 BRL |
| Devido à Fabrikam (Fabrikam Leste)   | 0,00 EUR / 12,66 BRL    |                         |
| Contas a pagar (Fabrikam Leste) |                         | 0,00 EUR / 12,66 BRL    |
| Contas a pagar (Fabrikam Leste) | 11,28 EUR / 13,61 BRL   |                         |
| Desconto à vista (Fabrikam Leste)    |                         | 11,28 EUR / 13,61 BRL   |

## <a name="example-5-vendor-credit-note-with-primary-payment"></a>Exemplo 5: nota de crédito do fornecedor com pagamento principal
A Fabrikam gera um pagamento de 75,00 para o fornecedor 3004, Fourth Coffee. O pagamento é liquidado com uma nota fiscal em aberto para o fornecedor 3004 da Fabrikam Oeste e uma nota de crédito aberta para o fornecedor 100 da Fabrikam Leste. O pagamento está selecionado como o principal ** transações de acordo ** na página.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>A fatura é lançada na Fabrikam Oeste para o fornecedor 3004

| Conta                          | Valor do débito | Valor do crédito |
|----------------------------------|--------------|---------------|
| Despesa (Fabrikam Oeste)          | 100,00       |               |
| Contas a pagar (Fabrikam Oeste) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Uma nota de crédito é lançada na Fabrikam Leste para o fornecedor 100

| Conta                          | Valor do débito | Valor do crédito |
|----------------------------------|--------------|---------------|
| Contas a pagar (Fabrikam Leste) | 25,00        |               |
| Devolução de compras (Fabrikam Leste) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>O pagamento é lançado na Fabrikam para o fornecedor 3004

| Conta                     | Valor do débito | Valor do crédito |
|-----------------------------|--------------|---------------|
| Contas a pagar (Fabrikam) | 75,00        |               |
| Pagamento à vista (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Oeste e a nota de crédito da Fabrikam Leste

**Fabrikam posting**

| Conta                           | Valor do débito | Valor do crédito |
|-----------------------------------|--------------|---------------|
| Contas a pagar (Fabrikam)       | 25,00        |               |
| Devido à Fabrikam Leste (Fabrikam)   |              | 25,00         |
| Devido pela Fabrikam Oeste (Fabrikam) | 100,00       |               |
| Contas a pagar (Fabrikam)       |              | 100,00        |

**Fabrikam East posting**

| Conta                           | Valor do débito | Valor do crédito |
|-----------------------------------|--------------|---------------|
| Devido pela Fabrikam (Fabrikam Leste) | 25,00        |               |
| Contas a pagar (Fabrikam Leste)  |              | 25,00         |

**Fabrikam West posting**

| Conta                          | Valor do débito | Valor do crédito |
|----------------------------------|--------------|---------------|
| Contas a pagar (Fabrikam Oeste) | 100,00       |               |
| Devido à Fabrikam (Fabrikam Oeste)  |              | 100,00        |

## <a name="example-6-vendor-credit-note-without-primary-payment"></a>Exemplo 6: nota de crédito do fornecedor sem o pagamento principal
A Fabrikam gera um pagamento de 75,00 para o fornecedor 3004, Fourth Coffee. O pagamento é liquidado com uma nota fiscal em aberto para o fornecedor 3004 da Fabrikam Oeste e uma nota de crédito aberta para o fornecedor 100 da Fabrikam Leste. O pagamento não está selecionado como o principal ** transações de acordo ** na página.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>A fatura é lançada na Fabrikam Oeste para o fornecedor 3004

| Conta                          | Valor do débito | Valor do crédito |
|----------------------------------|--------------|---------------|
| Despesa (Fabrikam Oeste)          | 100,00       |               |
| Contas a pagar (Fabrikam Oeste) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>Uma nota de crédito é lançada na Fabrikam Leste para o fornecedor 100

| Conta                          | Valor do débito | Valor do crédito |
|----------------------------------|--------------|---------------|
| Contas a pagar (Fabrikam Leste) | 25,00        |               |
| Devolução de compras (Fabrikam Leste) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>O pagamento é lançado na Fabrikam para o fornecedor 3004

| Conta                     | Valor do débito | Valor do crédito |
|-----------------------------|--------------|---------------|
| Contas a pagar (Fabrikam) | 75,00        |               |
| Pagamento à vista (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>O pagamento da Fabrikam é liquidado com a nota fiscal da Fabrikam Oeste e a nota de crédito da Fabrikam Leste

**Fabrikam posting**

| Conta                           | Valor do débito | Valor do crédito |
|-----------------------------------|--------------|---------------|
| Devido pela Fabrikam Oeste (Fabrikam) | 75,00        |               |
| Contas a pagar (Fabrikam)       |              | 75,00         |

**Fabrikam East posting**

| Conta                                | Valor do débito | Valor do crédito |
|----------------------------------------|--------------|---------------|
| Devido pela Fabrikam Oeste (Fabrikam Leste) | 25,00        |               |
| Contas a pagar (Fabrikam Leste)       |              | 25,00         |

**Fabrikam West posting**

| Conta                              | Valor do débito | Valor do crédito |
|--------------------------------------|--------------|---------------|
| Contas a pagar (Fabrikam Oeste)     | 75,00        |               |
| Devido à Fabrikam (Fabrikam Oeste)      |              | 75,00         |
| Contas a pagar (Fabrikam Oeste)     | 25,00        |               |
| Devido à Fabrikam Leste (Fabrikam Oeste) |              | 25,00         |




