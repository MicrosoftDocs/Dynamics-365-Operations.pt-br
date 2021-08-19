---
title: Depreciação da vida útil linear restante
description: Este artigo oferece uma visão geral do método Vida útil linear restante.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13851
ms.assetid: 0fa2f71a-596c-414c-a6e6-8f7405a0bf81
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4c150b779ab3ea98ff3390b0dca5a7e7d892ba40a60d350f3a721e0d4e6ca3e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732996"
---
# <a name="straight-line-life-remaining-depreciation"></a>Depreciação da vida útil linear restante

[!include [banner](../includes/banner.md)]

Este artigo oferece uma visão geral do método Vida útil linear restante.

Quando você configura um perfil de depreciação de ativo fixo e seleciona **Vida útil linear restante** no campo **Método**, na página **Perfis de depreciação**, a depreciação de ativos fixos atribuídos ao perfil de depreciação se baseia na vida útil restante do ativo. O valor de depreciação geralmente é igual em cada período de depreciação. Para configurar uma depreciação depreciação restante da vida útil linear, você também deve selecionar opções no campo **Ano de depreciação** e no campo **Frequência do período** na página **Perfis de depreciação**. As opções disponíveis no campo **Frequência do período** variam, dependendo do valor selecionado no campo **Ano de depreciação**.

## <a name="select-a-depreciation-year"></a>Selecione um ano de depreciação
Você pode selecionar **Calendário** ou **Fiscal** no campo **Ano de depreciação** na página **Perfis de depreciação**. O valor padrão é **Calendário**. Sua seleção determinará as opções disponíveis no campo **Frequência do período**. Esse campo define os valores e as datas de lançamento de acúmulo da depreciação ao longo do ano de calendário.

### <a name="calendar"></a>Calendário

Se você selecionar **Calendário** no campo **_Depreciação anual_*_, um ano de 1º de janeiro a 31 de dezembro será considerado, mesmo que você tenha definido o calendário fiscal de outra maneira. A opção* _Calendário** atualiza a base de depreciação em 1º de janeiro de cada ano. Normalmente, a base de depreciação é o valor líquido contábil menos o valor residual. No exemplo a seguir deste tópico, a base de depreciação é o numerador na primeira expressão da coluna de cálculos. Se você selecionar **Calendário** como o ano de depreciação, as seguintes opções ficarão disponíveis no campo **Frequência do período**:

-   **Anual** lança um valor em 31 de dezembro.
-   **Mensal** lança um valor mensal ao final de cada mês do calendário.
-   **Trimestral** lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).
-   **Semestral** lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).
-   **Diário** lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.

Por exemplo, se você selecionar **Anual**, a depreciação anual é lançada apenas uma vez, no dia 31 de dezembro de cada ano. Se você selecionar **Mensal**, a depreciação mensal é lançada a cada mês como um doze avos do valor de depreciação anual.

### <a name="fiscal"></a>fiscal

Caso você selecione **Fiscal** no campo **Ano de depreciação**, será usada a depreciação restante da vida útil linear restante. A depreciação é calculada com base nos anos fiscais restantes. Por exemplo, no ano fiscal entre 1 de julho de 2015 e 30 de junho de 2016, o cálculo da depreciação começa em 1 de julho. O ano fiscal pode ter mais ou menos do que 12 meses. A depreciação é ajustada para cada período fiscal. A duração do próximo ano fiscal será determinada pelos períodos fiscais configurados na página **Calendários fiscais**. Se você selecionar **Fiscal** como o ano de depreciação, as opções a seguir ficarão disponíveis no campo **Frequência do período**:

-   **Anual** lança o valor total da depreciação calculada para o ano fiscal como um valor, no último dia do ano fiscal.
-   **Período fiscal** calcula o valor total da depreciação para o ano fiscal. O valor é então acumulado em períodos fiscais definidos na página **Calendários fiscais** para o calendário fiscal especificado para o registro de depreciação.

## <a name="example-of-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Exemplo de depreciação linear de um ativo fixo não alterado
Um ativo fixo tem as características a seguir.

| Campo               | Alíquota  |
|---------------------|--------|
| Custo de Aquisição    | 11,000 |
| valor residual       | 1.000  |
| Base de depreciação   | 10.000 |
| Anos de vida útil  | 5      |
| Depreciação anual | 2.000  |

O valor de depreciação é igual a cada ano: (Custo de aquisição – Valor residual) ÷ Anos de vida útil

| Período | Cálculo do valor de depreciação anual | Valor líquido contábil no final do ano |
|--------|-----------------------------------------------|---------------------------------------|
| Ano 1 | (11.000 – 1.000) ÷ 5 = 2.000                  | 9.000                                 |
| Ano 2 | (9.000 – 1.000) ÷ 4 = 2.000                   | 7.000                                 |
| Ano 3 | (7.000 – 1.000) ÷ 3 = 2.000                   | 5.000                                 |
| Ano 4 | (5.000 – 1.000) ÷ 2 = 2.000                   | 3.000                                 |
| Ano 5 | (3.000 – 1.000) ÷ 1 = 2.000                   | 1.000                                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]