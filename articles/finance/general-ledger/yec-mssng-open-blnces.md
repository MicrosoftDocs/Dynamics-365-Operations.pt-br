---
title: Saldos iniciais ausentes do fechamento do exercício
description: Este tópico explica por que os saldos iniciais podem estar ausentes no fechamento de um exercício e como recriar esses saldos, se eles estiverem ausentes.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 045d0bf11b11c9a353858ce3ca82c698dbceea7c
ms.sourcegitcommit: 817716c2e96f24af0ef1d7d5323afdeccdc602f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "6028549"
---
# <a name="year-end-close-missing-opening-balances"></a><span data-ttu-id="fee43-103">Saldos iniciais ausentes do fechamento do exercício</span><span class="sxs-lookup"><span data-stu-id="fee43-103">Year-end close missing opening balances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fee43-104">Este tópico explica por que os saldos iniciais podem estar ausentes no fechamento de um exercício e como recriar esses saldos, se eles estiverem ausentes.</span><span class="sxs-lookup"><span data-stu-id="fee43-104">This topic explains why opening balances might be missing when you close a year, and how to rebuild those balances if they are missing.</span></span>

### <a name="symptom"></a><span data-ttu-id="fee43-105">Sintoma</span><span class="sxs-lookup"><span data-stu-id="fee43-105">Symptom</span></span>

<span data-ttu-id="fee43-106">Por que não há saldos iniciais após a execução do fechamento do exercício da Contabilidade?</span><span class="sxs-lookup"><span data-stu-id="fee43-106">Why are there no beginning balances after running the General ledger year-end close?</span></span> 

### <a name="resolution"></a><span data-ttu-id="fee43-107">Resolução</span><span class="sxs-lookup"><span data-stu-id="fee43-107">Resolution</span></span>

<span data-ttu-id="fee43-108">Veja os itens que devem ser verificados se você tiver fechado um exercício na Contabilidade e, em seguida, gerado um balancete que não exibe os saldos iniciais para o próximo ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="fee43-108">Here are things to check if you've closed a year in General ledger, and then generated a trial balance that doesn't display opening balances for the next fiscal year.</span></span>

<span data-ttu-id="fee43-109">Se o campo **Desfazer fechamento anterior** estiver definido como **Sim**, o fechamento do exercício anterior para o mesmo ano fiscal será revertido.</span><span class="sxs-lookup"><span data-stu-id="fee43-109">If the **Undo previous close** field is set to **Yes**, the previous year-end close for the same fiscal year is being reversed.</span></span> <span data-ttu-id="fee43-110">Ao executar um processo para reverter o fechamento do exercício, todas as entradas de saldo de fechamento e de saldo inicial serão excluídas, como se o fechamento do exercício nunca tivesse sido executado.</span><span class="sxs-lookup"><span data-stu-id="fee43-110">When running a process to reverse the year-end close, all entries for both closing and opening balances will be deleted, as if the year had never been closed.</span></span> <span data-ttu-id="fee43-111">Os comprovantes também serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="fee43-111">The vouchers are also deleted.</span></span> <span data-ttu-id="fee43-112">O processo de fechamento do exercício não será executado de forma automática novamente.</span><span class="sxs-lookup"><span data-stu-id="fee43-112">The year-end close process will not run again automatically.</span></span> <span data-ttu-id="fee43-113">Você deverá iniciar o processo novamente, desta vez atualizando a opção **Desfazer fechamento anterior** para **Não**.</span><span class="sxs-lookup"><span data-stu-id="fee43-113">You must start the process again, this time updating the **Undo previous close** option to **No**.</span></span>

<span data-ttu-id="fee43-114">Esse cenário é abordado no tópico Perguntas frequentes sobre fechamento do exercício.</span><span class="sxs-lookup"><span data-stu-id="fee43-114">This scenario is covered in the year-end close FAQ topic.</span></span> <span data-ttu-id="fee43-115">Para obter mais informações, consulte [Perguntas frequentes sobre fechamento do exercício](faq-year-end-activities.md).</span><span class="sxs-lookup"><span data-stu-id="fee43-115">For more information, see [Year-end activities FAQ](faq-year-end-activities.md).</span></span>

### <a name="symptom"></a><span data-ttu-id="fee43-116">Sintoma</span><span class="sxs-lookup"><span data-stu-id="fee43-116">Symptom</span></span>

<span data-ttu-id="fee43-117">Executei o fechamento do exercício com a opção **Desfazer fechamento anterior** definida como **Não** e ainda não tenho saldos iniciais para meu ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="fee43-117">I ran year-end close with the **Undo previous close** option set to **No**, and I still do not have opening balances for my fiscal year.</span></span>

### <a name="resolution"></a><span data-ttu-id="fee43-118">Resolução</span><span class="sxs-lookup"><span data-stu-id="fee43-118">Resolution</span></span>

<span data-ttu-id="fee43-119">Primeiramente, verifique o status do trabalho em lote.</span><span class="sxs-lookup"><span data-stu-id="fee43-119">First check the status of the batch job.</span></span> <span data-ttu-id="fee43-120">O fechamento de um exercício inclui várias tarefas separadas, mas a etapa mais importante é a tarefa em lote com a etapa de descrição **Tarefa 5.0.0**.</span><span class="sxs-lookup"><span data-stu-id="fee43-120">Closing a year includes a number of separate tasks, but the most critical step is the batch task with the task description **Step 5.0.0**.</span></span> <span data-ttu-id="fee43-121">O lançamento das transações de abertura e, opcionalmente, das transações de fechamento na Contabilidade ocorre durante essa etapa.</span><span class="sxs-lookup"><span data-stu-id="fee43-121">Posting the opening transactions, and optionally the closing transactions, to General ledger takes place during this step.</span></span> 

