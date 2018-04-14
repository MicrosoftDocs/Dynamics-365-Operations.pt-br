--- 
title: "Criar um produto lançado para uma única empresa"
description: "Este procedimento demonstra como criar um único produto lançado no contexto de uma unidade legal única."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ced48377f8f6cfdf416bcaf5e2b5e6473998ea91
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-released-product-for-a-single-company"></a><span data-ttu-id="b8ab2-103">Criar um produto lançado para uma única empresa</span><span class="sxs-lookup"><span data-stu-id="b8ab2-103">Create a released product for a single company</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b8ab2-104">Este procedimento demonstra como criar um único produto lançado no contexto de uma unidade legal única.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-104">This procedure walks through how to create a single released product in the context of a single legal unit.</span></span> <span data-ttu-id="b8ab2-105">Depois que o produto lançado é criado, ele está imediatamente disponível somente nessa unidade.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-105">After the released product is created,  it's immediately available in this unit only.</span></span> <span data-ttu-id="b8ab2-106">Você pode explorar esse procedimento na empresa de dados demonstrativos USMF.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-106">You can walk through this procedure in demo data company USMF.</span></span> <span data-ttu-id="b8ab2-107">Esta tarefa é executada geralmente por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-107">This task is usually performed by a product designer.</span></span>


## <a name="create-a-released-product"></a><span data-ttu-id="b8ab2-108">Crie um produto lançado</span><span class="sxs-lookup"><span data-stu-id="b8ab2-108">Create a released product</span></span>
1. <span data-ttu-id="b8ab2-109">Vá para Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-109">Go to Released products.</span></span>
2. <span data-ttu-id="b8ab2-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-110">Click New.</span></span>
3. <span data-ttu-id="b8ab2-111">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-111">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="b8ab2-112">Se um número de produto não é inserido automaticamente no campo Número do produto, digite um número de produto exclusivo.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-112">If a product number is not automatically entered in the Product number field, type a unique product number.</span></span> <span data-ttu-id="b8ab2-113">Essa etapa só é necessária se nenhuma sequência numérica foi definida para números de produto.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-113">This step is only  required if no number sequence has been set up for product numbers.</span></span>  
4. <span data-ttu-id="b8ab2-114">No campo Nome do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="b8ab2-115">O padrão do Nome do produto é o nome de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-115">The Product name is defaulted to the search name.</span></span> <span data-ttu-id="b8ab2-116">Se necessário, você pode selecionar para alterar o nome de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-116">If needed, you can select to change the search name.</span></span>  
5. <span data-ttu-id="b8ab2-117">No campo Grupo de modelo do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-117">In the Item model group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-118">Os grupos de modelos de item contêm configurações que determinam como os itens são controlados e manuseados em recebimentos e saídas.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-118">The item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="b8ab2-119">As configurações também determinam como o consumo de itens é calculado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-119">The settings also determine how the consumption of items are calculated.</span></span>  
6. <span data-ttu-id="b8ab2-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="b8ab2-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-121">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="b8ab2-122">No campo Grupo de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-122">In the Item group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-123">Os grupos de itens são usados para gerenciar o estoque, dividindo os itens de estoque em grupos com base nas características do item.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-123">Item groups are used to manage inventory by dividing inventory items into groups based on item characteristics.</span></span> <span data-ttu-id="b8ab2-124">Por exemplo, para gerenciar como as informações são postadas nas contas principais, você pode criar uma série de grupos de itens diferentes associados a contas principais específicas.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-124">For example, to manage how information is posted to main accounts, you can create a series of different item groups that are associated with specific main accounts.</span></span> <span data-ttu-id="b8ab2-125">Isso permite que você acompanhe o valor de estoque de itens em estágios diferentes.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-125">This lets you track the inventory value of items at different stages.</span></span>  
9. <span data-ttu-id="b8ab2-126">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-126">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="b8ab2-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-127">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="b8ab2-128">No campo Grupo de dimensão de armazenamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-128">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-129">As dimensões de armazenamento ajudam a controlar como os itens são armazenados e retirados do estoque.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-129">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="b8ab2-130">Por exemplo, uma dimensão de armazenamento pode ser Local e Depósito.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-130">For example, a storage dimension can be Site and Warehouse.</span></span>  
12. <span data-ttu-id="b8ab2-131">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-131">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="b8ab2-132">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-132">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="b8ab2-133">No campo Grupo de dimensão de rastreamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-133">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-134">O grupo de dimensões de rastreamento determina quais dimensões de rastreamento você pode adicionar a um produto.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-134">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="b8ab2-135">Por exemplo, o número de lote e o número de série são usados para rastrear itens de estoque.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-135">For example, the batch number and serial number are used to track inventory items.</span></span>  
15. <span data-ttu-id="b8ab2-136">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-136">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="b8ab2-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-137">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="b8ab2-138">No campo Unidade de estoque, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-138">In the Inventory unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-139">A unidade de estoque determina como o produto é quantificado quando é armazenado no estoque.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-139">The inventory unit determines how the product is quantified when it's stored in inventory.</span></span>  
18. <span data-ttu-id="b8ab2-140">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-140">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="b8ab2-141">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-141">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="b8ab2-142">No campo Unidade de compra, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-142">In the Purchase unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-143">A unidade de compra determina como o produto é quantificado quando é comprado de um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-143">The purchase unit determines how the product is quantified when it’s purchased from a vendor.</span></span>  
21. <span data-ttu-id="b8ab2-144">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-144">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="b8ab2-145">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-145">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="b8ab2-146">No campo Unidade de vendas, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-146">In the Sales unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-147">A unidade de vendas determina como o produto é quantificado quando é vendido a um cliente.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-147">The sales unit determines how the product is quantified when it’s sold to a customer.</span></span>  
24. <span data-ttu-id="b8ab2-148">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-148">In the list, find and select the desired record.</span></span>
25. <span data-ttu-id="b8ab2-149">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-149">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="b8ab2-150">No campo Unidade BOM, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-150">In the BOM unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-151">A unidade BOM determina como o produto é quantificado quando é incluso numa Lista de Materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="b8ab2-151">The BOM unit determines how the product is quantified when including it in a bill of materials (BOM).</span></span>  
27. <span data-ttu-id="b8ab2-152">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-152">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="b8ab2-153">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-153">In the list, click the link in the selected row.</span></span>
29. <span data-ttu-id="b8ab2-154">No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-154">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-155">O grupo de impostos sobre vendas do item no grupo de tributação de vendas determina como o imposto sobre as vendas é calculado para cada item.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-155">The item sales tax group in the Sales taxation group determines how sales tax is calculated for each item.</span></span>  
30. <span data-ttu-id="b8ab2-156">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-156">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="b8ab2-157">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-157">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="b8ab2-158">No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-158">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b8ab2-159">O grupo de impostos sobre vendas do item no grupo de tributação de compras determina como o imposto sobre as compras é calculado para cada item.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-159">The item sales tax group in the Purchase taxation group determines how purchase tax is calculated for each item.</span></span>  
33. <span data-ttu-id="b8ab2-160">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-160">In the list, find and select the desired record.</span></span>
34. <span data-ttu-id="b8ab2-161">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-161">In the list, click the link in the selected row.</span></span>
35. <span data-ttu-id="b8ab2-162">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-162">Click OK.</span></span>

