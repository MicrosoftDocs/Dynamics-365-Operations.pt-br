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
ms.openlocfilehash: afdcbb98c96b2a685f64a16886b9a064ed13c2c0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967021"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a><span data-ttu-id="9e2a6-103">Faça ajustes manuais para a previsão estatística</span><span class="sxs-lookup"><span data-stu-id="9e2a6-103">Make manual adjustments to the baseline forecast</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e2a6-104">Este tópico explica como é possível fazer ajustes manuais em uma previsão de linha de base e exibir os detalhes da previsão.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-104">This topic explains how you can make manual adjustments to a baseline forecast and view details of the forecast.</span></span> 

<span data-ttu-id="9e2a6-105">Antes de fazer ajustes manuais, é importante que você compreenda alguns conceitos em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-105">Before you make manual adjustments, it's important that you understand a few concepts on various pages.</span></span>

## <a name="grid-on-the-adjusted-demand-forecast-page"></a><span data-ttu-id="9e2a6-106">Grade da página Previsão de demanda ajustada</span><span class="sxs-lookup"><span data-stu-id="9e2a6-106">Grid on the Adjusted demand forecast page</span></span>
<span data-ttu-id="9e2a6-107">A página **Previsão de demanda ajustada** inclui uma grade com a seguinte estrutura:</span><span class="sxs-lookup"><span data-stu-id="9e2a6-107">The **Adjusted demand forecast** page includes a grid that has the following structure:</span></span>

-   <span data-ttu-id="9e2a6-108">A primeira coluna mostra os itens, as chaves de alocação de itens, as empresas etc. para os quais a previsão foi gerada.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-108">The first column shows the items, item allocation keys, companies, and so on, that the forecast has been generated for.</span></span> <span data-ttu-id="9e2a6-109">O subtítulo da página fornece uma descrição das dimensões de previsão atuais que aparecem na grade.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-109">The subtitle of the page provides a description of the current forecast dimensions that are shown in the grid.</span></span> <span data-ttu-id="9e2a6-110">Por exemplo, se o subtítulo da página for **Empresa/Site/Chave de alocação de item**, e um dos cabeçalhos de linha na grade for **USMF/1/D\_Alloc**, a linha mostrará a previsão para empresa USMF, site 1 e chave de alocação de item **D\_Alloc**.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-110">For example, if the subtitle of the page is **Company / Site / Item allocation key**, and one of the row headers in the grid is **USMF / 1 / D\_Alloc**, that row shows the forecast for the USMF company, site 1, and the **D\_Alloc** item allocation key.</span></span>
-   <span data-ttu-id="9e2a6-111">As colunas subsequentes representam as classificações de previsão para as quais a previsão foi gerada.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-111">Subsequent columns represent the forecast buckets that the forecast has been generated for.</span></span> <span data-ttu-id="9e2a6-112">Cada cabeçalho de coluna representa a primeira data da classificação de previsão exibida na coluna.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-112">Each column header is the first date of the forecast bucket that the column shows.</span></span>
-   <span data-ttu-id="9e2a6-113">Os valores nas células representam a previsão para um item, uma chave de alocação de item etc. nessa classificação de previsão específica.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-113">The values in the cells represent the forecast for one item, item allocation key, and so on, for that specific forecast bucket.</span></span>

## <a name="forecast-aggregation-and-de-aggregation"></a><span data-ttu-id="9e2a6-114">Agregação de previsão e desagregação</span><span class="sxs-lookup"><span data-stu-id="9e2a6-114">Forecast aggregation and de-aggregation</span></span>
<span data-ttu-id="9e2a6-115">O subtítulo da página mostra o nível da agregação de previsão.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-115">The subtitle of the page shows the level of forecast aggregation.</span></span> 

<span data-ttu-id="9e2a6-116">Por exemplo, se o subtítulo da página for **Empresa/Site/Chave de alocação/Número do item/Cor/Tamanho/Configuração/Estilo**, não haverá agregação de previsão, e a previsão aparecerá no nível do item e em suas dimensões.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-116">For example, if the subtitle of the page is **Company / Site / Allocation key / Item number / Color / Size / Configuration / Style**, there is no forecast aggregation, and the forecast is shown at the level of the item and its dimensions.</span></span> <span data-ttu-id="9e2a6-117">Para alterar a agregação, use a página **Alterar as dimensões de previsão**, que pode ser aberta no menu do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-117">To change the aggregation, use the **Change forecast dimensions** page, which you can open from the application menu.</span></span> 

