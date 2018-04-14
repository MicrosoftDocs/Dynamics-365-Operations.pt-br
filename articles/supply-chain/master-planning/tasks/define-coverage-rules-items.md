--- 
title: Definir regras de cobertura para itens
description: "A empresa de dados demo usada para criar este procedimento é USMF."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4d28abe06cb7bfd43fd95af8cd88e022a51f5380
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="bd2f1-103">Definir regras de cobertura para itens</span><span class="sxs-lookup"><span data-stu-id="bd2f1-103">Define coverage rules for items</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd2f1-104">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bd2f1-105">Este procedimento mostra como criar regras de cobertura e substituir configurações de cobertura para um item específico.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="bd2f1-106">Também mostra como especificar as configurações padrão de estoque.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="bd2f1-107">Crie um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-107">Create a coverage group</span></span>
1. <span data-ttu-id="bd2f1-108">Ir para Grupos de cobertura.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-108">Go to Coverage groups.</span></span>
2. <span data-ttu-id="bd2f1-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-109">Click New.</span></span>
3. <span data-ttu-id="bd2f1-110">No campo Grupo de cobertura, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-110">In the Coverage group field, type a value.</span></span>
4. <span data-ttu-id="bd2f1-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="bd2f1-112">No campo Calendário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-112">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="bd2f1-113">Escolha o calendário utilizado pelo planejamento mestre para criar indicações de reabastecimento para itens desse grupo.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="bd2f1-114">No campo Código de cobertura, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-114">In the Coverage code field, select an option.</span></span>
    * <span data-ttu-id="bd2f1-115">Selecione Requisito para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-115">Select Requirement for this procedure.</span></span>  
7. <span data-ttu-id="bd2f1-116">No Tempo limite de cobertura (dias), insira '90'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-116">In the Coverage time fence (days) field, enter '90'.</span></span>
    * <span data-ttu-id="bd2f1-117">Para itens desse grupo, o planejamento mestre criará indicações de reabastecimento por até 90 dias no futuro.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="bd2f1-118">No campo Dias negativos, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-118">In the Negative days field, enter '1'.</span></span>
9. <span data-ttu-id="bd2f1-119">No campo Dias positivos, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-119">In the Positive days field, enter '1'.</span></span>
10. <span data-ttu-id="bd2f1-120">Expandir ou recolher a seção Outros.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-120">Expand or collapse the Other section.</span></span>
11. <span data-ttu-id="bd2f1-121">No campo Margem de recebimento adicionada à data de requisição, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-121">In the Receipt margin added to requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="bd2f1-122">Por exemplo, se a margem de recebimento estiver definida para 1 dia, e uma linha da ordem de compra estiver programada para recebimento em 15 de maio, o planejamento mestre calculará a data de recebimento ajustada como 16 de maio.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="bd2f1-123">No campo Margem de emissão deduzida da data de requisição, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-123">In the Issue margin deducted from requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="bd2f1-124">Por exemplo, se a margem de segurança estiver definida como 1 dia, e uma linha da ordem de venda estiver programada para entrega em 15 de maio, o agendamento do planejamento mestre calculará a data de entrega ajustada como 14 de maio.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="bd2f1-125">No campo Reordenar margem adicionada ao prazo de entrega do item, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-125">In the Reorder margin added to item lead time field, enter '1'.</span></span>
14. <span data-ttu-id="bd2f1-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-126">Click Save.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="bd2f1-127">Criar um novo produto</span><span class="sxs-lookup"><span data-stu-id="bd2f1-127">Create a new product</span></span>
1. <span data-ttu-id="bd2f1-128">Vá para Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-128">Go to Released products.</span></span>
2. <span data-ttu-id="bd2f1-129">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-129">Click New.</span></span>
3. <span data-ttu-id="bd2f1-130">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-130">In the Product number field, type a value.</span></span>
4. <span data-ttu-id="bd2f1-131">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-131">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="bd2f1-132">No campo Grupo de modelo do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-132">In the Item model group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="bd2f1-133">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="bd2f1-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="bd2f1-135">No campo Grupo de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-135">In the Item group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="bd2f1-136">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="bd2f1-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="bd2f1-138">No campo Grupo de dimensão de armazenamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-138">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="bd2f1-139">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="bd2f1-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="bd2f1-141">No campo Grupo de dimensão de rastreamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-141">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="bd2f1-142">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="bd2f1-143">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="bd2f1-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-144">Click OK.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="bd2f1-145">Configurar ordem padrão</span><span class="sxs-lookup"><span data-stu-id="bd2f1-145">Setup default order settings</span></span>
1. <span data-ttu-id="bd2f1-146">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-146">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="bd2f1-147">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-147">Click Default order settings.</span></span>
3. <span data-ttu-id="bd2f1-148">No campo local de compra, digite o site usado como o padrão quando as ordens de compra são criadas.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-148">In the Purchase site field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="bd2f1-149">No campo Local de estoque, digite o local onde o item está armazenado.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-149">In the Inventory site field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="bd2f1-150">Expandir ou recolher a seção Estoque.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-150">Expand or collapse the Inventory section.</span></span>
6. <span data-ttu-id="bd2f1-151">Defina Múltiplo para '10'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-151">Set Multiple to '10'.</span></span>
7. <span data-ttu-id="bd2f1-152">Definir Min.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-152">Set Min.</span></span> <span data-ttu-id="bd2f1-153">quantidade de ordem para '10'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-153">order quantity to '10'.</span></span>
8. <span data-ttu-id="bd2f1-154">Definir Máx.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-154">Set Max.</span></span> <span data-ttu-id="bd2f1-155">quantidade de ordem para '100'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-155">order quantity to '100'.</span></span>
9. <span data-ttu-id="bd2f1-156">Definir Quantidade de ordem padrão para '10'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-156">Set Standard order quantity to '10'.</span></span>
10. <span data-ttu-id="bd2f1-157">No campo de prazo de entrega da compra, insira um número.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-157">In the Purchase lead time field, enter a number.</span></span>
11. <span data-ttu-id="bd2f1-158">Marque ou desmarque a caixa de seleção Dias úteis.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-158">Select or clear the Working days check box.</span></span>
12. <span data-ttu-id="bd2f1-159">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-159">Click Save.</span></span>
13. <span data-ttu-id="bd2f1-160">No campo de ordem padrão, selecione 'Ordem de compra'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-160">In the Default order type field select 'Purchase order'.</span></span>
14. <span data-ttu-id="bd2f1-161">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-161">Click Save.</span></span>
15. <span data-ttu-id="bd2f1-162">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-162">Close the page.</span></span>
    * <span data-ttu-id="bd2f1-163">Feche a página Configurações padrão da ordem.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-163">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="bd2f1-164">Adicionar um item ao grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="bd2f1-164">Add an item to a coverage group</span></span>
