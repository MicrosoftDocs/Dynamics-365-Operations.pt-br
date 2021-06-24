---
title: 'Guia: criar uma previsão de linha de base'
description: Um planejador de produção pode criar uma linha de base de previsão usando modelos de previsão das séries temporais ou copiando as demandas históricas.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 95a20b30827c9096dd8d8f67d149305cf594ff05
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6223953"
---
# <a name="guide-create-a-baseline-forecast"></a><span data-ttu-id="f3908-103">Guia: criar uma previsão de linha de base</span><span class="sxs-lookup"><span data-stu-id="f3908-103">Guide: Create a baseline forecast</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f3908-104">Um planejador de produção pode criar uma linha de base de previsão usando modelos de previsão das séries temporais ou copiando as demandas históricas.</span><span class="sxs-lookup"><span data-stu-id="f3908-104">A production planner can create a baseline forecast either by using time series forecast models or by copying the historical demand.</span></span> <span data-ttu-id="f3908-105">Este procedimento mostra como criar uma previsão da linha de base para todos os produtos com uma chave de alocação de itens ao copiar a demanda de histórico.</span><span class="sxs-lookup"><span data-stu-id="f3908-105">This procedure shows how to copy the historical demand to create a baseline forecast for all products using one item allocation key.</span></span>

## <a name="set-up-an-item-allocation-key"></a><span data-ttu-id="f3908-106">Configurar uma chave de alocação de item</span><span class="sxs-lookup"><span data-stu-id="f3908-106">Set up an item allocation key</span></span>

1. <span data-ttu-id="f3908-107">Vá para **Planejamento principal > Configuração > Grupos de planejamento entre empresas**.</span><span class="sxs-lookup"><span data-stu-id="f3908-107">Go to **Master planning > Setup > Intercompany planning groups**.</span></span>
2. <span data-ttu-id="f3908-108">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="f3908-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="f3908-109">Por exemplo, filtre no campo *Nome* com um valor de *10*.</span><span class="sxs-lookup"><span data-stu-id="f3908-109">For example, filter on the *Name* field with a value of *10*.</span></span>
    * <span data-ttu-id="f3908-110">A previsão de demanda executa por meio da pessoa jurídica.</span><span class="sxs-lookup"><span data-stu-id="f3908-110">Demand forecasting runs across legal entities.</span></span> <span data-ttu-id="f3908-111">Por isso é necessário configurar todas as empresas para o qual você deseja gerar previsões em um grupo de planejamento intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="f3908-111">That's why you need to set up all the companies for which you want to generate forecasts in one intercompany planning group.</span></span>  
3. <span data-ttu-id="f3908-112">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="f3908-112">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="f3908-113">Selecione **Chaves de alocação de itens**.</span><span class="sxs-lookup"><span data-stu-id="f3908-113">Select **Item allocation keys**.</span></span>
    * <span data-ttu-id="f3908-114">Selecione todas as chaves de alocação de item para o qual você deseja criar previsões.</span><span class="sxs-lookup"><span data-stu-id="f3908-114">Select all the item allocation keys for which you want to create forecasts.</span></span>  
5. <span data-ttu-id="f3908-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f3908-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f3908-116">Selecione a chave de alocação de item de D_Aloc.</span><span class="sxs-lookup"><span data-stu-id="f3908-116">Select D_Aloc item allocation key.</span></span>  
6. <span data-ttu-id="f3908-117">Selecione **>**.</span><span class="sxs-lookup"><span data-stu-id="f3908-117">Select **>**.</span></span>
7. <span data-ttu-id="f3908-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f3908-118">Close the page.</span></span>
8. <span data-ttu-id="f3908-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f3908-119">Close the page.</span></span>

## <a name="set-up-the-demand-forecasting-parameters"></a><span data-ttu-id="f3908-120">Configurar os parâmetros de previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="f3908-120">Set up the demand forecasting parameters</span></span>

