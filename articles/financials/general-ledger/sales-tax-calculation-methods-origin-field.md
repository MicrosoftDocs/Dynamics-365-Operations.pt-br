---
title: "Métodos de cálculo de imposto no campo Origem"
description: "Este artigo explica as opções no campo Origem na página de códigos de imposto e como os impostos são calculados com base na opção selecionada para um código de imposto."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1473eeb2950296f5ae6250d7a53794af3d9cba81
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="sales-tax-calculation-methods-in-the-origin-field"></a>Métodos de cálculo de imposto no campo Origem

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Este artigo explica as opções no campo Origem na página de códigos de imposto e como os impostos são calculados com base na opção selecionada para um código de imposto.

Para cada código de imposto que você cria na página Códigos de imposto, será necessário selecionar o método de cálculo a ser aplicado ao valor de base do imposto no campo Origem.

## <a name="percentage-of-net-amount"></a>Porcentagem do valor líquido
A Porcentagem do método de cálculo de valor líquido é o valor padrão no campo Origem. O imposto é calculado como uma porcentagem do valor de compra ou de venda, excluindo todos os demais impostos.
### <a name="example"></a>Exemplo

A taxa do imposto é de 25%. A linha da fatura mostra uma quantidade de 10 itens a 1,00 cada, e o cliente pode ter um desconto de linha de 10%. Valor líquido: (10 x 1,00) -10% = 9,00 Imposto: 9,00 x 25% = 2,25 Valor total: 9,00 + 2,25 = 11,25

## <a name="percentage-of-gross-amount"></a>Porcentagem do valor bruto
Se você selecionar o método Porcentagem do valor bruto, o imposto será calculado como uma porcentagem do valor das vendas brutas. O valor bruto é o valor líquido da linha mais todos os impostos e taxas da linha, com exceção de um imposto com Origem = Porcentagem do valor bruto.
### <a name="example"></a>Exemplo

A autoridade de imposto impôs impostos especiais sobre um item. Os valores do imposto são adicionados ao valor líquido antes do cálculo do imposto sobre vendas. Determinado os seguintes códigos de imposto:
-   IMPOSTO 1 = 10%, usando o método de cálculo Porcentagem do valor líquido
-   IMPOSTO 2 = 20%, usando o método de cálculo Porcentagem do valor líquido
-   IMPOSTO = 25%, usando o método de cálculo Porcentagem do valor bruto

Se o valor líquido for 10,00, o IMPOSTO 1 será 1,00 (10,00 x 10%) e o IMPOSTO 2 = 2,00 (10,00 x 20%). Os valores seriam da seguinte maneira: Valor bruto: Valor líquido + valor do IMPOSTO 1 + valor do IMPOSTO 2 (10,00 + 1,00 + 2,00) = 13,00 IMPOSTO = 13,00 x 25% = 3,25 Total de IMPOSTOS: 1,00 + 2,00 + 3,25 = 6,25 Valores totais: 10,00 + 6,25 = 16,25

| **Nota**                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Somente um código de imposto a Origem = Porcentagem do valor bruto pode ser usado para uma transação. Se mais de um código de imposto for determinado por uma transação será exibido um erro informando que os impostos não podem ser calculados. |


<a name="percentage-of-sales-tax"></a>Porcentagem do imposto
-----------------------

Quando você selecionar Porcentagem de imposto no campo Origem, o imposto é calculado como uma porcentagem do imposto selecionado no campo Imposto de imposto. O imposto selecionado no campo Imposto de imposto é calculado primeiro. Em seguida, o segundo imposto sobre vendas é calculado com base no valor do primeiro imposto sobre vendas.
### <a name="example"></a>Exemplo

Determinado os seguintes códigos de imposto:
-   IMPOSTO 1 = 10%, usando o método de Porcentagem do valor líquido
-   DIREITOS 2 = 20%, usando a Porcentagem do método de imposto, com Imposto 1 no campo Imposto do imposto
-   IMPOSTO = 25%, usando o método Porcentagem do valor bruto

Valor líquido: 10,00 IMPOSTO 1: 10,00 x 10% = 1,00 IMPOSTO 2: 1,00 x 20% = 0,20 Valor bruto: 10,00 + 1,00 + 0,20 = 11,20 IMPOSTO: 11,20 x 25% = 2,80 Total de IMPOSTOS: 1,00 + 0,20 + 2,80 = 4,00 Valor total: 10,00 + 4,00 = 14,00

| **Nota**                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Os impostos de vários níveis nos cálculos de impostos não são possíveis. Um imposto não pode ser calculado com base em um imposto que já tenha sido calculado com base em outro imposto. Os vários impostos de nível único sobre códigos de imposto podem ser calculados em uma transação. |

## <a name="amount-per-unit"></a>Valor por unidade
Quando você seleciona Valor por unidade no campo Origem, o imposto é calculado como um valor fixo por unidade multiplicado pela quantidade inserida na linha do documento. Uma unidade é selecionada no campo Unidade. O valor por unidade é especificado na página Valores do código de imposto.
### <a name="example"></a>Exemplo

