---
title: Reduzir depreciação por declínio após uma divisão
description: Este tópico descreve o método usado em Ativos fixos para calcular a depreciação depois que um ativo é dividido usando o método por declínio.
author: moaamer
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 056808b7d4d490bc4d60aa058108d159c1d4867c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826242"
---
# <a name="reduce-balance-depreciation-after-a-split"></a>Reduzir depreciação por declínio após uma divisão

[!include [banner](../includes/banner.md)]

Este tópico descreve o método usado em Ativos fixos para calcular a depreciação depois que um ativo é dividido para outro ativo usando o método por declínio. O ano de depreciação configurado no registro de ativos é o ano fiscal. Para obter mais informações, consulte [Depreciação por declínio](reduce-balance-depreciation.md) e [Dividir um ativo fixo](tasks/split-fixed-asset.md).

Se você dividir um ativo fixo durante um período fiscal posterior ao período em que o ativo foi adquirido, a depreciação de saldo reduzida contará como o valor líquido contábil (NBV) do ativo para o ano anterior. Também serão contabilizadas as transações de ajuste de aquisição e depreciação que foram geradas da transação que dividiu o ativo. Esse comportamento supõe que o ativo foi adquirido em um ano fiscal e dividido em um ano fiscal posterior. O valor que deve ser depreciado para o ativo original após a divisão reflete o NBV do ativo antes da divisão do ativo, e a transação de ajuste de aquisição e depreciação lançada para a divisão.

Por exemplo, as seguintes condições estão em vigor:

- O período fiscal vai de 30 de junho a 1º de julho.
- A porcentagem do saldo decrescente é 18% e um ativo é adquirido em junho de 2019, a um preço de aquisição de US$ 10.000.
- A depreciação do primeiro ano fiscal é igual a US$ 18.000, a depreciação mensal é igual a US$ 150 e o ativo é depreciado até novembro de 2019, no valor de US$ 738,75.
- Em novembro de 2019, 80% do ativo é dividido para outro ativo fixo.

[![Reduzir depreciação por declínio após uma divisão](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)

O valor a ser depreciado para o ativo original é de US$ 1.822,25. Esse valor é igual ao NBV antes da transação dividida ser lançada (US$ 9.111,25), além do ajuste de aquisição que é gerado durante o lançamento da transação dividida (-US$ 8.000), mais o ajuste de depreciação gerado durante a transação dividida (US$ 711). Portanto, a depreciação para o segundo ano é de (1.822,25 × 18%) ÷ 12 = US$ 27,33.

O valor a ser depreciado para o novo ativo fixo no primeiro ano é de (8.000 × 18%) ÷ 12 = US$ 120.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]