1. <span data-ttu-id="bd2f1-165">Expandir ou recolher a seção Plano.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-165">Expand or collapse the Plan section.</span></span>
2. <span data-ttu-id="bd2f1-166">No campo Grupo de cobertura, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-166">In the Coverage group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="bd2f1-167">Na lista, localize o grupo de cobertura que você criou.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-167">In the list, find the Coverage group you have created.</span></span>
4. <span data-ttu-id="bd2f1-168">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-168">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="bd2f1-169">Criar Regras de cobertura de item</span><span class="sxs-lookup"><span data-stu-id="bd2f1-169">Create item coverage rules</span></span>
1. <span data-ttu-id="bd2f1-170">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-170">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="bd2f1-171">Clique em Cobertura de item.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-171">Click Item coverage.</span></span>
3. <span data-ttu-id="bd2f1-172">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-172">Click New.</span></span>
4. <span data-ttu-id="bd2f1-173">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-173">Click the General tab.</span></span>
5. <span data-ttu-id="bd2f1-174">Marque a caixa no cabeçalho de Substituir configurações do grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-174">Check the box on the header of Override coverage group settings.</span></span>
6. <span data-ttu-id="bd2f1-175">No Tempo limite de cobertura (dias), insira '60'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-175">In the Coverage time fence (days) field, enter '60'.</span></span>
    * <span data-ttu-id="bd2f1-176">Embora os itens no Requisito de grupo de recursos sejam planejados com 90 dias de antecedência, esse item será planejado com 60 dias.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-176">Although items in coverage group Requirement are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="bd2f1-177">No campo Dias negativos, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-177">In the Negative days field, enter '2'.</span></span>
8. <span data-ttu-id="bd2f1-178">No campo Dias positivos, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-178">In the Positive days field, enter '2'.</span></span>
9. <span data-ttu-id="bd2f1-179">Clique na guia do prazo de entrega.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-179">Click the Lead time tab.</span></span>
10. <span data-ttu-id="bd2f1-180">Marque a caixa no cabeçalho de Compra.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-180">Check the box on the header of Purchase.</span></span>
11. <span data-ttu-id="bd2f1-181">No campo Tempo de compra, insira '5'.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-181">In the Purchase time field, enter '5'.</span></span>
12. <span data-ttu-id="bd2f1-182">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="bd2f1-182">Click Save.</span></span>