O código do imposto é configurado como: R$ 1,20 por unidade = caixa Em uma linha do imposto 25 caixas de um item são vendidas O imposto é calculado como 25 x 1,20 = 30,00

| **Nota**                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se a transação for inserida na unidade diferente da especificada no código do imposto, ela será convertida automaticamente com base nas conversões de unidade que são configuradas na página Conversões de unidade. |

###  <a name="amount-per-unit-additional-option"></a>Valor por unidade, opção adicional

Na guia Cálculo, você pode selecionar se um valor por imposto calculado da unidade é calculado antes de outros códigos de imposto e adicionado ao valor líquido antes que outros códigos de imposto com a Origem = Porcentagem do valor líquido sejam calculados.

### <a name="examples"></a>Exemplos

Suponha que calculamos 2 códigos de imposto em uma transação:

-   IMPOSTO: Origem = Valor por unidade e um imposto, o valor é definido como 5,00 por unidade = peças
-   IMPOSTO: Origem = como mostrado nos os exemplos abaixo, o valor é definido como 25%

Vendemos 1 peça de um item ao preço unitário de 10,00
#### <a name="example-1"></a>Exemplo 1

IMPOSTO: Origem = Método Porcentagem do valor bruto A opção Calcular antes do imposto não tem efeito porque o IMPOSTO é calculado como uma porcentagem do valor bruto. IMPOSTO: 1 x 5,00 = 5,00 Valor bruto: 10,00 + 5,00 = 15,00 IMPOSTO: 15,00 x 25% = 3,75 Total do imposto: 5,00 + 3,75 = 8,75 Valor total: 10,00 + 8,75 = 18,75

#### <a name="example-2"></a>Exemplo 2

IMPOSTO: Origem = Porcentagem do valor líquido A opção Calcular antes do imposto não é selecionada para cálculo do IMPOSTO. Valor líquido: 10,00 IMPOSTO: 1 x 5,00 = 5,00 IMPOSTO: 10,00 x 25% = 2,50 Total de imposto: 5,00 + 2,50 = 7,50 Valor total: 10,00 + 7,50 = 17,50

#### <a name="example-3"></a>Exemplo 3

IMPOSTO: Origem = Porcentagem do valor líquido A opção Calcular antes do imposto não é selecionada para cálculo do IMPOSTO. Valor líquido: 10,00 DUTY: 1 x 5,00 = 5,00 IMPOSTO: (10,00 + 5,00) x 25% = 3,75 Imposto total: 5,00 + 3,75 = 8,75 Valor total: 10,00 + 8,75 = 18,75

#### <a name="example-4"></a>Exemplo 4

O resultado dos exemplos 1 e 3 são iguais porque só há um imposto. Suponha que você tenha dois IMPOSTOS e somente um deles esteja incluído no valor líquido para o cálculo do imposto sobre vendas: IMPOSTO 1: 5,00, usando o método de Valor por unidade, e a opção Calcular antes do imposto é selecionada IMPOSTO 2: 2.50, usando o método Valor por unidade e a opção Calcular antes do imposto selecionado Imposto: 25%, usando o método Porcentagem do valor líquido Valor líquido: 10,00 IMPOSTO 1: 1 x 5,00 = 5,00 IMPOSTO 2: 1 x 2,50 = 2,50 Valor líquido sujeito ao imposto: 10,00 + 5,00 = 15,00 IMPOSTO: 15,00 x 25% = 3,75 Imposto total, incluindo imposto: 5,00 + 2,50 + 3,75 = 11,25 Valor total: 10,00 + 11,25 = 21,25 O IMPOSTO de 25% é calculado para a soma do valor líquido (10,00) + IMPOSTO 1 (5,00) = 15,00. IMPOSTO 2 é adicionado ao valor do imposto após o cálculo do imposto ser calculado.

## <a name="calculated-percentage-of-net-amount"></a>Porcentagem do valor líquido calculada
A Porcentagem calculada do valor líquido trata o cálculo do imposto de forma diferente, dependendo da configuração do parâmetro Os valores incluem imposto do documento ou do diário.
### <a name="example-1"></a>Exemplo 1

O documento/diário é definido para Os valores incluem imposto = Sim Valor da linha da transação: 10,00 Taxa do imposto: 25% Imposto: Valor da linha de transação x Taxa do imposto (10,00 x 25%) = 2,50 Valor base do imposto (valor de origem): Valor da linha da transação - Imposto (10,00 - 2,50) = 7,50

### <a name="example-2"></a>Exemplo 2

O documento/diário é definido para Os valores incluem imposto = Não Valor da linha da transação: 10,00 Taxa do imposto: 25% Imposto: (Valor da linha de transação x Taxa do imposto / (100 - taxa do imposto) (10,00 x 25%) / (100% - 25%) = 3,33 Valor base do imposto (valor do origem): Valor da linha da transação = 10.00



<a name="additional-resources"></a>Recursos adicionais
--------

[Determinando as alíquotas de imposto com base nos campos Base marginal e Método de cálculo](marginal-base-field.md)

[Opções de cálculo de intervalo e valor total para códigos de imposto](whole-amount-interval-options-sales-tax-codes.md)




