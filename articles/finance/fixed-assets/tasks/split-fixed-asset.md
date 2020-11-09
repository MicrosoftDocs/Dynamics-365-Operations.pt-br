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
ms.openlocfilehash: 40703622bc8c7a21451d31e7606596c5edbe90f7
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000284"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="0c27b-103">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="0c27b-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0c27b-104">Este tópico explica como dividir uma porcentagem do registro de ativos em um novo registro de ativos.</span><span class="sxs-lookup"><span data-stu-id="0c27b-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="0c27b-105">Usa os dados de função de contador e de demonstração de USMF.</span><span class="sxs-lookup"><span data-stu-id="0c27b-105">It uses the Accountant role and USMF demo data.</span></span>

## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="0c27b-106">Criar um novo ativo fixo</span><span class="sxs-lookup"><span data-stu-id="0c27b-106">Create a new fixed asset</span></span>

1. <span data-ttu-id="0c27b-107">No painel de navegação, vá para **Módulos \> Ativos fixos \> Ativos fixos \> Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-107">In the navigation pane, go to **Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="0c27b-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-108">Select **New**.</span></span>
3. <span data-ttu-id="0c27b-109">No campo **Grupo de ativo fixo** , insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0c27b-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="0c27b-110">Anote o número do ativo fixo a ser usado posteriormente no processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="0c27b-110">Note the fixed asset number to use in the split process later.</span></span>
4. <span data-ttu-id="0c27b-111">No campo **Nome** , insira um valor.</span><span class="sxs-lookup"><span data-stu-id="0c27b-111">In the **Name** field, enter a value.</span></span>
5. <span data-ttu-id="0c27b-112">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="0c27b-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="0c27b-113">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="0c27b-113">Split a fixed asset</span></span>

<span data-ttu-id="0c27b-114">Antes que um ativo com depreciação total seja dividido, o status do registro de ativos deve ser alterado manualmente de **Fechado** para **Aberto**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-114">Before a fully depreciated asset is split, the asset book status should be manually changed from **Closed** to **Open**.</span></span> <span data-ttu-id="0c27b-115">Essa etapa é necessária porque o status do registro precisa estar **Aberto** se você precisar lançar transações para o ativo (por exemplo, para uma venda de alienação).</span><span class="sxs-lookup"><span data-stu-id="0c27b-115">This step is required because the book status has to be **Open** if you must post transactions for the asset (for example, for a disposal sale).</span></span> <span data-ttu-id="0c27b-116">Depois que o status do registro de ativos for alterado, siga estas etapas para dividir o ativo.</span><span class="sxs-lookup"><span data-stu-id="0c27b-116">After the asset book status is changed, follow these steps to split the asset.</span></span>

1. <span data-ttu-id="0c27b-117">Na lista, localize e selecione o link do ativo fixo que você deseja dividir.</span><span class="sxs-lookup"><span data-stu-id="0c27b-117">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="0c27b-118">Selecione **Registros**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-118">Select **Books**.</span></span> <span data-ttu-id="0c27b-119">Selecione o registro a ser dividido no novo ativo.</span><span class="sxs-lookup"><span data-stu-id="0c27b-119">Select the book to split to the new asset.</span></span>
3. <span data-ttu-id="0c27b-120">Selecione **Funções**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-120">Select **Functions**.</span></span>
4. <span data-ttu-id="0c27b-121">Selecione **Dividir ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-121">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="0c27b-122">No campo **Para o ativo fixo** , insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0c27b-122">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="0c27b-123">No campo **Para o registro** , selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0c27b-123">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="0c27b-124">No campo **Data de transação** , insira uma data.</span><span class="sxs-lookup"><span data-stu-id="0c27b-124">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="0c27b-125">No campo **Porcentagem** , insira um número.</span><span class="sxs-lookup"><span data-stu-id="0c27b-125">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="0c27b-126">No campo **Nome do diário** , insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0c27b-126">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="0c27b-127">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-127">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="0c27b-128">Lançar a transação de diário</span><span class="sxs-lookup"><span data-stu-id="0c27b-128">Post the journal transaction</span></span>

1. <span data-ttu-id="0c27b-129">No Painel de navegação, vá para **Módulos \> Ativos fixos \> Entradas de diário \> Diário de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-129">In the navigation pane, go to **Modules \> Fixed assets \> Journal entries \> Fixed assets journal**.</span></span>
2. <span data-ttu-id="0c27b-130">Na lista, selecione o diário criado com o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="0c27b-130">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="0c27b-131">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-131">Select **Lines**.</span></span>

    - <span data-ttu-id="0c27b-132">Verifique as linhas de diário criadas.</span><span class="sxs-lookup"><span data-stu-id="0c27b-132">Verify the journal lines created.</span></span>
    - <span data-ttu-id="0c27b-133">Uma transação de ajuste de aquisição é criada para o ativo original diminuir o valor por porcentagem especificada durante o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="0c27b-133">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>
    - <span data-ttu-id="0c27b-134">Uma transação de aquisição é criada para o novo ativo para a mesma quantidade.</span><span class="sxs-lookup"><span data-stu-id="0c27b-134">An Acquisition transaction is created for the new asset for the same amount.</span></span>

4. <span data-ttu-id="0c27b-135">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="0c27b-135">Select **Post**.</span></span>
