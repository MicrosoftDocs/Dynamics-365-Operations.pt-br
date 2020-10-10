---
title: Análise de falhas de ativos
description: Este tópico explica a análise de falhas de ativos no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectFaultCalculate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e911f7ca3b67acd9d5a1b170d8c99135da730847
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889137"
---
# <a name="asset-fault-analysis"></a><span data-ttu-id="505b7-103">Análise de falhas de ativos</span><span class="sxs-lookup"><span data-stu-id="505b7-103">Asset fault analysis</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="505b7-104">No Gerenciamento de Ativos, você pode analisar os registros de falhas de ativos para obter uma visão geral do número total de falhas registradas durante um período específico.</span><span class="sxs-lookup"><span data-stu-id="505b7-104">In Asset Management, you can analyze asset fault registrations to get an overview of the total number of faults registered during a specific period.</span></span> <span data-ttu-id="505b7-105">Os registros de falhas podem ser analisados de diferentes perspectivas; por exemplo, com foco em ativos, tipos de ativos, locais funcionais, sintomas de falhas ou tipos de falhas.</span><span class="sxs-lookup"><span data-stu-id="505b7-105">Fault registrations can be analyzed from different perspectives, for example with focus on assets, asset types, functional locations, fault symptoms, or fault types.</span></span>

1. <span data-ttu-id="505b7-106">Clique em **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Análise de falhas de ativos**.</span><span class="sxs-lookup"><span data-stu-id="505b7-106">Click **Asset management** > **Inquiries** > **Asset fault** > **Asset fault analysis**.</span></span>

2. <span data-ttu-id="505b7-107">Na caixa de diálogo **Cálculo da análise de falhas de ativos**, você pode usar o campo **Nível** para indicar o grau de detalhamento nas linhas de falhas de ativos relativas a locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="505b7-107">In the **Asset fault analysis calculation** dialog, you can use the **Level** field to indicate how detailed you want the asset fault lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="505b7-108">Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de localização funcional em vários níveis, todas as linhas de falhas de ativos para um local funcional serão mostradas no nível superior e, portanto, as horas em uma linha poderão ser adicionadas em locais funcionais localizados em um nível inferior.</span><span class="sxs-lookup"><span data-stu-id="505b7-108">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all asset fault lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
        
    <span data-ttu-id="505b7-109">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de falhas de ativos em todo o nível do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="505b7-109">If you insert the number "0" in the **Level** field, you will see a detailed result showing all asset fault lines on all the functional location level to which they are related.</span></span>

3. <span data-ttu-id="505b7-110">Para limitar a pesquisa, você poderá selecionar ativos específicos, datas de falha, causas de falha e soluções de falha na Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="505b7-110">If you want to limit the search, you can select specific assets, fault dates, fault causes, and fault remedies on the **Records to include** FastTab.</span></span>

4. <span data-ttu-id="505b7-111">Clique em **OK** para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="505b7-111">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="505b7-112">Na guia **Análise de falhas de ativos**, clique em um ou mais botões **Agrupar por** para exibir o nível de detalhes que deseja ver.</span><span class="sxs-lookup"><span data-stu-id="505b7-112">On the **Asset fault analysis** tab, click one or more **Group by** buttons to display the detail level you want to see.</span></span> <span data-ttu-id="505b7-113">Os botões ativados são realçados.</span><span class="sxs-lookup"><span data-stu-id="505b7-113">Activated buttons are highlighted.</span></span> <span data-ttu-id="505b7-114">Ative ou desative os botões clicando neles.</span><span class="sxs-lookup"><span data-stu-id="505b7-114">Activate or deactivate buttons by clicking on them.</span></span>

6. <span data-ttu-id="505b7-115">Clique em **Atualizar cálculos** para mostrar suas seleções na tela.</span><span class="sxs-lookup"><span data-stu-id="505b7-115">Click **Update calculations** to show your selections on the screen.</span></span> 