<span data-ttu-id="9e2a6-118">Para modificar a previsão, clique em qualquer uma das células disponíveis e digite o valor de previsão ajustado.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-118">To modify the forecast, click in any of the cells that are available, and type the adjusted forecast value.</span></span> <span data-ttu-id="9e2a6-119">A célula editada fica imediatamente em negrito para indicar que a previsão mostrada não é a previsão que o serviço de previsão de demanda criou, mas foi ajustada manualmente.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-119">The edited cell immediately becomes bold to indicate that the forecast that it shows isn't the forecast that the demand forecasting service created, but has been manually adjusted.</span></span> 

<span data-ttu-id="9e2a6-120">Se você alterar a agregação para fazer com que a página mostre mais dados agregados, use a página **Linhas de previsão de demanda** para ver as linhas de previsão individuais que compõem a previsão agregada.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-120">If you change the aggregation to make the page show more aggregated data, you can use the **Demand forecast lines** page to see the individual forecast lines that make up the aggregated forecast.</span></span> 

<span data-ttu-id="9e2a6-121">Por exemplo, você gerou a previsão no nível do item, mas você sabe que a demanda desse item aumentará em todos os sites devido a uma promoção ou a outro evento similar.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-121">For example, you've generated the forecast at the item level, but you know that the demand for this item will increase across all sites because of a promotion or another similar event.</span></span> <span data-ttu-id="9e2a6-122">Nesse caso, você pode definir a agregação para **Empresa/Chave de alocação de item/Item** na página **Alterar as dimensões de previsão**.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-122">In this case, you can set the aggregation to **Company / Item allocation key / Item** on the **Change forecast dimensions** page.</span></span> <span data-ttu-id="9e2a6-123">Você pode ajustar a previsão global do item em todos os sites na grade **Previsão de demanda ajustada**.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-123">You can adjust the global forecast for the item across all sites in the **Adjusted demand forecast** grid.</span></span> <span data-ttu-id="9e2a6-124">Para ver o efeito da alteração em todos os sites, abra a página **Linhas de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-124">To see the effect of your change across all sites, open the **Demand forecast lines** page.</span></span> <span data-ttu-id="9e2a6-125">Nessa página, você verá uma linha para o item de cada site, a quantidade prevista ajustada e a quantidade original da previsão.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-125">On this page, you will see one line for the item for each site, the adjusted forecast quantity, and the original forecast quantity.</span></span> 

<span data-ttu-id="9e2a6-126">Quando o ajuste da quantidade prevista é feito em um nível agregado, o sistema usa a alocação ponderada para distribuir a alteração entre as linhas que criam a agregação.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-126">When the adjustment of the forecasted quantity is made at an aggregated level, the system uses weighted allocation to distribute the change among the lines that create the aggregation.</span></span> 

<span data-ttu-id="9e2a6-127">Você também pode fazer ajustes manuais na página **Linhas de previsão de demanda**, modificando o valor **Quantidade total** ou as células **Quantidade** na grade de desagregação.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-127">You can also make manual adjustments on the **Demand forecast lines** page, by modifying either the **Total quantity** value or the **Quantity** cells in the de-aggregation grid.</span></span>

## <a name="viewing-details-of-the-forecast"></a><span data-ttu-id="9e2a6-128">Exibindo os detalhes da previsão</span><span class="sxs-lookup"><span data-stu-id="9e2a6-128">Viewing details of the forecast</span></span>
<span data-ttu-id="9e2a6-129">Você pode abrir a página **Detalhes de previsão de demanda** para exibir mais informações sobre a previsão.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-129">You can open the **Demand forecast details** page to view more information about the forecast.</span></span> 

<span data-ttu-id="9e2a6-130">A página **Detalhes de previsão de demanda** mostra as seguintes informações em gráficos e tabelas:</span><span class="sxs-lookup"><span data-stu-id="9e2a6-130">The **Demand forecast details** page shows the following information in graphical and tabular formats:</span></span>

