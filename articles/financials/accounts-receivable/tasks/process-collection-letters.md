---
title: Processar cartas de cobrança
description: Este procedimento mostra como criar, imprimir e lançar cartas de cobrança.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/04/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 8a3f74d2891c050294e089eae14ba2386449d7c9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "358844"
---
# <a name="process-collection-letters"></a><span data-ttu-id="dcce0-103">Processar cartas de cobrança</span><span class="sxs-lookup"><span data-stu-id="dcce0-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dcce0-104">Este procedimento mostra como criar, imprimir e lançar cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="dcce0-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="dcce0-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="dcce0-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="dcce0-106">Configurar uma sequência de carta de cobrança no perfil de lançamento</span><span class="sxs-lookup"><span data-stu-id="dcce0-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="dcce0-107">Vá para **Crédito e cobranças > Configuração > Perfis de lançamentos de cliente**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-107">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="dcce0-108">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-108">Click **Edit**.</span></span>
3. <span data-ttu-id="dcce0-109">Selecione uma sequência de carta de cobrança na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="dcce0-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="dcce0-110">Se você não quiser gerar cartas de cobrança para transações usando este perfil de lançamento, deixe o campo em branco.</span><span class="sxs-lookup"><span data-stu-id="dcce0-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="dcce0-111">Expanda a guia de restrição de tabela para alterar a forma como as cartas de cobrança são processadas.</span><span class="sxs-lookup"><span data-stu-id="dcce0-111">Expand the table restriction tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="dcce0-112">Se este campo estiver definido como **Sim**, as cartas de cobrança serão criadas para este perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="dcce0-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="dcce0-113">Criar cartas de cobrança</span><span class="sxs-lookup"><span data-stu-id="dcce0-113">Create collection letters</span></span>
1. <span data-ttu-id="dcce0-114">Vá para **Crédito e cobranças > Carta de cobrança > Criar cartas de cobrança**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-114">Go to **Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="dcce0-115">Selecione os tipos de transação para os quais você usará cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="dcce0-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="dcce0-116">Todas as transações abertas para esses tipos serão incluídas no cálculo.</span><span class="sxs-lookup"><span data-stu-id="dcce0-116">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="dcce0-117">No campo **Carta de cobrança**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="dcce0-117">In the **Collection letter** field, select an option.</span></span>
3. <span data-ttu-id="dcce0-118">Insira a data da carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="dcce0-118">Enter the date of the collection letter.</span></span>
4. <span data-ttu-id="dcce0-119">Selecione um perfil de lançamentos se você tiver alterado **Usar perfil de lançamento de** para **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="dcce0-120">Há duas opções de perfil de lançamento:</span><span class="sxs-lookup"><span data-stu-id="dcce0-120">There are two posting profile options:</span></span>   
   - <span data-ttu-id="dcce0-121">**Conta** – use o perfil de lançamentos atribuído à conta de cliente para cada nota de juros.</span><span class="sxs-lookup"><span data-stu-id="dcce0-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="dcce0-122">**Selecionar** - use o perfil de lançamentos selecionado no campo **Perfil de lançamentos**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  
