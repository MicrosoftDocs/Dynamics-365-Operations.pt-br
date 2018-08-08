---
title: "Chaves de redução"
description: "Estes artigos oferecem exemplos que mostram como configurar uma chave de redução. Eles incluem informações sobre as diversas configurações da chave de redução e os resultados de cada uma delas. Você pode usar uma chave de redução para definir como reduzir os requisitos de previsão."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 3e62431a1fdbeb81dda68297f034ee00adece079
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="reduction-keys"></a><span data-ttu-id="884df-105">Chaves de redução</span><span class="sxs-lookup"><span data-stu-id="884df-105">Reduction keys</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="884df-106">Estes artigos oferecem exemplos que mostram como configurar uma chave de redução.</span><span class="sxs-lookup"><span data-stu-id="884df-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="884df-107">Eles incluem informações sobre as diversas configurações da chave de redução e os resultados de cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="884df-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="884df-108">Você pode usar uma chave de redução para definir como reduzir os requisitos de previsão.</span><span class="sxs-lookup"><span data-stu-id="884df-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="884df-109">Exemplo 1: Porcentagem - princípio de redução de previsão da chave de redução</span><span class="sxs-lookup"><span data-stu-id="884df-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="884df-110">Este exemplo mostra como uma chave de redução reduz requisitos de previsão de demanda de acordo com as porcentagens e os períodos que são definidos pela chave de redução.</span><span class="sxs-lookup"><span data-stu-id="884df-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1. <span data-ttu-id="884df-111">Na página **Chaves de redução**, configure as seguintes linhas.</span><span class="sxs-lookup"><span data-stu-id="884df-111">On the **Reduction keys** page, set up the following lines.</span></span>

   | <span data-ttu-id="884df-112">Troco</span><span class="sxs-lookup"><span data-stu-id="884df-112">Change</span></span> | <span data-ttu-id="884df-113">Unidade</span><span class="sxs-lookup"><span data-stu-id="884df-113">Unit</span></span>  | <span data-ttu-id="884df-114">Percentual</span><span class="sxs-lookup"><span data-stu-id="884df-114">Percent</span></span> |
   |--------|-------|---------|
   |   <span data-ttu-id="884df-115">1</span><span class="sxs-lookup"><span data-stu-id="884df-115">1</span></span>    | <span data-ttu-id="884df-116">Mês</span><span class="sxs-lookup"><span data-stu-id="884df-116">Month</span></span> |   <span data-ttu-id="884df-117">100</span><span class="sxs-lookup"><span data-stu-id="884df-117">100</span></span>   |
   |   <span data-ttu-id="884df-118">2</span><span class="sxs-lookup"><span data-stu-id="884df-118">2</span></span>    | <span data-ttu-id="884df-119">Mês</span><span class="sxs-lookup"><span data-stu-id="884df-119">Month</span></span> |   <span data-ttu-id="884df-120">75</span><span class="sxs-lookup"><span data-stu-id="884df-120">75</span></span>    |
   |   <span data-ttu-id="884df-121">3</span><span class="sxs-lookup"><span data-stu-id="884df-121">3</span></span>    | <span data-ttu-id="884df-122">Mês</span><span class="sxs-lookup"><span data-stu-id="884df-122">Month</span></span> |   <span data-ttu-id="884df-123">50</span><span class="sxs-lookup"><span data-stu-id="884df-123">50</span></span>    |
   |   <span data-ttu-id="884df-124">4</span><span class="sxs-lookup"><span data-stu-id="884df-124">4</span></span>    | <span data-ttu-id="884df-125">Mês</span><span class="sxs-lookup"><span data-stu-id="884df-125">Month</span></span> |   <span data-ttu-id="884df-126">25</span><span class="sxs-lookup"><span data-stu-id="884df-126">25</span></span>    |


