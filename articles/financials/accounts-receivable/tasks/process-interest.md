---
title: Processar juros
description: Este procedimento mostra como criar, imprimir e lançar notas de juros.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fba25c900461fbbf4db0cd3b93847d258704ab4e
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842872"
---
# <a name="process-interest"></a><span data-ttu-id="bc8bc-103">Processar juros</span><span class="sxs-lookup"><span data-stu-id="bc8bc-103">Process interest</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc8bc-104">Este procedimento mostra como criar, imprimir e lançar notas de juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="bc8bc-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="bc8bc-106">Configure o juros no perfil de lançamento</span><span class="sxs-lookup"><span data-stu-id="bc8bc-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="bc8bc-107">Vá para Crédito e coleções > Configuração > Perfis de lançamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-107">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
2. <span data-ttu-id="bc8bc-108">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-108">Click Edit.</span></span>
    * <span data-ttu-id="bc8bc-109">Selecione um código de juros na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-109">Select an interest code from the drop-down list.</span></span> <span data-ttu-id="bc8bc-110">Se você não desejar que os juros sejam calculados para as transações com o perfil de lançamento, deixe o campo em branco.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span>  
    * <span data-ttu-id="bc8bc-111">A guia de restrição de tabela permite que você altere o modo como os juros são processados.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-111">The Table restriction tab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="bc8bc-112">Se este campo estiver definido como Sim, os juros serão calculados para este perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="bc8bc-113">Calcular juros</span><span class="sxs-lookup"><span data-stu-id="bc8bc-113">Calculate interest</span></span>
1. <span data-ttu-id="bc8bc-114">Vá para Crédito e coleções > Juros > Criar notas de juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-114">Go to Credit and collections > Interest > Create interest notes.</span></span>
    * <span data-ttu-id="bc8bc-115">Você deve selecionar os tipos de transação para os quais calculará o juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="bc8bc-116">Todas as transações abertas para esses tipos serão incluídas no cálculo.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-116">All of the open transactions for these types will be included in the calculation.</span></span>  
    * <span data-ttu-id="bc8bc-117">Se você selecionar juros, você calculará juros em juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-117">If you select Interest, you will calculate interest on interest.</span></span> <span data-ttu-id="bc8bc-118">Você pode optar por verificar as leis que regem o cálculo de juros em juros antes de incluir essas transações.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
    * <span data-ttu-id="bc8bc-119">Os juros serão calculados a partir dessa data até "Até data".</span><span class="sxs-lookup"><span data-stu-id="bc8bc-119">Interest will be calculated from this date to the "To date".</span></span> <span data-ttu-id="bc8bc-120">Se você não especificou uma "Data de", então todas as notas de juros não serão canceladas e os juros serão recalculados da data da transação.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-120">If you do not specific a "From date", then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>  
2. <span data-ttu-id="bc8bc-121">Inserir a data da nota de juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-121">Enter the date of the interest note.</span></span>
    * <span data-ttu-id="bc8bc-122">Há três opções de perfil de lançamento: Conta – use o perfil de lançamento que é atribuído ao cliente para cada nota de juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-122">There are three posting profile options:   Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   <span data-ttu-id="bc8bc-123">Seleção - use o perfil de lançamento selecionado no campo Perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-123">Select – Use the posting profile that you select in the Posting profile field.</span></span>   <span data-ttu-id="bc8bc-124">Transação - use o perfil de lançamento individual de transações em que os juros são calculados para cada nota de juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-124">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="bc8bc-125">As transações que não têm um perfil de lançamento atribuído usarão o perfil de lançamento especificado na área Razão e imposto do formulário Parâmetros de conta recebida.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-125">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
    * <span data-ttu-id="bc8bc-126">Selecione um perfil de lançamentos aqui se modificou "Usar um perfil de lançamento de" para "Selecionar".</span><span class="sxs-lookup"><span data-stu-id="bc8bc-126">Select a posting profile here if you changed "Use posting profile from" to "Select".</span></span>  
3. <span data-ttu-id="bc8bc-127">Expanda ou recolha a seção de Registros a serem incluídos.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-127">Expand or collapse the Records to include section.</span></span>
4. <span data-ttu-id="bc8bc-128">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-128">Click Filter.</span></span>
5. <span data-ttu-id="bc8bc-129">No campo Critérios, insira um ID de cliente.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-129">In the Criteria field, enter a Customer ID.</span></span> <span data-ttu-id="bc8bc-130">Por exemplo, insira 'US-001'.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-130">For example, enter 'US-001'..</span></span>
6. <span data-ttu-id="bc8bc-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-131">Click OK.</span></span>
7. <span data-ttu-id="bc8bc-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-132">Click OK.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="bc8bc-133">Imprimir notas de juros</span><span class="sxs-lookup"><span data-stu-id="bc8bc-133">Print interest notes</span></span>
1. <span data-ttu-id="bc8bc-134">Vá para Crédito e coleções > Juros > Revisar e processar notas de juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-134">Go to Credit and collections > Interest > Review and process interest notes.</span></span>
2. <span data-ttu-id="bc8bc-135">No campo Status, selecione 'Criado'.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-135">In the Status field, select 'Created'.</span></span>
3. <span data-ttu-id="bc8bc-136">No campo Impresso, selecione 'Não impresso'.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-136">In the Printed field, select 'Not printed'.</span></span>
4. <span data-ttu-id="bc8bc-137">Clique em Imprimir.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-137">Click Print.</span></span>
5. <span data-ttu-id="bc8bc-138">Expanda ou recolha a seção de Registros a serem incluídos.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-138">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="bc8bc-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-139">Click OK.</span></span>
7. <span data-ttu-id="bc8bc-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-140">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="bc8bc-141">Lançar a nota de juros</span><span class="sxs-lookup"><span data-stu-id="bc8bc-141">Post the interest note</span></span>
1. <span data-ttu-id="bc8bc-142">Selecione uma nota de juros que está pronta para ser lançada (o status é criado).</span><span class="sxs-lookup"><span data-stu-id="bc8bc-142">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="bc8bc-143">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-143">Click Post.</span></span>
3. <span data-ttu-id="bc8bc-144">Digite a data de lançamento para as notas de juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-144">Enter the posting date for the interest note.</span></span>
    * <span data-ttu-id="bc8bc-145">Marque Sim para criar uma transação de contabilidade para cada nota de juros.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-145">Select Yes to create a general ledger transaction for each interest note.</span></span>     <span data-ttu-id="bc8bc-146">Se não marcar Sim, os juros em todas as notas de juros ao cliente serão acumulados e lançados na contabilidade em uma transação.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-146">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="bc8bc-147">Expanda ou recolha a seção de Registros a serem incluídos.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-147">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="bc8bc-148">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-148">Click OK.</span></span>
6. <span data-ttu-id="bc8bc-149">No campo Status, selecione 'Lançado'.</span><span class="sxs-lookup"><span data-stu-id="bc8bc-149">In the Status field, select 'Posted'.</span></span>

