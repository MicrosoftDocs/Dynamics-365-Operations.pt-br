---
title: Impostos brasileiros nas cotações de venda
description: Use este procedimento para criar uma cotação de venda que usa impostos brasileiros.
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
ms.openlocfilehash: 62664a77b43dd88f4616ea0cb45bbc1e069b4205
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852772"
---
# <a name="brazilian-tax-in-sales-quotations"></a><span data-ttu-id="0ab2c-103">Impostos brasileiros nas cotações de venda</span><span class="sxs-lookup"><span data-stu-id="0ab2c-103">Brazilian tax in sales quotations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0ab2c-104">Use este procedimento para criar uma cotação de venda que usa impostos brasileiros.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-104">Use this procedure to create a sales quotation that uses Brazilian taxes.</span></span> <span data-ttu-id="0ab2c-105">É possível criar uma cotação especificando as informações fiscais, como o tipo de operação e o CFOP (Código Fiscal de Operações e Prestações).</span><span class="sxs-lookup"><span data-stu-id="0ab2c-105">You can create a quotation by specifying fiscal information, such as the operation type and the Código Fiscal de Operações e Prestações (CFOP) code.</span></span> <span data-ttu-id="0ab2c-106">Ao criar uma linha de cotação, é possível selecionar um código de CFOP no campo CFOP.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-106">When you create a quotation line, you can select a CFOP code in the CFOP field.</span></span> <span data-ttu-id="0ab2c-107">Os códigos de CFOP disponíveis neste campo dependem do estabelecimento fiscal do site selecionado no campo Site.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-107">The CFOP codes that are available in this field depend on the fiscal establishment of the site that you selected in the Site field.</span></span> <span data-ttu-id="0ab2c-108">Os grupos de impostos nos campos Grupo de impostos sobre vendas e Imposto do item também são atualizados com base na matriz de imposto.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-108">The tax groups in the Sales tax group and Item sales tax group fields are also updated based on the tax matrix.</span></span> <span data-ttu-id="0ab2c-109">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-109">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="0ab2c-110">Vá para Vendas e marketing > Cotações de venda > Todas as cotações.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-110">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
2. <span data-ttu-id="0ab2c-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-111">Click New.</span></span>
3. <span data-ttu-id="0ab2c-112">No campo Tipo de conta, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-112">In the Account type field, select an option.</span></span>
4. <span data-ttu-id="0ab2c-113">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-113">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="0ab2c-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-114">Click OK.</span></span>
6. <span data-ttu-id="0ab2c-115">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-115">Click Yes.</span></span>
7. <span data-ttu-id="0ab2c-116">No campo Linhas ou cabeçalho, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-116">In the Lines or header field, select an option.</span></span>
8. <span data-ttu-id="0ab2c-117">Expanda a seção Informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-117">Expand the Fiscal information section.</span></span>
    * <span data-ttu-id="0ab2c-118">Use esta seção para inserir informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-118">Use this section to enter fiscal information.</span></span>  
9. <span data-ttu-id="0ab2c-119">Selecione Sim no campo Usuário final.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-119">Select Yes in the Final user field.</span></span>
    * <span data-ttu-id="0ab2c-120">Selecione Sim se todas as linhas da cotação são para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-120">Select Yes if all lines from the quotation are for a final user.</span></span>  <span data-ttu-id="0ab2c-121">Se você selecionar Sim, o ICMS (imposto sobre circulação de mercadorias e serviços) inclui o IPI (imposto sobre produtos industrializados) e todos os encargos de frete.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-121">If you select Yes, the Imposto Sobre Circulação de Mercadorias e Serviços (ICMS) tax includes the Imposto Sobre Produtos Industrializados (IPI) tax and any freight charges.</span></span>  
10. <span data-ttu-id="0ab2c-122">No campo Linhas ou cabeçalho, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-122">In the Lines or header field, select an option.</span></span>
11. <span data-ttu-id="0ab2c-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-123">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="0ab2c-124">No campo Item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-124">In the Item field, enter or select a value.</span></span>
13. <span data-ttu-id="0ab2c-125">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-125">In the Quantity field, enter a number.</span></span>
14. <span data-ttu-id="0ab2c-126">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-126">In the Site field, enter or select a value.</span></span>
15. <span data-ttu-id="0ab2c-127">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-127">In the Warehouse field, enter or select a value.</span></span>
16. <span data-ttu-id="0ab2c-128">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-128">In the CFOP field, enter or select a value.</span></span>
17. <span data-ttu-id="0ab2c-129">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-129">Expand the Line details section.</span></span>
18. <span data-ttu-id="0ab2c-130">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-130">Click the Setup tab.</span></span>
19. <span data-ttu-id="0ab2c-131">No campo Grupo de impostos sobre vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-131">In the Sales tax group field, enter or select a value.</span></span>
20. <span data-ttu-id="0ab2c-132">No campo Grupo de impostos sobre vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-132">In the Item sales tax group field, enter or select a value.</span></span>
21. <span data-ttu-id="0ab2c-133">Clique na guia Informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-133">Click the Fiscal information tab.</span></span>
22. <span data-ttu-id="0ab2c-134">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-134">Click Save.</span></span>
23. <span data-ttu-id="0ab2c-135">No Painel de Ação, clique em Cotação.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-135">On the Action Pane, click Quotation.</span></span>
24. <span data-ttu-id="0ab2c-136">Clique em Enviar cotação.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-136">Click Send quotation.</span></span>
25. <span data-ttu-id="0ab2c-137">Selecione Sim no campo Imprimir cotação.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-137">Select Yes in the Print quotation field.</span></span>
26. <span data-ttu-id="0ab2c-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-138">Click OK.</span></span>
27. <span data-ttu-id="0ab2c-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-139">Close the page.</span></span>
28. <span data-ttu-id="0ab2c-140">No Painel de Ação, clique em Acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-140">On the Action Pane, click Follow up.</span></span>
29. <span data-ttu-id="0ab2c-141">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-141">Click Confirm.</span></span>
30. <span data-ttu-id="0ab2c-142">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-142">Click Yes.</span></span>
31. <span data-ttu-id="0ab2c-143">No campo Motivo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-143">In the Reason field, enter or select a value.</span></span>
32. <span data-ttu-id="0ab2c-144">Marque a caixa de seleção Imprimir confirmação.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-144">Select the Print confirmation check box.</span></span>
33. <span data-ttu-id="0ab2c-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-145">Click OK.</span></span>
34. <span data-ttu-id="0ab2c-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-146">Close the page.</span></span>
35. <span data-ttu-id="0ab2c-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-147">Close the page.</span></span>
36. <span data-ttu-id="0ab2c-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0ab2c-148">Close the page.</span></span>

