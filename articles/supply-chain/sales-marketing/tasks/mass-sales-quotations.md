---
title: Criar cotações de venda em massa
description: Este procedimento demonstra como criar cotações de forma eficiente que oferecem um conjunto de produtos ou serviços que devem ser enviados a vários clientes.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 227ff0dd03f8917f4551ce08067ef26c6204b059
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980709"
---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="aa959-103">Criar cotações de venda em massa</span><span class="sxs-lookup"><span data-stu-id="aa959-103">Mass create sales quotations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aa959-104">Este procedimento demonstra como criar cotações de forma eficiente que oferecem um conjunto de produtos ou serviços que devem ser enviados a vários clientes.</span><span class="sxs-lookup"><span data-stu-id="aa959-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="aa959-105">A criação de cotação em massa foi baseada em modelos de cotação.</span><span class="sxs-lookup"><span data-stu-id="aa959-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="aa959-106">Você pode realizar esse procedimento em seus próprios dados ou na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="aa959-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="aa959-107">Criar um modelo de cotação</span><span class="sxs-lookup"><span data-stu-id="aa959-107">Create a quotation template</span></span>
1. <span data-ttu-id="aa959-108">Vá para Vendas e marketing > Configuração > Cotações > Grupos de modelo.</span><span class="sxs-lookup"><span data-stu-id="aa959-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="aa959-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="aa959-109">Click New.</span></span>
3. <span data-ttu-id="aa959-110">No campo de ID de grupo, digite uma ID de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="aa959-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="aa959-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="aa959-112">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="aa959-112">Click Save.</span></span>
6. <span data-ttu-id="aa959-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="aa959-113">Close the page.</span></span>
7. <span data-ttu-id="aa959-114">Vá para Vendas e marketing > Cotações de venda > Todas as cotações.</span><span class="sxs-lookup"><span data-stu-id="aa959-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="aa959-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="aa959-115">Click New.</span></span>
9. <span data-ttu-id="aa959-116">No tipo Conta, selecione 'Cliente'.</span><span class="sxs-lookup"><span data-stu-id="aa959-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="aa959-117">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="aa959-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="aa959-118">Click OK.</span></span>
    * <span data-ttu-id="aa959-119">Para que uma cotação se torne um modelo, você deve executar etapas de instalação do cabeçalho da cotação.</span><span class="sxs-lookup"><span data-stu-id="aa959-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="aa959-120">Isso deve ser feito antes para adicionar linhas à cotação.</span><span class="sxs-lookup"><span data-stu-id="aa959-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="aa959-121">No Painel de Ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="aa959-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="aa959-122">Clique em Alterar exibição.</span><span class="sxs-lookup"><span data-stu-id="aa959-122">Click Change view.</span></span>
