---
title: Configurar códigos de imposto
description: Este tópico explica como configurar códigos de imposto no Serviço de Cálculo de Imposto.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 8bdb194e7d8b704d1e58d3c25bf2e1f6bff1ba00
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883840"
---
# <a name="set-up-tax-codes"></a>Configurar códigos de imposto

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar códigos de imposto no serviço de Cálculo de Imposto. Ele inclui a configuração de um cenário simples para fazer com que o código de imposto funcione e informações sobre alguns recursos avançados do código de imposto para cenários complexos.

> [!IMPORTANT]
> A configuração dos códigos de imposto no Serviço de Cálculo de Imposto é agnóstica à entidade legal. Você pode concluir essa configuração no RCS (Regulatory Configuration Service) somente uma vez. Os códigos de imposto são sincronizados automaticamente com o Microsoft Dynamics 365 Finance quando você habilita o serviço de Cálculo de Imposto para uma entidade legal selecionada no Finance.

## <a name="simple-setup"></a>Configuração simples

Siga estas etapas para usar um código de imposto em um cenário simples, como um cenário em que haja somente uma taxa de imposto.

1. Entre no [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Acesse **Espaços de trabalho** \> **Recursos de globalização** \> **Cálculo de imposto**.
3. Selecione o recurso e a versão que deseja configurar e selecione **Editar**.
4. Na guia **Geral**, selecione **Versão da configuração**.
5. Na guia **Códigos de imposto**, selecione **Adicionar** e insira o código de imposto e uma descrição.
6. Selecione **Origem do cálculo**. Uma origem de cálculo é um grupo de métodos que estão definidos na versão da configuração de imposto que você selecionou. Para este cenário simples, selecione **Por valor líquido**.
7. Selecione **Salvar**. Mais campos serão disponibilizados, com base na origem do cálculo selecionada.
8. Na Guia Rápida **Taxas**, selecione **Adicionar** para adicionar uma taxa de imposto para o código de imposto.
9. Selecione **Salvar**.

## <a name="calculation-origin"></a>Origem do cálculo

A origem do cálculo define como o valor base do imposto e o valor do imposto são calculados. Ela é definida pela configuração de imposto no espaço de trabalho **Relatório eletrônico**. As seguintes valores estão disponíveis no campo **Origem do cálculo**:

- Por valor líquido
- Por valor bruto
- Por quantidade
- Por margem
- Imposto sobre imposto

### <a name="by-net-amount"></a>Por valor líquido

Se você selecionar **Por valor líquido** no campo **Origem do cálculo**, o valor do imposto será calculado como uma porcentagem do valor da compra ou da venda, excluindo outros códigos de imposto.

Por exemplo, a taxa de imposto é de 25%, a linha da fatura mostra uma quantidade de 10 itens a 1,00 cada, e o cliente tem um desconto de linha de 10%. Nesse caso, os valores são calculados da seguinte maneira:

- **Valor líquido:** (10 × 1,00) – 10% = 9,00 
- **Imposto:** 9,00 × 25% = 2,25 
- **Valor total da fatura:** 9,00 + 2,25 = 11,25

### <a name="by-gross-amount"></a>Por valor bruto

Se você selecionar **Por valor bruto** no campo **Origem do cálculo**, o valor do imposto será calculado como uma porcentagem do valor bruto das vendas. O valor bruto é o valor líquido da linha mais todos os impostos e taxas da linha, com exceção de um imposto em que o campo **Origem do cálculo** está definido como **Por valor bruto**.

Por exemplo, a autoridade de imposto impôs impostos especiais sobre um item. Os valores do imposto são adicionados ao valor líquido antes do cálculo do imposto. Os seguintes códigos de imposto são usados:

- **Obrigação 1** – a taxa é de 10%, e o método de cálculo **Por valor líquido** é usado.
- **Obrigação 2** – a taxa é de 20%, e o método de cálculo **Por valor líquido** é usado.
- **Taxa de imposto** – a taxa é de 25%, e o método de cálculo **Por valor bruto** é usado.

Se o valor líquido for 10,00, o valor da Obrigação 1 será 1,00 (10,00 × 10%) e o valor da Obrigação 2 será 2,00 (10,00 × 20%). Nesse caso, os valores são calculados da seguinte maneira: 

- **Valor bruto:** valor líquido + valor da Obrigação 1 + valor da Obrigação 2 = 10,00 + 1,00 + 2,00 = 13,00 
- **Valor do imposto:** 13 × 25% = 3,25 
- **Total de impostos:** 1,00 + 2,00 + 3,25 = 6,25 
- **Valor total da fatura:** 10,00 + 6,25 = 16,25

### <a name="by-quantity"></a>Por quantidade

Se você selecionar **Por quantidade** no campo **Origem do cálculo**, o valor do imposto será calculado como um valor fixo por unidade e multiplicado pela quantidade inserida na linha do documento. O valor por unidade é especificado na Guia Rápida **Taxas**.

Por exemplo, o código de imposto está configurado como 1,20 por unidade. Em uma linha da fatura de venda, foram vendidas 25 unidades de um item. Nesse caso, o valor do imposto é calculado como 25 x 1,20 = 30,00.

### <a name="by-margin"></a>Por margem

Se você selecionar **Por margem** no campo **Origem do cálculo**, o valor do imposto será calculado como uma porcentagem da margem de venda. A margem de venda é o valor de venda menos o valor de custo. Esse método de cálculo se aplica somente a transações de vendas.

Por exemplo, a taxa de imposto é de 25%, a linha da fatura mostra uma quantidade de 10 itens a 10,00 cada, e o custo por item é 6,00. Nesse caso, os valores são calculados da seguinte maneira:

- **Margem de venda:** 10 × ( 10,00 – 6,00) = 40,00
- **Valor do imposto:** 40 × 25% = 10,00
- **Valor total da fatura:** 100,00 + 10,00 = 110,00

### <a name="tax-on-tax"></a>Imposto sobre imposto

Se você selecionar **Imposto sobre imposto** no campo **Origem do cálculo**, o imposto será calculado como uma porcentagem de todos os outros valores de imposto na mesma linha do documento.

Por exemplo, os seguintes códigos de imposto são usados:

- **Obrigação 1** – a taxa é de 10%, e o método de cálculo **Por valor líquido** é usado.
- **Obrigação 2** – a taxa é de 20%, e o método de cálculo **Por valor líquido** é usado.
- **Imposto sobre obrigação** – a taxa é de 25%, e o método de cálculo **Imposto sobre imposto** é usado.

Nesse caso, os valores são calculados da seguinte maneira:

- **Valor líquido:** 10,00 
- **Obrigação 1:** 10,00 × 10% = 1,00 
- **Obrigação 2:** 10,00 × 20% = 2,00 
- **Imposto sobre obrigações:** 3, 0 × 25% = 0,75
- **Imposto total:** 1,00 + 2,00 + 0,75 = 3,75 
- **Valor total da fatura:** 10,00 + 3,75 = 13,75

## <a name="advanced-functionality"></a>Funcionalidade avançada

Esta seção explica algumas funcionalidades avançadas da configuração de códigos de imposto para cenários complexos.

### <a name="tax-exemption"></a>Isenção de imposto

Se você definir a opção **É Isento** como **Sim** na Guia Rápida **Geral**, o valor do imposto será sempre substituído por 0 (zero), independentemente da taxa de imposto real.

Você pode definir o campo **Código de Isenção** para especificar o motivo da isenção. 

É possível habilitar a pesquisa de dados mestres para o campo **Código de Isenção**. Dessa forma, você pode selecionar entre os valores de código de isenção que estão definidos no Finance. Para obter informações sobre como habilitar a pesquisa de dados mestres, consulte [Habilitar pesquisa de dados mestres para configuração de cálculo de imposto](tax-service-set-up-environment-master-data-lookup.md).

Por exemplo, a taxa de imposto é de 25%, e a opção **É Isento** está definida como **Sim** no código de imposto. A linha da fatura mostra uma quantidade de 10 itens a 1,00 cada, e o cliente tem um desconto de linha de 10%. Nesse caso, os valores são calculados da seguinte maneira:

- **Valor líquido:** (10 × 1,00) – 10% = 9,00 
- **Imposto:** 0,00 
- **Valor total da fatura:** 9,00 + 0,00 = 9,00

### <a name="use-tax"></a>Imposto sobre o uso

Se você definir a opção **É imposto sobre o uso** como **Sim** na Guia Rápida **Geral**, o valor do imposto será lançado na conta **Imposto sobre o uso a pagar** e não na conta **Resumo do fornecedor**.

Por exemplo, a taxa de imposto é de 25%, e a opção **É imposto sobre o uso** está definida como **Sim** no código de imposto. A linha da fatura mostra uma quantidade de 10 itens a 1,00 cada, e o cliente tem um desconto de linha de 10%. Nesse caso, os valores são calculados da seguinte maneira:

- **Valor líquido:** (10 × 1,00) – 10% = 9,00 
- **Imposto sobre o uso:** 9,00 × 25% = 2,25
- **Valor total da fatura:** 9,00 + 0,00 = 9,00

> [!IMPORTANT]
> Se ambas as opções **É Isento** e **É Imposto sobre o uso** estiverem definidas como **Sim** em um código de imposto, o código será reconhecido como isento de imposto para as transações de vendas e imposto sobre o uso para as transações de compra.

### <a name="reverse-charges"></a>​Encargos revertidos​

Se você definir a opção **É Encargo Revertido** como **Sim** na Guia Rápida **Geral**, a taxa de imposto poderá ser configurada como negativa. Para um cenário de encargo revertido, recomendamos configurar até dois códigos de imposto: um que tenha uma taxa de imposto positiva e o outro tenha uma taxa de imposto negativa. Os dois códigos de imposto devem ter o mesmo valor de taxa e a opção **É Encargo Revertido** deve estar definida como **Sim** no código de imposto que tenha uma taxa de imposto negativa. Para obter mais informações sobre a solução de encargo revertido no Finance, consulte [Mecanismo de encargo revertido do esquema de IVA/GST](emea-reverse-charge.md).

Por exemplo, dois códigos de imposto são determinados em uma linha da fatura. Uma taxa de imposto é de 25%. O outra taxa de imposto é de -25%, e a opção **É Encargo Revertido** está definida como **Sim** no segundo código de imposto. A linha da fatura mostra uma quantidade de 10 itens a 1,00 cada. Nesse caso, os valores são calculados da seguinte maneira:

- **Valor líquido:** (10 × 1,00) = 10,00 
- **Código de imposto 1:** 10,00 × 25% = 2,50
- **Código de imposto 2:** 10 × -25% = -2,50
- **Valor total da fatura:** = 10,00 + 2,50 - 2,50 = 10,00

### <a name="exclusion-from-base-amount-calculations"></a>Exclusão do valor base para cálculos

Se você definir a opção **Excluir do valor base para cálculo** como **Sim** na Guia Rápida **Geral**, o valor do imposto calculado do código de imposto será excluído do valor base do imposto para outros cálculos de código de imposto no cenário incluindo o preço.

Para obter mais informações, consulte [Calcular o imposto sobre os preços quando a opção Preços incluem impostos está habilitada](global-exclude-from-tax-base-amount-calculation.md).

### <a name="rates"></a>Taxas

Na Guia Rápida **Taxa**, você pode definir taxas de imposto diferentes para diferentes intervalos de valores base de imposto. Para calcular o valor do imposto, o serviço de Cálculo de Imposto sempre usa a taxa que corresponde ao valor base do imposto.

Por exemplo, as taxas de imposto podem ser configuradas conforme mostrado na tabela a seguir.

| Valor mínimo | Valor máximo | Alíquota do imposto   |
| -------------- | -------------- | ---------- |
| 0              | 1.000          | 10% |
| 1.000          | 5.000          | 15% |
| 5.000          | 10,000         | 20% |
| 10,000         | 0              | 30% |

Nesse caso, o valor do imposto é calculado da seguinte maneira:

- Se o valor base do imposto for 300,00, a taxa de imposto será 10% e o valor do imposto será 300,00 × 10% = 30,00.
- Se o valor base do imposto for 3.000,00, a taxa de imposto será 15% e o valor do imposto será 3.000,00 × 15% = 450,00.
- Se o valor base do imposto for 6.000,00, a taxa de imposto será 20% e o valor do imposto será 6.000,00 × 10% = 1.200,00.
- Se o valor base do imposto for 20.000,00, a taxa de imposto será 30% e o valor do imposto será 20.000,00 × 30% = 6.000,00.

> [!NOTE]
> Se o valor base do imposto puder corresponder ao valor máximo em uma linha e ao valor mínimo na outra linha, a base usará a taxa de imposto que corresponder ao valor base mínimo. Por exemplo, se o valor base do imposto for 1.000,00, a taxa de imposto será 15% e o valor do imposto será 1.000,00 × 15% = 150,00.

### <a name="limits"></a>Limites

Na Guia Rápida **Limites**, você pode definir limites de imposto para substituir o valor do imposto calculado se o valor do imposto se enquadrar no intervalo de mínimo/máximo.

- Se o valor do imposto calculado for maior ou igual ao valor máximo do imposto configurado na Guia Rápida **Limites**, o valor do imposto final será igual ao valor do imposto máximo.
- Se o valor do imposto calculado for inferior ao valor mínimo do imposto configurado na Guia Rápida **Limites**, o valor do imposto final será 0 (zero).

Por exemplo, os limites de imposto são configurados da seguinte maneira:

- **Valor mínimo do imposto:** 100 
- **Valor máximo do imposto:** 1.000

Se o valor do imposto calculado for 2.000, o valor do imposto final será 1.000.

Se o valor do imposto calculado for 500, o valor do imposto final será 500.

Se o valor do imposto calculado for 80, o valor do imposto final será 0 (zero).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
