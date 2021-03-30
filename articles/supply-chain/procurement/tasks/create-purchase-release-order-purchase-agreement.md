---
title: Criar uma ordem de liberação de compra de um contrato de compra
description: Este procedimento mostra como utilizar um contrato de compra quando você cria uma ordem de compra.
author: RichardLuan
manager: tfehr
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4e9a0551c0755fd006fc030d2e1bf4f28efe951
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211946"
---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a><span data-ttu-id="829a6-103">Criar uma ordem de liberação de compra de um contrato de compra</span><span class="sxs-lookup"><span data-stu-id="829a6-103">Create a purchase release order from a purchase agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="829a6-104">Este procedimento mostra como utilizar um contrato de compra quando você cria uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="829a6-104">This procedure shows how to use a purchase agreement when you create a purchase order.</span></span> <span data-ttu-id="829a6-105">O contrato de compra deve ser aplicado quando você cria a ordem de compra porque existem condições gerais que devem ser copiadas para o cabeçalho da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="829a6-105">The purchase agreement has to be applied when you create the purchase order because there are general terms that should be copied to the purchase order header.</span></span> <span data-ttu-id="829a6-106">Normalmente essa tarefa é realizada por um agente de compras.</span><span class="sxs-lookup"><span data-stu-id="829a6-106">Typically this task would be carried out by a purchasing agent.</span></span> <span data-ttu-id="829a6-107">Como um pré-requisito para esta guia, você deve ter um contrato de compra em vigor com um compromisso de quantidade do produto para um fornecedor e itens.</span><span class="sxs-lookup"><span data-stu-id="829a6-107">As a prerequisite for this guide, you must have an effective purchase agreement with a product quantity commitment for a vendor and items.</span></span> <span data-ttu-id="829a6-108">O mesmo procedimento pode ser utilizado se você tiver um contrato de compra com outros tipos de compromissos.</span><span class="sxs-lookup"><span data-stu-id="829a6-108">The same procedure can be used if you have a purchase agreement with other types of commitments.</span></span> <span data-ttu-id="829a6-109">Você pode executar este guia na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="829a6-109">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="829a6-110">Se você estiver usando USMF, é possível executar primeiro o guia "Criar um contrato de compra" para configurar as pré-condições necessárias para este guia.</span><span class="sxs-lookup"><span data-stu-id="829a6-110">If you're using USMF, you can run the "Create a purchase agreement" guide first to set up the necessary preconditions for this guide.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="829a6-111">Criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="829a6-111">Create a purchase order</span></span>
1. <span data-ttu-id="829a6-112">No **Painel de Navegação**, vá para **Espaços de trabalho > Preparação da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="829a6-112">In the **Navigation pane**, go to **Workspaces > Purchase order preparation**.</span></span> 
2. <span data-ttu-id="829a6-113">Clique em **Nova ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="829a6-113">Click **New purchase order**.</span></span>
3. <span data-ttu-id="829a6-114">No campo **Conta de fornecedor**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="829a6-114">In the **Vendor account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="829a6-115">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="829a6-115">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="829a6-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="829a6-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="829a6-117">Expanda a Guia Rápida **Geral**.</span><span class="sxs-lookup"><span data-stu-id="829a6-117">Expand the **General** fastTab.</span></span>
7. <span data-ttu-id="829a6-118">No campo **Contrato de compra**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="829a6-118">In the **Purchase agreement** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="829a6-119">Todos os contratos disponíveis para o fornecedor estão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="829a6-119">All available agreements for the vendor are listed here.</span></span> <span data-ttu-id="829a6-120">Encontre o contrato efetivo que você deseja utilizar.</span><span class="sxs-lookup"><span data-stu-id="829a6-120">Find the effective agreement that you want to use.</span></span>  
8. <span data-ttu-id="829a6-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="829a6-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="829a6-122">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="829a6-122">Click **Yes**.</span></span>
10. <span data-ttu-id="829a6-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="829a6-123">Click **OK**.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="829a6-124">Adicionar uma linha</span><span class="sxs-lookup"><span data-stu-id="829a6-124">Add a line</span></span>
1. <span data-ttu-id="829a6-125">No campo **Número de item**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="829a6-125">In the **Item number** field, type a value.</span></span> <span data-ttu-id="829a6-126">Se existem dimensões específicas de estoque ou de local no compromisso você deve inserir os mesmos valores na linha da ordem de compra para usar o contrato.</span><span class="sxs-lookup"><span data-stu-id="829a6-126">If there are specific inventory or location dimensions on the commitment you must enter the same values on the purchase order line to make use of the agreement.</span></span>  
2. <span data-ttu-id="829a6-127">No campo **Site**, clique no botão de menu suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="829a6-127">In the **Site** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="829a6-128">O local pode já estar preenchido com o valor padrão da ordem, ou do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="829a6-128">The site may already be populated with the default value from the order, or from the vendor.</span></span> <span data-ttu-id="829a6-129">Se esse for o caso, ignore essa etapa.</span><span class="sxs-lookup"><span data-stu-id="829a6-129">If this is the case, skip this step.</span></span>  
3. <span data-ttu-id="829a6-130">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="829a6-130">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="829a6-131">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="829a6-131">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="829a6-132">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="829a6-132">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="829a6-133">Confirme que o preço foi copiado do compromisso.</span><span class="sxs-lookup"><span data-stu-id="829a6-133">Validate that the price is copied from the commitment.</span></span>  

