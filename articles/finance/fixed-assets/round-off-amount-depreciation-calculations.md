---
title: Valor de arredondamento para cálculos de depreciação
description: Este artigo discute o campo Arredondar depreciação, encontrado nas páginas no registro de depreciações.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: kfend
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a93842f7cca483df89188695c945edf77e118cef
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870094"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Valor de arredondamento para cálculos de depreciação

[!include [banner](../includes/banner.md)]

Este artigo discute o campo **Arredondar depreciação**, encontrado nas páginas **Configuração de registro**.

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
