---
title: Regras de arredondamento de cálculo de imposto
description: Este artigo fornece informações sobre as regras de arredondamento nos parâmetros de cálculo de impostos do serviço de cálculo de impostos.
author: kailiang
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0f6182ab18a5a408a6e526feec7014ccdfce8af0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858291"
---
# <a name="tax-calculation-rounding-rules"></a>Regras de arredondamento de cálculo de imposto

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre como as regras de arredondamento funcionam nos parâmetros de cálculo de impostos do serviço de cálculo de impostos.

> [!NOTE] 
> Quando o serviço de cálculo de impostos está habilitado, as regras de arredondamento nas páginas **Código do imposto** e **Grupo de impostos sobre vendas** não estão ativas.

Você pode exibir a configuração de regras de arredondamento para o serviço de cálculo de imposto na seção **Regra de arredondamento de imposto** na Guia Rápida **Cálculo** na guia **Geral** da página **Parâmetros de cálculo do imposto** (**Imposto** \> **Configuração** \> **Configuração de imposto** \> **Parâmetros de cálculo do imposto**).

[![Configuração da regra de arredondamento na página Parâmetros de cálculo do imposto](./media/tax-calculation-parameters-calculation-1.png)](./media/tax-calculation-parameters-calculation-1.png)

Os campos **Precisão de arredondamento** e **Método de arredondamento** determinam como os valores calculados no conteúdo do serviço de cálculo de imposto são arredondados.

## <a name="rounding-precision"></a>Precisão de arredondamento

Os campos de **Precisão de arredondamento** dão suporte a um valor com até seis casas decimais. Por exemplo, se você definir o campo **Precisão de arredondamento** como **0,000000**, os valores calculados serão arredondados para seis casas decimais e enviados para o Microsoft Dynamics 365 Finance. Por exemplo, se o método de arredondamento **Normal** for usado, o valor **987,1234567** será arredondado para **987,123457**.

> [!NOTE]
> O Finance arredonda os valores de acordo com as regras de arredondamento de moeda. Portanto, os valores de impostos que são mostrados e registrados nas transações são afetados pelas regras de arredondamento de cálculo de imposto e pelas regras de arredondamento de moeda.

## <a name="rounding-method"></a>Método de arredondamento

O método de arredondamento para o cálculo do imposto pode ser configurado para cada entidade legal. No campo **Método de arredondamento**, você pode selecionar entre três opções: **Normal**, **Para baixo** e **Para cima**.

### <a name="rounding-example"></a>Exemplo de arredondamento

A tabela a seguir fornece um exemplo que mostra como o valor **987,345** é arredondado para diferentes combinações de precisões e métodos de arredondamento.

<table>
<thead>
<tr>
<th rowspan="2">Método de arredondamento</th>
<th colspan="8">Precisão de arredondamento</th>
</tr>
<tr>
<th>0,00</th>
<th>0.01</th>
<th>0.10</th>
<th>1.00</th>
<th>10,00</th>
<th>0.02</th>
<th>0.05</th>
<th>0.25</th>
</tr>
</thead>
<tbody>
<tr>
<td>Normal</td>
<td>987.35</td>
<td>987.35</td>
<td>987.30</td>
<td>987.00</td>
<td>990.00</td>
<td>987.34</td>
<td>987.35</td>
<td>987.25</td>
</tr>
<tr>
<td>Para baixo</td>
<td>987.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.00</td>
<td>980.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.25</td>
</tr>
<tr>
<td>Arredondamento</td>
<td>988.00</td>
<td>987.35</td>
<td>987.40</td>
<td>988.00</td>
<td>990.00</td>
<td>987.36</td>
<td>987.35</td>
<td>987.50</td>
</tr>
</tbody>
</table>

A lógica de cálculo e arredondamento dos valores dos impostos pode ser configurada de acordo com as regras de tributação.

## <a name="rounding-by"></a>Arredondamento por 

No campo **Arredondar por**, selecione o princípio de arredondamento que se aplica aos impostos. As opções a seguir estão disponíveis:

- **Códigos de imposto** — arredondar o valor do imposto dentro de cada código de imposto.
- **Combinações de códigos de impostos** — arredondar o valor do imposto dentro da combinação de código de imposto na linha.

## <a name="calculation-method"></a>Método de cálculo

No campo **Método de cálculo**, selecione se os impostos nas faturas são calculados para cada linha ou para todas as linhas. As opções a seguir estão disponíveis:

