---
title: Cálculo e arredondamento de imposto
description: Este artigo fornece uma visão geral do cálculo e do arredondamento do imposto, além de explicar os parâmetros da configuração de cálculo e arredondamento do imposto.
author: wangchen
ms.date: 06/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom:
- "13111"
- intro-internal
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2022-05-31
ms.dyn365.ops.version: AX 10.0.28
ms.openlocfilehash: aa3564f0fcf4a958637ba4a5cdcc497bffc50000
ms.sourcegitcommit: 8b716849707ec96d1cb4cac85b9e782dc25f5a70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8939223"
---
# <a name="sales-tax-calculation-and-rounding"></a>Cálculo e arredondamento de imposto

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do cálculo e arredondamento de imposto no Microsoft Dynamics 365 Finance. Ele também explica os parâmetros usados na configuração para o cálculo e o arredondamento do imposto e como esses parâmetros funcionam juntos.

## <a name="parameters"></a>Parâmetros

Vários parâmetros controlam o arredondamento e o cálculo do imposto:

- **Método de cálculo** – esse parâmetro é definido na página **Parâmetros da contabilidade** e define se o valor base do imposto será calculado por documento ou por linha. Se o parâmetro **Base marginal** do código do imposto for definido para **Valor líquido do saldo de fatura**, o valor base do imposto será sempre calculado por documento, independentemente da configuração desse parâmetro.
- **Arredondamento por** – esse parâmetro é definido para o grupo de impostos e define se o valor do imposto é arredondado por código de imposto ou por combinação de códigos de imposto.
- **Origem** – esse parâmetro é definido para o código de imposto e define como o valor do imposto é calculado. Para obter mais informações, consulte [Métodos de cálculo do imposto no campo Origem](sales-tax-calculation-methods-origin-field.md).
- **Base marginal** – esse parâmetro é definido para o código de imposto e determina qual valor é usado para selecionar as taxas de imposto apropriadas na página **Valores do código de imposto**. Para obter mais informações, consulte [Taxas de imposto baseadas nos métodos Base marginal e Cálculo](marginal-base-field.md)
- **Regra de arredondamento de imposto** – esse parâmetro é definido para o código do imposto e define como o valor do imposto determinado é arredondado, incluindo a precisão de arredondamento e o método de arredondamento.

O restante deste artigo apresenta alguns exemplos típicos de cálculo e arredondamento de imposto que usam uma combinação dos parâmetros anteriores.

## <a name="scenario-for-the-examples"></a>Cenários dos exemplos

- Há duas linhas no documento tributável, e o valor base do imposto para cada linha é 42,42.
- Dois códigos de imposto são definidos para cada linha: código de imposto 1 e código de imposto 2.
- A taxa de imposto do código de imposto 1 e do código de imposto 2 é 10%.
- O preço não inclui imposto.
- A precisão de arredondamento é 0,01.
- O método de arredondamento é **Arredondar**.

## <a name="example-1"></a>Exemplo 1

### <a name="parameter-values"></a>Valores de parâmetro

| Método de cálculo | Arredondamento por    | Origem                   | Base marginal       |
| ------------------ | -------------- | ------------------------ | ------------------- |
| Linha               | Código do imposto | Porcentagem do valor líquido | Valor líquido por linha |

### <a name="calculation-and-rounding-behavior"></a>Comportamento de cálculo e arredondamento

| Número da linha | Código do imposto | Origem do valor | Valor do imposto |
| ------------| ---------------| --------------| -----------------|
| 1           | Código 1         | 42.42         | 4.25             |
| 1           | Código 2         | 42.42         | 4.25             |
| 2           | Código 1         | 42.42         | 4.25             |
| 2           | Código 2         | 42.42         | 4.25             |

O valor base do imposto é calculado por linha:

- **Linha 1:** 42,42
- **Linha 2:** 42,42

O valor do imposto é calculado por código de imposto:

- **Linha 1:**

    - Valor do imposto para código de imposto 1 = 42,42 &times; 10% = 4,242
    - Valor do imposto para código de imposto 2 = 42,42 &times; 10% = 4,242

- **Linha 2:**

    - Valor do imposto para código de imposto 1 = 42,42 &times; 10% = 4,242
    - Valor do imposto para código de imposto 2 = 42,42 &times; 10% = 4,242

O valor do imposto é arredondado por código de imposto:

- **Linha 1:**

    - Valor do imposto arredondado para código de imposto 1 = 4,25
    - Valor do imposto arredondado para código de imposto 2 = 4,25

