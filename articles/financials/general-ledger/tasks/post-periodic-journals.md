--- 
title: "Lançar diários periódicos"
description: "Os diários periódicos são as vezes chamados diários de devolução porque o valor, o texto, e outras informações são repetidos toda vez que o diário periódico é recuperado."
author: aprilolson
manager: AnnBe
ms.date: 02/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 4132f647d8fa225b402a006f0da2347ac9660fa0
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="post-periodic-journals"></a><span data-ttu-id="3975d-103">Lançar diários periódicos</span><span class="sxs-lookup"><span data-stu-id="3975d-103">Post periodic journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3975d-104">Os diários periódicos são as vezes chamados diários de devolução porque o valor, o texto, e outras informações são repetidos toda vez que o diário periódico é recuperado.</span><span class="sxs-lookup"><span data-stu-id="3975d-104">Periodic journals are sometimes called recurring journals because the amount, text, and other information are repeated each time that the periodic journal is retrieved.</span></span> <span data-ttu-id="3975d-105">Quando você cria o diário periódico, você especifica o intervalo do período para a recorrência, como dias ou meses.</span><span class="sxs-lookup"><span data-stu-id="3975d-105">When you create the periodic journal, you specify the period interval for the recurrence, such as days or months.</span></span> <span data-ttu-id="3975d-106">Essa guia da tarefa criará um diário periódico com uma recorrência mensal.</span><span class="sxs-lookup"><span data-stu-id="3975d-106">This task guide will create a periodic journal with a monthly recurrence.</span></span>



1. <span data-ttu-id="3975d-107">Vá para Contabilidade > Tarefas periódicas > Diários periódicos.</span><span class="sxs-lookup"><span data-stu-id="3975d-107">Go to General ledger > Periodic tasks > Periodic journals.</span></span>
2. <span data-ttu-id="3975d-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3975d-108">Click New.</span></span>
3. <span data-ttu-id="3975d-109">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3975d-109">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="3975d-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3975d-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="3975d-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3975d-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="3975d-112">A descrição será o nome do diário periódico quando recuperada posteriormente e isso garantirá atribuir um nome relevante.</span><span class="sxs-lookup"><span data-stu-id="3975d-112">The description will be the name of the Periodic journal when retrieved later so make sure to give it a relevant name.</span></span>  
6. <span data-ttu-id="3975d-113">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="3975d-113">Click Lines.</span></span>
    * <span data-ttu-id="3975d-114">Um diário periódico incluirá normalmente várias linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="3975d-114">A periodic journal will typically include several journal lines.</span></span> <span data-ttu-id="3975d-115">essa guia de tarefa no entanto adicionará apenas uma linha.</span><span class="sxs-lookup"><span data-stu-id="3975d-115">this task guide will however only add one line.</span></span>  
7. <span data-ttu-id="3975d-116">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="3975d-116">In the Date field, enter a date.</span></span>
    * <span data-ttu-id="3975d-117">O campo Data contém a data de lançamento da próxima transferência para o diário.</span><span class="sxs-lookup"><span data-stu-id="3975d-117">The Date field contains the posting date for the next transfer to the daily journal.</span></span> <span data-ttu-id="3975d-118">Para os diários que serão recuperados cada mês na qual recomenda-se usar a data do mês em que será lançado, normalmente a primeira e a última data do período.</span><span class="sxs-lookup"><span data-stu-id="3975d-118">For journals that will be retrieved each month it is recommended to use the date in the month when it will be posted, typically the first or last date in the period.</span></span> <span data-ttu-id="3975d-119">É possível deixar o campo Data e inserir uma data quando o diário for recuperado, usando o campo vazio de data.</span><span class="sxs-lookup"><span data-stu-id="3975d-119">It is possible to leave the Date field blank and to give a date when the journal is retrieved, using the Empty date field.</span></span>    <span data-ttu-id="3975d-120">O campo é atualizado automaticamente para a próxima data de devolução em que as transações são recuperadas.</span><span class="sxs-lookup"><span data-stu-id="3975d-120">The field is automatically updated to the next recurring date when transactions are retrieved.</span></span>  
