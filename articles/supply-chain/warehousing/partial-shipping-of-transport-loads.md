---
title: Remessa parcial de uma carga de transporte
description: Este tópico explica como você pode enviar uma carga parcialmente e adiar o planejamento de capacidade da carga.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: f12f1c08d4d04c284f0f927f99747e763696e43a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234648"
---
# <a name="partial-shipment-of-a-transport-load"></a><span data-ttu-id="ef51f-103">Remessa parcial de uma carga de transporte</span><span class="sxs-lookup"><span data-stu-id="ef51f-103">Partial shipment of a transport load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ef51f-104">Configurando a remessa de cargas parcial, você pode administrar as cargas onde a capacidade não pode ser determinada até que todas as linhas de venda sejam adicionadas a uma carga.</span><span class="sxs-lookup"><span data-stu-id="ef51f-104">By setting up partial shipment of loads, you can handle loads where the capacity can't be determined until all the sales lines have been added to a load.</span></span> <span data-ttu-id="ef51f-105">O processo poderá ser finalizado quando a contagem exata de palete for conhecida.</span><span class="sxs-lookup"><span data-stu-id="ef51f-105">The process can then be finalized when the exact pallet count is known.</span></span> <span data-ttu-id="ef51f-106">Portanto, você não precisa concluir quais paletes serão atribuídos a qual transporte até o momento em que um transporte está sendo carregado fisicamente para o estoque preparado.</span><span class="sxs-lookup"><span data-stu-id="ef51f-106">Therefore, you don't have to decide which pallets will be assigned to which transport until the moment when a transport is being physically loaded out of the staged inventory.</span></span>

<span data-ttu-id="ef51f-107">Este recurso fornece uma alternativa para a aplicação de uma estrutura mais rígida, onde você pode determinar que paletes serão atribuídos ao transporte antes do trabalho de separação ou do trabalho de carga ser criado.</span><span class="sxs-lookup"><span data-stu-id="ef51f-107">This feature offers an alternative to the enforcement of a more rigid structure, where you must determine which pallets will be assigned to which transport before picking work or loading work can be created.</span></span> <span data-ttu-id="ef51f-108">Em vez disso, os usuários poderão configurar cargas individuais para uma confirmação parcial de remessa.</span><span class="sxs-lookup"><span data-stu-id="ef51f-108">Instead, users can configure individual loads for a partial shipment confirmation.</span></span> <span data-ttu-id="ef51f-109">Os processos de carga de transporte para essas em cargas podem ocorrer depois.</span><span class="sxs-lookup"><span data-stu-id="ef51f-109">The transport loading processes for those loads can then occur.</span></span> <span data-ttu-id="ef51f-110">Portanto, o departamento de planejamento de transporte pode planejar cargas sem ter que considerar a capacidade de transportes individuais.</span><span class="sxs-lookup"><span data-stu-id="ef51f-110">Therefore, the transportation planning department can plan loads without having to consider the capacity of individual transports.</span></span>

<span data-ttu-id="ef51f-111">No momento da carga, os funcionários podem definir uma nova carga de transporte que poderá ser carregada para um palete.</span><span class="sxs-lookup"><span data-stu-id="ef51f-111">At the time of loading, workers can define a new transport load that a pallet can be loaded to.</span></span> <span data-ttu-id="ef51f-112">Como alternativa, eles podem identificar uma carga de transporte existente.</span><span class="sxs-lookup"><span data-stu-id="ef51f-112">Alternatively, they can identify an existing transport load.</span></span> <span data-ttu-id="ef51f-113">Esses dados pode ser registrados por meio de um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="ef51f-113">This data can be recorded via a mobile device.</span></span> <span data-ttu-id="ef51f-114">Portanto, vários trabalhadores de depósito podem carregar o estoque das mesmas cargas ou de cargas diferentes no mesmo carrinho.</span><span class="sxs-lookup"><span data-stu-id="ef51f-114">Therefore, several warehouse workers can load inventory from the same loads or different loads onto the same truck.</span></span> <span data-ttu-id="ef51f-115">As cargas podem ser enviadas totalmente ou parcialmente.</span><span class="sxs-lookup"><span data-stu-id="ef51f-115">The loads can then be fully or partially shipped.</span></span>

> [!NOTE] 
> <span data-ttu-id="ef51f-116">Para carregar o estoque de uma carga para uma determinada carga de transporte e enviá-la parcialmente, o trabalho deve ser gerado usando uma classe de carga em um modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ef51f-116">In order to load inventory from a load to a specific transport load and partially ship the load, work must be generated by using a loading class in a work template.</span></span> <span data-ttu-id="ef51f-117">O trabalho ordinário de separação do tipo **Separação** não pode ser carregado para uma carga de transporte, como um carrinho.</span><span class="sxs-lookup"><span data-stu-id="ef51f-117">Ordinary picking work of the **Picking** type can't be loaded to a transport load such as a truck.</span></span>

