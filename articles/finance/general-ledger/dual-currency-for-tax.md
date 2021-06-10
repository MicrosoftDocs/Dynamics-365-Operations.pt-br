---
title: Suporte a moeda dupla para imposto
description: Este tópico explica como estender o recurso de contabilidade de duas moedas no domínio do imposto e o impacto no cálculo e no lançamento do imposto
author: EricWang
ms.date: 12/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 3673642729aa41fa3c00a09fe8fe205edd0624c7
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "6088456"
---
# <a name="dual-currency-support-for-sales-tax"></a>Suporte a moeda dupla para imposto
[!include [banner](../includes/banner.md)]

Este tópico explica como estender a contabilidade de moeda dupla para impostos e o impacto para cálculos, lançamentos e liquidações do imposto.

O recurso de moeda dupla do Dynamics 365 Finance foi introduzido na versão 8.1 (outubro de 2018). Ele altera a maneira como as entradas de contabilidade na moeda de relatório são calculadas.

Nas versões anteriores, as transações eram convertidas para a moeda do relatório na seguinte sequência: 

- O total da transação foi calculado na moeda da transação > O valor da transação foi convertido para a moeda contábil > O valor da moeda contábil foi convertido para a moeda do relatório

Depois de habilitar o recurso de moeda dupla, as transações foram convertidas para a moeda do relatório na seguinte sequência:

- Valor na moeda de transação > Valor na moeda de relatório

Para obter mais informações sobre moeda dupla, consulte [Moeda dupla](dual-currency.md).

Como consequência do suporte para moedas duplas, dois novos recursos estão disponíveis no gerenciamento de recursos: 

- Conversão de imposto (novo na versão 10.0.13)
- Inserir dimensões financeiras nas contas de lucro/perda de ajuste de moeda realizada para liquidação de imposto sobre vendas (nova na versão 10.0.17)

O suporte de moeda dupla para impostos garante que os impostos sejam calculados com precisão na moeda do imposto e que o saldo de liquidação do imposto seja calculado com precisão na moeda contábil e na moeda de relatório.

## <a name="sales-tax-conversion"></a>Conversão de imposto

O parâmetro **Conversão de imposto** fornece duas opções para converter o valor do imposto da moeda da transação para a moeda do imposto. 

- Moeda contábil: o caminho será "Valor na moeda da transação > Valor na moeda contábil > Valor na moeda do imposto". O tipo de taxa de câmbio da moeda contábil (configurado na configuração do razão) será usado para a conversão de moeda.
- Moeda de relatório: o caminho será "Valor na moeda da transação > Valor na moeda de relatório > Valor na moeda do imposto". O tipo de taxa de câmbio da moeda de relatório (configurado na configuração do razão) será usado para a conversão de moeda.

### <a name="example"></a>Exemplo

Um exemplo simples para demonstrar essa funcionalidade é:

Configuração de moeda para razão e imposto

| Moeda da transação | Moeda contábil | Moeda de relatório | Moeda do imposto |
| -------------------- | ------------------- | ------------------ | ------------ |
| EUR                  | USD                 | GBP                | GBP          |

Taxa de câmbio

| Moeda inicial | Moeda final | Fator | Taxa de câmbio |
| ------------- | ----------- | ------ | ------------- |
| EUR           | USD         | 1      | 1.11          |
| EUR           | GBP         | 1      | 0.83          |
| USD           | GBP         | 1      | 0.75          |

Cálculo do valor do imposto em diferentes opções de parâmetros

Valor do imposto = 100 EUR

