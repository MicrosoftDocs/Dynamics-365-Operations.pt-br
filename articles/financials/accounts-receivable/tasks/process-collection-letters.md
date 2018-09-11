--- 
title: "Processar cartas de cobrança"
description: "Este procedimento mostra como criar, imprimir e lançar cartas de cobrança."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, SysQueryForm, CustCollectionLetterNote
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: fe76f2934360580c4015ea13225b9228cc2780b9
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="process-collection-letters"></a><span data-ttu-id="e7594-103">Processar cartas de cobrança</span><span class="sxs-lookup"><span data-stu-id="e7594-103">Process collection letters</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e7594-104">Este procedimento mostra como criar, imprimir e lançar cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e7594-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="e7594-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="e7594-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="e7594-106">Configurar uma sequência de carta de cobrança no perfil de lançamento</span><span class="sxs-lookup"><span data-stu-id="e7594-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="e7594-107">Vá para Crédito e coleções > Configuração > Perfis de lançamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="e7594-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="e7594-108">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="e7594-108">Click Edit.</span></span>
    * <span data-ttu-id="e7594-109">Selecione uma sequência de carta de cobrança na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e7594-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="e7594-110">Se você não quiser gerar cartas de cobrança para transações usando este perfil de lançamento, deixe o campo em branco.</span><span class="sxs-lookup"><span data-stu-id="e7594-110">If you do not want generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="e7594-111">A guia de restrição de tabela permite que você altere a forma que as cartas de cobrança são processadas.</span><span class="sxs-lookup"><span data-stu-id="e7594-111">The table restriction tab allows you to change the way that collection letters are processed.</span></span> <span data-ttu-id="e7594-112">Se este campo estiver definido como Sim, as cartas de cobrança serão criadas para este perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="e7594-112">If this field is set to Yes, then collection letters will be created for this posting profile.</span></span>  
3. <span data-ttu-id="e7594-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e7594-113">Close the page.</span></span>

## <a name="create-collection-letters"></a><span data-ttu-id="e7594-114">Criar cartas de cobrança</span><span class="sxs-lookup"><span data-stu-id="e7594-114">Create collection letters</span></span>
1. <span data-ttu-id="e7594-115">Vá para Crédito e cobranças > Carta de cobrança > Criar cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e7594-115">Go to Credit and collections > Collection letter > Create collection letters.</span></span>
    * <span data-ttu-id="e7594-116">Você deve selecionar os tipos de transação para os quais cobrará as cartas.</span><span class="sxs-lookup"><span data-stu-id="e7594-116">You must select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="e7594-117">Todas as transações abertas para esses tipos serão incluídas no cálculo.</span><span class="sxs-lookup"><span data-stu-id="e7594-117">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="e7594-118">No campo Carta de coleção, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="e7594-118">In the Collection letter field, select an option.</span></span>
3. <span data-ttu-id="e7594-119">Insira a data da carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e7594-119">Enter the date of the collection letter.</span></span>
    * <span data-ttu-id="e7594-120">Há duas opções de perfil de lançamento: Conta – use o perfil de lançamento que é atribuído à conta do cliente para cada nota de juros.</span><span class="sxs-lookup"><span data-stu-id="e7594-120">There are two posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="e7594-121">Seleção - use o perfil de lançamento selecionado no campo Perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="e7594-121">Select – Use the posting profile that you select in the Posting profile field.</span></span>  
    * <span data-ttu-id="e7594-122">Selecione um perfil de lançamentos, se você modificou "Usar um perfil de lançamento de" para "Selecionar".</span><span class="sxs-lookup"><span data-stu-id="e7594-122">Select a posting profile if you changed "Use posting profile from" to "Select".</span></span>  
4. <span data-ttu-id="e7594-123">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="e7594-123">Expand the Records to include section.</span></span>
5. <span data-ttu-id="e7594-124">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="e7594-124">Click Filter.</span></span>
6. <span data-ttu-id="e7594-125">No campo Critérios, insira um ID do Cliente.</span><span class="sxs-lookup"><span data-stu-id="e7594-125">In the Criteria field, In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="e7594-126">Por exemplo, insira 'US-001'.</span><span class="sxs-lookup"><span data-stu-id="e7594-126">For example, enter 'US-001'..</span></span>
7. <span data-ttu-id="e7594-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e7594-127">Click OK.</span></span>
8. <span data-ttu-id="e7594-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e7594-128">Click OK.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="e7594-129">Imprimir cartas de cobrança</span><span class="sxs-lookup"><span data-stu-id="e7594-129">Print collection letters</span></span>
1. <span data-ttu-id="e7594-130">Vá para Crédito e cobranças > Carta de cobrança > Revisar e processar cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e7594-130">Go to Credit and collections > Collection letter > Review and process collection letters.</span></span>
2. <span data-ttu-id="e7594-131">No campo Status, selecione 'Criado'.</span><span class="sxs-lookup"><span data-stu-id="e7594-131">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="e7594-132">No campo Impresso, selecione 'Não impresso'.</span><span class="sxs-lookup"><span data-stu-id="e7594-132">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="e7594-133">Clique em Imprimir.</span><span class="sxs-lookup"><span data-stu-id="e7594-133">Click Print.</span></span>
5. <span data-ttu-id="e7594-134">Clique em Nota de carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e7594-134">Click Collection letter note.</span></span>
6. <span data-ttu-id="e7594-135">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="e7594-135">Expand the Records to include section.</span></span>
7. <span data-ttu-id="e7594-136">Insira a data de fechamento para lançamentos</span><span class="sxs-lookup"><span data-stu-id="e7594-136">Enter the cutoff date for postings</span></span>
8. <span data-ttu-id="e7594-137">Clique em OK para imprimir a carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e7594-137">Click OK to print the collection letter.</span></span>

## <a name="post-the-collection-letter"></a><span data-ttu-id="e7594-138">Lança a carta de cobrança</span><span class="sxs-lookup"><span data-stu-id="e7594-138">Post the collection letter</span></span>
1. <span data-ttu-id="e7594-139">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="e7594-139">Click Post.</span></span>
2. <span data-ttu-id="e7594-140">Inserir a nova data de lançamento para a carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e7594-140">Enter the posting date for the collection letter.</span></span>
3. <span data-ttu-id="e7594-141">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="e7594-141">Expand the Records to include section.</span></span>
4. <span data-ttu-id="e7594-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e7594-142">Click OK.</span></span>
5. <span data-ttu-id="e7594-143">No campo Status, selecione 'Lançado'.</span><span class="sxs-lookup"><span data-stu-id="e7594-143">In the Status field, select 'Posted'.</span></span>
6. <span data-ttu-id="e7594-144">No campo Impresso, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="e7594-144">In the Printed field, select an option.</span></span>


