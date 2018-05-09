--- 
title: Criar um contrato de compra
description: "Este procedimento irá guiá-lo na criação de um contrato de compra."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f060346308e7ee1191d0769664648cfe72c22b21
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-purchase-agreement"></a><span data-ttu-id="a6eb9-103">Criar um contrato de compra</span><span class="sxs-lookup"><span data-stu-id="a6eb9-103">Create a purchase agreement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a6eb9-104">Este procedimento irá guiá-lo na criação de um contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-104">This procedure guides you through the creation of a purchase agreement.</span></span> <span data-ttu-id="a6eb9-105">Isso seria feito normalmente por um gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-105">This would typically be done by a purchasing manager.</span></span> <span data-ttu-id="a6eb9-106">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-106">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="a6eb9-107">Você precisa ter classificações do contrato de compra configuradas antes de começar.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-107">You need to have set up purchase agreement classifications before you start.</span></span> <span data-ttu-id="a6eb9-108">Após criar um contrato é possível usá-lo quando você criar um PO, e isso irá copiar as condições do contrato de compra para o cabeçalho e para todas as linhas da ordem que são afetadas pelo contrato.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-108">Once you've created an agreement you can use it when you create a PO, and this will copy the purchase agreement conditions to the header and to any lines in the order that are affected by the agreement.</span></span>


## <a name="create-a-new-purchase-agreement"></a><span data-ttu-id="a6eb9-109">Criar um novo contrato de compra</span><span class="sxs-lookup"><span data-stu-id="a6eb9-109">Create a new purchase agreement</span></span>
1. <span data-ttu-id="a6eb9-110">Vá para Aquisição e fornecimento > Contratos de compra > Contratos de compra.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-110">Go to Procurement and sourcing > Purchase agreements > Purchase agreements.</span></span>
2. <span data-ttu-id="a6eb9-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-111">Click New.</span></span>
3. <span data-ttu-id="a6eb9-112">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a6eb9-113">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="a6eb9-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-114">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="a6eb9-115">No campo Classificação do contrato de compra, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-115">In the Purchase agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="a6eb9-116">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-116">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="a6eb9-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="a6eb9-118">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-118">Expand the General section.</span></span>
10. <span data-ttu-id="a6eb9-119">No campo Data de validade, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-119">In the Expiration date field, enter a date.</span></span>
    * <span data-ttu-id="a6eb9-120">Essa data de vencimento será o padrão para todas as linhas de compromisso e irá determinar por quanto tempo cada compromisso específico é válido.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-120">This expiration date will be the default for all commitment lines and will determine how long each specific commitment is valid.</span></span>  
11. <span data-ttu-id="a6eb9-121">No campo Título do documento, digite um nome para o contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-121">In the Document title field, type a name for your purchase agreement.</span></span>
    * <span data-ttu-id="a6eb9-122">Deixe o campo Comprometimento padrão definido como Comprometimento de quantidade do produto (ou altere-o caso não esteja definido assim).</span><span class="sxs-lookup"><span data-stu-id="a6eb9-122">Leave the Default commitment field set to Product quantity commitment (or change it if it’s not set to this).</span></span>  
    * <span data-ttu-id="a6eb9-123">O valor de compromisso padrão determina suas opções nas linhas do contrato.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-123">The default commitment value determines your options on the agreement lines.</span></span> <span data-ttu-id="a6eb9-124">Se for necessário um novo tipo de compromisso ao criar as linhas do contrato, é preciso alterar o compromisso padrão no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-124">If you need a new commitment type when you’re creating the agreement lines, you need to change the default commitment on the header.</span></span>  <span data-ttu-id="a6eb9-125">Existem 4 tipos de compromissos: Compromisso da quantidade do produto - para uma quantidade específica de um produto; Compromisso de valor do produto - para um valor monetário específico de um produto; Compromisso de valor da categoria do produto - para um valor monetário específico em uma categoria de aquisição em que o valor pode ser para um item de catálogo ou um item não catalogado; Compromisso de valor - para um valor monetário específico que pode ser atendido por qualquer produto ou por qualquer categoria de aquisição.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-125">There are 4 types of commitments: Product quantity commitment - for a specific quantity of a product; Product value commitment - for a specific currency amount of a product; Product category value commitment - for a specific currency amount in a procurement category where the amount can be for a catalog item or a non-catalog item; Value commitment - for a specific currency amount which can be fulfilled by any product or by any procurement category.</span></span>  
12. <span data-ttu-id="a6eb9-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-126">Click OK.</span></span>

