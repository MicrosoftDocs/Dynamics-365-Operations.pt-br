---
title: Estratégias de reabastecimento
description: Este tópico fornece informações sobre estratégias de reabastecimento e explica como você pode usar o campo Estratégia de reabastecimento nas linhas do modelo de reabastecimento de demanda do ciclo para selecionar como o reabastecimento é feito.
author: mirzaab
manager: tfehr
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-29
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 9c23126c6ab15a1924b34f98d33a0661011ba8bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996089"
---
# <a name="replenishment-strategies"></a><span data-ttu-id="dbbb6-103">Estratégias de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="dbbb6-103">Replenishment strategies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dbbb6-104">Os modelos definidos na página **Modelos de reabastecimento** incluem linhas de modelo de reabastecimento de demanda de ciclo que permitem selecionar como o reabastecimento é feito.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-104">The templates that are defined on the **Replenishment templates** page include wave demand replenishment template lines that let you select how replenishment is done.</span></span> <span data-ttu-id="dbbb6-105">Cada linha agora inclui um campo **Estratégia de reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-105">Each line now includes a **Replenishment strategy** field.</span></span>

<span data-ttu-id="dbbb6-106">A estratégia *Quantidade por demanda de ciclos* é a estratégia padrão.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-106">The *Wave demand quantity* strategy is the default strategy.</span></span> <span data-ttu-id="dbbb6-107">É a estratégia de reabastecimento usada antes da introdução do campo **Estratégia de reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-107">It's the replenishment strategy that was used before the introduction of the **Replenishment strategy** field.</span></span> <span data-ttu-id="dbbb6-108">Ele usa as diretivas de localização de reabastecimento para localizar locais que podem ser reabastecidos.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-108">It uses the replenishment location directives to find locations that can be replenished.</span></span> <span data-ttu-id="dbbb6-109">Em seguida, ele reabastecerá esses locais até que a demanda seja coberta.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-109">It then replenishes those locations until the demand is covered.</span></span>

<span data-ttu-id="dbbb6-110">A estratégia *Capacidade máxima local* introduz uma nova funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-110">The *Maximum location capacity* strategy introduces some new functionality.</span></span> <span data-ttu-id="dbbb6-111">Como a estratégia *Quantidade por demanda de ciclos*, essa estratégia usa as diretivas de localização de reabastecimento para encontrar locais que podem ser reabastecidos e reabastecem esses locais até que a demanda seja coberta.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-111">Like the *Wave demand quantity* strategy, this strategy uses the replenishment location directives to find locations that can be replenished, and then it replenishes those locations until the demand is covered.</span></span> <span data-ttu-id="dbbb6-112">Ele difere da estratégia *Quantidade por demanda de ciclos*, pois todos os locais reabastecidos são reabastecidos para sua capacidade máxima, conforme definido pelos limites de estoque do local.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-112">It differs from the *Wave demand quantity* strategy in that all the replenished locations are replenished to their maximum capacity, as defined by the location stocking limits.</span></span> <span data-ttu-id="dbbb6-113">A estratégia *Capacidade máxima do local* tenta criar um trabalho para trazer a quantidade solicitada, além de uma quantidade extra, para preencher os locais que estão sendo reabastecidos.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-113">The *Maximum location capacity* strategy tries to create work to bring in the requested quantity, plus some extra quantity, to fill the locations that are being replenished.</span></span> <span data-ttu-id="dbbb6-114">No entanto, em alguns casos, essa tentativa poderá falhar.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-114">However, in some cases, that attempt might fail.</span></span> <span data-ttu-id="dbbb6-115">Por exemplo, os locais de massa talvez não tenham estoque suficiente para cobrir a quantidade extra.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-115">For example, the bulk locations might not have enough inventory to cover the extra quantity.</span></span> <span data-ttu-id="dbbb6-116">Nesses casos, o sistema detecta a falha e tenta recuperar.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-116">In these cases, the system detects the failure and tries to recover.</span></span>

