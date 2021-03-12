---
title: Calcular o consumo de materiais
description: Este artigo oferece informações sobre as diversas opções relacionadas ao cálculo do consumo de material.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acccc677c855fc675d52814d7f6f0a5141bbc8af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001651"
---
# <a name="calculate-material-consumption"></a>Calcular o consumo de materiais

[!include [banner](../includes/banner.md)]

Este artigo oferece informações sobre as diversas opções relacionadas ao cálculo do consumo de material. 

As opções a seguir relacionadas ao cálculo de consumo de materiais estão disponíveis nas guias **Configuração** e **Consumo em etapas** na Guia Rápida **Detalhes da linha** da página **Lista de materiais**.

## <a name="variable-and-constant-consumption"></a>Consumo variável e constante
No campo **O consumo é**, você pode selecionar se o consumo deve ser calculado como uma quantidade constante ou uma quantidade variável Selecione **Constante** se um volume ou uma quantidade fixa for necessário para a produção, independentemente da quantidade produzida. Selecione **Variável**, que é a configuração padrão, se o valor do material necessário nas mercadorias concluídas for proporcional ao número de mercadorias concluídas produzidas.

## <a name="calculating-consumption-from-a-formula"></a>Cálculo de consumo usando uma fórmula
No campo **Fórmula**, você pode configurar diversas fórmulas para calcular o consumo de materiais. Se você usar o valor padrão, **Padrão**, o consumo não será calculado com uma fórmula. As seguintes fórmulas funcionam junto com os campos **Altura**, **Largura**, **Profundidade**, **Densidade** e **Constante**:

-   Altura \* constante
-   Altura \* largura \* constante
-   Altura \* largura \* profundidade \* constante
-   (Altura \* largura \* profundidade / densidade) \* constante

## <a name="rounding-up-and-multiples"></a>Arredondamento e múltiplos
Juntos, os campos **Arredondamento** e **Múltiplos** permitem que você arredonde o valor de consumo de materiais. Por exemplo, você pode arredondar o valor de acordo com a unidade de manuseio em que a matéria-prima é separada para a produção. As seguintes opções estão disponíveis no campo **Arredondamento**: **Quantidade**, **Medida** e **Consumo**.

### <a name="quantity"></a>Quantidade

Se você selecionar **Quantidade** como o mecanismo de arredondamento, a quantidade deverá ser um múltiplo da quantidade especificada. Por exemplo, se forem necessários números inteiros, selecione **1** no campo **Múltiplos**. Os números serão arredondados até uma quantidade que seja divisível por 1.

### <a name="measurement"></a>Medida

Normalmente, você selecionará **Medida** como o mecanismo de arredondamento quando a matéria-prima tiver dimensões específicas. Por exemplo, uma peça de tubo de metal de dois metros é necessária para uma mercadoria concluída, e o tubo de metal é armazenado em comprimentos de 4,5 metros. Nesse caso, o mecanismo de arredondamento de **Medida** pode ser usado para calcular quantos tubos de metal são necessários para produzir um número específico de peças da mercadoria concluída. Para esse exemplo, o campo **Fórmula** é definido como **Altura \* Constante**. O campo **Altura** definido como **2** para indicar o comprimento do tubo exigido para a mercadoria concluída. O campo **Múltiplo** é definido como **4,5** para indicar que o tubo será separado em comprimentos de 4,5 metros. Este é o cálculo:

1.  Número de múltiplos necessários para 10 peças da mercadoria concluída: 10 ÷ 2 = 5 peças
2.  Consumo total: 4,5 × 5 = 22,5 metros de tubo de metal

Presume-se que 0,5 metro de tubo será sucateado para cada cinco peças de tubo consumidas.

### <a name="consumption"></a>Consumo

Normalmente, você seleciona **Consumo** como o mecanismo de arredondamento quando a matéria-prima deve ser separada em quantidades inteiras de uma unidade de manuseio específica do produto. Por exemplo, 2 ml de tinta são usados para produzir uma peça de uma mercadoria concluída, e a tinta é escolhida em latas de 25 litros. Nesse caso, o mecanismo de arredondamento de **Consumo** pode ser usado para arredondar o consumo para números inteiros de 25 litros. Veja o cálculo para a quantidade de tinta necessária caso 180 peças da mercadoria concluída tenham de ser produzidas:

1.  A tinta necessária, excluindo a sucata: 180 × 2 = 360 ml.
2.  Número de latas: 360 ÷ 25 = 14,4, que é arredondado para 15
3.  A tinta necessária, incluindo a sucata: 15 × 25 = 375 ml.

## <a name="step-consumption"></a>Consumo em etapas
O consumo em etapas é usado para calcular o consumo constante em intervalos de quantidade. Se você selecionar **Consumo em etapas** no campo **Fórmula** na guia **Configuração**, você pode adicionar informações sobre as etapas na guia **Consumo da etapa**. A quantidade consumida fixa pode ser configurada em intervalos da quantidade produzida. Por exemplo, o consumo em etapas é configurado como mostrado na tabela a seguir.

| Da série | Quantidade |
|-------------|----------|
| 0,00        | 10,0000  |
| 100,00      | 20,0000  |
| 200,00      | 40,0000  |

A quantidade da lista de materiais (BOM) é 1, a quantidade de produção é 110. A fórmula para o consumo é De séries (Quantidade) = Consume. Como a quantidade de produção é 110, ela recai na "série A partir de 100". Portanto, a quantidade é 20.



