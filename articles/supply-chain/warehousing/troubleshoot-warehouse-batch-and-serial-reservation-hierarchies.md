---
title: Solucionar problemas de hierarquias de reserva de números de série e do lote do depósito
description: Este tópico descreve como corrigir problemas comuns que você poderá encontrar ao trabalhar com hierarquias de reserva que usam dimensões de números do lote ou de série.
author: perlynne
ms.date: 3/12/2021
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
ms.search.validFrom: 3/12/2021
ms.openlocfilehash: a1abb6f8657484d43d434076e5ee38d1c63fe2ff
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838169"
---
# <a name="troubleshoot-warehouse-batch-and-serial-reservation-hierarchies"></a><span data-ttu-id="27520-103">Solucionar problemas de hierarquias de reserva de números de série e do lote do depósito</span><span class="sxs-lookup"><span data-stu-id="27520-103">Troubleshoot warehouse batch and serial reservation hierarchies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="27520-104">Este tópico descreve como corrigir problemas comuns que você poderá encontrar ao trabalhar com hierarquias de reserva que usam dimensões de números do lote ou de série.</span><span class="sxs-lookup"><span data-stu-id="27520-104">This topic describes how to fix common issues that you might encounter while you work with reservation hierarchies that use batch or serial dimensions.</span></span>

