---
title: Funcionalidade com intervalo de composição
description: Este tópico fornece informações que ajudarão você a escolher entre os intervalos de composição mensal, trimestral, semestral e anual.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5978abfd4341bbca76ff0211f029097c3d2d785c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971444"
---
# <a name="compounding-interval-functionality"></a>Funcionalidade com intervalo de composição

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico fornece informações que ajudarão você a escolher entre os intervalos de composição mensal, trimestral, semestral e anual. A funcionalidade de intervalo de composição é usada para determinar o número de períodos de composição por ano em uma agenda de pagamento de arrendamento. Cada um dos quatro exemplos neste tópico mostra como será a aparência de uma agenda de pagamento de arrendamento para um intervalo diferente.

Não é possível selecionar um intervalo de composição que seja menos frequente do que a frequência de pagamento de arrendamento. Por exemplo, um intervalo de composição trimestral não pode ser usado com uma frequência de pagamento mensal e um intervalo de composição anual não pode ser usado com uma frequência de pagamento semestral. Se você tentar selecionar um intervalo de composição que seja menos frequente do que a frequência de pagamento de arrendamento, você receberá uma mensagem de erro.

> [!NOTE]
> Em todos os quatro exemplos deste tópico, o intervalo de composição coincide com a frequência de pagamento.

## <a name="examples"></a>Exemplos

### <a name="setup-for-all-four-leases"></a>Configuração de todos os quatro arrendamentos

As tabelas a seguir mostram os valores definidos nas guias **Geral** e **Linhas da agenda de pagamento** para os quatro arrendamentos usados nos exemplos.

**Guia Geral**

| Campo                      | Alíquota                        |
|----------------------------|------------------------------|
| Taxa incremental de empréstimo | **5%**                       |
| Tipo de anuidade               | **Anuidade comum**         |
| Intervalo de composição       | Consulte os exemplos individuais. |
| Frequência de pagamento          | **Mensalmente**                  |
| Data de início          | **1/1/2020**                 |

**Guia Linhas de agenda de pagamento**

| Campo             | Alíquota                        |
|-------------------|------------------------------|
| Data inicial        | **1/1/2020**                 |
| Períodos           | **120**                      |
| Intervalo do período   | **Meses**                   |
| Data de término          | **31/12/2029**               |
| Frequência de pagamento | Consulte os exemplos individuais. |
| Valor do pagamento    | **50.000**                   |

### <a name="lease-1-monthly-compounding-interval-and-monthly-payment-frequency"></a>Arrendamento 1: intervalo de composição mensal e frequência de pagamento mensal

A tabela a seguir lista os 12 primeiros meses da agenda de pagamento. Observe os seguintes detalhes:

- O valor na coluna "Período" aumenta em 1 a cada mês, porque cada mês é um novo intervalo de composição.
- Na fórmula da coluna "Valor presente", a taxa é dividida por 12, pois há 12 períodos de composição por ano. O expoente (ou seja, o numeral sobrescrito) é igual ao valor na coluna "Período".

| Período | Mês | Data        | Valor do pagamento | Valor presente                                       |
|--------|-------|------------|----------------|-----------------------------------------------------|
| 1      | 1     | 31/1/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>1</sup> = 49.792,53  |
| 2      | 2     | 29/2/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>2</sup> = 49.585,92  |
| 3      | 3     | 31/3/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>3</sup> = 49.380,17  |
| 4      | 4     | 30/4/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>4</sup> = 49.175,28  |
| 5      | 5     | 31/5/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>5</sup> = 48.971,23  |
| 6      | 6     | 30/6/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>6</sup> = 48.768,03  |
| 7      | 7     | 31/7/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>7</sup> = 48.565,67  |
| 8      | 8     | 31/8/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>8</sup> = 48.364,15  |
| 9      | 9     | 30/9/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>9</sup> = 48.163,47  |
| 10     | 10    | 31/10/2020 | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>10</sup> = 47.963,62 |
| 11     | 11    | 30/11/2020 | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>11</sup> = 47.764,61 |
| 12     | 12    | 31/12/2020 | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>12</sup> = 47.566,41 |

