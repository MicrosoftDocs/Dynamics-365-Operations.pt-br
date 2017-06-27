---
title: "Depreciação de vida útil linear"
description: "Este artigo oferece uma visão geral do Método de depreciação linear com base na vida útil."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5ff3d87f610489608f0bebadd9bb4c9c5c727992
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="straight-line-service-life-depreciation"></a>Depreciação de vida útil linear

[!include[banner](../includes/banner.md)]


Este artigo oferece uma visão geral do Método de depreciação linear com base na vida útil.

Quando você configura um perfil de depreciação de ativo fixo e seleciona Vida útil linear no campo Método, na página Perfis de depreciação, os ativos com esse perfil de depreciação atribuído serão depreciados com base na vida útil total do ativo. Esse geralmente é o mesmo valor de depreciação em cada período de depreciação. 

A diferença no valor de depreciação calculado entre a vida útil linear restante e a vida útil linear é quando ocorre um ajuste lançado no ativo. 

Para configurar a depreciação linear com base na vida útil, também é preciso selecionar opções nos campos Ano de depreciação e Frequência do período na página Perfis de depreciação.

## <a name="select-a-depreciation-year"></a>Selecione um ano de depreciação
Você pode selecionar Calendário ou Fiscal no campo Ano de depreciação na página Perfis de depreciação. A seleção define as opções disponíveis no campo Frequência do período. A opção padrão é Calendário.

### <a name="calendar"></a>Calendário

Se você selecionar Calendário, será considerado um ano de 1º de janeiro a 31 de dezembro, mesmo que você tenha definido o calendário fiscal de forma diferente. 

A opção Calendário atualiza a base da depreciação que, normalmente é o valor líquido contábil menos o valor residual, no dia 1º de janeiro de cada ano. Nos exemplos a seguir deste tópico, a base de depreciação é o numerador na primeira expressão da coluna de cálculos. 

Caso selecione Calendário, você terá estas opções no campo Frequência do período, que define as datas e os valores de lançamento acumulado da depreciação durante todo o ano civil.
-   Anualmente lança um valor em 31 de dezembro.
-   Mensal lança um valor mensal ao final de cada mês do calendário.
-   Trimestral lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).
-   Semestral lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).
-   Diário lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.

Por exemplo, se você selecionar Anual, a depreciação anual é lançada apenas uma vez, no dia 31 de dezembro de cada ano. Se você selecionar Mensal, a depreciação mensal é lançada a cada mês como 1/12 do valor de depreciação anual.

### <a name="fiscal"></a>fiscal

Caso você selecione Fiscal no campo Ano de depreciação, será usada a depreciação linear com base na vida útil. Ela é calculada com base no ano fiscal, que é definido pelo calendário fiscal que é especificado para o registro de depreciação, ou pelo calendário fiscal selecionado na página Razão. Os calendários fiscais são configurados na página Calendários fiscais.

Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho. O ano fiscal pode ter mais ou menos do que 12 meses. A depreciação é ajustada automaticamente para cada período fiscal. A duração do próximo ano fiscal baseia-se nos períodos fiscais configurados quando você cria um novo ano fiscal no formulário Calendários fiscais. 

Se você selecionar Fiscal, as opções a seguir estarão disponíveis no campo Frequência do período:
-   Anual lança o valor total da depreciação calculada para o ano fiscal como um valor no último dia do ano fiscal.
-   Período fiscal calcula o valor total da depreciação para o ano fiscal, acumulado nos períodos definidos no formulário de Calendários fiscais ou no formulário do calendário fiscal.

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Exemplo: depreciação linear de um ativo fixo não alterado
Suponha que um ativo fixo tenha as características a seguir.

|                     |        |
|---------------------|--------|
| Custo de Aquisição    | 11.000 |
| valor residual       | 1.000  |
| Base de depreciação   | 10.000 |
| Anos de vida útil  | 5      |
| Depreciação anual | 2.000  |

Você tem o mesmo valor de depreciação a cada ano. (Custo de aquisição - Valor residual)/Anos de vida útil

| Período | Cálculo do valor de depreciação anual | Valor líquido contábil no final do ano |
|--------|-------------------------------------------|---------------------------------------|
| Ano 1 | (11.000 - 1.000) / 5 = 2.000              | 9.000                                 |
| Ano 2 | (11.000 - 1.000) / 5 = 2.000              | 7.000                                 |
| Ano 3 | (11.000 - 1.000) / 5 = 2.000              | 5.000                                 |
| Ano 4 | (11.000 - 1.000) / 5 = 2.000              | 3.000                                 |
| Ano 5 | (11.000 - 1.000) / 5 = 2.000              | 1.000                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a>Exemplo: depreciação linear de um ativo fixo modificado

Suponha que você adicione um ajuste de aquisição de 4.000 no ano 2 para o mesmo ativo fixo. 

A vida útil do ajuste de aquisição é igual a do ativo fixo e começa no momento de sua aquisição. Um valor líquido contábil permanecerá no final do ano 5, correspondente ao valor líquido contábil do ajuste de aquisição. A depreciação por período é calculada conforme mostrado na tabela a seguir.

| Período | Cálculo do valor de depreciação anual | Valor líquido contábil no final do ano |
|--------|-------------------------------------------|---------------------------------------|
| Ano 1 | 10.000 / 5 = 2.000                        | 11.000 - 2.000 = 9.000                |
| Ano 2 | 4.000 (ajuste de aquisição)            | 9.000 + 4.000 =13.000                 |
| Ano 2 | 14.000 / 5 = 2.800                        | 13.000 - 2.800 = 10.200               |
| Ano 3 | 14.000 / 5 = 2.800                        | 10.200 - 2.800 = 7.400                |
| Ano 4 | 14.000 / 5 = 2.800                        | 7.400 - 2.800 = 4.600                 |
| Ano 5 | 14.000 / 5 = 2.800                        | 4.600 - 2.800 = 1.800                 |
| Ano 6 | Restante 800*\*                           | 1.800 – 800 = 1.000                   |

\**Como o valor restante é menor que o valor de depreciação, somente o valor restante menos o valor residual será obtido.






