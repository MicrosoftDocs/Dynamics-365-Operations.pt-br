---
title: "Monitorar precisão da previsão"
description: "Este artigo descreve os tipos de precisão de previsão calculados pelo Microsoft Dynamics 365 for Operations e explica como é possível exibir os valores da precisão."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d3f88a4fa54217cea909c54955de05e2175db0cd
ms.lasthandoff: 03/29/2017


---

# <a name="monitor-forecast-accuracy"></a>Monitorar precisão da previsão

[!include[banner](../includes/banner.md)]


Este artigo descreve os tipos de precisão de previsão calculados pelo Microsoft Dynamics 365 for Operations e explica como é possível exibir os valores da precisão.

O Microsoft Dynamics 365 for Operations calcula os seguintes tipos de precisão da previsão:

-   Precisão da previsão histórica, em comparação à previsão histórica que o Planejamento Mestre usa com a demanda histórica. Para exibir os valores (valores absolutos e valores percentuais) da precisão da previsão histórica, clique em **Mostrar precisão** na página **Detalhes de previsão de demanda**.
-   A precisão estimada do módulo de previsão usado para gerar as previsões. Você pode exibir a porcentagem de precisão em **Detalhes do modelo - MAPE** na página **Detalhes de previsão de demanda**. 

**Observação:** se você usar o serviço de Aprendizado de Máquina do Microsoft Azure de previsão de demanda do Microsoft Dynamics 365 for Operations, o cálculo da precisão do modelo interno se baseará no conjunto de dados de teste. Para especificar tamanho do conjunto de dados de teste, defina o parâmetro **TEST\_SET\_SIZE\_PERCENT** na página **Parâmetros de previsão de demanda**. Por exemplo, se você definir o valor como **20**, os últimos 20% dos dados históricos serão usado para calcular a precisão do modelo interno.


<a name="see-also"></a>Consulte também
--------

[Autorizando a previsão ajustada](authorize-adjusted-forecast.md)

[Remover exceções de dados históricos de transação ao calcular uma previsão de demanda](remove-historical-outliers-calculating-demand-forecast.md)



