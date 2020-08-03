---
title: Exemplos e lógica de relatório de classificação por vencimento de estoque
description: Este tópico apresenta alguns exemplos que mostram como interpretar os resultados de um relatório de classificação por vencimento de estoque.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: cb7b7a055c26b53ee3acc3b872acf04fcf089eca
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597231"
---
# <a name="inventory-aging-report-examples-and-logic"></a>Exemplos e lógica de relatório de classificação por vencimento de estoque

[!include [banner](../includes/banner.md)]

Este tópico apresenta alguns exemplos que mostram como interpretar os resultados de um relatório de **classificação por vencimento de estoque**. Este relatório categoriza os valores de estoque e quantidade disponíveis para um item ou grupo de itens selecionado em vários buckets de período. Este tópico também mostra a lógica interna do relatório.

Os exemplos neste tópico mostram resultados que são apresentados em um relatório **Classificação por vencimento de estoque** padrão. No entanto, em geral, recomendamos que você use a versão de [Armazenamento do relatório de classificação por vencimento de estoque](inventory-aging-report-storage.md) desse relatório, especialmente quando houver vários itens e depósitos que devem ser processados. A classificação por vencimento de estoque salva cada relatório gerado, mostra os resultados como uma página interativa e um gráfico e permite exportar qualquer relatório salvo.

## <a name="sample-data-that-is-used-in-these-examples"></a>Dados de exemplo usados nestes exemplos

Os exemplos neste tópico se baseiam nos dados de exemplo de transação de estoque descritos nesta seção.

### <a name="storage-dimension-setup"></a>Configuração de dimensão de armazenamento

O sistema de exemplo contém a seguinte configuração de dimensões de armazenamento.

| Nome      | Ativos | Estoque físico | Estoque financeiro |
|-----------|--------|--------------------|---------------------|
| Site      | Sim    | Sim                | Sim                 |
| Depósito | Sim    | Sim                | Não                  |

### <a name="inventory-model"></a>Modelo de estoque

Para o sistema de exemplo, o modelo de estoque para os produtos liberados é *PEPS*, e a configuração **Preço de custo** para o modelo de estoque é *Incluir valor físico*.

### <a name="inventory-transactions"></a>Transações de estoque

O sistema de exemplo contém as seguintes transações de estoque para um produto liberado que tem o número de item *1.000*.

| Demonstrativo      | Site | Depósito | Recebimento   | Problema | Data física | Data financeira | Quantidade | Valor de custo | Valor de custo físico |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| Ordem de Compra | 1    | 11        | Comprado |       | 15 de março      | 15 de março       | 10       | 1.000       | 1.000                |
| Ordem de Compra | 2    | 21        | Comprado |       | 15 de março      | 15 de março       | 10       | 2,000       | 2,000                |
| Ordem de Compra | 1    | 11        | Recebida  |       | 15 de abril      |                | 5        |             | 375                  |
| Ordem de transferência | 1    | 11        |           | Vendido  | Maio de 2         | Maio de 2          | -5       | -458,33     | -458,33              |
| Ordem de transferência | 1    | 12        | Comprado |       | Maio de 2         | Maio de 2          | 5        | 458.33      | 458.33               |
| Ordem de Venda    | 1    | 12        |           | Vendido  | Maio de 3         | Maio de 3          | -1       | -91,67      | -91,67               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a>Como as quantidades e os valores em cada bucket de período são calculados

Usando os dados de exemplo descritos nas seções anteriores, você pode executar um relatório **Classificação por vencimento de estoque** com as seguintes configurações:

- **A partir da data:** *9 de maio de 2020*
- **Site:** *Exibir*
- **Depósito:** *Não*
- **Número do item:** *Total*
- **Período de classificação por vencimento:** defina esse campo para gerar buckets mensais.

Nesse caso, o conteúdo do relatório gerado será semelhante ao exemplo a seguir.

<table>
<thead>
<tr>
    <th rowspan="2">Nº de itens</th>
    <th rowspan="2">Site</th>
    <th rowspan="2">Quantidade disponível</th>
    <th rowspan="2">Valor disponível</th>
    <th rowspan="2">Quantidade do valor do estoque</th>
    <th rowspan="2">Valor do estoque</th>
    <th rowspan="2">Custo unitário médio</th>
    <th colspan="2">8/5/2020 - 1/5/2020</th>
    <th colspan="2">30/4/2020 - 1/4/2020</th>
    <th colspan="2">31/3/2020 - 1/3/2020</th>
</tr>
<tr>
    <th>P1:Quantidade</th>
    <th>P1:Valor</th>
    <th>P2:Quantidade</th>
    <th>P2:Valor</th>
    <th>P3:Quantidade</th>
    <th>P3:Valor</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>9.00</td>
    <td>825.00</td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>Totais de 1.000</strong></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>19</strong></td>
    <td><strong>2,825.00</strong></td>
</tr>
</tfoot>
</table>

