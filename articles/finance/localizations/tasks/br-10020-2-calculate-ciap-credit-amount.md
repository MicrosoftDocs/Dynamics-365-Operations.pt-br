---
title: Calcular o valor de crédito CIAP (Brasil)
description: Cada mês, para cada estabelecimento fiscal, o valor de crédito de imposto é calculado para aquisições anteriores de ativo fixo de cada ativo fixo.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f6b4c1ea4d599c7c44f233cee09a0ab0c43e639
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183855"
---
# <a name="calculate-ciap-credit-amount-brazil"></a><span data-ttu-id="0db57-103">Calcular o valor de crédito CIAP (Brasil)</span><span class="sxs-lookup"><span data-stu-id="0db57-103">Calculate CIAP credit amount (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0db57-104">Cada mês, para cada estabelecimento fiscal, o valor de crédito de imposto é calculado para aquisições anteriores de ativo fixo de cada ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="0db57-104">Every month, for each fiscal establishment, the tax credit amount is calculated for past fixed asset acquisitions for each fixed asset.</span></span> <span data-ttu-id="0db57-105">O cálculo ocorre até que o número máximo de pagamentos de parcelas de crédito fiscal seja atingido, ou o ativo fixo não pertença à entidade legal.</span><span class="sxs-lookup"><span data-stu-id="0db57-105">This calculation occurs until the maximum number of tax credit installment payments is reached, or until the fixed asset no longer belongs to the legal entity.</span></span> <span data-ttu-id="0db57-106">Cada pagamento de parcela de crédito fiscal do ativo fixo é usado para criar uma nota fiscal de transferência ou apropriação de imposto que faz parte da apuração do imposto ICMS da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="0db57-106">Each fixed asset tax credit installment payment is used to create a tax fiscal document that is part of the ICMS tax assessment for the legal entity.</span></span> <span data-ttu-id="0db57-107">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="0db57-107">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="0db57-108">Vá para Livros fiscais > Comum > Período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="0db57-108">Go to Fiscal books > Common > Booking period.</span></span>
2. <span data-ttu-id="0db57-109">Clique em Criar novo período de escrituração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0db57-109">Click Create new booking period to open the drop dialog.</span></span>
3. <span data-ttu-id="0db57-110">No campo Estabelecimento fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0db57-110">In the Fiscal establishment field, enter or select a value.</span></span>
4. <span data-ttu-id="0db57-111">No campo Mês, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="0db57-111">In the Month field, select an option.</span></span>
5. <span data-ttu-id="0db57-112">No campo Ano, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0db57-112">In the Year field, enter a number.</span></span>
6. <span data-ttu-id="0db57-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0db57-113">Click OK.</span></span>
7. <span data-ttu-id="0db57-114">Clique em Sincronizar.</span><span class="sxs-lookup"><span data-stu-id="0db57-114">Click Sync.</span></span>
8. <span data-ttu-id="0db57-115">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0db57-115">Click OK.</span></span>
9. <span data-ttu-id="0db57-116">Clicar em ICMS.</span><span class="sxs-lookup"><span data-stu-id="0db57-116">Click ICMS.</span></span>
10. <span data-ttu-id="0db57-117">Clique em Apuração de imposto ICMS para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0db57-117">Click ICMS tax assessment to open the drop dialog.</span></span>
11. <span data-ttu-id="0db57-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0db57-118">Click OK.</span></span>
12. <span data-ttu-id="0db57-119">Clique em Apuração do CIAP.</span><span class="sxs-lookup"><span data-stu-id="0db57-119">Click CIAP assessment.</span></span>
13. <span data-ttu-id="0db57-120">Clique em Calcular fator do CIAP.</span><span class="sxs-lookup"><span data-stu-id="0db57-120">Click Calculate CIAP factor.</span></span>
14. <span data-ttu-id="0db57-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0db57-121">Close the page.</span></span>
15. <span data-ttu-id="0db57-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0db57-122">Close the page.</span></span>
16. <span data-ttu-id="0db57-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0db57-123">Close the page.</span></span>
17. <span data-ttu-id="0db57-124">Vá para Contabilidade > Entradas de diário > Todas as notas fiscais de transferência ou apropriação de imposto.</span><span class="sxs-lookup"><span data-stu-id="0db57-124">Go to General ledger > Journal entries > All tax fiscal documents.</span></span>
18. <span data-ttu-id="0db57-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0db57-125">Click New.</span></span>
19. <span data-ttu-id="0db57-126">No campo Tipo de documento fiscal de transferência ou apropriação de imposto, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="0db57-126">In the Tax fiscal document type field, select an option.</span></span>
20. <span data-ttu-id="0db57-127">No campo ID do estabelecimento fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0db57-127">In the Fiscal establishment ID field, enter or select a value.</span></span>
21. <span data-ttu-id="0db57-128">No campo Número de conta, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0db57-128">In the Account number field, enter or select a value.</span></span>
22. <span data-ttu-id="0db57-129">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="0db57-129">In the Date field, enter a date.</span></span>
23. <span data-ttu-id="0db57-130">No campo Nota fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0db57-130">In the Fiscal document type field, enter or select a value.</span></span>
24. <span data-ttu-id="0db57-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0db57-131">Click Save.</span></span>
25. <span data-ttu-id="0db57-132">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="0db57-132">Click Add line.</span></span>
26. <span data-ttu-id="0db57-133">No campo Descrição do item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0db57-133">In the Item description field, type a value.</span></span>
27. <span data-ttu-id="0db57-134">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0db57-134">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="0db57-135">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0db57-135">In the CFOP field, enter or select a value.</span></span>
29. <span data-ttu-id="0db57-136">No campo Código de impostos sobre vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0db57-136">In the Sales tax code field, enter or select a value.</span></span>
30. <span data-ttu-id="0db57-137">No campo Valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0db57-137">In the Amount field, enter a number.</span></span>
31. <span data-ttu-id="0db57-138">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="0db57-138">Click Post.</span></span>
32. <span data-ttu-id="0db57-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0db57-139">Click OK.</span></span>
33. <span data-ttu-id="0db57-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0db57-140">Close the page.</span></span>
34. <span data-ttu-id="0db57-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0db57-141">Close the page.</span></span>
35. <span data-ttu-id="0db57-142">Vá para Contas a receber > Notas fiscais > Notas fiscais eletrônicas > Exportar/importar processo de NF-e.</span><span class="sxs-lookup"><span data-stu-id="0db57-142">Go to Accounts receivable > Fiscal documents > Electronic fiscal documents > Export/import NF-e process.</span></span>
36. <span data-ttu-id="0db57-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0db57-143">Click OK.</span></span>
37. <span data-ttu-id="0db57-144">Vá para Livros fiscais > Comum > Período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="0db57-144">Go to Fiscal books > Common > Booking period.</span></span>
38. <span data-ttu-id="0db57-145">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0db57-145">In the list, mark the selected row.</span></span>
39. <span data-ttu-id="0db57-146">Clique em Sincronizar.</span><span class="sxs-lookup"><span data-stu-id="0db57-146">Click Sync.</span></span>
40. <span data-ttu-id="0db57-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0db57-147">Click OK.</span></span>
41. <span data-ttu-id="0db57-148">Clicar em ICMS.</span><span class="sxs-lookup"><span data-stu-id="0db57-148">Click ICMS.</span></span>
42. <span data-ttu-id="0db57-149">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0db57-149">Close the page.</span></span>
43. <span data-ttu-id="0db57-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0db57-150">Close the page.</span></span>