- **Linha 2:**

    - Valor do imposto arredondado para código de imposto 1 = 4,25
    - Valor do imposto arredondado para código de imposto 2 = 4,25

## <a name="example-2"></a>Exemplo 2

### <a name="parameter-values"></a>Valores de parâmetro

| Método de cálculo | Arredondamento por    | Origem                   | Base marginal                 |
| ------------------ | -------------- | ------------------------ | ----------------------------- |
| Linha/Total         | Código do imposto | Porcentagem do valor líquido | Valor líquido do saldo de fatura |

### <a name="calculation-and-rounding-behavior"></a>Comportamento de cálculo e arredondamento

| Número da linha | Código do imposto | Origem do valor | Valor do imposto |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.25             |
| 1           | Código 2         | 42.42         | 4.25             |
| 2           | Código 1         | 42.42         | 4.24             |
| 2           | Código 2         | 42.42         | 4.24             |

O valor base do imposto é calculado por documento:

- Valor base do imposto = 42,42 + 42,42 = 84,84

O valor do imposto é calculado por código de imposto:

- Valor do imposto para código de imposto 1 = 84,84 &times; 10% = 8,484
- Valor do imposto para código de imposto 2 = 84,84 &times; 10% = 8,484

O valor do imposto é arredondado por código de imposto:

- Valor do imposto arredondado para código de imposto 1 = 8,49
- Valor do imposto arredondado para código de imposto 2 = 8,49

O valor do imposto arredondado é alocado para cada linha por código de imposto:

- Aloque o valor de imposto arredondado do código de imposto 1 (8,49) para a linha 1 (4,25) e a linha 2 (4,24).
- Aloque o valor de imposto arredondado do código de imposto 2 (8,49) para a linha 1 (4,25) e a linha 2 (4,24).

## <a name="example-3"></a>Exemplo 3

### <a name="parameter-values"></a>Valores de parâmetro

| Método de cálculo | Arredondamento por    | Origem                              | Base marginal       |
| ------------------ | -------------- | ----------------------------------- | ------------------- |
| Linha               | Código do imposto | Porcentagem do valor líquido calculada | Valor líquido por linha |

### <a name="calculation-and-rounding-behavior"></a>Comportamento de cálculo e arredondamento

| Número da linha | Código do imposto | Origem do valor | Valor do imposto |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.72             |
| 1           | Código 2         | 42.42         | 4.72             |
| 2           | Código 1         | 42.42         | 4.72             |
| 2           | Código 2         | 42.42         | 4.72             |

O valor base do imposto é calculado por linha:

- **Linha 1:** 42,42
- **Linha 2:** 42,42

O valor do imposto é calculado por código de imposto:

- **Linha 1:**

    - Valor do imposto para código de imposto 1 = 42,42 &times; 10% &divide; (1 a 10%) = 4,7133
    - Valor do imposto para código de imposto 2 = 42,42 &times; 10% &divide; (1 a 10%) = 4,7133

- **Linha 2:**

    - Valor do imposto para código de imposto 1 = 42,42 &times; 10% &divide; (1 a 10%) = 4,7133
    - Valor do imposto para código de imposto 2 = 42,42 &times; 10% &divide; (1 a 10%) = 4,7133

O valor do imposto é arredondado por código de imposto:

- **Linha 1:**

    - Valor do imposto arredondado para código de imposto 1 = 4,72
    - Valor do imposto arredondado para código de imposto 2 = 4,72

- **Linha 2:**

    - Valor do imposto arredondado para código de imposto 1 = 4,72
    - Valor do imposto arredondado para código de imposto 2 = 4,72

## <a name="example-4"></a>Exemplo 4

### <a name="parameter-values"></a>Valores de parâmetro

| Método de cálculo | Arredondamento por    | Origem                              | Base marginal                 |
| ------------------ | -------------- | ----------------------------------- | ----------------------------- |
| Linha/Total         | Código do imposto | Porcentagem do valor líquido calculada | Valor líquido do saldo de fatura |

### <a name="calculation-and-rounding-behavior"></a>Comportamento de cálculo e arredondamento

| Número da linha | Código do imposto | Origem do valor | Valor do imposto |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.72             |
| 1           | Código 2         | 42.42         | 4.72             |
| 2           | Código 1         | 42.42         | 4.71             |
| 2           | Código 2         | 42.42         | 4.71             |

