---
title: Ajuste de estoque do depósito
description: Este tópico fornece informações sobre o diário de ajuste de estoque de depósito e o processamento quando você está usando unidades de escala.
author: perlynne
manager: tfehr
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: be386539ea7addf20256ac2b1f8a2a72736fcbec
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938217"
---
# <a name="warehouse-inventory-adjustment"></a><span data-ttu-id="10093-103">Ajuste de estoque do depósito</span><span class="sxs-lookup"><span data-stu-id="10093-103">Warehouse inventory adjustment</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="10093-104">O recurso de ajuste de estoque de depósito é usado na execução de unidades de escala de nuvem e de borda para [cargas de trabalho de fabricação](cloud-edge-workload-manufacturing.md) e de gerenciamento de [depósito](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="10093-104">The Warehouse inventory adjustment feature is used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="10093-105">Quando um trabalhador faz um ajuste de estoque usando o aplicativo de depósito em uma carga de trabalho de gerenciamento de depósito da unidade de escala, a atualização física disponível deve ser processada pelo trabalho em lotes do **diário de ajuste de estoque de depósito**, que você executa e agenda acessando o **Gerenciamento de depósito > Tarefas periódicas > Diário de ajuste de estoque de depósito**.</span><span class="sxs-lookup"><span data-stu-id="10093-105">When a worker does an inventory adjustment using the warehouse app against a scale unit warehouse management workload, the physical on-hand update must be processed by the **Warehouse inventory adjustment journal** batch job, which you run and schedule by going to **Warehouse management > Periodic tasks > Warehouse inventory adjustment journal**.</span></span>

<span data-ttu-id="10093-106">Os seguintes processos de trabalho do aplicativo de depósito no momento estão usando o **Diário de ajuste de estoque de depósito** nas cargas da unidade de escala:</span><span class="sxs-lookup"><span data-stu-id="10093-106">The following warehouse app work processes currently use the **Warehouse inventory adjustment journal** on scale unit workloads:</span></span>

- <span data-ttu-id="10093-107">Ajuste de entrada/saída</span><span class="sxs-lookup"><span data-stu-id="10093-107">Adjustment in/out</span></span>
- <span data-ttu-id="10093-108">Contagem cíclica</span><span class="sxs-lookup"><span data-stu-id="10093-108">Cycle counting</span></span>
- <span data-ttu-id="10093-109">Carregamento da placa de licença:</span><span class="sxs-lookup"><span data-stu-id="10093-109">License plate loading</span></span>

<span data-ttu-id="10093-110">Várias transações de estoque são criadas como parte da nuvem e borda no processo de ajuste de estoque porque as implantações de unidade de escala e de hub compartilham os registros de estoque.</span><span class="sxs-lookup"><span data-stu-id="10093-110">Several inventory transactions are created as part of cloud and edge an inventory adjustment process because the hub and scale unit deployments share the inventory records.</span></span>

## <a name="inventory-adjustment-example"></a><span data-ttu-id="10093-111">Exemplo de ajuste do estoque</span><span class="sxs-lookup"><span data-stu-id="10093-111">Inventory adjustment example</span></span>

<span data-ttu-id="10093-112">Neste exemplo, um trabalhador de depósito usou o aplicativo de depósito para registrar a inclusão de estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="10093-112">In this example, a warehouse worker has used the warehouse app to register the adding of on-hand inventory.</span></span>

<span data-ttu-id="10093-113">Primeiro, a carga de trabalho da unidade de escala cria uma transação de ajuste de estoque de depósito para o ajuste físico positivo, que, em seguida, é sincronizado com o hub e resulta em um aumento do estoque disponível no hub.</span><span class="sxs-lookup"><span data-stu-id="10093-113">First, the scale unit workload creates a warehouse inventory adjustment transaction for the positive physical adjustment, which is then synchronized to the hub and results in an increase of the on-hand inventory on the hub.</span></span>

| <span data-ttu-id="10093-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="10093-114">Type</span></span>                                    | <span data-ttu-id="10093-115">Unidade de escala</span><span class="sxs-lookup"><span data-stu-id="10093-115">Scale unit</span></span> | <span data-ttu-id="10093-116">Direção</span><span class="sxs-lookup"><span data-stu-id="10093-116">Direction</span></span> | <span data-ttu-id="10093-117">Hub</span><span class="sxs-lookup"><span data-stu-id="10093-117">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="10093-118">Ajuste de estoque do depósito</span><span class="sxs-lookup"><span data-stu-id="10093-118">Warehouse inventory adjustment</span></span>          | <span data-ttu-id="10093-119">+1</span><span class="sxs-lookup"><span data-stu-id="10093-119">+1</span></span>         | ->        | <span data-ttu-id="10093-120">+1</span><span class="sxs-lookup"><span data-stu-id="10093-120">+1</span></span>  |

<span data-ttu-id="10093-121">O hub processa um lançamento de diário de contagem, que é recebido por [mensagens de processador de mensagens](cloud-edge-message-processor-messages.md).</span><span class="sxs-lookup"><span data-stu-id="10093-121">The hub then processes a counting journal posting, which is received through [message processor messages](cloud-edge-message-processor-messages.md).</span></span> <span data-ttu-id="10093-122">Isso atualiza o estoque disponível adicional.</span><span class="sxs-lookup"><span data-stu-id="10093-122">This updates the additional inventory on hand.</span></span> <span data-ttu-id="10093-123">Para evitar um estoque duplo disponível, o hub cria uma transação de compensação como parte desse processo e remove o estoque disponível gravado anteriormente que está relacionado ao ajuste de estoque de depósito.</span><span class="sxs-lookup"><span data-stu-id="10093-123">To prevent double inventory on hand, the hub creates an offset transaction as part of this process and removes the previously recorded on-hand inventory that is related to the warehouse inventory adjustment.</span></span>

