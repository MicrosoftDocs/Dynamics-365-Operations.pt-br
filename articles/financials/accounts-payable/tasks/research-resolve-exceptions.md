--- 
title: "Pesquisar ou resolver exceções"
description: "As políticas de fatura de fornecedor são executadas quando você lança uma fatura de fornecedor usando a página de fatura do fornecedor e quando você abre a página de violações de política da fatura de fornecedor."
author: abruer
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: eb539d207906560eaf6f70ffea6ed6f21f003af0
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="research-or-resolve-exceptions"></a><span data-ttu-id="0f744-103">Pesquisar ou resolver exceções</span><span class="sxs-lookup"><span data-stu-id="0f744-103">Research or resolve exceptions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0f744-104">As políticas de fatura de fornecedor são executadas quando você lança uma fatura de fornecedor usando a página de fatura do fornecedor e quando você abre a página de violações de política da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0f744-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="0f744-105">Você também pode configurar o fluxo de trabalho da fatura do fornecedor para executar as políticas de fatura do fornecedor todas as vezes que você enviar uma fatura para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f744-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="0f744-106">As políticas de fatura do fornecedor não se aplicam às faturas que foram criadas no registro de fatura ou no diário de faturas.</span><span class="sxs-lookup"><span data-stu-id="0f744-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="0f744-107">A validação de conciliação de fatura não usa as políticas da fatura do fornecedor, mas é configurada na página de parâmetros de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="0f744-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="0f744-108">Este registro usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="0f744-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="0f744-109">A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0f744-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="0f744-110">Antes de começar, verifique se a configuração conciliação de faturas está marcada.</span><span class="sxs-lookup"><span data-stu-id="0f744-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="0f744-111">Preparar para criar políticas de fatura do fornecedor</span><span class="sxs-lookup"><span data-stu-id="0f744-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="0f744-112">Ir para Contas a pagar > Configuração > Parâmetros de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="0f744-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="0f744-113">Clique na guia Validação de fatura.</span><span class="sxs-lookup"><span data-stu-id="0f744-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="0f744-114">Marque ou desmarque a caixa de seleção automaticamente do status do cabeçalho da nota fiscal da atualização.</span><span class="sxs-lookup"><span data-stu-id="0f744-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="0f744-115">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0f744-115">Click OK.</span></span>
5. <span data-ttu-id="0f744-116">No campo Lançar nota fiscal com discrepâncias, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="0f744-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="0f744-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f744-117">Close the page.</span></span>
7. <span data-ttu-id="0f744-118">Ir para Contas a pagar > Configuração de política > Políticas de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0f744-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="0f744-119">Clique em Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0f744-119">Click Parameters.</span></span>
9. <span data-ttu-id="0f744-120">Clique em btnAdd.</span><span class="sxs-lookup"><span data-stu-id="0f744-120">Click btnAdd.</span></span>
10. <span data-ttu-id="0f744-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f744-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="0f744-122">Criar tipos de regras de política para faturas de fornecedor</span><span class="sxs-lookup"><span data-stu-id="0f744-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="0f744-123">Ir para Contas a pagar > Configuração de política > Tipos de regra de políticas de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0f744-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="0f744-124">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0f744-124">Click New.</span></span>
3. <span data-ttu-id="0f744-125">No campo Nome da regra, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f744-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="0f744-126">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f744-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0f744-127">No campo Nome da consulta, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f744-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="0f744-128">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="0f744-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="0f744-129">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f744-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="0f744-130">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0f744-130">Click Save.</span></span>
9. <span data-ttu-id="0f744-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f744-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="0f744-132">Definir uma política de fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="0f744-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="0f744-133">Ir para Contas a pagar > Configuração de política > Políticas de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0f744-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="0f744-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0f744-134">Click New.</span></span>
3. <span data-ttu-id="0f744-135">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f744-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="0f744-136">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f744-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0f744-137">Expanda ou recolha a seção de organizações de diretivas.</span><span class="sxs-lookup"><span data-stu-id="0f744-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="0f744-138">Na árvore, selecione 'Contoso Entertainment System USA'.</span><span class="sxs-lookup"><span data-stu-id="0f744-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="0f744-139">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="0f744-139">Click Add.</span></span>
8. <span data-ttu-id="0f744-140">Expanda ou recolha a seção de regras de diretivas.</span><span class="sxs-lookup"><span data-stu-id="0f744-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="0f744-141">Clique em Criar regra de política.</span><span class="sxs-lookup"><span data-stu-id="0f744-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="0f744-142">No campo Descrição de regra de política, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f744-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="0f744-143">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="0f744-143">Click Filter.</span></span>
12. <span data-ttu-id="0f744-144">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="0f744-144">Click Add.</span></span>
13. <span data-ttu-id="0f744-145">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f744-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="0f744-146">No campo Tabela, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f744-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="0f744-147">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f744-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="0f744-148">No campo Tabela derivada, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f744-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="0f744-149">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f744-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="0f744-150">No campo Campo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f744-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="0f744-151">No campo Campo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f744-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="0f744-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f744-152">Close the page.</span></span>
21. <span data-ttu-id="0f744-153">No campo Critérios, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f744-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="0f744-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0f744-154">Click OK.</span></span>
23. <span data-ttu-id="0f744-155">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0f744-155">Click OK.</span></span>
24. <span data-ttu-id="0f744-156">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f744-156">Close the page.</span></span>
25. <span data-ttu-id="0f744-157">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f744-157">Close the page.</span></span>