Observe os seguintes detalhes neste exemplo de relatório:

- Os valores de **Quantidade de valor de estoque**, **Valor de estoque** e **Custo unitário médio** exibidos no relatório são valores para a dimensão de estoque financeira (**Site**, neste caso).

    Por exemplo, para o site 1, o relatório mostra as seguintes informações:

    - O valor de **Quantidade de valor em estoque** é *14* (= 10 + 5 – 5 + 5 – 1).
    - O valor de **Valor em estoque** é *1.283,33* (= 1.000 + 375 – 458,33 + 458,33 – 91,67).
    - O valor de **Custo unitário médio** é *91,67*.
    - O valor de **Valor disponível** e o valor de **Valor** em cada bucket de período são calculados usando-se o valor de **Custo unitário médio**.

- O relatório determina a quantidade disponível para cada bucket de período resumindo a quantidade de estoque total recebida para cada bucket de período. Em seguida, ele aplica o princípio PEPS (primeiro a entrar, primeiro a sair) para deduzir a quantidade emitida total, independentemente do modelo de estoque usado pelos itens.

Se você executar o mesmo relatório novamente, mas, desta vez, definir os campos **Site** e **Depósito** como *Exibir*, o novo relatório será semelhante ao exemplo a seguir.

<table>
<thead>
<tr>
    <th rowspan="2">Nº de itens</th>
    <th rowspan="2">Site</th>
    <th rowspan="2">Depósito</th>
    <th rowspan="2">Quantidade disponível</th>
    <th rowspan="2">Valor disponível</th>
    <th rowspan="2">Quantidade do valor do estoque</th>
    <th rowspan="2">Valor do estoque</th>
    <th rowspan="2">Custo unitário médio</th>
    <th colspan="2">8/5/2020 - 1/5/2020</th>
    <th colspan="2">30/4/2020 - 1/4/2020</th>
    <th colspan="2">31/3/2020 - 1/3/2020</th>
</tr>
<tr>
    <th>P1:Quantidade</th>
    <th>P1:Valor</th>
    <th>P2:Quantidade</th>
    <th>P2:Valor</th>
    <th>P3:Quantidade</th>
    <th>P3:Valor</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>916.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>5.00</td>
    <td>458.33</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>366.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td>4.00</td>
    <td>366.67</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>Totais de 1.000</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>366.67</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,458.33</strong></td>
</tr>
</tfoot>
</table>

Desta vez, o site 1 é dividido em duas linhas, uma para o depósito 11 e outra para o depósito 12. No entanto, os valores de **Quantidade de valor de estoque**, **Valor de estoque** e **Custo unitário médio** são iguais, já que **Depósito** não é uma dimensão de estoque financeira.

Além disso, observe que a distribuição de quantidade do site 1 é diferente. No primeiro relatório que você executou, o sistema ignorou a ordem de transferência ocorrida no mesmo site e deduziu a quantidade da fatura de venda do bucket de período **31/3/2020-1/3/2020** no site 1. No entanto, no novo relatório, o sistema deduz a quantidade da fatura de venda do bucket de período **8/5/2020-1/5/2020** no depósito 12.

## <a name="effects-of-inventory-closing"></a>Efeitos do fechamento de estoque

Se você executar o fechamento de estoque para maio e executar o relatório anterior novamente, mas definir o campo **A partir da data** como *31 de maio de 2020*, os seguintes resultados serão observados:

- Os valores **Valor de estoque** e **Custo unitário médio** são atualizados.
- O valor de **Valor disponível** e todos os valores de **Valor** em cada bucket de período são atualizados adequadamente.

O novo relatório se assemelhará ao seguinte exemplo.

<table>
<thead>
<tr>
    <th rowspan="2">Nº de itens</th>
    <th rowspan="2">Site</th>
    <th rowspan="2">Depósito</th>
    <th rowspan="2">Quantidade disponível</th>
    <th rowspan="2">Valor disponível</th>
    <th rowspan="2">Quantidade do valor do estoque</th>
    <th rowspan="2">Valor do estoque</th>
    <th rowspan="2">Custo unitário médio</th>
    <th colspan="2">31/5/2020 - 1/5/2020</th>
    <th colspan="2">30/4/2020 - 1/4/2020</th>
    <th colspan="2">31/3/2020 - 1/3/2020</th>
</tr>
<tr>
    <th>P1:Quantidade</th>
    <th>P1:Valor</th>
    <th>P2:Quantidade</th>
    <th>P2:Valor</th>
    <th>P3:Quantidade</th>
    <th>P3:Valor</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>910.70</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>0,00</td>
    <td></td>
    <td>5.00</td>
    <td>455.36</td>
    <td>5.00</td>
    <td>455.36</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>364.29</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>4.00</td>
    <td>364.29</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>Totais de 1.000</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,275.00</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>364.29</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>455.36</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,455.36</strong></td>
</tr>
</tfoot>
</table>
