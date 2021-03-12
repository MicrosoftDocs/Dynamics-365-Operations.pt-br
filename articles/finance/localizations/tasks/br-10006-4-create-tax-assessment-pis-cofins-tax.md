---
title: Criar uma apuração de imposto - PIS e COFINS (Brasil)
description: Você pode criar uma avaliação de imposto para contribuições de PIS/COFINS por um período de escrituração específico.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a0c612da382c03f8295418cae56dfbab22bdf14
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997462"
---
# <a name="create-a-tax-assessment---pis-and-cofins-tax-brazil"></a><span data-ttu-id="0b5a0-103">Criar uma apuração de imposto - PIS e COFINS (Brasil)</span><span class="sxs-lookup"><span data-stu-id="0b5a0-103">Create a tax assessment - PIS and COFINS tax (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0b5a0-104">Você pode criar uma avaliação de imposto para contribuições de PIS/COFINS por um período de escrituração específico.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-104">You can create the tax assessment for PIS/COFINS contributions for a given booking period.</span></span> <span data-ttu-id="0b5a0-105">A avaliação de imposto considera o valor da contribuição de PIS/COFINS para recuperar e o valor da contribuição de PIS/COFINS para pagar os documentos fiscais.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-105">The tax assessment considers the PIS/COFINS contribution amount to recover and the PIS/COFINS contribution amount to pay from the fiscal documents.</span></span> <span data-ttu-id="0b5a0-106">Para o valor devido após a apuração de imposto, crie o pagamento de impostos.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-106">For the  amount that is due after the tax assessment, you can create the tax payment.</span></span> <span data-ttu-id="0b5a0-107">Este registro usa a empresa de dados de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-107">This recording uses the BRMF demo company.</span></span>

1. <span data-ttu-id="0b5a0-108">Vá para Livros fiscais > Comum > Período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-108">Go to Fiscal books > Common > Booking period.</span></span>
2. <span data-ttu-id="0b5a0-109">Clique em Criar novo período de escrituração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-109">Click Create new booking period to open the drop dialog.</span></span>
3. <span data-ttu-id="0b5a0-110">No campo Estabelecimento fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-110">In the Fiscal establishment field, enter or select a value.</span></span>
4. <span data-ttu-id="0b5a0-111">No campo Mês, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-111">In the Month field, select an option.</span></span>
5. <span data-ttu-id="0b5a0-112">No campo Ano, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-112">In the Year field, enter a number.</span></span>
6. <span data-ttu-id="0b5a0-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-113">Click OK.</span></span>
7. <span data-ttu-id="0b5a0-114">Clique em Sincronizar.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-114">Click Sync.</span></span>
8. <span data-ttu-id="0b5a0-115">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-115">Click OK.</span></span>
9. <span data-ttu-id="0b5a0-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-116">Close the page.</span></span>
10. <span data-ttu-id="0b5a0-117">Vá para Livros fiscais > Comum > Apuração de imposto > PIS-COFINS.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-117">Go to Fiscal books > Common > Tax assessment > PIS-COFINS.</span></span>
11. <span data-ttu-id="0b5a0-118">Clique em Apuração de imposto PIS e COFINS para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-118">Click PIS and COFINS tax assessment to open the drop dialog.</span></span>
12. <span data-ttu-id="0b5a0-119">No campo Período de escrituração, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-119">In the Booking period field, enter or select a value.</span></span>
13. <span data-ttu-id="0b5a0-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-120">Click OK.</span></span>
14. <span data-ttu-id="0b5a0-121">Clique em Pagamento de imposto.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-121">Click Tax payment.</span></span>
15. <span data-ttu-id="0b5a0-122">Clique em Criar a partir da apuração.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-122">Click Create from assessment.</span></span>
16. <span data-ttu-id="0b5a0-123">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-123">Click Edit.</span></span>
17. <span data-ttu-id="0b5a0-124">No campo Código da Receita, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-124">In the Receita Code field, type a value.</span></span>
18. <span data-ttu-id="0b5a0-125">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="0b5a0-126">No campo Data de vencimento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-126">In the Due date field, enter a date.</span></span>
20. <span data-ttu-id="0b5a0-127">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-127">Expand the General section.</span></span>
21. <span data-ttu-id="0b5a0-128">No campo Autoridade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-128">In the Authority field, enter or select a value.</span></span>
22. <span data-ttu-id="0b5a0-129">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-129">Click Post.</span></span>
23. <span data-ttu-id="0b5a0-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-130">Close the page.</span></span>
24. <span data-ttu-id="0b5a0-131">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-131">In the list, find and select the desired record.</span></span>
25. <span data-ttu-id="0b5a0-132">Clique em Pagamento de imposto.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-132">Click Tax payment.</span></span>
26. <span data-ttu-id="0b5a0-133">Clique em Criar a partir da apuração.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-133">Click Create from assessment.</span></span>
27. <span data-ttu-id="0b5a0-134">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-134">Click Edit.</span></span>
28. <span data-ttu-id="0b5a0-135">No campo Código da Receita, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-135">In the Receita Code field, type a value.</span></span>
29. <span data-ttu-id="0b5a0-136">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-136">In the list, mark the selected row.</span></span>
30. <span data-ttu-id="0b5a0-137">No campo Data de vencimento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-137">In the Due date field, enter a date.</span></span>
31. <span data-ttu-id="0b5a0-138">No campo Autoridade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-138">In the Authority field, enter or select a value.</span></span>
32. <span data-ttu-id="0b5a0-139">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-139">Click Post.</span></span>
33. <span data-ttu-id="0b5a0-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-140">Close the page.</span></span>
34. <span data-ttu-id="0b5a0-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0b5a0-141">Close the page.</span></span>

