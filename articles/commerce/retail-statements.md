---
title: Demonstrativos de varejo
description: Este tópico descreve como os demonstrativos são criados e lançados.
author: ashishmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 4409811d2ef60174a316db10307dc7af4697398c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021638"
---
# <a name="retail-statements"></a><span data-ttu-id="f0072-103">Demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="f0072-103">Retail statements</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f0072-104">No Dynamics 365 Commerce, o processo de lançamento de demonstrativo é usado para registrar contabilmente as transações que ocorrem no ponto de venda (PDV) da nuvem ou Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="f0072-104">In Dynamics 365 Commerce, the statement posting process is used to account for the transactions that occur in Cloud point of sale (POS) or Modern POS (MPOS).</span></span> <span data-ttu-id="f0072-105">O processos de lançamentos de demonstrativos usa a agenda de distribuição para receber um conjunto de transações PDV no cliente das sedes (HQ).</span><span class="sxs-lookup"><span data-stu-id="f0072-105">The statement posting process uses the distribution schedule to pull a set of POS transactions into the headquarters (HQ) client.</span></span> <span data-ttu-id="f0072-106">Os parâmetros definidos nas páginas **Parâmetros do Commerce** e **Lojas** são usados para selecionar as transações que são recebidas em demonstrativos individuais.</span><span class="sxs-lookup"><span data-stu-id="f0072-106">The parameters that are defined on the **Commerce parameters** and **Stores** pages are used to select the transactions that are pulled into individual statements.</span></span>

<span data-ttu-id="f0072-107">A ilustração a seguir mostra o processo de lançamento do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="f0072-107">The following illustration shows the statement posting process.</span></span> <span data-ttu-id="f0072-108">Nesse processo, as transações que são registradas no PDV são transmitidas para o cliente usando o agendador do Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0072-108">In this process, transactions that are recorded in the POS are transmitted to the client by using the Commerce scheduler.</span></span> <span data-ttu-id="f0072-109">Depois que o cliente receber as transações, você poderá criar, calcular e lançar o demonstrativo de transação para a loja.</span><span class="sxs-lookup"><span data-stu-id="f0072-109">After the client receives the transactions, you can create, calculate, and post the transaction statement for the store.</span></span>

<span data-ttu-id="f0072-110">[![Processo de lançamento de demonstrativo](./media/retail-statements.png)](./media/retail-statements.png)</span><span class="sxs-lookup"><span data-stu-id="f0072-110">[![Statement posting process](./media/retail-statements.png)](./media/retail-statements.png)</span></span>

## <a name="creating-and-posting-statements"></a><span data-ttu-id="f0072-111">Criação e lançamento de demonstrativos</span><span class="sxs-lookup"><span data-stu-id="f0072-111">Creating and posting statements</span></span>

<span data-ttu-id="f0072-112">Você pode criar um demonstrativo manualmente ou usar os processos em lote que você configurou para serem executados periodicamente ao longo do dia.</span><span class="sxs-lookup"><span data-stu-id="f0072-112">You can create a statement manually or by using batch processes that you set up to run periodically throughout the day.</span></span> <span data-ttu-id="f0072-113">Nos dois casos, as etapas a seguir são usadas para criar e lançar demonstrativos.</span><span class="sxs-lookup"><span data-stu-id="f0072-113">In both cases, the following steps are used to create and post statements.</span></span>

### <a name="create-the-statement"></a><span data-ttu-id="f0072-114">Criar o demonstrativo</span><span class="sxs-lookup"><span data-stu-id="f0072-114">Create the statement</span></span>

<span data-ttu-id="f0072-115">Esta etapa identifica a loja onde o demonstrativo foi criado manualmente.</span><span class="sxs-lookup"><span data-stu-id="f0072-115">This step identifies the store that the statement is manually created for.</span></span> <span data-ttu-id="f0072-116">Se você configurar um processo em lote, poderá criar automaticamente demonstrativos para todas as lojas com base em uma agenda definida.</span><span class="sxs-lookup"><span data-stu-id="f0072-116">If you configure a batch process, you can automatically create statements for all stores, based on a schedule that you define.</span></span>

