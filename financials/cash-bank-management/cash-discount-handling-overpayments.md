---
title: "Manuseio de descontos à vista para pagamentos a maior"
description: "Este artigo fornece os cenários que mostram como um pagamento é manuseado quando o cliente leva um desconto à vista, mas também paga em excesso."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14171
ms.assetid: a94d0fd0-57ba-4054-93c8-519d01d50e19
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 451273a8ee98f7033795182e754f76aca3788f47
ms.lasthandoff: 03/31/2017


---

# <a name="handling-cash-discounts-for-overpayments"></a>Manuseio de descontos à vista para pagamentos a maior

[!include[banner](../includes/banner.md)]


Este artigo fornece os cenários que mostram como um pagamento é manuseado quando o cliente leva um desconto à vista, mas também paga em excesso. 

Uma fatura será considerada liquidada quando o valor do pagamento for maior do que o valor da fatura menos o desconto à vista. Para especificar como uma diferença de desconto à vista viável é manuseada quando uma fatura é paga a maior, use os campos **Administração de descontos à vista** e **Pagamento máximo a maior/a menor** na página **Parâmetros de contas a receber**. No exemplo a seguir, o cliente pagou em excesso a fatura de 0,50.

| Total da fatura | Desconto à vista disponível | Valor a ser pago, o que inclui o desconto à vista | Valor que o cliente realmente paga |
|---------------|-------------------------|-----------------------------------------------------|-----------------------------------|
| R$ 105,00        | R$ 10,50                   | R$ 94,50                                               | R$ 95,00                             |

## <a name="cash-discount-administration--specific"></a>Opção de administração do desconto à vista = Específico
Quando **Específico** for selecionado no campo **Administração de descontos à vista** na página **Contas para transações automáticas**, o desconto à vista total será obtido. O valor do pagamento a maior é lançado em uma conta contábil da diferença de desconto à vista ou permanece um saldo da conta de cliente. O comportamento depende do fato de o valor do pagamento excedente estar entre 0,00 e o valor inserido no campo ** Pagamento máximo a maior/a menor** ou se o valor do pagamento a maior for maior do que o valor de **Pagamento máximo a maior/a menor**.

### <a name="scenario-1"></a>Cenário 1

Neste cenário, o valor do pagamento a maior está entre 0,00 e o pagamento máximo a maior/a menor. Uma fatura de 105,00 é inserida e um desconto à vista ficará disponível se a fatura for paga em até sete dias.

| Total da fatura | Desconto à vista disponível | Valor a ser pago, o que inclui o desconto à vista |
|---------------|-------------------------|-----------------------------------------------------|
| R$ 105,00        | R$ 10,50                   | R$ 94,50                                               |

O cliente envia um pagamento de 95,00 no período de desconto à vista. O pagamento é liquidado com a fatura de 105,00. Depois que a fatura e o pagamento forem liquidados, as transações a seguir serão criadas para o cliente em Contas a receber.

| Transação   | Valor | Saldo |
|---------------|--------|---------|
| Fatura       | R$ 105,00 | 0,00    |
| Pagamento       | -95,00 | 0,00    |
| Desconto à vista | -10,50 | 0,00    |

As seguintes entradas contábeis serão geradas para o pagamento e a liquidação. **Pagamento**

| Conta             | Valor do débito | Valor de crédito |
|---------------------|--------------|---------------|
| Pagamento à vista                | R$ 95,00        |               |
| Contas a Receber |              | R$ 95,00         |

**Liquidação**

| Conta                                                                                                          | Valor do débito | Valor de crédito |
|------------------------------------------------------------------------------------------------------------------|--------------|---------------|
| Desconto à vista (o campo **Conta principal para descontos do cliente** na página **Descontos à vista**)                 | R$ 10,50        |               |
| Contas a Receber                                                                                              |              | R$ 10,50         |
| Desconto à vista do cliente (o campo **Desconto à vista do cliente** na página **Conta para transações automáticas**) |              | 0,50          |
| Contas a Receber                                                                                              | 0,50         |               |

### <a name="scenario-2"></a>Cenário 2

Neste cenário, o valor de pagamento a maior excede o valor máximo de pagamento a maior ou a menor. Uma fatura de 105,00 é inserida e um desconto à vista ficará disponível se a fatura for paga em até sete dias.

| Total da fatura | Desconto à vista disponível | Valor a ser pago, o que inclui o desconto à vista |
|---------------|-------------------------|-----------------------------------------------------|
| R$ 105,00        | R$ 10,50                   | R$ 94,50                                               |

O cliente envia um pagamento de 95,00 no período de desconto à vista. O pagamento é liquidado com a fatura de 105,00. Depois que a fatura e o pagamento forem liquidados, as transações a seguir serão criadas para o cliente em Contas a receber.

| Transação   | Valor | Saldo |
|---------------|--------|---------|
| Fatura       | R$ 105,00 | 0,00    |
| Pagamento       | -95,00 | -0,50   |
| Desconto à vista | -10,50 | 0,00    |

O valor do pagamento a maior de 0.50 permanecerá como um saldo em aberto no pagamento e pode ser liquidado outra fatura. As seguintes entradas contábeis serão geradas para o pagamento e a liquidação. **Pagamento**

| Conta             | Valor do débito | Valor de crédito |
|---------------------|--------------|---------------|
| Pagamento à vista                | R$ 95,00        |               |
| Contas a Receber |              | R$ 95,00         |

**Liquidação**

| Conta                                                                                          | Valor do débito | Valor de crédito |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Desconto à vista (o campo **Conta principal para descontos do cliente** na página **Descontos à vista**) | R$ 10,50        |               |
| Contas a Receber                                                                              |              | R$ 10,50         |

## <a name="cash-discount-administration--unspecific"></a>Opção de administração do desconto à vista = Não específico
Quando **Não específico** for selecionado no campo **Administração de descontos à vista** na página **Contas para transações automáticas**, o valor do desconto à vista será reduzido pelo valor do pagamento a maior. Esse comportamento sempre se aplicará, mesmo se o valor do pagamento a maior for maior ou menor do que o valor inserido no campo **Pagamento máximo a maior/menor**.

### <a name="scenario-3"></a>Cenário 3

Neste cenário, uma fatura de 105,00 é inserida e um desconto à vista ficará disponível se a fatura for paga em até sete dias.

| Total da fatura | Desconto à vista disponível | Valor a ser pago, o que inclui o desconto à vista |
|---------------|-------------------------|-----------------------------------------------------|
| R$ 105,00        | R$ 10,50                   | R$ 94,50                                               |

O cliente envia um pagamento de 95,00 na data de desconto à vista. O pagamento é liquidado com a fatura de 105,00. Depois que a fatura e o pagamento forem liquidados, as transações a seguir serão criadas para o cliente em Contas a receber.

| Transação   | Valor | Saldo |
|---------------|--------|---------|
| Fatura       | R$ 105,00 | 0,00    |
| Pagamento       | -95,00 | -0,00   |
| Desconto à vista | -10,00 | 0,00    |

O valor do desconto à vista é reduzido de 10,50 para 10,00. O pagamento e a fatura são considerados liquidados. **Pagamento**

| Conta             | Valor de débito | Valor de crédito |
|---------------------|--------------|---------------|
| Pagamento à vista                | R$ 95,00        |               |
| Contas a Receber |              | R$ 95,00         |

**Liquidação**

| Conta                                                                                          | Valor do débito | Valor de crédito |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Desconto à vista (o campo **Conta principal para descontos do cliente** na página **Descontos à vista**) | R$ 10,50        |               |
| Contas a Receber                                                                              |              | R$ 10,50         |






