--- 
title: "Aprovar fornecedores para produtos específicos"
description: "Este procedimento mostra como aprovar fornecedores de produto específico."
author: mkirknel
manager: AnnBe
ms.date: 11/02/2016
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
ms.openlocfilehash: ffc58d2afe73fa2290e4e73a058d47ffd64b8d54
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="approve-vendors-for-specific-products"></a><span data-ttu-id="bd637-103">Aprovar fornecedores para produtos específicos</span><span class="sxs-lookup"><span data-stu-id="bd637-103">Approve vendors for specific products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd637-104">Este procedimento mostra como aprovar fornecedores de produto específico.</span><span class="sxs-lookup"><span data-stu-id="bd637-104">This procedure shows you how to approve vendors for specific products.</span></span> <span data-ttu-id="bd637-105">Isso permite que você controle fornecedores que podem ser usados quando os produtos são adicionados a uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="bd637-105">This allows you to control which vendors can be used when the product is added to a purchase order.</span></span> <span data-ttu-id="bd637-106">Você pode usar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="bd637-106">You can use this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="bd637-107">Normalmente essa tarefa é realizada por um Gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="bd637-107">This task would typically be carried out by a Purchasing manager.</span></span>

1. <span data-ttu-id="bd637-108">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="bd637-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="bd637-109">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="bd637-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="bd637-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="bd637-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bd637-111">Expandir a seção Compra.</span><span class="sxs-lookup"><span data-stu-id="bd637-111">Expand the Purchase section.</span></span>
    * <span data-ttu-id="bd637-112">Se houver um fornecedor principal mostrado no campo do fornecedor, você precisará adicionar esse fornecedor como um fornecedor aprovado nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="bd637-112">If there is a primary vendor shown in the Vendor field, then you need to add this vendor as an approved vendor in the following steps.</span></span> <span data-ttu-id="bd637-113">Faça uma nota do número do fornecedor, se for mostrado.</span><span class="sxs-lookup"><span data-stu-id="bd637-113">Make a note of the vendor number, if one is shown.</span></span>  
5. <span data-ttu-id="bd637-114">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="bd637-114">On the Action Pane, click Purchase.</span></span>
6. <span data-ttu-id="bd637-115">Clique em Configuração.</span><span class="sxs-lookup"><span data-stu-id="bd637-115">Click Setup.</span></span>
7. <span data-ttu-id="bd637-116">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="bd637-116">Click Add.</span></span>
8. <span data-ttu-id="bd637-117">No campo Fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="bd637-117">In the Vendor field, enter or select a value.</span></span>
    * <span data-ttu-id="bd637-118">Selecione o fornecedor aprovado.</span><span class="sxs-lookup"><span data-stu-id="bd637-118">Select the approved vendor.</span></span> <span data-ttu-id="bd637-119">Pelo menos uma das linhas tem de ser o fornecedor principal se houver um registro do produto.</span><span class="sxs-lookup"><span data-stu-id="bd637-119">At least one of the lines has to be the primary vendor if there was one in the product record.</span></span> <span data-ttu-id="bd637-120">Se você tiver feito uma anotação do número do fornecedor anterior, selecione-a aqui.</span><span class="sxs-lookup"><span data-stu-id="bd637-120">If you made a note of the vendor number earlier, select it here.</span></span>  
9. <span data-ttu-id="bd637-121">No campo Vencimento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="bd637-121">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="bd637-122">Escolha uma data que é daqui alguns meses.</span><span class="sxs-lookup"><span data-stu-id="bd637-122">Choose a date a that is a few months ahead.</span></span>  
10. <span data-ttu-id="bd637-123">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="bd637-123">Click Add.</span></span>
11. <span data-ttu-id="bd637-124">No campo Fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="bd637-124">In the Vendor field, enter or select a value.</span></span>
12. <span data-ttu-id="bd637-125">No campo Vencimento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="bd637-125">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="bd637-126">Escolha uma data diferente da data de vencimento anterior.</span><span class="sxs-lookup"><span data-stu-id="bd637-126">Choose a date that is different than the previous expiration date.</span></span>  
13. <span data-ttu-id="bd637-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd637-127">Close the page.</span></span>
14. <span data-ttu-id="bd637-128">Clique em Fornecedores aprovados.</span><span class="sxs-lookup"><span data-stu-id="bd637-128">Click Approved vendors.</span></span>
15. <span data-ttu-id="bd637-129">No campo Vencimento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="bd637-129">In the Expiration field, enter a date.</span></span>
    * <span data-ttu-id="bd637-130">Essa data atua como um filtro para que você possa ver quais os fornecedores são aprovados até uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="bd637-130">This date acts as a filter so you can see who the approved vendors are, up to a certain date.</span></span>  