<span data-ttu-id="dbbb6-117">Pico de época é um exemplo de uma situação em que a estratégia *Capacidade máxima do local* é em comparação à estratégia *Quantidade por demanda de ciclos*.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-117">Peak season is one example of a situation where the *Maximum location capacity* strategy is preferable to the *Wave demand quantity* strategy.</span></span> <span data-ttu-id="dbbb6-118">Durante a época de pico, alguns itens podem estar vendendo em alto volume.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-118">During peak season, some items might be selling at high volume.</span></span> <span data-ttu-id="dbbb6-119">Portanto, você pode desejar reabastecer proativamente as localizações de separação relevantes o máximo possível para reduzir o número de IDs de trabalho criadas para reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-119">Therefore, you might want to proactively replenish the relevant picking locations as much as possible, to reduce the number of work IDs that are created for replenishment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dbbb6-120">Para aproveitar totalmente a estratégia *Capacidade máxima local*, você deve redefinir os limites de estoque para os locais relevantes.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-120">To take full advantage of the *Maximum location capacity* strategy, you must redefine the stocking limits for the relevant locations.</span></span> <span data-ttu-id="dbbb6-121">Caso contrário, essa estratégia funcionará da mesma forma que a estratégia *Quantidade por demanda de ciclo*.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-121">Otherwise, this strategy works just like the *Wave demand quantity* strategy.</span></span>

## <a name="turn-on-the-replenish-to-max-based-on-stocking-limits-feature"></a><span data-ttu-id="dbbb6-122">Ativar o reabastecimento para máximo com base no recurso de limites de estoque</span><span class="sxs-lookup"><span data-stu-id="dbbb6-122">Turn on the Replenish to max based on stocking limits feature</span></span>

<span data-ttu-id="dbbb6-123">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-123">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="dbbb6-124">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-124">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of this feature and turn it on if it's required.</span></span> <span data-ttu-id="dbbb6-125">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dbbb6-125">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="dbbb6-126">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="dbbb6-126">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="dbbb6-127">**Nome do recurso:** *Ativar o reabastecimento para máximo com base nos limites de estoque*</span><span class="sxs-lookup"><span data-stu-id="dbbb6-127">**Feature name:** *Replenish to max based on stocking limits*</span></span>

## <a name="set-up-replenishment-strategies"></a><span data-ttu-id="dbbb6-128">Definir estratégias de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="dbbb6-128">Set up replenishment strategies</span></span>

<span data-ttu-id="dbbb6-129">Para acessar os modelos, acesse **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-129">To access the templates, go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span> <span data-ttu-id="dbbb6-130">Na seção **Visão geral**, selecione ou crie um modelo de reabastecimento de demanda de ondas onde o campo **Tipo de reabastecimento** está definido como *Demanda de ciclo*.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-130">In the **Overview** section, select or create a wave demand replenishment template where the **Replenishment type** field is set to *Wave demand*.</span></span> <span data-ttu-id="dbbb6-131">Em seguida, configure as linhas do modelo de reabastecimento na seção **Detalhes do modelo de reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-131">Then set up the replenishment template lines in the **Replenishment template details** section.</span></span> <span data-ttu-id="dbbb6-132">Para cada linha, no campo **Estratégia de reabastecimento**, selecione a estratégia de reabastecimento que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-132">For each line, in the **Replenishment strategy** field, select the replenishment strategy that you want to use.</span></span>

<span data-ttu-id="dbbb6-133">![Página de modelos de reabastecimento](media/ReplenTempWaveDmdMaxLocCap.png "Página de modelos de reabastecimento")</span><span class="sxs-lookup"><span data-stu-id="dbbb6-133">![Replenishment templates page](media/ReplenTempWaveDmdMaxLocCap.png "Replenishment templates page")</span></span>

<span data-ttu-id="dbbb6-134">Se a coluna **Estratégia de reabastecimento** não aparecer na grade na seção **Detalhes do modelo de reabastecimento**, verifique se o recurso foi ativado e se o modelo de reabastecimento selecionado tem um tipo de reabastecimento *Demanda de ciclo*.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-134">If the **Replenishment strategy** column doesn't appear in the grid in the **Replenishment template details** section, make sure that the feature has been turned on, and that the selected replenishment template has a replenishment type of *Wave demand*.</span></span>

