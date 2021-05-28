---
title: Processar exemplo de cartas de cobrança
description: Este tópico percorre um exemplo que mostra o processo de criação, impressão e lançamento de cartas de cobrança.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fb2651644efd2cadfccb91e48c34dfddc8383e1f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021407"
---
# <a name="process-collection-letters-example"></a><span data-ttu-id="2081e-103">Processar exemplo de cartas de cobrança</span><span class="sxs-lookup"><span data-stu-id="2081e-103">Process collection letters example</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2081e-104">Este tópico percorre um exemplo que mostra o processo de criação, impressão e lançamento de cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="2081e-104">This topic goes through an example that shows the process of creating, printing, and posting collection letters.</span></span> <span data-ttu-id="2081e-105">O exemplo se baseia na opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** em Crédito e cobranças.</span><span class="sxs-lookup"><span data-stu-id="2081e-105">The example is based on the **Ignore payments and credit memos when calculating collection letter code** option in Credit and collections.</span></span> <span data-ttu-id="2081e-106">Ele usa os dados da empresa de demonstração de USMF e um novo cliente, EUA-045.</span><span class="sxs-lookup"><span data-stu-id="2081e-106">It uses data in the USMF demo company and a new customer, US-045.</span></span>

<span data-ttu-id="2081e-107">Para começar, vá para **Clientes de contas \> a receber \> Todos os clientes**, selecione **Novo** e insira as informações necessárias para criar um cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="2081e-107">To begin, go to **Accounts receivable \> Customers \> All customers**, select **New**, and then enter the required information to create customer US-045.</span></span>

<span data-ttu-id="2081e-108">Quando terminar, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2081e-108">When you've finished, follow these steps.</span></span>

1. <span data-ttu-id="2081e-109">Vá para **Crédito e cobranças \> Carta de cobrança \> Configurar sequência de cartas de cobrança** e configure a sequência de carta de cobrança, conforme mostrado na tabela a seguir que é atribuída ao perfil de lançamentos do cliente.</span><span class="sxs-lookup"><span data-stu-id="2081e-109">Go to **Credit and collections \> Collection letter \> Setup collection letter sequence**, and set up the collection letter sequence as shown in the following table that is assigned to the customer posting profile.</span></span>

|     <span data-ttu-id="2081e-110">Código de carta de cobrança</span><span class="sxs-lookup"><span data-stu-id="2081e-110">Collection   letter code</span></span>      |     <span data-ttu-id="2081e-111">descrição</span><span class="sxs-lookup"><span data-stu-id="2081e-111">Description</span></span>                           |     <span data-ttu-id="2081e-112">Moeda</span><span class="sxs-lookup"><span data-stu-id="2081e-112">Currency</span></span>      |     <span data-ttu-id="2081e-113">Conta principal</span><span class="sxs-lookup"><span data-stu-id="2081e-113">Main   account</span></span>        |     <span data-ttu-id="2081e-114">Taxa em moeda</span><span class="sxs-lookup"><span data-stu-id="2081e-114">Fee   in currency</span></span>     |     <span data-ttu-id="2081e-115">Mínimo sobre</span><span class="sxs-lookup"><span data-stu-id="2081e-115">Minimum   over</span></span>        |     <span data-ttu-id="2081e-116">Bloco de Dias</span><span class="sxs-lookup"><span data-stu-id="2081e-116">Days   Block</span></span>      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     <span data-ttu-id="2081e-117">Carta de cobrança 1</span><span class="sxs-lookup"><span data-stu-id="2081e-117">Collection   letter 1</span></span>         |     <span data-ttu-id="2081e-118">Segunda notificação com taxa</span><span class="sxs-lookup"><span data-stu-id="2081e-118">Second   notification with fee</span></span>        |     <span data-ttu-id="2081e-119">USD</span><span class="sxs-lookup"><span data-stu-id="2081e-119">USD</span></span>           |                           |     <span data-ttu-id="2081e-120">0,00</span><span class="sxs-lookup"><span data-stu-id="2081e-120">0.00</span></span>                  |     <span data-ttu-id="2081e-121">0,00</span><span class="sxs-lookup"><span data-stu-id="2081e-121">0.00</span></span>                  |     <span data-ttu-id="2081e-122">2</span><span class="sxs-lookup"><span data-stu-id="2081e-122">2</span></span>                 |
|     <span data-ttu-id="2081e-123">Carta de cobrança 2</span><span class="sxs-lookup"><span data-stu-id="2081e-123">Collection   letter 2</span></span>         |     <span data-ttu-id="2081e-124">Segunda notificação com taxa</span><span class="sxs-lookup"><span data-stu-id="2081e-124">Second   notification with fee</span></span>        |     <span data-ttu-id="2081e-125">USC</span><span class="sxs-lookup"><span data-stu-id="2081e-125">USC</span></span>           |     <span data-ttu-id="2081e-126">403150</span><span class="sxs-lookup"><span data-stu-id="2081e-126">403150</span></span>                |     <span data-ttu-id="2081e-127">20.00</span><span class="sxs-lookup"><span data-stu-id="2081e-127">20.00</span></span>                 |     <span data-ttu-id="2081e-128">10,00</span><span class="sxs-lookup"><span data-stu-id="2081e-128">10.00</span></span>                 |     <span data-ttu-id="2081e-129">3</span><span class="sxs-lookup"><span data-stu-id="2081e-129">3</span></span>                 |
|     <span data-ttu-id="2081e-130">Cobrança</span><span class="sxs-lookup"><span data-stu-id="2081e-130">Collection</span></span>                    |     <span data-ttu-id="2081e-131">Notificação final com taxa</span><span class="sxs-lookup"><span data-stu-id="2081e-131">Final   notification with fee</span></span>         |     <span data-ttu-id="2081e-132">USD</span><span class="sxs-lookup"><span data-stu-id="2081e-132">USD</span></span>           |     <span data-ttu-id="2081e-133">403150</span><span class="sxs-lookup"><span data-stu-id="2081e-133">403150</span></span>                |     <span data-ttu-id="2081e-134">50.00</span><span class="sxs-lookup"><span data-stu-id="2081e-134">50.00</span></span>                 |     <span data-ttu-id="2081e-135">100.00</span><span class="sxs-lookup"><span data-stu-id="2081e-135">100.00</span></span>                |     <span data-ttu-id="2081e-136">15</span><span class="sxs-lookup"><span data-stu-id="2081e-136">15</span></span>                |

