---
title: Dividir um ativo fixo
description: Este guia da tarefas dividirá uma porcentagem do registro de ativos em um novo registro de ativos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6be9de64265a4d7b5c91af3ee8acfce80c78e0f1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "333360"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="8f77f-103">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="8f77f-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8f77f-104">Este guia da tarefas dividirá uma porcentagem do registro de ativos em um novo registro de ativos.</span><span class="sxs-lookup"><span data-stu-id="8f77f-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="8f77f-105">Usa os dados de função de contador e de demonstração de USMF.</span><span class="sxs-lookup"><span data-stu-id="8f77f-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="8f77f-106">Criar um novo ativo fixo</span><span class="sxs-lookup"><span data-stu-id="8f77f-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="8f77f-107">Vá para Ativos fixos > Ativos fixos > Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="8f77f-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="8f77f-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8f77f-108">Click New.</span></span>
3. <span data-ttu-id="8f77f-109">No campo Grupo de ativo fixo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8f77f-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="8f77f-110">Anote o número do ativo fixo a ser usado posteriormente no processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="8f77f-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="8f77f-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="8f77f-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="8f77f-112">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="8f77f-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="8f77f-113">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="8f77f-113">Split a fixed asset</span></span>
1. <span data-ttu-id="8f77f-114">Na lista, localize e selecione o ativo fixo que você deseja dividir.</span><span class="sxs-lookup"><span data-stu-id="8f77f-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="8f77f-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="8f77f-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="8f77f-116">Clique em Registros.</span><span class="sxs-lookup"><span data-stu-id="8f77f-116">Click Books.</span></span>
    * <span data-ttu-id="8f77f-117">Selecione o registro a ser dividido no novo ativo.</span><span class="sxs-lookup"><span data-stu-id="8f77f-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="8f77f-118">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="8f77f-118">Click Functions.</span></span>
5. <span data-ttu-id="8f77f-119">Clique em Dividir ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="8f77f-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="8f77f-120">No campo Para o ativo fixo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8f77f-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="8f77f-121">No campo Para o registro, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8f77f-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="8f77f-122">No campo Transação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="8f77f-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="8f77f-123">No campo Porcentagem, insira um número.</span><span class="sxs-lookup"><span data-stu-id="8f77f-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="8f77f-124">No campo Diário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8f77f-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="8f77f-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8f77f-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="8f77f-126">Lançar a transação de diário</span><span class="sxs-lookup"><span data-stu-id="8f77f-126">Post the journal transaction</span></span>
1. <span data-ttu-id="8f77f-127">Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="8f77f-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="8f77f-128">Na lista, selecione o diário criado com o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="8f77f-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="8f77f-129">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="8f77f-129">Click Lines.</span></span>
    * <span data-ttu-id="8f77f-130">Verifique as linhas de diário criadas.</span><span class="sxs-lookup"><span data-stu-id="8f77f-130">Verify the journal lines created.</span></span>  <span data-ttu-id="8f77f-131">Uma transação de ajuste de aquisição é criada para o ativo original diminuir o valor por porcentagem especificada durante o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="8f77f-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="8f77f-132">Uma transação de aquisição é criada para o novo ativo para a mesma quantidade.</span><span class="sxs-lookup"><span data-stu-id="8f77f-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="8f77f-133">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="8f77f-133">Click Post.</span></span>

