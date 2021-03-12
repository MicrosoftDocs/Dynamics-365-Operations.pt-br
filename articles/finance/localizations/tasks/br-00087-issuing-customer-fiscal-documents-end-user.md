---
title: Emitir notas fiscais para clientes (para usuários finais) (Brasil)
description: É possível emitir uma nota fiscal a um cliente que comprou mercadorias do estabelecimento fiscal.
author: sndray
manager: AnnBe
ms.date: 06/24/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d9d68c2decf79b17f3510240a1000b6de50ef44
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000358"
---
# <a name="issue-customer-fiscal-documents-for-end-users-brazil"></a><span data-ttu-id="4f654-103">Emitir notas fiscais para clientes (para usuários finais) (Brasil)</span><span class="sxs-lookup"><span data-stu-id="4f654-103">Issue customer fiscal documents (for end users) (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4f654-104">É possível emitir uma nota fiscal a um cliente que comprou mercadorias do estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="4f654-104">You can issue a fiscal document to a customer who bought goods from the fiscal establishment.</span></span> <span data-ttu-id="4f654-105">O cálculo do valor base do imposto ICMS considera o valor do imposto IPI.</span><span class="sxs-lookup"><span data-stu-id="4f654-105">The calculation of the ICMS tax base amount considers the IPI tax amount.</span></span> <span data-ttu-id="4f654-106">Este registro usa a empresa de dados de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="4f654-106">This recording uses the BRMF demo company.</span></span>

1. <span data-ttu-id="4f654-107">Ir para Contas recebíveis > Clientes > Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="4f654-107">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="4f654-108">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="4f654-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4f654-109">Por exemplo, no campo Conta, filtre com um valor de "BRMF-000004".</span><span class="sxs-lookup"><span data-stu-id="4f654-109">For example, filter on the Account field with a value of 'BRMF-000004'.</span></span>
3. <span data-ttu-id="4f654-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4f654-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4f654-111">Expanda a seção Informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="4f654-111">Expand the Fiscal information section.</span></span>
5. <span data-ttu-id="4f654-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="4f654-112">Click Edit.</span></span>
6. <span data-ttu-id="4f654-113">Selecione Sim no campo Usuário final.</span><span class="sxs-lookup"><span data-stu-id="4f654-113">Select Yes in the Final user field.</span></span>
7. <span data-ttu-id="4f654-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4f654-114">Click Save.</span></span>
8. <span data-ttu-id="4f654-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4f654-115">Close the page.</span></span>
9. <span data-ttu-id="4f654-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4f654-116">Close the page.</span></span>
10. <span data-ttu-id="4f654-117">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="4f654-117">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
11. <span data-ttu-id="4f654-118">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="4f654-118">Click New.</span></span>
12. <span data-ttu-id="4f654-119">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4f654-119">In the Customer account field, enter or select a value.</span></span>
13. <span data-ttu-id="4f654-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4f654-120">Click OK.</span></span>
14. <span data-ttu-id="4f654-121">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="4f654-121">Click Add line.</span></span>
15. <span data-ttu-id="4f654-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4f654-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="4f654-123">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4f654-123">In the Item number field, enter or select a value.</span></span>
17. <span data-ttu-id="4f654-124">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="4f654-124">In the Quantity field, enter a number.</span></span>
18. <span data-ttu-id="4f654-125">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4f654-125">In the Site field, enter or select a value.</span></span>
19. <span data-ttu-id="4f654-126">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4f654-126">In the Warehouse field, enter or select a value.</span></span>
20. <span data-ttu-id="4f654-127">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4f654-127">In the CFOP field, enter or select a value.</span></span>
21. <span data-ttu-id="4f654-128">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="4f654-128">Expand the Line details section.</span></span>
22. <span data-ttu-id="4f654-129">Clique na guia Informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="4f654-129">Click the Fiscal information tab.</span></span>
23. <span data-ttu-id="4f654-130">No campo Nota fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4f654-130">In the Fiscal document type field, enter or select a value.</span></span>
24. <span data-ttu-id="4f654-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4f654-131">Click Save.</span></span>
25. <span data-ttu-id="4f654-132">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="4f654-132">Click Invoice.</span></span>
26. <span data-ttu-id="4f654-133">No campo Quantidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="4f654-133">In the Quantity field, select an option.</span></span>
27. <span data-ttu-id="4f654-134">Selecione Sim no campo Imprimir fatura.</span><span class="sxs-lookup"><span data-stu-id="4f654-134">Select Yes in the Print invoice field.</span></span>
28. <span data-ttu-id="4f654-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4f654-135">Click OK.</span></span>
29. <span data-ttu-id="4f654-136">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="4f654-136">Click Yes.</span></span>
30. <span data-ttu-id="4f654-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4f654-137">Close the page.</span></span>
31. <span data-ttu-id="4f654-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4f654-138">Close the page.</span></span>
32. <span data-ttu-id="4f654-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4f654-139">Close the page.</span></span>
33. <span data-ttu-id="4f654-140">Vá para Contas a receber > Notas fiscais > Notas fiscais eletrônicas > Exportar/importar processo de NF-e.</span><span class="sxs-lookup"><span data-stu-id="4f654-140">Go to Accounts receivable > Fiscal documents > Electronic fiscal documents > Export/import NF-e process.</span></span>
34. <span data-ttu-id="4f654-141">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4f654-141">Click OK.</span></span>

