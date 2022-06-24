---
title: Cenários de data de alinhamento
description: Este artigo fornece exemplos que mostram como as datas de alinhamento funcionam na cobrança de assinatura.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 102e3a104be5be287f914172160e95aff65d0b18
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872605"
---
# <a name="alignment-date-scenarios"></a>Cenários de data de alinhamento

Este artigo fornece exemplos que mostram como as datas de alinhamento funcionam na cobrança de assinatura.

Para esses exemplos, um detalhe de cobrança para uma agenda de cobrança tem uma data de alinhamento de 31 de outubro de 2019. O primeiro detalhe de cobrança para a linha termina em 31 de outubro de 2019 e é rateado adequadamente. A linha é renovada automaticamente com data de início da renovação de 11 de novembro.

> [!NOTE]
> O ano é relevante, pois pode fazer com que a data de alinhamento seja maior ou menor do que um ano. Para esses exemplos, o método de rateio é ajustado para **Mensal** na página **Parâmetros de cobrança recorrente de contrato**. Se ele estiver definido como **Diário**, alguns valores parciais serão diferentes.

## <a name="scenario-1-no-alignment"></a>Cenário 1: sem alinhamento

A agenda de cobrança é configurada com os seguintes dados:

- **Data de início:** 1º de maio de 2019
- **Data de término:** 31 de dezembro de 2024
- **Valor:** $ 1.000

| Data inicial de faturamento | Data final de faturamento | Leitura anterior | Leitura atual | Quantidade inserida | Quantidade livre | Quantidade faturável | Preço unitário |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 30/4/2020 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/05/2020 | 30/04/2021 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/05/2021 | 30/04/2022 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/05/2022 | 30/04/2023 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/05/2023 | 30/04/2024 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/05/2024 | 31/12/2024 | | | 1,00 | | 1,00 | 666.67 |

## <a name="scenario-2-shortened-alignment"></a>Cenário 2: alinhamento reduzido

A agenda de cobrança é configurada com os seguintes dados:

- **Data de início:** 1º de maio de 2019
- **Data de término:** 31 de dezembro de 2024
- **Valor:** $ 1.000
- **Data de alinhamento:** 31 de dezembro de 2019

O primeiro valor de renovação é para menos de um ano.

| Data inicial de faturamento | Data final de faturamento | Leitura anterior | Leitura atual | Quantidade inserida | Quantidade livre | Quantidade faturável | Preço unitário |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 31/12/2019 | | | 1,00 | | 1,00 | 666.67 |
| 1/1/2020 | 31/12/2020 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/01/2021 | 31/12/2021 | | | 1,00 | | 1,00 | 1.000.00 |
| 1/1/2022 | 31/12/2022 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/01/2023 | 31/12/2023 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/01/2024 | 31/12/2024 | | | 1,00 | | 1,00 | 1.000.00 |

## <a name="scenario-3-extended-alignment"></a>Cenário 3: alinhamento estendido

A agenda de cobrança é configurada com os seguintes dados:

- **Data de início:** 1º de maio de 2019
- **Data de término:** 31 de dezembro de 2024
- **Valor:** $ 1.000
- **Data de alinhamento:** 31 de dezembro de 2020

O primeiro valor de renovação é para mais de um ano.

| Data inicial de faturamento | Data final de faturamento | Leitura anterior | Leitura atual | Quantidade inserida | Quantidade livre | Quantidade faturável | Preço unitário |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 31/12/2020 | | | 1,00 | | 1,00 | 1,666.67 |
| 01/01/2021 | 31/12/2021 | | | 1,00 | | 1,00 | 1.000.00 |
| 1/1/2022 | 31/12/2022 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/01/2023 | 31/12/2023 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/01/2024 | 31/12/2024 | | | 1,00 | | 1,00 | 1.000.00 |

## <a name="scenario-4-alignment-with-a-different-end-month"></a>Cenário 4: alinhamento com um mês final diferente

A agenda de cobrança é configurada com os seguintes dados:

- **Data de início:** 1º de maio de 2019
- **Data de término:** 31 de outubro de 2024
- **Valor:** $ 1.000
- **Data de alinhamento:** 31 de dezembro de 2019

> [!NOTE]
> Este cenário não é comum.

| Data inicial de faturamento | Data final de faturamento | Leitura anterior | Leitura atual | Quantidade inserida | Quantidade livre | Quantidade faturável | Preço unitário |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 31/12/2019 | | | 1,00 | | 1,00 | 666.67 |
| 1/1/2020 | 31/12/2020 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/01/2021 | 31/12/2021 | | | 1,00 | | 1,00 | 1.000.00 |
| 1/1/2022 | 31/12/2022 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/01/2023 | 31/12/2023 | | | 1,00 | | 1,00 | 1.000.00 |
| 01/01/2024 | 31/10/2024 | | | 1,00 | | 1,00 | 833.33 |

## <a name="scenario-5-single-partial-year"></a>Cenário 5: ano parcial simples

A agenda de cobrança é configurada com os seguintes dados:

- **Data de início:** 1º de maio de 2019
- **Data de término:** 31 de dezembro de 2019
- **Valor:** $ 1.000
- **Data de alinhamento:** 31 de dezembro de 2019

