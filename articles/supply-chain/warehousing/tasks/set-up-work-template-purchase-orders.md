---
title: Configurar um modelo de trabalho para ordens de compra
description: Este tópico descreve como configurar um modelo de trabalho simples que será usado no armazenamento dos itens recebidos.
author: ShylaThompson
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6628936a56619de255ca7dc7b332b5819918c310
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422394"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a><span data-ttu-id="8dfbd-103">Configurar um modelo de trabalho para ordens de compra</span><span class="sxs-lookup"><span data-stu-id="8dfbd-103">Set up a work template for purchase orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8dfbd-104">Este tópico descreve como configurar um modelo de trabalho simples que será usado no armazenamento dos itens recebidos.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-104">This topic describes how to set up a simple work template to be used when putting away received items.</span></span> <span data-ttu-id="8dfbd-105">Modelos de trabalho determinam o conjunto de instruções apresentadas ao trabalhador do depósito em um dispositivo móvel ao mover itens da área de recebimento.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-105">Work templates determine the set of instructions presented to the warehouse worker on a mobile device when moving items from the receiving area.</span></span> <span data-ttu-id="8dfbd-106">Você pode usar esse procedimento com os dados mencionados na empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-106">You can use this procedure with the data mentioned in demo data company USMF.</span></span> <span data-ttu-id="8dfbd-107">Antes de iniciar este guia, crie uma ID de grupo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-107">Before you start this guide, create a work pool ID.</span></span> <span data-ttu-id="8dfbd-108">Neste exemplo, uma ID de grupo de trabalho chamada na Entrada é usada.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-108">In this example, a work pool ID called in Inbound is used.</span></span> <span data-ttu-id="8dfbd-109">Esse procedimento é destinado ao gerente do depósito.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="8dfbd-110">No painel de navegação, vá para **Módulos > Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-110">In the navigation pane, go to **Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="8dfbd-111">No campo **Tipo de ordem de trabalho**, selecione **Ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-111">In the **Work order type** field, select **Purchase orders**.</span></span>

## <a name="create-a-work-template-header"></a><span data-ttu-id="8dfbd-112">Criar um cabeçalho do modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="8dfbd-112">Create a work template header</span></span>
1. <span data-ttu-id="8dfbd-113">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-113">Select **New**.</span></span>
2. <span data-ttu-id="8dfbd-114">No campo **Número de sequência**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-114">In the **Sequence number** field, enter a number.</span></span> <span data-ttu-id="8dfbd-115">Esta é a sequência em que os modelos de trabalho são avaliados.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-115">This is the sequence in which the work templates are evaluated.</span></span> <span data-ttu-id="8dfbd-116">Você pode modificar a sequência, se necessário.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-116">You can modify the sequence, if needed.</span></span>  
3. <span data-ttu-id="8dfbd-117">No campo **Modelo de trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-117">In the **Work template** field, type a value.</span></span> <span data-ttu-id="8dfbd-118">Este é o identificador exclusivo desse modelo.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-118">This is the unique identifier for this template.</span></span>  
4. <span data-ttu-id="8dfbd-119">No campo **Descrição do modelo do trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-119">In the **Work template description** field, type a value.</span></span>
    - <span data-ttu-id="8dfbd-120">A opção **Válido** não será marcada até que você tenha concluído todas as informações exigidas pelo modelo e, depois, tenha selecionado **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-120">The **Valid** option will not be checked until you've completed all the information that's needed by the template and have then selected **Save**.</span></span>  
    - <span data-ttu-id="8dfbd-121">Uma ordem de trabalho do tipo **Ordem de compra** não pode ser processada automaticamente. Por isso, deixa a opção **Processar automaticamente** definida como **Não**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-121">A work order of type **Purchase order** cannot be automatically processed, so leave the **Automatically process** option set to **No**.</span></span>  