1. <span data-ttu-id="f3908-121">Vá para **Planejamento principal > Configuração > Previsão de demanda > Parâmetros de previsão de demanda**.</span><span class="sxs-lookup"><span data-stu-id="f3908-121">Go to **Master planning > Setup > Demand forecasting > Demand forecasting parameters**.</span></span>
2. <span data-ttu-id="f3908-122">Expanda a seção **Parâmetros do algoritmo de previsão**.</span><span class="sxs-lookup"><span data-stu-id="f3908-122">Expand the **Forecast algorithm parameters** section.</span></span>
3. <span data-ttu-id="f3908-123">No campo **Estratégia de geração de previsão**, selecione **Copiar histórico de demanda**.</span><span class="sxs-lookup"><span data-stu-id="f3908-123">In the **Forecast generation strategy** field, select **Copy over historical demand**.</span></span>
4. <span data-ttu-id="f3908-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f3908-124">Select **Save**.</span></span>

## <a name="create-a-baseline-forecast"></a><span data-ttu-id="f3908-125">Criar uma previsão de linha de base</span><span class="sxs-lookup"><span data-stu-id="f3908-125">Create a baseline forecast</span></span>

1. <span data-ttu-id="f3908-126">Vá para **Planejamento principal > Previsão > Previsão de demanda > Gerar previsão de linha de base estatística**.</span><span class="sxs-lookup"><span data-stu-id="f3908-126">Go to **Master planning > Forecasting > Demand forecasting > Generate statistical baseline forecast**.</span></span>
2. <span data-ttu-id="f3908-127">No campo **Data inicial**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f3908-127">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="f3908-128">Se você tem ordens de venda que começam desde 1º de janeiro de 2015, insira esta data.</span><span class="sxs-lookup"><span data-stu-id="f3908-128">If you have sales orders starting from January 1, 2015, enter this date.</span></span> <span data-ttu-id="f3908-129">Caso contrário, insira a data mais anterior das ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="f3908-129">If you don't, enter the earliest date of your sales orders.</span></span>  
3. <span data-ttu-id="f3908-130">No campo **Data final**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f3908-130">In the **To date** field, enter a date.</span></span>
    * <span data-ttu-id="f3908-131">Insira a última data de suas ordens de venda, por exemplo *2015-31-03*.</span><span class="sxs-lookup"><span data-stu-id="f3908-131">Enter the last date of your sales orders, for example *2015-03-31*.</span></span>  
4. <span data-ttu-id="f3908-132">No campo **Data inicial**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="f3908-132">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="f3908-133">Digite *2015-01-04*.</span><span class="sxs-lookup"><span data-stu-id="f3908-133">Enter *2015-04-01*.</span></span> <span data-ttu-id="f3908-134">Essa data será calculada automaticamente como a data de início da próxima da previsão.</span><span class="sxs-lookup"><span data-stu-id="f3908-134">This date will be automatically calculated as the start date of the next forecasting bucket.</span></span>  
5. <span data-ttu-id="f3908-135">Expanda a seção **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="f3908-135">Expand the **Records to include** section.</span></span>
6. <span data-ttu-id="f3908-136">Selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="f3908-136">Select **Filter**.</span></span>
7. <span data-ttu-id="f3908-137">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f3908-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f3908-138">Marque a linha em que **Campo** = *Grupo de planejamento entre empresas*.</span><span class="sxs-lookup"><span data-stu-id="f3908-138">Mark the row where **Field** = *Intercompany planning group*.</span></span>  
8. <span data-ttu-id="f3908-139">No campo **Critérios**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f3908-139">In the **Criteria** field, type a value.</span></span>
    * <span data-ttu-id="f3908-140">Digite o grupo de planejamento entre empresas (por exemplo, *10*) que você usou na primeira tarefa.</span><span class="sxs-lookup"><span data-stu-id="f3908-140">Type the intercompany planning group (for example, *10*) that you used in the first task.</span></span>  
