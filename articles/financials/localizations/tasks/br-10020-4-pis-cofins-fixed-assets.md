---
title: Ativos fixos de PIS e COFINS (Brasil)
description: Quando uma entidade legal compra um ativo fixo, o crédito fiscal de PIS e COFINS que é calculado sobre essa transação pode ser adquirido em um número de parcelas específico.
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
ms.openlocfilehash: 9915e6c2dbe38d954f27ed1af1d3b8cdadeb5461
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852755"
---
# <a name="pis-and-cofins-fixed-assets-brazil"></a><span data-ttu-id="ed32e-103">Ativos fixos de PIS e COFINS (Brasil)</span><span class="sxs-lookup"><span data-stu-id="ed32e-103">PIS and COFINS fixed assets (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ed32e-104">Quando uma entidade legal compra um ativo fixo, o crédito fiscal de PIS e COFINS que é calculado sobre essa transação pode ser adquirido em um número de parcelas específico.</span><span class="sxs-lookup"><span data-stu-id="ed32e-104">When a legal entity purchases a fixed asset, the PIS and COFINS tax credit that is calculated on that transaction can be appropriated in a specific number of installments.</span></span> <span data-ttu-id="ed32e-105">Para ter o cálculo correto desta restituição do imposto, a entidade legal deve apresentar um livro fiscal específico ou relatar informações no arquivo Contribuições EFD SPED para demonstrar a apropriação correta do valor do crédito fiscal de PIS e COFINS.</span><span class="sxs-lookup"><span data-stu-id="ed32e-105">For the correct calculation for this tax refund, the legal entity must present a specific fiscal book or report for the information in the SPED EFD Contributions file to demonstrate correct appropriation of the PIS and COFINS tax credit amount.</span></span> <span data-ttu-id="ed32e-106">O controle de crédito apropriado no período de avaliação de imposto é detalhado em registros F120 e F130 de contribuições de EFD SPED.</span><span class="sxs-lookup"><span data-stu-id="ed32e-106">The control of credit that is appropriated in the tax assessment period is detailed in records F120 and F130 of SPED EFD Contributions.</span></span> <span data-ttu-id="ed32e-107">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="ed32e-107">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="ed32e-108">Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="ed32e-108">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="ed32e-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ed32e-109">Click New.</span></span>
3. <span data-ttu-id="ed32e-110">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ed32e-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="ed32e-111">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ed32e-111">Click OK.</span></span>
5. <span data-ttu-id="ed32e-112">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="ed32e-112">Click Add line.</span></span>
6. <span data-ttu-id="ed32e-113">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ed32e-113">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="ed32e-114">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ed32e-114">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="ed32e-115">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ed32e-115">In the CFOP field, enter or select a value.</span></span>
9. <span data-ttu-id="ed32e-116">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ed32e-116">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="ed32e-117">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ed32e-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="ed32e-118">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="ed32e-118">Expand the Line details section.</span></span>
12. <span data-ttu-id="ed32e-119">Clique na guia Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="ed32e-119">Click the Fixed assets tab.</span></span>
13. <span data-ttu-id="ed32e-120">Selecione Sim no campo Novo ativo fixo? .</span><span class="sxs-lookup"><span data-stu-id="ed32e-120">Select Yes in the New fixed asset? field.</span></span>
14. <span data-ttu-id="ed32e-121">No campo Grupo de ativo fixo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ed32e-121">In the Fixed asset group field, enter or select a value.</span></span>
15. <span data-ttu-id="ed32e-122">Clique na guia Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="ed32e-122">Click the Financial dimensions tab.</span></span>
16. <span data-ttu-id="ed32e-123">No campo CostCenter, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ed32e-123">In the CostCenter field, enter or select a value.</span></span>
17. <span data-ttu-id="ed32e-124">No campo Filial, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ed32e-124">In the Filial field, enter or select a value.</span></span>
18. <span data-ttu-id="ed32e-125">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="ed32e-125">On the Action Pane, click Purchase.</span></span>
19. <span data-ttu-id="ed32e-126">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="ed32e-126">Click Confirm.</span></span>
20. <span data-ttu-id="ed32e-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ed32e-127">Close the page.</span></span>
21. <span data-ttu-id="ed32e-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ed32e-128">Close the page.</span></span>
22. <span data-ttu-id="ed32e-129">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="ed32e-129">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
23. <span data-ttu-id="ed32e-130">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ed32e-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="ed32e-131">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="ed32e-131">On the Action Pane, click Invoice.</span></span>
25. <span data-ttu-id="ed32e-132">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="ed32e-132">Click Invoice.</span></span>
26. <span data-ttu-id="ed32e-133">Clique em Padrão de: Quantidade de recebimento de produtos para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ed32e-133">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
27. <span data-ttu-id="ed32e-134">No campo Quantidade padrão para linhas, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="ed32e-134">In the Default quantity for lines field, select an option.</span></span>
28. <span data-ttu-id="ed32e-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ed32e-135">Click OK.</span></span>
29. <span data-ttu-id="ed32e-136">No campo Modelo do documento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ed32e-136">In the Document model field, enter or select a value.</span></span>
30. <span data-ttu-id="ed32e-137">No campo Chave de acesso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ed32e-137">In the Access key field, type a value.</span></span>
31. <span data-ttu-id="ed32e-138">No campo Data da fatura, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="ed32e-138">In the Invoice date field, enter a date.</span></span>
32. <span data-ttu-id="ed32e-139">No campo Lançamento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="ed32e-139">In the Posting date field, enter a date.</span></span>
33. <span data-ttu-id="ed32e-140">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="ed32e-140">Click Post.</span></span>
34. <span data-ttu-id="ed32e-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ed32e-141">Close the page.</span></span>
35. <span data-ttu-id="ed32e-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ed32e-142">Close the page.</span></span>
36. <span data-ttu-id="ed32e-143">Vá para Livros fiscais > Comum > Período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="ed32e-143">Go to Fiscal books > Common > Booking period.</span></span>
37. <span data-ttu-id="ed32e-144">Clique em Criar novo período de escrituração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ed32e-144">Click Create new booking period to open the drop dialog.</span></span>
38. <span data-ttu-id="ed32e-145">No campo Estabelecimento fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ed32e-145">In the Fiscal establishment field, enter or select a value.</span></span>
39. <span data-ttu-id="ed32e-146">No campo Mês, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="ed32e-146">In the Month field, select an option.</span></span>
40. <span data-ttu-id="ed32e-147">No campo Ano, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ed32e-147">In the Year field, enter a number.</span></span>
41. <span data-ttu-id="ed32e-148">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ed32e-148">Click OK.</span></span>
42. <span data-ttu-id="ed32e-149">Clique em Sincronizar.</span><span class="sxs-lookup"><span data-stu-id="ed32e-149">Click Sync.</span></span>
43. <span data-ttu-id="ed32e-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ed32e-150">Click OK.</span></span>
44. <span data-ttu-id="ed32e-151">Clique em PIS-COFINS.</span><span class="sxs-lookup"><span data-stu-id="ed32e-151">Click PIS-COFINS.</span></span>
45. <span data-ttu-id="ed32e-152">Clique em Apuração de imposto PIS e COFINS para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ed32e-152">Click PIS and COFINS tax assessment to open the drop dialog.</span></span>
46. <span data-ttu-id="ed32e-153">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ed32e-153">Click OK.</span></span>
47. <span data-ttu-id="ed32e-154">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ed32e-154">Close the page.</span></span>
48. <span data-ttu-id="ed32e-155">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ed32e-155">Close the page.</span></span>
49. <span data-ttu-id="ed32e-156">Vá para Livros fiscais > Comum > Ativos fixos > Todos os ativos fixos com PIS e COFINS.</span><span class="sxs-lookup"><span data-stu-id="ed32e-156">Go to Fiscal books > Common > Fixed assets > All PIS and COFINS fixed assets.</span></span>
50. <span data-ttu-id="ed32e-157">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ed32e-157">In the list, click the link in the selected row.</span></span>
51. <span data-ttu-id="ed32e-158">Expanda a seção de transações de ativo fixo de PIS e COFINS.</span><span class="sxs-lookup"><span data-stu-id="ed32e-158">Expand the PIS and COFINS fixed asset transactions section.</span></span>
52. <span data-ttu-id="ed32e-159">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ed32e-159">Close the page.</span></span>
53. <span data-ttu-id="ed32e-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ed32e-160">Close the page.</span></span>

