---
title: Tipos de diagnóstico para não conformidades
description: Este tópico descreve como usar e criar tipos de diagnóstico que possam ser usados com não conformidades.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19fcd57e28efabd6ca32c444ab961b876bde424d
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956543"
---
# <a name="diagnostic-types-for-nonconformances"></a><span data-ttu-id="9c3ea-103">Tipos de diagnóstico para não conformidades</span><span class="sxs-lookup"><span data-stu-id="9c3ea-103">Diagnostic types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c3ea-104">Este tópico descreve como usar e criar tipos de diagnóstico que possam ser usados com não conformidades.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-104">This topic describes how to use and create diagnostic types that can be used with nonconformances.</span></span>

<span data-ttu-id="9c3ea-105">Use a página **Tipos de diagnóstico** para definir uma classificação de ações de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-105">You use the **Diagnostic types** page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="9c3ea-106">Em seguida, ao criar uma correção para uma não conformidade, selecione um diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-106">Then, when you create a correction for a nonconformance, you select a diagnostic.</span></span> <span data-ttu-id="9c3ea-107">Uma correção especifica o tipo de ação de diagnóstico que deve ser tomada para uma não conformidade aprovada e quem deve realizar essa ação.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-107">A correction specifies what type of diagnostic action should be taken for an approved nonconformance, and who should take that action.</span></span> <span data-ttu-id="9c3ea-108">Ela também especifica a data de conclusão solicitada e a data de conclusão planejada.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-108">It also specifies the requested completion date and the planned completion date.</span></span>

## <a name="examples-of-diagnostic-types"></a><span data-ttu-id="9c3ea-109">Exemplos de tipos de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9c3ea-109">Examples of diagnostic types</span></span>

<span data-ttu-id="9c3ea-110">Você trabalha para uma empresa de fabricação e vários itens foram reprovados nos testes de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-110">You work for a manufacturing company, and several items have failed quality tests.</span></span> <span data-ttu-id="9c3ea-111">Esses itens são movidos para uma área de quarentena e marcados como produtos que não estão em conformidade.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-111">Those items are moved into a quarantine area and marked as nonconforming products.</span></span> <span data-ttu-id="9c3ea-112">Um registro de não conformidade é criado no Microsoft Dynamics 365 Supply Chain Management para acompanhar os detalhes durante a resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-112">A nonconformance record is created in Microsoft Dynamics 365 Supply Chain Management to track the details through issue resolution.</span></span>

<span data-ttu-id="9c3ea-113">Nesse caso, os problemas de qualidade estão ocorrendo porque rolamentos na máquina que empacota os itens foram danificados e estão superaquecendo.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-113">In this case, the quality issues are occurring because bearings in the machine that packages the items have gone bad and are overheating.</span></span> <span data-ttu-id="9c3ea-114">A correção desse problema é substituir as peças na máquina.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-114">The correction for this problem is to replace the parts in the machine.</span></span>

<span data-ttu-id="9c3ea-115">Ao configurar os tipos de diagnóstico, você pode criar vários registros, cada um deles representando um tipo diferente de problema que a máquina pode ter.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-115">When you configure the diagnostic types, you can create multiple records, each of which represents a different type of problem that the machine might have.</span></span> <span data-ttu-id="9c3ea-116">Como alternativa, você pode criar um tipo de diagnóstico genérico que represente o reparo da máquina.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-116">Alternatively, you can create one generic diagnostic type that represents machine repair.</span></span>

## <a name="create-a-diagnostic-type"></a><span data-ttu-id="9c3ea-117">Criar um tipo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9c3ea-117">Create a diagnostic type</span></span>

1. <span data-ttu-id="9c3ea-118">Vá para **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Tipos de diagnóstico**.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-118">Go to **Inventory management \> Setup \> Quality management \> Diagnostic types**.</span></span>
1. <span data-ttu-id="9c3ea-119">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="9c3ea-120">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="9c3ea-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="9c3ea-121">**Diagnóstico** – Insira um nome ou uma ID exclusiva para o tipo de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-121">**Diagnostic** – Enter a unique ID or name for the diagnostic type.</span></span>
    - <span data-ttu-id="9c3ea-122">**Descrição** – Insira uma descrição detalhada do tipo de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-122">**Description** – Enter a detailed description of the diagnostic type.</span></span>

1. <span data-ttu-id="9c3ea-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9c3ea-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c3ea-124">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9c3ea-124">Additional resources</span></span>

- [<span data-ttu-id="9c3ea-125">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="9c3ea-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="9c3ea-126">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="9c3ea-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="9c3ea-127">Trabalhadores responsáveis por aprovar não conformidades</span><span class="sxs-lookup"><span data-stu-id="9c3ea-127">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="9c3ea-128">Zonas de quarentena para não conformidades</span><span class="sxs-lookup"><span data-stu-id="9c3ea-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="9c3ea-129">Tipos de problema para não conformidades</span><span class="sxs-lookup"><span data-stu-id="9c3ea-129">Problem types for nonconformances</span></span>](quality-problem-types.md)
- [<span data-ttu-id="9c3ea-130">Encargos de qualidade para não conformidades</span><span class="sxs-lookup"><span data-stu-id="9c3ea-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="9c3ea-131">Operações para não conformidades</span><span class="sxs-lookup"><span data-stu-id="9c3ea-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="9c3ea-132">Gerenciamento de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="9c3ea-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
