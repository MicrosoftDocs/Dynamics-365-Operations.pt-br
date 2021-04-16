---
title: Configurar mestres de taxa
description: Este procedimento mostra como configurar um mestre de taxa.
author: ShylaThompson
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8cb25726e05f11420c7355c39f7e262abca5da62
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808981"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="e90f8-103">Configurar mestres de taxa</span><span class="sxs-lookup"><span data-stu-id="e90f8-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e90f8-104">Este procedimento mostra como configurar um mestre de taxa.</span><span class="sxs-lookup"><span data-stu-id="e90f8-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="e90f8-105">O gerente logístico geralmente configura os mestres de taxa, dependendo dos contratos assinados com as transportadoras.</span><span class="sxs-lookup"><span data-stu-id="e90f8-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="e90f8-106">Neste cenário você irá configurar um mestre de taxa para um transportador aérea.</span><span class="sxs-lookup"><span data-stu-id="e90f8-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="e90f8-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="e90f8-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-break-master"></a><span data-ttu-id="e90f8-108">Configurar mestre de interrupção</span><span class="sxs-lookup"><span data-stu-id="e90f8-108">Set up break master</span></span>

1. <span data-ttu-id="e90f8-109">Vá para **Gerenciamento de transporte > Configurar > Classificação > Mestre de quebra**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-109">Go to **Transportation management > Setup > Rating > Break master**.</span></span> <span data-ttu-id="e90f8-110">Mestres de interrupção são usados para definir a estrutura de definição de preços e seus pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="e90f8-110">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="e90f8-111">A estrutura de definição de preços usa definição de preços hierarquizada baseada em dimensões físicas.</span><span class="sxs-lookup"><span data-stu-id="e90f8-111">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
1. <span data-ttu-id="e90f8-112">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-112">Select **New**.</span></span>
1. <span data-ttu-id="e90f8-113">No campo **Mestre de quebra**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="e90f8-113">In the **Break master** field, enter a value.</span></span>
1. <span data-ttu-id="e90f8-114">No campo **Nome**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="e90f8-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="e90f8-115">No campo **Tipo de dados**, selecione o tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="e90f8-115">In the **Data type** field, select the data type.</span></span>
1. <span data-ttu-id="e90f8-116">No campo **Comparação**, insira o tipo de comparação solicitada (usando operadores).</span><span class="sxs-lookup"><span data-stu-id="e90f8-116">In the **Comparison** field, enter the kind of comparison requested (using operators).</span></span>
1. <span data-ttu-id="e90f8-117">No campo **Quebrar unidade**, insira os valores da unidade de interrupção.</span><span class="sxs-lookup"><span data-stu-id="e90f8-117">In the **Break unit** field, enter the break unit.</span></span>
1. <span data-ttu-id="e90f8-118">Na seção **Detalhes**, crie quantas quebras forem necessárias para a estrutura de preços.</span><span class="sxs-lookup"><span data-stu-id="e90f8-118">In the **Details** section, create as many breaks as needed for the pricing structure.</span></span>
1. <span data-ttu-id="e90f8-119">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-119">Select **Save**.</span></span>

## <a name="set-up-rate-master"></a><span data-ttu-id="e90f8-120">Configurar mestre de taxa</span><span class="sxs-lookup"><span data-stu-id="e90f8-120">Set up rate master</span></span>

