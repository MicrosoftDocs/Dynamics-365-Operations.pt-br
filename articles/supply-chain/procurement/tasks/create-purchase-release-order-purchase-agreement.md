--- 
title: "Criar uma ordem de liberação de compra de um contrato de compra"
description: "Este procedimento mostra como utilizar um contrato de compra quando você cria uma ordem de compra."
author: mkirknel
manager: AnnBe
ms.date: 12/04/2015
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: cecda03dd4d224d4319f2b0b196560389bb54195
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a><span data-ttu-id="e2f58-103">Criar uma ordem de liberação de compra de um contrato de compra</span><span class="sxs-lookup"><span data-stu-id="e2f58-103">Create a purchase release order from a purchase agreement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e2f58-104">Este procedimento mostra como utilizar um contrato de compra quando você cria uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e2f58-104">This procedure shows how to use a purchase agreement when you create a purchase order.</span></span> <span data-ttu-id="e2f58-105">O contrato de compra deve ser aplicado quando você cria a ordem de compra porque existem condições gerais que devem ser copiadas para o cabeçalho da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e2f58-105">The purchase agreement has to be applied when you create the purchase order because there are general terms that should be copied to the purchase order header.</span></span> <span data-ttu-id="e2f58-106">Normalmente essa tarefa é realizada por um agente de compras.</span><span class="sxs-lookup"><span data-stu-id="e2f58-106">Typically this task would be carried out by a purchasing agent.</span></span> <span data-ttu-id="e2f58-107">Como um pré-requisito para esta guia, você deve ter um contrato de compra em vigor com um compromisso de quantidade do produto para um fornecedor e itens.</span><span class="sxs-lookup"><span data-stu-id="e2f58-107">As a prerequisite for this guide, you must have an effective purchase agreement with a product quantity commitment for a vendor and items.</span></span> <span data-ttu-id="e2f58-108">O mesmo procedimento pode ser utilizado se você tiver um contrato de compra com outros tipos de compromissos.</span><span class="sxs-lookup"><span data-stu-id="e2f58-108">The same procedure can be used if you have a purchase agreement with other types of commitments.</span></span> <span data-ttu-id="e2f58-109">Você pode executar este guia na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="e2f58-109">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="e2f58-110">Se você estiver usando USMF, é possível executar primeiro o guia “Criar um contrato de compra“ para configurar as pré-condições necessárias para este guia.</span><span class="sxs-lookup"><span data-stu-id="e2f58-110">If you’re using USMF, you can run the “Create a purchase agreement” guide first to set up the necessary preconditions for this guide.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="e2f58-111">Crie uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="e2f58-111">Create a purchase order</span></span>
1. <span data-ttu-id="e2f58-112">Abra o espaço de trabalho de preparação de ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="e2f58-112">Open the purchase order preparation workspace.</span></span>
2. <span data-ttu-id="e2f58-113">Clique em Nova ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e2f58-113">Click New purchase order.</span></span>
3. <span data-ttu-id="e2f58-114">No campo Conta de fornecedor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e2f58-114">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e2f58-115">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="e2f58-115">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e2f58-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e2f58-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e2f58-117">Alternar a expansão da seção Geral.</span><span class="sxs-lookup"><span data-stu-id="e2f58-117">Toggle the expansion of the General section.</span></span>
7. <span data-ttu-id="e2f58-118">No campo Contrato de compra, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e2f58-118">In the Purchase agreement field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e2f58-119">Todos os contratos disponíveis para o fornecedor estão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="e2f58-119">All available agreements for the vendor are listed here.</span></span> <span data-ttu-id="e2f58-120">Encontre o contrato efetivo que você deseja utilizar.</span><span class="sxs-lookup"><span data-stu-id="e2f58-120">Find the effective agreement that you want to use.</span></span>  
8. <span data-ttu-id="e2f58-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e2f58-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="e2f58-122">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="e2f58-122">Click Yes.</span></span>
10. <span data-ttu-id="e2f58-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2f58-123">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="e2f58-124">Adicionar uma linha</span><span class="sxs-lookup"><span data-stu-id="e2f58-124">Add a line</span></span>
1. <span data-ttu-id="e2f58-125">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e2f58-125">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="e2f58-126">Se existem dimensões específicas de estoque ou de local no compromisso você deve inserir os mesmos valores na linha da ordem de compra para usar o contrato.</span><span class="sxs-lookup"><span data-stu-id="e2f58-126">If there are specific inventory or location dimensions on the commitment you must enter the same values on the purchase order line to make use of the agreement.</span></span>  
2. <span data-ttu-id="e2f58-127">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e2f58-127">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e2f58-128">O local pode já estar preenchido com o valor padrão da ordem, ou do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e2f58-128">The site may already be populated with the default value from the order, or from the vendor.</span></span> <span data-ttu-id="e2f58-129">Se esse for o caso, ignore essa etapa.</span><span class="sxs-lookup"><span data-stu-id="e2f58-129">If this is the case, skip this step.</span></span>  
3. <span data-ttu-id="e2f58-130">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="e2f58-130">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="e2f58-131">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e2f58-131">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="e2f58-132">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="e2f58-132">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="e2f58-133">Confirme que o preço foi copiado do compromisso.</span><span class="sxs-lookup"><span data-stu-id="e2f58-133">Validate that the price is copied from the commitment.</span></span>  

