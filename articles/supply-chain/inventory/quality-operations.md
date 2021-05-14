---
title: Operações para não conformidades
description: Este tópico descreve como criar e usar operações para não conformidades.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6454a56323ea66369696dd6e3310a41b4eb9ee58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956555"
---
# <a name="operations-for-nonconformances"></a><span data-ttu-id="42dda-103">Operações para não conformidades</span><span class="sxs-lookup"><span data-stu-id="42dda-103">Operations for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42dda-104">Este tópico descreve como criar e usar operações para não conformidades.</span><span class="sxs-lookup"><span data-stu-id="42dda-104">This topic describes how to create and use operations for nonconformances.</span></span>

<span data-ttu-id="42dda-105">Use a página **Operações** para definir classificações do trabalho que pode ser realizado para uma não conformidade aprovada.</span><span class="sxs-lookup"><span data-stu-id="42dda-105">You can use the **Operations** page to define classifications of the work that can be performed for an approved nonconformance.</span></span> <span data-ttu-id="42dda-106">Ao atribuir uma operação relacionada a uma não conformidade, é possível fornecer detalhes como o material associado, as horas de trabalho e os encargos necessários para executar a operação.</span><span class="sxs-lookup"><span data-stu-id="42dda-106">When you assign a related operation to a nonconformance, you can provide details such as the associated material, labor hours, and charges that are required to do the operation.</span></span> <span data-ttu-id="42dda-107">O sistema usa essas informações para calcular um custo estimado para a operação.</span><span class="sxs-lookup"><span data-stu-id="42dda-107">The system uses this information to calculate an estimated cost for the operation.</span></span> <span data-ttu-id="42dda-108">As informações detalhadas e os custos estimados são para referência apenas.</span><span class="sxs-lookup"><span data-stu-id="42dda-108">The detailed information and estimated costs are for reference.</span></span> <span data-ttu-id="42dda-109">As operações relacionadas para qualidade diferem das operações que podem ser definidas para um roteiro de produção.</span><span class="sxs-lookup"><span data-stu-id="42dda-109">The related operations for quality differ from the operations that can be defined for a production route.</span></span>

> [!NOTE]
> <span data-ttu-id="42dda-110">Embora seja possível rastrear os custos, o tempo e os itens usados em uma operação relacionada a uma não conformidade, os dados inseridos são apenas informativos.</span><span class="sxs-lookup"><span data-stu-id="42dda-110">Although you can track costs, time, and the items that are used in an operation that is related to a nonconformance, the data that you enter is only informational.</span></span> <span data-ttu-id="42dda-111">Eles não são integrados automaticamente à contabilidade, ao razão auxiliar de estoque ou ao módulo **Horário e presença**.</span><span class="sxs-lookup"><span data-stu-id="42dda-111">It isn't automatically integrated with the general ledger, inventory subledger, or the **Time and attendance** module.</span></span>

## <a name="examples-of-operations"></a><span data-ttu-id="42dda-112">Exemplos de operações</span><span class="sxs-lookup"><span data-stu-id="42dda-112">Examples of operations</span></span>

<span data-ttu-id="42dda-113">Você trabalha para uma empresa de fabricação.</span><span class="sxs-lookup"><span data-stu-id="42dda-113">You work for a manufacturing company.</span></span> <span data-ttu-id="42dda-114">Uma não conformidade foi criada e aprovada para itens que foram reprovados em um teste de qualidade.</span><span class="sxs-lookup"><span data-stu-id="42dda-114">A nonconformance was created and approved for items that failed a quality test.</span></span> <span data-ttu-id="42dda-115">Uma correção foi criada para indicar que o problema estava relacionado a um rolamento danificado em uma máquina.</span><span class="sxs-lookup"><span data-stu-id="42dda-115">A correction was created to indicate that the problem was related to a bad bearing on a machine.</span></span> <span data-ttu-id="42dda-116">Várias etapas são necessárias para substituir o rolamento, e a responsabilidade por cada operação é rastreada.</span><span class="sxs-lookup"><span data-stu-id="42dda-116">Several steps are required to replace the bearing, and the responsibility for each operation is tracked.</span></span> <span data-ttu-id="42dda-117">Por exemplo, as seguintes etapas podem ser necessárias:</span><span class="sxs-lookup"><span data-stu-id="42dda-117">For example, the following steps might be required:</span></span>

