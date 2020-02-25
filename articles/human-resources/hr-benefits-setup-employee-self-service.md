---
title: Configurar autoatendimento para funcionários
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e44a35071b8d0987e6c949fb11312204317b44a1
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008101"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="5d231-102">Configurar autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="5d231-102">Configure employee self service</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="5d231-103">No Microsoft Dynamics 365 Human Resources, você pode configurar blocos para navegação de alto nível no autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="5d231-103">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="5d231-104">Os blocos do plano de benefícios direcionam os usuários a planos de benefícios nos quais eles estão qualificados para inscrição.</span><span class="sxs-lookup"><span data-stu-id="5d231-104">Benefit plan tiles direct users to benefit plans that they are eligible to enroll in.</span></span>

## <a name="set-up-a-role-center-tile"></a><span data-ttu-id="5d231-105">Configurar um bloco central de funções</span><span class="sxs-lookup"><span data-stu-id="5d231-105">Set up a role center tile</span></span>

1. <span data-ttu-id="5d231-106">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="5d231-106">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="5d231-107">Selecione a guia **Configuração do bloco central de funções** e depois **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5d231-107">Select the **Role center tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="5d231-108">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="5d231-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="5d231-109">Campo</span><span class="sxs-lookup"><span data-stu-id="5d231-109">Field</span></span> | <span data-ttu-id="5d231-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d231-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="5d231-111">ID do bloco</span><span class="sxs-lookup"><span data-stu-id="5d231-111">Tile ID</span></span> | <span data-ttu-id="5d231-112">O identificador exclusivo para o bloco.</span><span class="sxs-lookup"><span data-stu-id="5d231-112">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="5d231-113">Texto de rótulo de bloco</span><span class="sxs-lookup"><span data-stu-id="5d231-113">Tile label text</span></span> | <span data-ttu-id="5d231-114">O texto que aparecerá para o bloco no autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="5d231-114">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="5d231-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d231-115">Description</span></span> | <span data-ttu-id="5d231-116">Uma descrição do bloco.</span><span class="sxs-lookup"><span data-stu-id="5d231-116">A description of the tile.</span></span> |
   | <span data-ttu-id="5d231-117">Endereço na Internet</span><span class="sxs-lookup"><span data-stu-id="5d231-117">Internet address</span></span> | <span data-ttu-id="5d231-118">Digite a URL para a página de autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="5d231-118">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="5d231-119">Tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="5d231-119">Tile size</span></span> | <span data-ttu-id="5d231-120">O tamanho do bloco: pequeno, médio ou grande.</span><span class="sxs-lookup"><span data-stu-id="5d231-120">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="5d231-121">Alvo</span><span class="sxs-lookup"><span data-stu-id="5d231-121">Target</span></span> | <span data-ttu-id="5d231-122">Especifica se a página deve abrir em uma nova janela ou na janela atual.</span><span class="sxs-lookup"><span data-stu-id="5d231-122">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="5d231-123">Imagem de plano de fundo de bloco</span><span class="sxs-lookup"><span data-stu-id="5d231-123">Tile background image</span></span> | <span data-ttu-id="5d231-124">A URL da imagem a ser usada para o bloco (opcional).</span><span class="sxs-lookup"><span data-stu-id="5d231-124">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="5d231-125">Início</span><span class="sxs-lookup"><span data-stu-id="5d231-125">Start</span></span> | <span data-ttu-id="5d231-126">A data e hora de início do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5d231-126">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="5d231-127">End</span><span class="sxs-lookup"><span data-stu-id="5d231-127">End</span></span> | <span data-ttu-id="5d231-128">A data e hora de término do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5d231-128">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="5d231-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5d231-129">Select **Save**.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="5d231-130">Configurar um bloco de planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="5d231-130">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="5d231-131">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="5d231-131">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="5d231-132">Selecione a guia **Configuração do bloco de planos de benefícios** e depois **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5d231-132">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="5d231-133">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="5d231-133">Specify values for the following fields:</span></span>

   | <span data-ttu-id="5d231-134">Campo</span><span class="sxs-lookup"><span data-stu-id="5d231-134">Field</span></span> | <span data-ttu-id="5d231-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d231-135">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="5d231-136">ID do bloco</span><span class="sxs-lookup"><span data-stu-id="5d231-136">Tile ID</span></span> | <span data-ttu-id="5d231-137">O identificador exclusivo para o bloco.</span><span class="sxs-lookup"><span data-stu-id="5d231-137">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="5d231-138">Texto de rótulo de bloco</span><span class="sxs-lookup"><span data-stu-id="5d231-138">Tile label text</span></span> | <span data-ttu-id="5d231-139">O texto que aparecerá para o bloco no autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="5d231-139">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="5d231-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d231-140">Description</span></span> | <span data-ttu-id="5d231-141">Uma descrição do bloco.</span><span class="sxs-lookup"><span data-stu-id="5d231-141">A description of the tile.</span></span> |
   | <span data-ttu-id="5d231-142">Endereço na Internet</span><span class="sxs-lookup"><span data-stu-id="5d231-142">Internet address</span></span> | <span data-ttu-id="5d231-143">Digite a URL para a página de autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="5d231-143">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="5d231-144">Tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="5d231-144">Tile size</span></span> | <span data-ttu-id="5d231-145">O tamanho do bloco: pequeno, médio ou grande.</span><span class="sxs-lookup"><span data-stu-id="5d231-145">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="5d231-146">Alvo</span><span class="sxs-lookup"><span data-stu-id="5d231-146">Target</span></span> | <span data-ttu-id="5d231-147">Especifica se a página deve abrir em uma nova janela ou na janela atual.</span><span class="sxs-lookup"><span data-stu-id="5d231-147">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="5d231-148">Imagem de plano de fundo de bloco</span><span class="sxs-lookup"><span data-stu-id="5d231-148">Tile background image</span></span> | <span data-ttu-id="5d231-149">A URL da imagem a ser usada para o bloco (opcional).</span><span class="sxs-lookup"><span data-stu-id="5d231-149">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="5d231-150">Início</span><span class="sxs-lookup"><span data-stu-id="5d231-150">Start</span></span> | <span data-ttu-id="5d231-151">A data e hora de início do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5d231-151">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="5d231-152">End</span><span class="sxs-lookup"><span data-stu-id="5d231-152">End</span></span> | <span data-ttu-id="5d231-153">A data e hora de término do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5d231-153">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="5d231-154">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5d231-154">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="5d231-155">Configurar um bloco de plano de crédito flexível</span><span class="sxs-lookup"><span data-stu-id="5d231-155">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="5d231-156">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="5d231-156">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="5d231-157">Selecione a guia **Configuração do bloco de plano de crédito flexível** e depois **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5d231-157">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="5d231-158">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="5d231-158">Specify values for the following fields:</span></span>

   | <span data-ttu-id="5d231-159">Campo</span><span class="sxs-lookup"><span data-stu-id="5d231-159">Field</span></span> | <span data-ttu-id="5d231-160">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d231-160">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="5d231-161">ID do bloco</span><span class="sxs-lookup"><span data-stu-id="5d231-161">Tile ID</span></span> | <span data-ttu-id="5d231-162">O identificador exclusivo para o bloco.</span><span class="sxs-lookup"><span data-stu-id="5d231-162">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="5d231-163">Texto de rótulo de bloco</span><span class="sxs-lookup"><span data-stu-id="5d231-163">Tile label text</span></span> | <span data-ttu-id="5d231-164">O texto que aparecerá para o bloco no autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="5d231-164">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="5d231-165">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d231-165">Description</span></span> | <span data-ttu-id="5d231-166">Uma descrição do bloco.</span><span class="sxs-lookup"><span data-stu-id="5d231-166">A description of the tile.</span></span> |
   | <span data-ttu-id="5d231-167">Endereço na Internet</span><span class="sxs-lookup"><span data-stu-id="5d231-167">Internet address</span></span> | <span data-ttu-id="5d231-168">Digite a URL para a página de autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="5d231-168">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="5d231-169">Tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="5d231-169">Tile size</span></span> | <span data-ttu-id="5d231-170">O tamanho do bloco: pequeno, médio ou grande.</span><span class="sxs-lookup"><span data-stu-id="5d231-170">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="5d231-171">Alvo</span><span class="sxs-lookup"><span data-stu-id="5d231-171">Target</span></span> | <span data-ttu-id="5d231-172">Especifica se a página deve abrir em uma nova janela ou na janela atual.</span><span class="sxs-lookup"><span data-stu-id="5d231-172">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="5d231-173">Imagem de plano de fundo de bloco</span><span class="sxs-lookup"><span data-stu-id="5d231-173">Tile background image</span></span> | <span data-ttu-id="5d231-174">A URL da imagem a ser usada para o bloco (opcional).</span><span class="sxs-lookup"><span data-stu-id="5d231-174">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="5d231-175">Início</span><span class="sxs-lookup"><span data-stu-id="5d231-175">Start</span></span> | <span data-ttu-id="5d231-176">A data e hora de início do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5d231-176">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="5d231-177">End</span><span class="sxs-lookup"><span data-stu-id="5d231-177">End</span></span> | <span data-ttu-id="5d231-178">A data e hora de término do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5d231-178">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="5d231-179">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5d231-179">Select **Save**.</span></span>
