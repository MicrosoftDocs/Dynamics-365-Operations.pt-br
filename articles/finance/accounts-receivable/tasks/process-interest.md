---
title: Processar juros
description: Este procedimento mostra como criar, imprimir e lançar notas de juros.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
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
ms.openlocfilehash: 093fbd23f9fcaf62db9988a98a94b8cebf582768
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140136"
---
# <a name="process-interest"></a><span data-ttu-id="e6ce5-103">Processar juros</span><span class="sxs-lookup"><span data-stu-id="e6ce5-103">Process interest</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e6ce5-104">Este procedimento mostra como criar, imprimir e lançar notas de juros.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="e6ce5-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="e6ce5-106">Configure o juros no perfil de lançamento</span><span class="sxs-lookup"><span data-stu-id="e6ce5-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="e6ce5-107">No **Painel de navegação**, vá para **Módulos > Crédito e coleções > Configuração > Perfis de lançamentos de cliente**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-107">In the **Navigation pane**, go to **Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="e6ce5-108">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-108">Click **Edit**.</span></span>
3. <span data-ttu-id="e6ce5-109">Na **Guia Rápida Configuração**, no campo **Código de juros**, selecione um código de juros na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-109">In the **Setup fastTab**, in the **Interest code** field, select an interest code from the drop-down list.</span></span> <span data-ttu-id="e6ce5-110">Se você não desejar que os juros sejam calculados para as transações com o perfil de lançamento, deixe o campo em branco.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span> <span data-ttu-id="e6ce5-111">A guia rápida **Restrição de tabela** permite que você altere o modo como os juros são processados.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-111">The **Table restriction** fastTab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="e6ce5-112">Se este campo estiver definido como Sim, os juros serão calculados para este perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="e6ce5-113">Calcular juros</span><span class="sxs-lookup"><span data-stu-id="e6ce5-113">Calculate interest</span></span>
1. <span data-ttu-id="e6ce5-114">No **Painel de navegação**, vá para **Módulos > Crédito e coleções > Juros > Criar notas de juros**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-114">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Create interest notes**.</span></span>
2. <span data-ttu-id="e6ce5-115">Você deve selecionar os tipos de transação para os quais calculará o juros.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="e6ce5-116">Todas as transações abertas para esses tipos serão incluídas no cálculo.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="e6ce5-117">Se você definir **Juros** como "Sim", você calculará juros em juros.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-117">If you set **Interest** to 'Yes', you will calculate interest on interest.</span></span> <span data-ttu-id="e6ce5-118">Você pode optar por verificar as leis que regem o cálculo de juros em juros antes de incluir essas transações.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
4. <span data-ttu-id="e6ce5-119">No campo **A partir da data**, insira uma data a partir da qual os juros serão calculados.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-119">In the **From date** field, enter a date from which the interest will be calculated.</span></span> <span data-ttu-id="e6ce5-120">Se você não especificou uma **Data inicial**, então todas as notas de juros não lançadas serão canceladas e os juros serão recalculados da data da transação.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-120">If you do not specific a **From date**, then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>
5. <span data-ttu-id="e6ce5-121">No campo **Até**, insira uma data para a qual os juros seriam calculados.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-121">In the **To date** field, enter a date to which the interest would be calculated.</span></span>
6. <span data-ttu-id="e6ce5-122">No campo **Usar perfil de lançamentos de**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-122">In the **Use posting profile from** field, select an option.</span></span> <span data-ttu-id="e6ce5-123">Há três opções de perfil de lançamento:</span><span class="sxs-lookup"><span data-stu-id="e6ce5-123">There are three posting profile options:</span></span>
    - <span data-ttu-id="e6ce5-124">Conta – use o perfil de lançamentos atribuído à conta de cliente para cada nota de juros.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-124">Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span> 
    - <span data-ttu-id="e6ce5-125">Seleção - use o perfil de lançamento selecionado no campo Perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-125">Select – Use the posting profile that you select in the Posting profile field.</span></span>
    - <span data-ttu-id="e6ce5-126">Transação - use o perfil de lançamento individual de transações em que os juros são calculados para cada nota de juros.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-126">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="e6ce5-127">As transações que não têm um perfil de lançamento atribuído usarão o perfil de lançamento especificado na área Razão e imposto do formulário Parâmetros de conta recebida.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-127">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
7. <span data-ttu-id="e6ce5-128">Expanda a Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-128">Expand the **Records to include** fastTab.</span></span>
8. <span data-ttu-id="e6ce5-129">Clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-129">Click **Filter**.</span></span>
9. <span data-ttu-id="e6ce5-130">No campo **Critérios**, insira uma ID do Cliente.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-130">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="e6ce5-131">Por exemplo, insira 'US-001'.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-131">For example, enter 'US-001'.</span></span>
6. <span data-ttu-id="e6ce5-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-132">Click **OK**.</span></span>
7. <span data-ttu-id="e6ce5-133">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-133">Click **OK**.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="e6ce5-134">Imprimir notas de juros</span><span class="sxs-lookup"><span data-stu-id="e6ce5-134">Print interest notes</span></span>
1. <span data-ttu-id="e6ce5-135">No **Painel de navegação**, vá para **Módulos > Crédito e coleções > Juros > Revisar e processar notas de juros**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-135">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Review and process interest notes**.</span></span>
2. <span data-ttu-id="e6ce5-136">No campo **Status**, selecione "Criado".</span><span class="sxs-lookup"><span data-stu-id="e6ce5-136">In the **Status** field, select 'Created'.</span></span>
3. <span data-ttu-id="e6ce5-137">No campo **Impresso**, selecione "Não impresso".</span><span class="sxs-lookup"><span data-stu-id="e6ce5-137">In the **Printed** field, select 'Not printed'.</span></span>
4. <span data-ttu-id="e6ce5-138">Clique em **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-138">Click **Print**.</span></span>
5. <span data-ttu-id="e6ce5-139">Expanda a Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-139">Expand the **Records to include** fastTab.</span></span>
6. <span data-ttu-id="e6ce5-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-140">Click **OK**.</span></span>
7. <span data-ttu-id="e6ce5-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-141">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="e6ce5-142">Lançar a nota de juros</span><span class="sxs-lookup"><span data-stu-id="e6ce5-142">Post the interest note</span></span>
1. <span data-ttu-id="e6ce5-143">Selecione uma nota de juros que está pronta para ser lançada (o status é criado).</span><span class="sxs-lookup"><span data-stu-id="e6ce5-143">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="e6ce5-144">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-144">Click **Post**.</span></span>
3. <span data-ttu-id="e6ce5-145">Digite a data de lançamento para as notas de juros.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-145">Enter the posting date for the interest note.</span></span> <span data-ttu-id="e6ce5-146">Marque Sim para criar uma transação de contabilidade para cada nota de juros.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-146">Select Yes to create a general ledger transaction for each interest note.</span></span> <span data-ttu-id="e6ce5-147">Se não marcar Sim, os juros em todas as notas de juros ao cliente serão acumulados e lançados na contabilidade em uma transação.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-147">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="e6ce5-148">Expanda a Guia Rápida **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-148">Expand the **Records to include** fastTab.</span></span>
5. <span data-ttu-id="e6ce5-149">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ce5-149">Click **OK**.</span></span>
6. <span data-ttu-id="e6ce5-150">No campo **Status**, selecione "Lançado".</span><span class="sxs-lookup"><span data-stu-id="e6ce5-150">In the **Status** field, select 'Posted'.</span></span>

