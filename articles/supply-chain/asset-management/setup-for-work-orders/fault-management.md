---
title: Gerenciamento de falhas
description: Este tópico explica o gerenciamento de falhas no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 48c90a8b776cc16804de8e20ada7d8ca347fa5b9
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874730"
---
# <a name="fault-management"></a><span data-ttu-id="fc832-103">Gerenciamento de falhas</span><span class="sxs-lookup"><span data-stu-id="fc832-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="fc832-104">No Gerenciamento de ativos, você pode usar o designer de falhas para configurar sintomas, áreas e tipos de falha nos tipos de ativos.</span><span class="sxs-lookup"><span data-stu-id="fc832-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="fc832-105">Assim, você pode gerenciar falhas detectadas nos ativos.</span><span class="sxs-lookup"><span data-stu-id="fc832-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="fc832-106">Além disso, as causas e sugestões de falha para corrigir falhas podem ser registradas em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="fc832-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="fc832-107">O processo para registro e gerenciamento de falhas consiste nessas etapas.</span><span class="sxs-lookup"><span data-stu-id="fc832-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="fc832-108">Crie uma lista de sintomas, áreas e tipos de falhas que podem ocorrer nos seus tipos de ativos.</span><span class="sxs-lookup"><span data-stu-id="fc832-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="fc832-109">No designer de falhas, configure sintomas, áreas e tipos de falhas.</span><span class="sxs-lookup"><span data-stu-id="fc832-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="fc832-110">Veja alguns exemplos que podem ajudar você a entender a diferença entre sintomas, áreas e tipos de falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="fc832-111">**Sintomas de falha:**</span><span class="sxs-lookup"><span data-stu-id="fc832-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="fc832-112">Tensões desequilibradas</span><span class="sxs-lookup"><span data-stu-id="fc832-112">Unbalanced voltages</span></span>
- <span data-ttu-id="fc832-113">Curto-circuito</span><span class="sxs-lookup"><span data-stu-id="fc832-113">Short circuit</span></span>
- <span data-ttu-id="fc832-114">Ruído</span><span class="sxs-lookup"><span data-stu-id="fc832-114">Noise</span></span>
- <span data-ttu-id="fc832-115">Vazamento</span><span class="sxs-lookup"><span data-stu-id="fc832-115">Leak</span></span>
- <span data-ttu-id="fc832-116">Vibrações</span><span class="sxs-lookup"><span data-stu-id="fc832-116">Vibrations</span></span>

<span data-ttu-id="fc832-117">**Áreas de falha:**</span><span class="sxs-lookup"><span data-stu-id="fc832-117">**Fault areas:**</span></span>

- <span data-ttu-id="fc832-118">Elétrica</span><span class="sxs-lookup"><span data-stu-id="fc832-118">Electrical</span></span>
- <span data-ttu-id="fc832-119">Mecânica</span><span class="sxs-lookup"><span data-stu-id="fc832-119">Mechanical</span></span>
- <span data-ttu-id="fc832-120">Hidráulica</span><span class="sxs-lookup"><span data-stu-id="fc832-120">Hydraulic</span></span>
- <span data-ttu-id="fc832-121">Pneumático</span><span class="sxs-lookup"><span data-stu-id="fc832-121">Pneumatic</span></span>

<span data-ttu-id="fc832-122">**Tipos de falha:**</span><span class="sxs-lookup"><span data-stu-id="fc832-122">**Fault types:**</span></span>

- <span data-ttu-id="fc832-123">Enrolamento do estator principal com defeito</span><span class="sxs-lookup"><span data-stu-id="fc832-123">Faulty main stator winding</span></span>
- <span data-ttu-id="fc832-124">Diodo defeituoso</span><span class="sxs-lookup"><span data-stu-id="fc832-124">Faulty diode</span></span>
- <span data-ttu-id="fc832-125">Enrolamentos sujos</span><span class="sxs-lookup"><span data-stu-id="fc832-125">Dirty windings</span></span>
- <span data-ttu-id="fc832-126">Gerador defeituoso</span><span class="sxs-lookup"><span data-stu-id="fc832-126">Defective generator</span></span>
- <span data-ttu-id="fc832-127">Sensor defeituoso</span><span class="sxs-lookup"><span data-stu-id="fc832-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="fc832-128">Criar sintomas de falha</span><span class="sxs-lookup"><span data-stu-id="fc832-128">Create fault symptoms</span></span>

<span data-ttu-id="fc832-129">Siga estas etapas para criar uma lista de sintomas que podem ser usados no designer de falhas.</span><span class="sxs-lookup"><span data-stu-id="fc832-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="fc832-130">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Sintomas de falha**.</span><span class="sxs-lookup"><span data-stu-id="fc832-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="fc832-131">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="fc832-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="fc832-132">No campo **Sintoma de falha**, insira um nome para o sintoma de falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="fc832-133">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="fc832-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="fc832-134">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fc832-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="fc832-135">Criar áreas de falha</span><span class="sxs-lookup"><span data-stu-id="fc832-135">Create fault areas</span></span>

