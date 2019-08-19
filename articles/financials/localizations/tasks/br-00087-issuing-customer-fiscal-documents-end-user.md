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
ms.search.scope: Operations
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4fd968ac18bd0e2e4da06ba758cc70ddaaa203a9
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852764"
---
# <a name="issue-customer-fiscal-documents-for-end-users-brazil"></a><span data-ttu-id="806ee-103">Emitir notas fiscais para clientes (para usuários finais) (Brasil)</span><span class="sxs-lookup"><span data-stu-id="806ee-103">Issue customer fiscal documents (for end users) (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="806ee-104">É possível emitir uma nota fiscal a um cliente que comprou mercadorias do estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="806ee-104">You can issue a fiscal document to a customer who bought goods from the fiscal establishment.</span></span> <span data-ttu-id="806ee-105">O cálculo do valor base do imposto ICMS considera o valor do imposto IPI.</span><span class="sxs-lookup"><span data-stu-id="806ee-105">The calculation of the ICMS tax base amount considers the IPI tax amount.</span></span> <span data-ttu-id="806ee-106">Este registro usa a empresa de dados de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="806ee-106">This recording uses the BRMF demo company.</span></span>

1. <span data-ttu-id="806ee-107">Ir para Contas recebíveis > Clientes > Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="806ee-107">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="806ee-108">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="806ee-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="806ee-109">Por exemplo, no campo Conta, filtre com um valor de "BRMF-000004".</span><span class="sxs-lookup"><span data-stu-id="806ee-109">For example, filter on the Account field with a value of 'BRMF-000004'.</span></span>
3. <span data-ttu-id="806ee-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="806ee-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="806ee-111">Expanda a seção Informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="806ee-111">Expand the Fiscal information section.</span></span>
5. <span data-ttu-id="806ee-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="806ee-112">Click Edit.</span></span>
6. <span data-ttu-id="806ee-113">Selecione Sim no campo Usuário final.</span><span class="sxs-lookup"><span data-stu-id="806ee-113">Select Yes in the Final user field.</span></span>
7. <span data-ttu-id="806ee-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="806ee-114">Click Save.</span></span>
8. <span data-ttu-id="806ee-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="806ee-115">Close the page.</span></span>
9. <span data-ttu-id="806ee-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="806ee-116">Close the page.</span></span>
10. <span data-ttu-id="806ee-117">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="806ee-117">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
11. <span data-ttu-id="806ee-118">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="806ee-118">Click New.</span></span>
12. <span data-ttu-id="806ee-119">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="806ee-119">In the Customer account field, enter or select a value.</span></span>
13. <span data-ttu-id="806ee-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="806ee-120">Click OK.</span></span>
14. <span data-ttu-id="806ee-121">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="806ee-121">Click Add line.</span></span>
15. <span data-ttu-id="806ee-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="806ee-122">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="806ee-123">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="806ee-123">In the Item number field, enter or select a value.</span></span>
17. <span data-ttu-id="806ee-124">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="806ee-124">In the Quantity field, enter a number.</span></span>
18. <span data-ttu-id="806ee-125">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="806ee-125">In the Site field, enter or select a value.</span></span>
19. <span data-ttu-id="806ee-126">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="806ee-126">In the Warehouse field, enter or select a value.</span></span>
20. <span data-ttu-id="806ee-127">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="806ee-127">In the CFOP field, enter or select a value.</span></span>
21. <span data-ttu-id="806ee-128">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="806ee-128">Expand the Line details section.</span></span>
22. <span data-ttu-id="806ee-129">Clique na guia Informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="806ee-129">Click the Fiscal information tab.</span></span>
23. <span data-ttu-id="806ee-130">No campo Nota fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="806ee-130">In the Fiscal document type field, enter or select a value.</span></span>
24. <span data-ttu-id="806ee-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="806ee-131">Click Save.</span></span>
25. <span data-ttu-id="806ee-132">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="806ee-132">Click Invoice.</span></span>
26. <span data-ttu-id="806ee-133">No campo Quantidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="806ee-133">In the Quantity field, select an option.</span></span>
27. <span data-ttu-id="806ee-134">Selecione Sim no campo Imprimir fatura.</span><span class="sxs-lookup"><span data-stu-id="806ee-134">Select Yes in the Print invoice field.</span></span>
28. <span data-ttu-id="806ee-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="806ee-135">Click OK.</span></span>
29. <span data-ttu-id="806ee-136">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="806ee-136">Click Yes.</span></span>
30. <span data-ttu-id="806ee-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="806ee-137">Close the page.</span></span>
31. <span data-ttu-id="806ee-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="806ee-138">Close the page.</span></span>
32. <span data-ttu-id="806ee-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="806ee-139">Close the page.</span></span>
33. <span data-ttu-id="806ee-140">Vá para Contas a receber > Notas fiscais > Notas fiscais eletrônicas > Exportar/importar processo de NF-e.</span><span class="sxs-lookup"><span data-stu-id="806ee-140">Go to Accounts receivable > Fiscal documents > Electronic fiscal documents > Export/import NF-e process.</span></span>
34. <span data-ttu-id="806ee-141">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="806ee-141">Click OK.</span></span>