<span data-ttu-id="27520-105">Para obter mais informações, consulte [Política de reserva de dimensão no nível de depósito flexível](flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="27520-105">For more information, see [Flexible warehouse-level dimension reservation policy](flexible-warehouse-level-dimension-reservation.md).</span></span>

<span data-ttu-id="27520-106">A hierarquia de reservas de um item dita a necessidade de dimensões de loja que devem ser atendidas para a atribuição de um local a uma ordem de demanda.</span><span class="sxs-lookup"><span data-stu-id="27520-106">The reservation hierarchy of an item dictates the requirement of storage dimensions that must be fulfilled to assign a location to a demand order.</span></span> <span data-ttu-id="27520-107">Essas dimensões podem ser descritas como *dimensões acima do local*, para todas as dimensões que devem ser preenchidas antes que um local seja atribuído, e *dimensões abaixo do local*, para dimensões que podem ser alocadas depois que um local for atribuído à ordem de demanda.</span><span class="sxs-lookup"><span data-stu-id="27520-107">These dimensions can be described as *dimensions above location*, for all the dimensions that must be fulfilled before a location is assigned, and *dimensions below location*, for dimensions that can be allocated after a location has been assigned to the demand order.</span></span> <span data-ttu-id="27520-108">Essas hierarquias de reserva também são conhecidas como hierarquias de reserva *acima do número do lote* e *abaixo do número do lote*, ou hierarquias de reserva *acima do número de série* ou *abaixo do número de série*.</span><span class="sxs-lookup"><span data-stu-id="27520-108">These reservation hierarchies are also known as *batch-above* and *batch-below* reservation hierarchies, or *serial-above* and *serial-below* reservation hierarchies.</span></span>

<span data-ttu-id="27520-109">O estoque só poderá ser alocado com êxito se não houver intervalos nas dimensões acima do local.</span><span class="sxs-lookup"><span data-stu-id="27520-109">Inventory can be successfully allocated only if there are no gaps in the dimensions above location.</span></span> <span data-ttu-id="27520-110">Por exemplo, em uma hierarquia de reservas *acima do número do lote*, você espera que as dimensões **Local**, **Depósito** e **número do lote** sejam especificadas na ordem de demanda.</span><span class="sxs-lookup"><span data-stu-id="27520-110">For example, in a *batch-above* reservation hierarchy, you expect **Site,** **Warehouse,** and **Batch number** dimensions to be specified on the demand order.</span></span> <span data-ttu-id="27520-111">Se alguma dessas dimensões estiver ausente, o processo de alocação falhará.</span><span class="sxs-lookup"><span data-stu-id="27520-111">If any of these dimensions are missing, the allocation process will fail.</span></span> <span data-ttu-id="27520-112">Por outro lado, em uma hierarquia de reservas *abaixo do número do lote* ou *abaixo do número de série*, um número do lote ou de série poderá ser especificado na ordem de demanda, mas o processo de alocação exige isso.</span><span class="sxs-lookup"><span data-stu-id="27520-112">By contrast, in a *batch-below* or *serial-below* reservation hierarchy, a batch or serial number might be specified on the demand order, but the allocation process doesn't require it.</span></span>

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a><span data-ttu-id="27520-113">Recebo a seguinte mensagem de erro: "Para ser atribuído ao ciclo, as linhas de carga devem especificar as dimensões acima do local.</span><span class="sxs-lookup"><span data-stu-id="27520-113">I receive the following error message: "To be assigned to wave, load lines must specify the dimensions above the location.</span></span> <span data-ttu-id="27520-114">Para atribuir essas dimensões, reserve e recrie a linha de carga."</span><span class="sxs-lookup"><span data-stu-id="27520-114">To assign these dimensions, reserve and recreate the load line."</span></span>

### <a name="issue-description"></a><span data-ttu-id="27520-115">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="27520-115">Issue description</span></span>

<span data-ttu-id="27520-116">Quando você usa um item com uma hierarquia de reservas *acima do número do lote*, o comando **Liberar para o depósito** na página **Bancada do planejamento de carga** não funcionará se você tentar liberar uma carga para uma quantidade parcial.</span><span class="sxs-lookup"><span data-stu-id="27520-116">When you use an item that has a *batch-above* reservation hierarchy, the **Release to warehouse** command on the **Load planning workbench** page doesn't work if you try to release a load for a partial quantity.</span></span> <span data-ttu-id="27520-117">Você recebe essa mensagem de erro e nenhum trabalho é criado para a quantidade parcial.</span><span class="sxs-lookup"><span data-stu-id="27520-117">You receive this error message, and no work is created for the partial quantity.</span></span>

<span data-ttu-id="27520-118">Contudo, quando usar um item com uma hierarquia de reservas *acima do número do lote*, você poderá liberar uma carga para a quantidade parcial da página **Bancada do planejamento de carga**.</span><span class="sxs-lookup"><span data-stu-id="27520-118">However, when you use an item that has a *batch-below* reservation hierarchy, you can release a load for a partial quantity from the **Load planning workbench** page.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="27520-119">Causa do problema</span><span class="sxs-lookup"><span data-stu-id="27520-119">Issue cause</span></span>

<span data-ttu-id="27520-120">Quando uma dimensão estiver acima da dimensão **Local** na hierarquia de reservas, ela deverá ser especificada antes da liberação para o depósito.</span><span class="sxs-lookup"><span data-stu-id="27520-120">When a dimension is above the **Location** dimension in the reservation hierarchy, it must be specified before the release to the warehouse.</span></span> <span data-ttu-id="27520-121">Quantidades parciais não podem ser liberadas se uma ou mais dimensões acima de **Local** não forem especificadas.</span><span class="sxs-lookup"><span data-stu-id="27520-121">Partial quantities can't be released if one or more dimensions above **Location** aren't specified.</span></span>

## <a name="the-auto-reservation-prompt-for-a-batch-number-is-triggered-even-though-there-is-available-inventory"></a><span data-ttu-id="27520-122">O aviso de reserva automática para um número do lote será disparado mesmo que haja um estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="27520-122">The auto-reservation prompt for a batch number is triggered even though there is available inventory.</span></span>

### <a name="issue-description"></a><span data-ttu-id="27520-123">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="27520-123">Issue description</span></span>

<span data-ttu-id="27520-124">Quando você usa um item com uma hierarquia de reservas *acima do número do lote* em um depósito que não tenha habilitado processos de depósito, e se a reserva automática estiver habilitada, o aviso de reserva automática para um número do lote será mostrado mesmo se apenas um lote estiver disponível para separação.</span><span class="sxs-lookup"><span data-stu-id="27520-124">When you use an item that has a *batch-above* reservation hierarchy in a warehouse that hasn't enabled warehouse processes, and automatic reservation is enabled, the auto-reservation prompt for a batch number is shown even if only one batch is available for picking.</span></span>

<span data-ttu-id="27520-125">No entanto, quando você usar o mesmo item em um depósito onde os processos de depósito estiverem habilitados, o prompt de reserva automática não será exibido.</span><span class="sxs-lookup"><span data-stu-id="27520-125">However, when you use the same item in a warehouse where warehouse processes are enabled, the auto-reservation prompt isn't shown.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="27520-126">Causa do problema</span><span class="sxs-lookup"><span data-stu-id="27520-126">Issue cause</span></span>

<span data-ttu-id="27520-127">Se uma hierarquia de reserva for definida como um *acima do número do lote* ou *acima do número de série*, a dimensão referenciada (**número do lote** ou **Número de série**) sempre deverá ser especificada em ordens de demanda.</span><span class="sxs-lookup"><span data-stu-id="27520-127">If a reservation hierarchy is defined as *batch-above* or *serial-above*, the referenced dimension (**Batch number** or **Serial number**) must always be specified on demand orders.</span></span> <span data-ttu-id="27520-128">Talvez os processos de depósito consigam completar as informações se um único número do lote ou de série estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="27520-128">Warehouse processes might be able to complete the information if a single batch or serial number is available.</span></span> <span data-ttu-id="27520-129">No entanto, como o depósito não está habilitado para processos de depósito, o usuário sempre deverá especificar todas as dimensões acima do **Local**.</span><span class="sxs-lookup"><span data-stu-id="27520-129">However, because the warehouse isn't enabled for warehouse processes, the user must always specify all the dimensions above **Location**.</span></span>

## <a name="slotting-templates-that-have-the-consider-on-hand-slot-criterion-dont-consider-current-on-hand-inventory-for-batch-enabled-items"></a><span data-ttu-id="27520-130">Os modelos de slots com o critério de slot Considerar disponível não consideram o estoque disponível atual para itens habilitados para lotes.</span><span class="sxs-lookup"><span data-stu-id="27520-130">Slotting templates that have the Consider on-hand slot criterion don't consider current on-hand inventory for batch-enabled items.</span></span>

<span data-ttu-id="27520-131">Para obter mais informações, consulte [Slots de depósito](warehouse-slotting.md).</span><span class="sxs-lookup"><span data-stu-id="27520-131">For more information, see [Warehouse slotting](warehouse-slotting.md).</span></span>

### <a name="issue-description"></a><span data-ttu-id="27520-132">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="27520-132">Issue description</span></span>

<span data-ttu-id="27520-133">Os modelos de slots com o critério de slot *Considerar disponível* não consideram o estoque disponível atual para itens *acima do número do lote*.</span><span class="sxs-lookup"><span data-stu-id="27520-133">Slotting templates that have the *Consider on-hand* slot criterion don't consider current on-hand inventory for *batch-above* items.</span></span> <span data-ttu-id="27520-134">Eles só o considerarão se o número do lote for especificado na linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="27520-134">They consider it only if the batch number is specified on the sales order line.</span></span>

<span data-ttu-id="27520-135">No entanto, quando você usa itens *abaixo do número do lote*, o estoque disponível atual é considerado esperado.</span><span class="sxs-lookup"><span data-stu-id="27520-135">However, when you use *batch-below* items, the current on-hand inventory is considered as expected.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="27520-136">Causa do problema</span><span class="sxs-lookup"><span data-stu-id="27520-136">Issue cause</span></span>

<span data-ttu-id="27520-137">O cabeçalho do modelo de slot pode ser definido para a estratégia de demanda *Encomendado*, *Reservado* ou *Liberado*.</span><span class="sxs-lookup"><span data-stu-id="27520-137">The slotting template header can be defined for the *Ordered,* *Reserved*, or *Released* demand strategy.</span></span> <span data-ttu-id="27520-138">Para a estratégia de demanda *Encomendado*, os mesmos requisitos de hierarquia de reservas se aplicam para reserva ou liberação para processos de depósito.</span><span class="sxs-lookup"><span data-stu-id="27520-138">For the *Ordered* demand strategy, the same reservation hierarchy requirements apply that apply to reservation or release to warehouse processes.</span></span> <span data-ttu-id="27520-139">Portanto, para os itens com hierarquias de reservas *acima do número do lote* e *abaixo do número de série*, o número do lote ou de série deverá ser especificado na ordem de demanda (venda ou transferência).</span><span class="sxs-lookup"><span data-stu-id="27520-139">Therefore, for items that have *batch-above* and *serial-below* reservation hierarchies, the batch or serial number must be specified on the demand order (sales or transfer).</span></span> <span data-ttu-id="27520-140">Como alternativa, a estratégia de demanda *Reservado* poderá ser usada para selecionar o número do lote ou de série antes que a demanda de slots de depósito seja gerada.</span><span class="sxs-lookup"><span data-stu-id="27520-140">Alternatively, the *Reserved* demand strategy can be used to select the batch or serial number before the warehouse slotting demand is generated.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]