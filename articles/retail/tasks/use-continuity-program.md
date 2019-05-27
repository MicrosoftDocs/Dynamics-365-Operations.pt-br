---
title: Usando programas de continuidade
description: Este procedimento aborda a venda de um programa de continuidade e o processamento relacionados às ordens de venda.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45bd4a3cc9f9b03c713d33638d6dc93aa696c581
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564892"
---
# <a name="using-continuity-program"></a><span data-ttu-id="36e82-103">Usando programas de continuidade</span><span class="sxs-lookup"><span data-stu-id="36e82-103">Using continuity program</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="36e82-104">Este procedimento aborda a venda de um programa de continuidade e o processamento relacionados às ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="36e82-104">This procedure walks through selling a continuity program and processing related sales orders.</span></span> <span data-ttu-id="36e82-105">Para concluir o procedimento, o usuário precisa estar configurado como usuário de call center.</span><span class="sxs-lookup"><span data-stu-id="36e82-105">To complete this procedure, the user has to be set up as a call center user.</span></span> <span data-ttu-id="36e82-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="36e82-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="36e82-107">Vá para Varejo e comércio > Clientes > SAC.</span><span class="sxs-lookup"><span data-stu-id="36e82-107">Go to Retail and commerce > Customers > Customer service.</span></span>
2. <span data-ttu-id="36e82-108">No campo SearchText, digite "Karen" e depois pressione a tecla Tab.</span><span class="sxs-lookup"><span data-stu-id="36e82-108">In the SearchText field, type 'Karen' and then press the Tab key.</span></span>
    * <span data-ttu-id="36e82-109">A caixa de diálogo de pesquisa avançada deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="36e82-109">The advanced search dialog should pop up.</span></span> <span data-ttu-id="36e82-110">Caso isso não ocorra, clique em Pesquisa à direita desse campo.</span><span class="sxs-lookup"><span data-stu-id="36e82-110">If it doesn't, click Search to the right of this field.</span></span>  
3. <span data-ttu-id="36e82-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="36e82-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="36e82-112">Deve haver apenas uma linha exibindo Karen Berg.</span><span class="sxs-lookup"><span data-stu-id="36e82-112">There should be only one row with Karen Berg showing.</span></span> <span data-ttu-id="36e82-113">Selecione a linha clicando na coluna de marca de seleção na extremidade esquerda da grade.</span><span class="sxs-lookup"><span data-stu-id="36e82-113">Select the row by clicking on the checkmark column on the far left of the grid.</span></span>  
4. <span data-ttu-id="36e82-114">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="36e82-114">Click Select.</span></span>
5. <span data-ttu-id="36e82-115">Clique em Nova ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="36e82-115">Click New sales order.</span></span>
    * <span data-ttu-id="36e82-116">É recomendável anotar o número da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="36e82-116">It's a good idea to note the sales order number.</span></span> <span data-ttu-id="36e82-117">Você precisará dele posteriormente neste procedimento.</span><span class="sxs-lookup"><span data-stu-id="36e82-117">You'll need it later in this procedure.</span></span>  
6. <span data-ttu-id="36e82-118">No campo Número de item, digite "88000" e depois pressione a tecla Tab.</span><span class="sxs-lookup"><span data-stu-id="36e82-118">In the Item number field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="36e82-119">Trata-se de um item de continuidade nos dados de demonstração da USRT.</span><span class="sxs-lookup"><span data-stu-id="36e82-119">This is a continuity item in the USRT demo data.</span></span>  
7. <span data-ttu-id="36e82-120">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="36e82-120">Click Complete.</span></span>
8. <span data-ttu-id="36e82-121">No campo Forma de pagamento, insira "Visa".</span><span class="sxs-lookup"><span data-stu-id="36e82-121">In the Payment method field, enter 'Visa'.</span></span>
9. <span data-ttu-id="36e82-122">Clique em Adicionar cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="36e82-122">Click Add credit card.</span></span>
    * <span data-ttu-id="36e82-123">Insira as informações de cartão de crédito necessárias nesta página.</span><span class="sxs-lookup"><span data-stu-id="36e82-123">Enter the required credit card information on this page.</span></span>  
