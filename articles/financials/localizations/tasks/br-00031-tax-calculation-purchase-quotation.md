---
title: Calcular impostos em cotações de compra (Brasil)
description: Você pode criar uma solicitação de cotação (RFQ) de compra e, ao inserir a resposta do fornecedor, você pode fornecer informações fiscais aplicáveis.
author: sndray
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b4968ae2e02993f730c3d13b28c9287a300a0a0
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852777"
---
# <a name="calculate-tax-on-purchase-quotations-brazil"></a><span data-ttu-id="2e00e-103">Calcular impostos em cotações de compra (Brasil)</span><span class="sxs-lookup"><span data-stu-id="2e00e-103">Calculate tax on purchase quotations (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e00e-104">Você pode criar uma solicitação de cotação (RFQ) de compra e, ao inserir a resposta do fornecedor, você pode fornecer informações fiscais aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="2e00e-104">You can create a purchase request for quotation (RFQ), and when you enter the vendor reply, you can enter applicable fiscal information.</span></span> <span data-ttu-id="2e00e-105">Quando a RFQ é aceita, cria-se uma ordem de compra com as mesmas informações fiscais inseridas no RFQ.</span><span class="sxs-lookup"><span data-stu-id="2e00e-105">When the RFQ is accepted, a purchase order is created that has the same fiscal information that is entered in the RFQ.</span></span> <span data-ttu-id="2e00e-106">Este registro usa a empresa de dados de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="2e00e-106">This recording uses the BRMF demo company.</span></span>

1. <span data-ttu-id="2e00e-107">Vá para Aquisição e fornecimento > Solicitações de cotações > Todas as solicitações de cotações.</span><span class="sxs-lookup"><span data-stu-id="2e00e-107">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="2e00e-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2e00e-108">Click New.</span></span>
3. <span data-ttu-id="2e00e-109">No campo Título do documento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2e00e-109">In the Document title field, type a value.</span></span>
4. <span data-ttu-id="2e00e-110">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2e00e-110">In the Site field, enter or select a value.</span></span>
5. <span data-ttu-id="2e00e-111">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2e00e-111">In the Warehouse field, enter or select a value.</span></span>
6. <span data-ttu-id="2e00e-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2e00e-112">Click OK.</span></span>
7. <span data-ttu-id="2e00e-113">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2e00e-113">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="2e00e-114">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2e00e-114">In the Item number field, enter or select a value.</span></span>
9. <span data-ttu-id="2e00e-115">No campo Linhas ou cabeçalho, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="2e00e-115">In the Lines or header field, select an option.</span></span>
10. <span data-ttu-id="2e00e-116">Expandir a seção Fornecedor.</span><span class="sxs-lookup"><span data-stu-id="2e00e-116">Expand the Vendor section.</span></span>
11. <span data-ttu-id="2e00e-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2e00e-117">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="2e00e-118">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2e00e-118">In the Vendor account field, enter or select a value.</span></span>
13. <span data-ttu-id="2e00e-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2e00e-119">Click Save.</span></span>
14. <span data-ttu-id="2e00e-120">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="2e00e-120">Click Send.</span></span>
15. <span data-ttu-id="2e00e-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2e00e-121">Click OK.</span></span>
16. <span data-ttu-id="2e00e-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2e00e-122">Close the page.</span></span>
17. <span data-ttu-id="2e00e-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2e00e-123">Close the page.</span></span>
18. <span data-ttu-id="2e00e-124">Vá para Compras > Solicitações de cotações > Acompanhamento de solicitações de cotações > Resposta da solicitação de cotação.</span><span class="sxs-lookup"><span data-stu-id="2e00e-124">Go to Procurement and sourcing > Requests for quotations > Request for quotations follow-up > Request for quotation replies.</span></span>
19. <span data-ttu-id="2e00e-125">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2e00e-125">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="2e00e-126">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="2e00e-126">Click Edit.</span></span>
21. <span data-ttu-id="2e00e-127">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="2e00e-127">In the Quantity field, enter a number.</span></span>
22. <span data-ttu-id="2e00e-128">No campo Unidade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2e00e-128">In the Unit field, enter or select a value.</span></span>
23. <span data-ttu-id="2e00e-129">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="2e00e-129">In the Unit price field, enter a number.</span></span>
24. <span data-ttu-id="2e00e-130">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="2e00e-130">Expand the Line details section.</span></span>
25. <span data-ttu-id="2e00e-131">Clique na guia Informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="2e00e-131">Click the Fiscal information tab.</span></span>
26. <span data-ttu-id="2e00e-132">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2e00e-132">In the CFOP field, enter or select a value.</span></span>
27. <span data-ttu-id="2e00e-133">Clique na guia Outros.</span><span class="sxs-lookup"><span data-stu-id="2e00e-133">Click the Other tab.</span></span>
28. <span data-ttu-id="2e00e-134">Clique em Totais.</span><span class="sxs-lookup"><span data-stu-id="2e00e-134">Click Totals.</span></span>
29. <span data-ttu-id="2e00e-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2e00e-135">Click OK.</span></span>
30. <span data-ttu-id="2e00e-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2e00e-136">Click Save.</span></span>
31. <span data-ttu-id="2e00e-137">Clique em Aceitar.</span><span class="sxs-lookup"><span data-stu-id="2e00e-137">Click Accept.</span></span>
32. <span data-ttu-id="2e00e-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2e00e-138">Click OK.</span></span>
33. <span data-ttu-id="2e00e-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2e00e-139">Close the page.</span></span>
34. <span data-ttu-id="2e00e-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2e00e-140">Close the page.</span></span>

