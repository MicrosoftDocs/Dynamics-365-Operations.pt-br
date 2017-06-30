---
title: "Depreciação manual"
description: "Este artigo fornece uma visão geral do método de depreciação manual."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 75d176623b4fdf2198440becd0345628f873f6da
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="manual-depreciation"></a>Depreciação manual

[!include[banner](../includes/banner.md)]


Este artigo fornece uma visão geral do método de depreciação manual.

Quando um perfil de depreciação do ativo fixo é configurado e você seleciona **Manual** no campo **Método** da página **Perfis de depreciação**, a depreciação de ativos fixos atribuídos a esse perfil de depreciação é determinada pela porcentagem informada para cada intervalo do ano de calendário. Os intervalos para os quais você configura porcentagens são lançados de acordo com o valor selecionado no campo **Frequência de período** da Guia Rápida **Geral** na página **Perfis de depreciação**. Estes são os valores que você pode selecionar:

-   Anualmente
-   Mensalmente
-   Trimestral
-   Semestral
-   Diariamente

Depois de selecionar a frequência de período, clique em **Planos manuais** e configure as porcentagens de cada intervalo de lançamento. Juntos, os planos manuais e os intervalos de lançamento definem, juntos, o valor da depreciação, como mostram os exemplos posteriormente neste artigo. A depreciação manual sempre é calculada como uma porcentagem do preço de aquisição. Para a depreciação manual, as porcentagens informadas nos intervalos de depreciação não precisam somar 100%. A depreciação manual é um método de depreciação flexível que define um perfil de depreciação extraordinário na página **Registros**, como uma depreciação não periódica para fins especiais (por exemplo, impostos).

## <a name="examples"></a>Exemplos
Preço de aquisição: 11.000,00 Valor de sucata esperado: 1.000,00 A tabela a seguir mostra os intervalos e as porcentagens que você configura na página **Planos de perfil de depreciação de ativo fixo**.

| Número de intervalo | Porcentagem |
|-----------------|------------|
| 1               | 10.00      |
| 2               | 50,00      |
| 3               | 8,00       |

A tabela a seguir mostra como a depreciação é calculada para cada intervalo.

|  Número de intervalo | Cálculo do valor de depreciação anual | Valor contábil líquido no final do intervalo |
|------------------|-----------------------------------------------|-------------------------------------------|
| 1                | (11.000 – 1.000) × 10% = 1.000                | 10.000 (11.000 – 1.000)                   |
| 2                | (11.000 – 1.000) × 50% = 5.000                | 5.000 (10.000 – 5.000)                    |
| 3                | (11.000 – 1.000) × 8% = 800                   | 4.200 (5.000 – 800)                       |

Se você selecionar **Mensal** no campo**Frequência do período**, configurará 12 intervalos manuais de planejamento. A tabela a seguir mostra os valores de depreciação para os dois primeiros intervalos.

| Intervalo | Valor de depreciação            |
|----------|--------------------------------|
| Janeiro  | (11.000 – 1.000) × 10% = 1.000 |
| Fevereiro | (11.000 – 1.000) × 50% = 5.000 |

Se você selecionar **Semestral** no campo ****Frequência do período**, você configurará dois intervalos manuais de planejamento. A tabela a seguir mostra os valores de depreciação para esses dois intervalos.

| Intervalo    | Valor de depreciação            |
|-------------|--------------------------------|
| 30 de junho     | (11.000 – 1.000) × 10% = 1.000 |
| 31 de dezembro | (11.000 – 1.000) × 50% = 5.000 |

O total de porcentagens para todos os intervalos não precisa ser 100. Entretanto, você receberá uma mensagem se o valor no campo **Porcentagem cumulativa** na página **Planos de perfil de depreciação de ativo fixo** não for **100**.