8. <span data-ttu-id="3975d-121">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="3975d-121">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="3975d-122">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3975d-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="3975d-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="3975d-123">Close the page.</span></span>
11. <span data-ttu-id="3975d-124">No campo Débito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="3975d-124">In the Debit field, enter a number.</span></span>
12. <span data-ttu-id="3975d-125">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="3975d-125">In the Offset account field, specify the desired values.</span></span>
13. <span data-ttu-id="3975d-126">No campo Unidade, selecione 'Meses'.</span><span class="sxs-lookup"><span data-stu-id="3975d-126">In the Unit field, select 'Months'.</span></span>
14. <span data-ttu-id="3975d-127">No campo Número de unidades, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="3975d-127">In the Number of units field, enter '1'.</span></span>
15. <span data-ttu-id="3975d-128">No campo Última data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="3975d-128">In the Last date field, enter a date.</span></span>
    * <span data-ttu-id="3975d-129">Inserir a última data do período anterior evitará que o diário de devolução seja criado por engano no período inicial incorreto.</span><span class="sxs-lookup"><span data-stu-id="3975d-129">Entering last date in the preceding period will prevent that the recurring journal by mistake is created in the wrong starting period.</span></span> <span data-ttu-id="3975d-130">A última data será atualizada posteriormente cada vez que o diário periódico for recuperado.</span><span class="sxs-lookup"><span data-stu-id="3975d-130">Last date will later on be updated each time the periodic journal is retrieved.</span></span>  
16. <span data-ttu-id="3975d-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3975d-131">Click Save.</span></span>
17. <span data-ttu-id="3975d-132">Ir para o painel Padrão.</span><span class="sxs-lookup"><span data-stu-id="3975d-132">Go to Default dashboard.</span></span>
18. <span data-ttu-id="3975d-133">Ir para Contabilidade > Entradas de diários > Diários gerais.</span><span class="sxs-lookup"><span data-stu-id="3975d-133">Go to General ledger > Journal entries > General journals.</span></span>
19. <span data-ttu-id="3975d-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3975d-134">Click New.</span></span>
20. <span data-ttu-id="3975d-135">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3975d-135">In the Name field, enter or select a value.</span></span>
21. <span data-ttu-id="3975d-136">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="3975d-136">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="3975d-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3975d-137">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="3975d-138">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3975d-138">In the Description field, type a value.</span></span>
24. <span data-ttu-id="3975d-139">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="3975d-139">Click Lines.</span></span>
25. <span data-ttu-id="3975d-140">Clique em Diário do período.</span><span class="sxs-lookup"><span data-stu-id="3975d-140">Click Period journal.</span></span>
26. <span data-ttu-id="3975d-141">Clique em Recuperar diário.</span><span class="sxs-lookup"><span data-stu-id="3975d-141">Click Retrieve journal.</span></span>
27. <span data-ttu-id="3975d-142">No campo Para data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="3975d-142">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="3975d-143">O Até a data serve como corte de data para as linhas de comprovante periódicas.</span><span class="sxs-lookup"><span data-stu-id="3975d-143">The To date serves as the cutoff date for the periodic voucher lines.</span></span> <span data-ttu-id="3975d-144">Com base na configuração de recorrência, a Última data e Até data da mesma linha podem ser incluídas mais de uma vez no diário resultante.</span><span class="sxs-lookup"><span data-stu-id="3975d-144">Based on the recurrence setting, the Last date and To date the same line might be included more than once in the resulting journal.</span></span> <span data-ttu-id="3975d-145">Até data é atualizado automaticamente com base na data da sessão de vezes em que a linha periódica foi transferida para um diário.</span><span class="sxs-lookup"><span data-stu-id="3975d-145">To date is automatically updated based on  session date of the last time the periodic line was transferred to a journal.</span></span>  
28. <span data-ttu-id="3975d-146">No campo Número de diário periódico, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3975d-146">In the Periodic journal number field, enter or select a value.</span></span>
29. <span data-ttu-id="3975d-147">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3975d-147">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="3975d-148">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="3975d-148">Click OK.</span></span>
    * <span data-ttu-id="3975d-149">O diário do período pode então ser revisto aprovado ou lançado, dependendo do requisito e da configuração.</span><span class="sxs-lookup"><span data-stu-id="3975d-149">The period journal can now be reviewed, approved or posted depending on requirement and setup.</span></span>  


