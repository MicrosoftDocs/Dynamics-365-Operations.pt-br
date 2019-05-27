---
title: Simulação de preço
description: Este artigo fornece informações sobre a simulação de preço para cotações. A simulação de preço ajuda a avaliar o efeito de deduções no preço de venda futuro durante o processo de cotação, para que você confirme a um preço específico.
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationPriceSimulation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 12254
ms.assetid: 92be7c85-73cf-4f77-833c-d37ce779a031
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0369c1a4bbc893a86cf14bd59a2d28a7bbca15c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554635"
---
# <a name="price-simulation"></a>Simulação de preço

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre a simulação de preço para cotações. A simulação de preço ajuda a avaliar o efeito de deduções no preço de venda futuro durante o processo de cotação, para que você confirme a um preço específico.

Uma simulação de preço para uma cotação mostra um novo valor total, com base em um novo preço proposto. Uma simulação de preço também pode mostrar um novo valor para uma linha específica criada em uma cotação existente. Você pode inserir uma simulação de preço e aplicá-la posteriormente. Opcionalmente, você pode usar a cotação original sem uma simulação de preço, fazer mais alterações enquanto trabalha no processo de vendas com seu cliente.  

Uma simulação de preço não altera o preço da cotação. Se a simulação de preço for aplicada a uma cotação inteira, ela será tratada como um desconto especial no cabeçalho da cotação. Se a simulação de preço for aplicada a itens específicos, ela será tratada como um desconto especial nas linhas de cotação. O preço de venda unitário em uma linha de cotação criada não é alterado quando uma simulação de preço é aplicada. Em vez disso, um percentual de desconto correspondente à redução de preço da linha da cotação é aplicado. Quando uma simulação de preço é aplicada, o preço de venda unitário e o percentual de desconto são transferidos para a linha ou para o cabeçalho da cotação.  

>[Observação!] Ao executar uma simulação de preço, somente a moeda de venda atual é usada para criar a simulação. Entretanto, ao exibir os totais da cotação, você verá uma combinação da moeda da empresa e da moeda de venda.  

Os itens complementares que são adicionados às linhas de cotação podem desencadear descontos de linha e descontos combinados. Eles também podem desencadear descontos totais que modificam as margens e os índices de contribuição das linhas de cotação e de desconto total.  

É possível executar várias simulações de preço para controlar os impactos dos ajustes de preço nos destinos de uma cotação. Executar essas simulações permite ajustar o preço geral da cotação ou o preço de uma ou mais de suas linhas e, depois, aplicar a simulação que provavelmente ajudará a fechar a venda.  

Ao criar uma cotação, você pode configurar um alerta. Veja aqui algumas das formas como os alertas são usados:

-   Eles podem manter você a par do status das cotações na organização.
-   Eles podem desencadear a revisão de uma cotação específica ou informar você quando os limites de desconto são excedidos.

## <a name="price-simulation-and-discounts"></a>Simulação e descontos de preço
Para garantir que os descontos e preços sejam calculados corretamente, tenha cuidado ao executar simulações de preço nas cotações com descontos. Como todas as simulações de preço são tratadas como descontos especiais na linha da cotação ativa ou em toda a cotação, é preciso controlar as diferenças nos descontos.

### <a name="types-of-discounts-in-trade-agreements"></a>Tipos de desconto em contratos comerciais

Os contratos comerciais no Microsoft Dynamics 365 for Finance and Operations podem ter quatro tipos de descontos de preço. Esses descontos podem ser configurados para diferentes grupos de itens, de clientes ou de preços e podem ser limitados por data. Para evitar erros de cálculo, considere contratos comerciais ao executar simulações de preço. Os quatro tipos de descontos nos contratos comerciais são os seguintes:

-   **Preço de venda** – Os preços de venda separados podem ser especificadas para itens. Quando as linhas da cotação forem criadas, o programa pesquisará pelo preço de venda correto para um item e o transferirá para as linhas de cotação. Portanto, um acordo comercial com esse tipo de desconto não afeta a simulação de preço. O preço de venda da linha de cotação reflete o contrato comercial.
-   **Desconto de linha** – Descontos especiais são especificados para itens, dependendo do valor encomendado. Os valores da linha são tipicamente reduzidos pelo desconto de linha antes da execução de uma simulação de preço. Portanto, um acordo comercial com esse tipo de desconto afeta a simulação de preço.
-   **Desconto combinado** – Se os valores combinados excederem o limite que você definiu, as combinações predefinidas de itens pedidos disparará um desconto na ordem inteira. Os valores da linha são tipicamente reduzidos pelo desconto de linha antes da execução de uma simulação de preço. Portanto, um acordo comercial com esse tipo de desconto afeta a simulação de preço.
-   **Desconto total** – Se os valores combinados excederem o limite que você definiu, os itens encomendados predefinidos dispararão um desconto na ordem inteira. O desconto total é gerado pelas linhas da cotação. No entanto, como o desconto total é aplicado ao total da cotação como um desconto, reduz o valor total da cotação. Portanto, um acordo comercial com esse tipo de desconto afeta a simulação de preço.

### <a name="quotation-lines-and-trade-agreements"></a>Linhas de cotação e contratos comerciais

Quando você cria ou ajusta uma linha de cotação, os descontos de linha são calculados automaticamente. O preço de venda relevante será encontrado para o item, com base no contrato comercial.

## <a name="price-simulation-examples"></a>Exemplos de simulação de preço
Os exemplos a seguir usam a simulação de preços para cabeçalhos de cotação e itens de única linha.

### <a name="price-simulation-for-quotation-headers"></a>Simulação de preços para cabeçalhos de cotação

Você cria uma cotação que contém as linhas a seguir:

-   10 unidades do item BR-12 (preço de custo por unidade USD 9,52 e preço de venda por unidade USD 15,32)
-   12 unidades do item BR-14 (preço de custo por unidade USD 7,48 e preço de venda por unidade USD 13,75)

A tabela a seguir mostra as linhas de cotação.

|                            | Cálculo                          | Resultado   |
|----------------------------|--------------------------------------|----------|
| Quantidade de venda             | 10 unidades + 12 unidades                  | 22 unidades |
| Valor de venda em USD         | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Valor de custo em USD          | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Margem de contribuição em USD | 318,20 – 184,96                      | 133,24   |
| Índice de contribuição         | (\[318,20 – 184,96\] ÷ 318,20) × 100 | 41,87%   |

Você executa uma simulação de preços e aplica um desconto total de 15 por cento em toda a cotação ou no cabeçalho da cotação. A tabela a seguir mostra os novos totais da cotação após a execução da simulação de preço.

|                                                      | Cálculo                               | Resultado   |
|------------------------------------------------------|-------------------------------------------|----------|
| Quantidade de venda                                       | 10 unidades + 12 unidades                       | 22 unidades |
| Valor de venda antigo em USD                               | (10 × 15,32) + (12 × 13,75)               | 318,20   |
| Valor de custo antigo em USD                                | (10 × 9,52) + (12 × 7,48)                 | 184,96   |
| Margem de contribuição antiga em USD                       | 318,20 – 184,96                           | 133,24   |
| Índice de contribuição antigo                               | (\[318,20 – (10 × 9,52)\] ÷ 318,20) × 100 | 41,87%   |
| Simulação de preços com 15% de desconto total em USD | (15 × 318,2) ÷ 100                        | 47,73    |
| Novo valor de venda em USD                               | 318,20 – 47,73                            | 270,47   |
| Nova margem de contribuição em USD                       | 270,47 – 184,96                           | 85,51    |
| Novo índice de contribuição                               | \[(270,47 – 184,96) ÷ 270,47\] × 100      | 31,61%   |

### <a name="price-simulation-for-single-line-items"></a>Simulação de preços para itens de única linha

Você cria uma cotação que contém as linhas a seguir:

-   10 unidades do item BR-12 (preço de custo por unidade USD 9,52 e preço de venda por unidade USD 15,32)
-   12 unidades do item BR-14 (preço de custo por unidade USD 7,48 e preço de venda por unidade USD 13,75)

A tabela a seguir mostra as linhas de cotação.

|                                      | Cálculo                          | Resultado   |
|--------------------------------------|--------------------------------------|----------|
| Quantidade de venda                       | 10 unidades + 12 unidades                  | 22 unidades |
| Valor de vendas em USD de BR-12         | 10 × 15,32                           | 153,20   |
| Valor de venda em USD de BR-14         | 12 × 13,75                           | 165,00   |
| Valor de custo em USD de BR-12          | 10 × 9,52                            | 95,20    |
| Valor de custo em USD de BR-14          | 12 × 7,48                            | 89,76    |
| Margem de contribuição em USD de BR-12 | 153,20 – 95,20                       | 58,00    |
| Margem de contribuição em USD de BR-14 | 165,00 – 89,76                       | 75,24    |
| Índice de contribuição em USD de BR-12  | \[(153,20 – 95,20) ÷ 153,20\] × 100  | 37,86    |
| Índice de contribuição em USD de BR-14  | \[(165,00 – 89,76) ÷ 165,00\] × 100  | 45,60    |
| Valor de venda total em USD             | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Valor de custo total em USD              | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Margem de contribuição total em USD     | 318,20 – 184,96                      | 133,24   |
| Índice de contribuição total             | \[(318,20 – 184,96) ÷ 318,20\] × 100 | 41,87%   |

Você executa uma simulação de preços e aplica um desconto total de 10 por cento em unidades BR-12. A tabela a seguir mostra os novos totais da cotação após a execução da simulação de preço para o item de única linha.

|                                                   | Cálculo                             | Resultado   |
|---------------------------------------------------|-----------------------------------------|----------|
| Quantidade de vendas                                    | 10 unidades + 12 unidades                     | 22 unidades |
| Valor de venda antigo em USD de BR-12                  | 10 × 15,32                              | 153,20   |
| Simulação de preços com 10% de desconto para BR-12 | (10 × 153,2) ÷ 100                      | 15,32    |
| Novo valor de venda em USD de BR-12                  | (10 × 15,32) – 15,32                    | 137,88   |
| Valor de venda em USD de BR-14                      | 12 × 13,75                              | 165,00   |
| Valor de custo em USD de BR-12                       | 10 × 9,52                               | 95,20    |
| Valor de custo em USD de BR-14                       | 12 × 7,48                               | 89,76    |
| Nova margem de contribuição em USD de BR-12          | 137,88 – 95,20                          | 42,68    |
| Margem de contribuição em USD de BR-14              | 165,00 – 89,76                          | 75,24    |
| Novo índice de contribuição em USD de BR-12           | \[(137,88 – 95,20) ÷ 137,88\] × 100     | 30,95    |
| Índice de contribuição em USD de BR-14               | \[(165,00 – 89,76) ÷ 165,00\] × 100     | 45,60    |
| Novo valor total de venda em USD                      | \[(10 × 15,32) – 15,32\] + (12 × 13,75) | 302,88   |
| Valor de custo total em USD                           | (10 × 9,52) + (12 × 7,48)               | 184,96   |
| Nova margem de contribuição total em USD              | 302,88 – 184,96                         | 117,92   |
| Novo índice total de contribuição                      | \[(302,88 – 184,96) ÷ 302,88\] × 100    | 38,93%   |

A simulação de preço afeta somente a linha na qual ela é aplicada e reduz o total dessa linha.