### <a name="calculate-the-statement"></a><span data-ttu-id="f0072-117">Calcular o demonstrativo</span><span class="sxs-lookup"><span data-stu-id="f0072-117">Calculate the statement</span></span>

<span data-ttu-id="f0072-118">Nesta etapa, as linhas de transação são selecionadas com base nos critérios definidos para cada loja nas páginas **Parâmetros do Commerce** e **Lojas**.</span><span class="sxs-lookup"><span data-stu-id="f0072-118">In this step, the transaction lines are selected based on criteria that are defined for each store on the **Commerce parameters** and **Stores** pages.</span></span> <span data-ttu-id="f0072-119">Nestas páginas, você define os critérios e especifica como as transações são calculadas.</span><span class="sxs-lookup"><span data-stu-id="f0072-119">On these pages, you define the criteria and specify how the transactions are calculated.</span></span> <span data-ttu-id="f0072-120">Para exibir uma lista de transações que são incluídas no demonstrativo antes de calculá-lo, use a página **Transações**.</span><span class="sxs-lookup"><span data-stu-id="f0072-120">To view a list of the transactions that are included in the statement before you calculate the statement, use the **Transactions** page.</span></span>

<span data-ttu-id="f0072-121">O cálculo do demonstrativo usa declarações da proposta dos terminais de acordo com o valor contado.</span><span class="sxs-lookup"><span data-stu-id="f0072-121">Statement calculation uses tender declarations from the registers as the counted amount.</span></span> <span data-ttu-id="f0072-122">Como alternativa, você poderá inserir manualmente o valor contato.</span><span class="sxs-lookup"><span data-stu-id="f0072-122">Alternatively, you can enter the counted amount manually.</span></span> <span data-ttu-id="f0072-123">O demonstrativo mostra a diferença entre o valor de venda das transações e o valor real contado em todos os métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f0072-123">The statement shows the difference between the sales amount for the transactions and the actual counted amount in all payment methods.</span></span> <span data-ttu-id="f0072-124">O demonstrativo será lançado apenas se a diferença for menor do que a diferença máxima de lançamento definida para a loja.</span><span class="sxs-lookup"><span data-stu-id="f0072-124">The statement is posted only if this difference is less than the maximum posting difference that is defined for the store.</span></span>

> [!NOTE]
> <span data-ttu-id="f0072-125">O processo de cálculo do demonstrativo usa a sequência numérica global.</span><span class="sxs-lookup"><span data-stu-id="f0072-125">The statement calculation process uses the global number sequence.</span></span>

<span data-ttu-id="f0072-126">Quando você calcula um demonstrativo, o cálculo inclui as tarefas a seguir:</span><span class="sxs-lookup"><span data-stu-id="f0072-126">When you calculate a statement, the calculation includes the following tasks:</span></span>

