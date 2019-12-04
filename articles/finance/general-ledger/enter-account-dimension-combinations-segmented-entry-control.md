---
title: Insira a conta e as combinações de dimensões (controle segmentado de entradas)
description: Este artigo descreve como inserir a conta e as combinações de dimensões ou contas contábeis. A experiência de entrada é também conhecida como o controle segmentado de entrada.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 872ee7812d98e6102798c3a10773176541c02c90
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186638"
---
# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a><span data-ttu-id="6ce13-104">Insira a conta e as combinações de dimensões (controle segmentado de entradas)</span><span class="sxs-lookup"><span data-stu-id="6ce13-104">Enter account and dimension combinations (segmented entry control)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ce13-105">Este artigo descreve como inserir a conta e as combinações de dimensões ou contas contábeis.</span><span class="sxs-lookup"><span data-stu-id="6ce13-105">This article describes how to enter account and dimension combinations or ledger accounts.</span></span> <span data-ttu-id="6ce13-106">A experiência de entrada é também conhecida como o controle segmentado de entrada.</span><span class="sxs-lookup"><span data-stu-id="6ce13-106">The entry experience is often referred to as segmented entry control.</span></span>

<span data-ttu-id="6ce13-107">Os usuários inserem as combinações de conta e dimensão em várias páginas como páginas para diários gerais, orçamento e definições de lançamentos.</span><span class="sxs-lookup"><span data-stu-id="6ce13-107">Users enter account and dimension combinations on various pages, such as pages for general journals, budgeting, and posting definitions.</span></span> <span data-ttu-id="6ce13-108">A conta válida e as combinações de dimensão dependem das estruturas de conta que são atribuídas ao razão e as regras avançadas que são atribuídas às estruturas da conta.</span><span class="sxs-lookup"><span data-stu-id="6ce13-108">The valid account and dimension combinations depend on the account structures that are assigned to the ledger and the advanced rules that are assigned to the account structures.</span></span> <span data-ttu-id="6ce13-109">Quando os usuários inserem combinações, eles podem digitar manualmente os valores ou aproveitar uma experiência rica de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6ce13-109">When users enter a combination, they can either manually type the values or take advantage of a rich, lookup experience.</span></span> <span data-ttu-id="6ce13-110">Quando entrar no campo, você poderá começar a digitar e pesquisar o valor e a descrição.</span><span class="sxs-lookup"><span data-stu-id="6ce13-110">When you enter the field, you can start to type and it will search the value and the description.</span></span> <span data-ttu-id="6ce13-111">Por exemplo, se você digitar 180 será pesquisado qualquer valor que inicie com essa combinação numérica.</span><span class="sxs-lookup"><span data-stu-id="6ce13-111">For example, if you type 180 it will search any value that begins with that number combination.</span></span> <span data-ttu-id="6ce13-112">Ou é possível digitar Dinheiro e será pesquisado qualquer valor que tenha uma descrição que começa com Pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="6ce13-112">Or you may type Cash and it will search any value that has a description that begins with Cash.</span></span> <span data-ttu-id="6ce13-113">Você também pode usar um curinga, como \*Pagamento à vista ou \*180 para pesquisar se o valor ou descrição contém os critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6ce13-113">You can also use a wildcard, such as \*Cash or \*180 to search if the value or description contain the search criteria.</span></span> 