2. <span data-ttu-id="884df-127">Vincule a chave de redução ao grupo de cobertura do item.</span><span class="sxs-lookup"><span data-stu-id="884df-127">Link the reduction key to the item's coverage group.</span></span>
3. <span data-ttu-id="884df-128">Na página **Planos mestres**, no campo **Princípio de redução**, selecione **Percentual - chave de redução**.</span><span class="sxs-lookup"><span data-stu-id="884df-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4. <span data-ttu-id="884df-129">Crie uma previsão de demanda de 1.000 peças por mês.</span><span class="sxs-lookup"><span data-stu-id="884df-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="884df-130">Se você executar o plano de previsão em 1º de janeiro, os requisitos de previsão de demanda serão consumidos de acordo com as porcentagens configuradas na página **Chaves de redução**.</span><span class="sxs-lookup"><span data-stu-id="884df-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="884df-131">As quantidades da requisição a seguir são transferidas para o plano mestre.</span><span class="sxs-lookup"><span data-stu-id="884df-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="884df-132">Mês</span><span class="sxs-lookup"><span data-stu-id="884df-132">Month</span></span>                | <span data-ttu-id="884df-133">Número de peças necessárias</span><span class="sxs-lookup"><span data-stu-id="884df-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="884df-134">Janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-134">January</span></span>              | <span data-ttu-id="884df-135">0</span><span class="sxs-lookup"><span data-stu-id="884df-135">0</span></span>                         |
| <span data-ttu-id="884df-136">Fevereiro</span><span class="sxs-lookup"><span data-stu-id="884df-136">February</span></span>             | <span data-ttu-id="884df-137">250</span><span class="sxs-lookup"><span data-stu-id="884df-137">250</span></span>                       |
| <span data-ttu-id="884df-138">Março</span><span class="sxs-lookup"><span data-stu-id="884df-138">March</span></span>                | <span data-ttu-id="884df-139">500</span><span class="sxs-lookup"><span data-stu-id="884df-139">500</span></span>                       |
| <span data-ttu-id="884df-140">Abril</span><span class="sxs-lookup"><span data-stu-id="884df-140">April</span></span>                | <span data-ttu-id="884df-141">750</span><span class="sxs-lookup"><span data-stu-id="884df-141">750</span></span>                       |
| <span data-ttu-id="884df-142">Maio até dezembro</span><span class="sxs-lookup"><span data-stu-id="884df-142">May through December</span></span> | <span data-ttu-id="884df-143">1.000</span><span class="sxs-lookup"><span data-stu-id="884df-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="884df-144">Exemplo 2: Transações - princípio de redução de previsão da chave de redução</span><span class="sxs-lookup"><span data-stu-id="884df-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="884df-145">Este exemplo mostra como as ordens reais que ocorrem durante os períodos definidos pela chave de redução reduzem requisitos de previsão de demanda.</span><span class="sxs-lookup"><span data-stu-id="884df-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="884df-146">Na página **Planos mestres**, no campo **Princípio de redução**, selecione **Transações - chave de redução**.</span><span class="sxs-lookup"><span data-stu-id="884df-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="884df-147">As ordens de venda a seguir existem em 1º de janeiro.</span><span class="sxs-lookup"><span data-stu-id="884df-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="884df-148">Mês</span><span class="sxs-lookup"><span data-stu-id="884df-148">Month</span></span>    | <span data-ttu-id="884df-149">Número de peças pedidas</span><span class="sxs-lookup"><span data-stu-id="884df-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="884df-150">Janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-150">January</span></span>  | <span data-ttu-id="884df-151">956</span><span class="sxs-lookup"><span data-stu-id="884df-151">956</span></span>                      |
| <span data-ttu-id="884df-152">Fevereiro</span><span class="sxs-lookup"><span data-stu-id="884df-152">February</span></span> | <span data-ttu-id="884df-153">1.176</span><span class="sxs-lookup"><span data-stu-id="884df-153">1,176</span></span>                    |
| <span data-ttu-id="884df-154">Março</span><span class="sxs-lookup"><span data-stu-id="884df-154">March</span></span>    | <span data-ttu-id="884df-155">451</span><span class="sxs-lookup"><span data-stu-id="884df-155">451</span></span>                      |
| <span data-ttu-id="884df-156">Abril</span><span class="sxs-lookup"><span data-stu-id="884df-156">April</span></span>    | <span data-ttu-id="884df-157">119</span><span class="sxs-lookup"><span data-stu-id="884df-157">119</span></span>                      |