10. <span data-ttu-id="36e82-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="36e82-124">Click OK.</span></span>
11. <span data-ttu-id="36e82-125">Expandir a seção Pagamento.</span><span class="sxs-lookup"><span data-stu-id="36e82-125">Expand the Payment section.</span></span>
    * <span data-ttu-id="36e82-126">Para enviar uma ordem de call center, os pagamentos precisam ser inseridos para a ordem.</span><span class="sxs-lookup"><span data-stu-id="36e82-126">To submit a call center order, payments have to be entered for the order.</span></span>  
12. <span data-ttu-id="36e82-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="36e82-127">Click OK.</span></span>
13. <span data-ttu-id="36e82-128">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="36e82-128">Click Submit.</span></span>
    * <span data-ttu-id="36e82-129">Você acabou de criar uma ordem de continuidade.</span><span class="sxs-lookup"><span data-stu-id="36e82-129">You're done creating a new continuity order.</span></span> <span data-ttu-id="36e82-130">Em seguida, você executará dois processos de lote que serão usados para processar as ordens de continuidade.</span><span class="sxs-lookup"><span data-stu-id="36e82-130">Next, you'll run two batch processes that are used to process the continuity orders.</span></span>  
14. <span data-ttu-id="36e82-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="36e82-131">Close the page.</span></span>
15. <span data-ttu-id="36e82-132">Vá para Varejo e comércio > Continuidade > Processar pagamentos de continuidade.</span><span class="sxs-lookup"><span data-stu-id="36e82-132">Go to Retail and commerce > Continuity > Process continuity payments.</span></span>
16. <span data-ttu-id="36e82-133">No campo Item de continuidade, digite "88000" e depois pressione a tecla Tab.</span><span class="sxs-lookup"><span data-stu-id="36e82-133">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
17. <span data-ttu-id="36e82-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="36e82-134">Click OK.</span></span>
18. <span data-ttu-id="36e82-135">Vá para Varejo e comércio > Continuidade > Criar ordens filho de continuidade.</span><span class="sxs-lookup"><span data-stu-id="36e82-135">Go to Retail and commerce > Continuity > Create continuity child orders.</span></span>
    * <span data-ttu-id="36e82-136">Esse processo criará ordens de venda com base nas configurações dos seus programas de continuidade.</span><span class="sxs-lookup"><span data-stu-id="36e82-136">This process will create new sales orders based on the settings of your continuity programs.</span></span>  
19. <span data-ttu-id="36e82-137">No campo Item de continuidade, digite "88000" e depois pressione a tecla Tab.</span><span class="sxs-lookup"><span data-stu-id="36e82-137">In the Continuity item field, type '88000' and then press the Tab key.</span></span>
    * <span data-ttu-id="36e82-138">O item "88000" é um item de continuidade nos dados de demonstração da USRT.</span><span class="sxs-lookup"><span data-stu-id="36e82-138">Item '88000' is a continuity item in the USRT demo data.</span></span>  
20. <span data-ttu-id="36e82-139">No campo Ordem de venda, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="36e82-139">In the Sales order field, enter or select a value.</span></span>
    * <span data-ttu-id="36e82-140">Insira o número da ordem de venda que você anotou anteriormente no procedimento.</span><span class="sxs-lookup"><span data-stu-id="36e82-140">Enter the sales order number that you noted earlier in the procedure.</span></span> <span data-ttu-id="36e82-141">Isso reduzirá o tempo de processamento ao mínimo para este procedimento.</span><span class="sxs-lookup"><span data-stu-id="36e82-141">This will keep the processing time to a minimal for this procedure.</span></span> <span data-ttu-id="36e82-142">O campo Ordem de venda é opcional - você pode processar todas as ordens de qualquer programa.</span><span class="sxs-lookup"><span data-stu-id="36e82-142">The Sales order field field is optional--you could process all orders for any one program.</span></span>  
21. <span data-ttu-id="36e82-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="36e82-143">Click OK.</span></span>

