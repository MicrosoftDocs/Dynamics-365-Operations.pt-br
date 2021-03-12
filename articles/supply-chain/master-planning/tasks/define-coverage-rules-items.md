---
title: Definir regras de cobertura para itens
description: A empresa de dados demo usada para criar este procedimento é USMF.
author: ShylaThompson
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c156ae4a8a19a428378581a0d5c7dc01d86b5ec7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999872"
---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="c1c52-103">Definir regras de cobertura para itens</span><span class="sxs-lookup"><span data-stu-id="c1c52-103">Define coverage rules for items</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c1c52-104">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="c1c52-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c1c52-105">Este procedimento mostra como criar regras de cobertura e substituir configurações de cobertura para um item específico.</span><span class="sxs-lookup"><span data-stu-id="c1c52-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="c1c52-106">Também mostra como especificar as configurações padrão de estoque.</span><span class="sxs-lookup"><span data-stu-id="c1c52-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="c1c52-107">Crie um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="c1c52-107">Create a coverage group</span></span>
1. <span data-ttu-id="c1c52-108">Vá para **Painel de navegação > Módulos > Planejamento mestre > Configuração > Grupos de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-108">Go to **Navigation pane > Modules > Master planning > Setup > Coverage groups**.</span></span>
2. <span data-ttu-id="c1c52-109">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-109">Click **New**.</span></span>
3. <span data-ttu-id="c1c52-110">No campo **Grupo de cobertura**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c1c52-110">In the **Coverage group** field, type a value.</span></span>
4. <span data-ttu-id="c1c52-111">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c1c52-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="c1c52-112">No campo **Calendário**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c1c52-112">In the **Calendar** field, type a value.</span></span> <span data-ttu-id="c1c52-113">Escolha o calendário utilizado pelo planejamento mestre para criar indicações de reabastecimento para itens desse grupo.</span><span class="sxs-lookup"><span data-stu-id="c1c52-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="c1c52-114">No campo **Código de cobertura**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="c1c52-114">In the **Coverage code** field, select an option.</span></span> <span data-ttu-id="c1c52-115">Selecione 'Requisito' para este procedimento.</span><span class="sxs-lookup"><span data-stu-id="c1c52-115">Select 'Requirement' for this procedure.</span></span>  
7. <span data-ttu-id="c1c52-116">No campo **Limite de tempo de cobertura (dias)**, insira '90'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-116">In the **Coverage time fence (days) field**, enter '90'.</span></span> <span data-ttu-id="c1c52-117">Para itens desse grupo, o planejamento mestre criará indicações de reabastecimento por até 90 dias no futuro.</span><span class="sxs-lookup"><span data-stu-id="c1c52-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="c1c52-118">No campo **Dias negativos**, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-118">In the **Negative days** field, enter '1'.</span></span>
9. <span data-ttu-id="c1c52-119">No campo **Dias positivos**, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-119">In the **Positive days** field, enter '1'.</span></span>
10. <span data-ttu-id="c1c52-120">Expanda ou recolha a seção **Outros**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-120">Expand or collapse the **Other** section.</span></span>
11. <span data-ttu-id="c1c52-121">Na seção **Margens de segurança em dias**, no campo **Margem de recebimento adicionada à data de requisição**, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-121">Under the **Safety margins in days** section, in the **Receipt margin added to requirement date** field, enter '1'.</span></span> <span data-ttu-id="c1c52-122">Por exemplo, se a margem de recebimento estiver definida para 1 dia, e uma linha da ordem de compra estiver programada para recebimento em 15 de maio, o planejamento mestre calculará a data de recebimento ajustada como 16 de maio.</span><span class="sxs-lookup"><span data-stu-id="c1c52-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="c1c52-123">No campo **Margem de emissão deduzida da data de requisição**, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-123">In the **Issue margin deducted from requirement date** field, enter '1'.</span></span> <span data-ttu-id="c1c52-124">Por exemplo, se a margem de segurança estiver definida como 1 dia, e uma linha da ordem de venda estiver programada para entrega em 15 de maio, o agendamento do planejamento mestre calculará a data de entrega ajustada como 14 de maio.</span><span class="sxs-lookup"><span data-stu-id="c1c52-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="c1c52-125">No campo **Reordenar margem adicionada ao prazo de entrega do item**, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-125">In the **Reorder margin added to item lead time** field, enter '1'.</span></span>
14. <span data-ttu-id="c1c52-126">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-126">Click **Save**.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="c1c52-127">Criar um novo produto</span><span class="sxs-lookup"><span data-stu-id="c1c52-127">Create a new product</span></span>
1. <span data-ttu-id="c1c52-128">Vá para **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-128">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="c1c52-129">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-129">Click **New**.</span></span>
3. <span data-ttu-id="c1c52-130">No campo **Número do produto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c1c52-130">In the **Product number** field, type a value.</span></span>
4. <span data-ttu-id="c1c52-131">No campo **Nome do produto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c1c52-131">In the **Product name** field, type a value.</span></span>
5. <span data-ttu-id="c1c52-132">No campo **Grupo de modelos de item**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c1c52-132">In the **Item model group** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="c1c52-133">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c1c52-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="c1c52-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c1c52-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="c1c52-135">No campo **Grupo de itens**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c1c52-135">In the **Item group** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="c1c52-136">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c1c52-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="c1c52-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c1c52-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="c1c52-138">No campo **Grupo de dimensões de armazenamento**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c1c52-138">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="c1c52-139">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="c1c52-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="c1c52-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c1c52-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="c1c52-141">No campo **Grupo de dimensões de rastreamento**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c1c52-141">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="c1c52-142">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="c1c52-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="c1c52-143">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c1c52-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="c1c52-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-144">Click **OK**.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="c1c52-145">Configurar ordem padrão</span><span class="sxs-lookup"><span data-stu-id="c1c52-145">Setup default order settings</span></span>
1. <span data-ttu-id="c1c52-146">No **Painel de Ação**, clique em **Plano**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-146">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="c1c52-147">Em **Configurações da ordem**, clique em **Configurações Padrão da Ordem**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-147">Under **Order settings**, click **Default order settings**.</span></span>
3. <span data-ttu-id="c1c52-148">Em **Ordem de compra**, no campo **Site padrão**, digite o site usado como padrão quando ordens de compra são criadas.</span><span class="sxs-lookup"><span data-stu-id="c1c52-148">Under **Purchase order**, in the **Default site** field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="c1c52-149">No campo **Depósito padrão**, digite o local onde o item está armazenado.</span><span class="sxs-lookup"><span data-stu-id="c1c52-149">In the **Default warehouse** field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="c1c52-150">Expanda ou recolha a seção **Estoque**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-150">Expand or collapse the **Inventory** section.</span></span>
6. <span data-ttu-id="c1c52-151">No campo **Múltiplo**, digite '10'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-151">In the **Multiple** field, type '10'.</span></span>
7. <span data-ttu-id="c1c52-152">No campo **Quantidade mínima para ordem**, digite '10'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-152">In the **Min. order quantity** field, type '10'.</span></span>
8. <span data-ttu-id="c1c52-153">No campo **Quantidade máxima para ordem**, digite '100'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-153">In the **Max. order quantity** field, type '100'.</span></span>
9. <span data-ttu-id="c1c52-154">No campo **Quantidade da ordem padrão**, digite '10'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-154">In the **Standard order quantity**, type '10'.</span></span>
10. <span data-ttu-id="c1c52-155">No campo **Prazo de entrega da compra**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c1c52-155">In the **Purchase lead time** field, enter a number.</span></span>
11. <span data-ttu-id="c1c52-156">Marque ou desmarque a caixa de seleção **Dias úteis**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-156">Select or clear the **Working days** check box.</span></span>
12. <span data-ttu-id="c1c52-157">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-157">Click **Save**.</span></span>
13. <span data-ttu-id="c1c52-158">No campo **Tipo de ordem padrão**, selecione 'Ordem de compra'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-158">In the **Default order type** field select 'Purchase order'.</span></span>
14. <span data-ttu-id="c1c52-159">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-159">Click **Save**.</span></span>
15. <span data-ttu-id="c1c52-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c1c52-160">Close the page.</span></span> <span data-ttu-id="c1c52-161">Feche a página Configurações padrão da ordem.</span><span class="sxs-lookup"><span data-stu-id="c1c52-161">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="c1c52-162">Adicionar um item ao grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="c1c52-162">Add an item to a coverage group</span></span>
1. <span data-ttu-id="c1c52-163">Expanda ou recolha a seção **Plano**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-163">Expand or collapse the **Plan** section.</span></span>
2. <span data-ttu-id="c1c52-164">No campo **Grupo de cobertura**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c1c52-164">In the **Coverage group** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="c1c52-165">Na lista, localize o **Grupo de cobertura** que você criou.</span><span class="sxs-lookup"><span data-stu-id="c1c52-165">In the list, find the **Coverage group** you have created.</span></span>
4. <span data-ttu-id="c1c52-166">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c1c52-166">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="c1c52-167">Criar Regras de cobertura de item</span><span class="sxs-lookup"><span data-stu-id="c1c52-167">Create item coverage rules</span></span>
1. <span data-ttu-id="c1c52-168">No **Painel de Ação**, clique em **Plano**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-168">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="c1c52-169">Em **Cobertura**, clique em **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-169">Under **Coverage**, click **Item coverage**.</span></span>
3. <span data-ttu-id="c1c52-170">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-170">Click **New**.</span></span>
4. <span data-ttu-id="c1c52-171">Clique na guia **Geral**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-171">Click the **General** tab.</span></span>
5. <span data-ttu-id="c1c52-172">Marque a caixa no cabeçalho de **Substituir configurações do grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-172">Check the box on the header of **Override coverage group** settings.</span></span>
6. <span data-ttu-id="c1c52-173">No campo **Limite de tempo de cobertura (dias)**, insira '60'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-173">In the **Coverage time fence (days)** field, enter '60'.</span></span> <span data-ttu-id="c1c52-174">Embora os itens no grupo de cobertura Requiremen sejam planejados 90 dias depois, esse item será planejado com 60 dias.</span><span class="sxs-lookup"><span data-stu-id="c1c52-174">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="c1c52-175">No campo **Dias negativos**, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-175">In the **Negative days** field, enter '2'.</span></span>
8. <span data-ttu-id="c1c52-176">No campo **Dias positivos**, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-176">In the **Positive days** field, enter '2'.</span></span>
9. <span data-ttu-id="c1c52-177">Clique na guia **Prazo de entrega**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-177">Click the **Lead time** tab.</span></span>
10. <span data-ttu-id="c1c52-178">Marque a caixa no cabeçalho de **Compra**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-178">Check the box on the header of **Purchase**.</span></span>
11. <span data-ttu-id="c1c52-179">No campo **Tempo de compra**, insira '5'.</span><span class="sxs-lookup"><span data-stu-id="c1c52-179">In the **Purchase time** field, enter '5'.</span></span>
12. <span data-ttu-id="c1c52-180">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c1c52-180">Click **Save**.</span></span>