> [!NOTE]
> <span data-ttu-id="dbbb6-135">A estratégia *Quantidade por demanda de ciclos* é a estratégia padrão.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-135">The *Wave demand quantity* strategy is the default strategy.</span></span> <span data-ttu-id="dbbb6-136">Portanto, basta atualizar as linhas do modelo de reabastecimento em que você deseja usar a estratégia *Capacidade máxima local*.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-136">Therefore, you just have to update the replenishment template lines where you want to use the *Maximum location capacity* strategy instead.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="dbbb6-137">Cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="dbbb6-137">Example scenarios</span></span>

### <a name="example-1"></a><span data-ttu-id="dbbb6-138">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="dbbb6-138">Example 1</span></span>

<span data-ttu-id="dbbb6-139">Neste exemplo, há apenas um modelo de reabastecimento que tem apenas uma linha de modelo de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-139">For this example, there is only one replenishment template that has only one replenishment template line.</span></span>

<span data-ttu-id="dbbb6-140">Você cria uma ordem de venda de 130 peças (pcs) do item A0001.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-140">You create a sales order for 130 pieces (pcs) of item A0001.</span></span> <span data-ttu-id="dbbb6-141">Antes de liberar a ordem para o depósito, o depósito é configurado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dbbb6-141">Before you release the order to the warehouse, the warehouse is set up in the following way:</span></span>

- <span data-ttu-id="dbbb6-142">Existe apenas um local de massa e tem 500 pcs de estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-142">There is only one bulk location, and it has 500 pcs of available on-hand inventory.</span></span>
- <span data-ttu-id="dbbb6-143">Há três locais de separação, cada qual com um limite de estoque de 100 pcs.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-143">There are three pick locations, each of which has a stocking limit of 100 pcs.</span></span> <span data-ttu-id="dbbb6-144">(Lembre-se de que os limites de estoque são necessários para a estratégia *Capacidade máxima de local*.)</span><span class="sxs-lookup"><span data-stu-id="dbbb6-144">(Remember that stocking limits are required for the *Maximum location capacity* strategy.)</span></span>
- <span data-ttu-id="dbbb6-145">O reabastecimento de locais put é o mesmo que os de locais pick de vendas.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-145">The replenishment put locations are the same as the sales pick locations.</span></span>
- <span data-ttu-id="dbbb6-146">A unidade de reabastecimento é uma caixa (1 caixa = 20 pcs).</span><span class="sxs-lookup"><span data-stu-id="dbbb6-146">The replenishment unit is a box (1 box = 20 pcs).</span></span>

<span data-ttu-id="dbbb6-147">No momento da ordem, o seguinte estoque está disponível nos locais de separação de vendas:</span><span class="sxs-lookup"><span data-stu-id="dbbb6-147">At the time of the order, the following inventory is on hand at the sales pick locations:</span></span>

- <span data-ttu-id="dbbb6-148">**Grupo-001:** 20 pcs (1 caixa)</span><span class="sxs-lookup"><span data-stu-id="dbbb6-148">**Pick-001:** 20 pcs (1 box)</span></span>
- <span data-ttu-id="dbbb6-149">**Grupo-002:** 0 pcs</span><span class="sxs-lookup"><span data-stu-id="dbbb6-149">**Pick-002:** 0 pcs</span></span>
- <span data-ttu-id="dbbb6-150">**Grupo-003:** 0 pcs</span><span class="sxs-lookup"><span data-stu-id="dbbb6-150">**Pick-003:** 0 pcs</span></span>

<span data-ttu-id="dbbb6-151">Inicialmente, a estratégia de reabastecimento é definida como *Quantidade de demanda de ciclos*.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-151">Initially, the replenishment strategy is set to *Wave demand quantity*.</span></span>