<span data-ttu-id="884df-158">Se você usar a mesma previsão de demanda de 1.000 peças por mês, as quantidades da requisição a seguir serão transferidas para o plano mestre.</span><span class="sxs-lookup"><span data-stu-id="884df-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="884df-159">Mês</span><span class="sxs-lookup"><span data-stu-id="884df-159">Month</span></span>                | <span data-ttu-id="884df-160">Número de peças necessárias</span><span class="sxs-lookup"><span data-stu-id="884df-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="884df-161">Janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-161">January</span></span>              | <span data-ttu-id="884df-162">44</span><span class="sxs-lookup"><span data-stu-id="884df-162">44</span></span>                        |
| <span data-ttu-id="884df-163">Fevereiro</span><span class="sxs-lookup"><span data-stu-id="884df-163">February</span></span>             | <span data-ttu-id="884df-164">0</span><span class="sxs-lookup"><span data-stu-id="884df-164">0</span></span>                         |
| <span data-ttu-id="884df-165">Março</span><span class="sxs-lookup"><span data-stu-id="884df-165">March</span></span>                | <span data-ttu-id="884df-166">549</span><span class="sxs-lookup"><span data-stu-id="884df-166">549</span></span>                       |
| <span data-ttu-id="884df-167">Abril</span><span class="sxs-lookup"><span data-stu-id="884df-167">April</span></span>                | <span data-ttu-id="884df-168">881</span><span class="sxs-lookup"><span data-stu-id="884df-168">881</span></span>                       |
| <span data-ttu-id="884df-169">Maio até dezembro</span><span class="sxs-lookup"><span data-stu-id="884df-169">May through December</span></span> | <span data-ttu-id="884df-170">1.000</span><span class="sxs-lookup"><span data-stu-id="884df-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="884df-171">Exemplo 3: Transações - princípio de redução de previsão do período dinâmico</span><span class="sxs-lookup"><span data-stu-id="884df-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="884df-172">Na maioria dos casos, os sistemas são configurados de forma que as transações reduzam a previsão de demanda nos períodos de previsão específicos: semanas, meses, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="884df-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="884df-173">Os períodos são definidos na chave de redução.</span><span class="sxs-lookup"><span data-stu-id="884df-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="884df-174">No entanto, o tempo entre duas linhas de previsão de demanda também pode *implicar* em um período.</span><span class="sxs-lookup"><span data-stu-id="884df-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1. <span data-ttu-id="884df-175">Crie uma previsão de demanda para as seguintes datas e quantidades.</span><span class="sxs-lookup"><span data-stu-id="884df-175">Create a demand forecast for the following dates and quantities.</span></span>

   | <span data-ttu-id="884df-176">Data</span><span class="sxs-lookup"><span data-stu-id="884df-176">Date</span></span>       | <span data-ttu-id="884df-177">Previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="884df-177">Demand forecast</span></span> |
   |------------|-----------------|
   | <span data-ttu-id="884df-178">1º de janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-178">January 1</span></span>  | <span data-ttu-id="884df-179">1.000</span><span class="sxs-lookup"><span data-stu-id="884df-179">1,000</span></span>           |
   | <span data-ttu-id="884df-180">5 de janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-180">January 5</span></span>  | <span data-ttu-id="884df-181">500</span><span class="sxs-lookup"><span data-stu-id="884df-181">500</span></span>             |
   | <span data-ttu-id="884df-182">12 de janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-182">January 12</span></span> | <span data-ttu-id="884df-183">1.000</span><span class="sxs-lookup"><span data-stu-id="884df-183">1,000</span></span>           |

   <span data-ttu-id="884df-184">Nesta previsão, não há um período desmarcado entre as datas da previsão: entre as primeiras e segundas datas há um período de quatro dias e, entre a segunda e terceira datas há um período de sete dias.</span><span class="sxs-lookup"><span data-stu-id="884df-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="884df-185">Esses vários períodos são os períodos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="884df-185">These various spans are the dynamic periods.</span></span>
2. <span data-ttu-id="884df-186">Crie linhas de ordem de venda como segue.</span><span class="sxs-lookup"><span data-stu-id="884df-186">Create sales order lines as follows.</span></span>
   | <span data-ttu-id="884df-187">Data</span><span class="sxs-lookup"><span data-stu-id="884df-187">Date</span></span>                             | <span data-ttu-id="884df-188">Quantidade da ordem de venda</span><span class="sxs-lookup"><span data-stu-id="884df-188">Sales order quantity</span></span> |
   |----------------------------------|----------------------|
   | <span data-ttu-id="884df-189">15 de dezembro do ano anterior</span><span class="sxs-lookup"><span data-stu-id="884df-189">December 15 in the previous year</span></span> | <span data-ttu-id="884df-190">500</span><span class="sxs-lookup"><span data-stu-id="884df-190">500</span></span>                  |
   | <span data-ttu-id="884df-191">3 de janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-191">January 3</span></span>                        | <span data-ttu-id="884df-192">100</span><span class="sxs-lookup"><span data-stu-id="884df-192">100</span></span>                  |
   | <span data-ttu-id="884df-193">10 de janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-193">January 10</span></span>                       | <span data-ttu-id="884df-194">200</span><span class="sxs-lookup"><span data-stu-id="884df-194">200</span></span>                  |

