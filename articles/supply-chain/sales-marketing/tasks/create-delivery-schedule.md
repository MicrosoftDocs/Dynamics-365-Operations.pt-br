---
title: Criar agenda de entrega
description: Este procedimento demonstra como criar uma agenda de entrega para ordem de venda.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af983b30530a7f5d0a82f98deeb12180c42d86cd
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215806"
---
# <a name="create-delivery-schedule"></a><span data-ttu-id="39845-103">Criar agenda de entrega</span><span class="sxs-lookup"><span data-stu-id="39845-103">Create delivery schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="39845-104">Este procedimento demonstra como criar uma agenda de entrega para ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="39845-104">This procedure demonstrates how to create a delivery schedule for a sales order.</span></span> <span data-ttu-id="39845-105">Um plano de entrega é usado quando uma quantidade em uma ordem ou cotação for exigido para ser entregue em várias remessas.</span><span class="sxs-lookup"><span data-stu-id="39845-105">A delivery schedule is used when a quantity on an order or a quotation is requested to be delivered in multiple shipments.</span></span> <span data-ttu-id="39845-106">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="39845-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-delivery-schedule"></a><span data-ttu-id="39845-107">Criar agenda de entrega</span><span class="sxs-lookup"><span data-stu-id="39845-107">Create delivery schedule</span></span>
1. <span data-ttu-id="39845-108">Ir para Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="39845-108">Go to All sales orders.</span></span>
2. <span data-ttu-id="39845-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="39845-109">Click New.</span></span>
3. <span data-ttu-id="39845-110">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="39845-110">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="39845-111">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="39845-111">Click OK.</span></span>
5. <span data-ttu-id="39845-112">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="39845-112">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="39845-113">No campo Quantidade, insira um número que é maior do que 1.</span><span class="sxs-lookup"><span data-stu-id="39845-113">In the Quantity field, enter a number that is bigger than 1.</span></span>
7. <span data-ttu-id="39845-114">Clique em Linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="39845-114">Click Sales order line.</span></span>
8. <span data-ttu-id="39845-115">Clique em Agenda de entrega.</span><span class="sxs-lookup"><span data-stu-id="39845-115">Click Delivery schedule.</span></span>
    * <span data-ttu-id="39845-116">A página do plano de entrega é o local onde é possível especificar o número de remessas na qual a quantidade total da linha da ordem será enviado ao cliente.</span><span class="sxs-lookup"><span data-stu-id="39845-116">The Delivery schedule page is the place where you can specify the number of shipments in which the total quantity of the order line will be delivered to the customer.</span></span>    
    * <span data-ttu-id="39845-117">Por padrão, o sistema copia a quantidade total e outros detalhes de entrega das vendas originais de linha na primeira linha do plano de entrega.</span><span class="sxs-lookup"><span data-stu-id="39845-117">By default, the system copies the total quantity and other delivery details of the original sales line into the first delivery schedule line.</span></span> <span data-ttu-id="39845-118">Neste exemplo, criaremos um plano para duas remessas, com a segunda data de remessa compensada em uma semana da primeira.</span><span class="sxs-lookup"><span data-stu-id="39845-118">In this example, we'll create a schedule for two shipments, with the second shipment's date offset by a week from the first one.</span></span>  
9. <span data-ttu-id="39845-119">No campo Quantidade, insira um número que faz parte da quantidade total.</span><span class="sxs-lookup"><span data-stu-id="39845-119">In the Quantity field, enter a number that is part of the total quantity.</span></span>
10. <span data-ttu-id="39845-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="39845-120">Click New.</span></span>
11. <span data-ttu-id="39845-121">No campo Quantidade, insira a quantidade restante.</span><span class="sxs-lookup"><span data-stu-id="39845-121">In the Quantity field, enter the remaining quantity.</span></span>
12. <span data-ttu-id="39845-122">No campo Data de remessa solicitada, insira uma data a partir de uma data que seja uma semana depois da data da primeira linha de entrega.</span><span class="sxs-lookup"><span data-stu-id="39845-122">In the Requested ship date field, enter a date a date that is one week ahead from the date of the first delivery line.</span></span>
    * <span data-ttu-id="39845-123">As duas opções na conversão dos encargos FastTab controlam como deseja que os encargos devem ser distribuídos nas linhas do plano de entrega, uma vez que foram atribuídos à linha da ordem original.</span><span class="sxs-lookup"><span data-stu-id="39845-123">The two options on the Charges conversion FastTab control how you want the charges to be distributed across the delivery schedule lines, once they've been assigned to the original order line.</span></span> <span data-ttu-id="39845-124">Se você selecionar valores brutos de impressão, o mesmo valor de encargo será copiado para cada linha.</span><span class="sxs-lookup"><span data-stu-id="39845-124">If you select Copy gross amounts, the same charge amount is copied to each line.</span></span> <span data-ttu-id="39845-125">A opção Alocar à opção das linhas de entrega divide os encargos igualmente pelas linhas de entrega.</span><span class="sxs-lookup"><span data-stu-id="39845-125">The Allocate to delivery lines option divides the charge equally across the delivery lines.</span></span>  
    * <span data-ttu-id="39845-126">Somente os encargos fixos podem ser divididos, enquanto os encargos variáveis ainda serão copiados para as linhas.</span><span class="sxs-lookup"><span data-stu-id="39845-126">Only fixed charges can be divided, whereas variable charges will still be copied to the lines.</span></span>  