<span data-ttu-id="2081e-137">A ilustração a seguir mostra as informações que estão na tabela como apareceriam na página **Cartas de cobrança**.</span><span class="sxs-lookup"><span data-stu-id="2081e-137">The following illustration shows the information that's in the table as it would appear on the **Collection letters** page.</span></span> 

<span data-ttu-id="2081e-138">[![Configurando uma sequência de cartas de cobrança](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span><span class="sxs-lookup"><span data-stu-id="2081e-138">[![Setting up a collection letter sequence](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span></span>

 <span data-ttu-id="2081e-139">Agora você deve definir os dois parâmetros necessários para este exemplo.</span><span class="sxs-lookup"><span data-stu-id="2081e-139">You must now set the two parameters that are required for this example.</span></span>

2. <span data-ttu-id="2081e-140">Vá para **Crédito e cobranças \> Configuração \> Parâmetros de contas a receber** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2081e-140">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and follow these steps:</span></span>

    1. <span data-ttu-id="2081e-141">Na guia **Cobranças**, defina a opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2081e-141">On the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **Yes**.</span></span>
    2. <span data-ttu-id="2081e-142">Verifique se o campo **Criar carta de cobrança por** foi definido como **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="2081e-142">Make sure that the **Create collection letter per** field is set to **Customer**.</span></span>

    <span data-ttu-id="2081e-143">[![Configurando parâmetros de contas a receber para Crédito e cobranças](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span><span class="sxs-lookup"><span data-stu-id="2081e-143">[![Setting Accounts receivable parameters for Credit collections](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span></span>

3. <span data-ttu-id="2081e-144">Vá para **Contas a receber \> Faturas \> Todas as faturas de texto livre**, selecione **Novo** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2081e-144">Go to **Accounts receivable \> Invoices \> All free text invoices**, select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="2081e-145">No campo **Conta do cliente**, selecione **US-045**.</span><span class="sxs-lookup"><span data-stu-id="2081e-145">In the **Customer account** field select **US-045**.</span></span>
    2. <span data-ttu-id="2081e-146">No campo **Data da fatura**, digite **15/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="2081e-146">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="2081e-147">No campo **Data de conclusão**, digite **16/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="2081e-147">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="2081e-148">Na guia rápida **Linhas da fatura** no campo **Conta principal**, digite **401100**.</span><span class="sxs-lookup"><span data-stu-id="2081e-148">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="2081e-149">No campo **Preço unitário**, insira **500.00**.</span><span class="sxs-lookup"><span data-stu-id="2081e-149">In the **Unit price** field, enter **500.00**.</span></span>
    6. <span data-ttu-id="2081e-150">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="2081e-150">Select **Post**.</span></span>

    <span data-ttu-id="2081e-151">Agora, você deve inserir duas notas de crédito para o cliente.</span><span class="sxs-lookup"><span data-stu-id="2081e-151">You must now enter two credit notes for the customer.</span></span>

4. <span data-ttu-id="2081e-152">Selecione **Novo** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2081e-152">Select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="2081e-153">No campo **Conta do cliente**, selecione **US-045**.</span><span class="sxs-lookup"><span data-stu-id="2081e-153">In the **Customer account** field, select **US-045**.</span></span>
    2. <span data-ttu-id="2081e-154">No campo **Data da fatura**, digite **15/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="2081e-154">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="2081e-155">No campo **Data de conclusão**, digite **16/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="2081e-155">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="2081e-156">Na guia rápida **Linhas da fatura** no campo **Conta principal**, digite **401100**.</span><span class="sxs-lookup"><span data-stu-id="2081e-156">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="2081e-157">No campo **Preço unitário**, digite **-100.00**.</span><span class="sxs-lookup"><span data-stu-id="2081e-157">In the **Unit price** field, enter **-100.00**.</span></span>
    6. <span data-ttu-id="2081e-158">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="2081e-158">Select **Post**.</span></span>

5. <span data-ttu-id="2081e-159">Repita a etapa 4, mas insira **-200,00** no campo **Preço unitário**.</span><span class="sxs-lookup"><span data-stu-id="2081e-159">Repeat step 4, but enter **-200.00** in the **Unit price** field.</span></span>
6. <span data-ttu-id="2081e-160">Vá para **Contas a receber \> Clientes \> Todos os clientes** e selecione cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="2081e-160">Go to **Accounts receivable \> Customers \> All customers**, and select customer **US-045**.</span></span> <span data-ttu-id="2081e-161">Em seguida, no painel de ação, selecione **Transações \> Transações** para revisar as transações de cliente lançadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2081e-161">Then, on the Action Pane, select **Transactions \> Transactions** to review the customer transactions that you posted earlier.</span></span>

    <span data-ttu-id="2081e-162">[![Analisando as transações do cliente lançadas](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span><span class="sxs-lookup"><span data-stu-id="2081e-162">[![Reviewing the posted customer transactions](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span></span>

    <span data-ttu-id="2081e-163">Agora você precisa criar cartas de cobrança para um cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="2081e-163">You must now create collection letters for customer US-045.</span></span>

7. <span data-ttu-id="2081e-164">Vá para **Crédito e cobranças \> Carta de cobrança \> Criar cartas de cobrança** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2081e-164">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="2081e-165">Defina as **Fatura** e **Nota de crédito** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2081e-165">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="2081e-166">Por padrão, o campo **Carta de cobrança** deve ser definido como **Coleção por cliente**.</span><span class="sxs-lookup"><span data-stu-id="2081e-166">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="2081e-167">No campo **Data da carta de cobrança**, digite **19/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="2081e-167">In the **Collection letter date** field, enter **1/19/2021**.</span></span>
    3. <span data-ttu-id="2081e-168">Na guia rápida **Registros a serem incluídos**, selecione **Filtrar** e, em seguida, no campo **Conta de cliente**, adicione o cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="2081e-168">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="2081e-169">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2081e-169">Select **OK**.</span></span>
    5. <span data-ttu-id="2081e-170">Selecione **OK** para criar cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="2081e-170">Select **OK** to create collection letters.</span></span>

8. <span data-ttu-id="2081e-171">Vá para **Crédito e cobranças \> Carta de cobrança \> Revisar e processar cartas de cobrança** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2081e-171">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="2081e-172">Observe que o código da carta de cobrança no cabeçalho e nas linhas de transação é **Carta de cobrança 1**, pois essa carta de cobrança é a primeira carta de cobrança na sequência.</span><span class="sxs-lookup"><span data-stu-id="2081e-172">Notice that the collection letter code on both the header and the transaction lines is **Collection letter 1**, because this collection letter is the first collection letter in the sequence.</span></span> <span data-ttu-id="2081e-173">(Para exibir as linhas de transação, talvez seja necessário selecionar a guia rápida **Transações**.)</span><span class="sxs-lookup"><span data-stu-id="2081e-173">(To view the transaction lines, you might have to select the **Transactions** FastTab.)</span></span>

   <span data-ttu-id="2081e-174">[![Verificando se o mesmo código de carta de cobrança aparece no cabeçalho e nas linhas](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span><span class="sxs-lookup"><span data-stu-id="2081e-174">[![Verifying that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span></span>

    2. <span data-ttu-id="2081e-175">No Painel de Ação, selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="2081e-175">On the Action Pane, select **Post**.</span></span>
    3. <span data-ttu-id="2081e-176">No campo **Data do lançamento**, digite **19/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="2081e-176">In the **Posting date** field, enter **1/19/2021**.</span></span>

    <span data-ttu-id="2081e-177">Agora você precisa criar cartas de cobrança novamente para um cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="2081e-177">You must now create collection letters again for customer US-045.</span></span>

9. <span data-ttu-id="2081e-178">Vá para **Crédito e cobranças \> Carta de cobrança \> Criar cartas de cobrança** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2081e-178">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="2081e-179">Defina as **Fatura** e **Nota de crédito** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2081e-179">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="2081e-180">Por padrão, o campo **Carta de cobrança** deve ser definido como **Coleção por cliente**.</span><span class="sxs-lookup"><span data-stu-id="2081e-180">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="2081e-181">No campo **Data da carta de cobrança**, digite **23/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="2081e-181">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="2081e-182">Na guia rápida **Registros a serem incluídos**, selecione **Filtrar** e, em seguida, no campo **Conta de cliente**, adicione o cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="2081e-182">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="2081e-183">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2081e-183">Select **OK**.</span></span>
    5. <span data-ttu-id="2081e-184">Selecione **OK** para criar cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="2081e-184">Select **OK** to create collection letters.</span></span>

10. <span data-ttu-id="2081e-185">Vá para **Crédito e cobranças \> Carta de cobrança \> Revisar e processar cartas de cobrança** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2081e-185">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="2081e-186">Observe que o código da carta de cobrança no cabeçalho é **Carta de cobrança 1**.</span><span class="sxs-lookup"><span data-stu-id="2081e-186">Notice that the collection letter code on the header is **Collection letter 1**.</span></span> <span data-ttu-id="2081e-187">No entanto, o código nas linhas de transação é **Carta de cobrança 2**.</span><span class="sxs-lookup"><span data-stu-id="2081e-187">However, the code on the transaction lines is **Collection letter 2**.</span></span>

   <span data-ttu-id="2081e-188">[![Verifica se os diferentes códigos de carta de cobrança aparece no cabeçalho e nas linhas](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span><span class="sxs-lookup"><span data-stu-id="2081e-188">[![Verifies that different collection letter codes appear on the header and the lines](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span></span>

  <span data-ttu-id="2081e-189">Os códigos diferem porque a opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** é definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2081e-189">The codes differ because the **Ignore payments and credit memos when calculating collection letter code** option is to **Yes**.</span></span>

  2. <span data-ttu-id="2081e-190">Não lançar a carta de cobrança.</span><span class="sxs-lookup"><span data-stu-id="2081e-190">Don't post this collection letter.</span></span>

11. <span data-ttu-id="2081e-191">Vá para **Crédito e cobranças \> Configuração \> Parâmetros de contas a receber** e na guia **Cobranças**, defina a opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="2081e-191">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and then, on the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **No**.</span></span>

    <span data-ttu-id="2081e-192">[![Defina a opção Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança como Não](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span><span class="sxs-lookup"><span data-stu-id="2081e-192">[![Setting the Ignore payments and credit memos when calculating collection letter code option to No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span></span>

    <span data-ttu-id="2081e-193">Agora você precisa criar cartas de cobrança novamente para um cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="2081e-193">You must now create collection letters again for customer US-045.</span></span>

12. <span data-ttu-id="2081e-194">Vá para **Crédito e cobranças \> Carta de cobrança \> Criar cartas de cobrança** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2081e-194">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="2081e-195">Defina as **Fatura** e **Nota de crédito** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2081e-195">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="2081e-196">Por padrão, o campo **Carta de cobrança** deve ser definido como **Coleção por cliente**.</span><span class="sxs-lookup"><span data-stu-id="2081e-196">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="2081e-197">No campo **Data da carta de cobrança**, digite **23/01/2021**.</span><span class="sxs-lookup"><span data-stu-id="2081e-197">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="2081e-198">Na guia rápida **Registros a serem incluídos**, selecione **Filtrar** e, em seguida, no campo **Conta de cliente**, adicione o cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="2081e-198">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="2081e-199">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2081e-199">Select **OK**.</span></span>
    5. <span data-ttu-id="2081e-200">Selecione **OK** para criar cartas de cobrança.</span><span class="sxs-lookup"><span data-stu-id="2081e-200">Select **OK** to create collection letters.</span></span>

13. <span data-ttu-id="2081e-201">Vá para **Crédito e cobranças \> Carta de cobrança \> Revisar e processar cartas de cobrança** e observe que o código da carta de cobrança no cabeçalho e nas linhas de transação é **Carta de cobrança 2**.</span><span class="sxs-lookup"><span data-stu-id="2081e-201">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and notice that the collection letter code on both the header and the transaction lines is **Collection letter 2**.</span></span>

    <span data-ttu-id="2081e-202">[![Mostrando novamente que o mesmo código de carta de cobrança aparece no cabeçalho e nas linhas](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span><span class="sxs-lookup"><span data-stu-id="2081e-202">[![Showing again that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span></span>

    <span data-ttu-id="2081e-203">O mesmo código aparece nos dois locais porque a opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** agora foi definida como **Não**.</span><span class="sxs-lookup"><span data-stu-id="2081e-203">The same code appears in both places because the **Ignore payments and credit memos when calculating collection letter code** option is now set to **No**.</span></span>
