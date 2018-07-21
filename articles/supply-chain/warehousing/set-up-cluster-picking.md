---
title: "Configurar separação de cluster"
description: "Este tópico descreve como configurar a separação do cluster e como aplicar a confirmação do item com a separação do cluster."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 52750321588d69483439873861682636c13a4936
ms.contentlocale: pt-br
ms.lasthandoff: 07/21/2018

---

[!include[banner](../includes/banner.md)]

# <a name="set-up-cluster-picking"></a><span data-ttu-id="ddbb4-103">Configurar separação de cluster</span><span class="sxs-lookup"><span data-stu-id="ddbb4-103">Set up cluster picking</span></span>

<span data-ttu-id="ddbb4-104">Este tópico descreve como habilitar os operadores para usarem os dispositivos móveis para agrupar o trabalho de separação em clusters, de forma que possam selecionar itens de um único local para várias ordens de trabalho ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-104">This topic describes how to enable workers to use their mobile devices to group picking work into clusters, so that they can pick items from a single location for multiple work orders at the same time.</span></span> <span data-ttu-id="ddbb4-105">Isso é chamado de *separação de cluster*.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-105">This is called *cluster picking*.</span></span>

## <a name="about-cluster-picking"></a><span data-ttu-id="ddbb4-106">Sobre separação de cluster</span><span class="sxs-lookup"><span data-stu-id="ddbb4-106">About cluster picking</span></span>

<span data-ttu-id="ddbb4-107">Depois que as ordens de trabalho são liberadas para o depósito, o trabalhador pode usar um dispositivo móvel para atribuir as ordens a um cluster.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-107">After work orders are released to the warehouse, the worker can use a mobile device to assign the orders to a cluster.</span></span> <span data-ttu-id="ddbb4-108">O cluster organizará o trabalho de separação para o trabalhador.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-108">The cluster will organize the picking work for the worker.</span></span> <span data-ttu-id="ddbb4-109">Quando uma ordem de trabalho é atribuída a um cluster, o trabalhador deve usar a separação de cluster para executar o trabalho de separação da ordem.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-109">When a work order is assigned to a cluster, the worker must use cluster picking to perform the picking work for the order.</span></span> <span data-ttu-id="ddbb4-110">O trabalhador não pode usar outros métodos de separação.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-110">The worker cannot use other picking methods.</span></span> <span data-ttu-id="ddbb4-111">Se uma ordem de trabalho for atribuída a um cluster por engano, o trabalhador deverá dividir o cluster e recriá-lo.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-111">If a work order is assigned to a cluster by mistake, the worker must break the cluster and then re-create it.</span></span>

<span data-ttu-id="ddbb4-112">Se for necessário, um trabalhador poderá passar um cluster para outro trabalhador.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-112">If needed, a worker can pass a cluster to another worker.</span></span> <span data-ttu-id="ddbb4-113">Isso altera o status do cluster para Aprovado.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-113">This changes the cluster status to Passed.</span></span> <span data-ttu-id="ddbb4-114">Quando o trabalhador usa um dispositivo móvel para indicar que o trabalho de separação e armazenamento foi concluído, a remessa ou a carga deve ser confirmada no cliente do Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-114">When the worker uses a mobile device to indicate that the picking and put away work is completed, the shipment or load must be confirmed in the Dynamics 365 for Finance and Operations client.</span></span>

## <a name="set-up-cluster-picking"></a><span data-ttu-id="ddbb4-115">Configurar separação de cluster</span><span class="sxs-lookup"><span data-stu-id="ddbb4-115">Set up cluster picking</span></span>

<span data-ttu-id="ddbb4-116">Para habilitar a separação de cluster, você deverá configurar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ddbb4-116">To enable cluster picking, you must set up the following:</span></span>

-   <span data-ttu-id="ddbb4-117">**Perfis do cluster** – especifique se deseja gerar automaticamente as IDs do cluster, o número de posições a serem usadas, quando dividir os clusters e como sequenciar e verificar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-117">**Cluster profiles** – Specify whether to automatically generate cluster IDs, the number of positions to use, when to break clusters, and how to sequence and verify the picking work.</span></span>

-   <span data-ttu-id="ddbb4-118">**Modelos de trabalho** – defina como criar o trabalho de separação para a separação do cluster.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-118">**Work templates** – Define how to create the picking work for cluster picking.</span></span>

-   <span data-ttu-id="ddbb4-119">**Diretivas de local** – especifique de onde separar itens e onde colocá-los.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-119">**Location directives** – Specify where to pick items from, and where to put them.</span></span>

-   <span data-ttu-id="ddbb4-120">**Itens de menu do dispositivo móvel** – configure um item de menu do dispositivo móvel para usar o trabalho existente que é direcionado pela separação de cluster.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-120">**Mobile device menu items** – Configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="ddbb4-121">Você deve adicionar o item de menu a um menu do dispositivo móvel de forma que seja exibido em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-121">You must then add the menu item to a mobile device menu so that it is displayed on mobile devices.</span></span>

-   <span data-ttu-id="ddbb4-122">**Parâmetros de gerenciamento de depósito** – especifique a sequência numérica que será usada se você quiser gerar identificadores para clusters.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-122">**Warehouse management parameters** – Specify the number sequence to use if you want to generate identifiers for clusters.</span></span>