>[!NOTE]
><span data-ttu-id="505b7-116">Sempre que você ativar ou desativar um botão **Agrupar por**, lembre-e de clicar no botão **Atualizar cálculos** .</span><span class="sxs-lookup"><span data-stu-id="505b7-116">Every time you activate or deactivate a **Group by** button, remember to click the **Update calculations** button.</span></span> <span data-ttu-id="505b7-117">Isso é necessário porque uma grande quantidade de dados é processada à medida que você recalcula a probabilidade de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-117">This is required because a large amount of data is processed as you are recalculating fault probability.</span></span>

## <a name="examples"></a><span data-ttu-id="505b7-118">Exemplos</span><span class="sxs-lookup"><span data-stu-id="505b7-118">Examples</span></span>

<span data-ttu-id="505b7-119">Há várias formas de analisar registros de falhas.</span><span class="sxs-lookup"><span data-stu-id="505b7-119">There are many ways to analyze fault registrations.</span></span> <span data-ttu-id="505b7-120">Esta seção tem cinco exemplos de como seleções de dados diferentes podem fornecer mais insight e detalhes na análise dos registros de falhas de ativos.</span><span class="sxs-lookup"><span data-stu-id="505b7-120">This section has five examples of how different data selections can provide more insight and detail when analyzing asset fault registrations.</span></span>

### <a name="group-by-symptoms"></a><span data-ttu-id="505b7-121">Agrupar por sintomas</span><span class="sxs-lookup"><span data-stu-id="505b7-121">Group by symptoms</span></span>

<span data-ttu-id="505b7-122">Na captura de tela abaixo, apenas o botão **Sintoma** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="505b7-122">In the screenshot below, only the **Symptom** button is selected.</span></span>

- <span data-ttu-id="505b7-123">Registros de falhas foram feitos com três sintomas de falha: "Vazamento de ar", "Fusível queimado" e "Equipamento danificado".</span><span class="sxs-lookup"><span data-stu-id="505b7-123">Fault registrations have been made on three fault symptoms: "Air leak", "Blown fuse", and "Equipment jammed".</span></span>  
- <span data-ttu-id="505b7-124">Na coluna **Probabilidade %**, todas as porcentagens somam 100%.</span><span class="sxs-lookup"><span data-stu-id="505b7-124">In the **Probability %** column, all percentages add up to 100%.</span></span> <span data-ttu-id="505b7-125">A probabilidade é baseada em todos os registros **Sintoma** nessa análise de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-125">Probability is based on all **Symptom** registrations in this fault analysis.</span></span>

![Figura 1](media/06-controlling-and-reporting.png)

### <a name="group-by-symptoms-and-time-period"></a><span data-ttu-id="505b7-127">Agrupar por sintomas e período</span><span class="sxs-lookup"><span data-stu-id="505b7-127">Group by symptoms and time period</span></span>

<span data-ttu-id="505b7-128">Na captura de tela abaixo, **Ano** e **Mês** são adicionados para mostrar como você pode exibir os registros de falhas durante um período selecionado.</span><span class="sxs-lookup"><span data-stu-id="505b7-128">In the screenshot below, **Year** and **Month** are added to show how you can view fault registrations during a selected period.</span></span>

- <span data-ttu-id="505b7-129">Os sintomas de falha agora são mostrados como registros por ano/mês.</span><span class="sxs-lookup"><span data-stu-id="505b7-129">The fault symptoms are now shown as registrations per year/month.</span></span>  
- <span data-ttu-id="505b7-130">Na coluna **Probabilidade %**, se você adicionar todas as porcentagens de cada mês, elas somarão 100%.</span><span class="sxs-lookup"><span data-stu-id="505b7-130">In the **Probability %** column, if you add all percentages for each month, they add up to 100%.</span></span> <span data-ttu-id="505b7-131">A probabilidade é baseada nos registros **Sintoma** nessa análise de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-131">Probability is based on the **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="505b7-132">Se você tiver um grande número de linhas em um ativo, mas uma grande porcentagem se destacar em uma linha, isso seria uma indicação de um sintoma de falha a ser examinado com mais cuidado para encontrar uma maneira de limitar o número de registros desse sintoma de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-132">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 2](media/07-controlling-and-reporting.png)