<span data-ttu-id="fee43-122">[![Lista de histórico de lotes](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span><span class="sxs-lookup"><span data-stu-id="fee43-122">[![Batch history list](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)</span></span>

<span data-ttu-id="fee43-123">Se essa etapa foi concluída com êxito, mas você não vê os saldos iniciais na página **Consulta de balancete** (**Contabilidade > Consultas e relatórios > Balancete**), examine os resultados do trabalho em lotes do fechamento do exercício para ver se a etapa Recriar saldos foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="fee43-123">If this step ended successfully but you don’t see opening balances on the **Trial balance inquiry** page (**General ledger > Inquires and reports > Trial balance**), review the results of the year-end close batch job to see if the Rebuild balances step completed successfully.</span></span>

<span data-ttu-id="fee43-124">[![Resultados do trabalho em lotes do fechamento do exercício](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span><span class="sxs-lookup"><span data-stu-id="fee43-124">[![Results of year-end close batch job](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)</span></span>

<span data-ttu-id="fee43-125">Se houve falha nessa etapa por algum motivo, provavelmente as transações de abertura (e opcionalmente as de fechamento) foram lançadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="fee43-125">If this step has failed for any reason, the opening (and optionally closing) transactions were likely posted successfully.</span></span> <span data-ttu-id="fee43-126">É possível verificar se as transações da Contabilidade foram lançadas com êxito usando a página **Consulta de transações de comprovante** especificando o número do comprovante e a data fornecidos na caixa de diálogo de fechamento do exercício para o exercício fechado, (**Contabilidade > Consultas e relatórios > Transações de comprovante**).</span><span class="sxs-lookup"><span data-stu-id="fee43-126">You can verify that the General ledger transactions were posted successfully using the **Voucher transactions inquiry** page by specifying the voucher number and date provided on the year-end close dialog for the year that you closed, (**General Ledger > Inquiries and reports > Voucher transactions**).</span></span>

<span data-ttu-id="fee43-127">[![Consulta de transações de comprovante](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span><span class="sxs-lookup"><span data-stu-id="fee43-127">[![Voucher transactions inquiry](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)</span></span>

<span data-ttu-id="fee43-128">Se os comprovantes de abertura (e, opcionalmente, de fechamento) estiverem presentes, não será necessário executar o fechamento do exercício novamente.</span><span class="sxs-lookup"><span data-stu-id="fee43-128">If the opening (and optionally closing) vouchers are present, you don’t need to run the year-end close again.</span></span> <span data-ttu-id="fee43-129">Em vez disso, consulte a próxima seção para obter mais informações sobre como avançar.</span><span class="sxs-lookup"><span data-stu-id="fee43-129">Instead refer to the next section for information about how to move forward.</span></span>

### <a name="symptom"></a><span data-ttu-id="fee43-130">Sintoma</span><span class="sxs-lookup"><span data-stu-id="fee43-130">Symptom</span></span>

<span data-ttu-id="fee43-131">Há falha na etapa "Recriar saldos" no fechamento do exercício. Devo executar novamente o processo inteiro de fechamento do exercício?</span><span class="sxs-lookup"><span data-stu-id="fee43-131">The “Rebuild balances” step in the year-end close failed, do I need to re-run the entire year-end close process?</span></span>

### <a name="resolution"></a><span data-ttu-id="fee43-132">Resolução</span><span class="sxs-lookup"><span data-stu-id="fee43-132">Resolution</span></span>

<span data-ttu-id="fee43-133">A etapa Recriar saldos atualiza os saldos da Contabilidade usados quando a Consulta de balancete é gerada.</span><span class="sxs-lookup"><span data-stu-id="fee43-133">The Rebuild balances step updates the General ledger balances that are used when the Trial balance inquiry is generated.</span></span>  <span data-ttu-id="fee43-134">É a etapa final do processo de fechamento do exercício.</span><span class="sxs-lookup"><span data-stu-id="fee43-134">It is the final step in the year-end close process.</span></span>  <span data-ttu-id="fee43-135">Se essa etapa for a única etapa com falha, as transações da Contabilidade foram lançadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="fee43-135">If this step is the only step that failed, the General ledger transactions have posted successfully.</span></span>  <span data-ttu-id="fee43-136">Não será necessário executar o fechamento do exercício novamente.</span><span class="sxs-lookup"><span data-stu-id="fee43-136">You do not need to run the year-end close again.</span></span> <span data-ttu-id="fee43-137">Você pode executar o processo para recriar os saldos manualmente usando a página **Conjuntos de dimensões financeiras** (**Contabilidade > Plano de contas > Dimensões > Conjuntos de dimensões financeiras**).</span><span class="sxs-lookup"><span data-stu-id="fee43-137">You can run the process to rebuild the balances manually using the **Financial dimension sets** page (**General ledger > Chart of accounts > Dimensions > Financial dimension sets**).</span></span>

<span data-ttu-id="fee43-138">[![Botão Recriar saldos na página Conjuntos de dimensões financeiras](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span><span class="sxs-lookup"><span data-stu-id="fee43-138">[![Rebuild balances button on Financial dimension sets page](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)</span></span>

<span data-ttu-id="fee43-139">Se essa etapa levar muito tempo para ser processada, recomendamos que você examine as práticas recomendadas para conjuntos de dimensões financeiras, conforme descrito em [Práticas recomendadas para atualizar Conjuntos de dimensões financeiras](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span><span class="sxs-lookup"><span data-stu-id="fee43-139">If this step takes a long time to process, we recommend reviewing the best practices for financial dimension sets as described in [Best practices for updating Financial dimension sets](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets).</span></span> 