-   <span data-ttu-id="9e2a6-131">A demanda histórica na qual as previsões se baseiam.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-131">The historical demand that the forecast predictions are based on.</span></span>
-   <span data-ttu-id="9e2a6-132">A previsão atual usada pelo Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-132">The current forecast that is used by Master planning.</span></span>
-   <span data-ttu-id="9e2a6-133">Os novos valores de previsão de demanda e os valores que serviram de base para o ajuste manual.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-133">The new demand forecast values and the amounts they have been manually adjusted by.</span></span>
-   <span data-ttu-id="9e2a6-134">O intervalo de confiança dos valores previstos.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-134">The confidence interval for the forecasted values.</span></span>
-   <span data-ttu-id="9e2a6-135">O modelo de previsão usado para gerar a previsão.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-135">The forecast model that was used to generate the forecast.</span></span> <span data-ttu-id="9e2a6-136">Se você estiver exibindo dados agregados, verá a lista de todos os métodos usados em todas as séries de tempo agregada.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-136">If you're viewing aggregated data, you will see the list of all the methods that were used for all the aggregated time series.</span></span>
-   <span data-ttu-id="9e2a6-137">A precisão do modelo interno (MAPE).</span><span class="sxs-lookup"><span data-stu-id="9e2a6-137">The internal model accuracy (MAPE).</span></span> <span data-ttu-id="9e2a6-138">Para obter mais informações sobre a precisão da previsão, consulte [Monitorar a precisão da previsão](monitor-forecast-accuracy.md).</span><span class="sxs-lookup"><span data-stu-id="9e2a6-138">For more information about forecast accuracy, see [Monitor forecast accuracy](monitor-forecast-accuracy.md).</span></span>

<span data-ttu-id="9e2a6-139">**Observações:**</span><span class="sxs-lookup"><span data-stu-id="9e2a6-139">**Notes:**</span></span>

-   <span data-ttu-id="9e2a6-140">Se você habilitar **Seleção do modelo de previsão nos detalhes da previsão de Demanda** do gerenciamento de Recursos, você poderá selecionar os modelos de previsão a serem incluídos para a previsão histórica na página **Detalhes de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-140">If you enable **Forecast model selection on Demand forecast details** from Feature management, you will be able to select the forecast models to be include, for the historical forecast, on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="9e2a6-141">O intervalo de confiança exibido na seção **Previsão** da página representa a diferença entre os limites superior e inferior do intervalo de confiança.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-141">The confidence interval that appears in the **Forecast** section of the page represents the difference between the confidence interval upper limit and the confidence interval lower limit.</span></span> <span data-ttu-id="9e2a6-142">Para ver os valores dos limites superior e inferior, focalize o gráfico na seção **Demanda histórica e previsão graficamente**.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-142">To see the values for the upper and lower limits, hover over the chart in the **Historical demand and forecast graphically** section.</span></span>
-   <span data-ttu-id="9e2a6-143">Se você usar o Aprendizado de Máquina do Microsoft Azure de previsão de Demanda, você pode especificar a porcentagem do nível de confiança que a previsão que é gerada deve ter.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-143">If you use the Demand forecasting Microsoft Azure Machine Learning, you can specify the confidence level percentage that the forecast that is generated should have.</span></span> <span data-ttu-id="9e2a6-144">Um intervalo de confiança consiste em um intervalo de valores que representam boas estimativas para a previsão de demanda.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-144">A confidence interval consists of a range of values that act as good estimates for the demand forecast.</span></span> <span data-ttu-id="9e2a6-145">Um nível de confiança de 95% indica que há um risco de 5% de que a previsão de demanda fique fora do intervalo de confiança.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-145">A 95-percent confidence level percentage indicates that there is a 5-percent risk that the demand forecast falls outside the confidence interval range.</span></span>

<span data-ttu-id="9e2a6-146">Você também pode fazer ajustes manuais na previsão na página **Detalhes de previsão de demanda**, modificando os valores na linha **Previsão** da seção **Previsão**.</span><span class="sxs-lookup"><span data-stu-id="9e2a6-146">You can also make manual adjustments to the forecast on the **Demand forecast details** page, by modifying the values in the **Forecast** row in the **Forecast** section.</span></span>

<a name="additional-resources"></a><span data-ttu-id="9e2a6-147">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9e2a6-147">Additional resources</span></span>
--------

[<span data-ttu-id="9e2a6-148">​Monitorar precisão da previsão​</span><span class="sxs-lookup"><span data-stu-id="9e2a6-148">Monitor forecast accuracy</span></span>](monitor-forecast-accuracy.md)

[<span data-ttu-id="9e2a6-149">​Gerar uma previsão estatística​</span><span class="sxs-lookup"><span data-stu-id="9e2a6-149">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)