<span data-ttu-id="fc832-136">Siga estas etapas para criar uma lista de áreas ou locais que podem ser usados no designer de falhas.</span><span class="sxs-lookup"><span data-stu-id="fc832-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="fc832-137">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Áreas de falha**.</span><span class="sxs-lookup"><span data-stu-id="fc832-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="fc832-138">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="fc832-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="fc832-139">No campo **Área com falha**, insira um nome para a área com falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="fc832-140">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="fc832-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="fc832-141">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fc832-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="fc832-142">Criar tipos de falha</span><span class="sxs-lookup"><span data-stu-id="fc832-142">Create fault types</span></span>

<span data-ttu-id="fc832-143">Siga estas etapas para criar uma lista de tipos de falhas que podem ser usados no designer de falhas.</span><span class="sxs-lookup"><span data-stu-id="fc832-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="fc832-144">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Tipos de falha**.</span><span class="sxs-lookup"><span data-stu-id="fc832-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="fc832-145">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="fc832-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="fc832-146">No campo **Tipo de falha**, insira um nome para o tipo de falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="fc832-147">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="fc832-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="fc832-148">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fc832-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="fc832-149">Configurar o designer de falha</span><span class="sxs-lookup"><span data-stu-id="fc832-149">Set up the fault designer</span></span>

<span data-ttu-id="fc832-150">No designer de falhas, você configura os dados das falhas nos tipos de ativos.</span><span class="sxs-lookup"><span data-stu-id="fc832-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="fc832-151">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Designer de falha**.</span><span class="sxs-lookup"><span data-stu-id="fc832-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="fc832-152">No painel esquerdo, selecione o tipo de ativo para o qual configurar um registro de falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="fc832-153">Na Guia Rápida **Sintoma de falha**, selecione **Adicionar linha** e, no campo **Sintoma de falha**, selecione um sintoma de falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="fc832-154">Na Guia Rápida **Área com falha**, selecione **Adicionar linha** e, no campo **Área com falha**, selecione uma área com falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="fc832-155">Na Guia Rápida **Tipo de falha**, selecione **Adicionar linha** e, no campo **Tipo de falha**, selecione um tipo de falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="fc832-156">Para criar rapidamente combinações de todos os sintomas, áreas e tipos de falha existentes para o tipo de ativo selecionado, selecione **Criar combinações de falhas**.</span><span class="sxs-lookup"><span data-stu-id="fc832-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="fc832-157">Essa função é útil se você adicionou muitos sintomas, áreas e tipos de falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="fc832-158">É mais fácil excluir as linhas de qualquer combinação irrelevante para o tipo de ativo que criar novas linhas manualmente.</span><span class="sxs-lookup"><span data-stu-id="fc832-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc832-159">Para copiar a configuração de sintomas, áreas e tipos de falha de um tipo de ativo para o tipo de ativo selecionado, selecione **Copiar do tipo de ativo**.</span><span class="sxs-lookup"><span data-stu-id="fc832-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="fc832-160">Selecione **Salvar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="fc832-160">Select **Save** to save your changes.</span></span>

![Figura 1](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="fc832-162">Criar causas de falha</span><span class="sxs-lookup"><span data-stu-id="fc832-162">Create fault causes</span></span>

<span data-ttu-id="fc832-163">Siga estas etapas para criar uma lista de causas conhecidas de falhas que podem ser adicionadas a uma ordem de serviço ou solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="fc832-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="fc832-164">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Causas da falha**.</span><span class="sxs-lookup"><span data-stu-id="fc832-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="fc832-165">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="fc832-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="fc832-166">No campo **Causa da falha**, insira um nome para a causa da falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="fc832-167">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="fc832-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="fc832-168">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fc832-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="fc832-169">Criar soluções de falha</span><span class="sxs-lookup"><span data-stu-id="fc832-169">Create fault remedies</span></span>

<span data-ttu-id="fc832-170">Siga estas etapas para criar uma lista de sugestões para correção e reparo que podem ser adicionadas a uma ordem de serviço ou solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="fc832-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="fc832-171">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Falha** \> **Soluções de falha**.</span><span class="sxs-lookup"><span data-stu-id="fc832-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="fc832-172">Selecione **Novo** para criar um registro.</span><span class="sxs-lookup"><span data-stu-id="fc832-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="fc832-173">No campo **Solução de falha**, insira um nome para a solução de falha.</span><span class="sxs-lookup"><span data-stu-id="fc832-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="fc832-174">No campo **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="fc832-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="fc832-175">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fc832-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="fc832-176">Você pode alterar os nomes dos sintomas, áreas, tipos, causas e soluções de suas falhas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fc832-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="fc832-177">As alterações de nome são refletidas automaticamente nos registros de falha relacionados.</span><span class="sxs-lookup"><span data-stu-id="fc832-177">The name changes are automatically reflected in the related fault registrations.</span></span>