5. <span data-ttu-id="dcce0-123">Expanda a seção **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-123">Expand the **Records to include** section.</span></span>
6. <span data-ttu-id="dcce0-124">Clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-124">Click **Filter**.</span></span>
7. <span data-ttu-id="dcce0-125">No campo **Critérios**, insira uma ID do Cliente.</span><span class="sxs-lookup"><span data-stu-id="dcce0-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="dcce0-126">Por exemplo, insira 'US-001'.</span><span class="sxs-lookup"><span data-stu-id="dcce0-126">For example, enter 'US-001'.</span></span>
8. <span data-ttu-id="dcce0-127">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-127">Click **OK**.</span></span>
9. <span data-ttu-id="dcce0-128">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-128">Click **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="dcce0-129">Imprimir cartas de cobrança</span><span class="sxs-lookup"><span data-stu-id="dcce0-129">Print collection letters</span></span>
1. <span data-ttu-id="dcce0-130">Vá para **Crédito e cobranças > Carta de cobrança > Revisar e processar cartas de cobrança**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-130">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="dcce0-131">No campo **Status**, selecione **Criado'**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="dcce0-132">No campo **Impresso**, selecione **Não impresso'**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="dcce0-133">Clique em **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-133">Click **Print**.</span></span>
5. <span data-ttu-id="dcce0-134">Clique em **Nota de carta de cobrança**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-134">Click **Collection letter note**.</span></span>
6. <span data-ttu-id="dcce0-135">Expanda a seção **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-135">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="dcce0-136">Insira a data de fechamento para lançamentos.</span><span class="sxs-lookup"><span data-stu-id="dcce0-136">Enter the cutoff date for postings.</span></span>
8. <span data-ttu-id="dcce0-137">Clique em **OK** para imprimir a carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="dcce0-137">Click **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="dcce0-138">Lance a carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="dcce0-138">Post the collection letter.</span></span>
   1. <span data-ttu-id="dcce0-139">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-139">Click **Post**.</span></span>
   2. <span data-ttu-id="dcce0-140">Inserir a nova data de lançamento para a carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="dcce0-140">Enter the posting date for the collection letter.</span></span>
   3. <span data-ttu-id="dcce0-141">Expanda a seção **Registros a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-141">Expand the **Records to include** section.</span></span>
   4. <span data-ttu-id="dcce0-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-142">Click **OK**.</span></span>
   5. <span data-ttu-id="dcce0-143">No campo **Status**, selecione **Lançado'**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-143">In the **Status** field, select **Posted**.</span></span>
   6. <span data-ttu-id="dcce0-144">No campo **Impresso**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="dcce0-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="dcce0-145">Controle cartas de cobrança em nível de cliente</span><span class="sxs-lookup"><span data-stu-id="dcce0-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="dcce0-146">Você também pode configurar cartas de cobrança em nível de cliente para que o código da carta de cobrança para cada transação seja rastreado, mas o processamento da carta de cobrança será baseado em um único nível de carta de cobrança que é armazenado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="dcce0-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="dcce0-147">A única carta de cobrança conterá todas as transações que estão vencidas para o cliente.</span><span class="sxs-lookup"><span data-stu-id="dcce0-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="dcce0-148">Como os dias de carência agora são rastreados em nível de cliente, a próxima carta de cobrança não será enviada até que o número de dias de carência passe para a próxima carta de cobrança na sequência, mesmo que as transações expirem após o envio da última carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="dcce0-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="dcce0-149">Esta opção reduz o número de cartas de cobrança enviadas por cliente.</span><span class="sxs-lookup"><span data-stu-id="dcce0-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="dcce0-150">Configure o cliente para controlar as cartas de cobrança em nível de cliente</span><span class="sxs-lookup"><span data-stu-id="dcce0-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="dcce0-151">Vá para **Crédito e cobranças > Configuração > Parâmetros de contas a receber** e clique na guia **Cobranças**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-151">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2.  <span data-ttu-id="dcce0-152">Altere o valor de **Criar carta de cobrança por** para **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="dcce0-153">Vá para **Crédito e cobranças > Carta de cobrança > Revisar e processar cartas de cobrança**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-153">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="dcce0-154">Apenas uma carta de cobrança será gerada para um cliente com todas as transações vencidas.</span><span class="sxs-lookup"><span data-stu-id="dcce0-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="dcce0-155">Ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança</span><span class="sxs-lookup"><span data-stu-id="dcce0-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="dcce0-156">Se você incluir pagamentos e memorandos de crédito nas transações que serão incluídas nas cartas de cobrança, talvez alguns pagamentos ou memorando de crédito disparem uma carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="dcce0-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="dcce0-157">Você pode controlar como os pagamentos e os memorandos de crédito controlam o código de carta de cobrança alterando o valor do parâmetro **Ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="dcce0-158">Para ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dcce0-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>
1. <span data-ttu-id="dcce0-159">Vá para **Crédito e cobranças > Configuração > Parâmetros de contas a receber** e clique na guia **Cobranças**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-159">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="dcce0-160">Altere o valor de **Ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="dcce0-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>