1. <span data-ttu-id="42dda-118">A linha de produção é interrompida e a rotina de limpeza é executada.</span><span class="sxs-lookup"><span data-stu-id="42dda-118">The production line is stopped, and the clean-out routine is performed.</span></span>
1. <span data-ttu-id="42dda-119">A equipe de manutenção substitui o rolamento.</span><span class="sxs-lookup"><span data-stu-id="42dda-119">Maintenance personnel replace the bearing.</span></span>
1. <span data-ttu-id="42dda-120">A equipe de garantia da qualidade inspeciona a máquina antes de ligá-la novamente.</span><span class="sxs-lookup"><span data-stu-id="42dda-120">Quality assurance personnel inspect the machine before it's turned back on.</span></span>

<span data-ttu-id="42dda-121">Neste exemplo, as seguintes operações podem ser criadas para representar o trabalho que deve ser feito:</span><span class="sxs-lookup"><span data-stu-id="42dda-121">For this example, the following operations can be created to represent the work that must be done:</span></span>

- <span data-ttu-id="42dda-122">Interromper a linha de produção.</span><span class="sxs-lookup"><span data-stu-id="42dda-122">Stop the production line.</span></span>
- <span data-ttu-id="42dda-123">Limpar a linha de produção.</span><span class="sxs-lookup"><span data-stu-id="42dda-123">Clean out the production line.</span></span>
- <span data-ttu-id="42dda-124">Realizar a manutenção na máquina.</span><span class="sxs-lookup"><span data-stu-id="42dda-124">Perform machine maintenance.</span></span>
- <span data-ttu-id="42dda-125">Inspecionar a máquina.</span><span class="sxs-lookup"><span data-stu-id="42dda-125">Inspect the machine.</span></span>

## <a name="create-an-operation"></a><span data-ttu-id="42dda-126">Criar uma operação</span><span class="sxs-lookup"><span data-stu-id="42dda-126">Create an operation</span></span>

1. <span data-ttu-id="42dda-127">Vá para **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Operações**.</span><span class="sxs-lookup"><span data-stu-id="42dda-127">Go to **Inventory management \> Setup \> Quality management \> Operations**.</span></span>
1. <span data-ttu-id="42dda-128">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="42dda-128">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="42dda-129">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="42dda-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="42dda-130">**Operação** – Insira um nome ou uma ID exclusiva para a operação.</span><span class="sxs-lookup"><span data-stu-id="42dda-130">**Operation** – Enter a unique ID or name for the operation.</span></span>
    - <span data-ttu-id="42dda-131">**Descrição** – Insira uma descrição detalhada da operação.</span><span class="sxs-lookup"><span data-stu-id="42dda-131">**Description** – Enter a detailed description of the operation.</span></span>
    - <span data-ttu-id="42dda-132">**Tipo** – Se a operação puder ser usada somente com não conformidades relacionadas a um tipo específico de ordem, selecione o tipo de ordem (*Ordem de compra* ou *Ordem de venda*).</span><span class="sxs-lookup"><span data-stu-id="42dda-132">**Type** – If the operation can be used only with nonconformances that are related to a specific type of order, select the order type (*Purchase order* or *Sales order*).</span></span>

1. <span data-ttu-id="42dda-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="42dda-133">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42dda-134">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="42dda-134">Additional resources</span></span>

- [<span data-ttu-id="42dda-135">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="42dda-135">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="42dda-136">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="42dda-136">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="42dda-137">Criar e processar não conformidades</span><span class="sxs-lookup"><span data-stu-id="42dda-137">Create and process nonconformances</span></span>](tasks/create-process-non-conformance.md)
- [<span data-ttu-id="42dda-138">Trabalhadores responsáveis por aprovar não conformidades</span><span class="sxs-lookup"><span data-stu-id="42dda-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="42dda-139">Zonas de quarentena para não conformidades</span><span class="sxs-lookup"><span data-stu-id="42dda-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="42dda-140">Tipos de diagnóstico para não conformidades</span><span class="sxs-lookup"><span data-stu-id="42dda-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="42dda-141">Encargos de qualidade para não conformidades</span><span class="sxs-lookup"><span data-stu-id="42dda-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="42dda-142">Tipos de problema para não conformidades</span><span class="sxs-lookup"><span data-stu-id="42dda-142">Problem types for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="42dda-143">Gerenciamento de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="42dda-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
