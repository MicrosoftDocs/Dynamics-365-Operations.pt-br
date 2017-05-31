---
title: "Determinando as alíquotas de imposto com base nos campos Base marginal e Métodos de cálculo"
description: "Este artigo explica como os valores com base no método de cálculo marginais dos campos determinam as taxas de impostos sobre vendas e as transações de compra."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 49cbaba7360fb3a16a70c6889d23608c7fbfa412
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a>Determinando as alíquotas de imposto com base nos campos Base marginal e Métodos de cálculo

[!include[banner](../includes/banner.md)]


Este artigo explica como os valores com base no método de cálculo marginais dos campos determinam as taxas de impostos sobre vendas e as transações de compra.

A Base marginal na Guia Rápida Cálculo na página de códigos Imposto determina qual valor será usado para separar as alíquotas apropriadas das taxas na página Valores de código de imposto. O tipo de valor no campo Base marginal em combinação com o método no campo Método de cálculo determina a lógica para encontrar as alíquotas corretas para uma transação. 

As diversas combinações de valores nesses campos produzem cálculos de imposto muito diferentes, como mostram os exemplos a seguir. Os exemplos usam os mesmos valores de intervalo de imposto, configurados para cada código de imposto na página Valores de códigos de imposto. Para abrir essa página, clique em Código do imposto &gt; Valores na página Códigos de imposto.

> [!Important]                                                                                                                  
> Se a Base marginal em um ou mais dos seus códigos de imposto se basear em valores ou em unidades de linha, o valor do campo Método de cálculo da página Parâmetros de contabilidade deverá ser definido como Linha. |

## <a name="net-amount-per-line"></a>Valor líquido por linha
Selecione essa opção para determinar as taxas de imposto com base no valor líquido das linhas da fatura, excluindo outros impostos.

### <a name="example"></a>exemplo

As taxas de impostos são configuradas nos intervalos a seguir.

| Intervalo de valores    | Taxa de imposto |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

> [!NOTE]                                                                                                             
> O limite superior de zero (0) no último intervalo significa que todos os valores que ultrapassam 100 são incluídos no intervalo.

Base marginal: **Valor líquido por linha** 

Método de cálculo: **Intervalo** 

Você compra oito luminárias que custam 25,00 cada. 

O valor líquido da linha da fatura é 200,00. 

O imposto é calculado da seguinte maneira: 

Imposto total = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35,00. 

Valor total da fatura = 200,00 + 35,00 = 235,00 

**Variação** 

Se a fatura tiver duas linhas com quatro itens em cada, o valor líquido em cada linha será 100,00, e o imposto será calculado da seguinte forma: 

Linha 1 do imposto = 50 x 30% + 50 x 20% = 15 + 10 = 25,00. 

Linha 2 do imposto = 50 x 30% + 50 x 20% = 15 + 10 = 25,00 

Total de imposto = 25,00 + 25,00 = 50,00 

Valor total da fatura = 200,00 + 50,00 = 250,00

## <a name="net-amount-per-unit"></a>Valor líquido por unidade
Selecione essa opção para determinar as taxas de imposto com base no valor de cada unidade, excluindo outros impostos. Quando uma Base marginal baseada em unidade for selecionada, então uma Unidade terá de ser especificada para o Código de imposto.

### <a name="example"></a>Exemplo

As taxas de impostos são configuradas nos intervalos a seguir.

| Valor             | Taxa de imposto |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Base marginal: **Valor líquido por unidade** 

Método de cálculo: **Valor total** 

Você compra oito luminárias que custam 25,00 cada. 

O valor líquido da linha da fatura é 200,00. 

O imposto é calculado da seguinte maneira: Imposto por unidade = 25,00 x 30% = 7,50 Total de impostos = 7.50 x 8 = 60,00 Valor total da fatura = 200,00 + 60,00 = 260,00

## <a name="net-amount-of-invoice-balance"></a>Valor líquido do saldo de fatura

Selecione essa opção para determinar as taxas de imposto no valor total da fatura, excluindo outros impostos.

### <a name="example"></a>exemplo

As taxas de impostos são configuradas nos intervalos a seguir.

| Valor            | Taxa de imposto |
|-------------------|----------|
| 0 - 50            | 30%      |
| 50 - 100          | 20%      |
| 100 -0 (&gt; 100) | 10%      |

Base marginal: **Valor líquido do saldo de fatura** 

