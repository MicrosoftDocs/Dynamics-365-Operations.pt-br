---
title: Criar um orçamento preliminar para o setor público
description: Você pode criar entradas de registro de orçamento preliminar para um modelo de orçamento específico e valores de dimensão.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c7937402f63db23c2b42d61c584c17dce5e1bf10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811206"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="5c1cb-103">Criar um orçamento preliminar para o setor público</span><span class="sxs-lookup"><span data-stu-id="5c1cb-103">Create a preliminary budget for Public sector</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5c1cb-104">Você pode criar entradas de registro de orçamento preliminar para um modelo de orçamento específico e valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="5c1cb-105">Depois que o orçamento real for aprovado, você pode criar entradas de registro do orçamento original.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="5c1cb-106">Este procedimento foi criado usando os dados da empresa de demonstração PSUS na partição do setor público.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="5c1cb-107">Vá para Orçamento > Entradas de registro de orçamento.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="5c1cb-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-108">Click New.</span></span>
3. <span data-ttu-id="5c1cb-109">No campo Modelo de orçamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="5c1cb-110">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="5c1cb-111">No campo Orçamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="5c1cb-112">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="5c1cb-113">No campo Motivo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="5c1cb-114">Na lista, clique no registro desejado.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="5c1cb-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-115">Click Save.</span></span>
10. <span data-ttu-id="5c1cb-116">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-116">Click Add line.</span></span>
    * <span data-ttu-id="5c1cb-117">Opcionais: Se quiser alterar a data de em um cabeçalho, insira uma nova data.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="5c1cb-118">Esta data determina o período fiscal no qual o orçamento será registrado.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="5c1cb-119">Ao exibir a guia de tarefas, para preencher outros campos, clique Desbloquear na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="5c1cb-120">No campo Estrutura de conta, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="5c1cb-121">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="5c1cb-122">No campo Valores de dimensão, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="5c1cb-123">No campo Valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="5c1cb-124">Você também pode inserir um tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="5c1cb-125">No campo Moeda, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="5c1cb-126">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="5c1cb-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-127">Click Save.</span></span>
18. <span data-ttu-id="5c1cb-128">Clique em Atualizar saldos de orçamentos.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="5c1cb-129">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-129">Click Update.</span></span>
    * <span data-ttu-id="5c1cb-130">Para ver os resultados da atualização, clique em Detalhes da mensagem na barra azul.</span><span class="sxs-lookup"><span data-stu-id="5c1cb-130">To see the results of the update, click Message details on the blue bar.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]