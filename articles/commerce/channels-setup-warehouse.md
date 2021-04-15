---
title: Configurar um depósito
description: Este tópico descreve como configurar um depósito a ser usado com um novo canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 154ec719e16e4826b0e24deb5ecadf587d938e3c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800486"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="ae5c6-103">Configuração do depósito</span><span class="sxs-lookup"><span data-stu-id="ae5c6-103">Warehouse set up</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ae5c6-104">Este tópico descreve como configurar um depósito a ser usado com um novo canal no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ae5c6-105">Cada canal do Commerce requer que um depósito configurado seja associado a ele.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-105">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="ae5c6-106">Os procedimentos a seguir fornecem a configuração mínima necessária para um depósito de um canal do Commerce.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-106">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="ae5c6-107">Para obter mais informações sobre configuração de depósitos, consulte a [Visão geral de gerenciamento de depósito](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="ae5c6-107">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="ae5c6-108">Configurar um site de depósito</span><span class="sxs-lookup"><span data-stu-id="ae5c6-108">Configure a warehouse site</span></span>

<span data-ttu-id="ae5c6-109">Antes de configurar um depósito, você precisa configurar um site de depósito.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-109">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="ae5c6-110">Para configurar um site de depósito, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-110">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="ae5c6-111">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Sites**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="ae5c6-112">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="ae5c6-113">No campo **Site**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-113">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="ae5c6-114">No campo **Nome**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="ae5c6-115">Na seção **Geral**, defina o **Fuso horário** apropriado.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-115">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="ae5c6-116">Na seção **Endereços**, insira um endereço.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-116">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="ae5c6-117">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-117">On the action pane, select **Save**.</span></span>

<span data-ttu-id="ae5c6-118">A imagem a seguir mostra um exemplo de site de depósito.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-118">The following image shows an example warehouse site.</span></span>

![Exemplo de site de depósito](media/warehouse-site.png)

## <a name="set-up-a-warehouse&quot;></a><span data-ttu-id=&quot;ae5c6-120&quot;>Configurar um depósito</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-120&quot;>Set up a warehouse</span></span>

<span data-ttu-id=&quot;ae5c6-121&quot;>Para configurar um depósito, siga estas etapas.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-121&quot;>To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id=&quot;ae5c6-122&quot;>No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Depósitos**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-122&quot;>In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id=&quot;ae5c6-123&quot;>No painel de ação, selecione **Novo**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-123&quot;>On the action pane, select **New**.</span></span>
1. <span data-ttu-id=&quot;ae5c6-124&quot;>No campo **Depósito**, insira um valor.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-124&quot;>In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id=&quot;ae5c6-125&quot;>No caso de um mapeamento 1:1 para uma loja, use o nome da loja ou o nome de um centro de distribuição regional.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-125&quot;>If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id=&quot;ae5c6-126&quot;>No campo **Nome**, insira um valor.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-126&quot;>In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id=&quot;ae5c6-127&quot;>Na lista suspensa **Site**, selecione o site de depósito criado anteriormente.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-127&quot;>In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id=&quot;ae5c6-128&quot;>No campo **Tipo**, selecione **Padrão**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-128&quot;>In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id=&quot;ae5c6-129&quot;>Se você quiser definir um **Depósito de quarentena**, primeiro, precisará seguir estas etapas para criar um depósito adicional no qual o **Tipo** seja definido como **Quarentena**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-129&quot;>If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id=&quot;ae5c6-130&quot;>Se você quiser definir um **Depósito de trânsito**, primeiro, precisará seguir estas etapas para criar um depósito adicional no qual o **Tipo** seja definido como **Trânsito**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-130&quot;>If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id=&quot;ae5c6-131&quot;>No painel de ação, selecione **Salvar**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-131&quot;>On the action pane, select **Save**.</span></span>

## <a name=&quot;set-up-inventory-aisles&quot;></a><span data-ttu-id=&quot;ae5c6-132&quot;>Configurar corredores do estoque</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-132&quot;>Set up inventory aisles</span></span>

