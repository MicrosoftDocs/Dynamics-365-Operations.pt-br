---
title: ​Monitorar precisão da previsão​
description: Este tópico descreve os tipos de precisão de previsão calculados pelo Dynamics 365 Supply Chain Management e explica como é possível exibir os valores de precisão.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a21e9d6199229438b73bfdf8307030eed60c21bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977929"
---
# <a name="monitor-forecast-accuracy"></a>​Monitorar precisão da previsão​

[!include [banner](../includes/banner.md)]

Este tópico descreve os tipos de precisão de previsão calculados pelo Microsoft Dynamics 365 Supply Chain Management e explica como é possível exibir os valores de precisão.

O Supply Chain Management calcula os seguintes tipos de precisão de previsão:

-   Precisão da previsão histórica, em comparação à previsão histórica que o Planejamento Mestre usa com a demanda histórica. Para exibir os valores (valores absolutos e valores percentuais) da precisão da previsão histórica, clique em **Mostrar precisão** na página **Detalhes de previsão de demanda**.
-   A precisão estimada do módulo de previsão usado para gerar as previsões. Você pode exibir a porcentagem de precisão em **Detalhes do modelo - MAPE** na página **Detalhes de previsão de demanda**. 

> [!NOTE]
> Se você usar o Aprendizado de Máquina do Microsoft Azure de previsão de demanda, o cálculo da precisão do modelo interno se baseará no conjunto de dados de teste. Para especificar tamanho do conjunto de dados de teste, defina o parâmetro **TEST\_SET\_SIZE\_PERCENT** na página **Parâmetros de previsão de demanda**. Por exemplo, se você definir o valor como **20**, os últimos 20% dos dados históricos serão usado para calcular a precisão do modelo interno.


<a name="additional-resources"></a>Recursos adicionais
--------

[Autorizar uma previsão ajustada](authorize-adjusted-forecast.md)

[Remover exceções de dados históricos de transação ao calcular uma previsão de demanda](remove-historical-outliers-calculating-demand-forecast.md)