- <span data-ttu-id="f0072-127">Para o intervalo de datas selecionado, marque as transações que não foram incluídas em um cálculo de demonstrativo anterior.</span><span class="sxs-lookup"><span data-stu-id="f0072-127">For the selected date range, mark transactions that weren't included in a previous statement calculation.</span></span>
- <span data-ttu-id="f0072-128">Calcule os valores totais que foram propostos nas transações selecionadas.</span><span class="sxs-lookup"><span data-stu-id="f0072-128">Calculate the total amounts that were tendered in the selected transactions.</span></span> <span data-ttu-id="f0072-129">Os resultados são exibidos nas linhas do demonstrativo, dependendo do método do demonstrativo:</span><span class="sxs-lookup"><span data-stu-id="f0072-129">The results are shown on the statement lines, depending on the statement method:</span></span>

    - <span data-ttu-id="f0072-130">Se o método do demonstrativo for **Total**, será criada uma linha para cada método de pagamento nas transações selecionadas.</span><span class="sxs-lookup"><span data-stu-id="f0072-130">If the statement method is **Total**, a line is created for each payment method in the selected transactions.</span></span>
    - <span data-ttu-id="f0072-131">Se o método do demonstrativo for **Equipe**, será criada uma linha para cada método de pagamento nas transações realizadas pelo membro da equipe selecionado.</span><span class="sxs-lookup"><span data-stu-id="f0072-131">If the statement method is **Staff**, a line is created for each payment method in transactions that were performed by the selected staff member.</span></span>
    - <span data-ttu-id="f0072-132">Se o método de demonstrativo for **Terminal de PDV**, será criada uma linha para método de pagamento nas transações realizadas no terminal selecionado.</span><span class="sxs-lookup"><span data-stu-id="f0072-132">If the statement method is **POS terminal**, a line is created for each payment method in transactions that were performed on the selected register.</span></span>
    - <span data-ttu-id="f0072-133">Se o método de demonstrativo for **Turno**, será criada uma linha para método de pagamento nas transações realizadas durante um turno.</span><span class="sxs-lookup"><span data-stu-id="f0072-133">If the statement method is **Shift**, a line is created for each payment method in transactions that were performed during a shift.</span></span>

<span data-ttu-id="f0072-134">Se a caixa de seleção **Método Dividir por Demonstrativo** estiver marcada na página **Lojas**, uma instrução separada é criada com base no valor selecionado no campo **Método de demonstrativo**.</span><span class="sxs-lookup"><span data-stu-id="f0072-134">If the **Split by Statement method** check box is selected on the **Stores** page, a separate statement is created based on the value that is selected in the **Statement method** field.</span></span>

<span data-ttu-id="f0072-135">Se as horas de operação da loja se estenderam após a meia-noite, você pode configurar lançamento de demonstrativos com base no final do dia útil, em vez de no final do dia do calendário.</span><span class="sxs-lookup"><span data-stu-id="f0072-135">If your store's operating hours extend past midnight, you can configure statement posting so that it's based on the end of the business day instead of the end of the calendar day.</span></span>

<span data-ttu-id="f0072-136">Na página **Lojas**, na Guia Rápida **Demonstrativo/fechamento**, no campo **Fim do dia útil**, insira a hora em que a última transação deve ser registrada para ser incluída no demonstrativo do dia útil.</span><span class="sxs-lookup"><span data-stu-id="f0072-136">On the **Stores** page, on the **Statement/closing** FastTab, in the **End of business day** field, enter the time that the last transaction must be recorded to be included in the business day's statement.</span></span> <span data-ttu-id="f0072-137">Marque a caixa de seleção **Lançar como dia útil** para lançar as transações dentro do mesmo dia útil.</span><span class="sxs-lookup"><span data-stu-id="f0072-137">Select the **Post as business day** check box to post the transactions within the same business day.</span></span> <span data-ttu-id="f0072-138">Quando o demonstrativo é lançado, as transações que são registradas no mesmo dia útil podem ser incluídas na mesma ordem de venda, mesmo que algumas transações ocorram antes e outras depois da meia-noite.</span><span class="sxs-lookup"><span data-stu-id="f0072-138">When the statement is posted, transactions that are recorded within the same business day can be included on the same sales order, even if some transactions occur before midnight and other transactions occur after midnight.</span></span>

#### <a name="example-post-a-statement-for-a-business-day-that-extends-over-two-calendar-days"></a><span data-ttu-id="f0072-139">Exemplo: lançar um demonstrativo para um dia útil que se estenda sobre dois dias do calendário</span><span class="sxs-lookup"><span data-stu-id="f0072-139">Example: Post a statement for a business day that extends over two calendar days</span></span>