- **Linha** — calcular o valor do imposto linha a linha. O valor do imposto em cada linha não é afetado pelo valor do imposto em outras linhas.
- **Total** — calcular o valor do imposto em todas as linhas de um documento.

### <a name="rounding-calculation-example"></a>Exemplo de cálculo de arredondamento

Esse exemplo mostra os diferentes cálculos que podem ser feitos para uma fatura, para diferentes combinações de valores de **Arredondar por** e **Método de cálculo**. Para esse exemplo, a seguinte configuração está em vigor:

- A fatura tem quatro linhas.
- Existem dois códigos de imposto: **VAT1** (10%) e **VAT2** (10%).
- A precisão de arredondamento é definida como **0,01**.
- O método de arredondamento é definido como **Para cima**.

#### <a name="rounding-by--tax-codes-and-calculation-method--line"></a>Arredondar por = Códigos de impostos e Método de cálculo = Linha

| Número da linha | Valor líquido da linha | Códigos de impostos determinados | Valor do imposto antes do arredondamento | Valor do imposto arredondado |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | VAT1                 | 1.111                      | 1.12               |
| 2           | 22.22           | VAT1; VAT2           | 2,222; 2,222               | 2,23; 2,23         |
| 3           | 33.33           | VAT1                 | 3.333                      | 3.34               |
| 4           | 44.44           | VAT1; VAT2           | 4,444; 4,444               | 4,45; 4,45         |

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--line"></a>Arredondar por = Combinações de códigos de impostos e Método de cálculo = Linha

| Número da linha | Valor líquido da linha | Códigos de impostos determinados | Valor do imposto antes do arredondamento | Valor do imposto arredondado |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | VAT1                 | 1.111                      | 1.12               |
| 2\*         | 22.22           | VAT1; VAT2           | 2,222; 2,222               | 2,23; 2,22         |
| 3           | 33.33           | VAT1                 | 3.333                      | 3.34               |
| 4\*\*       | 44.44           | VAT1; VAT2           | 4,444; 4,444               | 4,45; 4,44         |

\* Linha 2 = Arredondar\[22,22 × (10% + 10%)\] = 2,23 + 2,22

\*\* Linha 4 = Arredondar\[44,44 × (10% + 10%)\] = 4,45 + 4,44

#### <a name="rounding-by--tax-codes-and-calculation-method--total"></a>Arredondar por = Códigos de impostos e Método de cálculo = Total

| Número da linha | Valor líquido da linha | Códigos de impostos determinados | Valor do imposto antes do arredondamento | Valor do imposto arredondado |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | VAT1\*               | 1.111                      | 1.12               |
| 2           | 22.22           | VAT1\*; VAT2\*\*     | 2,222; 2,222               | 2,22; 2,23         |
| 3           | 33.33           | VAT1\*               | 3.333                      | 3.33               |
| 4           | 44.44           | VAT1\*; VAT2\*\*     | 4,444; 4,444               | 4,44; 4,44         |

\* VAT1(Linha 1, Linha 2, Linha 3, Linha 4) = Arredondar\[(11,11 + 22,22 + 33,33 + 44,44) × 10%\] = 1,12 + 2,22 + 3,33 + 4,44

\*\* VAT2 (Linha 2, Linha 4) = Arredondar\[(22,22 + 44,44) × 10%\] = 2,23 + 4,44

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--total"></a>Arredondar por = Combinações de códigos de impostos e Método de cálculo = Total

| Número da linha | Valor líquido da linha | Códigos de impostos determinados | Valor do imposto antes do arredondamento | Valor do imposto arredondado |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1\*         | 11.11           | VAT1                 | 1.111                      | 1.12               |
| 2\*\*       | 22.22           | VAT1; VAT2           | 2,222; 2,222               | 2,23; 2,22         |
| 3\*         | 33.33           | VAT1                 | 3.333                      | 3.33               |
| 4\*\*       | 44.44           | VAT1; VAT2           | 4,444; 4,444               | 4,44; 4,45         |

\* Linha 1, Linha 3 = Arredondar\[(11,11 + 33,33) × 10%\] = 1,12 + 3,33

\*\* Linha 2, Linha 4 = Arredondar\[(22,22 + 44,44) × (10% + 10%)\] = 2,23 + 2,22 + 4,44 + 4,45

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
