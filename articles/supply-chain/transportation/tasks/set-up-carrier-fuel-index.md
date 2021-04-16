---
title: Configurar um índice de combustível da transportadora
description: Este guia mostra como criar uma região do índice de combustível, um índice de combustível e um índice de combustível da transportadora.
author: ShylaThompson
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1e972f2ba8211c47b11a4b83dac9ff60f813b1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837565"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="fa187-103">Configurar um índice de combustível da transportadora</span><span class="sxs-lookup"><span data-stu-id="fa187-103">Set up a carrier fuel index</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fa187-104">Este guia mostra como criar uma região do índice de combustível, um índice de combustível e um índice de combustível da transportadora.</span><span class="sxs-lookup"><span data-stu-id="fa187-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="fa187-105">A região do índice de combustível especifica em qual região o índice de combustível deve ser aplicado, e o índice de combustível especifica um preço do combustível para um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="fa187-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="fa187-106">Para refletir a alteração nos preços do combustível ao longo do tempo, você pode associar múltiplos índices de combustível da transportadora.</span><span class="sxs-lookup"><span data-stu-id="fa187-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="fa187-107">Essas tarefas são feitas tipicamente por um coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="fa187-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="fa187-108">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="fa187-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="fa187-109">Crie uma região de índice de combustível</span><span class="sxs-lookup"><span data-stu-id="fa187-109">Create a fuel index region</span></span>
1. <span data-ttu-id="fa187-110">Vá para Gerenciamento de transporte > Configurar > Índices de combustível > Regiões de índices de combustível.</span><span class="sxs-lookup"><span data-stu-id="fa187-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="fa187-111">Primeiro você deve criar as diferentes regiões, onde você opera e calcula as diferentes sobretaxas de combustível.</span><span class="sxs-lookup"><span data-stu-id="fa187-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="fa187-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fa187-112">Click New.</span></span>
3. <span data-ttu-id="fa187-113">No campo Região, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fa187-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="fa187-114">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fa187-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="fa187-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fa187-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="fa187-116">Crie um índice de combustível</span><span class="sxs-lookup"><span data-stu-id="fa187-116">Create a fuel index</span></span>
1. <span data-ttu-id="fa187-117">Vá para Gerenciamento de transporte > Configurar > Índices de combustível > Índices de combustível.</span><span class="sxs-lookup"><span data-stu-id="fa187-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="fa187-118">Para as regiões que você configurou é preciso inserir os preços atuais do combustível.</span><span class="sxs-lookup"><span data-stu-id="fa187-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="fa187-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fa187-119">Click New.</span></span>
3. <span data-ttu-id="fa187-120">No campo Região, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fa187-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="fa187-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fa187-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="fa187-122">No campo Preço por galão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="fa187-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="fa187-123">No campo Data e hora efetiva de início, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="fa187-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="fa187-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fa187-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="fa187-125">Crie um índice de combustível da transportadora</span><span class="sxs-lookup"><span data-stu-id="fa187-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="fa187-126">Vá para Gerenciamento de transporte > Configurar > Índices de combustível > Índices de combustível da transportadora.</span><span class="sxs-lookup"><span data-stu-id="fa187-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="fa187-127">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fa187-127">Click New.</span></span>
3. <span data-ttu-id="fa187-128">No campo Índice de combustível da transportadora, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fa187-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="fa187-129">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fa187-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fa187-130">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fa187-130">Click New.</span></span>
6. <span data-ttu-id="fa187-131">No campo Data e hora efetiva de início, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="fa187-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="fa187-132">No campo PPG De, insira um número.</span><span class="sxs-lookup"><span data-stu-id="fa187-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="fa187-133">Neste exemplo, você pode definir o campo PPG De para 1,95.</span><span class="sxs-lookup"><span data-stu-id="fa187-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="fa187-134">No campo PPG Até, insira um número.</span><span class="sxs-lookup"><span data-stu-id="fa187-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="fa187-135">Neste exemplo, você pode definir o campo PPG Até para 2.</span><span class="sxs-lookup"><span data-stu-id="fa187-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="fa187-136">No campo Porcentagem, insira um número.</span><span class="sxs-lookup"><span data-stu-id="fa187-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="fa187-137">Neste exemplo, você pode definir a porcentagem para 3.</span><span class="sxs-lookup"><span data-stu-id="fa187-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="fa187-138">No campo Moeda, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fa187-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="fa187-139">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fa187-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="fa187-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fa187-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="fa187-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fa187-141">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]