| Parâmetros de conversão do imposto | Moeda de transação (EUR) | Moeda contábil (USD) | Moeda de relatório (GBP) | Moeda de imposto (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Moeda contábil             | 100                        | 111                       | 83                       | **83.25**          |
| Moeda de relatório              | 100                        | 111                       | 83                       | **83**             |

Esse parâmetro pode ser configurado com base na necessidade de conformidade da autoridade fiscal.


### <a name="upgrade-consideration"></a>Atualizar considerações

Esse recurso se aplica apenas a novas transações. Em transações fiscais já salvas na tabela TAXTRANS, mas ainda não liquidadas, o sistema não recalcula o valor do imposto na moeda do imposto porque a taxa de câmbio no momento do lançamento do imposto já está ausente.

Para evitar o cenário anterior, recomendamos alterar esse valor do parâmetro em um novo período de liquidação de imposto (limpo) que não contenha transações fiscais não definidas. Para alterar esse valor no meio de um período de liquidação de impostos, execute o programa "Liquidar e lançar imposto" para o período atual de liquidação de impostos antes de alterar esse valor de parâmetro.

Este recurso adicionará entradas contábeis que esclarecem ganhos e perdas de trocas de moedas. As entradas serão feitas nas contas de lucros e perdas de ajuste de moeda realizadas quando a reavaliação for feita durante a liquidação do imposto sobre vendas. Para obter mais informações, consulte a seção [Saldo automático de liquidação de imposto na moeda de relatório](#tax-settlement-auto-balance-in-reporting-currency) posteriormente neste tópico.

> [!NOTE]
> Durante a liquidação, as informações de dimensões financeiras são tiradas de contas de impostos sobre vendas, que são contas de balanço e inseridas em contas de lucros e perdas de ajuste de moeda, que são contas de demonstrativo de lucros e perdas. Como as restrições ao valor das dimensões financeiras diferem entre contas de balanço e contas de demonstrativo de lucros e perdas, um erro pode ocorrer durante o processo de liquidação e lançamento de imposto sobre vendas. Para evitar ter que modificar estruturas de conta, você pode ativar a recurso "Preencher dimensões financeiras para o ajuste de moeda realizado de lucros/perdas para liquidação de imposto sobre vendas". Este recurso forçará a derivação de dimensões financeiras para contas de lucros/perdas de ajuste de moeda. 

## <a name="track-reporting-currency-tax-amount"></a>Acompanhar o valor do imposto da moeda de relatório

Três novos campos foram adicionados às tabelas relacionadas a impostos para rastrear valores na moeda de relatório. Esses campos estão nas tabelas TAXUNCOMMITTED e TAXTRANS:

- TaxAmountRep: valor do imposto na moeda de relatório
- TaxBaseAmountRep: valor base na moeda de relatório
- TaxInCostPriceRep: valor não dedutível na moeda de relatório

Para impostos salvos apenas na tabela TAXUNCOMMITTED, mas ainda não lançados, o sistema recalcula o valor do imposto na moeda de relatório no momento do lançamento e salva na tabela TAXTRANS.

Esta versão não incluirá alterações nos relatórios e formulários que mostram o valor do imposto na moeda de relatório. Alterações nos relatórios e formulários serão entregues na versão futura.



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a>Saldo automático de liquidação de imposto na moeda do relatório

Se a liquidação do imposto não for equilibrada na moeda de relatório por algum motivo, como o caminho de conversão do imposto é "Moeda contábil" ou a alteração da taxa de câmbio em um único período de liquidação de imposto, o sistema gerará automaticamente entradas contábeis para ajustar a variação do valor do imposto e compensá-lo com a conta de ganhos/perdas de câmbio realizada, definida na configuração do razão.

Usando o exemplo anterior para demonstrar esse recurso, suponha que os dados na tabela TAXTRANS no momento do lançamento sejam os seguintes:

| Parâmetros de conversão do imposto | Moeda de transação (EUR) | Moeda contábil (USD) | Moeda de relatório (GBP) | Moeda de imposto (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Moeda contábil             | 100                        | 111                       | 83                       | **83.25**          |
| Moeda de relatório              | 100                        | 111                       | 83                       | **83**             |

Ao executar o programa de liquidação do imposto no fim do mês, a entrada contábil será a seguinte.
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a>Cenário: conversão de imposto = "Moeda contábil"

| Conta principal           | Moeda de transação (GBP) | Moeda contábil (USD) | Moeda de relatório (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Imposto a pagar/receber | -83,25                     | -111                      | -83,25                   |
| Liquidação de imposto         | 83.25                      | 111                       | 83.25                    |
| Lucros/perdas realizadas     | 0                          | 0                         | -0,25                    |
| Imposto a pagar/receber | 0                          | 0                         | 0.25                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a>Cenário: conversão de imposto = "Moeda de relatório"


| Conta principal           | Moeda de transação (GBP) | Moeda contábil (USD) | Moeda de relatório (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Imposto a pagar/receber | -83                        | -110,67                   | -83                      |
| Liquidação de imposto         | 83                         | 110.67                    | 83                       |
| Lucros/perdas realizadas     | 0                          | 0.33                      | 0                        |
| Imposto a pagar/receber | 0                          | -0,33                     | 0                        |



Para obter mais informações, consulte os seguintes tópicos:

- [Moeda dupla](dual-currency.md)
- [Visão geral de imposto](indirect-taxes-overview.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
