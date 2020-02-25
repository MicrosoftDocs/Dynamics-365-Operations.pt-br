---
title: Configurar um depósito
description: Este tópico descreve como configurar um depósito a ser usado com um novo canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: fe785e3bfd503193a588958ae5df0d1c0fdb9e52
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002303"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="f9a9a-103">Configuração do depósito</span><span class="sxs-lookup"><span data-stu-id="f9a9a-103">Warehouse set up</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f9a9a-104">Este tópico descreve como configurar um depósito a ser usado com um novo canal no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f9a9a-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="f9a9a-105">Overview</span></span>

<span data-ttu-id="f9a9a-106">Cada canal do Commerce requer que um depósito configurado seja associado a ele.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-106">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="f9a9a-107">Os procedimentos a seguir fornecem a configuração mínima necessária para um depósito de um canal do Commerce.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-107">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="f9a9a-108">Para obter mais informações sobre configuração de depósitos, consulte a [Visão geral de gerenciamento de depósito](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview).</span><span class="sxs-lookup"><span data-stu-id="f9a9a-108">For more information regarding warehouse setup, please see the [Warehouse management overview](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="f9a9a-109">Configurar um site de depósito</span><span class="sxs-lookup"><span data-stu-id="f9a9a-109">Configure a warehouse site</span></span>

<span data-ttu-id="f9a9a-110">Antes de configurar um depósito, você precisa configurar um site de depósito.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-110">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="f9a9a-111">Para configurar um site de depósito, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-111">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="f9a9a-112">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-112">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="f9a9a-113">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f9a9a-114">No campo **Site**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-114">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="f9a9a-115">No campo **Nome**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-115">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="f9a9a-116">Na seção **Geral**, defina o **Fuso horário** apropriado.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-116">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="f9a9a-117">Na seção **Endereços**, insira um endereço.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-117">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="f9a9a-118">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f9a9a-119">A imagem a seguir mostra um exemplo de site de depósito.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-119">The following image shows an example warehouse site.</span></span>

![Exemplo de site de depósito](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="f9a9a-121">Configurar um depósito</span><span class="sxs-lookup"><span data-stu-id="f9a9a-121">Set up a warehouse</span></span>

<span data-ttu-id="f9a9a-122">Para configurar um depósito, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-122">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="f9a9a-123">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-123">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="f9a9a-124">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-124">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f9a9a-125">No campo **Depósito**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-125">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="f9a9a-126">No caso de um mapeamento 1:1 para uma loja de varejo, use o nome da loja ou o nome de um centro de distribuição regional.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-126">If this is a 1:1 mapping to a retail store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="f9a9a-127">No campo **Nome**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-127">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="f9a9a-128">Na lista suspensa **Site**, selecione o site de depósito criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-128">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="f9a9a-129">No campo **Tipo**, selecione **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-129">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="f9a9a-130">Se você quiser definir um **Depósito de quarentena**, primeiro, precisará seguir estas etapas para criar um depósito adicional no qual o **Tipo** seja definido como **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-130">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="f9a9a-131">Se você quiser definir um **Depósito de trânsito**, primeiro, precisará seguir estas etapas para criar um depósito adicional no qual o **Tipo** seja definido como **Trânsito**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-131">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="f9a9a-132">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-132">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="f9a9a-133">Configurar corredores do estoque</span><span class="sxs-lookup"><span data-stu-id="f9a9a-133">Set up inventory aisles</span></span>

<span data-ttu-id="f9a9a-134">Para configurar corredores de estoque, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-134">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="f9a9a-135">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Configuração de localização \> Corredores de estoque**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-135">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="f9a9a-136">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f9a9a-137">Na lista suspensa **Depósito**, selecione o depósito criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-137">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="f9a9a-138">No campo **Corredor**, insira um nome (por exemplo, "Padr").</span><span class="sxs-lookup"><span data-stu-id="f9a9a-138">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="f9a9a-139">No campo **Nome**, insira um nome (por exemplo, "Corredor padrão").</span><span class="sxs-lookup"><span data-stu-id="f9a9a-139">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="f9a9a-140">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-140">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="f9a9a-141">Configurar localizações de estoque no depósito</span><span class="sxs-lookup"><span data-stu-id="f9a9a-141">Set up warehouse inventory locations</span></span>

<span data-ttu-id="f9a9a-142">Para configurar localizações de estoque no depósito para estoque padrão, danificado e devolvido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-142">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="f9a9a-143">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-143">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="f9a9a-144">Selecione o estoque criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-144">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="f9a9a-145">No painel de ação, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-145">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="f9a9a-146">No painel de ação, selecione **Depósito** e, depois, **Localização de estoque**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-146">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="f9a9a-147">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-147">On the action pane, select **New**.</span></span> <span data-ttu-id="f9a9a-148">A lista suspensa **Depósito** deve usar como padrão o novo depósito.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-148">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="f9a9a-149">Na caixa **Corredor**, insira o nome do corredor especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-149">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="f9a9a-150">Defina **Atualização manual** como **Sim**</span><span class="sxs-lookup"><span data-stu-id="f9a9a-150">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="f9a9a-151">Na caixa **Localização**, insira o nome do depósito.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-151">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="f9a9a-152">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-152">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="f9a9a-153">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-153">On the action pane, select **New**.</span></span>  <span data-ttu-id="f9a9a-154">A lista suspensa **Depósito** deve usar como padrão o novo depósito.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-154">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="f9a9a-155">Na caixa **Corredor**, insira o nome do corredor especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-155">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="f9a9a-156">Defina **Atualização manual** como **Sim**</span><span class="sxs-lookup"><span data-stu-id="f9a9a-156">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="f9a9a-157">Na caixa **Localização**, digite "Danificado".</span><span class="sxs-lookup"><span data-stu-id="f9a9a-157">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="f9a9a-158">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-158">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="f9a9a-159">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-159">On the action pane, select **New**.</span></span>  <span data-ttu-id="f9a9a-160">A lista suspensa **Depósito** deve usar como padrão o novo depósito.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-160">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="f9a9a-161">Na caixa **Corredor**, insira o nome do corredor especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-161">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="f9a9a-162">Defina **Atualização manual** como **Sim**</span><span class="sxs-lookup"><span data-stu-id="f9a9a-162">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="f9a9a-163">Na caixa **Localização**, digite "Devoluções".</span><span class="sxs-lookup"><span data-stu-id="f9a9a-163">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="f9a9a-164">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-164">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="f9a9a-165">A imagem a seguir mostra uma configuração de localização de estoque no depósito de São Francisco.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-165">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Exemplo de configuração de localização no estoque](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="f9a9a-167">Concluir a configuração de depósito</span><span class="sxs-lookup"><span data-stu-id="f9a9a-167">Complete warehouse setup</span></span>

<span data-ttu-id="f9a9a-168">Para concluir a configuração do depósito, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-168">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="f9a9a-169">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-169">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="f9a9a-170">Selecione o estoque criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-170">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="f9a9a-171">No painel de ação, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-171">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="f9a9a-172">Em **Gerenciamento de estoque e depósito**:</span><span class="sxs-lookup"><span data-stu-id="f9a9a-172">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="f9a9a-173">Defina **Local de recebimento padrão** como o local padrão criado acima.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-173">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="f9a9a-174">Selecione **Local de saída padrão** como o local padrão criado acima.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-174">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="f9a9a-175">Na seção **Endereços**, insira o endereço de um depósito.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-175">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="f9a9a-176">Na seção **Varejo**:</span><span class="sxs-lookup"><span data-stu-id="f9a9a-176">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="f9a9a-177">Na caixa **Localização de devolução padrão**, insira a localização de devoluções criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-177">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="f9a9a-178">Defina **Loja** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-178">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="f9a9a-179">Defina **Peso** como **1,00**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-179">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="f9a9a-180">Na caixa **Dimensões de Armazenamento**, insira a localização padrão criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-180">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="f9a9a-181">Na seção **Depósito**, defina **Estoque físico negativo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-181">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="f9a9a-182">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-182">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f9a9a-183">A imagem a seguir mostra detalhes de um depósito configurado.</span><span class="sxs-lookup"><span data-stu-id="f9a9a-183">The following image shows details for a configured warehouse.</span></span>

![Exemplo de depósito configurado](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="f9a9a-185">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f9a9a-185">Additional resources</span></span>

[<span data-ttu-id="f9a9a-186">Visão geral de gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="f9a9a-186">Warehouse management overview</span></span>](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview)

[<span data-ttu-id="f9a9a-187">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="f9a9a-187">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="f9a9a-188">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="f9a9a-188">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="f9a9a-189">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="f9a9a-189">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="f9a9a-190">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="f9a9a-190">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="f9a9a-191">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="f9a9a-191">Set up a call center channel</span></span>](channel-setup-callcenter.md)