<span data-ttu-id="884df-195">A previsão será reduzida da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="884df-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="884df-196">A primeira ordem de venda não está dentro de um período, dessa forma ela não reduzirá nenhuma previsão.</span><span class="sxs-lookup"><span data-stu-id="884df-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="884df-197">A segunda ordem de venda está entre 1º e 5 de janeiro, então isso reduzirá a previsão de 1º de janeiro por 100.</span><span class="sxs-lookup"><span data-stu-id="884df-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="884df-198">A terceira ordem de venda está entre o 5 e 12 de janeiro, então isso reduzirá a previsão de 5 de janeiro por 200.</span><span class="sxs-lookup"><span data-stu-id="884df-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="884df-199">A seguinte ordem planejada será criada para atender à previsão.</span><span class="sxs-lookup"><span data-stu-id="884df-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="884df-200">Data da previsão de demanda</span><span class="sxs-lookup"><span data-stu-id="884df-200">Demand forecast date</span></span> | <span data-ttu-id="884df-201">Quantidade reduzida</span><span class="sxs-lookup"><span data-stu-id="884df-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="884df-202">1º de janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-202">January 1</span></span>            | <span data-ttu-id="884df-203">900</span><span class="sxs-lookup"><span data-stu-id="884df-203">900</span></span>              |
| <span data-ttu-id="884df-204">5 de janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-204">January 5</span></span>            | <span data-ttu-id="884df-205">300</span><span class="sxs-lookup"><span data-stu-id="884df-205">300</span></span>              |
| <span data-ttu-id="884df-206">12 de janeiro</span><span class="sxs-lookup"><span data-stu-id="884df-206">January 12</span></span>           | <span data-ttu-id="884df-207">1.000</span><span class="sxs-lookup"><span data-stu-id="884df-207">1,000</span></span>            |

<span data-ttu-id="884df-208">Aqui está um resumo de **Transações - redução de período** dinâmico:</span><span class="sxs-lookup"><span data-stu-id="884df-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="884df-209">Os requisitos de previsão são reduzidos por transações de ordens reais que ocorrem durante o período dinâmico.</span><span class="sxs-lookup"><span data-stu-id="884df-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="884df-210">O período dinâmico cobre as datas de previsão atuais e termina no início da próxima previsão.</span><span class="sxs-lookup"><span data-stu-id="884df-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="884df-211">Este método não usa ou não requer uma chave de redução.</span><span class="sxs-lookup"><span data-stu-id="884df-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="884df-212">Quando esta opção é usada, o seguinte comportamento ocorre:</span><span class="sxs-lookup"><span data-stu-id="884df-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="884df-213">Se a previsão for completamente reduzida, os requisitos da previsão atual se tornam 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="884df-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="884df-214">Se não houver previsão futura, os requisitos de previsão da última previsão que foi inserida serão reduzidos.</span><span class="sxs-lookup"><span data-stu-id="884df-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="884df-215">Os limites de tempo são incluídos no cálculo de redução de previsão.</span><span class="sxs-lookup"><span data-stu-id="884df-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="884df-216">Os dias positivos são incluídos no cálculo de redução de previsão.</span><span class="sxs-lookup"><span data-stu-id="884df-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="884df-217">Se as transações de ordens reais excederam os requisitos de previsão, as outras transações não serão encaminhadas para o próximo período de previsão.</span><span class="sxs-lookup"><span data-stu-id="884df-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="additional-resources"></a><span data-ttu-id="884df-218">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="884df-218">Additional resources</span></span>
--------

[<span data-ttu-id="884df-219">Planos mestres</span><span class="sxs-lookup"><span data-stu-id="884df-219">Master plans</span></span>](master-plans.md)




