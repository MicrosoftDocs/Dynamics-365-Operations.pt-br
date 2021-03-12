---
title: Configurar juros e multas para pagamentos de fornecedores (Brasil)
description: Você deve configurar contas para juros e multas financeiras, códigos padrão para juros e multas, e códigos de juros e de multas para fornecedores e ordens de compra.
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
ms.openlocfilehash: 2ac8cef3e09776e1749aaf684c4b345b97ccb479
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975291"
---
# <a name="set-up-interest-and-fines-for-vendor-payments-brazil"></a><span data-ttu-id="683d8-103">Configurar juros e multas para pagamentos de fornecedores (Brasil)</span><span class="sxs-lookup"><span data-stu-id="683d8-103">Set up interest and fines for vendor payments (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="683d8-104">Você deve configurar contas para juros e multas financeiras, códigos padrão para juros e multas, e códigos de juros e de multas para fornecedores e ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="683d8-104">You must set up accounts for financial interest and fines, default codes for interest and fines, and interest codes and fine codes for vendors and purchase orders.</span></span> <span data-ttu-id="683d8-105">Também é necessário definir os feriados ou dias não úteis durante um ano financeiro que não serão considerados quando as multas e os juros forem calculados.</span><span class="sxs-lookup"><span data-stu-id="683d8-105">You must also define the holidays or non-business days during a financial year that aren't considered when interest and fines are calculated.</span></span>  <span data-ttu-id="683d8-106">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="683d8-106">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="683d8-107">Vá para Contas a pagar > Configuração > Perfis de lançamentos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="683d8-107">Go to Accounts payable > Setup > Vendor posting profiles.</span></span>
2. <span data-ttu-id="683d8-108">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="683d8-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="683d8-109">Por exemplo, filtre no campo Perfil de lançamento com um valor de '010'.</span><span class="sxs-lookup"><span data-stu-id="683d8-109">For example, filter on the Posting profile field with a value of '010'.</span></span>
3. <span data-ttu-id="683d8-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="683d8-110">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="683d8-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="683d8-111">Click Edit.</span></span>
5. <span data-ttu-id="683d8-112">No campo Juros financeiros, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="683d8-112">In the Financial interest field, specify the desired values.</span></span>
6. <span data-ttu-id="683d8-113">No campo Multa, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="683d8-113">In the Fine field, specify the desired values.</span></span>
7. <span data-ttu-id="683d8-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="683d8-114">Click Save.</span></span>
8. <span data-ttu-id="683d8-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="683d8-115">Close the page.</span></span>
9. <span data-ttu-id="683d8-116">Vá para Contas a pagar > Configuração de pagamento > Calendário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="683d8-116">Go to Accounts payable > Payment setup > Payment calendar.</span></span>
10. <span data-ttu-id="683d8-117">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="683d8-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="683d8-118">Por exemplo, filtre o campo Calendário de pagamentos com um valor de 'Brasil'.</span><span class="sxs-lookup"><span data-stu-id="683d8-118">For example, filter on the Payment calendar field with a value of 'Brazil'.</span></span>
11. <span data-ttu-id="683d8-119">Clique em feriados do estado/província.</span><span class="sxs-lookup"><span data-stu-id="683d8-119">Click State/province holidays.</span></span>
12. <span data-ttu-id="683d8-120">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="683d8-120">Use the Quick Filter to find records.</span></span> <span data-ttu-id="683d8-121">Por exemplo, filtre o campo Estado/província com um valor de 'SP'.</span><span class="sxs-lookup"><span data-stu-id="683d8-121">For example, filter on the State/province field with a value of 'SP'.</span></span>
13. <span data-ttu-id="683d8-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="683d8-122">Click New.</span></span>
14. <span data-ttu-id="683d8-123">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="683d8-123">In the Date field, enter a date.</span></span>
15. <span data-ttu-id="683d8-124">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="683d8-124">In the Description field, type a value.</span></span>
16. <span data-ttu-id="683d8-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="683d8-125">Click Save.</span></span>
17. <span data-ttu-id="683d8-126">Clique em Feriados municipais.</span><span class="sxs-lookup"><span data-stu-id="683d8-126">Click City holidays.</span></span>
18. <span data-ttu-id="683d8-127">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="683d8-127">Use the Quick Filter to find records.</span></span> <span data-ttu-id="683d8-128">Por exemplo, filtre no campo Cidade com um valor de 'São Paulo'.</span><span class="sxs-lookup"><span data-stu-id="683d8-128">For example, filter on the City field with a value of 'São Paulo'.</span></span>
19. <span data-ttu-id="683d8-129">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="683d8-129">Click Add.</span></span>
20. <span data-ttu-id="683d8-130">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="683d8-130">In the Date field, enter a date.</span></span>
21. <span data-ttu-id="683d8-131">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="683d8-131">In the Description field, type a value.</span></span>
22. <span data-ttu-id="683d8-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="683d8-132">Click Save.</span></span>
23. <span data-ttu-id="683d8-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="683d8-133">Close the page.</span></span>
24. <span data-ttu-id="683d8-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="683d8-134">Close the page.</span></span>
25. <span data-ttu-id="683d8-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="683d8-135">Close the page.</span></span>
26. <span data-ttu-id="683d8-136">Vá para Contas a receber > Configuração de pagamento > Códigos de multa.</span><span class="sxs-lookup"><span data-stu-id="683d8-136">Go to Accounts payable > Payment setup > Fine codes.</span></span>
27. <span data-ttu-id="683d8-137">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="683d8-137">Click New.</span></span>
28. <span data-ttu-id="683d8-138">No campo Código de multa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="683d8-138">In the Fine code field, type a value.</span></span>
29. <span data-ttu-id="683d8-139">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="683d8-139">In the Description field, type a value.</span></span>
30. <span data-ttu-id="683d8-140">No campo % de multa, digite um número.</span><span class="sxs-lookup"><span data-stu-id="683d8-140">In the Fine % field, enter a number.</span></span>
31. <span data-ttu-id="683d8-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="683d8-141">Click Save.</span></span>
32. <span data-ttu-id="683d8-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="683d8-142">Close the page.</span></span>
33. <span data-ttu-id="683d8-143">Vá para Contas a pagar > Configuração de pagamento > Códigos de juros.</span><span class="sxs-lookup"><span data-stu-id="683d8-143">Go to Accounts payable > Payment setup > Interest codes.</span></span>
34. <span data-ttu-id="683d8-144">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="683d8-144">Click New.</span></span>
35. <span data-ttu-id="683d8-145">No campo Código de juros, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="683d8-145">In the Interest code field, type a value.</span></span>
36. <span data-ttu-id="683d8-146">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="683d8-146">In the Description field, type a value.</span></span>
37. <span data-ttu-id="683d8-147">No campo % de juros, insira um número.</span><span class="sxs-lookup"><span data-stu-id="683d8-147">In the Interest % field, enter a number.</span></span>
38. <span data-ttu-id="683d8-148">No campo Cálculo de juros por campo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="683d8-148">In the Interest calculation per field, enter a number.</span></span>
39. <span data-ttu-id="683d8-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="683d8-149">Click Save.</span></span>
40. <span data-ttu-id="683d8-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="683d8-150">Close the page.</span></span>
41. <span data-ttu-id="683d8-151">Vá para Contas a pagar > Fornecedores > Todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="683d8-151">Go to Accounts payable > Vendors > All vendors.</span></span>
42. <span data-ttu-id="683d8-152">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="683d8-152">Use the Quick Filter to find records.</span></span> <span data-ttu-id="683d8-153">Por exemplo, no campo Conta de fornecedor, filtre com um valor de 'BRMF-000001'.</span><span class="sxs-lookup"><span data-stu-id="683d8-153">For example, filter on the Vendor account field with a value of 'BRMF-000001'.</span></span>
43. <span data-ttu-id="683d8-154">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="683d8-154">In the list, click the link in the selected row.</span></span>
44. <span data-ttu-id="683d8-155">Expandir a seção Pagamento.</span><span class="sxs-lookup"><span data-stu-id="683d8-155">Expand the Payment section.</span></span>
45. <span data-ttu-id="683d8-156">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="683d8-156">Click Edit.</span></span>
46. <span data-ttu-id="683d8-157">No campo Código de juros, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="683d8-157">In the Fine code field, enter or select a value.</span></span>
47. <span data-ttu-id="683d8-158">No campo Código de juros, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="683d8-158">In the Interest code field, enter or select a value.</span></span>
48. <span data-ttu-id="683d8-159">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="683d8-159">Click Save.</span></span>
49. <span data-ttu-id="683d8-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="683d8-160">Close the page.</span></span>
50. <span data-ttu-id="683d8-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="683d8-161">Close the page.</span></span>

