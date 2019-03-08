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
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "325747"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a><span data-ttu-id="d95f4-103">Criar uma ordem de compra a partir de uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="d95f4-103">Create a purchase order from a sales order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d95f4-104">Este procedimento mostra como criar uma ordem de compra que é baseada em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d95f4-104">This procedure shows you how to create a purchase order that is based on a sales order.</span></span> <span data-ttu-id="d95f4-105">As quantidades do produto na ordem de compra são designadas para atender a demanda da ordem de venda original.</span><span class="sxs-lookup"><span data-stu-id="d95f4-105">The product's quantities on the purchase order are then designated to fulfill the demand of the originating sales order.</span></span> <span data-ttu-id="d95f4-106">Atender a demanda de vendas desta forma é uma alternativa a um método mais abrangente e mais otimizado de Planejamento de requisitos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="d95f4-106">Fulfilling sales demand this way is an alternative to a more comprehensive and optimized method of Distribution Requirements Planning.</span></span> <span data-ttu-id="d95f4-107">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="d95f4-107">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-a-purchase-order-from-a-sales-order"></a><span data-ttu-id="d95f4-108">Criar uma ordem de compra a partir de uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="d95f4-108">Create a purchase order from a sales order</span></span>
1. <span data-ttu-id="d95f4-109">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="d95f4-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="d95f4-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d95f4-110">Click New.</span></span>
3. <span data-ttu-id="d95f4-111">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d95f4-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d95f4-112">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="d95f4-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="d95f4-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d95f4-113">Click OK.</span></span>
6. <span data-ttu-id="d95f4-114">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d95f4-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d95f4-115">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="d95f4-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d95f4-116">Se você estiver usando USMF, é possível selecionar D0001.</span><span class="sxs-lookup"><span data-stu-id="d95f4-116">If you're using USMF, you could select D0001.</span></span>  
8. <span data-ttu-id="d95f4-117">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d95f4-117">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="d95f4-118">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="d95f4-118">Click Add line.</span></span>
10. <span data-ttu-id="d95f4-119">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d95f4-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="d95f4-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="d95f4-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d95f4-121">Se você estiver usando USMF, é possível selecionar T0020.</span><span class="sxs-lookup"><span data-stu-id="d95f4-121">If you're using USMF, you could select T0020.</span></span>  
12. <span data-ttu-id="d95f4-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d95f4-122">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="d95f4-123">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d95f4-123">In the Quantity field, enter a number.</span></span>
14. <span data-ttu-id="d95f4-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d95f4-124">Click Save.</span></span>
15. <span data-ttu-id="d95f4-125">No Painel de Ação, clique em Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d95f4-125">On the Action Pane, click Sales order.</span></span>
16. <span data-ttu-id="d95f4-126">Clique em Ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="d95f4-126">Click Purchase order.</span></span>
    * <span data-ttu-id="d95f4-127">A página Criar ordem de compra lista todas as linhas da ordem de venda abertas que foram copiadas da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d95f4-127">The Create purchase order page lists all the open sales order lines which have been copied from the sales order.</span></span> <span data-ttu-id="d95f4-128">Você pode revisar os detalhes da ordem e, se necessário, pode modificar os detalhes selecionados, como quantidade de compra e condições de preço, antes de criar as compras.</span><span class="sxs-lookup"><span data-stu-id="d95f4-128">You can review the order details, and if required, you can modify selected details such purchase quantity and pricing terms, before you create the purchases.</span></span>  
17. <span data-ttu-id="d95f4-129">Selecione a opção Incluir tudo.</span><span class="sxs-lookup"><span data-stu-id="d95f4-129">Select the Include all option.</span></span>
    * <span data-ttu-id="d95f4-130">Se quiser gerar ordens de compra para só um subconjunto de linhas da ordem de venda, selecione-as individualmente.</span><span class="sxs-lookup"><span data-stu-id="d95f4-130">If you want to generate purchase orders for only a subset of the sales order lines, select these individually.</span></span>  
    * <span data-ttu-id="d95f4-131">O campo Conta de fornecedor poderá ou não ser preenchido com um número de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="d95f4-131">The Vendor account field may or may not already be populated with a vendor number.</span></span> <span data-ttu-id="d95f4-132">Se o fornecedor padrão for configurado para o produto (na cobertura do Item associado), então este fornecedor será copiado para a linha.</span><span class="sxs-lookup"><span data-stu-id="d95f4-132">If the default vendor is set up for the product (on the associated Item coverage) then this vendor will be copied  to the line.</span></span> <span data-ttu-id="d95f4-133">Caso contrário, você deverá inserir um fornecedor manualmente.</span><span class="sxs-lookup"><span data-stu-id="d95f4-133">Otherwise, you must enter a vendor manually.</span></span>  <span data-ttu-id="d95f4-134">Nesta guia, independentemente de o campo Conta de fornecedor já ter ou não um valor, as seguintes etapas o instruem para selecionar um novo fornecedor que é diferente de cada linha.</span><span class="sxs-lookup"><span data-stu-id="d95f4-134">In this guide, regardless of whether the Vendor account field already contains a value or not, the following steps instruct you to select a new vendor which is different for each line.</span></span>  
