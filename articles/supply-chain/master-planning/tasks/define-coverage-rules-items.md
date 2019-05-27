---
title: Definir regras de cobertura para itens
description: A empresa de dados demo usada para criar este procedimento é USMF.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 02aa3b2b7924cdf6317225bfce23f182aa390b8c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565640"
---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="73c1b-103">Definir regras de cobertura para itens</span><span class="sxs-lookup"><span data-stu-id="73c1b-103">Define coverage rules for items</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="73c1b-104">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="73c1b-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="73c1b-105">Este procedimento mostra como criar regras de cobertura e substituir configurações de cobertura para um item específico.</span><span class="sxs-lookup"><span data-stu-id="73c1b-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="73c1b-106">Também mostra como especificar as configurações padrão de estoque.</span><span class="sxs-lookup"><span data-stu-id="73c1b-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="73c1b-107">Crie um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="73c1b-107">Create a coverage group</span></span>
1. <span data-ttu-id="73c1b-108">Ir para Grupos de cobertura.</span><span class="sxs-lookup"><span data-stu-id="73c1b-108">Go to Coverage groups.</span></span>
2. <span data-ttu-id="73c1b-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="73c1b-109">Click New.</span></span>
3. <span data-ttu-id="73c1b-110">No campo Grupo de cobertura, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="73c1b-110">In the Coverage group field, type a value.</span></span>
4. <span data-ttu-id="73c1b-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="73c1b-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="73c1b-112">No campo Calendário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="73c1b-112">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="73c1b-113">Escolha o calendário utilizado pelo planejamento mestre para criar indicações de reabastecimento para itens desse grupo.</span><span class="sxs-lookup"><span data-stu-id="73c1b-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="73c1b-114">No campo Código de cobertura, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="73c1b-114">In the Coverage code field, select an option.</span></span>
    * <span data-ttu-id="73c1b-115">Selecione Requisito para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="73c1b-115">Select Requirement for this procedure.</span></span>  
7. <span data-ttu-id="73c1b-116">No Tempo limite de cobertura (dias), insira '90'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-116">In the Coverage time fence (days) field, enter '90'.</span></span>
    * <span data-ttu-id="73c1b-117">Para itens desse grupo, o planejamento mestre criará indicações de reabastecimento por até 90 dias no futuro.</span><span class="sxs-lookup"><span data-stu-id="73c1b-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="73c1b-118">No campo Dias negativos, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-118">In the Negative days field, enter '1'.</span></span>
9. <span data-ttu-id="73c1b-119">No campo Dias positivos, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-119">In the Positive days field, enter '1'.</span></span>
10. <span data-ttu-id="73c1b-120">Expandir ou recolher a seção Outros.</span><span class="sxs-lookup"><span data-stu-id="73c1b-120">Expand or collapse the Other section.</span></span>
11. <span data-ttu-id="73c1b-121">No campo Margem de recebimento adicionada à data de requisição, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-121">In the Receipt margin added to requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="73c1b-122">Por exemplo, se a margem de recebimento estiver definida para 1 dia, e uma linha da ordem de compra estiver programada para recebimento em 15 de maio, o planejamento mestre calculará a data de recebimento ajustada como 16 de maio.</span><span class="sxs-lookup"><span data-stu-id="73c1b-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="73c1b-123">No campo Margem de emissão deduzida da data de requisição, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-123">In the Issue margin deducted from requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="73c1b-124">Por exemplo, se a margem de segurança estiver definida como 1 dia, e uma linha da ordem de venda estiver programada para entrega em 15 de maio, o agendamento do planejamento mestre calculará a data de entrega ajustada como 14 de maio.</span><span class="sxs-lookup"><span data-stu-id="73c1b-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="73c1b-125">No campo Reordenar margem adicionada ao prazo de entrega do item, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-125">In the Reorder margin added to item lead time field, enter '1'.</span></span>
14. <span data-ttu-id="73c1b-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="73c1b-126">Click Save.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="73c1b-127">Criar um novo produto</span><span class="sxs-lookup"><span data-stu-id="73c1b-127">Create a new product</span></span>
1. <span data-ttu-id="73c1b-128">Vá para Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="73c1b-128">Go to Released products.</span></span>
2. <span data-ttu-id="73c1b-129">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="73c1b-129">Click New.</span></span>
3. <span data-ttu-id="73c1b-130">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="73c1b-130">In the Product number field, type a value.</span></span>
4. <span data-ttu-id="73c1b-131">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="73c1b-131">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="73c1b-132">No campo Grupo de modelo do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="73c1b-132">In the Item model group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="73c1b-133">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="73c1b-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="73c1b-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="73c1b-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="73c1b-135">No campo Grupo de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="73c1b-135">In the Item group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="73c1b-136">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="73c1b-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="73c1b-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="73c1b-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="73c1b-138">No campo Grupo de dimensão de armazenamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="73c1b-138">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="73c1b-139">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="73c1b-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="73c1b-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="73c1b-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="73c1b-141">No campo Grupo de dimensão de rastreamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="73c1b-141">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="73c1b-142">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="73c1b-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="73c1b-143">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="73c1b-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="73c1b-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="73c1b-144">Click OK.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="73c1b-145">Configurar ordem padrão</span><span class="sxs-lookup"><span data-stu-id="73c1b-145">Setup default order settings</span></span>
1. <span data-ttu-id="73c1b-146">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="73c1b-146">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="73c1b-147">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="73c1b-147">Click Default order settings.</span></span>
3. <span data-ttu-id="73c1b-148">No campo local de compra, digite o site usado como o padrão quando as ordens de compra são criadas.</span><span class="sxs-lookup"><span data-stu-id="73c1b-148">In the Purchase site field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="73c1b-149">No campo Local de estoque, digite o local onde o item está armazenado.</span><span class="sxs-lookup"><span data-stu-id="73c1b-149">In the Inventory site field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="73c1b-150">Expandir ou recolher a seção Estoque.</span><span class="sxs-lookup"><span data-stu-id="73c1b-150">Expand or collapse the Inventory section.</span></span>
6. <span data-ttu-id="73c1b-151">Defina Múltiplo para '10'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-151">Set Multiple to '10'.</span></span>
7. <span data-ttu-id="73c1b-152">Definir Min.</span><span class="sxs-lookup"><span data-stu-id="73c1b-152">Set Min.</span></span> <span data-ttu-id="73c1b-153">quantidade de ordem para '10'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-153">order quantity to '10'.</span></span>
8. <span data-ttu-id="73c1b-154">Definir Máx.</span><span class="sxs-lookup"><span data-stu-id="73c1b-154">Set Max.</span></span> <span data-ttu-id="73c1b-155">quantidade de ordem para '100'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-155">order quantity to '100'.</span></span>
9. <span data-ttu-id="73c1b-156">Definir Quantidade de ordem padrão para '10'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-156">Set Standard order quantity to '10'.</span></span>
10. <span data-ttu-id="73c1b-157">No campo de prazo de entrega da compra, insira um número.</span><span class="sxs-lookup"><span data-stu-id="73c1b-157">In the Purchase lead time field, enter a number.</span></span>
11. <span data-ttu-id="73c1b-158">Marque ou desmarque a caixa de seleção Dias úteis.</span><span class="sxs-lookup"><span data-stu-id="73c1b-158">Select or clear the Working days check box.</span></span>
12. <span data-ttu-id="73c1b-159">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="73c1b-159">Click Save.</span></span>
13. <span data-ttu-id="73c1b-160">No campo de ordem padrão, selecione 'Ordem de compra'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-160">In the Default order type field select 'Purchase order'.</span></span>
14. <span data-ttu-id="73c1b-161">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="73c1b-161">Click Save.</span></span>
15. <span data-ttu-id="73c1b-162">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="73c1b-162">Close the page.</span></span>
    * <span data-ttu-id="73c1b-163">Feche a página Configurações padrão da ordem.</span><span class="sxs-lookup"><span data-stu-id="73c1b-163">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="73c1b-164">Adicionar um item ao grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="73c1b-164">Add an item to a coverage group</span></span>