## <a name="look-up-the-commitment"></a><span data-ttu-id="829a6-134">Pesquisar o compromisso</span><span class="sxs-lookup"><span data-stu-id="829a6-134">Look up the commitment</span></span>
1. <span data-ttu-id="829a6-135">Clique em **Atualizar linha**.</span><span class="sxs-lookup"><span data-stu-id="829a6-135">Click **Update line**.</span></span>
2. <span data-ttu-id="829a6-136">Clique em **Anexado**.</span><span class="sxs-lookup"><span data-stu-id="829a6-136">Click **Attached**.</span></span> <span data-ttu-id="829a6-137">Aqui você pode obter detalhes do contrato de compra.</span><span class="sxs-lookup"><span data-stu-id="829a6-137">Here you can get details for the purchase agreement.</span></span> <span data-ttu-id="829a6-138">Por exemplo, é possível ver o preço e ver se o preço e o desconto são fixos, o que significa que se você alterar o preço ou o desconto na ordem de compra para um valor diferente daquele do compromisso, o sistema removerá a ligação para que a linha da ordem de compra não satisfaça o compromisso.</span><span class="sxs-lookup"><span data-stu-id="829a6-138">For example, you can see the price and whether the price and discount are fixed, which means that if you change price or discount on the purchase order to a different value than on the commitment, the system will remove the link so the purchase order line does not fulfill the commitment.</span></span> <span data-ttu-id="829a6-139">Também é possível verificar se a opção Máximo é forçado está selecionada, o que significa que a quantidade do compromisso não pode ser excedida através da soma de todas as compras que satisfaçam o compromisso.</span><span class="sxs-lookup"><span data-stu-id="829a6-139">You can also see if the Max is enforced option is selected, which means that the quantity on the commitment cannot be exceeded by summing all of the purchases that fulfill the commitment.</span></span>  
3. <span data-ttu-id="829a6-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="829a6-140">Close the page.</span></span>

## <a name="look-up-the-purchase-agreement"></a><span data-ttu-id="829a6-141">Pesquisar o contrato de compra</span><span class="sxs-lookup"><span data-stu-id="829a6-141">Look up the purchase agreement</span></span>
1. <span data-ttu-id="829a6-142">No **Painel de Ações**, clique em **Geral**.</span><span class="sxs-lookup"><span data-stu-id="829a6-142">On the **Action Pane**, click **General**.</span></span>
2. <span data-ttu-id="829a6-143">Clique em **Contrato de compra**.</span><span class="sxs-lookup"><span data-stu-id="829a6-143">Click **Purchase agreement**.</span></span>
3. <span data-ttu-id="829a6-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="829a6-144">Close the page.</span></span>
4. <span data-ttu-id="829a6-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="829a6-145">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]