### <a name="group-by-multiple-symptoms-and-assets"></a><span data-ttu-id="505b7-134">Agrupar por vários sintomas e ativos</span><span class="sxs-lookup"><span data-stu-id="505b7-134">Group by multiple symptoms and assets</span></span>

<span data-ttu-id="505b7-135">A combinação de ativos e um tipo de ativo é usada como base para os cálculos mostrados nas três capturas de tela abaixo, o que aumentará em nível de detalhes.</span><span class="sxs-lookup"><span data-stu-id="505b7-135">The combination of assets and an asset type is used as a basis for the calculations shown in the three screenshots below, which will increase in detail level.</span></span>  

<span data-ttu-id="505b7-136">Geralmente, os botões nos grupos do Painel de Ações **Agrupar por data**, **Agrupar por ativo**, **Agrupar por local funcional**, bem como o botão **Falha** (ID da Falha), contêm períodos ou relações de ativos.</span><span class="sxs-lookup"><span data-stu-id="505b7-136">Generally, the buttons in the **Group by date**, **Group by asset**, **Group by functional location** Action Pane groups, as well as the **Fault** button (Fault ID), contain periods or asset relations.</span></span> <span data-ttu-id="505b7-137">Os botões **Sintoma**, **Área**, **Tipo**, **Causa** e **Recurso** são categorizações usadas no gerenciamento de falhas para analisar registros de falhas de ativos e identificar áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="505b7-137">The **Symptom**, **Area**, **Type**, **Cause**, and **Remedy** buttons are categorizations used in fault management to analyze asset fault registrations and pinpoint problem areas.</span></span>  

<span data-ttu-id="505b7-138">**Agrupar por sintoma, ativo e tipo de ativo**</span><span class="sxs-lookup"><span data-stu-id="505b7-138">**Group by symptom, asset, and asset type**</span></span>

<span data-ttu-id="505b7-139">Na captura de tela abaixo, **Ativo** e **Tipo de ativo** foram adicionados para fornecer mais detalhes sobre os registros de falhas.</span><span class="sxs-lookup"><span data-stu-id="505b7-139">In the screenshot below, **Asset** and **Asset type** were added to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="505b7-140">Os sintomas de falha agora são divididos em combinações **Ativo** / **Tipo de ativo** / **Sintoma**.</span><span class="sxs-lookup"><span data-stu-id="505b7-140">The fault symptoms are now split up in **Asset** / **Asset type** / **Symptom** combinations.</span></span>  
- <span data-ttu-id="505b7-141">Na coluna **Probabilidade %**, se você adicionar todas as porcentagens para a combinação de **Ativo** / **Tipo de ativo** / **Sintoma** respectivamente, cada uma delas somará 100%.</span><span class="sxs-lookup"><span data-stu-id="505b7-141">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** respectively, they each add up to 100%.</span></span> <span data-ttu-id="505b7-142">A probabilidade é baseada nos registros **Sintoma** nessa análise de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-142">Probability is based on **Symptom** registrations in this fault analysis.</span></span> <span data-ttu-id="505b7-143">Se você tiver um grande número de linhas em um ativo, mas uma grande porcentagem se destacar em uma linha, isso seria uma indicação de um sintoma de falha a ser examinado com mais cuidado para encontrar uma maneira de limitar o número de registros desse sintoma de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-143">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault symptom to examine more closely to find a way to limit the number of registrations for that fault symptom.</span></span>

![Figura 3](media/08-controlling-and-reporting.png)

<span data-ttu-id="505b7-145">**Agrupar por dois sintomas, ativo e tipo de ativo**</span><span class="sxs-lookup"><span data-stu-id="505b7-145">**Group by two symptoms, asset, and asset type**</span></span>

