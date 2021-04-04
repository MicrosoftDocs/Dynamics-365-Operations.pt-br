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
ms.openlocfilehash: 8548fa9f64a579816e51bbd7ad9f63db290eaa38
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244198"
---
# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="24b0a-103">​Monitorar precisão da previsão​</span><span class="sxs-lookup"><span data-stu-id="24b0a-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24b0a-104">Este tópico descreve os tipos de precisão de previsão calculados pelo Microsoft Dynamics 365 Supply Chain Management e explica como é possível exibir os valores de precisão.</span><span class="sxs-lookup"><span data-stu-id="24b0a-104">This topic describes the types of forecast accuracy that Microsoft Dynamics 365 Supply Chain Management calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="24b0a-105">O Supply Chain Management calcula os seguintes tipos de precisão de previsão:</span><span class="sxs-lookup"><span data-stu-id="24b0a-105">Supply Chain Management calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="24b0a-106">Precisão da previsão histórica, em comparação à previsão histórica que o Planejamento Mestre usa com a demanda histórica.</span><span class="sxs-lookup"><span data-stu-id="24b0a-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="24b0a-107">Para exibir os valores (valores absolutos e valores percentuais) da precisão da previsão histórica, clique em **Mostrar precisão** na página **Detalhes de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="24b0a-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="24b0a-108">A precisão estimada do módulo de previsão usado para gerar as previsões.</span><span class="sxs-lookup"><span data-stu-id="24b0a-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="24b0a-109">Você pode exibir a porcentagem de precisão em **Detalhes do modelo - MAPE** na página **Detalhes de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="24b0a-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="24b0a-110">Se você usar o Aprendizado de Máquina do Microsoft Azure de previsão de demanda, o cálculo da precisão do modelo interno se baseará no conjunto de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="24b0a-110">If you use the Demand forecasting Microsoft Azure Machine Learning, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="24b0a-111">Para especificar tamanho do conjunto de dados de teste, defina o parâmetro **TEST\_SET\_SIZE\_PERCENT** na página **Parâmetros de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="24b0a-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="24b0a-112">Por exemplo, se você definir o valor como **20**, os últimos 20% dos dados históricos serão usado para calcular a precisão do modelo interno.</span><span class="sxs-lookup"><span data-stu-id="24b0a-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="additional-resources"></a><span data-ttu-id="24b0a-113">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="24b0a-113">Additional resources</span></span>
--------

[<span data-ttu-id="24b0a-114">Autorizar uma previsão ajustada</span><span class="sxs-lookup"><span data-stu-id="24b0a-114">Authorize an adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="24b0a-115">Remover exceções de dados históricos de transação ao calcular uma previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="24b0a-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]