9. <span data-ttu-id="f3908-141">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="f3908-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f3908-142">Selecione a linha em que **Campo** = *Chave de alocação de item*.</span><span class="sxs-lookup"><span data-stu-id="f3908-142">Select the row where **Field** = *Item allocation key*.</span></span>  
10. <span data-ttu-id="f3908-143">No campo **Critérios**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f3908-143">In the **Criteria** field, type a value.</span></span>
11. <span data-ttu-id="f3908-144">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3908-144">Select **OK**.</span></span>
12. <span data-ttu-id="f3908-145">Expanda a seção **Parâmetros avançados**.</span><span class="sxs-lookup"><span data-stu-id="f3908-145">Expand the **Advanced parameters** section.</span></span>
13. <span data-ttu-id="f3908-146">No campo **Bucket de previsão**, selecione *Mês*.</span><span class="sxs-lookup"><span data-stu-id="f3908-146">In the **Forecast bucket** field, select *Month*.</span></span>
14. <span data-ttu-id="f3908-147">No campo **Horizonte de previsão**, insira *3*.</span><span class="sxs-lookup"><span data-stu-id="f3908-147">In the **Forecast horizon** field, enter *3*.</span></span>
15. <span data-ttu-id="f3908-148">No campo **Congelar limite de tempo**, insira *1*.</span><span class="sxs-lookup"><span data-stu-id="f3908-148">In the **Freeze time fence** field, enter *1*.</span></span>
16. <span data-ttu-id="f3908-149">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f3908-149">Select **OK**.</span></span>

## <a name="visualize-the-demand-forecast"></a><span data-ttu-id="f3908-150">Visualize a previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="f3908-150">Visualize the demand forecast</span></span>

1. <span data-ttu-id="f3908-151">Vá para **Planejamento principal > Previsão > Previsão de demanda > Previsão de demanda ajustada**.</span><span class="sxs-lookup"><span data-stu-id="f3908-151">Go to **Master planning > Forecasting > Demand forecasting > Adjusted demand forecast**.</span></span>
2. <span data-ttu-id="f3908-152">Na tabela de exibição agregada, selecione a célula na linha 1, coluna 2.</span><span class="sxs-lookup"><span data-stu-id="f3908-152">In the aggregated view table, select the cell in row 1, column 2.</span></span> <span data-ttu-id="f3908-153">Este é o segundo mês para o qual você criou uma previsão.</span><span class="sxs-lookup"><span data-stu-id="f3908-153">This is the second month for which you have created forecast.</span></span>
3. <span data-ttu-id="f3908-154">Defina **QtyCell** como *400*.</span><span class="sxs-lookup"><span data-stu-id="f3908-154">Set **QtyCell** to *400*.</span></span>
    * <span data-ttu-id="f3908-155">Na célula, insira um número diferente de aquele que foi previsto, por exemplo, 400.</span><span class="sxs-lookup"><span data-stu-id="f3908-155">In the cell, enter a different number than the one that was forecasted, for example, 400.</span></span>  
4. <span data-ttu-id="f3908-156">Você tiver feito um ajuste manual para a previsão.</span><span class="sxs-lookup"><span data-stu-id="f3908-156">You have made a manual adjustment to the forecast.</span></span> <span data-ttu-id="f3908-157">Observe a indicação gráfica na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="f3908-157">Notice the graphical indication in the next step.</span></span>
5. <span data-ttu-id="f3908-158">Selecione **Detalhes da linha de previsão**.</span><span class="sxs-lookup"><span data-stu-id="f3908-158">Select **Forecast line details**.</span></span>
    * <span data-ttu-id="f3908-159">Nessa página, você pode ver os valores de precisão, a demanda histórica e a previsão.</span><span class="sxs-lookup"><span data-stu-id="f3908-159">In this page, you can see the accuracy values, historical demand, and forecast.</span></span> <span data-ttu-id="f3908-160">Você pode fazer alterações para a previsão também.</span><span class="sxs-lookup"><span data-stu-id="f3908-160">You can make changes to the forecast as well.</span></span>  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]