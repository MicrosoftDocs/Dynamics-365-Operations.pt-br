---
title: Dividir um ativo fixo
description: Este tópico explica como dividir uma porcentagem do registro de ativos em um novo registro de ativos.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 85ccf187e77faf338ac29452d823c3652b806a21
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138106"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="589c8-103">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="589c8-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="589c8-104">Este tópico explica como dividir uma porcentagem do registro de ativos em um novo registro de ativos.</span><span class="sxs-lookup"><span data-stu-id="589c8-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="589c8-105">Usa os dados de função de contador e de demonstração de USMF.</span><span class="sxs-lookup"><span data-stu-id="589c8-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="589c8-106">Criar um novo ativo fixo</span><span class="sxs-lookup"><span data-stu-id="589c8-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="589c8-107">No Painel de Navegação, vá para **Módulos > Ativos fixos > Ativos fixos > Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="589c8-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="589c8-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="589c8-108">Select **New**.</span></span>
3. <span data-ttu-id="589c8-109">No campo **Grupo de ativo fixo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="589c8-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="589c8-110">Anote o número do ativo fixo a ser usado posteriormente no processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="589c8-110">Note the fixed asset number to use in the split process later.</span></span>  
4. <span data-ttu-id="589c8-111">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="589c8-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="589c8-112">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="589c8-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="589c8-113">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="589c8-113">Split a fixed asset</span></span>
1. <span data-ttu-id="589c8-114">Na lista, localize e selecione o link do ativo fixo que você deseja dividir.</span><span class="sxs-lookup"><span data-stu-id="589c8-114">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="589c8-115">Selecione **Registros**.</span><span class="sxs-lookup"><span data-stu-id="589c8-115">Select **Books**.</span></span> <span data-ttu-id="589c8-116">Selecione o registro a ser dividido no novo ativo.</span><span class="sxs-lookup"><span data-stu-id="589c8-116">Select the book to split to the new asset.</span></span>  
3. <span data-ttu-id="589c8-117">Selecione **Funções**.</span><span class="sxs-lookup"><span data-stu-id="589c8-117">Select **Functions**.</span></span>
4. <span data-ttu-id="589c8-118">Selecione **Dividir ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="589c8-118">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="589c8-119">No campo **Para o ativo fixo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="589c8-119">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="589c8-120">No campo **Para o registro**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="589c8-120">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="589c8-121">No campo **Data de transação**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="589c8-121">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="589c8-122">No campo **Porcentagem**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="589c8-122">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="589c8-123">No campo **Nome do diário**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="589c8-123">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="589c8-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="589c8-124">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="589c8-125">Lançar a transação de diário</span><span class="sxs-lookup"><span data-stu-id="589c8-125">Post the journal transaction</span></span>
1. <span data-ttu-id="589c8-126">No Painel de navegação, vá para **Módulos > Ativos fixos > Entradas de diário > Diário de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="589c8-126">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="589c8-127">Na lista, selecione o diário criado com o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="589c8-127">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="589c8-128">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="589c8-128">Select **Lines**.</span></span>

    - <span data-ttu-id="589c8-129">Verifique as linhas de diário criadas.</span><span class="sxs-lookup"><span data-stu-id="589c8-129">Verify the journal lines created.</span></span>  
    - <span data-ttu-id="589c8-130">Uma transação de ajuste de aquisição é criada para o ativo original diminuir o valor por porcentagem especificada durante o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="589c8-130">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  
    - <span data-ttu-id="589c8-131">Uma transação de aquisição é criada para o novo ativo para a mesma quantidade.</span><span class="sxs-lookup"><span data-stu-id="589c8-131">An Acquisition transaction is created for the new asset for the same amount.</span></span>  

4. <span data-ttu-id="589c8-132">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="589c8-132">Select **Post**.</span></span>

