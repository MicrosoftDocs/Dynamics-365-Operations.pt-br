--- 
title: Dividir um ativo fixo
description: "Este guia da tarefas dividirá uma porcentagem do registro de ativos em um novo registro de ativos."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b4c1b39bcae1fa3830f3a217d1ad89e84cd72134
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="cf1c9-103">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="cf1c9-103">Split a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cf1c9-104">Este guia da tarefas dividirá uma porcentagem do registro de ativos em um novo registro de ativos.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="cf1c9-105">Usa os dados de função de contador e de demonstração de USMF.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="cf1c9-106">Criar um novo ativo fixo</span><span class="sxs-lookup"><span data-stu-id="cf1c9-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="cf1c9-107">Vá para Ativos fixos > Ativos fixos > Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="cf1c9-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-108">Click New.</span></span>
3. <span data-ttu-id="cf1c9-109">No campo Grupo de ativo fixo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="cf1c9-110">Anote o número do ativo fixo a ser usado posteriormente no processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="cf1c9-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="cf1c9-112">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="cf1c9-113">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="cf1c9-113">Split a fixed asset</span></span>
1. <span data-ttu-id="cf1c9-114">Na lista, localize e selecione o ativo fixo que você deseja dividir.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="cf1c9-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="cf1c9-116">Clique em Registros.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-116">Click Books.</span></span>
    * <span data-ttu-id="cf1c9-117">Selecione o registro a ser dividido no novo ativo.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="cf1c9-118">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-118">Click Functions.</span></span>
5. <span data-ttu-id="cf1c9-119">Clique em Dividir ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="cf1c9-120">No campo Para o ativo fixo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="cf1c9-121">No campo Para o registro, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="cf1c9-122">No campo Transação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="cf1c9-123">No campo Porcentagem, insira um número.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="cf1c9-124">No campo Diário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="cf1c9-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="cf1c9-126">Lançar a transação de diário</span><span class="sxs-lookup"><span data-stu-id="cf1c9-126">Post the journal transaction</span></span>
1. <span data-ttu-id="cf1c9-127">Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="cf1c9-128">Na lista, selecione o diário criado com o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="cf1c9-129">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-129">Click Lines.</span></span>
    * <span data-ttu-id="cf1c9-130">Verifique as linhas de diário criadas.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-130">Verify the journal lines created.</span></span>  <span data-ttu-id="cf1c9-131">Uma transação de ajuste de aquisição é criada para o ativo original diminuir o valor por porcentagem especificada durante o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="cf1c9-132">Uma transação de aquisição é criada para o novo ativo para a mesma quantidade.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="cf1c9-133">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="cf1c9-133">Click Post.</span></span>


