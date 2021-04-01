---
title: Solucionar problemas de reservas no gerenciamento de depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reservas de depósito no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a9a5d20732a802fc58c392853af8334bbc07de73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248706"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="43fc9-103">Solucionar problemas de reservas no gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="43fc9-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43fc9-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reservas de depósito no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="43fc9-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="43fc9-105">Recebo a seguinte mensagem de erro: "As reservas não podem ser removidas porque há um trabalho criado com base nas reservas."</span><span class="sxs-lookup"><span data-stu-id="43fc9-105">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="43fc9-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="43fc9-106">Issue description</span></span>

<span data-ttu-id="43fc9-107">Não é possível cancelar a reserva de estoque em uma linha de vendas, porque há trabalho aberto em relação à linha.</span><span class="sxs-lookup"><span data-stu-id="43fc9-107">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="43fc9-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="43fc9-108">Issue resolution</span></span>

<span data-ttu-id="43fc9-109">Investigue se existe trabalho de grupo de embalagem aberto para mudar o item de uma estação de embalagem para outro local (como *Baydoor*).</span><span class="sxs-lookup"><span data-stu-id="43fc9-109">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="43fc9-110">Revise os registros nas páginas **Log de histórico de criação de trabalho** e **Detalhes do trabalho** para determinar o que está reservando fisicamente o estoque e, depois, conclua ou exclua o trabalho para liberar a reserva.</span><span class="sxs-lookup"><span data-stu-id="43fc9-110">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="43fc9-111">Recebo a seguinte mensagem de erro: "A quantidade em estoque -%1 não pôde ser atualizada em razão de transações de estoque insuficientes para o item %2...."</span><span class="sxs-lookup"><span data-stu-id="43fc9-111">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="43fc9-112">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="43fc9-112">Issue description</span></span>

<span data-ttu-id="43fc9-113">Esse problema pode ocorrer se o sistema não puder atualizar uma quantidade de estoque porque não há transações de estoque suficientes com as dimensões especificadas.</span><span class="sxs-lookup"><span data-stu-id="43fc9-113">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="43fc9-114">Aqui está o texto completo da mensagem de erro completa:</span><span class="sxs-lookup"><span data-stu-id="43fc9-114">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="43fc9-115">A quantidade de estoque -%1 não pôde ser atualizada em razão de transações de estoque insuficientes para o item %2 com dimensões de Tamanho = %3, Cor = %4, Adições = %5, Local = %6, Depósito = %7, Local = %8, Status do estoque = Disponível, Placa de licença = %9, Número do lote = %10 para a ID de referência %11 na ID de lote %12.</span><span class="sxs-lookup"><span data-stu-id="43fc9-115">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="43fc9-116">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="43fc9-116">Issue resolution</span></span>

<span data-ttu-id="43fc9-117">Certifique-se de que nenhuma transação de estoque esteja reservando fisicamente a quantidade.</span><span class="sxs-lookup"><span data-stu-id="43fc9-117">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="43fc9-118">Por exemplo, essas transações podem abrir ordens de qualidade, registros de bloqueio de estoque ou ordens de saída.</span><span class="sxs-lookup"><span data-stu-id="43fc9-118">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="43fc9-119">Recebo a seguinte mensagem de erro: "Físico disponível... não pode ser reservado porque apenas 0,00 estão disponíveis no estoque."</span><span class="sxs-lookup"><span data-stu-id="43fc9-119">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="43fc9-120">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="43fc9-120">Issue description</span></span>

<span data-ttu-id="43fc9-121">Esse problema pode ocorrer se o sistema não puder atualizar uma quantidade de estoque porque não há transações de estoque suficientes com as dimensões especificadas.</span><span class="sxs-lookup"><span data-stu-id="43fc9-121">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="43fc9-122">Aqui está o texto completo da mensagem de erro completa:</span><span class="sxs-lookup"><span data-stu-id="43fc9-122">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="43fc9-123">Físico disponível Local = %1, Depósito = %2, Status do estoque = Disponível, Nº do lote = %3, Proprietário = %4: %5 não pode ser reservado porque somente 0,00 está disponível no estoque.</span><span class="sxs-lookup"><span data-stu-id="43fc9-123">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="43fc9-124">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="43fc9-124">Issue resolution</span></span>

