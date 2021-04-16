---
title: Dividir um ativo fixo
description: Este tópico explica como dividir uma porcentagem do registro de ativos em um novo registro de ativos.
author: saraschi2
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa21d5698275ff691ca83d29abd297a796b652d1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823899"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="069b6-103">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="069b6-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="069b6-104">Este tópico explica como dividir uma porcentagem do registro de ativos em um novo registro de ativos.</span><span class="sxs-lookup"><span data-stu-id="069b6-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="069b6-105">Usa os dados de função de contador e de demonstração de USMF.</span><span class="sxs-lookup"><span data-stu-id="069b6-105">It uses the Accountant role and USMF demo data.</span></span>

## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="069b6-106">Criar um novo ativo fixo</span><span class="sxs-lookup"><span data-stu-id="069b6-106">Create a new fixed asset</span></span>

1. <span data-ttu-id="069b6-107">No painel de navegação, vá para **Módulos \> Ativos fixos \> Ativos fixos \> Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="069b6-107">In the navigation pane, go to **Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="069b6-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="069b6-108">Select **New**.</span></span>
3. <span data-ttu-id="069b6-109">No campo **Grupo de ativo fixo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="069b6-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="069b6-110">Anote o número do ativo fixo a ser usado posteriormente no processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="069b6-110">Note the fixed asset number to use in the split process later.</span></span>
4. <span data-ttu-id="069b6-111">No campo **Nome**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="069b6-111">In the **Name** field, enter a value.</span></span>
5. <span data-ttu-id="069b6-112">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="069b6-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="069b6-113">Dividir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="069b6-113">Split a fixed asset</span></span>

<span data-ttu-id="069b6-114">Antes que um ativo com depreciação total seja dividido, o status do registro de ativos deve ser alterado manualmente de **Fechado** para **Aberto**.</span><span class="sxs-lookup"><span data-stu-id="069b6-114">Before a fully depreciated asset is split, the asset book status should be manually changed from **Closed** to **Open**.</span></span> <span data-ttu-id="069b6-115">Essa etapa é necessária porque o status do registro precisa estar **Aberto** se você precisar lançar transações para o ativo (por exemplo, para uma venda de alienação).</span><span class="sxs-lookup"><span data-stu-id="069b6-115">This step is required because the book status has to be **Open** if you must post transactions for the asset (for example, for a disposal sale).</span></span> <span data-ttu-id="069b6-116">Você também deve ativar o parâmetro **Permitir várias transações em um comprovante** na guia **Geral** da página **Parâmetros da contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="069b6-116">You must also turn on the **Allow multiple transactions within one voucher** parameter on the **General** tab of the **General ledger parameters** page.</span></span> <span data-ttu-id="069b6-117">Depois que o status do registro de ativos for alterado e várias transações em um comprovante forem permitidas, conclua as etapas a seguir para dividir o ativo.</span><span class="sxs-lookup"><span data-stu-id="069b6-117">After the asset book status is changed and multiple transactions within one voucher have been allowed, complete the following steps to split the asset.</span></span>

1. <span data-ttu-id="069b6-118">Na lista, localize e selecione o link do ativo fixo que você deseja dividir.</span><span class="sxs-lookup"><span data-stu-id="069b6-118">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="069b6-119">Selecione **Registros**.</span><span class="sxs-lookup"><span data-stu-id="069b6-119">Select **Books**.</span></span> <span data-ttu-id="069b6-120">Selecione o registro a ser dividido no novo ativo.</span><span class="sxs-lookup"><span data-stu-id="069b6-120">Select the book to split to the new asset.</span></span>
3. <span data-ttu-id="069b6-121">Selecione **Funções**.</span><span class="sxs-lookup"><span data-stu-id="069b6-121">Select **Functions**.</span></span>
4. <span data-ttu-id="069b6-122">Selecione **Dividir ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="069b6-122">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="069b6-123">No campo **Para o ativo fixo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="069b6-123">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="069b6-124">No campo **Para o registro**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="069b6-124">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="069b6-125">No campo **Data de transação**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="069b6-125">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="069b6-126">No campo **Porcentagem**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="069b6-126">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="069b6-127">No campo **Nome do diário**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="069b6-127">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="069b6-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="069b6-128">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="069b6-129">Lançar a transação de diário</span><span class="sxs-lookup"><span data-stu-id="069b6-129">Post the journal transaction</span></span>

1. <span data-ttu-id="069b6-130">No Painel de navegação, vá para **Módulos \> Ativos fixos \> Entradas de diário \> Diário de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="069b6-130">In the navigation pane, go to **Modules \> Fixed assets \> Journal entries \> Fixed assets journal**.</span></span>
2. <span data-ttu-id="069b6-131">Na lista, selecione o diário criado com o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="069b6-131">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="069b6-132">Selecione **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="069b6-132">Select **Lines**.</span></span>

    - <span data-ttu-id="069b6-133">Verifique as linhas de diário criadas.</span><span class="sxs-lookup"><span data-stu-id="069b6-133">Verify the journal lines created.</span></span>
    - <span data-ttu-id="069b6-134">Uma transação de ajuste de aquisição é criada para o ativo original diminuir o valor por porcentagem especificada durante o processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="069b6-134">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>
    - <span data-ttu-id="069b6-135">Uma transação de aquisição é criada para o novo ativo para a mesma quantidade.</span><span class="sxs-lookup"><span data-stu-id="069b6-135">An Acquisition transaction is created for the new asset for the same amount.</span></span>

4. <span data-ttu-id="069b6-136">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="069b6-136">Select **Post**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]