| <span data-ttu-id="10093-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="10093-124">Type</span></span>                                    | <span data-ttu-id="10093-125">Unidade de escala</span><span class="sxs-lookup"><span data-stu-id="10093-125">Scale unit</span></span> | <span data-ttu-id="10093-126">Direção</span><span class="sxs-lookup"><span data-stu-id="10093-126">Direction</span></span> | <span data-ttu-id="10093-127">Hub</span><span class="sxs-lookup"><span data-stu-id="10093-127">Hub</span></span> |
|-----------------------------------------|------------|-----------|-----|
| <span data-ttu-id="10093-128">Contagem</span><span class="sxs-lookup"><span data-stu-id="10093-128">Counting</span></span>                                | <span data-ttu-id="10093-129">+1</span><span class="sxs-lookup"><span data-stu-id="10093-129">+1</span></span>         | <-        | <span data-ttu-id="10093-130">+1</span><span class="sxs-lookup"><span data-stu-id="10093-130">+1</span></span>  |
| <span data-ttu-id="10093-131">Ajuste de estoque de depósito (compensação)</span><span class="sxs-lookup"><span data-stu-id="10093-131">Warehouse inventory adjustment (Offset)</span></span> | <span data-ttu-id="10093-132">-1</span><span class="sxs-lookup"><span data-stu-id="10093-132">-1</span></span>         | <-        | <span data-ttu-id="10093-133">-1</span><span class="sxs-lookup"><span data-stu-id="10093-133">-1</span></span>  |

<span data-ttu-id="10093-134">Depois que uma unidade de escala cria um **Diário de ajuste de estoque de depósito** no hub, você pode revisar o **Diário de contagem** e o **Diário de compensação**, que são criados pelo hub como parte do processo de ajuste.</span><span class="sxs-lookup"><span data-stu-id="10093-134">After a scale unit has created a **Warehouse inventory adjustment journal** on the hub, you can review both the **Counting journal** and the **Offset journal**, which are created by the hub as part of the adjustment process.</span></span>

<span data-ttu-id="10093-135">Você pode revisar cada uma dessas entradas de diário e transações no Supply Chain Management seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="10093-135">You can review each of these journal entries and transaction in Supply Chain Management by doing the following steps:</span></span>

1. <span data-ttu-id="10093-136">Entre na unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="10093-136">Sign in on the scale unit.</span></span>
1. <span data-ttu-id="10093-137">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Diário de ajuste de estoque de depósito**.</span><span class="sxs-lookup"><span data-stu-id="10093-137">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="10093-138">Na página **Diário de ajuste de estoque de depósito**, localize e abra o diário que gravou a alteração de estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="10093-138">On the **Warehouse inventory adjustment journal** page, find and open the journal that recorded the on-hand inventory change.</span></span> <span data-ttu-id="10093-139">A seção **Linhas do diário** mostra cada ajuste registrado pelo diário.</span><span class="sxs-lookup"><span data-stu-id="10093-139">The **Journal lines** section shows each adjustment recorded by this journal.</span></span>
1. <span data-ttu-id="10093-140">Entre no Hub.</span><span class="sxs-lookup"><span data-stu-id="10093-140">Sign in on the hub.</span></span>
1. <span data-ttu-id="10093-141">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Diário de ajuste de estoque de depósito**.</span><span class="sxs-lookup"><span data-stu-id="10093-141">Go to **Warehouse management \> Periodic tasks \> Warehouse inventory adjustment journal**.</span></span>
1. <span data-ttu-id="10093-142">Na página **Diário de ajustes de estoque de depósito**, você deve ver o mesmo diário listado, se a unidade de escala e o hub foram sincronizados.</span><span class="sxs-lookup"><span data-stu-id="10093-142">On the **Warehouse inventory adjustment journal** page, you should see the same journal listed if the hub and scale unit have synced.</span></span>
1. <span data-ttu-id="10093-143">Abrir o diário.</span><span class="sxs-lookup"><span data-stu-id="10093-143">Open the journal.</span></span> <span data-ttu-id="10093-144">Se as [mensagens do processador de mensagens](cloud-edge-message-processor-messages.md) tiverem sido processadas, você verá links para o **Diário de contagem** e o **Diário de compensação** no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="10093-144">If the [message processor messages](cloud-edge-message-processor-messages.md) have been processed, you will see links to the **Counting journal** and the **Offset journal** in the header.</span></span>
    - <span data-ttu-id="10093-145">O **Diário de contagem** deve mostrar os mesmos valores de dimensão que as linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="10093-145">The **Counting journal** should show the same dimension values as the journal lines.</span></span>
    - <span data-ttu-id="10093-146">O **Diário de compensação** deve mostrar a compensação, que remove o ajuste de estoque duplo.</span><span class="sxs-lookup"><span data-stu-id="10093-146">The **Offset journal** should show the offset, which removes the double inventory adjustment.</span></span>
    > [!NOTE]
    > <span data-ttu-id="10093-147">Quando toda sincronização e processamento são concluídos, o **Diário de contagem** e o **Diário de compensação** são sincronizados novamente para a unidade de escala.</span><span class="sxs-lookup"><span data-stu-id="10093-147">When all syncing and processing is complete, the **Counting journal** and the **Offset journal** are synced back to the scale unit.</span></span> <span data-ttu-id="10093-148">Eles também podem ser exibidos na página **Diário de ajuste de estoque de depósito** relevante.</span><span class="sxs-lookup"><span data-stu-id="10093-148">These can also be viewed from the relevant **Warehouse inventory adjustment journal** page.</span></span>