## <a name="add-a-commitment"></a><span data-ttu-id="a6eb9-127">Adicionar um compromisso</span><span class="sxs-lookup"><span data-stu-id="a6eb9-127">Add a commitment</span></span>
1. <span data-ttu-id="a6eb9-128">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-128">Click Add line.</span></span>
2. <span data-ttu-id="a6eb9-129">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="a6eb9-130">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-130">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a6eb9-131">Selecione o produto para o qual você deseja adicionar um compromisso.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-131">Select the product you want to add a commitment for.</span></span>
5. <span data-ttu-id="a6eb9-132">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-132">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="a6eb9-133">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-133">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="a6eb9-134">Esta é a quantidade total que você concordou em comprar do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-134">This is the total quantity that you have agreed to buy from your vendor.</span></span>  
7. <span data-ttu-id="a6eb9-135">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-135">In the Unit price field, enter a number.</span></span>
8. <span data-ttu-id="a6eb9-136">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-136">Expand the Line details section.</span></span>
9. <span data-ttu-id="a6eb9-137">Defina a opção Máximo é forçado para Sim.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-137">Set the Max is enforced option to Yes.</span></span>
    * <span data-ttu-id="a6eb9-138">A opção Máximo é forçado limita o uso do compromisso.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-138">The Max is enforced option limits the use of the commitment.</span></span> <span data-ttu-id="a6eb9-139">Você só pode comprar até a quantidade especificada no campo Quantidade para a linha.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-139">You can only purchase up to the quantity that's specified in the Quantity field for the line.</span></span>  
10. <span data-ttu-id="a6eb9-140">Recolha a seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-140">Collapse the Line details section.</span></span>

## <a name="add-header-conditions"></a><span data-ttu-id="a6eb9-141">Adicionar condições de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="a6eb9-141">Add header conditions</span></span>
1. <span data-ttu-id="a6eb9-142">No Painel de Ação, clique em Opções.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-142">On the Action Pane, click Options.</span></span>
2. <span data-ttu-id="a6eb9-143">Clique em Alterar exibição.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-143">Click Change view.</span></span>
3. <span data-ttu-id="a6eb9-144">Clique em Exibição do cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-144">Click Header view.</span></span>
4. <span data-ttu-id="a6eb9-145">Expandir a seção Condições.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-145">Expand the Terms section.</span></span>
5. <span data-ttu-id="a6eb9-146">No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-146">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a6eb9-147">As condições de pagamento da conta do fornecedor são exibidas aqui por padrão.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-147">The payment terms from the vendor account are shown here by default.</span></span>       
6. <span data-ttu-id="a6eb9-148">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-148">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="a6eb9-149">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-149">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="a6eb9-150">No campo Modo de entrega, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-150">In the Mode of delivery field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="a6eb9-151">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-151">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="a6eb9-152">No campo Condições de entrega, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-152">In the Delivery terms field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="a6eb9-153">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-153">In the list, click the link in the selected row.</span></span>

## <a name="confirm-and-activate-the-agreement"></a><span data-ttu-id="a6eb9-154">Confirmar e ativar o contrato</span><span class="sxs-lookup"><span data-stu-id="a6eb9-154">Confirm and activate the agreement</span></span>
1. <span data-ttu-id="a6eb9-155">No Painel de Ação, clique em Contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-155">On the Action Pane, click Purchase agreement.</span></span>
2. <span data-ttu-id="a6eb9-156">Clique em Confirmação.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-156">Click Confirmation.</span></span>
    * <span data-ttu-id="a6eb9-157">Defina a opção Marcar contrato como efetivo para Sim.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-157">Set the Mark agreement as effective option to Yes.</span></span>  
3. <span data-ttu-id="a6eb9-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-158">Click OK.</span></span>
4. <span data-ttu-id="a6eb9-159">No Painel de Ação, clique em Contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-159">On the Action Pane, click Purchase agreement.</span></span>
5. <span data-ttu-id="a6eb9-160">Clique em Confirmações do contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-160">Click Purchase agreement confirmations.</span></span>
    * <span data-ttu-id="a6eb9-161">A opção de Visualizar/Imprimir permite que você gere um documento para o contrato de compra, o qual você poderá imprimir ou enviar ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-161">The Preview/Print option allows you to generate a document for the purchase agreement which you can then print or send to the vendor.</span></span> <span data-ttu-id="a6eb9-162">Se você atualizar o contrato mais tarde e o reconfirmá-lo, ambas as versões serão exibidas aqui.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-162">If you update the agreement later on and re-confirm it, both versions will be shown here.</span></span>  
6. <span data-ttu-id="a6eb9-163">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a6eb9-163">Close the page.</span></span>