5. <span data-ttu-id="8dfbd-122">No campo **ID de grupo de trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-122">In the **Work pool ID** field, type a value.</span></span> <span data-ttu-id="8dfbd-123">As IDs de grupo de trabalho permitem organizar o trabalho em grupos.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-123">Work pool IDs allow you to organize work into groups.</span></span> <span data-ttu-id="8dfbd-124">O valor definido aqui será o valor padrão de qualquer trabalho criado usando esse modelo.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-124">The value that you set here will be the default value for any work that's created using this template.</span></span>  
6. <span data-ttu-id="8dfbd-125">No campo **Prioridade de trabalho**, insira `1`.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-125">In the **Work priority** field, enter `1`.</span></span> <span data-ttu-id="8dfbd-126">Isso indica a importância do trabalho, e o valor que você definiu aqui será o padrão de qualquer trabalho criado com esse modelo.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-126">This indicates the importance of the work, and the value that you set here will be the default for any work created using this template.</span></span>  
7. <span data-ttu-id="8dfbd-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-127">Select **Save**.</span></span> <span data-ttu-id="8dfbd-128">Você deve salvar o cabeçalho do modelo de trabalho antes que o botão **Editar consulta** fique disponível.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-128">You must save the work template header before the **Edit Query** button becomes available.</span></span>  

## <a name="set-up-the-query-for-the-work-template"></a><span data-ttu-id="8dfbd-129">Configurar a consulta do modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="8dfbd-129">Set up the query for the work template</span></span>
1. <span data-ttu-id="8dfbd-130">Selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-130">Select **Edit query**.</span></span> <span data-ttu-id="8dfbd-131">Definiremos uma limitação segundo a qual o modelo só pode ser usado em um depósito específico.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-131">We'll set a limitation that the template can only be used within a specific warehouse.</span></span>  
2. <span data-ttu-id="8dfbd-132">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-132">Select **Add**.</span></span>
3. <span data-ttu-id="8dfbd-133">No campo **Campo** da nova coluna, digite `warehouse`.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-133">In the **Field** field of the new row, type `warehouse`.</span></span>
4. <span data-ttu-id="8dfbd-134">No campo **Critérios**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-134">In the **Criteria** field, type a value.</span></span>
5. <span data-ttu-id="8dfbd-135">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-135">Select **OK**.</span></span>
6. <span data-ttu-id="8dfbd-136">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-136">Select **Yes**.</span></span>

## <a name="set-work-template-details"></a><span data-ttu-id="8dfbd-137">Definir detalhes do modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="8dfbd-137">Set work template details</span></span>
1. <span data-ttu-id="8dfbd-138">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-138">Select **New**.</span></span>
2. <span data-ttu-id="8dfbd-139">No campo **Tipo de trabalho**, selecione **Separar**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-139">In the **Work type** field, select **Pick**.</span></span>
3. <span data-ttu-id="8dfbd-140">No campo **ID de classe de trabalho**, digite `purchase`.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-140">In the **Work class ID** field, type `purchase`.</span></span> <span data-ttu-id="8dfbd-141">A classe de trabalho definida aqui será a padrão em todas as linhas de trabalho de tipo Separar criadas com esse modelo.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-141">The work class that you set here will be the default on all work lines of type Pick that are created using this template.</span></span> <span data-ttu-id="8dfbd-142">A classe de trabalho não pode ser substituída nas linhas da ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-142">The work class cannot be overridden from the work order lines.</span></span> <span data-ttu-id="8dfbd-143">Classes de trabalho são usadas para direcionar e/ou limitar os tipos de linhas da ordem de trabalho que um funcionário do depósito pode processar em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-143">Work classes are used to direct and/or limit the type of work order lines a warehouse worker can process on a mobile device.</span></span>  
4. <span data-ttu-id="8dfbd-144">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-144">Select **New**.</span></span>
5. <span data-ttu-id="8dfbd-145">No campo **Tipo de trabalho**, selecione **Colocar**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-145">In the **Work type** field, select **Put**.</span></span>
6. <span data-ttu-id="8dfbd-146">No campo **ID da classe de trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-146">In the **Work class ID** field, type a value.</span></span> <span data-ttu-id="8dfbd-147">As instruções de separação e armazenamento formam um conjunto.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-147">The pick and put instructions are a set.</span></span> <span data-ttu-id="8dfbd-148">Cada conjunto separar/armazenar deve ter a mesma classe de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-148">Each pick/put set must have the same work class.</span></span> <span data-ttu-id="8dfbd-149">Use a mesma classe de trabalho que você forneceu para a instrução de separação.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-149">Use the same work class that you provided for the pick instruction.</span></span>  
7. <span data-ttu-id="8dfbd-150">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-150">Select **Save**.</span></span> <span data-ttu-id="8dfbd-151">Note que agora a caixa de seleção **Válido** está marcada.</span><span class="sxs-lookup"><span data-stu-id="8dfbd-151">Note that the **Valid** checkbox is now checked.</span></span>  

