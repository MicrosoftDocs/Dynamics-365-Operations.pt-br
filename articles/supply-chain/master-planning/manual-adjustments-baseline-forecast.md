---
title: Faça ajustes manuais para a previsão estatística
description: Este tópico explica como é possível fazer ajustes manuais em uma previsão de linha de base e exibir os detalhes da previsão.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90d19e9465abc71125931a7946febe2d633c3181
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251952"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>Faça ajustes manuais para a previsão estatística

[!include [banner](../includes/banner.md)]

Este tópico explica como é possível fazer ajustes manuais em uma previsão de linha de base e exibir os detalhes da previsão. 

Antes de fazer ajustes manuais, é importante que você compreenda alguns conceitos em várias páginas.

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>Grade da página Previsão de demanda ajustada
A página **Previsão de demanda ajustada** inclui uma grade com a seguinte estrutura:

-   A primeira coluna mostra os itens, as chaves de alocação de itens, as empresas etc. para os quais a previsão foi gerada. O subtítulo da página fornece uma descrição das dimensões de previsão atuais que aparecem na grade. Por exemplo, se o subtítulo da página for **Empresa/Site/Chave de alocação de item**, e um dos cabeçalhos de linha na grade for **USMF/1/D\_Alloc**, a linha mostrará a previsão para empresa USMF, site 1 e chave de alocação de item **D\_Alloc**.
-   As colunas subsequentes representam as classificações de previsão para as quais a previsão foi gerada. Cada cabeçalho de coluna representa a primeira data da classificação de previsão exibida na coluna.
-   Os valores nas células representam a previsão para um item, uma chave de alocação de item etc. nessa classificação de previsão específica.

## <a name="forecast-aggregation-and-de-aggregation"></a>Agregação de previsão e desagregação
O subtítulo da página mostra o nível da agregação de previsão. 

Por exemplo, se o subtítulo da página for **Empresa/Site/Chave de alocação/Número do item/Cor/Tamanho/Configuração/Estilo**, não haverá agregação de previsão, e a previsão aparecerá no nível do item e em suas dimensões. Para alterar a agregação, use a página **Alterar as dimensões de previsão**, que pode ser aberta no menu do aplicativo. 

Para modificar a previsão, clique em qualquer uma das células disponíveis e digite o valor de previsão ajustado. A célula editada fica imediatamente em negrito para indicar que a previsão mostrada não é a previsão que o serviço de previsão de demanda criou, mas foi ajustada manualmente. 

Se você alterar a agregação para fazer com que a página mostre mais dados agregados, use a página **Linhas de previsão de demanda** para ver as linhas de previsão individuais que compõem a previsão agregada. 

Por exemplo, você gerou a previsão no nível do item, mas você sabe que a demanda desse item aumentará em todos os sites devido a uma promoção ou a outro evento similar. Nesse caso, você pode definir a agregação para **Empresa/Chave de alocação de item/Item** na página **Alterar as dimensões de previsão**. Você pode ajustar a previsão global do item em todos os sites na grade **Previsão de demanda ajustada**. Para ver o efeito da alteração em todos os sites, abra a página **Linhas de previsão de demanda**. Nessa página, você verá uma linha para o item de cada site, a quantidade prevista ajustada e a quantidade original da previsão. 

Quando o ajuste da quantidade prevista é feito em um nível agregado, o sistema usa a alocação ponderada para distribuir a alteração entre as linhas que criam a agregação. 

Você também pode fazer ajustes manuais na página **Linhas de previsão de demanda**, modificando o valor **Quantidade total** ou as células **Quantidade** na grade de desagregação.

## <a name="viewing-details-of-the-forecast"></a>Exibindo os detalhes da previsão
Você pode abrir a página **Detalhes de previsão de demanda** para exibir mais informações sobre a previsão. 

A página **Detalhes de previsão de demanda** mostra as seguintes informações em gráficos e tabelas:

-   A demanda histórica na qual as previsões se baseiam.
-   A previsão atual usada pelo Planejamento mestre.
-   Os novos valores de previsão de demanda e os valores que serviram de base para o ajuste manual.
-   O intervalo de confiança dos valores previstos.
-   O modelo de previsão usado para gerar a previsão. Se você estiver exibindo dados agregados, verá a lista de todos os métodos usados em todas as séries de tempo agregada.
-   A precisão do modelo interno (MAPE). Para obter mais informações sobre a precisão da previsão, consulte [Monitorar a precisão da previsão](monitor-forecast-accuracy.md).

**Observações:**

-   Se você habilitar **Seleção do modelo de previsão nos detalhes da previsão de Demanda** do gerenciamento de Recursos, você poderá selecionar os modelos de previsão a serem incluídos para a previsão histórica na página **Detalhes de previsão de demanda**.
-   O intervalo de confiança exibido na seção **Previsão** da página representa a diferença entre os limites superior e inferior do intervalo de confiança. Para ver os valores dos limites superior e inferior, focalize o gráfico na seção **Demanda histórica e previsão graficamente**.
-   Se você usar o Aprendizado de Máquina do Microsoft Azure de previsão de Demanda, você pode especificar a porcentagem do nível de confiança que a previsão que é gerada deve ter. Um intervalo de confiança consiste em um intervalo de valores que representam boas estimativas para a previsão de demanda. Um nível de confiança de 95% indica que há um risco de 5% de que a previsão de demanda fique fora do intervalo de confiança.

Você também pode fazer ajustes manuais na previsão na página **Detalhes de previsão de demanda**, modificando os valores na linha **Previsão** da seção **Previsão**.

<a name="additional-resources"></a>Recursos adicionais
--------

[​Monitorar precisão da previsão​](monitor-forecast-accuracy.md)

[​Gerar uma previsão estatística​](generate-statistical-baseline-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]