---
title: "Monitorar precisão da previsão"
description: "Este artigo descreve os tipos de precisão de previsão calculados pelo Microsoft Dynamics 365 for Finance and Operations e explica como é possível exibir os valores da precisão."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bd84dde353972d2d259706dd9f8f3621cef04472
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="0ca89-103">Monitorar precisão da previsão</span><span class="sxs-lookup"><span data-stu-id="0ca89-103">Monitor forecast accuracy</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0ca89-104">Este artigo descreve os tipos de precisão de previsão calculados pelo Microsoft Dynamics 365 for Finance and Operations e explica como é possível exibir os valores da precisão.</span><span class="sxs-lookup"><span data-stu-id="0ca89-104">This article describes the types of forecast accuracy that Microsoft Dynamics 365 for Finance and Operations calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="0ca89-105">O Finance and Operations calcula os seguintes tipos de precisão da previsão:</span><span class="sxs-lookup"><span data-stu-id="0ca89-105">Finance and Operations calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="0ca89-106">Precisão da previsão histórica, em comparação à previsão histórica que o Planejamento Mestre usa com a demanda histórica.</span><span class="sxs-lookup"><span data-stu-id="0ca89-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="0ca89-107">Para exibir os valores (valores absolutos e valores percentuais) da precisão da previsão histórica, clique em **Mostrar precisão** na página **Detalhes de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="0ca89-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="0ca89-108">A precisão estimada do módulo de previsão usado para gerar as previsões.</span><span class="sxs-lookup"><span data-stu-id="0ca89-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="0ca89-109">Você pode exibir a porcentagem de precisão em **Detalhes do modelo - MAPE** na página **Detalhes de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="0ca89-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

<span data-ttu-id="0ca89-110">**Observação:** se você usar o serviço de Aprendizado de Máquina do Microsoft Azure de previsão de demanda do Finance and Operations, o cálculo da precisão do modelo interno se baseará no conjunto de dados de teste.</span><span class="sxs-lookup"><span data-stu-id="0ca89-110">**Note:** If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="0ca89-111">Para especificar tamanho do conjunto de dados de teste, defina o parâmetro **TEST\_SET\_SIZE\_PERCENT** na página **Parâmetros de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="0ca89-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="0ca89-112">Por exemplo, se você definir o valor como **20**, os últimos 20% dos dados históricos serão usado para calcular a precisão do modelo interno.</span><span class="sxs-lookup"><span data-stu-id="0ca89-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="see-also"></a><span data-ttu-id="0ca89-113">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0ca89-113">See also</span></span>
--------

[<span data-ttu-id="0ca89-114">Autorizando a previsão ajustada</span><span class="sxs-lookup"><span data-stu-id="0ca89-114">Authorizing the adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="0ca89-115">Remover exceções de dados históricos de transação ao calcular uma previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="0ca89-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)




