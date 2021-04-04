---
title: Criar uma previsão de linha de base
description: Um planejador de produção pode criar uma linha de base de previsão usando modelos de previsão das séries temporais ou copiando as demandas históricas.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f18da9563421e7e092869451376e53a450abdf7e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246708"
---
# <a name="create-a-baseline-forecast"></a><span data-ttu-id="393fa-103">Criar uma previsão de linha de base</span><span class="sxs-lookup"><span data-stu-id="393fa-103">Create a baseline forecast</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="393fa-104">Um planejador de produção pode criar uma linha de base de previsão usando modelos de previsão das séries temporais ou copiando as demandas históricas.</span><span class="sxs-lookup"><span data-stu-id="393fa-104">A production planner can create a baseline forecast either by using time series forecast models or by copying the historical demand.</span></span> <span data-ttu-id="393fa-105">Este procedimento mostra como criar uma previsão da linha de base para todos os produtos com uma chave de alocação de itens ao copiar a demanda de histórico.</span><span class="sxs-lookup"><span data-stu-id="393fa-105">This procedure shows how to copy the historical demand to create a baseline forecast for all products using one item allocation key.</span></span> 


## <a name="set-up-an-item-allocation-key"></a><span data-ttu-id="393fa-106">Configurar uma chave de alocação de item</span><span class="sxs-lookup"><span data-stu-id="393fa-106">Set up an item allocation key</span></span>
1. <span data-ttu-id="393fa-107">Vá para Planejamento mestre > Configuração > Grupos de planejamento intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="393fa-107">Go to Master planning > Setup > Intercompany planning groups.</span></span>
2. <span data-ttu-id="393fa-108">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="393fa-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="393fa-109">Por exemplo, filtre o campo Nome com um valor de '10'.</span><span class="sxs-lookup"><span data-stu-id="393fa-109">For example, filter on the Name field with a value of '10'.</span></span>
    * <span data-ttu-id="393fa-110">A previsão de demanda executa por meio da pessoa jurídica.</span><span class="sxs-lookup"><span data-stu-id="393fa-110">Demand forecasting runs across legal entities.</span></span> <span data-ttu-id="393fa-111">Por isso é necessário configurar todas as empresas para o qual você deseja gerar previsões em um grupo de planejamento intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="393fa-111">That's why you need to set up all the companies for which you want to generate forecasts in one intercompany planning group.</span></span>  
3. <span data-ttu-id="393fa-112">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="393fa-112">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="393fa-113">Clique em Chaves de alocação de item.</span><span class="sxs-lookup"><span data-stu-id="393fa-113">Click Item allocation keys.</span></span>
    * <span data-ttu-id="393fa-114">Selecione todas as chaves de alocação de item para o qual você deseja criar previsões.</span><span class="sxs-lookup"><span data-stu-id="393fa-114">Select all the item allocation keys for which you want to create forecasts.</span></span>  
5. <span data-ttu-id="393fa-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="393fa-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="393fa-116">Selecione a chave de alocação de item de D_Aloc.</span><span class="sxs-lookup"><span data-stu-id="393fa-116">Select D_Aloc item allocation key.</span></span>  
6. <span data-ttu-id="393fa-117">Clique em >.</span><span class="sxs-lookup"><span data-stu-id="393fa-117">Click >.</span></span>
7. <span data-ttu-id="393fa-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="393fa-118">Close the page.</span></span>
8. <span data-ttu-id="393fa-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="393fa-119">Close the page.</span></span>

## <a name="set-up-the-demand-forecasting-parameters"></a><span data-ttu-id="393fa-120">Configurar os parâmetros de previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="393fa-120">Set up the demand forecasting parameters</span></span>
1. <span data-ttu-id="393fa-121">Vá para Planejamento mestre > Configuração > Previsão de demanda > Parâmetros de previsão de demanda.</span><span class="sxs-lookup"><span data-stu-id="393fa-121">Go to Master planning > Setup > Demand forecasting > Demand forecasting parameters.</span></span>
2. <span data-ttu-id="393fa-122">Expanda a seção de parâmetros de algoritmo de previsão.</span><span class="sxs-lookup"><span data-stu-id="393fa-122">Expand the Forecast algorithm parameters section.</span></span>
3. <span data-ttu-id="393fa-123">No campo da estratégia de geração de previsão, selecione 'Copiar sobre demanda histórica'.</span><span class="sxs-lookup"><span data-stu-id="393fa-123">In the Forecast generation strategy field, select 'Copy over historical demand'.</span></span>
4. <span data-ttu-id="393fa-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="393fa-124">Click Save.</span></span>

