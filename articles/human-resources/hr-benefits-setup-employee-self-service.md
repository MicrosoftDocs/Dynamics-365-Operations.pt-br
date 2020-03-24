---
title: Configurar autoatendimento para funcionários
description: No Microsoft Dynamics 365 Human Resources, você pode configurar blocos para navegação de alto nível no autoatendimento para funcionários.
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
ms.openlocfilehash: 17918fc7b894929c92c54b59b7440ab8aef980bd
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092651"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="90084-103">Configurar autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="90084-103">Configure employee self service</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="90084-104">No Microsoft Dynamics 365 Human Resources, você pode configurar blocos para navegação de alto nível no autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="90084-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="90084-105">Os blocos do plano de benefícios direcionam os usuários a planos de benefícios nos quais eles estão qualificados para inscrição.</span><span class="sxs-lookup"><span data-stu-id="90084-105">Benefit plan tiles direct users to benefit plans that they are eligible to enroll in.</span></span>

## <a name="set-up-a-role-center-tile"></a><span data-ttu-id="90084-106">Configurar um bloco central de funções</span><span class="sxs-lookup"><span data-stu-id="90084-106">Set up a role center tile</span></span>

1. <span data-ttu-id="90084-107">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="90084-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="90084-108">Selecione a guia **Configuração do bloco central de funções** e depois **Novo**.</span><span class="sxs-lookup"><span data-stu-id="90084-108">Select the **Role center tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="90084-109">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="90084-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="90084-110">Campo</span><span class="sxs-lookup"><span data-stu-id="90084-110">Field</span></span> | <span data-ttu-id="90084-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="90084-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="90084-112">ID do bloco</span><span class="sxs-lookup"><span data-stu-id="90084-112">Tile ID</span></span> | <span data-ttu-id="90084-113">O identificador exclusivo para o bloco.</span><span class="sxs-lookup"><span data-stu-id="90084-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="90084-114">Texto de rótulo de bloco</span><span class="sxs-lookup"><span data-stu-id="90084-114">Tile label text</span></span> | <span data-ttu-id="90084-115">O texto que aparecerá para o bloco no autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="90084-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="90084-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="90084-116">Description</span></span> | <span data-ttu-id="90084-117">Uma descrição do bloco.</span><span class="sxs-lookup"><span data-stu-id="90084-117">A description of the tile.</span></span> |
   | <span data-ttu-id="90084-118">Endereço na Internet</span><span class="sxs-lookup"><span data-stu-id="90084-118">Internet address</span></span> | <span data-ttu-id="90084-119">Digite a URL para a página de autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="90084-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="90084-120">Tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="90084-120">Tile size</span></span> | <span data-ttu-id="90084-121">O tamanho do bloco: pequeno, médio ou grande.</span><span class="sxs-lookup"><span data-stu-id="90084-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="90084-122">Alvo</span><span class="sxs-lookup"><span data-stu-id="90084-122">Target</span></span> | <span data-ttu-id="90084-123">Especifica se a página deve abrir em uma nova janela ou na janela atual.</span><span class="sxs-lookup"><span data-stu-id="90084-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="90084-124">Imagem de plano de fundo de bloco</span><span class="sxs-lookup"><span data-stu-id="90084-124">Tile background image</span></span> | <span data-ttu-id="90084-125">A URL da imagem a ser usada para o bloco (opcional).</span><span class="sxs-lookup"><span data-stu-id="90084-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="90084-126">Início</span><span class="sxs-lookup"><span data-stu-id="90084-126">Start</span></span> | <span data-ttu-id="90084-127">A data e hora de início do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="90084-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="90084-128">End</span><span class="sxs-lookup"><span data-stu-id="90084-128">End</span></span> | <span data-ttu-id="90084-129">A data e hora de término do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="90084-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="90084-130">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="90084-130">Select **Save**.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="90084-131">Configurar um bloco de planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="90084-131">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="90084-132">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="90084-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="90084-133">Selecione a guia **Configuração do bloco de planos de benefícios** e depois **Novo**.</span><span class="sxs-lookup"><span data-stu-id="90084-133">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="90084-134">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="90084-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="90084-135">Campo</span><span class="sxs-lookup"><span data-stu-id="90084-135">Field</span></span> | <span data-ttu-id="90084-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="90084-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="90084-137">ID do bloco</span><span class="sxs-lookup"><span data-stu-id="90084-137">Tile ID</span></span> | <span data-ttu-id="90084-138">O identificador exclusivo para o bloco.</span><span class="sxs-lookup"><span data-stu-id="90084-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="90084-139">Texto de rótulo de bloco</span><span class="sxs-lookup"><span data-stu-id="90084-139">Tile label text</span></span> | <span data-ttu-id="90084-140">O texto que aparecerá para o bloco no autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="90084-140">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="90084-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="90084-141">Description</span></span> | <span data-ttu-id="90084-142">Uma descrição do bloco.</span><span class="sxs-lookup"><span data-stu-id="90084-142">A description of the tile.</span></span> |
   | <span data-ttu-id="90084-143">Endereço na Internet</span><span class="sxs-lookup"><span data-stu-id="90084-143">Internet address</span></span> | <span data-ttu-id="90084-144">Digite a URL para a página de autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="90084-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="90084-145">Tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="90084-145">Tile size</span></span> | <span data-ttu-id="90084-146">O tamanho do bloco: pequeno, médio ou grande.</span><span class="sxs-lookup"><span data-stu-id="90084-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="90084-147">Alvo</span><span class="sxs-lookup"><span data-stu-id="90084-147">Target</span></span> | <span data-ttu-id="90084-148">Especifica se a página deve abrir em uma nova janela ou na janela atual.</span><span class="sxs-lookup"><span data-stu-id="90084-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="90084-149">Imagem de plano de fundo de bloco</span><span class="sxs-lookup"><span data-stu-id="90084-149">Tile background image</span></span> | <span data-ttu-id="90084-150">A URL da imagem a ser usada para o bloco (opcional).</span><span class="sxs-lookup"><span data-stu-id="90084-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="90084-151">Início</span><span class="sxs-lookup"><span data-stu-id="90084-151">Start</span></span> | <span data-ttu-id="90084-152">A data e hora de início do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="90084-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="90084-153">End</span><span class="sxs-lookup"><span data-stu-id="90084-153">End</span></span> | <span data-ttu-id="90084-154">A data e hora de término do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="90084-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="90084-155">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="90084-155">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="90084-156">Configurar um bloco de plano de crédito flexível</span><span class="sxs-lookup"><span data-stu-id="90084-156">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="90084-157">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="90084-157">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="90084-158">Selecione a guia **Configuração do bloco de plano de crédito flexível** e depois **Novo**.</span><span class="sxs-lookup"><span data-stu-id="90084-158">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="90084-159">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="90084-159">Specify values for the following fields:</span></span>

   | <span data-ttu-id="90084-160">Campo</span><span class="sxs-lookup"><span data-stu-id="90084-160">Field</span></span> | <span data-ttu-id="90084-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="90084-161">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="90084-162">ID do bloco</span><span class="sxs-lookup"><span data-stu-id="90084-162">Tile ID</span></span> | <span data-ttu-id="90084-163">O identificador exclusivo para o bloco.</span><span class="sxs-lookup"><span data-stu-id="90084-163">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="90084-164">Texto de rótulo de bloco</span><span class="sxs-lookup"><span data-stu-id="90084-164">Tile label text</span></span> | <span data-ttu-id="90084-165">O texto que aparecerá para o bloco no autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="90084-165">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="90084-166">Descrição</span><span class="sxs-lookup"><span data-stu-id="90084-166">Description</span></span> | <span data-ttu-id="90084-167">Uma descrição do bloco.</span><span class="sxs-lookup"><span data-stu-id="90084-167">A description of the tile.</span></span> |
   | <span data-ttu-id="90084-168">Endereço na Internet</span><span class="sxs-lookup"><span data-stu-id="90084-168">Internet address</span></span> | <span data-ttu-id="90084-169">Digite a URL para a página de autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="90084-169">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="90084-170">Tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="90084-170">Tile size</span></span> | <span data-ttu-id="90084-171">O tamanho do bloco: pequeno, médio ou grande.</span><span class="sxs-lookup"><span data-stu-id="90084-171">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="90084-172">Alvo</span><span class="sxs-lookup"><span data-stu-id="90084-172">Target</span></span> | <span data-ttu-id="90084-173">Especifica se a página deve abrir em uma nova janela ou na janela atual.</span><span class="sxs-lookup"><span data-stu-id="90084-173">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="90084-174">Imagem de plano de fundo de bloco</span><span class="sxs-lookup"><span data-stu-id="90084-174">Tile background image</span></span> | <span data-ttu-id="90084-175">A URL da imagem a ser usada para o bloco (opcional).</span><span class="sxs-lookup"><span data-stu-id="90084-175">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="90084-176">Início</span><span class="sxs-lookup"><span data-stu-id="90084-176">Start</span></span> | <span data-ttu-id="90084-177">A data e hora de início do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="90084-177">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="90084-178">End</span><span class="sxs-lookup"><span data-stu-id="90084-178">End</span></span> | <span data-ttu-id="90084-179">A data e hora de término do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="90084-179">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="90084-180">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="90084-180">Select **Save**.</span></span>