## <a name="set-up-transport-loads-for-partial-shipment"></a><span data-ttu-id="ef51f-118">Configurar cargas de transporte para remessa parcial</span><span class="sxs-lookup"><span data-stu-id="ef51f-118">Set up transport loads for partial shipment</span></span>

<span data-ttu-id="ef51f-119">A configuração de remessa parcial de cargas consistem nos dois procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="ef51f-119">The setup for partial shipment of loads consists of the following two procedures.</span></span>

### <a name="set-the-loading-strategy"></a><span data-ttu-id="ef51f-120">Configurar a estratégia de carga</span><span class="sxs-lookup"><span data-stu-id="ef51f-120">Set the loading strategy</span></span>

<span data-ttu-id="ef51f-121">É necessário habilitar a carga parcial definindo a estratégia de carga.</span><span class="sxs-lookup"><span data-stu-id="ef51f-121">You must enable partial loading by setting the loading strategy.</span></span> <span data-ttu-id="ef51f-122">Você pode definir a estratégia de carga após criar uma carga.</span><span class="sxs-lookup"><span data-stu-id="ef51f-122">You can set the loading strategy after you've created a load.</span></span>

1. <span data-ttu-id="ef51f-123">Selecione **Gerenciamento de depósito** \> **Cargas** \> **Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-123">Select **Warehouse management** \> **Loads** \> **All loads**.</span></span>
2. <span data-ttu-id="ef51f-124">Selecione uma carga e clique em **Cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-124">Select a load, and then click **Header**.</span></span>
3. <span data-ttu-id="ef51f-125">No campo **Estratégia de carga** , selecione **Remessa de carga parcial permitida**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-125">In the **Loading strategy** field, select **Partial load shipping allowed**.</span></span>

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a><span data-ttu-id="ef51f-126">Criar um item de menu para cargas de transporte</span><span class="sxs-lookup"><span data-stu-id="ef51f-126">Create a menu item for loading of transport loads</span></span>

<span data-ttu-id="ef51f-127">É necessário criar um novo item de menu que permite que as cargas de transporte sejam carregadas.</span><span class="sxs-lookup"><span data-stu-id="ef51f-127">You must create a new menu item that enables transport loads to be loaded.</span></span> <span data-ttu-id="ef51f-128">Uma carga de transporte permite o agrupamento de linhas de trabalho de uma carga ou de várias cargas.</span><span class="sxs-lookup"><span data-stu-id="ef51f-128">A transport load lets you group work lines from one load or multiple loads.</span></span> <span data-ttu-id="ef51f-129">Tudo que é adicionado à carga de transporte pode ser enviado por um scanner móvel.</span><span class="sxs-lookup"><span data-stu-id="ef51f-129">Everything that is added to the transport load can then be shipped by using a mobile scanner.</span></span>

1. <span data-ttu-id="ef51f-130">Selecione **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-130">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="ef51f-131">Selecione **Novo** e, depois, no campo **Modo** , selecione **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-131">Select **New**, and then, in the **Mode** field, select **Work**.</span></span>
3. <span data-ttu-id="ef51f-132">Defina a opção **Usar trabalho existente** para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-132">Set the **Use existing work** option to **Yes**.</span></span>
4. <span data-ttu-id="ef51f-133">Na guia **Geral**, no campo **Direcionado por**, selecione **Carga de transporte**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-133">On the **General** tab, in the **Directed by** field, select **Transport loading**.</span></span>
5. <span data-ttu-id="ef51f-134">Para habilitar a confirmação de remessa em um scanner móvel, no campo **Tipo de confirmação de remessa permitido** , selecione **Carga de transporte**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-134">To enable shipment confirmation on a mobile scanner, in the **Allowed ship confirmation type** field, select **Transport load**.</span></span>

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a><span data-ttu-id="ef51f-135">Confirmar remessa de uma carga de transporte do cliente</span><span class="sxs-lookup"><span data-stu-id="ef51f-135">Confirm shipment of a transport load from the client</span></span>

<span data-ttu-id="ef51f-136">Essa configuração permite confirmar uma carga de transporte que inclua uma carga máxima ou uma carga parcialmente carregada a ser enviada.</span><span class="sxs-lookup"><span data-stu-id="ef51f-136">This setup lets you confirm a transport load that includes a full load or a partially loaded load to be shipped.</span></span>

1. <span data-ttu-id="ef51f-137">Selecione **Gerenciamento de depósito** \> **Cargas** \> **Cargas de transporte**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-137">Select **Warehouse management** \> **Loads** \> **Transport loads**.</span></span>
2. <span data-ttu-id="ef51f-138">No painel de ação, na guia **Enviar e receber** , no grupo **Confirmar** , selecione **Transporte**.</span><span class="sxs-lookup"><span data-stu-id="ef51f-138">On the Action Pane, on the **Ship and receive** tab, in the **Confirm** group, select **Transport**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]