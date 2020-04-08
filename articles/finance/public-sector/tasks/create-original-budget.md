---
title: Criar um orçamento original e depois reverter entradas de orçamento preliminar no setor público
description: Quando você cria uma entrada de orçamento original e usa o modelo de orçamento e os valores de dimensão que contêm valores de orçamento preliminar, os valores de orçamento preliminar podem ser revertidos.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32d89216d49a743729de8910f738276cbddcd8bb
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144536"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a><span data-ttu-id="22702-103">Criar um orçamento original e depois reverter entradas de orçamento preliminar no setor público</span><span class="sxs-lookup"><span data-stu-id="22702-103">Create an original budget and then reverse preliminary budget entries in the public sector</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="22702-104">Quando você cria uma entrada de orçamento original e usa o modelo de orçamento e os valores de dimensão que contêm valores de orçamento preliminar, os valores de orçamento preliminar podem ser revertidos.</span><span class="sxs-lookup"><span data-stu-id="22702-104">When you create an original budget entry and use the budget model and dimension values that contain preliminary budget amounts, the preliminary budget amounts can be reversed.</span></span> <span data-ttu-id="22702-105">Este procedimento foi criado usando os dados da empresa de demonstração PSUS na partição do setor público.</span><span class="sxs-lookup"><span data-stu-id="22702-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="22702-106">Vá para Orçamento > Entradas de registro de orçamento.</span><span class="sxs-lookup"><span data-stu-id="22702-106">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="22702-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="22702-107">Click New.</span></span>
3. <span data-ttu-id="22702-108">No campo Modelo de orçamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="22702-108">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="22702-109">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="22702-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="22702-110">No campo Orçamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="22702-110">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="22702-111">Na lista, clique em Orçamento original.</span><span class="sxs-lookup"><span data-stu-id="22702-111">In the list, click Original budget.</span></span>
7. <span data-ttu-id="22702-112">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="22702-112">Click Save.</span></span>
8. <span data-ttu-id="22702-113">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="22702-113">Click Add line.</span></span>
9. <span data-ttu-id="22702-114">Opcionais: Se quiser alterar a data de em um cabeçalho, insira uma nova data.</span><span class="sxs-lookup"><span data-stu-id="22702-114">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="22702-115">Esta data determina o período fiscal no qual o orçamento será registrado.</span><span class="sxs-lookup"><span data-stu-id="22702-115">This date determines the fiscal period that the budget will be recorded to.</span></span>
10. <span data-ttu-id="22702-116">No campo Estrutura de conta, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="22702-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="22702-117">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="22702-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="22702-118">No campo Valores de dimensão, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="22702-118">In the Dimension values field, specify the desired values.</span></span>
13. <span data-ttu-id="22702-119">No campo Valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="22702-119">In the Amount field, enter a number.</span></span>
14. <span data-ttu-id="22702-120">No campo Moeda, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="22702-120">In the Currency field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="22702-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="22702-121">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="22702-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="22702-122">Click Save.</span></span>
17. <span data-ttu-id="22702-123">Clique em Atualizar saldos de orçamentos.</span><span class="sxs-lookup"><span data-stu-id="22702-123">Click Update budget balances.</span></span>
    * <span data-ttu-id="22702-124">Opcionais: Você pode selecionar a opção Reverter orçamento preliminar.</span><span class="sxs-lookup"><span data-stu-id="22702-124">Optional: You can select the Reverse preliminary budget option.</span></span> <span data-ttu-id="22702-125">Observe que você pode reverter todas as entradas de orçamento preliminar, ou somente as entradas de orçamento preliminar com o código de orçamento que você especificar.</span><span class="sxs-lookup"><span data-stu-id="22702-125">Note that you can reverse all preliminary budget entries, or only the preliminary budget entries that have the budget code that you specify.</span></span>  
    * <span data-ttu-id="22702-126">Para fazer seleções opcionais, clique no ícone Desbloquear na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="22702-126">To make optional selections, click the Unlock icon at the top of the page.</span></span>  
18. <span data-ttu-id="22702-127">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="22702-127">Click Update.</span></span>

