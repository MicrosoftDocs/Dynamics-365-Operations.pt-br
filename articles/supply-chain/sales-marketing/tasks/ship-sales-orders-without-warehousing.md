--- 
title: Enviar ordens de venda sem armazenamento
description: "Este guia demonstra como atualizar uma ordem de venda quando produtos são enviados ao cliente."
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8e7d2198b4976a6f60f05690d7b6f11f3da55e28
ms.openlocfilehash: a98e58b26432ee01e62d60f81a768f14568e34e4
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---
# <a name="ship-sales-orders-without-warehousing"></a><span data-ttu-id="d7a83-103">Enviar ordens de venda sem armazenamento</span><span class="sxs-lookup"><span data-stu-id="d7a83-103">Ship sales orders without warehousing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d7a83-104">Este guia demonstra como atualizar uma ordem de venda quando produtos são enviados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="d7a83-104">This guide demonstrates how to update a sales order when products are shipped to the customer.</span></span> <span data-ttu-id="d7a83-105">Este guia é aplicável ao fluxo de realizações que não está definido para o gerenciamento de depósito (sem armazenamento básico ou avançado) e, portanto, não requer separação de produtos que serão registrados antes da remessa.</span><span class="sxs-lookup"><span data-stu-id="d7a83-105">The guide is applicable to the fulfillment flow that is not set up for warehouse management (neither basic or advanced warehousing), and therefore does not require product picking to be registered before shipment.</span></span> <span data-ttu-id="d7a83-106">Você pode realizar esse procedimento em seus próprios dados ou na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="d7a83-106">You can run this procedure on your own data or in demo data company USMF.</span></span> <span data-ttu-id="d7a83-107">Em ambos os casos, antes de começar esta tarefa, crie uma ordem de venda para um produto inventariado com uma quantidade maior que 1.</span><span class="sxs-lookup"><span data-stu-id="d7a83-107">In both cases, before you start this task, create a sales order for an inventoried product with a quantity of greater than 1.</span></span> <span data-ttu-id="d7a83-108">Para evitar um erro de lançamento, você precisa verificar se a quantidade disponível do produto no site e o depósito que você selecionou na ordem abrangem a quantidade da ordem.</span><span class="sxs-lookup"><span data-stu-id="d7a83-108">To avoid a posting error, you need to check that the product's on-hand quantity in the site and warehouse that you’ve selected on the order covers the order quantity.</span></span>


## <a name="post-packing-slip-for-an-order"></a><span data-ttu-id="d7a83-109">Lançar guia de remessa para uma ordem</span><span class="sxs-lookup"><span data-stu-id="d7a83-109">Post packing slip for an order</span></span>
1. <span data-ttu-id="d7a83-110">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="d7a83-110">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="d7a83-111">Na lista, localize e selecione a ordem que você criou para essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="d7a83-111">In the list, find and select the order you have created for this task.</span></span>
3. <span data-ttu-id="d7a83-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d7a83-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d7a83-113">No Painel de Ação, clique em Separar e empacotar.</span><span class="sxs-lookup"><span data-stu-id="d7a83-113">On the Action Pane, click Pick and pack.</span></span>
5. <span data-ttu-id="d7a83-114">Clique em Postar guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="d7a83-114">Click Post packing slip.</span></span>
6. <span data-ttu-id="d7a83-115">Expanda e recolha a seção Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="d7a83-115">Expand or collapse the Parameters section.</span></span>
7. <span data-ttu-id="d7a83-116">No campo Quantidade, selecione 'Tudo'.</span><span class="sxs-lookup"><span data-stu-id="d7a83-116">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="d7a83-117">Outras opções incluem Entregar agora e Separado.</span><span class="sxs-lookup"><span data-stu-id="d7a83-117">Other options include Deliver now and Picked.</span></span> <span data-ttu-id="d7a83-118">Se a linha da ordem estiver pronta para ser parcialmente remetida e o campo Entregar agora na linha da ordem contiver uma quantidade, você selecionará Entregar agora.</span><span class="sxs-lookup"><span data-stu-id="d7a83-118">If the order line is to be shipped partially and the Deliver now field on the order line contains a quantity, you would select Deliver now.</span></span> <span data-ttu-id="d7a83-119">Se o fluxo de realizações da sua organização incluir a separação como um processo à parte que é gerenciado por e registrado com uma lista de separação, você selecionará Separado.</span><span class="sxs-lookup"><span data-stu-id="d7a83-119">If your organization's fulfillment flow includes picking as a separate process that is managed by and registered with a picking list, you would select Picked.</span></span>  
    * <span data-ttu-id="d7a83-120">Verifique se a opção Lançamento está definida como Sim.</span><span class="sxs-lookup"><span data-stu-id="d7a83-120">Check that the Posting option is set to Yes.</span></span>  