### <a name="lease-2-quarterly-compounding-interval-and-quarterly-payment-frequency"></a>Arrendamento 2: intervalo de composição trimestral e frequência de pagamento trimestral

A tabela a seguir lista os 12 primeiros meses da agenda de pagamento. Observe os seguintes detalhes:

- O valor na coluna "Período" aumenta em 1 a cada três meses (isto é, a cada trimestre) porque cada trimestre é um novo intervalo de composição.
- Na fórmula da coluna "Valor presente", a taxa é dividida por 4, pois há quatro períodos de composição por ano. O expoente é igual ao valor na coluna "Período".

| Período | Mês | Data        | Valor do pagamento | Valor presente                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/1/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 2     | 29/2/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 3     | 31/3/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 49.382,72 |
| 2      | 4     | 30/4/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 5     | 31/5/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 6     | 30/6/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 48.773,05 |
| 3      | 7     | 31/7/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 8     | 31/8/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 9     | 30/9/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 48.170,92 |
| 4      | 10    | 31/10/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 11    | 30/11/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 12    | 31/12/2020 | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 47.576,21 |

> [!NOTE]
> Se o tipo de anuidade for alterado para **Anuidade devido**, o pagamento será no início do trimestre, e não no final do trimestre.

### <a name="lease-3-semiannual-compounding-interval-and-semiannual-payment-frequency"></a>Arrendamento 3: intervalo de composição semestral e frequência de pagamento semestral

A tabela a seguir lista os 12 primeiros meses da agenda de pagamento. Observe os seguintes detalhes:

- O valor na coluna "Período" aumenta em 1 a cada seis meses (isto é, a cada semestre) porque cada semestre é um novo intervalo de composição.
- Na fórmula da coluna "Valor presente", a taxa é dividida por 2, pois há dois períodos de composição por ano. O expoente é igual ao valor na coluna "Período".

| Período | Mês | Data        | Valor do pagamento | Valor presente                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/1/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 2     | 29/2/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 3     | 31/3/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 4     | 30/4/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 5     | 31/5/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 6     | 30/6/2020  | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 48.780,49 |
| 2      | 7     | 31/7/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 8     | 31/8/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 9     | 30/9/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 10    | 31/10/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 11    | 30/11/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 12    | 31/12/2020 | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 47.590,72 |

> [!NOTE]
> Se o tipo de anuidade for alterado para **anuidade devido**, o pagamento será em janeiro e julho, em vez de em junho e dezembro.

### <a name="lease-4-annual-compounding-interval-and-annual-payment-frequency"></a>Arrendamento 4: intervalo de composição anual e frequência de pagamento anual

A tabela a seguir lista os 12 primeiros meses da agenda de pagamento. Observe os seguintes detalhes:

- O valor na coluna "Período" aumenta em 1 a cada 12 meses (isto é, anualmente) porque cada ano é um novo intervalo de composição.
- Na fórmula da coluna "Valor presente", a taxa é dividida por 1, pois há um período de composição por ano. O expoente é igual ao valor na coluna "Período".

| Período | Mês | Data        | Valor do pagamento | Valor presente                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 31/1/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 2     | 29/2/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 3     | 31/3/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 4     | 30/4/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 5     | 31/5/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 6     | 30/6/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 7     | 31/7/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 8     | 31/8/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 9     | 30/9/2020  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 10    | 31/10/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 11    | 30/11/2020 | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 12    | 31/12/2020 | 50.000,00      | 50.000 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 47.619,05 |

> [!NOTE]
> Se o tipo de anuidade for alterado para **anuidade devido**, o pagamento será em janeiro em vez de dezembro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]