18. <span data-ttu-id="d95f4-135">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d95f4-135">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="d95f4-136">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="d95f4-136">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="d95f4-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d95f4-137">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="d95f4-138">Selecione a segunda linha de ordem.</span><span class="sxs-lookup"><span data-stu-id="d95f4-138">Select the second order line.</span></span>
22. <span data-ttu-id="d95f4-139">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d95f4-139">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="d95f4-140">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="d95f4-140">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="d95f4-141">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d95f4-141">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="d95f4-142">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="d95f4-142">Click Validate.</span></span>
26. <span data-ttu-id="d95f4-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d95f4-143">Click OK.</span></span>
    * <span data-ttu-id="d95f4-144">A mensagem informa que uma ou mais ordens de compra foram criadas.</span><span class="sxs-lookup"><span data-stu-id="d95f4-144">The message informs you that one or more purchase orders have been created.</span></span> <span data-ttu-id="d95f4-145">O sistema gera uma ordem de compra separada para cada fornecedor especificado nas linhas da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d95f4-145">The system generates a separate purchase order for each vendor that you specified for the sales order lines.</span></span> <span data-ttu-id="d95f4-146">Isso significa que se várias linhas de ordens de venda forem fornecidas pelo mesmo fornecedor, uma única ordem de compra com várias linhas será gerada.</span><span class="sxs-lookup"><span data-stu-id="d95f4-146">This means that if several sales order lines are to be supplied by the same vendor, a single purchase order with multiple lines will be generated.</span></span>  

## <a name="review-purchase-orders-created-from-sales-orders"></a><span data-ttu-id="d95f4-147">Revise as ordens de compra criadas das ordens de venda</span><span class="sxs-lookup"><span data-stu-id="d95f4-147">Review purchase orders created from sales orders</span></span>
1. <span data-ttu-id="d95f4-148">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="d95f4-148">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="d95f4-149">Clique em Ordens relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d95f4-149">Click Related orders.</span></span>
    * <span data-ttu-id="d95f4-150">A página Ordens relacionadas lista as ordens que foram criadas a partir da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d95f4-150">The Related orders page lists all the orders that were created from the sales order.</span></span> <span data-ttu-id="d95f4-151">Neste exemplo, há duas ordens de compra geradas para dois fornecedores diferentes, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d95f4-151">In this example, there are two purchase orders generated for two different vendors respectively.</span></span>  
3. <span data-ttu-id="d95f4-152">Clique para seguir o link no campo Ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="d95f4-152">Click to follow the link in the Purchase order field.</span></span>
    * <span data-ttu-id="d95f4-153">Cada linha da ordem de compra é associada à linha da ordem de venda que gerou a compra.</span><span class="sxs-lookup"><span data-stu-id="d95f4-153">Each purchase order line is associated with the sales order line that led to the purchase.</span></span> <span data-ttu-id="d95f4-154">A relação com a ordem de venda é indicada na guia Produto na Guia Rápida Detalhes da linha, nos campos Tipo de referência, Número de referência e Lote de referência.</span><span class="sxs-lookup"><span data-stu-id="d95f4-154">The relation to the sales order is indicated on the Product tab in the Line details FastTab, in the Reference type, Reference number, and Reference lot fields.</span></span>  
4. <span data-ttu-id="d95f4-155">Expandir ou recolher a seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="d95f4-155">Expand or collapse the Line details section.</span></span>
5. <span data-ttu-id="d95f4-156">Clique na guia de Produto.</span><span class="sxs-lookup"><span data-stu-id="d95f4-156">Click the Product tab.</span></span>
    * <span data-ttu-id="d95f4-157">O Lote de referência garante que os custos da compra atual sejam cobrados na ordem de venda anexada.</span><span class="sxs-lookup"><span data-stu-id="d95f4-157">The Reference lot guarantees that the costs from the current purchase are charged on the attached sales order.</span></span>  
    * <span data-ttu-id="d95f4-158">Você pode navegar na ordem de venda original ao abrir o link no campo Número de referência.</span><span class="sxs-lookup"><span data-stu-id="d95f4-158">You can navigate to the originating sales order by opening the link in the Reference number field.</span></span>  

