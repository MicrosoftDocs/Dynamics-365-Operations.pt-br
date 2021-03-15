---
title: Valor de arredondamento para cálculos de depreciação
description: Este artigo discute o campo Arredondar depreciação, encontrado nas páginas no registro de depreciações.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01c8662f0731abd089c9039c16bb77e39c1d3e51
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976006"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Valor de arredondamento para cálculos de depreciação

[!include [banner](../includes/banner.md)]

Este artigo discute o campo Arredondar depreciação, encontrado nas páginas no registro de depreciações.

Montantes de amortização arredondados são definidos para cada livro. Os valores de depreciação arredondados são usados no perfil de depreciação de ativo fixo que mostra a depreciação e o valor futuro do ativo fixo, e também nas propostas de depreciação. Insira o menor valor de depreciação que é permitido para o registro. 

Independentemente de arredondamento configurado, o valor de depreciação no último período de depreciação não é arredondado. No final do último período de depreciação, o valor do ativo fixo deve ser 0 (zero) ou o valor de sucata, se o valor de sucata é usado.

### <a name="example"></a>Exemplo

Depreciação sem arredondamento é calculada como 2.444,44. Como mostrado na tabela a seguir, os valores sugeridos variam dependendo da configuração do arredondamento.

| Método de arredondamento | Valor de depreciação |
|-----------------|---------------------|
| Arredondar 0,1    | 2.444,40            |
| Arredondar 1,00   | 2.444,00            |
| Arredondar 10,00  | 2.440,00            |
| Arredondar 100,00 | 2.400,00            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]