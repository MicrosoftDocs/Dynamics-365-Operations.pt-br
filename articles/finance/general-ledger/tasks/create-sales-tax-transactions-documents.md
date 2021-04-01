---
title: Criar transações de imposto em documentos
description: Os impostos sobre vendas nos documentos são calculados fornecendo um grupo de impostos sobre vendas e um grupo de impostos sobre vendas de itens nas linhas do documento.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3cc70915902863d85aa75af7f4c03e5b83c7cb22
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240801"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="07ffa-103">Criar transações de imposto em documentos</span><span class="sxs-lookup"><span data-stu-id="07ffa-103">Create sales tax transactions on documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="07ffa-104">Os impostos sobre vendas nos documentos são calculados fornecendo um grupo de impostos sobre vendas e um grupo de impostos sobre vendas de itens nas linhas do documento.</span><span class="sxs-lookup"><span data-stu-id="07ffa-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="07ffa-105">Esses padrões derivam dos dados mestre, mas podem ser alterados manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="07ffa-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="07ffa-106">Os impostos sobre vendas calculado podem ser feitos em um nível de linha e do documento.</span><span class="sxs-lookup"><span data-stu-id="07ffa-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="07ffa-107">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="07ffa-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="07ffa-108">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="07ffa-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="07ffa-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="07ffa-109">Click New.</span></span>
3. <span data-ttu-id="07ffa-110">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="07ffa-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="07ffa-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="07ffa-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="07ffa-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="07ffa-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="07ffa-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="07ffa-113">Click OK.</span></span>
7. <span data-ttu-id="07ffa-114">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="07ffa-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="07ffa-115">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="07ffa-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="07ffa-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="07ffa-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="07ffa-117">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="07ffa-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="07ffa-118">Expandir ou recolher a seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="07ffa-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="07ffa-119">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="07ffa-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="07ffa-120">No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="07ffa-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="07ffa-121">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="07ffa-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="07ffa-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="07ffa-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="07ffa-123">Clique em Financeiros.</span><span class="sxs-lookup"><span data-stu-id="07ffa-123">Click Financials.</span></span>
17. <span data-ttu-id="07ffa-124">Clique em Impostos.</span><span class="sxs-lookup"><span data-stu-id="07ffa-124">Click Sales tax.</span></span>
18. <span data-ttu-id="07ffa-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="07ffa-125">Click OK.</span></span>
19. <span data-ttu-id="07ffa-126">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="07ffa-126">Click Add line.</span></span>
20. <span data-ttu-id="07ffa-127">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="07ffa-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="07ffa-128">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="07ffa-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="07ffa-129">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="07ffa-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="07ffa-130">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="07ffa-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="07ffa-131">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="07ffa-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="07ffa-132">No campo Grupo de imposto do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="07ffa-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="07ffa-133">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="07ffa-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="07ffa-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="07ffa-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="07ffa-135">No Painel de Ação, clique em Vender.</span><span class="sxs-lookup"><span data-stu-id="07ffa-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="07ffa-136">Clique em Impostos.</span><span class="sxs-lookup"><span data-stu-id="07ffa-136">Click Sales tax.</span></span>
30. <span data-ttu-id="07ffa-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="07ffa-137">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]