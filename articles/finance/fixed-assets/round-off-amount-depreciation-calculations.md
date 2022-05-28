---
title: Valor de arredondamento de cálculos de depreciação
description: Este tópico discute o campo Arredondar depreciação, encontrado nas páginas da Configuração de registro.
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
ms.openlocfilehash: 98d6a21bea4688d6f258a98eab174485ceee2cfc
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726715"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Valor de arredondamento de cálculos de depreciação

[!include [banner](../includes/banner.md)]

Este tópico discute o campo **Arredondar depreciação**, encontrado nas páginas da **Configuração de registro**.

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