Neste cenário, a data de alinhamento não é necessária. Esse cenário é comum para renovações automáticas.

| Data inicial de faturamento | Data final de faturamento | Leitura anterior | Leitura atual | Quantidade inserida | Quantidade livre | Quantidade faturável | Preço unitário |
|---|---|---|---|---|---|---|---|
| 01/05/2019 | 31/12/2019 | | | 1,00 | | 1,00 | 666.67 |

## <a name="scenario-6-calculated-dates"></a>Cenário 6: datas calculadas

O suporte e a renovação são configurados com os seguintes dados:

- **Substituir data de início:** não
- **Datas de início de suporte e renovação:** início do próximo mês
- **Data de lançamento da fatura:** 22 de junho de 2019
- **Data de alinhamento:** 31 de dezembro de 2020

| Data inicial de faturamento | Data final de faturamento | Leitura anterior | Leitura atual | Quantidade inserida | Quantidade livre | Quantidade faturável | Preço unitário |
|---|---|---|---|---|---|---|---|
| 01/07/2019 | 31/07/2019 | | | 1,00 | | 1,00 | 297.60 |
| 01/08/2019 | 31/12/2020 | | | 1,00 | | 1,00 | 6,936.00 |

## <a name="scenario-7-calculated-dates-and-future-posting"></a>Cenário 7: datas calculadas e lançamentos futuros

O suporte e a renovação são configurados com os seguintes dados:

- **Substituir data de início:** não
- **Datas de início de suporte e renovação:** início do próximo mês
- **Data de lançamento da fatura:** 22 de junho de 2019
- **Data de alinhamento:** 31 de dezembro de 2020

Para esse cenário, a data de alinhamento é alterada para 31 de dezembro de 2021.

| Data inicial de faturamento | Data final de faturamento | Leitura anterior | Leitura atual | Quantidade inserida | Quantidade livre | Quantidade faturável | Preço unitário |
|---|---|---|---|---|---|---|---|
| 22/06/2019 | 22/06/2019 | | | 1,00 | | 1,00 | 0,00 |
| 01/08/2019 | 31/12/2020 | | | 1,00 | | 1,00 | 4,250.00 |

## <a name="scenario-8-manual-dates-and-multiple-years"></a>Cenário 8: datas manuais e vários anos

O suporte e a renovação são configurados com os seguintes dados:

- **Substituir data de início:** sim
- **Data de início da renovação**: 1º de julho de 2020
- **Data de término da renovação**: 31 de dezembro de 2024
- **Data de alinhamento:** 31 de dezembro de 2021

| Data inicial de faturamento | Data final de faturamento | Leitura anterior | Leitura atual | Quantidade inserida | Quantidade livre | Quantidade faturável | Preço unitário |
|---|---|---|---|---|---|---|---|
| 22/06/2019 | 22/06/2019 | | | 1,00 | | 1,00 | 0,00 |
| 01/07/2020 | 31/12/2021 | | | 1,00 | | 1,00 | 375.00 |
| 1/1/2022 | 31/12/2022 | | | 1,00 | | 1,00 | 250,00 |
| 01/01/2023 | 31/12/2023 | | | 1,00 | | 1,00 | 250,00 |
| 01/01/2024 | 31/12/2024 | | | 1,00 | | 1,00 | 250,00 |

## <a name="scenario-9-manual-dates-multiple-years-and-a-different-end-month"></a>Cenário 9: datas manuais, vários anos e um mês final diferente

O suporte e a renovação são configurados com os seguintes dados:

- **Substituir data de início:** sim
- **Data de início da renovação**: 1º de julho de 2020
- **Data de término da renovação**: 31 de outubro de 2024
- **Data de alinhamento:** 31 de dezembro de 2021

| Data inicial de faturamento | Data final de faturamento | Leitura anterior | Leitura atual | Quantidade inserida | Quantidade livre | Quantidade faturável | Preço unitário |
|---|---|---|---|---|---|---|---|
| 22/06/2019 | 22/06/2019 | | | 1,00 | | 1,00 | 0,00 |
| 01/07/2020 | 31/12/2021 | | | 1,00 | | 1,00 | 375.00 |
| 1/1/2022 | 31/12/2022 | | | 1,00 | | 1,00 | 250,00 |
| 01/01/2023 | 31/12/2023 | | | 1,00 | | 1,00 | 250,00 |
| 01/01/2024 | 31/10/2024 | | | 1,00 | | 1,00 | 208.33 |

## <a name="scenario-10-alignment-without-proration"></a>Cenário 10: alinhamento sem rateio

O suporte e a renovação são configurados com os seguintes dados:

- **Substituir data de início:** não
- **Data de lançamento da fatura:** 22 de junho de 2019
- **Data de alinhamento:** 31 de dezembro de 2019

A data de início da renovação e as datas de alinhamento são ajustadas para que ambas as datas de início sejam posteriores à data de lançamento.

- **Data de início da renovação**: 1º de janeiro de 2020
- **Data de término da renovação**: 31 de dezembro de 2020