1. <span data-ttu-id="73c1b-165">Expandir ou recolher a seção Plano.</span><span class="sxs-lookup"><span data-stu-id="73c1b-165">Expand or collapse the Plan section.</span></span>
2. <span data-ttu-id="73c1b-166">No campo Grupo de cobertura, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="73c1b-166">In the Coverage group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="73c1b-167">Na lista, localize o grupo de cobertura que você criou.</span><span class="sxs-lookup"><span data-stu-id="73c1b-167">In the list, find the Coverage group you have created.</span></span>
4. <span data-ttu-id="73c1b-168">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="73c1b-168">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="73c1b-169">Criar Regras de cobertura de item</span><span class="sxs-lookup"><span data-stu-id="73c1b-169">Create item coverage rules</span></span>
1. <span data-ttu-id="73c1b-170">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="73c1b-170">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="73c1b-171">Clique em Cobertura de item.</span><span class="sxs-lookup"><span data-stu-id="73c1b-171">Click Item coverage.</span></span>
3. <span data-ttu-id="73c1b-172">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="73c1b-172">Click New.</span></span>
4. <span data-ttu-id="73c1b-173">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="73c1b-173">Click the General tab.</span></span>
5. <span data-ttu-id="73c1b-174">Marque a caixa no cabeçalho de Substituir configurações do grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="73c1b-174">Check the box on the header of Override coverage group settings.</span></span>
6. <span data-ttu-id="73c1b-175">No Tempo limite de cobertura (dias), insira '60'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-175">In the Coverage time fence (days) field, enter '60'.</span></span>
    * <span data-ttu-id="73c1b-176">Embora os itens no grupo de cobertura Requiremen sejam planejados 90 dias depois, esse item será planejado com 60 dias.</span><span class="sxs-lookup"><span data-stu-id="73c1b-176">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="73c1b-177">No campo Dias negativos, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-177">In the Negative days field, enter '2'.</span></span>
8. <span data-ttu-id="73c1b-178">No campo Dias positivos, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-178">In the Positive days field, enter '2'.</span></span>
9. <span data-ttu-id="73c1b-179">Clique na guia do prazo de entrega.</span><span class="sxs-lookup"><span data-stu-id="73c1b-179">Click the Lead time tab.</span></span>
10. <span data-ttu-id="73c1b-180">Marque a caixa no cabeçalho de Compra.</span><span class="sxs-lookup"><span data-stu-id="73c1b-180">Check the box on the header of Purchase.</span></span>
11. <span data-ttu-id="73c1b-181">No campo Tempo de compra, insira '5'.</span><span class="sxs-lookup"><span data-stu-id="73c1b-181">In the Purchase time field, enter '5'.</span></span>
12. <span data-ttu-id="73c1b-182">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="73c1b-182">Click Save.</span></span>