## <a name="create-a-baseline-forecast"></a><span data-ttu-id="393fa-125">Criar uma previsão de linha de base</span><span class="sxs-lookup"><span data-stu-id="393fa-125">Create a baseline forecast</span></span>
1. <span data-ttu-id="393fa-126">Vá para Planejamento mestre > Previsão > Previsão de demanda > Previsão estatística.</span><span class="sxs-lookup"><span data-stu-id="393fa-126">Go to Master planning > Forecasting > Demand forecasting > Generate statistical baseline forecast.</span></span>
2. <span data-ttu-id="393fa-127">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="393fa-127">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="393fa-128">Se você tem ordens de venda que começam desde 1º de janeiro de 2015, insira esta data.</span><span class="sxs-lookup"><span data-stu-id="393fa-128">If you have sales orders starting from January 1, 2015, enter this date.</span></span> <span data-ttu-id="393fa-129">Caso contrário, insira a data mais anterior das ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="393fa-129">If you don't, enter the earliest date of your sales orders.</span></span>  
3. <span data-ttu-id="393fa-130">No campo Até, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="393fa-130">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="393fa-131">Insira a última data das ordens de venda, por exemplo, "31-03-2015".</span><span class="sxs-lookup"><span data-stu-id="393fa-131">Enter the last date of your sales orders, for example '2015-03-31'.</span></span>  
4. <span data-ttu-id="393fa-132">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="393fa-132">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="393fa-133">Insira "01-04-2015"</span><span class="sxs-lookup"><span data-stu-id="393fa-133">Enter '2015-04-01'.</span></span> <span data-ttu-id="393fa-134">Essa data será calculada automaticamente como a data de início da próxima da previsão.</span><span class="sxs-lookup"><span data-stu-id="393fa-134">This date will be automatically calculated as the start date of the next forecasting bucket.</span></span>  
5. <span data-ttu-id="393fa-135">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="393fa-135">Expand the Records to include section.</span></span>
6. <span data-ttu-id="393fa-136">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="393fa-136">Click Filter.</span></span>
7. <span data-ttu-id="393fa-137">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="393fa-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="393fa-138">Marque a linha no campo = grupo de planejamento intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="393fa-138">Mark the row where Field = Intercompany planning group.</span></span>  
8. <span data-ttu-id="393fa-139">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="393fa-139">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="393fa-140">Digite o grupo de planejamento intercompanhia, por exemplo, 10, que é usado na primeira tarefa.</span><span class="sxs-lookup"><span data-stu-id="393fa-140">Type the intercompany planning group, for example, 10, that you used in the first task.</span></span>  
9. <span data-ttu-id="393fa-141">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="393fa-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="393fa-142">Selecione a linha em que o campo = chave de alocação de item.</span><span class="sxs-lookup"><span data-stu-id="393fa-142">Select the row where Field = Item allocation key.</span></span>  
10. <span data-ttu-id="393fa-143">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="393fa-143">In the Criteria field, type a value.</span></span>
11. <span data-ttu-id="393fa-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="393fa-144">Click OK.</span></span>
12. <span data-ttu-id="393fa-145">Expanda a seção Parâmetros avançados.</span><span class="sxs-lookup"><span data-stu-id="393fa-145">Expand the Advanced parameters section.</span></span>
13. <span data-ttu-id="393fa-146">No campo Classificação por Previsão, selecione 'Mês'.</span><span class="sxs-lookup"><span data-stu-id="393fa-146">In the Forecast bucket field, select 'Month'.</span></span>
14. <span data-ttu-id="393fa-147">No campo Horizonte de previsão, insira '3'.</span><span class="sxs-lookup"><span data-stu-id="393fa-147">In the Forecast horizon field, enter '3'.</span></span>
15. <span data-ttu-id="393fa-148">No Tempo limite de congelamento, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="393fa-148">In the Freeze time fence field, enter '1'.</span></span>
16. <span data-ttu-id="393fa-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="393fa-149">Click OK.</span></span>

## <a name="visualize-the-demand-forecast"></a><span data-ttu-id="393fa-150">Visualize a previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="393fa-150">Visualize the demand forecast</span></span>
1. <span data-ttu-id="393fa-151">Vá para Planejamento mestre > Previsão > Previsão de demanda > Previsão de demanda ajustada.</span><span class="sxs-lookup"><span data-stu-id="393fa-151">Go to Master planning > Forecasting > Demand forecasting > Adjusted demand forecast.</span></span>
2. <span data-ttu-id="393fa-152">Na tabela de exibição agregada, selecione a célula na linha 1, coluna 2.</span><span class="sxs-lookup"><span data-stu-id="393fa-152">In the aggregated view table, select the cell in row 1, column 2.</span></span> <span data-ttu-id="393fa-153">Este é o segundo mês para o qual você criou uma previsão.</span><span class="sxs-lookup"><span data-stu-id="393fa-153">This is the second month for which you have created forecast.</span></span>
3. <span data-ttu-id="393fa-154">Definir QtyCell a '400'.</span><span class="sxs-lookup"><span data-stu-id="393fa-154">Set QtyCell to '400'.</span></span>
    * <span data-ttu-id="393fa-155">Na célula, insira um número diferente de aquele que foi previsto, por exemplo, 400.</span><span class="sxs-lookup"><span data-stu-id="393fa-155">In the cell, enter a different number than the one that was forecasted, for example, 400.</span></span>  
4. <span data-ttu-id="393fa-156">Você tiver feito um ajuste manual para a previsão.</span><span class="sxs-lookup"><span data-stu-id="393fa-156">You have made a manual adjustment to the forecast.</span></span> <span data-ttu-id="393fa-157">Observe a indicação gráfica na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="393fa-157">Notice the graphical indication in the next step.</span></span>
5. <span data-ttu-id="393fa-158">Clique em Detalhes da linha de previsão.</span><span class="sxs-lookup"><span data-stu-id="393fa-158">Click Forecast line details.</span></span>
    * <span data-ttu-id="393fa-159">Nessa página, você pode ver os valores de precisão, a demanda histórica e a previsão.</span><span class="sxs-lookup"><span data-stu-id="393fa-159">In this page, you can see the accuracy values, historical demand, and forecast.</span></span> <span data-ttu-id="393fa-160">Você pode fazer alterações para a previsão também.</span><span class="sxs-lookup"><span data-stu-id="393fa-160">You can make changes to the forecast as well.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]