1. <span data-ttu-id="e90f8-121">Vá para **Gerenciamento de transporte > Configurar > Classificação > Mestre de taxa**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-121">Go to **Transportation management > Setup > Rating > Rate master**.</span></span>
1. <span data-ttu-id="e90f8-122">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-122">Select **New**.</span></span>
1. <span data-ttu-id="e90f8-123">No campo **Mestre de taxa**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e90f8-123">In the **Rate master** field, type a value.</span></span>
1. <span data-ttu-id="e90f8-124">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e90f8-124">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="e90f8-125">No campo **ID de metadados de classificação**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e90f8-125">In the **Rating metadata ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="e90f8-126">A ID de metadados de classificação determinará os dados necessários para o mestre de taxa, uma vez que ela define os metadados esperados pelo mecanismo de gerenciamento de transporte usando esse mestre de taxa.</span><span class="sxs-lookup"><span data-stu-id="e90f8-126">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the transportation management engine using this rate master.</span></span>  
1. <span data-ttu-id="e90f8-127">Para este exemplo, selecione a opção P2P.</span><span class="sxs-lookup"><span data-stu-id="e90f8-127">For this example, select the P2P option.</span></span> <span data-ttu-id="e90f8-128">Isso já está definido nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="e90f8-128">This is already defined in the demo data.</span></span>
1. <span data-ttu-id="e90f8-129">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e90f8-129">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="e90f8-130">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-130">Select **Save**.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="e90f8-131">Configurar base da taxa</span><span class="sxs-lookup"><span data-stu-id="e90f8-131">Set up rate base</span></span>

1. <span data-ttu-id="e90f8-132">Selecione **Base de taxa**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-132">Select **Rate base**.</span></span>
    * <span data-ttu-id="e90f8-133">A base da taxa determina a taxa da transportadora, e pode ser usada para configurar uma estrutura de tarifa uma vez que ela estrutura as taxas nos pontos de interrupção definidos pelo mestre de interrupção.</span><span class="sxs-lookup"><span data-stu-id="e90f8-133">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="e90f8-134">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-134">Select **New**.</span></span>
3. <span data-ttu-id="e90f8-135">No campo **Base de taxa**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e90f8-135">In the **Rate base** field, type a value.</span></span>
4. <span data-ttu-id="e90f8-136">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e90f8-136">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="e90f8-137">No campo **Mestre de interrupção**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e90f8-137">In the **Break master** field, select the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e90f8-138">Mestres de interrupção são usados para definir a estrutura de definição de preços e seus pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="e90f8-138">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="e90f8-139">A estrutura de definição de preços usa definição de preços hierarquizada baseada em dimensões físicas.</span><span class="sxs-lookup"><span data-stu-id="e90f8-139">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="e90f8-140">Neste exemplo, use peso.</span><span class="sxs-lookup"><span data-stu-id="e90f8-140">For this example, use weight.</span></span> <span data-ttu-id="e90f8-141">Isso já está definido nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="e90f8-141">This is already defined in the demo data.</span></span>
7. <span data-ttu-id="e90f8-142">Na lista, selecione o link na linha destacada.</span><span class="sxs-lookup"><span data-stu-id="e90f8-142">In the list, select the link in the highlighted row.</span></span>
8. <span data-ttu-id="e90f8-143">Expanda a seção **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-143">Expand the **Details** section.</span></span>
9. <span data-ttu-id="e90f8-144">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-144">Select **New**.</span></span>
10. <span data-ttu-id="e90f8-145">No campo **CEP de entrega De**, digite "30301".</span><span class="sxs-lookup"><span data-stu-id="e90f8-145">In the **Drop-off Postal Code From** field, type "30301".</span></span>
11. <span data-ttu-id="e90f8-146">No campo **CEP de entrega Até**, digite "30318".</span><span class="sxs-lookup"><span data-stu-id="e90f8-146">In the **Drop-off Postal Code To** field, type "30318".</span></span>
12. <span data-ttu-id="e90f8-147">No campo **Região do país de entrega**, digite "USA".</span><span class="sxs-lookup"><span data-stu-id="e90f8-147">In the **Drop-off Country Region** field, type "USA".</span></span>
13. <span data-ttu-id="e90f8-148">No campo **<1,00 Lbs**, digite "100".</span><span class="sxs-lookup"><span data-stu-id="e90f8-148">In the **<1.00 Lbs** field, type "100".</span></span>
    * <span data-ttu-id="e90f8-149">Insira a taxa por libras se o peso total da carga for menor que 1 libra.</span><span class="sxs-lookup"><span data-stu-id="e90f8-149">Insert the rate per pounds if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="e90f8-150">No campo **<5,00 Lbs**, digite "300".</span><span class="sxs-lookup"><span data-stu-id="e90f8-150">In the **<5.00 Lbs** field, type "300".</span></span>
    * <span data-ttu-id="e90f8-151">Insira a taxa por libras se o peso total da carga for menor que 5 libras.</span><span class="sxs-lookup"><span data-stu-id="e90f8-151">Insert the rate per pounds if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="e90f8-152">No campo **<20,00 Lbs**, digite "500".</span><span class="sxs-lookup"><span data-stu-id="e90f8-152">In the **<20.00 Lbs** field, type "500".</span></span>
    * <span data-ttu-id="e90f8-153">Insira a taxa por libras se o peso total da carga for menor que 20 libras.</span><span class="sxs-lookup"><span data-stu-id="e90f8-153">Insert the rate per pounds if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="e90f8-154">No campo **<100,00 Lbs**, digite "1000".</span><span class="sxs-lookup"><span data-stu-id="e90f8-154">In the **<100.00 Lbs** field, type "1000".</span></span>
    * <span data-ttu-id="e90f8-155">Insira a taxa por libras se o peso total da carga for menor que 100 libras.</span><span class="sxs-lookup"><span data-stu-id="e90f8-155">Insert the rate per pounds if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="e90f8-156">No campo **<1.000,00 Lbs**, digite "3000".</span><span class="sxs-lookup"><span data-stu-id="e90f8-156">In the **<1,000.00 Lbs** field, type "3000".</span></span>
    * <span data-ttu-id="e90f8-157">Insira a taxa por libras se o peso total da carga for menor que 1000 libras.</span><span class="sxs-lookup"><span data-stu-id="e90f8-157">Insert the rate per pounds if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="e90f8-158">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-158">Select **Save**.</span></span>