## <a name="add-product-characteristics"></a><span data-ttu-id="b8ab2-163">Adicione características do produto.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-163">Add product characteristics</span></span>
1. <span data-ttu-id="b8ab2-164">Expandir ou recolher a seção Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-164">Expand or collapse the Manage inventory section.</span></span>
2. <span data-ttu-id="b8ab2-165">No campo Peso líquido, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-165">In the Net weight field, enter a number.</span></span>
3. <span data-ttu-id="b8ab2-166">No campo Tara, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-166">In the Tare weight field, enter a number.</span></span>
4. <span data-ttu-id="b8ab2-167">No campo Profundidade bruta, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-167">In the Gross depth field, enter a number.</span></span>
5. <span data-ttu-id="b8ab2-168">No campo Largura bruta, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-168">In the Gross width field, enter a number.</span></span>
6. <span data-ttu-id="b8ab2-169">No campo Altura bruta, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-169">In the Gross height field, enter a number.</span></span>
7. <span data-ttu-id="b8ab2-170">No campo Volume, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-170">In the Volume field, enter a number.</span></span>

## <a name="add-financial-dimensions"></a><span data-ttu-id="b8ab2-171">Adicione dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="b8ab2-171">Add financial dimensions</span></span>
1. <span data-ttu-id="b8ab2-172">Expanda ou recolha a seção Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-172">Expand or collapse the Financial dimensions section.</span></span>
2. <span data-ttu-id="b8ab2-173">No campo Unidade de Negócios, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-173">In the BusinessUnit field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b8ab2-174">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-174">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b8ab2-175">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-175">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b8ab2-176">No campo Centro de Custo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-176">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="b8ab2-177">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-177">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="b8ab2-178">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-178">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="b8ab2-179">No campo Departamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-179">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="b8ab2-180">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-180">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="b8ab2-181">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-181">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="b8ab2-182">No campo Grupo de Item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-182">In the ItemGroup field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="b8ab2-183">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-183">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="b8ab2-184">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b8ab2-184">In the list, click the link in the selected row.</span></span>


