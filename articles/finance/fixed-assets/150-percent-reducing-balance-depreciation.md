---
title: Depreciação com redução de 150% do saldo
description: Este artigo apresenta uma visão geral do método de depreciação com redução de 150% do saldo.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: kfend
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f3bccb9d64851901d43b55887bb66c9b1b4e5a70
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870210"
---
# <a name="150-percent-reducing-balance-depreciation"></a>Depreciação com redução de 150% do saldo

[!include [banner](../includes/banner.md)]

Este artigo apresenta uma visão geral do método de depreciação com redução de 150% do saldo.

Ao configurar um perfil de depreciação de ativos fixos e selecionar **declínio de 150%** no campo **Método** na página **Perfis de depreciação**, os ativos fixos que são atribuídos ao perfil de depreciação são depreciados pela mesma porcentagem em cada período de depreciação. Essa porcentagem é calculada com base na vida útil do ativo. Por exemplo, se um ativo tiver uma vida útil de cinco anos, será calculada uma porcentagem de 30% (150% ÷ 5). 

Para configurar uma depreciação por declínio de 150%, você também deve selecionar opções no campo **Ano de depreciação** e no campo **Frequência do período** na página **Perfis de depreciação**. As opções disponíveis no campo **Frequência do período** variam, dependendo do valor selecionado no campo **Ano de depreciação**.

## <a name="selection-of-depreciation-year"></a>Seleção do ano da depreciação
Você pode selecionar **Calendário** ou **Fiscal** no campo **Ano de depreciação** na página **Perfis de depreciação**. 

O valor padrão é **Calendário**. Sua seleção determinará as opções disponíveis no campo **Frequência do período**. Esse campo define os valores e as datas de lançamento de acúmulo da depreciação ao longo do ano de calendário.

### <a name="calendar"></a>Calendário

Você pode optar por manter o valor padrão no campo **Ano de depreciação**, **Calendário**. 

A opção **Calendário** atualiza a base de depreciação em 1º de janeiro de cada ano. Normalmente, a base de depreciação é o valor líquido contábil menos o valor de sucata. Nos exemplos a seguir deste artigo, a base de depreciação é o numerador na primeira expressão da coluna de cálculos. 

Se você selecionar **Calendário** como o ano de depreciação, as seguintes opções ficarão disponíveis no campo **Frequência do período**:

-   **Anual** lança um valor em 31 de dezembro.
-   **Mensal** lança um valor mensal ao final de cada mês do calendário.
-   **Trimestral** lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).
-   **Semestral** lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).
-   **Diário** lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.

### <a name="fiscal"></a>Fiscal

Se você selecionar **Fiscal** no campo **Ano de depreciação**, a depreciação com declínio de 150% será calculada com base no ano fiscal especificado para o registro de depreciação, ou para o calendário fiscal selecionado na página **Razão**. Os calendários fiscais são configurados na página **Calendários fiscais**. 

Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho. O ano fiscal pode ter mais ou menos do que 12 meses. A depreciação é ajustada para cada período fiscal. A duração do próximo ano fiscal será determinada pela configuração de períodos na página **Calendários fiscais**. 

Se você selecionar **Fiscal** como o ano de depreciação, as opções a seguir ficarão disponíveis no campo **Frequência do período**:

-   **Anual** lança o valor total da depreciação calculada para o ano fiscal no último dia do ano fiscal.
-   **Período fiscal** lança o valor total da depreciação calculada para o ano fiscal. Esse valor é acumulado nos períodos fiscais definidos na página **Calendários fiscais**.

## <a name="example-of-150-reducing-balance-depreciation"></a>Exemplo de depreciação com declínio de 150%

| &nbsp;                         | &nbsp; |
|--------------------------------|--------|
| Custo de Aquisição               | 11.000 |
| Valor residual                  | 1.000  |
| Base de depreciação              | 10.000 |
| Anos de vida útil             | 5      |
| Porcentagem de depreciação anual | 30%    |

O método por declínio de 150% divide 150% pelos anos de vida útil. Essa porcentagem será multiplicada pelo valor líquido contábil do ativo para determinar o valor da depreciação anual.

| Período | Cálculo do valor de depreciação anual | Valor contábil             | Valor líquido contábil no final do ano |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| Ano 1 | (11.000 – 1.000) × 30% = 3.000                | 11.000 – 3.000 = 8.000 | 11.000 – 1.000 – 3.000 = 7.000        |
| Ano 2 | 7.000 × 30% = 2.100                           | 8.000 (2.100 -5.900)  | 7.000 (2.100 -4.900)                 |
| Ano 3 | 4.900 × 30% = 1.470                           | 5.900 – 1.470 = 4.430  | 4.900 – 1.470 = 3.430                 |

> [!NOTE]
> Normalmente, quando o valor que é calculado usando o método de depreciação por declínio de 150% se torna menor do que o valor que será calculado usando o método linear, há uma conversão para o método linear método para a vida restante.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
