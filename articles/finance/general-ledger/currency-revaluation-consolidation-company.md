---
title: Reavaliação de moeda em uma empresa de consolidação
description: Este artigo descreve como reavaliar a moeda em uma empresa de consolidação.
author: aprilolson
ms.date: 10/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: twheeloc
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c05ef0d4d05d5113d3b858dafe49ee9c1c7211d9
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779653"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a>Reavaliação de moeda em uma empresa de consolidação

[!include [banner](../includes/banner.md)]

Após consolidar dados de uma moeda contábil para outra, você ainda deverá executar a reavaliação de moeda se houver uma alteração em taxas de câmbio, de forma que os saldos da conta sejam reavaliados corretamente. Ao consolidar originalmente os dados, use a guia **Conversão de moeda** para selecionar as taxas de câmbio iniciais para conversão durante o processo de consolidação. Após inserir uma nova taxa de câmbio (por exemplo, no mês seguinte), você deve reavaliar os saldos da conta. Os lucros não realizados ou as perdas são atualizados em conformidade, com base na nova taxa de câmbio e data. O exemplo a seguir ilustra as entradas contábeis que são criadas durante o processo.

## <a name="company-setup"></a>Configuração da empresa
-   **Empresa de origem/operacional (USMF)** – Os dólares norte-americanos (USD) são usados como a contabilidade e a moeda de relatório.
-   **Empresa consolidada (CON)** – Os euros (EUR) são usados como a contabilidade e a moeda de relatório.
    -   **Lucro realizado** – conta contábil 801500
    -   **Perda realizada** – conta contábil 801600
    -   **Lucro não realizado** – conta contábil 801600
    -   **Perda não realizada** – conta contábil 801400

## <a name="original-transactions"></a>Transações originais
### <a name="cash-receipt-transactions-in-usmf"></a>Transações de recebimento à vista em USMF

| Data       | Conta contábil               | Moeda | Valor |
|------------|------------------------------|----------|--------|
| 11/10/2020 | 110110 – à vista                | USD      | 500    |
| 11/10/2020 | 130100 – Contas a Receber | USD      | -500   |

## <a name="exchange-rates"></a>Taxas de câmbio

| Moeda inicial | Moeda final | Data inicial | Taxa de câmbio |
|---------------|-------------|------------|---------------|
| EUR           | USD         | 1/10/2020  | 200           |
| EUR           | USD         | 1/11/2020  | 150           |
| EUR           | USD         | 1/12/2017  | 100           |

## <a name="perform-the-consolidation-for-october-2020"></a>Execute a consolidação de outubro de 2020
### <a name="balances-in-the-consolidation-company"></a>Saldos na empresa de consolidação

| Conta contábil | Moeda | Valor | Cálculo    |
|----------------|----------|--------|----------------|
| 110110         | EUR      | 250    | R$500 × 50%  |
| 130100         | EUR      | -250   | -R$500 × 50% |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2020-through-november-30-2020"></a>Executar a reavaliação de moeda para as contas desde 1º de outubro de 2020 até 30 de novembro de 2020
### <a name="balances-in-the-consolidation-company"></a>Saldos na empresa de consolidação

| Conta contábil | Moeda | Valor  | Cálculo                        |
|----------------|----------|---------|------------------------------------|
| 110110         | EUR      | 333.33  | Valor original de 500 × 66,6667%  |
| 130100         | EUR      | -333,33 | Valor original de -500 × 66,6667% |
| 801400         | EUR      | 83,33   | 333,33 – 250                       |
| 801600         | EUR      | -83,33  | -333,33 – (-250)                   |

Você verá transações adicionais para os valores de moeda de relatório.

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2020-through-december-31-2020"></a>Executar a reavaliação de moeda para as contas desde 1º de outubro de 2020 até 31 de dezembro de 2020
### <a name="balances-in-the-consolidation-company"></a>Saldos na empresa de consolidação

| Conta contábil | Moeda | Valor  | Cálculo                                          |
|----------------|----------|---------|------------------------------------------------------|
| 110110         | EUR      | 500,00  | Valor original de 500 × 1                           |
| 130100         | EUR      | -500,00 | Valor original de -500 × 1                          |
| 801400         | EUR      | 250     | 500 – 333,33 = 166,67 166,67 + 83,33 = 250           |
| 801600         | EUR      | -250    | -500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
