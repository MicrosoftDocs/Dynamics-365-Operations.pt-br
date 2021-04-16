---
title: Configurar autoatendimento para funcionários
description: No Microsoft Dynamics 365 Human Resources, você pode configurar blocos para navegação de alto nível no autoatendimento para funcionários.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3e763a09e0a0f13eb7222a6ffbcb31b6230b83f4
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797926"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="4c4f6-103">Configurar autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="4c4f6-103">Configure employee self service</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4c4f6-104">No Microsoft Dynamics 365 Human Resources, você pode configurar blocos para navegação de alto nível no autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="4c4f6-105">Os blocos do plano de benefícios direcionam os usuários a planos de benefícios para os quais eles são qualificados.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-105">Benefit plan tiles direct users to benefit plans that they're eligible for.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="4c4f6-106">Configurar um bloco de planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="4c4f6-106">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="4c4f6-107">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="4c4f6-108">Selecione a guia **Configuração do bloco de planos de benefícios** e depois **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-108">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="4c4f6-109">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4c4f6-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="4c4f6-110">Campo</span><span class="sxs-lookup"><span data-stu-id="4c4f6-110">Field</span></span> | <span data-ttu-id="4c4f6-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c4f6-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="4c4f6-112">**ID do bloco**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-112">**Tile ID**</span></span> | <span data-ttu-id="4c4f6-113">O identificador exclusivo para o bloco.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="4c4f6-114">**Texto de rótulo de bloco**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-114">**Tile label text**</span></span> | <span data-ttu-id="4c4f6-115">O texto que aparecerá para o bloco no autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="4c4f6-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-116">**Description**</span></span> | <span data-ttu-id="4c4f6-117">Uma descrição do bloco.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-117">A description of the tile.</span></span> |
   | <span data-ttu-id="4c4f6-118">**Endereço na Internet**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-118">**Internet address**</span></span> | <span data-ttu-id="4c4f6-119">Digite a URL para a página de autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="4c4f6-120">**Tamanho do arquivo**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-120">**Tile size**</span></span> | <span data-ttu-id="4c4f6-121">O tamanho do bloco: pequeno, médio ou grande.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="4c4f6-122">**Alvo**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-122">**Target**</span></span> | <span data-ttu-id="4c4f6-123">Especifica se a página deve abrir em uma nova janela ou na janela atual.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="4c4f6-124">**Imagem de plano de fundo de bloco**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-124">**Tile background image**</span></span> | <span data-ttu-id="4c4f6-125">A URL da imagem a ser usada para o bloco (opcional).</span><span class="sxs-lookup"><span data-stu-id="4c4f6-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="4c4f6-126">**Início**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-126">**Start**</span></span> | <span data-ttu-id="4c4f6-127">A data e hora de início do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="4c4f6-128">**End**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-128">**End**</span></span> | <span data-ttu-id="4c4f6-129">A data e hora de término do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="4c4f6-130">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-130">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="4c4f6-131">Configurar um bloco de plano de crédito flexível</span><span class="sxs-lookup"><span data-stu-id="4c4f6-131">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="4c4f6-132">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração** , selecione **Parâmetros de autoatendimento para funcionários**.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="4c4f6-133">Selecione a guia **Configuração do bloco de plano de crédito flexível** e depois **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-133">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="4c4f6-134">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4c4f6-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="4c4f6-135">Campo</span><span class="sxs-lookup"><span data-stu-id="4c4f6-135">Field</span></span> | <span data-ttu-id="4c4f6-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c4f6-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="4c4f6-137">**ID do bloco**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-137">**Tile ID**</span></span> | <span data-ttu-id="4c4f6-138">O identificador exclusivo para o bloco.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="4c4f6-139">**Texto de rótulo de bloco**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-139">**Tile label text**</span></span> | <span data-ttu-id="4c4f6-140">O texto que aparecerá para o bloco no autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-140">The text that will appear for the tile on Self service.</span></span> |
   | <span data-ttu-id="4c4f6-141">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-141">**Description**</span></span> | <span data-ttu-id="4c4f6-142">Uma descrição do bloco.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-142">A description of the tile.</span></span> |
   | <span data-ttu-id="4c4f6-143">**Endereço na Internet**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-143">**Internet address**</span></span> | <span data-ttu-id="4c4f6-144">Digite a URL para a página de autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="4c4f6-145">**Tamanho do arquivo**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-145">**Tile size**</span></span> | <span data-ttu-id="4c4f6-146">O tamanho do bloco: pequeno, médio ou grande.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="4c4f6-147">**Alvo**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-147">**Target**</span></span> | <span data-ttu-id="4c4f6-148">Especifica se a página deve abrir em uma nova janela ou na janela atual.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="4c4f6-149">**Imagem de plano de fundo de bloco**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-149">**Tile background image**</span></span> | <span data-ttu-id="4c4f6-150">A URL da imagem a ser usada para o bloco (opcional).</span><span class="sxs-lookup"><span data-stu-id="4c4f6-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="4c4f6-151">**Início**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-151">**Start**</span></span> | <span data-ttu-id="4c4f6-152">A data e hora de início do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="4c4f6-153">**End**</span><span class="sxs-lookup"><span data-stu-id="4c4f6-153">**End**</span></span> | <span data-ttu-id="4c4f6-154">A data e hora de término do bloco devem estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="4c4f6-155">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4c4f6-155">Select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]