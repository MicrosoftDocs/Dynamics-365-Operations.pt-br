---
title: Impostos retidos na fonte no Brasil
description: Este procedimento configura um código de imposto retido na fonte, um tipo de imposto retido na fonte e um parâmetro de cálculo para calcular o imposto retido na fonte para pagamentos de serviços da consulta ou de serviço profissional.
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
ms.openlocfilehash: 78fcb736ae4a7dccf4a67187bd794062c06c611e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204708"
---
# <a name="brazilian-withholding-taxes"></a><span data-ttu-id="7f907-103">Impostos retidos na fonte no Brasil</span><span class="sxs-lookup"><span data-stu-id="7f907-103">Brazilian withholding taxes</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7f907-104">Este procedimento configura um código de imposto retido na fonte, um tipo de imposto retido na fonte e um parâmetro de cálculo para calcular o imposto retido na fonte para pagamentos de serviços da consulta ou de serviço profissional.</span><span class="sxs-lookup"><span data-stu-id="7f907-104">This procedure sets up a withholding tax code, withholding tax type, and calculation parameter to calculate withholding taxes for consultancy services or professional service payments.</span></span> <span data-ttu-id="7f907-105">Este procedimento usa a empresa de dados de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="7f907-105">This procedure uses the BRMF demo company.</span></span>

1. <span data-ttu-id="7f907-106">Vá para Imposto > Configuração > Imposto retido na fonte > Períodos de liquidação de imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="7f907-106">Go to Tax > Setup > Withholding tax > Withholding tax settlement periods.</span></span>
2. <span data-ttu-id="7f907-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7f907-107">Click New.</span></span>
3. <span data-ttu-id="7f907-108">No campo de Período de liquidação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-108">In the Settlement period field, type a value.</span></span>
4. <span data-ttu-id="7f907-109">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7f907-110">No campo Autoridade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-110">In the Authority field, enter or select a value.</span></span>
6. <span data-ttu-id="7f907-111">No campo Unidade de intervalo do período, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="7f907-111">In the Period interval unit field, select an option.</span></span>
7. <span data-ttu-id="7f907-112">No campo Duração de intervalo do período, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7f907-112">In the Period interval duration field, enter a number.</span></span>
8. <span data-ttu-id="7f907-113">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7f907-113">Click Add.</span></span>
9. <span data-ttu-id="7f907-114">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7f907-114">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="7f907-115">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="7f907-115">In the From date field, enter a date.</span></span>
11. <span data-ttu-id="7f907-116">No campo Até, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="7f907-116">In the To date field, enter a date.</span></span>
12. <span data-ttu-id="7f907-117">No Painel de Ação, clique em ActionPaneTab..</span><span class="sxs-lookup"><span data-stu-id="7f907-117">On the Action Pane, click ActionPaneTab.</span></span>
13. <span data-ttu-id="7f907-118">Clique em Novo período.</span><span class="sxs-lookup"><span data-stu-id="7f907-118">Click New period.</span></span>
14. <span data-ttu-id="7f907-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7f907-119">Click Save.</span></span>
15. <span data-ttu-id="7f907-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7f907-120">Close the page.</span></span>
16. <span data-ttu-id="7f907-121">Vá para Imposto > Impostos indiretos > Impostos retidos na fonte > Códigos de impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="7f907-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
17. <span data-ttu-id="7f907-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7f907-122">Click New.</span></span>
18. <span data-ttu-id="7f907-123">No campo Impostos retidos na fonte, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-123">In the Withholding tax code field, type a value.</span></span>
19. <span data-ttu-id="7f907-124">No campo Nome do imposto retido na fonte, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-124">In the Withholding tax name field, type a value.</span></span>
20. <span data-ttu-id="7f907-125">No campo Tipo de imposto retido na fonte brasileiro, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="7f907-125">In the Brazilian tax withhold type field, select an option.</span></span>
21. <span data-ttu-id="7f907-126">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="7f907-126">In the Main account field, specify the desired values.</span></span>
22. <span data-ttu-id="7f907-127">No campo Imposto retido na fonte a receber, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="7f907-127">In the Withholding tax receivable field, specify the desired values.</span></span>
23. <span data-ttu-id="7f907-128">No campo Período de definição, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-128">In the Settlement period field, enter or select a value.</span></span>
24. <span data-ttu-id="7f907-129">Expandir a seção Cálculo.</span><span class="sxs-lookup"><span data-stu-id="7f907-129">Expand the Calculation section.</span></span>
25. <span data-ttu-id="7f907-130">No campo Origem, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="7f907-130">In the Origin field, select an option.</span></span>
26. <span data-ttu-id="7f907-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7f907-131">Click Save.</span></span>
27. <span data-ttu-id="7f907-132">Clique em Valores.</span><span class="sxs-lookup"><span data-stu-id="7f907-132">Click Values.</span></span>
28. <span data-ttu-id="7f907-133">No campo Valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7f907-133">In the Value field, enter a number.</span></span>
29. <span data-ttu-id="7f907-134">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7f907-134">Click Save.</span></span>
30. <span data-ttu-id="7f907-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7f907-135">Close the page.</span></span>
31. <span data-ttu-id="7f907-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7f907-136">Close the page.</span></span>
32. <span data-ttu-id="7f907-137">Vá para Imposto > Impostos indiretos > Imposto retido na fonte > Grupos de impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="7f907-137">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
33. <span data-ttu-id="7f907-138">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7f907-138">Click New.</span></span>
34. <span data-ttu-id="7f907-139">No campo Grupo de impostos retidos na fonte, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-139">In the Withholding tax group field, type a value.</span></span>
35. <span data-ttu-id="7f907-140">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-140">In the Description field, type a value.</span></span>
36. <span data-ttu-id="7f907-141">No campo Código de imposto retido na fonte, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-141">In the Withholding tax code field, enter or select a value.</span></span>
37. <span data-ttu-id="7f907-142">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7f907-142">Click Save.</span></span>
38. <span data-ttu-id="7f907-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7f907-143">Close the page.</span></span>
39. <span data-ttu-id="7f907-144">Vá para Imposto > Impostos indiretos > Imposto retido na fonte > Grupos de impostos retidos na fonte do item.</span><span class="sxs-lookup"><span data-stu-id="7f907-144">Go to Tax > Indirect taxes > Withholding tax > Item withholding tax groups.</span></span>
40. <span data-ttu-id="7f907-145">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7f907-145">Click New.</span></span>
41. <span data-ttu-id="7f907-146">No campo Grupo de impostos retidos na fonte do item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-146">In the Item withholding tax group field, type a value.</span></span>
42. <span data-ttu-id="7f907-147">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-147">In the Description field, type a value.</span></span>
43. <span data-ttu-id="7f907-148">No campo Código de imposto retido na fonte, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7f907-148">In the Withholding tax code field, enter or select a value.</span></span>
44. <span data-ttu-id="7f907-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7f907-149">Click Save.</span></span>
45. <span data-ttu-id="7f907-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7f907-150">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]