8. <span data-ttu-id="d7a83-121">Defina a opção Imprimir guia de remessa como Sim.</span><span class="sxs-lookup"><span data-stu-id="d7a83-121">Set the Print packing slip option to Yes.</span></span>
    * <span data-ttu-id="d7a83-122">A guia Visão geral contém uma lista de guias de remessa que serão geradas nesse lançamento.</span><span class="sxs-lookup"><span data-stu-id="d7a83-122">The Overview tab contains a list of packing slips to be generated in this posting.</span></span> <span data-ttu-id="d7a83-123">Se estiver remetendo uma ordem individual, normalmente haverá uma guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="d7a83-123">If you are shipping an individual order, there will typically be one packing slip.</span></span> <span data-ttu-id="d7a83-124">No entanto, se as linhas dessa ordem estiverem prontas para ser enviadas de sites diferentes, o lançamento será automaticamente dividido no número apropriado de documentos.</span><span class="sxs-lookup"><span data-stu-id="d7a83-124">However, if that order's lines are to be shipped from different sites, posting will automatically be split into the appropriate number of documents.</span></span> <span data-ttu-id="d7a83-125">Essa é uma condição obrigatória que não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="d7a83-125">This is a mandatory condition that cannot be changed.</span></span> <span data-ttu-id="d7a83-126">De modo semelhante, o lançamento também será dividido em vários documentos se as linhas da ordem estiverem prontas para ser enviadas a endereços de entrega diferentes, e a política de envio é definida para requerer divisão.</span><span class="sxs-lookup"><span data-stu-id="d7a83-126">Similarly, the posting will also be split into multiple documents if the order’s lines are to be shipped to different delivery addresses, and the shipping policy is set up to require a split.</span></span>  
9. <span data-ttu-id="d7a83-127">Na guia Linhas, selecione a linha para a linha de ordem que será remetida.</span><span class="sxs-lookup"><span data-stu-id="d7a83-127">On the Lines tab, select the row for the order line to be shipped.</span></span>
10. <span data-ttu-id="d7a83-128">No campo Atualizar, insira um número menor que a quantidade original.</span><span class="sxs-lookup"><span data-stu-id="d7a83-128">In the Update field, enter a number lower than the original quantity.</span></span>
11. <span data-ttu-id="d7a83-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d7a83-129">Click OK.</span></span>
12. <span data-ttu-id="d7a83-130">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="d7a83-130">Click Yes.</span></span>
13. <span data-ttu-id="d7a83-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d7a83-131">Close the page.</span></span>
14. <span data-ttu-id="d7a83-132">No Painel de Ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="d7a83-132">On the Action Pane, click Options.</span></span>
15. <span data-ttu-id="d7a83-133">Clique em Alterar exibição.</span><span class="sxs-lookup"><span data-stu-id="d7a83-133">Click Change view.</span></span>
16. <span data-ttu-id="d7a83-134">Clique em Exibição do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="d7a83-134">Click Header view.</span></span>
    * <span data-ttu-id="d7a83-135">Se todas as linhas na ordem foram completamente enviadas, o status da ordem muda de Aberto para Entregue.</span><span class="sxs-lookup"><span data-stu-id="d7a83-135">If all of the lines on the order have been fully shipped, the order status changes from Open to Delivered.</span></span>  
    * <span data-ttu-id="d7a83-136">Neste exemplo, a linha da ordem foi remetida parcialmente.</span><span class="sxs-lookup"><span data-stu-id="d7a83-136">In this example, the order line has been shipped partially.</span></span> <span data-ttu-id="d7a83-137">É por isso que o status da ordem permanece Aberto.</span><span class="sxs-lookup"><span data-stu-id="d7a83-137">This is why the order status remains Open.</span></span>     
    * <span data-ttu-id="d7a83-138">Se o campo Status do documento estiver definido como Guia de remessa, é porque pelo menos uma das linhas da ordem foi enviada.</span><span class="sxs-lookup"><span data-stu-id="d7a83-138">The Document status field is set to Packing slip because at least one of the order lines have been shipped.</span></span>  
17. <span data-ttu-id="d7a83-139">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="d7a83-139">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="d7a83-140">Clique em Quantidade da linha.</span><span class="sxs-lookup"><span data-stu-id="d7a83-140">Click Line quantity.</span></span>
19. <span data-ttu-id="d7a83-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d7a83-141">Close the page.</span></span>
20. <span data-ttu-id="d7a83-142">No Painel de Ação, clique em Separar e empacotar.</span><span class="sxs-lookup"><span data-stu-id="d7a83-142">On the Action Pane, click Pick and pack.</span></span>
21. <span data-ttu-id="d7a83-143">Clique em Guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="d7a83-143">Click Packing slip.</span></span>
    * <span data-ttu-id="d7a83-144">A página Diário de guias de remessa contém todos os documentos de guia de remessa que foram gerados para sua ordem.</span><span class="sxs-lookup"><span data-stu-id="d7a83-144">The Packing slip journal page contains all the packing slip documents that were generated for your order.</span></span> <span data-ttu-id="d7a83-145">Você pode revisar os detalhes de cada documento e imprimi-los, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d7a83-145">You can review details of each document and print them, if needed.</span></span>  


