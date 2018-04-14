--- 
title: "Criar uma entrada de diário usando um modelo"
description: "Os comprovantes de diário lançados podem ser salvos como modelos de comprovante e ser aplicados em um novo comprovante de diário."
author: aprilolson
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 5885e90786c15542997deb8fcea7038a39bd0bec
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-journal-entry-using-a-template"></a><span data-ttu-id="f75ec-103">Criar uma entrada de diário usando um modelo</span><span class="sxs-lookup"><span data-stu-id="f75ec-103">Create a journal entry using a template</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f75ec-104">Os comprovantes de diário lançados podem ser salvos como modelos de comprovante e ser aplicados em um novo comprovante de diário.</span><span class="sxs-lookup"><span data-stu-id="f75ec-104">Posted journal vouchers can be saved as Voucher templates and applied in a new journal voucher.</span></span> <span data-ttu-id="f75ec-105">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="f75ec-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="f75ec-106">Contabilidade > Entradas de diários > Diários gerais.</span><span class="sxs-lookup"><span data-stu-id="f75ec-106">General ledger > Journal entries > General journals.</span></span> <span data-ttu-id="f75ec-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f75ec-107">Click New.</span></span>
    * <span data-ttu-id="f75ec-108">Este procedimento começa criando e lançando um comprovante de diário, mas qualquer comprovante de diário lançado anteriormente pode ser salvo como um modelo.</span><span class="sxs-lookup"><span data-stu-id="f75ec-108">This procedure starts by creating and posting a journal voucher, but any previously posted journal voucher can be saved as a template.</span></span>  
2. <span data-ttu-id="f75ec-109">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f75ec-109">In the Name field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="f75ec-110">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="f75ec-110">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="f75ec-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f75ec-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f75ec-112">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="f75ec-112">Click Lines.</span></span>
6. <span data-ttu-id="f75ec-113">Insira uma conta para o Tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="f75ec-113">Enter an account for the Account type.</span></span>
7. <span data-ttu-id="f75ec-114">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f75ec-114">In the Description field, type a value.</span></span>
8. <span data-ttu-id="f75ec-115">Insira um valor no campo Débito.</span><span class="sxs-lookup"><span data-stu-id="f75ec-115">Enter an amount in the Debit field.</span></span>
9. <span data-ttu-id="f75ec-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f75ec-116">Click New.</span></span>
10. <span data-ttu-id="f75ec-117">Insira uma conta diferente para o Tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="f75ec-117">Enter a different account for the Account type.</span></span>
11. <span data-ttu-id="f75ec-118">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f75ec-118">In the Description field, type a value.</span></span>
12. <span data-ttu-id="f75ec-119">Insira um valor no campo Débito.</span><span class="sxs-lookup"><span data-stu-id="f75ec-119">Enter an amount in the Debit field.</span></span>
13. <span data-ttu-id="f75ec-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f75ec-120">Click New.</span></span>
14. <span data-ttu-id="f75ec-121">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="f75ec-121">In the Account field, specify the desired values.</span></span>
15. <span data-ttu-id="f75ec-122">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f75ec-122">In the Description field, type a value.</span></span>
16. <span data-ttu-id="f75ec-123">Insira um valor no campo de crédito para verificar o comprovante.</span><span class="sxs-lookup"><span data-stu-id="f75ec-123">Enter an amount in the Credit field to balance the voucher.</span></span>
17. <span data-ttu-id="f75ec-124">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="f75ec-124">Click Post.</span></span>
18. <span data-ttu-id="f75ec-125">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="f75ec-125">Click Functions.</span></span>
19. <span data-ttu-id="f75ec-126">Clique em Salvar o modelo de comprovante.</span><span class="sxs-lookup"><span data-stu-id="f75ec-126">Click Save voucher template.</span></span>
20. <span data-ttu-id="f75ec-127">Este procedimento pressupõe um tipo de modelo percentual.</span><span class="sxs-lookup"><span data-stu-id="f75ec-127">This procedure assumes a Percent Template type.</span></span> <span data-ttu-id="f75ec-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f75ec-128">Click OK.</span></span>
    * <span data-ttu-id="f75ec-129">• Porcentagem: Os valores do comprovante são convertidos em fatores de porcentagem, que permitem que qualquer valor seja aplicado quando o modelo de comprovante for selecionado.</span><span class="sxs-lookup"><span data-stu-id="f75ec-129">• Percent: The amounts in the voucher are converted into percentage factors, which allows any amount to be applied when the Voucher template is selected.</span></span>  <span data-ttu-id="f75ec-130">• Valor: Os valores reais serão armazenados e serão aplicados.</span><span class="sxs-lookup"><span data-stu-id="f75ec-130">• Amount: The actual amounts will be stored and applied.</span></span>  
21. <span data-ttu-id="f75ec-131">Clique em Diários gerais.</span><span class="sxs-lookup"><span data-stu-id="f75ec-131">Click General journals.</span></span>
22. <span data-ttu-id="f75ec-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f75ec-132">Click New.</span></span>
23. <span data-ttu-id="f75ec-133">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f75ec-133">In the Name field, click the drop-down button to open the lookup.</span></span>
24. <span data-ttu-id="f75ec-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f75ec-134">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="f75ec-135">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="f75ec-135">Click Lines.</span></span>
26. <span data-ttu-id="f75ec-136">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="f75ec-136">Click Functions.</span></span>
27. <span data-ttu-id="f75ec-137">Clique em Selecionar modelo de comprovante.</span><span class="sxs-lookup"><span data-stu-id="f75ec-137">Click Select voucher template.</span></span>
28. <span data-ttu-id="f75ec-138">Encontre o modelo criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f75ec-138">Find the template that you created earlier.</span></span> <span data-ttu-id="f75ec-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f75ec-139">Click OK.</span></span>
    * <span data-ttu-id="f75ec-140">Talvez você precise clicar na etapa anterior e selecionar o modelo correto se outros modelos existirem.</span><span class="sxs-lookup"><span data-stu-id="f75ec-140">You may need to click Previous step and then select the correct template if other templates exist.</span></span>  
29. <span data-ttu-id="f75ec-141">No campo Valor, insira o valor a ser aplicado ao comprovante.</span><span class="sxs-lookup"><span data-stu-id="f75ec-141">In the Amount field, enter the amount to be applied to the voucher.</span></span>
    * <span data-ttu-id="f75ec-142">O campo Valor é apenas exibido se o modelo de comprovante for do tipo Porcentagem.</span><span class="sxs-lookup"><span data-stu-id="f75ec-142">The amount field is only displayed if the voucher template is of type Percent.</span></span>  
30. <span data-ttu-id="f75ec-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f75ec-143">Click OK.</span></span>


