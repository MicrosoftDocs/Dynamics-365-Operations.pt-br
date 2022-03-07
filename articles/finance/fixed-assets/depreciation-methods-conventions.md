---
title: Métodos e convenções de depreciação
description: Este artigo oferece uma visão geral das convenções e dos métodos de depreciação com suporte no Microsoft Dynamics 365 Finance.
author: moaamer
ms.date: 12/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f0f3b8be86225fd68df9b099e5c8e13a220a213
ms.sourcegitcommit: a5861c2fef4071e130208ad20e26cb3a42a45cf1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2021
ms.locfileid: "7927420"
---
# <a name="depreciation-methods-and-conventions"></a>Métodos e convenções de depreciação

[!include [banner](../includes/banner.md)]

Este artigo oferece uma visão geral das convenções de depreciação e dos métodos de depreciação com suporte.

Você pode selecionar vários métodos de depreciação e convenções. A finalidade dos métodos é alocar o valor depreciável do ativo fixo em períodos fiscais. O valor depreciável do ativo fixo é o preço de aquisição, reduzido por um valor de sucata, se houver. 

Se você estiver usando convenções de depreciação e modificar a última data de execução da depreciação para um ativo, o que ignora algumas depreciações, a depreciação do último ano poderá ser maior ou menor que o esperado. A depreciação é ajustada pelo número de períodos de depreciação afetados pela modificação da última data de execução.

Por exemplo, se você estiver usando a convenção de depreciação de meio ano durante três anos, a depreciação normalmente ocorrerá em três anos e meio. Se você alterar a última data de execução de depreciação durante os três anos e meio, o último ano de depreciação sairá do número de períodos afetados. Se você mover a data em três meses, o último ano terá nove meses de depreciação, quando geralmente haveria seis meses de depreciação.

Você pode selecionar uma das convenções de depreciação a seguir.


-   Semestre
-   Mês inteiro
-   Meio do trimestre
-   Meio do mês (Primeiro Dia do Mês)
-   Meio do mês (Décimo quinto dia do Mês)
-   Semestre (início do ano)
-   Semestre (próximo ano)

Você pode selecionar um dos seguintes métodos de depreciação.
-   Vida útil linear
-   Saldo decrescente
-   Manual
-   Fator
-   Consumo
-   Vida útil linear restante
-   Declínio de 200%
-   Declínio de 175%
-   Declínio de 150%
-   Declínio de 125%





## <a name="additional-resources"></a>Recursos adicionais

[Depreciação de ativo fixo](fixed-asset-depreciation.md)

[Depreciação de vida útil linear](Straight-line-service-life-depreciation.md)

[Depreciação por declínio](reduce-balance-depreciation.md)

[Depreciação manual](manual-depreciation.md)

[Depreciação por fator](factor-depreciation.md)

[Depreciação de consumo](consumption-depreciation.md)

[Depreciação da vida útil linear restante](straight-line-life-remaining-depreciation.md)

[Depreciação por declínio de 125%](125-percent-reducing-balance-depreciation.md)

[depreciação com declínio de 150%](150-percent-reducing-balance-depreciation.md)

[depreciação com declínio de 175%](175-percent-reducing-balance-depreciation.md)

[depreciação com declínio de 200%](200-percent-reducing-balance-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
