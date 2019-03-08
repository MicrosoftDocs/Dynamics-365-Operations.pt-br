---
title: Configurar mestres de taxa
description: Este procedimento mostra como configurar um mestre de taxa.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 462bfce89fa77c8830a93a22b0dd6c8c8fb2cde6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "344906"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="2cc0d-103">Configurar mestres de taxa</span><span class="sxs-lookup"><span data-stu-id="2cc0d-103">Set up rate masters</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2cc0d-104">Este procedimento mostra como configurar um mestre de taxa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="2cc0d-105">O gerente logístico geralmente configura os mestres de taxa, dependendo dos contratos assinados com as transportadoras.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="2cc0d-106">Neste cenário você irá configurar um mestre de taxa para um transportador aérea.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="2cc0d-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-rate-master"></a><span data-ttu-id="2cc0d-108">Configurar mestre de taxa</span><span class="sxs-lookup"><span data-stu-id="2cc0d-108">Set up rate master</span></span>
1. <span data-ttu-id="2cc0d-109">Vá para Gerenciamento de transporte > Configurar > Classificação > Mestre de taxa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-109">Go to Transportation management > Setup > Rating > Rate master.</span></span>
2. <span data-ttu-id="2cc0d-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-110">Click New.</span></span>
3. <span data-ttu-id="2cc0d-111">No campo Mestre de taxa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-111">In the Rate master field, type a value.</span></span>
4. <span data-ttu-id="2cc0d-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2cc0d-113">No campo ID de metadados de classificação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-113">In the Rating metadata ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2cc0d-114">A ID de metadados de classificação irá determinar os dados necessários para o mestre de taxa, uma vez que ela define os metadados esperados pelo mecanismo TMS usando esse mestre de taxa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-114">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the TMS engine using this rate master.</span></span>  
6. <span data-ttu-id="2cc0d-115">Para este exemplo, selecione a opção P2P.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-115">For this example, select the P2P option</span></span>
7. <span data-ttu-id="2cc0d-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="2cc0d-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-117">Click Save.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="2cc0d-118">Configurar base da taxa</span><span class="sxs-lookup"><span data-stu-id="2cc0d-118">Set up rate base</span></span>
1. <span data-ttu-id="2cc0d-119">Clique em Base de taxa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-119">Click Rate base.</span></span>
    * <span data-ttu-id="2cc0d-120">A base da taxa determina a taxa da transportadora, e pode ser usada para configurar uma estrutura de tarifa uma vez que ela estrutura as taxas nos pontos de interrupção definidos pelo mestre de interrupção.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-120">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="2cc0d-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-121">Click New.</span></span>
3. <span data-ttu-id="2cc0d-122">No campo Base de taxa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-122">In the Rate base field, type a value.</span></span>
4. <span data-ttu-id="2cc0d-123">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-123">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2cc0d-124">No campo Mestre de interrupção, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-124">In the Break master field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2cc0d-125">Mestres de interrupção são usados para definir a estrutura de definição de preços e seus pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-125">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="2cc0d-126">A estrutura de definição de preços usa definição de preços hierarquizada baseada em dimensões físicas.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-126">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="2cc0d-127">Neste exemplo, use peso</span><span class="sxs-lookup"><span data-stu-id="2cc0d-127">For this example, use weight</span></span>
7. <span data-ttu-id="2cc0d-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-128">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="2cc0d-129">Ative a expansão da seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-129">Toggle the expansion of the Details section.</span></span>
9. <span data-ttu-id="2cc0d-130">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-130">Click New.</span></span>
10. <span data-ttu-id="2cc0d-131">No campo CEP de entrega De, digite '30301'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-131">In the Drop-off Postal Code From field, type '30301'.</span></span>
11. <span data-ttu-id="2cc0d-132">No campo CEP de entrega Até, digite '30318'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-132">In the Drop-off Postal Code To field, type '30318'.</span></span>
12. <span data-ttu-id="2cc0d-133">No campo Região do país de entrega, digite 'USA'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-133">In the Drop-off Country Region field, type 'USA'.</span></span>
13. <span data-ttu-id="2cc0d-134">No campo <1,00 Lbs, digite '100'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-134">In the <1.00 Lbs field, type '100'.</span></span>
    * <span data-ttu-id="2cc0d-135">Insira a taxa por libras se o peso total da carga for menor que 1 libra.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-135">Insert the rate per lbs if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="2cc0d-136">No campo <5,00 lbs, digite '300'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-136">In the <5.00 Lbs field, type '300'.</span></span>
    * <span data-ttu-id="2cc0d-137">Insira a taxa por libras se o peso total da carga for menor que 5 libras.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-137">Insert the rate per lbs if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="2cc0d-138">No campo <20,00 lbs, digite '500'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-138">In the <20.00 Lbs field, type '500'.</span></span>
    * <span data-ttu-id="2cc0d-139">Insira a taxa por libras se o peso total da carga for menor que 20 libras.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-139">Insert the rate per lbs if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="2cc0d-140">No campo <100,00 lbs, digite '1000'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-140">In the <100.00 Lbs field, type '1000'.</span></span>
    * <span data-ttu-id="2cc0d-141">Insira a taxa por libras se o peso total da carga for menor que 100 libras.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-141">Insert the rate per lbs if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="2cc0d-142">No campo <1.000,00 lbs, digite '3000'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-142">In the <1,000.00 Lbs field, type '3000'.</span></span>
    * <span data-ttu-id="2cc0d-143">Insira a taxa por libras se o peso total da carga for menor que 1000 libras.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-143">Insert the rate per lbs if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="2cc0d-144">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-144">Click Save.</span></span>
19. <span data-ttu-id="2cc0d-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-145">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="2cc0d-146">Atribua base de taxa</span><span class="sxs-lookup"><span data-stu-id="2cc0d-146">Assign rate base</span></span>
1. <span data-ttu-id="2cc0d-147">Ative a expansão da seção Atribuições da base da taxa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-147">Toggle the expansion of the Rate base assignments section.</span></span>
2. <span data-ttu-id="2cc0d-148">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-148">Click New.</span></span>
    * <span data-ttu-id="2cc0d-149">Você pode ter diversas atribuições de base da taxa para cada mestre de taxa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-149">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="2cc0d-150">Isso possibilita criar vários pontos de preço para cada transportadora de acordo com os destinos, serviços ou diferentes bases da taxa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-150">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="2cc0d-151">Neste procedimento você irá criar somente uma atribuição de base da taxa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-151">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="2cc0d-152">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-152">In the Name field, type a value.</span></span>
4. <span data-ttu-id="2cc0d-153">No campo Base da taxa, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-153">In the Rate base field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2cc0d-154">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-154">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="2cc0d-155">No campo Serviço, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-155">In the Service field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="2cc0d-156">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-156">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="2cc0d-157">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2cc0d-158">No campo CEP de retirada, digite '98052'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-158">In the Pick-up Postal Code field, type '98052'.</span></span>
    * <span data-ttu-id="2cc0d-159">Especifique de qual CEP essa atribuição da base da taxa deverá ser válida.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-159">Specify which postal code this rate base assignment should be valid from.</span></span>    
10. <span data-ttu-id="2cc0d-160">No campo Região do país de retirada, digite 'USA'.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-160">In the Pick-up Country Region field, type 'USA'.</span></span>
11. <span data-ttu-id="2cc0d-161">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2cc0d-161">Click Save.</span></span>

