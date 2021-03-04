---
title: Reduzir depreciação de saldo
description: Este artigo fornece uma visão geral do método de saldo de reduzir a depreciação.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dd4a8726ca194de2e5d95128659f3b212eaace5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440408"
---
# <a name="reduce-balance-depreciation"></a>Reduzir depreciação de saldo

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do método de saldo de reduzir a depreciação.

Quando você define um perfil de depreciação de ativo fixo e seleciona Saldo decrescente no campo Método da página Perfis de depreciação, os ativos fixos atribuídos ao perfil de depreciação são depreciados na mesma porcentagem em cada um dos períodos de depreciação.

Para definir a depreciação de saldo decrescente, você também deve fazer seleções nos campos da Guia Rápida Geral da página Perfis de depreciação. Primeiro, selecione um ano no campo Ano de depreciação. Dependendo da seleção, as opções diferentes aparecerão no campo Frequência do período, como explicado nas sessões a seguir. 

Você também deve inserir um valor no campo Porcentagem relativo ao perfil de depreciação. Caso selecione a opção Depreciação total, a base de depreciação restante será obtida no último período de depreciação e poderá ser um valor muito grande. Alguns países/regiões não usam uma alternativa ao método linear. A alternativa ocorre quando o método de depreciação alternativa for superior ou igual ao valor do perfil de depreciação principal, e o valor de depreciação obtido é o valor do método alternativo. 

Como um ativo jamais será totalmente depreciado com base no cálculo de uma porcentagem, você deve selecionar a opção Depreciação total para depreciar um ativo por completo.

## <a name="select-a-depreciation-year"></a>Selecione um ano de depreciação
Você pode selecionar Calendário ou Fiscal no campo Ano de depreciação na página Perfis de depreciação. A seleção define as opções disponíveis no campo Frequência do período. A opção padrão é Calendário.

### <a name="calendar"></a>Calendário

A opção Calendário atualiza a base da depreciação que, normalmente é o valor líquido contábil menos o valor residual, no dia 1º de janeiro de cada ano. No exemplo de depreciação do saldo decrescente que será apresentado neste tópico, a base de depreciação é o numerados da primeira expressão na coluna de cálculos. 

Caso selecione Calendário, você terá estas opções no campo Frequência do período, que define as datas e os valores de lançamento acumulado da depreciação durante todo o ano civil.

-   Anual lança no dia 31 de dezembro.
-   Mensal lança um valor mensal ao final de cada mês do calendário.
-   Trimestral lança um valor trimestral ao final de cada trimestre do calendário (31 de março, 30 de junho, 30 de setembro e 31 de dezembro).
-   Semestral lança um valor semestral no final de cada semestre do calendário (30 de junho e 31 de dezembro).
-   Diário lança o valor de depreciação do método de depreciação diária usando uma transação para cada dia.

Por exemplo, se você selecionar Anual, a depreciação anual é lançada apenas uma vez, no dia 31 de dezembro de cada ano. Se você selecionar Mensal, a depreciação mensal é lançada a cada mês como 1/12 do valor de depreciação anual.

### <a name="fiscal"></a>fiscal

Caso você selecione Fiscal no campo Ano de depreciação, será usado o método de depreciação linear. Ele é calculado com base no ano fiscal, definido na página Calendários fiscais para o calendário fiscal selecionado na página Razão. Por exemplo, no ano fiscal entre 1 de julho e 30 de junho, o cálculo da depreciação começa em 1 de julho. O ano fiscal pode ter mais ou menos do que 12 meses. A depreciação é ajustada para cada período fiscal. A duração do próximo ano fiscal baseia-se nos períodos fiscais configurados quando você cria um novo ano fiscal na página Calendários fiscais.


Se você selecionar Fiscal, as opções a seguir estarão disponíveis no campo Frequência do período:

-   Anual lança o valor total da depreciação calculada para o ano fiscal como um valor no último dia do ano fiscal.
-   Período fiscal lança o valor total da depreciação calculado para o ano fiscal, que é acumulado em períodos fiscais definidos para o calendário fiscal selecionado na página Razão, ou para o calendário fiscal selecionado para o livro de depreciação para um ativo fixo.

## <a name="example-of-reducing-balance-depreciation"></a>Exemplo de depreciação de saldo decrescente

Suponhamos que o preço de aquisição do ativo fixo seja 11.000, o valor de sucata seja 1.000 e o fator de porcentagem da depreciação seja 30. 

Usando o método Reduzindo saldo, 30 por cento da base de depreciação (valor líquido contábil menos o valor de sucata) são calculados ao final do período de depreciação anterior. A depreciação para os três primeiros anos é mostrada na tabela a seguir.

| Período | Cálculo do valor de depreciação anual | Valor líquido contábil no final do ano |
|--------|-------------------------------------------|---------------------------------------|
| Ano 1 | (11.000 - 1.000) \* 30% = 3.000           | (11.000 - 1.000) - 3.000 = 7.000      |
| Ano 2 | (7.000 - 1.000) \* 30% = 1.800            | (7.000 -1.800) = 5.200                |
| Ano 3 | (5.200 - 1.000) \* 30% = 1.260            | (5.200 - 1.260) = 3.940               |


-







[!INCLUDE[footer-include](../../includes/footer-banner.md)]