O valor base do imposto é calculado por documento:

- Valor base do imposto = 42,42 + 42,42 = 84,84

O valor do imposto é calculado por código de imposto:

- Valor do imposto para código de imposto 1 = 84,84 &times; 10% &divide; (1 a 10%) = 9,4267
- Valor do imposto para código de imposto 2 = 84,84 &times; 10% &divide; (1 a 10%) = 9,4267

O valor do imposto é arredondado por código de imposto:

- Valor do imposto arredondado para código de imposto 1 = 9,43
- Valor do imposto arredondado para código de imposto 2 = 9,43

O valor do imposto arredondado é alocado para cada linha por código de imposto:

- Aloque o valor de imposto do código de imposto 1 (9,43) para a linha 1 (4,72) e a linha 2 (4,71).
- Aloque o valor de imposto do código de imposto 2 (9,43) para a linha 1 (4,72) e a linha 2 (4,71).

## <a name="example-5"></a>Exemplo 5

### <a name="parameter-values"></a>Valores de parâmetro

| Método de cálculo | Arredondamento por                | Origem                   | Base marginal       |
| ------------------ | -------------------------- | ------------------------ | ------------------- |
| Linha               | Combinação de código do imposto | Porcentagem do valor líquido | Valor líquido por linha |

### <a name="calculation-and-rounding-behavior"></a>Comportamento de cálculo e arredondamento

| Número da linha | Código do imposto | Origem do valor | Valor do imposto |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.25             |
| 1           | Código 2         | 42.42         | 4.24             |
| 2           | Código 1         | 42.42         | 4.24             |
| 2           | Código 2         | 42.42         | 4.24             |

O valor base do imposto é calculado por linha:

- **Linha 1:** 42,42
- **Linha 2:** 42,42

O valor do imposto é calculado por código de imposto:

- **Linha 1:**

    - Valor do imposto para código de imposto 1 = 42,42 &times; 10% = 4,242
    - valor do imposto para código de imposto 2 = 42,42 &times; 10% = 4,242

- **Linha 2:**

    - Valor do imposto para código de imposto 1 = 42,42 &times; 10% = 4,242
    - Valor do imposto para código de imposto 2 = 42,42 &times; 10% = 4,242

O valor do imposto é arredondado por combinação de código de imposto:

- Valor total do imposto = 4,242 + 4,242 + 4,242 + 4,242 = 16,968, que é arredondado para 16,97

O valor do imposto arredondado é alocado para cada linha por código de imposto:

- Aloque o valor do imposto (16,97) para a linha 1 e a linha 2:

    - **Linha 1:**

        - Valor do imposto para código de imposto 1 = 4,25
        - Valor do imposto para código de imposto 2 = 4,24

    - **Linha 2:**

        - Valor do imposto para código de imposto 1 = 4,24
        - Valor do imposto para código de imposto 2 = 4,24

## <a name="example-6"></a>Exemplo 6

### <a name="parameter-values"></a>Valores de parâmetro

| Método de cálculo | Arredondamento por                | Origem                   | Base marginal                 |
| ------------------ | -------------------------- | ------------------------ | ----------------------------- |
| Linha/Total         | Combinação de código do imposto | Porcentagem do valor líquido | Valor líquido do saldo de fatura |

### <a name="calculation-and-rounding-behavior"></a>Comportamento de cálculo e arredondamento

| Número da linha | Código do imposto | Origem do valor | Valor do imposto |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.25             |
| 1           | Código 2         | 42.42         | 4.24             |
| 2           | Código 1         | 42.42         | 4.24             |
| 2           | Código 2         | 42.42         | 4.24             |

O valor base do imposto é calculado por documento:

- Valor base do imposto = 42,42 + 42,42 = 84,84

O valor do imposto é calculado por código de imposto:

- Valor do imposto para código de imposto 1 = 84,84 &times; 10% = 8,484
- Valor do imposto para código de imposto 2 = 84,84 &times; 10% = 8,484

O valor do imposto é arredondado por combinação de código de imposto:

- Valor total do imposto = 8,484 + 8,484 = 16,968, que é arredondado para 16,97

O valor do imposto arredondado é alocado para cada linha por código de imposto:

- Aloque o valor do imposto (16,97) para a linha 1 e a linha 2:

    - **Linha 1:**

        - Valor do imposto para código de imposto 1 = 4,25
        - Valor do imposto para código de imposto 2 = 4,24

    - **Linha 2:**

        - Valor do imposto para código de imposto 1 = 4,24
        - Valor do imposto para código de imposto 2 = 4,24

