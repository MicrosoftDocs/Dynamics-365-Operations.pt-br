---
title: Criar uma ordem de compra a partir de uma ordem de venda
description: Este procedimento mostra como criar uma ordem de compra que é baseada em uma ordem de venda.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7991476b86ace92cda513ae8906c62ba7fbbe915
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547406"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a><span data-ttu-id="474e1-103">Criar uma ordem de compra a partir de uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="474e1-103">Create a purchase order from a sales order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="474e1-104">Este procedimento mostra como criar uma ordem de compra que é baseada em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="474e1-104">This procedure shows you how to create a purchase order that is based on a sales order.</span></span> <span data-ttu-id="474e1-105">As quantidades do produto na ordem de compra são designadas para atender a demanda da ordem de venda original.</span><span class="sxs-lookup"><span data-stu-id="474e1-105">The product's quantities on the purchase order are then designated to fulfill the demand of the originating sales order.</span></span> <span data-ttu-id="474e1-106">Atender a demanda de vendas desta forma é uma alternativa a um método mais abrangente e mais otimizado de Planejamento de requisitos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="474e1-106">Fulfilling sales demand this way is an alternative to a more comprehensive and optimized method of Distribution Requirements Planning.</span></span> <span data-ttu-id="474e1-107">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="474e1-107">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-a-purchase-order-from-a-sales-order"></a><span data-ttu-id="474e1-108">Criar uma ordem de compra a partir de uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="474e1-108">Create a purchase order from a sales order</span></span>
1. <span data-ttu-id="474e1-109">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="474e1-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="474e1-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="474e1-110">Click New.</span></span>
3. <span data-ttu-id="474e1-111">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="474e1-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="474e1-112">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="474e1-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="474e1-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="474e1-113">Click OK.</span></span>
6. <span data-ttu-id="474e1-114">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="474e1-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="474e1-115">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="474e1-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="474e1-116">Se você estiver usando USMF, é possível selecionar D0001.</span><span class="sxs-lookup"><span data-stu-id="474e1-116">If you're using USMF, you could select D0001.</span></span>  
8. <span data-ttu-id="474e1-117">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="474e1-117">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="474e1-118">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="474e1-118">Click Add line.</span></span>
10. <span data-ttu-id="474e1-119">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="474e1-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="474e1-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="474e1-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="474e1-121">Se você estiver usando USMF, é possível selecionar T0020.</span><span class="sxs-lookup"><span data-stu-id="474e1-121">If you're using USMF, you could select T0020.</span></span>  
12. <span data-ttu-id="474e1-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="474e1-122">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="474e1-123">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="474e1-123">In the Quantity field, enter a number.</span></span>
14. <span data-ttu-id="474e1-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="474e1-124">Click Save.</span></span>
15. <span data-ttu-id="474e1-125">No Painel de Ação, clique em Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="474e1-125">On the Action Pane, click Sales order.</span></span>
16. <span data-ttu-id="474e1-126">Clique em Ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="474e1-126">Click Purchase order.</span></span>
    * <span data-ttu-id="474e1-127">A página Criar ordem de compra lista todas as linhas da ordem de venda abertas que foram copiadas da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="474e1-127">The Create purchase order page lists all the open sales order lines which have been copied from the sales order.</span></span> <span data-ttu-id="474e1-128">Você pode revisar os detalhes da ordem e, se necessário, pode modificar os detalhes selecionados, como quantidade de compra e condições de preço, antes de criar as compras.</span><span class="sxs-lookup"><span data-stu-id="474e1-128">You can review the order details, and if required, you can modify selected details such purchase quantity and pricing terms, before you create the purchases.</span></span>  
17. <span data-ttu-id="474e1-129">Selecione a opção Incluir tudo.</span><span class="sxs-lookup"><span data-stu-id="474e1-129">Select the Include all option.</span></span>
    * <span data-ttu-id="474e1-130">Se quiser gerar ordens de compra para só um subconjunto de linhas da ordem de venda, selecione-as individualmente.</span><span class="sxs-lookup"><span data-stu-id="474e1-130">If you want to generate purchase orders for only a subset of the sales order lines, select these individually.</span></span>  
    * <span data-ttu-id="474e1-131">O campo Conta de fornecedor poderá ou não ser preenchido com um número de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="474e1-131">The Vendor account field may or may not already be populated with a vendor number.</span></span> <span data-ttu-id="474e1-132">Se o fornecedor padrão for configurado para o produto (na cobertura do Item associado), então este fornecedor será copiado para a linha.</span><span class="sxs-lookup"><span data-stu-id="474e1-132">If the default vendor is set up for the product (on the associated Item coverage) then this vendor will be copied  to the line.</span></span> <span data-ttu-id="474e1-133">Caso contrário, você deverá inserir um fornecedor manualmente.</span><span class="sxs-lookup"><span data-stu-id="474e1-133">Otherwise, you must enter a vendor manually.</span></span>  <span data-ttu-id="474e1-134">Nesta guia, independentemente de o campo Conta de fornecedor já ter ou não um valor, as seguintes etapas o instruem para selecionar um novo fornecedor que é diferente de cada linha.</span><span class="sxs-lookup"><span data-stu-id="474e1-134">In this guide, regardless of whether the Vendor account field already contains a value or not, the following steps instruct you to select a new vendor which is different for each line.</span></span>  