<span data-ttu-id="6ce13-114">A tabela a seguir descreve os atalhos de teclado que podem ser usados quando a pesquisa estiver fechada.</span><span class="sxs-lookup"><span data-stu-id="6ce13-114">The following table describes the keyboard shortcuts that can be used when the lookup is closed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ce13-115">Atalho do teclado</span><span class="sxs-lookup"><span data-stu-id="6ce13-115">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="6ce13-116">Ação</span><span class="sxs-lookup"><span data-stu-id="6ce13-116">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6ce13-117">Alt+Seta para baixo</span><span class="sxs-lookup"><span data-stu-id="6ce13-117">Alt+Down Arrow</span></span></td>
<td><span data-ttu-id="6ce13-118">Abra a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6ce13-118">Open the lookup.</span></span> <span data-ttu-id="6ce13-119">Se você pressionar Alt+Seta para baixo novamente, o foco é alterado para os segmentos em submenu.</span><span class="sxs-lookup"><span data-stu-id="6ce13-119">If you press Alt+Down Arrow a second time, the focus moves to the segments in the flyout.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="6ce13-120">Enter e Shift+Enter</span><span class="sxs-lookup"><span data-stu-id="6ce13-120">Enter and Shift+Enter</span></span></li>
<li><span data-ttu-id="6ce13-121">Delimitador do plano de contas</span><span class="sxs-lookup"><span data-stu-id="6ce13-121">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="6ce13-122">Seta para a direita e seta para esquerda</span><span class="sxs-lookup"><span data-stu-id="6ce13-122">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="6ce13-123">Mova para o próximo segmento ou segmento anterior.</span><span class="sxs-lookup"><span data-stu-id="6ce13-123">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6ce13-124">Tabulação</span><span class="sxs-lookup"><span data-stu-id="6ce13-124">Tab</span></span></td>
<td><span data-ttu-id="6ce13-125">Mova para o próximo campo na grade.</span><span class="sxs-lookup"><span data-stu-id="6ce13-125">Move to the next field in the grid.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="6ce13-126">A tabela a seguir descreve os atalhos de teclado que podem ser usados quando a pesquisa estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="6ce13-126">The following table describes the keyboard shortcuts that can be used when the lookup is open.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ce13-127">Atalho do teclado</span><span class="sxs-lookup"><span data-stu-id="6ce13-127">Keyboard shortcut</span></span></th>
<th><span data-ttu-id="6ce13-128">Ação</span><span class="sxs-lookup"><span data-stu-id="6ce13-128">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6ce13-129">Esc</span><span class="sxs-lookup"><span data-stu-id="6ce13-129">Esc</span></span></td>
<td><span data-ttu-id="6ce13-130">Feche a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6ce13-130">Close the lookup.</span></span></td>
</tr>
<tr class="even">
<td><ul>
<li><span data-ttu-id="6ce13-131">Seta para cima e seta para baixo</span><span class="sxs-lookup"><span data-stu-id="6ce13-131">Up Arrow and Down Arrow</span></span></li>
<li><span data-ttu-id="6ce13-132">Page Up e Page Down</span><span class="sxs-lookup"><span data-stu-id="6ce13-132">Page Up and Page Down</span></span></li>
<li><span data-ttu-id="6ce13-133">Home e End</span><span class="sxs-lookup"><span data-stu-id="6ce13-133">Home and End</span></span></li>
</ul></td>
<td><span data-ttu-id="6ce13-134">Mover para o próximo valor ou valor anterior nas listas, para o grupo anterior ou próximo grupo de valores ou para o primeiro ou último elemento na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6ce13-134">Move to the previous or next value in the lists, to the previous or next group of values, or to the first or last element in the lookup.</span></span></td>
</tr>
<tr class="odd">
<td><ul>
<li><span data-ttu-id="6ce13-135">Delimitador do plano de contas</span><span class="sxs-lookup"><span data-stu-id="6ce13-135">Chart of accounts delimiter</span></span></li>
<li><span data-ttu-id="6ce13-136">Seta para a direita e seta para esquerda</span><span class="sxs-lookup"><span data-stu-id="6ce13-136">Right Arrow and Left Arrow</span></span></li>
</ul></td>
<td><span data-ttu-id="6ce13-137">Mova para o próximo segmento ou segmento anterior.</span><span class="sxs-lookup"><span data-stu-id="6ce13-137">Move to the next or previous segment.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6ce13-138">Guia</span><span class="sxs-lookup"><span data-stu-id="6ce13-138">Tab</span></span></td>
<td><span data-ttu-id="6ce13-139">Mova para o próximo campo na grade.</span><span class="sxs-lookup"><span data-stu-id="6ce13-139">Move to the next field in the grid.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6ce13-140">Alt+W</span><span class="sxs-lookup"><span data-stu-id="6ce13-140">Alt+W</span></span></td>
<td><span data-ttu-id="6ce13-141">Alterna entre <strong>Mostrar tudo</strong> e <strong>Mostrar válido</strong>.</span><span class="sxs-lookup"><span data-stu-id="6ce13-141">Switch between <strong>Show all</strong> and <strong>Show valid</strong>.</span></span></td>
</tr>
</tbody>
</table>




