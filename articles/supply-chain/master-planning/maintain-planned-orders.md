---
title: Manter ordens planejadas
description: Este tópico fornece informações sobre como gerenciar ordens planejadas. Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada.
author: roxanadiaconu
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec67caf596b0efc256c957eca17a04509fe86855
ms.sourcegitcommit: 274ff2bb6872ff714781b348b29fd9f1affff9d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2904027"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="b0a18-104">Manter ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="b0a18-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b0a18-105">Este tópico fornece informações sobre como gerenciar ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="b0a18-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="b0a18-106">Descreve como é possível atualizar o status de ordens planejadas, confirmá-las e filtrar ordens planejadas com o mesmo status como uma ordem planejada selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0a18-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="b0a18-107">Você pode gerenciar ordens planejados no espaço de trabalho **Planejamento mestre**, na lista **Ordem planejada** ou nas listas **Ordens de produção planejadas**, **Ordens de compra planejadas** e **Transferência planejada**.</span><span class="sxs-lookup"><span data-stu-id="b0a18-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="b0a18-108">Status da ordem planejada</span><span class="sxs-lookup"><span data-stu-id="b0a18-108">Planned order status</span></span>
<span data-ttu-id="b0a18-109">Você pode usar o campo **Status** para ajudar a acompanhar seu progresso.</span><span class="sxs-lookup"><span data-stu-id="b0a18-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="b0a18-110">Os seguintes valores são usados:</span><span class="sxs-lookup"><span data-stu-id="b0a18-110">The following values are used:</span></span>

-   <span data-ttu-id="b0a18-111">Quando o planejamento mestre gerar ordens planejadas, elas terão o status **Não processado**.</span><span class="sxs-lookup"><span data-stu-id="b0a18-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="b0a18-112">Se você optar por não confirmar uma ordem planejada, poderá atribuir a ela o status **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b0a18-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="b0a18-113">Se você desejar confirmar uma ordem planejada, poderá alterar o status para **Aprovado**.</span><span class="sxs-lookup"><span data-stu-id="b0a18-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="b0a18-114">As ordens planejadas com o status **Aprovada** são respeitadas pelo planejamento mestre e, portanto, não são modificadas nem excluídas durante uma execução de um planejamento mestre posterior.</span><span class="sxs-lookup"><span data-stu-id="b0a18-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted during a later master planning run.</span></span> <span data-ttu-id="b0a18-115">Para fazer isso, a lógica de planejamento copia as ordens planejadas **Aprovadas** da versão anterior do plano para a nova versão do plano durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="b0a18-115">To achieve this, the planning logic copies the **Approved** planned orders from the old plan version to the new plan version during master planning.</span></span>

## <a name="firming-planned-orders"></a><span data-ttu-id="b0a18-116">Confirmar ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="b0a18-116">Firming planned orders</span></span> 
<span data-ttu-id="b0a18-117">Ao confirmar ordens planejadas, ordens reais são criadas.</span><span class="sxs-lookup"><span data-stu-id="b0a18-117">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="b0a18-118">Elas também são conhecidas como *ordens em aberto* ou *liberadas*.</span><span class="sxs-lookup"><span data-stu-id="b0a18-118">These are also known as *released* or *open orders*.</span></span> <span data-ttu-id="b0a18-119">Ao ser confirmada, uma ordem planejada é movida para a seção de ordens do módulo relevante.</span><span class="sxs-lookup"><span data-stu-id="b0a18-119">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="b0a18-120">Você pode selecionar duas opções de confirmação na página **Ordens planejadas**:</span><span class="sxs-lookup"><span data-stu-id="b0a18-120">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="b0a18-121">**Confirmar** – Isso confirmará uma ou várias ordens planejadas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="b0a18-121">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="b0a18-122">**Confirmar tudo** – Isso confirmará todas as ordens planejadas no filtro.</span><span class="sxs-lookup"><span data-stu-id="b0a18-122">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="b0a18-123">Ao usar **Confirmar tudo**, não é necessário selecionar a ordem planejada, todas as ordens planejadas no filtro serão confirmadas.</span><span class="sxs-lookup"><span data-stu-id="b0a18-123">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="b0a18-124">Essa opção pode ser útil se você estiver confirmando uma grande quantidade de ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="b0a18-124">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="b0a18-125">É possível rastrear uma ordem planejada que foi confirmada no **Histórico de confirmação**, acessando **Formulário Ordens planejadas > Exibir > Histórico de confirmação**.</span><span class="sxs-lookup"><span data-stu-id="b0a18-125">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="b0a18-126">Paralelizar confirmação</span><span class="sxs-lookup"><span data-stu-id="b0a18-126">Parallelize firming</span></span>
<span data-ttu-id="b0a18-127">Se você estiver planejando confirmar várias ordens ao mesmo tempo, a paralelização da execução pode melhorar o tempo de execução ou o desempenho.</span><span class="sxs-lookup"><span data-stu-id="b0a18-127">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="b0a18-128">Essa opção está disponível ao confirmar várias ordens planejadas com **Confirmar** ou **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="b0a18-128">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="b0a18-129">Estão disponíveis os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="b0a18-129">The following parameters are available:</span></span>

-   <span data-ttu-id="b0a18-130">**Paralelizar confirmação** – Se estiver definido como **Sim**, o processo de confirmação será paralelizado com o número de threads definido em **Número de threads**.</span><span class="sxs-lookup"><span data-stu-id="b0a18-130">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="b0a18-131">**Número de threads** – Controla o número de threads usado para paralelizar o processo de confirmação.</span><span class="sxs-lookup"><span data-stu-id="b0a18-131">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="b0a18-132">O parâmetro será exibido somente quando **Paralelizar confirmação** estiver definido como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b0a18-132">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>

> [!NOTE]
> <span data-ttu-id="b0a18-133">A opção para **Paralelizar confirmação** só é mostrada quando você tem mais de uma ordem planejada selecionada para confirmação.</span><span class="sxs-lookup"><span data-stu-id="b0a18-133">The option for **Parallelize firming** is only shown when you have more than one planned order selected for firming.</span></span>

<a name="additional-resources"></a><span data-ttu-id="b0a18-134">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b0a18-134">Additional resources</span></span>
--------

[<span data-ttu-id="b0a18-135">Visão geral de planos mestres</span><span class="sxs-lookup"><span data-stu-id="b0a18-135">Master plans overview</span></span>](master-plans.md)