<span data-ttu-id="f0072-140">Uma loja é aberta entre 8:00 e 3:00 e a caixa de seleção **Lançar como dia útil** é marcada na configuração da loja.</span><span class="sxs-lookup"><span data-stu-id="f0072-140">A store is open between 8:00 AM and 3:00 AM, and the **Post as business day** check box is selected in the store's configuration.</span></span> <span data-ttu-id="f0072-141">Em 31 de maio, a loja registra transações entre 8:00 e meia-noite.</span><span class="sxs-lookup"><span data-stu-id="f0072-141">On May 31, the store records transactions between 8:00 AM and midnight.</span></span> <span data-ttu-id="f0072-142">A loja também registra transações entre 12:01 e 3:00 em 1º de junho.</span><span class="sxs-lookup"><span data-stu-id="f0072-142">The store also records transactions between 12:01 AM and 3:00 AM on June 1.</span></span>

<span data-ttu-id="f0072-143">Quando a loja lança seu demonstrativo para o fechamento do dia útil, a ordem de venda que é gerada inclui todas as transações que foram registradas entre 8:00 e 3:00h, mesmo que as transações tenham ocorrido em dois dias, 31 de maio e 1° de junho.</span><span class="sxs-lookup"><span data-stu-id="f0072-143">When the store posts its statement for the close of the business day, the sales order that is generated includes all transactions that were recorded between the business hours of 8:00 AM and 3:00 AM, even though the transactions occurred on two days, May 31 and June 1.</span></span>

<span data-ttu-id="f0072-144">Se a caixa de seleção **Lançar como dia útil** for desmarcada para a mesma loja, as ordens de venda separada são geradas quando a loja lança seu demonstrativo para o fechamento do dia útil.</span><span class="sxs-lookup"><span data-stu-id="f0072-144">If the **Post as business day** check box is cleared for the same store, separate sales orders are generated when the store posts its statement for the close of the business day.</span></span> <span data-ttu-id="f0072-145">Uma ordem de venda inclui as transações que foram registradas entre os horários 8:00 e a meia-noite de 31 de maio, e a segunda ordem de venda inclui transações que foram registradas entre 12:01 e 3:00 de 1º de junho do horário comercial.</span><span class="sxs-lookup"><span data-stu-id="f0072-145">One sales order includes the transactions that were recorded between the business hours of 8:00 AM and midnight on May 31, and the second sales order includes the transactions that were recorded between the business hours of 12:01 AM and 3:00 AM on June 1.</span></span>

> [!NOTE]
> <span data-ttu-id="f0072-146">Antes de criar demonstrativos, você deve fechar os turnos no período do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="f0072-146">Before you can create statements, you should close the shifts in the statement period.</span></span>

### <a name="post-the-statement"></a><span data-ttu-id="f0072-147">Lançar o demonstrativo</span><span class="sxs-lookup"><span data-stu-id="f0072-147">Post the statement</span></span>

<span data-ttu-id="f0072-148">Quando você lançar um demonstrativo, as ordens de venda e faturas são criadas para as vendas no demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="f0072-148">When you post a statement, sales orders and invoices are created for the sales in the statement.</span></span>

- <span data-ttu-id="f0072-149">As vendas à vista e realizadas são agregadas em ordens de venda e são faturadas para o cliente padrão que está atribuído à loja.</span><span class="sxs-lookup"><span data-stu-id="f0072-149">Cash and carry sales are aggregated onto one sales order, and are invoiced for the default customer who is assigned to the store.</span></span>
- <span data-ttu-id="f0072-150">As vendas para as quais um cliente foi adicionado à transação no PDV geram ordens de venda e faturas separadas, uma para cada cliente exclusivo.</span><span class="sxs-lookup"><span data-stu-id="f0072-150">Sales for which a customer was added to the transaction in POS generate separate sales orders and invoices, one for each unique customer.</span></span>

<span data-ttu-id="f0072-151">Os diários de pagamentos são criados automaticamente para os pagamentos no demonstrativo e o estoque é atualizado para a loja POS.</span><span class="sxs-lookup"><span data-stu-id="f0072-151">Payment journals are automatically created for the payments in the statement, and the inventory is updated for the POS store.</span></span>