<span data-ttu-id="dbbb6-152">Depois que você libera a ordem de venda para o depósito e o processamento de ciclos é executado para o ciclo, você obtém o seguinte trabalho de reabastecimento:</span><span class="sxs-lookup"><span data-stu-id="dbbb6-152">After you release the sales order to the warehouse, and wave processing runs for the wave, you get the following replenishment work:</span></span>

- <span data-ttu-id="dbbb6-153">**Trabalho de reabastecimento 1:** Escolha 4 caixas do local em massa e coloque-as na localização pick-001.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-153">**Replenishment work 1:** Pick 4 boxes from the bulk location, and put them in location pick-001.</span></span>
- <span data-ttu-id="dbbb6-154">**Trabalho de reabastecimento 2:** Escolha 2 caixas do local em massa e coloque-as na localização pick-002.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-154">**Replenishment work 2:** Pick 2 boxes from the bulk location, and put them in location pick-002.</span></span>

<span data-ttu-id="dbbb6-155">Você obtém duas IDs de trabalho de reabastecimento porque deve reabastecer dois locais e não há suporte para vários lugares.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-155">You get two replenishment work IDs because you must replenish two locations, and multi-puts aren't supported.</span></span>

<span data-ttu-id="dbbb6-156">Se você definir a estratégia de reabastecimento como *Capacidade máxima do local*, obterá o seguinte trabalho de reabastecimento:</span><span class="sxs-lookup"><span data-stu-id="dbbb6-156">If you set the replenishment strategy to *Maximum location capacity* instead, you get the following replenishment work:</span></span>

- <span data-ttu-id="dbbb6-157">**Trabalho de reabastecimento 1:** Escolha 4 caixas do local em massa e coloque-as na localização pick-001.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-157">**Replenishment work 1:** Pick 4 boxes from the bulk location, and put them in location pick-001.</span></span>
- <span data-ttu-id="dbbb6-158">**Trabalho de reabastecimento 2:** Escolha 5 caixas do local em massa e coloque-as na localização pick-002.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-158">**Replenishment work 2:** Pick 5 boxes from the bulk location, and put them in location pick-002.</span></span>

<span data-ttu-id="dbbb6-159">[![Exemplo 1](media/ReplenTemp_example_1.png "Exemplo 1")](media/ReplenTemp_example_1_large.png)</span><span class="sxs-lookup"><span data-stu-id="dbbb6-159">[![Example 1](media/ReplenTemp_example_1.png "Example 1")](media/ReplenTemp_example_1_large.png)</span></span>

### <a name="example-2"></a><span data-ttu-id="dbbb6-160">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="dbbb6-160">Example 2</span></span>

<span data-ttu-id="dbbb6-161">Este exemplo mostra o que acontece quando o local de massa não tem estoque suficiente para cobrir a quantidade extra.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-161">This example shows what happens when the bulk location doesn't have enough inventory to cover the extra quantity.</span></span> <span data-ttu-id="dbbb6-162">Ele usa o mesmo cenário que o exemplo 1, mas o local de massa tem 160 pcs (8 caixas).</span><span class="sxs-lookup"><span data-stu-id="dbbb6-162">It uses the same scenario as example 1, but the bulk location has 160 pcs (8 boxes).</span></span>

<span data-ttu-id="dbbb6-163">A estratégia *Quantidade por demanda de ciclos* cria o mesmo trabalho feito no exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-163">The *Wave demand quantity* strategy creates the same work that it did in example 1.</span></span>

<span data-ttu-id="dbbb6-164">No entanto, como a estratégia *Capacidade máxima de localização* tenta criar as IDs de trabalho como fazia no exemplo 1, ela pode falhar.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-164">However, because the *Maximum location capacity* strategy tries to create the work IDs as it did in example 1, it might fail.</span></span> <span data-ttu-id="dbbb6-165">Nesse ponto, o sistema tenta recuperar.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-165">At that point, the system tries to recover.</span></span>

