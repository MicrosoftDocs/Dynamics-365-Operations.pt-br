---
title: "depreciação com declínio de 150%"
description: "Este artigo fornece uma visão geral do método de saldo de reduzem de 150 de porcentagem de depreciação."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 0ec99c4bb0c86b1097a22fdc9785928267b80ade
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="150-percent-reducing-balance-depreciation"></a>depreciação com declínio de 150%

[!include[banner](../includes/banner.md)]


Este artigo fornece uma visão geral do método de saldo de reduzem de 150 de porcentagem de depreciação.

Ao configurar um perfil de depreciação de ativos fixos e selecionar **declínio de 150%** no campo **Método** na página **Perfis de depreciação**, os ativos fixos que são atribuídos ao perfil de depreciação são depreciados pela mesma porcentagem em cada período de depreciação. Essa porcentagem é calculada com base na vida útil do ativo. Por exemplo, se um ativo tiver uma vida útil de cinco anos, será calculada uma porcentagem de 30% (150% ÷ 5). 

Para configurar uma depreciação por declínio de 150%, você também deve selecionar opções no campo **Ano de depreciação** e no campo **Frequência do período** na página **Perfis de depreciação**. As opções disponíveis no campo **Frequência do período** variam, dependendo do valor selecionado no campo **Ano de depreciação**.

## <a name="selection-of-depreciation-year"></a>Seleção do ano da depreciação
Você pode selecionar **Calendário** ou **Fiscal** no campo **Ano de depreciação** na página **Perfis de depreciação**. 

O valor padrão é **Calendário**. Sua seleção determinará as opções disponíveis no campo **Frequência do período**. Esse campo define os valores e as datas de lançamento de acúmulo da depreciação ao longo do ano de calendário.

### <a name="calendar"></a>Calendário

Você pode optar por manter o valor padrão no campo **Ano de depreciação**, **Calendário**. 

A opção **Calendário** atualiza a base de depreciação em 1º de janeiro de cada ano. Normalmente, a base de depreciação é o valor líquido contábil menos o valor de sucata. Nos exemplos a seguir deste tópico, a base de depreciação é o numerador na primeira expressão da coluna de cálculos. 

Se você selecionar **Calendário** como o ano de depreciação, as seguintes opções ficarão disponíveis no campo **Frequência do período**:

-   **Anual** lança um valor em 31 de dezembro.
-   **Mensal** lança um valor mensal ao final de cada mês do calendário.
-   **Trimestral** lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).
-   **Semestral** lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).
-   **Diário** lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.

### <a name="fiscal"></a>fiscal

Se você selecionar **Fiscal** no campo **Ano de depreciação**, a depreciação com declínio de 150% será calculada com base no ano fiscal especificado para o registro de depreciação, ou para o calendário fiscal selecionado na página **Razão**. Os calendários fiscais são configurados na página **Calendários fiscais**. 

Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho. O ano fiscal pode ter mais ou menos do que 12 meses. A depreciação é ajustada para cada período fiscal. A duração do próximo ano fiscal será determinada pela configuração de períodos na página **Calendários fiscais**. 

Se você selecionar **Fiscal** como o ano de depreciação, as opções a seguir ficarão disponíveis no campo **Frequência do período**:

-   **Anual** lança o valor total da depreciação calculada para o ano fiscal no último dia do ano fiscal.
-   **Período fiscal**lança o valor total da depreciação calculada para o ano fiscal. Esse valor é acumulado nos períodos fiscais definidos na página **Calendários fiscais**.

## <a name="example-of-150-reducing-balance-depreciation"></a>Exemplo de depreciação com declínio de 150%
|                                |        |
|--------------------------------|--------|
| Custo de Aquisição               | 11.000 |
| valor residual                  | 1.000  |
| Base de depreciação              | 10.000 |
| Anos de vida útil             | 5      |
| 5; porcentagem de depreciação: | 30%    |

O método por declínio de 150% divide 150% pelos anos de vida útil. Essa porcentagem será multiplicada pelo valor líquido contábil do ativo para determinar o valor da depreciação anual.

| Período | Cálculo do valor de depreciação anual | Valor Contábil             | Valor líquido contábil no final do ano |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| Ano 1 | (11.000 – 1.000) × 30% = 3.000                | 11.000 – 3.000 = 8.000 | 11.000 – 1.000 – 3.000 = 7.000        |
| Ano 2 | 7.000 × 30% = 2.100                           | 8.000 (2.100 -5.900)  | 7.000 (2.100 -4.900)                 |
| Ano 3 | 4.900 × 30% = 1.470                           | 5.900 – 1.470 = 4.430  | 4.900 – 1.470 = 3.430                 |

> [!NOTE]
> Normalmente, quando o valor que é calculado usando o método de depreciação por declínio de 150% se torna menor do que o valor que será calculado usando o método linear, há uma conversão para o método linear método para a vida restante.