<span data-ttu-id="43fc9-125">Esse problema é provavelmente causado por um trabalho aberto.</span><span class="sxs-lookup"><span data-stu-id="43fc9-125">This issue is probably caused by open work.</span></span> <span data-ttu-id="43fc9-126">Conclua a obra ou receba sem criação de trabalho.</span><span class="sxs-lookup"><span data-stu-id="43fc9-126">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="43fc9-127">Certifique-se de que nenhuma transação de estoque esteja reservando fisicamente a quantidade.</span><span class="sxs-lookup"><span data-stu-id="43fc9-127">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="43fc9-128">Por exemplo, essas transações podem abrir ordens de qualidade, registros de bloqueio de estoque ou ordens de saída.</span><span class="sxs-lookup"><span data-stu-id="43fc9-128">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a><span data-ttu-id="43fc9-129">Recebo a seguinte mensagem de erro: "Para ser atribuído ao ciclo, as linhas de carga devem especificar as dimensões acima do local.</span><span class="sxs-lookup"><span data-stu-id="43fc9-129">I receive the following error message: "To be assigned to wave, load lines must specify the dimensions above the location.</span></span> <span data-ttu-id="43fc9-130">Para atribuir essas dimensões, reserve e recrie a linha de carga."</span><span class="sxs-lookup"><span data-stu-id="43fc9-130">To assign these dimensions, reserve and recreate the load line."</span></span>

### <a name="issue-description"></a><span data-ttu-id="43fc9-131">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="43fc9-131">Issue description</span></span>

<span data-ttu-id="43fc9-132">Quando você usa um item que tem uma hierarquia de reserva de "lote acima" (com a dimensão **Nº do lote** posicionada *acima* da dimensão **Local**), o comando **Liberar para o depósito** na página **Bancada do planejamento de carga** para uma quantidade parcial não funciona.</span><span class="sxs-lookup"><span data-stu-id="43fc9-132">When you use an item that has a "batch above" reservation hierarchy (with the **Batch number** dimension placed *above* the **Location** dimension), the **Release to warehouse** command on the **Load planning workbench** page for a partial quantity doesn't work.</span></span> <span data-ttu-id="43fc9-133">Você recebe essa mensagem de erro e nenhum trabalho é criado para a quantidade parcial.</span><span class="sxs-lookup"><span data-stu-id="43fc9-133">You receive this error message, and no work is created for the partial quantity.</span></span>

<span data-ttu-id="43fc9-134">Contudo, se você usar um item que tem uma hierarquia de reserva de "lote abaixo" (com a dimensão **Nº do lote** posicionada *abaixo* da dimensão **Local**), você pode liberar uma carga da página **Bancada do planejamento de carga** para uma quantidade parcial.</span><span class="sxs-lookup"><span data-stu-id="43fc9-134">However, if you use an item that has a "batch below" reservation hierarchy (with the **Batch number** dimension placed *below* the **Location** dimension), you can release a load from the **Load planning workbench** page for a partial quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="43fc9-135">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="43fc9-135">Issue resolution</span></span>

<span data-ttu-id="43fc9-136">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="43fc9-136">This behavior is by design.</span></span> <span data-ttu-id="43fc9-137">Se você colocar uma dimensão acima da dimensão **Local** na hierarquia de reserva, ela deve ser especificada antes da liberação para o depósito.</span><span class="sxs-lookup"><span data-stu-id="43fc9-137">If you put a dimension above the **Location** dimension in the reservation hierarchy, it must be specified before the release to the warehouse.</span></span> <span data-ttu-id="43fc9-138">A Microsoft avaliou esse problema e determinou que é uma limitação do recurso durante as liberações para o depósito da bancada de planejamento de carga.</span><span class="sxs-lookup"><span data-stu-id="43fc9-138">Microsoft has evaluated this issue and has determined that it's a feature limitation during releases to the warehouse from the load planning workbench.</span></span> <span data-ttu-id="43fc9-139">Quantidades parciais não podem ser liberadas se uma ou mais dimensões acima de **Local** não forem especificadas.</span><span class="sxs-lookup"><span data-stu-id="43fc9-139">Partial quantities can't be released if one or more dimensions above **Location** aren't specified.</span></span>

<span data-ttu-id="43fc9-140">Para obter mais informações, consulte [Política de reserva de dimensão no nível de depósito flexível](flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="43fc9-140">For more information, see [Flexible warehouse-level dimension reservation policy](flexible-warehouse-level-dimension-reservation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]