## <a name="set-up-a-cluster-profile"></a><span data-ttu-id="ddbb4-123">Configurar um perfil de cluster</span><span class="sxs-lookup"><span data-stu-id="ddbb4-123">Set up a cluster profile</span></span>

<span data-ttu-id="ddbb4-124">Para configurar um perfil de cluster, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ddbb4-124">To set up a cluster profile, follow these steps:</span></span>

1.  <span data-ttu-id="ddbb4-125">Clique em **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Perfis do cluster**.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-125">Click **Warehouse management** \> **Setup** \> **Mobile device** \> **Cluster profiles**.</span></span>

2.  <span data-ttu-id="ddbb4-126">Clique em **Novo** para criar um novo perfil.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-126">Click **New** to create a new profile.</span></span>

3.  <span data-ttu-id="ddbb4-127">Clique em **Criar cluster** e, em **Classificação de cluster**, clique em **Novo** para configurar os critérios de classificação para o cluster.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-127">Click **Create cluster** and, under **Cluster sorting**, click **New** to set up the sorting criteria for the cluster.</span></span> <span data-ttu-id="ddbb4-128">Os critérios de classificação controlam a ordem na qual o trabalhador realizará o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-128">The sorting criteria control the order in which the worker will perform the picking work.</span></span> <span data-ttu-id="ddbb4-129">É possível adicionar quantos critérios forem necessários.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-129">You can add as many criteria as needed.</span></span>

4.  <span data-ttu-id="ddbb4-130">No campo **Número de sequência**, insira um número para definir a ordem na qual os critérios de classificação são processados.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-130">In the **Sequence number** field, enter a number to define the order in which the sorting criteria are processed.</span></span>

5.  <span data-ttu-id="ddbb4-131">No campo **Nome do campo**, selecione o campo que determinará a classificação.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-131">In the **Field name** field, select the field that will determine the sorting.</span></span> <span data-ttu-id="ddbb4-132">Por exemplo, se você selecionar o campo **WMSLocationId**, o trabalho será classificado por local.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-132">For example, if you select the **WMSLocationId** field, the work will be sorted by location.</span></span>

6.  <span data-ttu-id="ddbb4-133">No campo **Classificação**, selecione uma das seguintes opções.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-133">In the **Sorting** field, select one of the following options.</span></span>

| <span data-ttu-id="ddbb4-134">**Opção**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-134">**Option**</span></span>     | <span data-ttu-id="ddbb4-135">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-135">**Description**</span></span>                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ddbb4-136">**Crescente**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-136">**Ascending**</span></span>  | <span data-ttu-id="ddbb4-137">O trabalho de separação é ordenado em ordem crescente com base nos critérios de classificação.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-137">Picking work is sequenced in ascending order based on the sorting criteria.</span></span> <span data-ttu-id="ddbb4-138">Por exemplo, se você usa o campo **WMSLocationId** como critério de classificação e as IDs do local são 1, 2, 3, 4, você escolherá primeiro do local 4.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-138">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 4 first.</span></span> |
| <span data-ttu-id="ddbb4-139">**Decrescente**</span><span class="sxs-lookup"><span data-stu-id="ddbb4-139">**Descending**</span></span> | <span data-ttu-id="ddbb4-140">O trabalho de separação é ordenado em ordem decrescente com base nos critérios de classificação.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-140">Picking work is sequenced in descending order based on the sorting criteria.</span></span> <span data-ttu-id="ddbb4-141">Por exemplo, se você usa o campo **WMSLocationId** como critério de classificação e as IDs do local são 1, 2, 3, 4, você escolherá primeiro do local 1.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-141">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 1 first.</span></span> |

## <a name="item-confirmation"></a><span data-ttu-id="ddbb4-142">Confirmação do item</span><span class="sxs-lookup"><span data-stu-id="ddbb4-142">Item confirmation</span></span>

<span data-ttu-id="ddbb4-143">Quando a separação do cluster é aplicada, confirmação do item é importante para verificar os itens adicionados aos clusters.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-143">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="ddbb4-144">Você pode verificar os itens na separação do cluster durante o processo de separação do cluster.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-144">You can verify items in cluster picking during the cluster picking process.</span></span> <span data-ttu-id="ddbb4-145">A configuração é baseada na configuração de código de barras de produto.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-145">The setup is based on the product bar code setup.</span></span>

### <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="ddbb4-146">Configurar verificação do item com separação de cluster</span><span class="sxs-lookup"><span data-stu-id="ddbb4-146">Set up item verification with cluster picking</span></span>

1.  <span data-ttu-id="ddbb4-147">No item de menu do dispositivo móvel, abra o formulário de configuração para a confirmação de trabalho: **Gerenciamento de depósito** \> **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-147">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** \> **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>

2.  <span data-ttu-id="ddbb4-148">Do item de menu de dispositivo móvel, abra a **Configuração de confirmação de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-148">From the mobile device menu item, open **Work confirmation setup**.</span></span> <span data-ttu-id="ddbb4-149">A opção **Confirmação do produto** permite que você verifique cada peça de estoque no dispositivo móvel quando verificado.</span><span class="sxs-lookup"><span data-stu-id="ddbb4-149">The **Product confirmation** option allows you to verify each piece of inventory from the mobile device when scanned.</span></span>

