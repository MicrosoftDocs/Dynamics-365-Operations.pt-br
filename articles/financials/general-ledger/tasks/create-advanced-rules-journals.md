---
title: Criar regras avançadas para diários
description: Este procedimento aborda a criação de regras avançadas para diários.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e3fc764a6fa92a050084ae610a11acac46995d2a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553098"
---
# <a name="create-advanced-rules-for-journals"></a><span data-ttu-id="94c8b-103">Criar regras avançadas para diários</span><span class="sxs-lookup"><span data-stu-id="94c8b-103">Create advanced rules for journals</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="94c8b-104">Este procedimento aborda a criação de regras avançadas para diários.</span><span class="sxs-lookup"><span data-stu-id="94c8b-104">This procedure steps through creating advanced rules for journals.</span></span> <span data-ttu-id="94c8b-105">Inclui a configuração de controle de diário e restrições de lançamento de usuário.</span><span class="sxs-lookup"><span data-stu-id="94c8b-105">This includes setting up journal control and user posting restrictions.</span></span> <span data-ttu-id="94c8b-106">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="94c8b-106">This procedure uses the USMF demo data company.</span></span>


## <a name="set-up-journal-control"></a><span data-ttu-id="94c8b-107">Configurar controle do diário</span><span class="sxs-lookup"><span data-stu-id="94c8b-107">Set up journal control</span></span>
1. <span data-ttu-id="94c8b-108">Vá para Contabilidade > Configuração do diário > Nomes de diário.</span><span class="sxs-lookup"><span data-stu-id="94c8b-108">Go to General ledger > Journal setup > Journal names.</span></span>
2. <span data-ttu-id="94c8b-109">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="94c8b-109">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="94c8b-110">Clique em Controle de diário.</span><span class="sxs-lookup"><span data-stu-id="94c8b-110">Click Journal control.</span></span>
4. <span data-ttu-id="94c8b-111">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="94c8b-111">Click Add.</span></span>
5. <span data-ttu-id="94c8b-112">No campo Contas da empresa, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="94c8b-112">In the Company accounts field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="94c8b-113">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="94c8b-113">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="94c8b-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="94c8b-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="94c8b-115">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="94c8b-115">Click Add.</span></span>
9. <span data-ttu-id="94c8b-116">No campo Estrutura de conta, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="94c8b-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="94c8b-117">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="94c8b-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="94c8b-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="94c8b-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="94c8b-119">No campo Segmento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="94c8b-119">In the Segment field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="94c8b-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="94c8b-120">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="94c8b-121">No campo Valor inicial, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="94c8b-121">In the From value field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="94c8b-122">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="94c8b-122">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="94c8b-123">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="94c8b-123">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="94c8b-124">No campo Valor final, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="94c8b-124">In the To value field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="94c8b-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="94c8b-125">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="94c8b-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="94c8b-126">In the list, click the link in the selected row.</span></span>

## <a name="set-up-posting-restrictions"></a><span data-ttu-id="94c8b-127">Configurar restrições de lançamento</span><span class="sxs-lookup"><span data-stu-id="94c8b-127">Set up posting restrictions</span></span>
1. <span data-ttu-id="94c8b-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="94c8b-128">Close the page.</span></span>
2. <span data-ttu-id="94c8b-129">Clique em Restrições de lançamento.</span><span class="sxs-lookup"><span data-stu-id="94c8b-129">Click Posting restrictions.</span></span>
3. <span data-ttu-id="94c8b-130">No Como deseja configurar as restrições de lançamento, selecione Por grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="94c8b-130">In the How do you want to set up posting restrictions, select By user group.</span></span>
4. <span data-ttu-id="94c8b-131">Na árvore, verifique 'o grupo do qual deseja permitir o lançamento para o nome desse diário'.</span><span class="sxs-lookup"><span data-stu-id="94c8b-131">In the tree, check 'the group that you want to allow posting for this journal name.'.</span></span>
5. <span data-ttu-id="94c8b-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="94c8b-132">Click OK.</span></span>