16. <span data-ttu-id="bd637-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd637-131">Close the page.</span></span>
17. <span data-ttu-id="bd637-132">Clique em Período efetivo.</span><span class="sxs-lookup"><span data-stu-id="bd637-132">Click Effective period.</span></span>
18. <span data-ttu-id="bd637-133">Em Exibir fornecedores ultrapassados por campo, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="bd637-133">In the Show vendors expired by field, enter a date.</span></span>
    * <span data-ttu-id="bd637-134">Você pode usar a página para identificar os fornecedores em que o status de aprovação expirará após uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="bd637-134">You can use this page to identify vendors where the approval status will expire after a certain date.</span></span>  
19. <span data-ttu-id="bd637-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd637-135">Close the page.</span></span>
20. <span data-ttu-id="bd637-136">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="bd637-136">Click Edit.</span></span>
21. <span data-ttu-id="bd637-137">No campo Método de verificação de fornecedores aprovados, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="bd637-137">In the Approved vendor check method field, select an option.</span></span>
    * <span data-ttu-id="bd637-138">Este campo permite que você selecione a diretiva para o que deve acontecer se os produtos forem adicionados a uma linha da ordem de compra no qual o fornecedor não é um fornecedor aprovado.</span><span class="sxs-lookup"><span data-stu-id="bd637-138">This field allows you to select the policy for what should happen if the product is added to a purchase order line where the vendor is not an approved vendor.</span></span>  
22. <span data-ttu-id="bd637-139">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="bd637-139">Click Save.</span></span>
23. <span data-ttu-id="bd637-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd637-140">Close the page.</span></span>
24. <span data-ttu-id="bd637-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd637-141">Close the page.</span></span>
25. <span data-ttu-id="bd637-142">Vá para Aquisição e fornecimento > Fornecedores > Relações fornecedor/item > Lista de fornecedores aprovados por item.</span><span class="sxs-lookup"><span data-stu-id="bd637-142">Go to Procurement and sourcing > Vendors > Vendor/item relations > Approved vendor list by item.</span></span>
    * <span data-ttu-id="bd637-143">Essa página apresenta uma visão geral de todos os produtos e fornecedores aprovados.</span><span class="sxs-lookup"><span data-stu-id="bd637-143">This page gives you an overview of all products and the approved vendors.</span></span>  
26. <span data-ttu-id="bd637-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd637-144">Close the page.</span></span>
27. <span data-ttu-id="bd637-145">Vá para Aquisição e fornecimento > Fornecedores > Todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="bd637-145">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
    * <span data-ttu-id="bd637-146">Também é possível partir de um fornecedor e ir para a lista de produtos aprovados da conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="bd637-146">You can also start from a vendor and then go to the list of approved products for that vendor account.</span></span>  
28. <span data-ttu-id="bd637-147">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="bd637-147">In the list, find and select the desired record.</span></span>
29. <span data-ttu-id="bd637-148">No Painel de Ação, clique em Aquisição.</span><span class="sxs-lookup"><span data-stu-id="bd637-148">On the Action Pane, click Procurement.</span></span>
30. <span data-ttu-id="bd637-149">Clique em Lista de fornecedores aprovados por fornecedor.</span><span class="sxs-lookup"><span data-stu-id="bd637-149">Click Approved vendor list by vendor.</span></span>
31. <span data-ttu-id="bd637-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd637-150">Close the page.</span></span>
32. <span data-ttu-id="bd637-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bd637-151">Close the page.</span></span>