19. <span data-ttu-id="e90f8-159">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e90f8-159">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="e90f8-160">Atribua base de taxa</span><span class="sxs-lookup"><span data-stu-id="e90f8-160">Assign rate base</span></span>

1. <span data-ttu-id="e90f8-161">Expanda a seção **Atribuições base de taxa**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-161">Expand the **Rate base assignments** section.</span></span>
2. <span data-ttu-id="e90f8-162">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-162">Select **New**.</span></span>
    * <span data-ttu-id="e90f8-163">Você pode ter diversas atribuições de base da taxa para cada mestre de taxa.</span><span class="sxs-lookup"><span data-stu-id="e90f8-163">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="e90f8-164">Isso possibilita criar vários pontos de preço para cada transportadora de acordo com os destinos, serviços ou diferentes bases da taxa.</span><span class="sxs-lookup"><span data-stu-id="e90f8-164">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="e90f8-165">Neste procedimento você irá criar somente uma atribuição de base da taxa.</span><span class="sxs-lookup"><span data-stu-id="e90f8-165">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="e90f8-166">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e90f8-166">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="e90f8-167">No campo **Base da taxa**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e90f8-167">In the **Rate base** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="e90f8-168">Na lista, selecione o link na linha destacada.</span><span class="sxs-lookup"><span data-stu-id="e90f8-168">In the list, select the link in the highlighted row.</span></span>
6. <span data-ttu-id="e90f8-169">No campo **Serviço**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e90f8-169">In the **Service** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="e90f8-170">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="e90f8-170">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="e90f8-171">Na lista, selecione o link na linha destacada.</span><span class="sxs-lookup"><span data-stu-id="e90f8-171">In the list, select the link in the highlighted row.</span></span>
9. <span data-ttu-id="e90f8-172">No campo **CEP de retirada**, digite "98052".</span><span class="sxs-lookup"><span data-stu-id="e90f8-172">In the **Pick-up Postal Code** field, type "98052".</span></span>
    * <span data-ttu-id="e90f8-173">Especifique de qual CEP essa atribuição da base da taxa deverá ser válida.</span><span class="sxs-lookup"><span data-stu-id="e90f8-173">Specify which postal code this rate base assignment should be valid from.</span></span>
10. <span data-ttu-id="e90f8-174">No campo **Região do país de retirada**, digite "USA".</span><span class="sxs-lookup"><span data-stu-id="e90f8-174">In the **Pick-up Country Region** field, type "USA".</span></span>
11. <span data-ttu-id="e90f8-175">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e90f8-175">Select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]