---
title: "Mapear membros de dimensão de elemento de custo para um conjunto comum de membros de dimensão"
description: "Mapeando membros diferentes de dimensões do elemento de custo estimado na comum conjunto de elementos de custo previsto dimensões membros, você mesclam dados em um formato comum para fins de análise."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension, CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 3cbcc5e7090f1a32b0c35fdb06427b5c225e857b
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>Mapear membros de dimensão de elemento de custo para um conjunto comum de membros de dimensão

[!include[banner](../includes/banner.md)]


Mapeando membros diferentes de dimensões do elemento de custo estimado na comum conjunto de elementos de custo previsto dimensões membros, você mesclam dados em um formato comum para fins de análise.

Se for uma empresa e global obedecer os requisitos legais de contabilidade, você pode usar vários gráficos de contas. Quando você importa membros da dimensão do elemento de custo previsto de gráfico de contas diferentes, você pode encerrar acima com uma mistura de contas. Porém, essas contas podem ter a mesma realmente natureza, e você pode querer analisar e alocar custos para eles usando um formato comum.

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>Mapear membros da dimensão do elemento de custo estimado em um formato comum
O exemplo a seguir mostra como é, como controlador de custo previsto, pode criar uma nova dimensão de elemento de custo estimado na contabilização de custo previsto que os membros da dimensão do elemento de custo previsto de mapas de gráfico. de E contracheques. estrutura de contas e de plano francês estrutura de contas na comum conjunto de elementos de custo previsto de membros. Você pode usar a comum definida de membros da dimensão do elemento de custo estimado para analisar dados de custo previsto de duas entidades legais em um motivo de contabilização de custo previsto.

| Fonte: plano de contas dos EUA                                          | Fonte: plano de contas Francês                                          | Novo comum definido de membros da dimensão do elemento de custo previsto                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Membros importados dimensão de elemento de custo previsto plano de contas dos EUA | Membros importados dimensão de elemento de custo previsto do gráfico de contas Francês. | Mapeamento de membros franceses e dos EUA e dimensão de elemento de custo previsto a um conjunto comuns |
| 5001: vendas                                                           | 5001: Vendas e propaganda                                               | 5000: Vendas e propaganda                                             |
| 5030: Publicidade                                                     | 6390: Compra de estoque*\*                                                    | 7000: Limpeza de despesas                                                 |
| 7001: Limpeza de despesas                                               | 7001: Despesa de viagens                                                      | 7001: Despesa de viagens                                                   |

\***O membro francês dimensão de elemento de custo previsto de compra de estoque não é mapeado.

## <a name="currency-conversion"></a>Conversão de moeda
Vários gráficos de contas usado podem ser definidos para usar moedas diferentes. Nesse caso, verifique especifique uma conversão de moedas, de modo que os dados de custo previsto são processados usando a moeda correta, como definido no razão da contabilização de custo estimado nos membros da dimensão do elemento de custo previsto são usados. No exemplo acima, se os dólares americanos (USD) são usados no razão da contabilização de custo previsto, você deve criar uma conversão de moeda USD em euro (EUR) para processar transações dos membros mapeados dimensão de elemento de custo previsto.

## <a name="update-mappings-at-any-time"></a>Mapeamentos de atualização a qualquer momento
Você pode atualizar as definições de mapeamento para uma dimensão de elemento de custo previsto a qualquer momento. Como os mapeamentos não são efetivos data, as alterações são aplicadas na próxima vez que você processa transações de custo estimado ou cálculos de custo estimados executado.