<span data-ttu-id="dbbb6-166">Dependendo da configuração da opção **Permitir divisão** nas diretivas de localização para a separação de reabastecimento, dois resultados são possíveis:</span><span class="sxs-lookup"><span data-stu-id="dbbb6-166">Depending on the setting of the **Allow split** option on the location directives for replenishment picking, two outcomes are possible:</span></span>

- <span data-ttu-id="dbbb6-167">Se a opção **Permitir divisão** estiver definida como *Sim*, o trabalho de reabastecimento a seguir será criado:</span><span class="sxs-lookup"><span data-stu-id="dbbb6-167">If the **Allow split** option is set to *Yes*, the following replenishment work is created:</span></span>

    - <span data-ttu-id="dbbb6-168">**Trabalho de reabastecimento 1:** Escolha 4 caixas do local em massa e coloque-as na localização pick-001.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-168">**Replenishment work 1:** Pick 4 boxes from the bulk location, and put them in location pick-001.</span></span>
    - <span data-ttu-id="dbbb6-169">**Trabalho de reabastecimento 2:** Escolha 4 caixas do local em massa e coloque-as na localização pick-002.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-169">**Replenishment work 2:** Pick 4 boxes from the bulk location, and put them in location pick-002.</span></span>

- <span data-ttu-id="dbbb6-170">Se a opção **Permitir divisão** estiver definida como *Não*, o trabalho de reabastecimento a seguir será criado:</span><span class="sxs-lookup"><span data-stu-id="dbbb6-170">If the **Allow split** option is set to *No*, the following replenishment work is created:</span></span>

    - <span data-ttu-id="dbbb6-171">**Trabalho de reabastecimento 1:** Escolha 4 caixas do local em massa e coloque-as na localização pick-001.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-171">**Replenishment work 1:** Pick 4 boxes from the bulk location, and put them in location pick-001.</span></span>
    - <span data-ttu-id="dbbb6-172">**Trabalho de reabastecimento 2:** Escolha 2 caixas do local em massa e coloque-as na localização pick-002.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-172">**Replenishment work 2:** Pick 2 boxes from the bulk location, and put them in location pick-002.</span></span>

<span data-ttu-id="dbbb6-173">Os resultados são diferentes devido às informações disponíveis quando você cria o trabalho.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-173">The outcomes differ because of the information that is available when you create the work.</span></span> <span data-ttu-id="dbbb6-174">Quando **Permitir divisão** é definida como *Sim* nas diretivas de localização para a separação de reabastecimento, você sabe que gerencia para encontrar 160 pcs.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-174">When the **Allow split** is set to *Yes* on the location directives for replenishment picking, you know that you managed to find 160 pcs.</span></span> <span data-ttu-id="dbbb6-175">Portanto, você pode criar trabalho para essa quantidade.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-175">Therefore, you can create work for that quantity.</span></span> <span data-ttu-id="dbbb6-176">No entanto, quando a opção **Permitir divisão** está definida como *Não*, você não sabe a existência das 160 pcs.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-176">However, when the **Allow split** option is set to *No*, you don't know about the existence of the 160 pcs.</span></span> <span data-ttu-id="dbbb6-177">Como a quantidade extra que você decidiu reabastecer era de 3 caixas, você pode soltar essa quantidade extra e tentar a quantidade original novamente.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-177">Because the extra quantity that you decided to replenish was 3 boxes, you drop that extra quantity and try the original quantity again.</span></span>

<span data-ttu-id="dbbb6-178">[![Exemplo 2](media/ReplenTemp_example_2.png "Exemplo 2")](media/ReplenTemp_example_2_large.png)</span><span class="sxs-lookup"><span data-stu-id="dbbb6-178">[![Example 2](media/ReplenTemp_example_2.png "Example 2")](media/ReplenTemp_example_2_large.png)</span></span>

<span data-ttu-id="dbbb6-179">Portanto, para obter a quantidade máxima para os locais reabastecidos, você deve definir a opção **Permitir divisão** como *Sim* nas diretivas de localização para a separação de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="dbbb6-179">Therefore, to get the maximum quantity to the replenished locations, you should set the **Allow split** option to *Yes* on the location directives for replenishment picking.</span></span>