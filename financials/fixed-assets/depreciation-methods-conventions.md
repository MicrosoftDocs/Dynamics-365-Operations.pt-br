---
title: "Métodos e convenções de depreciação"
description: "Este artigo oferece uma visão geral das convenções de depreciação e os métodos de depreciação com suporte no Microsoft Dynamics AX."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 51c053e6c130d20258e02284d097431a18bb38cb
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-methods-and-conventions"></a>Métodos e convenções de depreciação

[!include[banner](../includes/banner.md)]


Este artigo oferece uma visão geral das convenções de depreciação e os métodos de depreciação com suporte no Microsoft Dynamics AX.

Você pode selecionar vários métodos de depreciação e convenções. A finalidade dos métodos é alocar o valor depreciável do ativo fixo em períodos fiscais. O valor depreciável do ativo fixo é o preço de aquisição, reduzido por um valor de sucata, se houver. 

Se você estiver usando convenções de depreciação e modificar a última data de execução da depreciação para um ativo, o que ignora algumas depreciações, a depreciação do último ano poderá ser maior ou menor que o esperado. A depreciação é ajustada pelo número de períodos de depreciação afetados pela modificação da última data de execução.

Por exemplo, se você estiver usando a convenção de depreciação de meio ano durante três anos, a depreciação normalmente ocorrerá em 3 1/2 anos. Se você alterar a última data de execução de depreciação durante os 3 1/2 anos, o último ano de depreciação sairá do número de períodos afetados. Se você mover a data em três meses, o último ano terá nove meses de depreciação, quando geralmente haveria seis meses de depreciação.

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

 



<a name="see-also"></a>Consulte também
--------

[Depreciação de ativo fixo](fixed-asset-depreciation.md)

[Depreciação de vida útil linear](Straight-line-service-life-depreciation.md)

[Depreciação por declínio](reduce-balance-depreciation.md)

[Depreciação manual](manual-depreciation.md)

[Depreciação por fator](factor-depreciation.md)

[Depreciação de consumo](consumption-depreciation.md)

[Depreciação da vida útil linear restante](straight-line-life-remaining-depreciation.md)

[depreciação com declínio de 125%](125-percent-reducing-balance-depreciation.md)

[depreciação com declínio de 150%](150-percent-reducing-balance-depreciation.md)

[depreciação com declínio de 175%](175-percent-reducing-balance-depreciation.md)

[depreciação com declínio de 200%](200-percent-reducing-balance-depreciation.md)