## <a name="look-up-the-commitment"></a><span data-ttu-id="e2f58-134">Pesquisar o compromisso</span><span class="sxs-lookup"><span data-stu-id="e2f58-134">Look up the commitment</span></span>
1. <span data-ttu-id="e2f58-135">Clique em Atualizar linha.</span><span class="sxs-lookup"><span data-stu-id="e2f58-135">Click Update line.</span></span>
2. <span data-ttu-id="e2f58-136">Clique em Anexado.</span><span class="sxs-lookup"><span data-stu-id="e2f58-136">Click Attached.</span></span>
    * <span data-ttu-id="e2f58-137">Aqui você pode obter detalhes do contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="e2f58-137">Here you can get details for the purchase agreement.</span></span> <span data-ttu-id="e2f58-138">Por exemplo, é possível ver o preço e ver se o preço e o desconto são fixos, o que significa que se você alterar o preço ou o desconto na ordem de compra para um valor diferente daquele do compromisso, o sistema removerá a ligação para que a linha da ordem de compra não satisfaça o compromisso.</span><span class="sxs-lookup"><span data-stu-id="e2f58-138">For example, you can see the price and whether the price and discount are fixed, which means that if you change price or discount on the purchase order to a different value than on the commitment, the system will remove the link so the purchase order line does not fulfill the commitment.</span></span> <span data-ttu-id="e2f58-139">Também é possível verificar se a opção Máximo é forçado está selecionada, o que significa que a quantidade do compromisso não pode ser excedida através da soma de todas as compras que satisfaçam o compromisso.</span><span class="sxs-lookup"><span data-stu-id="e2f58-139">You can also see if the Max is enforced option is selected, which means that the quantity on the commitment cannot be exceeded by summing all of the purchases that fulfill the commitment.</span></span>  
3. <span data-ttu-id="e2f58-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e2f58-140">Close the page.</span></span>

## <a name="look-up-the-purchase-agreement"></a><span data-ttu-id="e2f58-141">Pesquisar o contrato de compra</span><span class="sxs-lookup"><span data-stu-id="e2f58-141">Look up the purchase agreement</span></span>
1. <span data-ttu-id="e2f58-142">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="e2f58-142">On the Action Pane, click General.</span></span>
2. <span data-ttu-id="e2f58-143">Clique em Contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="e2f58-143">Click Purchase agreement.</span></span>
3. <span data-ttu-id="e2f58-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e2f58-144">Close the page.</span></span>
4. <span data-ttu-id="e2f58-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e2f58-145">Close the page.</span></span>