13. <span data-ttu-id="39845-127">Mova o cursor distante da segunda linha de entrega para atualizar a página.</span><span class="sxs-lookup"><span data-stu-id="39845-127">Move the cursor away from the second delivery line to update the page.</span></span>
    * <span data-ttu-id="39845-128">Você pode controlar a quantidade total alocada para as linhas do plano de entrega olhando totais e os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="39845-128">You can keep track of the total quantity that's allocated to the delivery schedule lines by looking at the Total and Remaining fields.</span></span> <span data-ttu-id="39845-129">Quando a quantidade restante for zero, a quantidade total de linha original esteve alocada ao plano.</span><span class="sxs-lookup"><span data-stu-id="39845-129">When the remaining quantity is zero, the full quantity from the original line has been allocated to the schedule.</span></span>   
14. <span data-ttu-id="39845-130">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="39845-130">Click OK.</span></span>
    * <span data-ttu-id="39845-131">A agenda de entrega agora foi copiada para as linhas da ordem.</span><span class="sxs-lookup"><span data-stu-id="39845-131">The delivery schedule has now been copied to the order lines.</span></span>   
    * <span data-ttu-id="39845-132">A linha da ordem original, conhecida como uma linha comercial, foi convertida em uma linha da ordem com várias entregas.</span><span class="sxs-lookup"><span data-stu-id="39845-132">The original order line, referred to as a Commercial line, has been converted to an Order line with multiple deliveries.</span></span> <span data-ttu-id="39845-133">São marcadas com um ícone distinto e atuam como um cabeçalho para as linhas de entrega.</span><span class="sxs-lookup"><span data-stu-id="39845-133">It is marked with a distinct icon and acts as a header for the delivery lines.</span></span>  
    * <span data-ttu-id="39845-134">As duas novas linhas, referidas como linhas de entrega, compõem uma agenda de entrega.</span><span class="sxs-lookup"><span data-stu-id="39845-134">The two new lines, referred to as delivery lines, make up one delivery schedule.</span></span> <span data-ttu-id="39845-135">A ordem será processada nessas linhas e não na linha original.</span><span class="sxs-lookup"><span data-stu-id="39845-135">The order will be processed against these lines and not the original line.</span></span> <span data-ttu-id="39845-136">Se os documentos como guias de confirmações, listas de separação, guias de remessa ou notas fiscais forem impressos, apenas as linhas de entrega serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="39845-136">If documents such as confirmation slips, picking lists, packing slips, or invoices are printed, only the delivery lines are shown.</span></span>   
    * <span data-ttu-id="39845-137">As linhas de entrega podem ter datas de entrega diferentes, quantidades, modos de entrega e dimensões de armazenamento, como o site e o depósito.</span><span class="sxs-lookup"><span data-stu-id="39845-137">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span> <span data-ttu-id="39845-138">Entretanto, as dimensões do produto devem corresponder sempre àquela na linha comercial e não podem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="39845-138">However, the product dimensions must always match the ones on the commercial line and can't be changed.</span></span>  
15. <span data-ttu-id="39845-139">No campo Quantidade, insira um número que é maior do que o atual.</span><span class="sxs-lookup"><span data-stu-id="39845-139">In the Quantity field, enter a number that's bigger than the current one.</span></span>
16. <span data-ttu-id="39845-140">Selecione a linha comercial para ver o efeito do recálculo de quantidade.</span><span class="sxs-lookup"><span data-stu-id="39845-140">Select the commercial line to see the effect of the quantity recalculation.</span></span>
17. <span data-ttu-id="39845-141">No Painel de Ação, clique em Separar e empacotar.</span><span class="sxs-lookup"><span data-stu-id="39845-141">On the Action Pane, click Pick and pack.</span></span>
18. <span data-ttu-id="39845-142">Clique em Postar guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="39845-142">Click Post packing slip.</span></span>
19. <span data-ttu-id="39845-143">Expanda a seção Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="39845-143">Expand the Parameters section.</span></span>
20. <span data-ttu-id="39845-144">No campo Quantidade, selecione 'Tudo'.</span><span class="sxs-lookup"><span data-stu-id="39845-144">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="39845-145">Observe que a guia de remessa será criada para as duas linhas do plano de entrega e não a linha da ordem original.</span><span class="sxs-lookup"><span data-stu-id="39845-145">Note that the packing slip will be created for the two delivery schedule lines and not the original order line.</span></span>  
21. <span data-ttu-id="39845-146">Selecione Sim no campo Imprimir guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="39845-146">Select Yes in the Print packing slip field.</span></span>
22. <span data-ttu-id="39845-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="39845-147">Click OK.</span></span>
23. <span data-ttu-id="39845-148">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="39845-148">Click Yes.</span></span>
24. <span data-ttu-id="39845-149">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="39845-149">Close the page.</span></span>