Método de cálculo: **Intervalo** Uma fatura de venda tem duas linhas com quatro lâmpadas em cada linha por 25,00 cada. O valor líquido do saldo da fatura é 4 x 25,00 + 4 x 25,00 = 200,00. O imposto é calculado da seguinte maneira: Total de impostos = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Valor total da fatura = 200,00 + 35,00 = 235,00

## <a name="gross-amount-per-line"></a>Valor bruto por linha

Selecione essa opção para determinar as taxas de imposto com base no valor da linha, incluindo todos os outros impostos para essa linha.

> [!NOTE]
> Em um grupo de impostos sobre vendas, você só pode ter um código de imposto com essa seleção no campo Base marginal.

### <a name="example"></a>Exemplo

As taxas de impostos são configuradas nos intervalos a seguir.

| Valor             | Taxa de imposto |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Base marginal: **Valor bruto por linha** Método de cálculo: **Intervalo** Adicionalmente, há um outro código de imposto calculado para um imposto especial de 5,00 sobre cada luminária. O imposto é somado ao valor líquido antes do cálculo do imposto sobre vendas. Você compra oito luminárias que custam 25,00 cada. O valor líquido da linha da fatura é 200,00. O valor bruto da linha da fatura é 8 x 25,00 + 8 x 5,00 = 240,00. O imposto é calculado da seguinte maneira: Total de impostos = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 Total de impostos especiais = 5,00 x 8 = 40,00 Valor total da fatura = 200,00 + 39,00 + 40,00 = 279,00

**Variação** 

Se a fatura for criada com duas linhas de fatura com 4 itens em cada linha, o valor líquido por linha da fatura será 100,00. O valor bruto (incluindo o imposto especial de 4 x 5,00) por linha da fatura será 120,00, e os impostos são criados como se segue: Linha da fatura de imposto 1 = 50 x 0,30 + 50 x 0,20 + 20 x 0,.10 = 15 + 10 + 2 = 27,00 Linha da fatura de imposto 2 = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Total de impostos = 27,00 = 27,00 + 54,00 Total de impostos especiais = 5,00 x 8 = 40,00 Valor total da fatura = 200,00 + 54,00 + 40,00 = 294,00

## <a name="gross-amount-per-unit"></a>Valor bruto por unidade

Selecione essa opção para determinar as taxas de imposto com base no valor da unidade, incluindo outros impostos.

> [!NOTE]
> Em um grupo de impostos sobre vendas, você só pode ter um código de imposto com essa seleção no campo Base marginal.

### <a name="example"></a>Exemplo

As taxas de impostos são configuradas nos intervalos a seguir.

| Valor             | Taxa de imposto |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Base marginal: **Valor bruto por unidade** Há um imposto especial de 5,00 sobre cada luminária. O imposto é somado ao valor líquido antes do cálculo do imposto sobre vendas. Você compra oito luminárias que custam 25,00 cada. O valor bruto por unidade é 30,00. O imposto é calculado da seguinte maneira: Imposto por unidade = 30 x 30% = 9,00 Total de impostos = 9,00 x 8 = 72,00 Total de impostos especiais = 5,00 x 8 = 40,00 Valor total da fatura = 200,00 + 72,00 + 40,00 = 312,00

## <a name="invoice-total-incl-other-sales-tax-amounts"></a>Total da fatura incluindo outros valores de imposto

Selecione essa opção para determinar as taxas de imposto no valor total da fatura, incluindo outros impostos.
> [!NOTE]
> Em um grupo de impostos, você só pode ter um código de imposto com essa seleção no campo Base marginal.

### <a name="example"></a>Exemplo

As taxas de impostos são configuradas nos intervalos a seguir.

| Valor             | Taxa de imposto |
|--------------------|----------|
| 0 - 50             | 30%      |
| 50 - 100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Base marginal: **Total de fatura incluindo outros valores de imposto** Método de cálculo: **Intervalo**   
Há um imposto especial de 5,00 sobre cada luminária. O imposto é somado ao valor líquido antes do cálculo do imposto sobre vendas. Você compra oito luminárias que custam 25,00 cada. O valor líquido da fatura é 200,00. O valor bruto da fatura é 200,00 + (8 x 5,00) = 240,00. O imposto é calculado da seguinte maneira: Total de impostos = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Total de impostos especiais = 5,00 x 8 = 40,00 Valor total da fatura = 200,00 + 39,00 + 40,00 = 279,00

Para obter mais informações, consulte [Opções de cálculo de intervalo e valor total para códigos de imposto](whole-amount-interval-options-sales-tax-codes.md) e [Métodos de cálculo de imposto no campo Origem](sales-tax-calculation-methods-origin-field.md).