<span data-ttu-id=&quot;ae5c6-133&quot;>Para configurar corredores de estoque, siga estas etapas.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-133&quot;>To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id=&quot;ae5c6-134&quot;>No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Configuração de localização \> Corredores de estoque**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-134&quot;>In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id=&quot;ae5c6-135&quot;>No painel de ação, selecione **Novo**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-135&quot;>On the action pane, select **New**.</span></span>
1. <span data-ttu-id=&quot;ae5c6-136&quot;>Na lista suspensa **Depósito**, selecione o depósito criado anteriormente.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ae5c6-136&quot;>In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id=&quot;ae5c6-137&quot;>No campo **Corredor**, insira um nome (por exemplo, &quot;Padr").</span><span class="sxs-lookup"><span data-stu-id="ae5c6-137">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="ae5c6-138">No campo **Nome**, insira um nome (por exemplo, "Corredor padrão").</span><span class="sxs-lookup"><span data-stu-id="ae5c6-138">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="ae5c6-139">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-139">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="ae5c6-140">Configurar localizações de estoque no depósito</span><span class="sxs-lookup"><span data-stu-id="ae5c6-140">Set up warehouse inventory locations</span></span>

<span data-ttu-id="ae5c6-141">Para configurar localizações de estoque no depósito para estoque padrão, danificado e devolvido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-141">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="ae5c6-142">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-142">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="ae5c6-143">Selecione o estoque criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-143">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="ae5c6-144">No painel de ação, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-144">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="ae5c6-145">No painel de ação, selecione **Depósito** e, depois, **Localização de estoque**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-145">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="ae5c6-146">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-146">On the action pane, select **New**.</span></span> <span data-ttu-id="ae5c6-147">A lista suspensa **Depósito** deve usar como padrão o novo depósito.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-147">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="ae5c6-148">Na caixa **Corredor**, insira o nome do corredor especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-148">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="ae5c6-149">Defina **Atualização manual** como **Sim**</span><span class="sxs-lookup"><span data-stu-id="ae5c6-149">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="ae5c6-150">Na caixa **Localização**, insira o nome do depósito.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-150">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="ae5c6-151">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-151">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="ae5c6-152">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-152">On the action pane, select **New**.</span></span>  <span data-ttu-id="ae5c6-153">A lista suspensa **Depósito** deve usar como padrão o novo depósito.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-153">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="ae5c6-154">Na caixa **Corredor**, insira o nome do corredor especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-154">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="ae5c6-155">Defina **Atualização manual** como **Sim**</span><span class="sxs-lookup"><span data-stu-id="ae5c6-155">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="ae5c6-156">Na caixa **Localização**, digite "Danificado".</span><span class="sxs-lookup"><span data-stu-id="ae5c6-156">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="ae5c6-157">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-157">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="ae5c6-158">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-158">On the action pane, select **New**.</span></span>  <span data-ttu-id="ae5c6-159">A lista suspensa **Depósito** deve usar como padrão o novo depósito.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-159">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="ae5c6-160">Na caixa **Corredor**, insira o nome do corredor especificado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-160">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="ae5c6-161">Defina **Atualização manual** como **Sim**</span><span class="sxs-lookup"><span data-stu-id="ae5c6-161">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="ae5c6-162">Na caixa **Localização**, digite "Devoluções".</span><span class="sxs-lookup"><span data-stu-id="ae5c6-162">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="ae5c6-163">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-163">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="ae5c6-164">A imagem a seguir mostra uma configuração de localização de estoque no depósito de São Francisco.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-164">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Exemplo de configuração de localização no estoque](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="ae5c6-166">Concluir a configuração de depósito</span><span class="sxs-lookup"><span data-stu-id="ae5c6-166">Complete warehouse setup</span></span>

<span data-ttu-id="ae5c6-167">Para concluir a configuração do depósito, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-167">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="ae5c6-168">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Configuração de canal \> Depósitos**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-168">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="ae5c6-169">Selecione o estoque criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-169">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="ae5c6-170">No painel de ação, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-170">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="ae5c6-171">Em **Gerenciamento de estoque e depósito**:</span><span class="sxs-lookup"><span data-stu-id="ae5c6-171">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="ae5c6-172">Defina **Local de recebimento padrão** como o local padrão criado acima.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-172">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="ae5c6-173">Selecione **Local de saída padrão** como o local padrão criado acima.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-173">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="ae5c6-174">Na seção **Endereços**, insira o endereço de um depósito.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-174">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="ae5c6-175">Na seção **Varejo**:</span><span class="sxs-lookup"><span data-stu-id="ae5c6-175">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="ae5c6-176">Na caixa **Localização de devolução padrão**, insira a localização de devoluções criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-176">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="ae5c6-177">Defina **Loja** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-177">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="ae5c6-178">Defina **Peso** como **1,00**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-178">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="ae5c6-179">Na caixa **Dimensões de Armazenamento**, insira a localização padrão criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-179">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="ae5c6-180">Na seção **Depósito**, defina **Estoque físico negativo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-180">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="ae5c6-181">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-181">On the action pane, select **Save**.</span></span>

<span data-ttu-id="ae5c6-182">A imagem a seguir mostra detalhes de um depósito configurado.</span><span class="sxs-lookup"><span data-stu-id="ae5c6-182">The following image shows details for a configured warehouse.</span></span>

![Exemplo de depósito configurado](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="ae5c6-184">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ae5c6-184">Additional resources</span></span>

[<span data-ttu-id="ae5c6-185">Visão geral de gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="ae5c6-185">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="ae5c6-186">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="ae5c6-186">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="ae5c6-187">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="ae5c6-187">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="ae5c6-188">Configurar um canal de varejo</span><span class="sxs-lookup"><span data-stu-id="ae5c6-188">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="ae5c6-189">Configurar um canal online</span><span class="sxs-lookup"><span data-stu-id="ae5c6-189">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="ae5c6-190">Configurar um canal de call center</span><span class="sxs-lookup"><span data-stu-id="ae5c6-190">Set up a call center channel</span></span>](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