## <a name="example-7"></a>Exemplo 7

### <a name="parameter-values"></a>Valores de parâmetro

| Método de cálculo | Arredondamento por                | Origem                              | Base marginal       |
| ------------------ | -------------------------- | ----------------------------------- | ------------------- |
| Linha               | Combinação de código do imposto | Porcentagem do valor líquido calculada | Valor líquido por linha |

### <a name="calculation-and-rounding-behavior"></a>Comportamento de cálculo e arredondamento

| Número da linha | Código do imposto | Origem do valor | Valor do imposto |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.72             |
| 1           | Código 2         | 42.42         | 4.71             |
| 2           | Código 1         | 42.42         | 4.71             |
| 2           | Código 2         | 42.42         | 4.72             |

O valor base do imposto é calculado por linha:

- **Linha 1:** 42,42
- **Linha 2:** 42,42

O valor do imposto é calculado por código de imposto:

- **Linha 1:**

    - Valor do imposto para código de imposto 1 = 42,42 &times; 10% &divide; (1 a 10%) = 4,7133
    - Valor do imposto para código de imposto 2 = 42,42 &times; 10% &divide; (1 a 10%) = 4,7133

- **Linha 2:**

    - Valor do imposto para código de imposto 1 = 42,42 &times; 10% &divide; (1 a 10%) = 4,7133
    - Valor do imposto para código de imposto 2 = 42,42 &times; 10% &divide; (1 a 10%) = 4,7133

O valor do imposto é arredondado por combinação de código de imposto:

- Valor total do imposto = 4,7133 + 4,7133 + 4,7133 + 4,7133 = 18,8532, que é arredondado para 18,86

O valor do imposto arredondado é alocado para cada linha por código de imposto:

- Aloque o valor do imposto (18,86) para a linha 1 e a linha 2:

    - **Linha 1:**

        - Valor do imposto para código de imposto 1 = 4,72
        - Valor do imposto para código de imposto 2 = 4,71

    - **Linha 2:**

        - Valor do imposto para código de imposto 1 = 4,71
        - Valor do imposto para código de imposto 2 = 4,72

## <a name="example-8"></a>Exemplo 8

### <a name="parameter-values"></a>Valores de parâmetro

| Método de cálculo | Arredondamento por                | Origem                              | Base marginal                 |
| ------------------ | -------------------------- | ----------------------------------- | ----------------------------- |
| Linha/Total         | Combinação de código do imposto | Porcentagem do valor líquido calculada | Valor líquido do saldo de fatura |

### <a name="calculation-and-rounding-behavior"></a>Comportamento de cálculo e arredondamento

| Número da linha | Código do imposto | Origem do valor | Valor do imposto |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | Código 1         | 42.42         | 4.72             |
| 1           | Código 2         | 42.42         | 4.71             |
| 2           | Código 1         | 42.42         | 4.71             |
| 2           | Código 2         | 42.42         | 4.72             |

O valor base do imposto é calculado por documento:

- Valor base do imposto = 42,42 + 42,42 = 84,84

O valor do imposto é calculado por código de imposto:

- Valor do imposto para código de imposto 1 = 84,84 &times; 10% &divide; (1 a 10%) = 9,4267
- Valor do imposto para código de imposto 2 = 84,84 &times; 10% &divide; (1 a 10%) = 9,4267

O valor do imposto é arredondado por combinação de código de imposto:

- Valor total do imposto = 9,4267 + 9,4267 = 18,8534, que é arredondado para 18,86

O valor do imposto arredondado é alocado para cada linha por código de imposto:

- Aloque o valor do imposto (18,86) para a linha 1 e a linha 2:

    - **Linha 1:**

        - Valor do imposto para código de imposto 1 = 4,72
        - Valor do imposto para código de imposto 2 = 4,71

    - **Linha 2:**

        - Valor do imposto para código de imposto 1 = 4,71
        - Valor do imposto para código de imposto 2 = 4,72

## <a name="additional-resources"></a>Recursos adicionais

- [Métodos de cálculo de impostos no campo de Origem](sales-tax-calculation-methods-origin-field.md)
- [Determinando as alíquotas de imposto com base nos campos Base marginal e Métodos de cálculo](marginal-base-field.md)
- [Opções de cálculo do valor total e do intervalo para códigos de impostos](whole-amount-interval-options-sales-tax-codes.md)