<span data-ttu-id="505b7-146">Na captura de tela abaixo, a **Área** foi adicionada a **Sintoma**, **Ativo** e **Tipo de ativo** para fornecer mais detalhes sobre os registros de falhas.</span><span class="sxs-lookup"><span data-stu-id="505b7-146">In the screenshot below, **Area** was added to **Symptom**, **Asset**, and **Asset type** to provide more detail regarding fault registrations.</span></span>

- <span data-ttu-id="505b7-147">Na coluna **Probabilidade %**, se você adicionar todas as porcentagens para a combinação de **Ativo** / **Tipo de ativo** / **Sintoma** em um ativo, cada uma delas somará 100%.</span><span class="sxs-lookup"><span data-stu-id="505b7-147">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="505b7-148">A probabilidade é baseada na combinação de **Sintoma** e **Área** nessa análise de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-148">Probability is based on the combination of **Symptom** and **Area** in this fault analysis.</span></span> <span data-ttu-id="505b7-149">Se você tiver um grande número de linhas em um ativo, mas uma grande porcentagem se destacar em uma linha, isso seria uma indicação de uma área de falha a ser examinada com mais cuidado para encontrar uma maneira de limitar o número de registros dessa área de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-149">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault area to examine more closely to find a way to limit the number of registrations for that fault area.</span></span>  

![Figura 4](media/09-controlling-and-reporting.png)

<span data-ttu-id="505b7-151">**Agrupar por três sintomas, ativo e tipo de ativo**</span><span class="sxs-lookup"><span data-stu-id="505b7-151">**Group by three symptom, asset, and asset type**</span></span>

<span data-ttu-id="505b7-152">Na captura de tela abaixo, o **Tipo** foi adicionado e o cálculo mais detalhado neste exemplo é mostrado.</span><span class="sxs-lookup"><span data-stu-id="505b7-152">In the screenshot below, **Type** was added, and the most detailed calculation in this example is shown.</span></span>
 
- <span data-ttu-id="505b7-153">Na coluna **Probabilidade %**, se você adicionar todas as porcentagens para a combinação de **Ativo** / **Tipo de ativo** / **Sintoma** em um ativo, cada uma delas somará 100%.</span><span class="sxs-lookup"><span data-stu-id="505b7-153">In the **Probability %** column, if you add all percentages for the combination of **Asset** / **Asset type** / **Symptom** on an asset, they each add up to 100%.</span></span> <span data-ttu-id="505b7-154">A probabilidade é baseada na combinação de **Sintoma**, **Área** e **Tipo** nessa análise de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-154">Probability is based on the combination of **Symptom**, **Area**, and **Type** in this fault analysis.</span></span> <span data-ttu-id="505b7-155">Se você tiver um grande número de linhas em um ativo, mas uma grande porcentagem se destacar em uma linha, isso seria uma indicação de um tipo de falha a ser examinado com mais cuidado para encontrar uma maneira de limitar o número de registros desse tipo de falha.</span><span class="sxs-lookup"><span data-stu-id="505b7-155">If you have a large number of lines on an asset, but a large percentage stands out on a line, that would be an indication of a fault type to examine more closely to find a way to limit the number of registrations on that fault type.</span></span>

![Figura 5](media/10-controlling-and-reporting.png)


>[!NOTE]
><span data-ttu-id="505b7-157">Para obter uma visão geral de todos os registros de falhas criados em ordens de serviço e solicitações de manutenção, clique em **Gerenciamento de ativos** > **Consultas** > **Falha de ativo** > **Falhas de ativo**.</span><span class="sxs-lookup"><span data-stu-id="505b7-157">For an overview of all fault registrations created on work orders and maintenance requests, click **Asset management** > **Inquiries** > **Asset fault** > **Asset faults**.</span></span> <span data-ttu-id="505b7-158">Na página **Falhas de ativo**, selecione um registro de falha de ativo e expanda o painel **Informações relacionadas** para ver informações sobre a ordem de serviço ou solicitação de manutenção relacionada.</span><span class="sxs-lookup"><span data-stu-id="505b7-158">On the **Asset faults** page, select an asset fault registration and expand the **Related information** pane to see information regarding the related work order or maintenance request.</span></span>