14. <span data-ttu-id="aa959-123">Clique em Exibição do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="aa959-123">Click Header view.</span></span>
15. <span data-ttu-id="aa959-124">Expandir a seção Instalação.</span><span class="sxs-lookup"><span data-stu-id="aa959-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="aa959-125">No campo ID do Grupo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="aa959-126">No campo Nome de modelo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="aa959-127">Selecione Sim no campo Ativo.</span><span class="sxs-lookup"><span data-stu-id="aa959-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="aa959-128">Somente os modelos ativos podem ser usados quando você aplica um modelo a uma nova cotação de venda.</span><span class="sxs-lookup"><span data-stu-id="aa959-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="aa959-129">No Painel de Ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="aa959-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="aa959-130">Clique em Alterar exibição.</span><span class="sxs-lookup"><span data-stu-id="aa959-130">Click Change view.</span></span>
21. <span data-ttu-id="aa959-131">Clique em Exibição em linha.</span><span class="sxs-lookup"><span data-stu-id="aa959-131">Click Line view.</span></span>
22. <span data-ttu-id="aa959-132">No campo Item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="aa959-133">No campo Item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="aa959-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="aa959-134">Close the page.</span></span>
25. <span data-ttu-id="aa959-135">No campo Percentual de desconto, insira um número.</span><span class="sxs-lookup"><span data-stu-id="aa959-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="aa959-136">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="aa959-136">Click Add line.</span></span>
27. <span data-ttu-id="aa959-137">No campo Item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="aa959-138">No campo Item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="aa959-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="aa959-139">Close the page.</span></span>
30. <span data-ttu-id="aa959-140">No campo Preço unitário, insira um novo preço ou altere o atual.</span><span class="sxs-lookup"><span data-stu-id="aa959-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="aa959-141">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="aa959-141">Click Add line.</span></span>
32. <span data-ttu-id="aa959-142">No campo Item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="aa959-143">No campo Item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="aa959-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="aa959-144">Close the page.</span></span>
35. <span data-ttu-id="aa959-145">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="aa959-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="aa959-146">No campo Desconto, insira um número.</span><span class="sxs-lookup"><span data-stu-id="aa959-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="aa959-147">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="aa959-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="aa959-148">Aplique o modelo para criar uma única cotação</span><span class="sxs-lookup"><span data-stu-id="aa959-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="aa959-149">Vá para Vendas e marketing > Cotações de venda > Todas as cotações.</span><span class="sxs-lookup"><span data-stu-id="aa959-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="aa959-150">Observe que a cotação que você acabou de criar está marcada como modelo.</span><span class="sxs-lookup"><span data-stu-id="aa959-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="aa959-151">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="aa959-151">Click New.</span></span>
3. <span data-ttu-id="aa959-152">No tipo Conta, selecione 'Cliente'.</span><span class="sxs-lookup"><span data-stu-id="aa959-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="aa959-153">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="aa959-154">Expanda a seção Modelo.</span><span class="sxs-lookup"><span data-stu-id="aa959-154">Expand the Template section.</span></span>
6. <span data-ttu-id="aa959-155">No campo ID do Grupo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="aa959-156">No campo Nome do modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="aa959-157">No campo Método de cálculo, selecione 'Com base em valores modelo'.</span><span class="sxs-lookup"><span data-stu-id="aa959-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="aa959-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="aa959-158">Click OK.</span></span>
    * <span data-ttu-id="aa959-159">A nova cotação agora foi criada, com base nos dados e nas condições do modelo.</span><span class="sxs-lookup"><span data-stu-id="aa959-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="aa959-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="aa959-160">Close the page.</span></span>
11. <span data-ttu-id="aa959-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="aa959-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="aa959-162">Aplique o modelo para criar cotações em massa</span><span class="sxs-lookup"><span data-stu-id="aa959-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="aa959-163">Vá para Vendas e marketing > Cotações de venda > Atualização da cotação > Criar cotações em massa.</span><span class="sxs-lookup"><span data-stu-id="aa959-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="aa959-164">No tipo Conta, selecione 'Cliente'.</span><span class="sxs-lookup"><span data-stu-id="aa959-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="aa959-165">No campo ID do Grupo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="aa959-166">No campo Nome do modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="aa959-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="aa959-167">No campo Método de cálculo, selecione 'Com base em valores modelo'.</span><span class="sxs-lookup"><span data-stu-id="aa959-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="aa959-168">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="aa959-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="aa959-169">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="aa959-169">Click Filter.</span></span>
8. <span data-ttu-id="aa959-170">No campo Critérios, defina o filtro para cobrir um intervalo de clientes que você deseja incluir nesta criação de cotação em massa.</span><span class="sxs-lookup"><span data-stu-id="aa959-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="aa959-171">Use o seguinte formato "Customer1..CustomerN.</span><span class="sxs-lookup"><span data-stu-id="aa959-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="aa959-172">Por exemplo, você pode definir o filtro: US-001.US-004</span><span class="sxs-lookup"><span data-stu-id="aa959-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="aa959-173">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="aa959-173">Click OK.</span></span>
10. <span data-ttu-id="aa959-174">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="aa959-174">Click OK.</span></span>
11. <span data-ttu-id="aa959-175">Vá para Vendas e marketing > Cotações de venda > Todas as cotações.</span><span class="sxs-lookup"><span data-stu-id="aa959-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="aa959-176">Verifique se as cotações foram criadas para todos os clientes especificados na rotina de atualização em massa, conforme baseado no modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="aa959-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  