18. <span data-ttu-id="474e1-135">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="474e1-135">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="474e1-136">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="474e1-136">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="474e1-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="474e1-137">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="474e1-138">Selecione a segunda linha de ordem.</span><span class="sxs-lookup"><span data-stu-id="474e1-138">Select the second order line.</span></span>
22. <span data-ttu-id="474e1-139">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="474e1-139">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="474e1-140">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="474e1-140">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="474e1-141">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="474e1-141">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="474e1-142">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="474e1-142">Click Validate.</span></span>
26. <span data-ttu-id="474e1-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="474e1-143">Click OK.</span></span>
    * <span data-ttu-id="474e1-144">A mensagem informa que uma ou mais ordens de compra foram criadas.</span><span class="sxs-lookup"><span data-stu-id="474e1-144">The message informs you that one or more purchase orders have been created.</span></span> <span data-ttu-id="474e1-145">O sistema gera uma ordem de compra separada para cada fornecedor especificado nas linhas da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="474e1-145">The system generates a separate purchase order for each vendor that you specified for the sales order lines.</span></span> <span data-ttu-id="474e1-146">Isso significa que se várias linhas de ordens de venda forem fornecidas pelo mesmo fornecedor, uma única ordem de compra com várias linhas será gerada.</span><span class="sxs-lookup"><span data-stu-id="474e1-146">This means that if several sales order lines are to be supplied by the same vendor, a single purchase order with multiple lines will be generated.</span></span>  

## <a name="review-purchase-orders-created-from-sales-orders"></a><span data-ttu-id="474e1-147">Revise as ordens de compra criadas das ordens de venda</span><span class="sxs-lookup"><span data-stu-id="474e1-147">Review purchase orders created from sales orders</span></span>
1. <span data-ttu-id="474e1-148">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="474e1-148">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="474e1-149">Clique em Ordens relacionadas.</span><span class="sxs-lookup"><span data-stu-id="474e1-149">Click Related orders.</span></span>
    * <span data-ttu-id="474e1-150">A página Ordens relacionadas lista as ordens que foram criadas a partir da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="474e1-150">The Related orders page lists all the orders that were created from the sales order.</span></span> <span data-ttu-id="474e1-151">Neste exemplo, há duas ordens de compra geradas para dois fornecedores diferentes, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="474e1-151">In this example, there are two purchase orders generated for two different vendors respectively.</span></span>  
3. <span data-ttu-id="474e1-152">Clique para seguir o link no campo Ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="474e1-152">Click to follow the link in the Purchase order field.</span></span>
    * <span data-ttu-id="474e1-153">Cada linha da ordem de compra é associada à linha da ordem de venda que gerou a compra.</span><span class="sxs-lookup"><span data-stu-id="474e1-153">Each purchase order line is associated with the sales order line that led to the purchase.</span></span> <span data-ttu-id="474e1-154">A relação com a ordem de venda é indicada na guia Produto na Guia Rápida Detalhes da linha, nos campos Tipo de referência, Número de referência e Lote de referência.</span><span class="sxs-lookup"><span data-stu-id="474e1-154">The relation to the sales order is indicated on the Product tab in the Line details FastTab, in the Reference type, Reference number, and Reference lot fields.</span></span>  
4. <span data-ttu-id="474e1-155">Expandir ou recolher a seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="474e1-155">Expand or collapse the Line details section.</span></span>
5. <span data-ttu-id="474e1-156">Clique na guia de Produto.</span><span class="sxs-lookup"><span data-stu-id="474e1-156">Click the Product tab.</span></span>
    * <span data-ttu-id="474e1-157">O Lote de referência garante que os custos da compra atual sejam cobrados na ordem de venda anexada.</span><span class="sxs-lookup"><span data-stu-id="474e1-157">The Reference lot guarantees that the costs from the current purchase are charged on the attached sales order.</span></span>  
    * <span data-ttu-id="474e1-158">Você pode navegar na ordem de venda original ao abrir o link no campo Número de referência.</span><span class="sxs-lookup"><span data-stu-id="474e1-158">You can navigate to the originating sales order by opening the link in the Reference number field.</span></span>  

