---
title: Criar uma entrada de diário usando modelo
description: Os comprovantes de diário lançados podem ser salvos como modelos de comprovante e ser aplicados em um novo comprovante de diário.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 234cfb98cc07f6c8c81821584e4e1d509d033477
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988565"
---
# <a name="create-a-journal-entry-using-template"></a><span data-ttu-id="fcc44-103">Criar uma entrada de diário usando modelo</span><span class="sxs-lookup"><span data-stu-id="fcc44-103">Create a journal entry using template</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fcc44-104">Os comprovantes de diário lançados podem ser salvos como modelos de comprovante e ser aplicados em um novo comprovante de diário.</span><span class="sxs-lookup"><span data-stu-id="fcc44-104">Posted journal vouchers can be saved as Voucher templates and applied in a new journal voucher.</span></span> <span data-ttu-id="fcc44-105">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="fcc44-105">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="fcc44-106">Vá até **Painel de Navegação > Módulos > Contabilidade > Entradas de diário > Diários gerais**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-106">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
2. <span data-ttu-id="fcc44-107">No **Painel de Ações**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-107">On the **Action pane**, click **New**.</span></span> <span data-ttu-id="fcc44-108">Este procedimento começa criando e lançando um comprovante de diário, mas qualquer comprovante de diário lançado anteriormente pode ser salvo como um modelo.</span><span class="sxs-lookup"><span data-stu-id="fcc44-108">This procedure starts by creating and posting a journal voucher, but any previously posted journal voucher can be saved as a template.</span></span>  
3. <span data-ttu-id="fcc44-109">No campo **Nome**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcc44-109">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="fcc44-110">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="fcc44-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="fcc44-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcc44-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="fcc44-112">Clique em **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-112">Click **Lines**.</span></span>
7. <span data-ttu-id="fcc44-113">No campo **Tipo de conta**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="fcc44-113">In the **Account type** field, type a value.</span></span>
8. <span data-ttu-id="fcc44-114">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fcc44-114">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="fcc44-115">No campo **Débito**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fcc44-115">In the **Debit** field, type a value.</span></span>
10. <span data-ttu-id="fcc44-116">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-116">Click **New**.</span></span>
11. <span data-ttu-id="fcc44-117">No campo **Tipo de conta**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="fcc44-117">In the **Account type** field, type a value.</span></span>
12. <span data-ttu-id="fcc44-118">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fcc44-118">In the **Description** field, type a value.</span></span>
13. <span data-ttu-id="fcc44-119">No campo **Débito**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fcc44-119">In the **Debit** field, type a value.</span></span>
14. <span data-ttu-id="fcc44-120">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-120">Click **New**.</span></span>
14. <span data-ttu-id="fcc44-121">No campo **Conta**, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="fcc44-121">In the **Account** field, specify the desired values.</span></span>
15. <span data-ttu-id="fcc44-122">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fcc44-122">In the **Description** field, type a value.</span></span>
16. <span data-ttu-id="fcc44-123">No campo **Crédito**, digite um valor para verificar o comprovante.</span><span class="sxs-lookup"><span data-stu-id="fcc44-123">In the **Credit** field, type a value to balance the voucher.</span></span>
17. <span data-ttu-id="fcc44-124">No **Painel de Ações**, clique em **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-124">On the **Action pane**, click **Post**.</span></span>
18. <span data-ttu-id="fcc44-125">Clique em **Funções**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-125">Click **Functions**.</span></span>
19. <span data-ttu-id="fcc44-126">Clique no modelo **Salvar comprovante**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-126">Click **Save voucher** template.</span></span>
20. <span data-ttu-id="fcc44-127">Este procedimento pressupõe um tipo **Modelo percentual**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-127">This procedure assumes a **Percent Template** type.</span></span> <span data-ttu-id="fcc44-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fcc44-128">Click OK.</span></span>
    - <span data-ttu-id="fcc44-129">Porcentagem: os valores do comprovante são convertidos em fatores de porcentagem, que permitem que qualquer valor seja aplicado quando o modelo de comprovante é selecionado.</span><span class="sxs-lookup"><span data-stu-id="fcc44-129">Percent: The amounts in the voucher are converted into percentage factors, which allows any amount to be applied when the Voucher template is selected.</span></span>
    - <span data-ttu-id="fcc44-130">Valor: os valores reais serão armazenados e serão aplicados.</span><span class="sxs-lookup"><span data-stu-id="fcc44-130">Amount: The actual amounts will be stored and applied.</span></span>  
21. <span data-ttu-id="fcc44-131">Clique em **Diários gerais**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-131">Click **General journals**.</span></span>
22. <span data-ttu-id="fcc44-132">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-132">Click **New**.</span></span>
23. <span data-ttu-id="fcc44-133">No campo **Nome**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcc44-133">In the **Name** field, click the drop-down button to open the lookup.</span></span>
24. <span data-ttu-id="fcc44-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcc44-134">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="fcc44-135">Clique em **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-135">Click **Lines**.</span></span>
26. <span data-ttu-id="fcc44-136">Clique em **Funções**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-136">Click **Functions**.</span></span>
27. <span data-ttu-id="fcc44-137">Clique em **Selecionar modelo de comprovante**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-137">Click **Select voucher template**.</span></span>
28. <span data-ttu-id="fcc44-138">Encontre o modelo criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fcc44-138">Find the template that you created earlier.</span></span> <span data-ttu-id="fcc44-139">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-139">Click **OK**.</span></span> <span data-ttu-id="fcc44-140">Talvez você precise clicar em **Etapa anterior** e selecionar o modelo correto se outros modelos existirem.</span><span class="sxs-lookup"><span data-stu-id="fcc44-140">You may need to click **Previous step** and then select the correct template if other templates exist.</span></span>  
29. <span data-ttu-id="fcc44-141">No campo **Valor**, insira o valor a ser aplicado ao comprovante.</span><span class="sxs-lookup"><span data-stu-id="fcc44-141">In the **Amount** field, enter the amount to be applied to the voucher.</span></span> <span data-ttu-id="fcc44-142">O campo **Valor** é apenas exibido se o modelo de comprovante for do tipo Porcentagem.</span><span class="sxs-lookup"><span data-stu-id="fcc44-142">The **Amount** field is only displayed if the voucher template is of type Percent.</span></span>  
30. <span data-ttu-id="fcc44-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fcc44-143">Click **OK**.</span></span>

