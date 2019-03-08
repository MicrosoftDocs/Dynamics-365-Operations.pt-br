---
title: Monitorar precisão da previsão
description: Este artigo descreve os tipos de precisão de previsão calculados pelo Microsoft Dynamics 365 for Finance and Operations e explica como é possível exibir os valores da precisão.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d7070c15f9ee23cfdba871af68d1fc5954735651
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "356406"
---
# <a name="monitor-forecast-accuracy"></a>Monitorar precisão da previsão

[!include [banner](../includes/banner.md)]

Este artigo descreve os tipos de precisão de previsão calculados pelo Microsoft Dynamics 365 for Finance and Operations e explica como é possível exibir os valores da precisão.

O Finance and Operations calcula os seguintes tipos de precisão da previsão:

-   Precisão da previsão histórica, em comparação à previsão histórica que o Planejamento Mestre usa com a demanda histórica. Para exibir os valores (valores absolutos e valores percentuais) da precisão da previsão histórica, clique em **Mostrar precisão** na página **Detalhes de previsão de demanda**.
-   A precisão estimada do módulo de previsão usado para gerar as previsões. Você pode exibir a porcentagem de precisão em **Detalhes do modelo - MAPE** na página **Detalhes de previsão de demanda**. 

**Observação:** se você usar o serviço de Aprendizado de Máquina do Microsoft Azure de previsão de demanda do Finance and Operations, o cálculo da precisão do modelo interno se baseará no conjunto de dados de teste. Para especificar tamanho do conjunto de dados de teste, defina o parâmetro **TEST\_SET\_SIZE\_PERCENT** na página **Parâmetros de previsão de demanda**. Por exemplo, se você definir o valor como **20**, os últimos 20% dos dados históricos serão usado para calcular a precisão do modelo interno.


<a name="additional-resources"></a>Recursos adicionais
--------

[Autorizando a previsão ajustada](authorize-adjusted-forecast.md)

[Remover exceções de dados históricos de transação ao calcular uma previsão de demanda](remove-historical-outliers-calculating-demand-forecast.md)



