---
title: Zonas de quarentena para não conformidades
description: Este tópico descreve como criar e usar zonas de quarentena para não conformidades.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80f4b9dfc7882af4570bf1908784b8d114396402
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021795"
---
# <a name="quarantine-zones-for-nonconformances"></a><span data-ttu-id="bf96d-103">Zonas de quarentena para não conformidades</span><span class="sxs-lookup"><span data-stu-id="bf96d-103">Quarantine zones for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bf96d-104">Este tópico descreve como criar e usar zonas de quarentena para não conformidades.</span><span class="sxs-lookup"><span data-stu-id="bf96d-104">This topic describes how to create and use quarantine zones for nonconformances.</span></span>

<span data-ttu-id="bf96d-105">Use a página **Zonas de quarentena** para definir zonas que podem ser atribuídas a não conformidades.</span><span class="sxs-lookup"><span data-stu-id="bf96d-105">You use the **Quarantine zones** page to define zones that can be assigned to nonconformances.</span></span> <span data-ttu-id="bf96d-106">Ao criar uma não conformidade, você pode definir os campos **Zona de quarentena** e **Tipo de quarentena** na guia **Geral** da página **Não conformidades**.</span><span class="sxs-lookup"><span data-stu-id="bf96d-106">When you create a nonconformance, you can set the **Quarantine zone** and **Quarantine type** fields on the **General** tab of the **Non conformances** page.</span></span> <span data-ttu-id="bf96d-107">O campo **Zona de quarentena** normalmente indica a área ou o local em que o item está localizado.</span><span class="sxs-lookup"><span data-stu-id="bf96d-107">The **Quarantine zone** field typically indicates the area or location where the item is located.</span></span> <span data-ttu-id="bf96d-108">O campo **Tipo de quarentena** define o item como *Uso restrito* ou *Inutilizável*.</span><span class="sxs-lookup"><span data-stu-id="bf96d-108">The **Quarantine type** field defines the item as either *Restricted usage* or *Unusable*.</span></span>

<span data-ttu-id="bf96d-109">Ao imprimir um relatório de não conformidade ou de correções para uma não conformidade, você pode exibir a zona de quarentena na qual o item está localizado.</span><span class="sxs-lookup"><span data-stu-id="bf96d-109">When you print a nonconformance or corrections report for a nonconformance, you can view the quarantine zone where the item is located.</span></span>

<span data-ttu-id="bf96d-110">Você também pode imprimir um rótulo de não conformidade para uma não conformidade.</span><span class="sxs-lookup"><span data-stu-id="bf96d-110">You can also print a nonconformance tag for a nonconformance.</span></span> <span data-ttu-id="bf96d-111">Este relatório mostra a zona de quarentena atribuída e informações sobre o uso para fornecer orientações sobre como manusear material defeituoso.</span><span class="sxs-lookup"><span data-stu-id="bf96d-111">This report shows the assigned quarantine zone and information about usage to provide guidance about how defective material should be handled.</span></span> <span data-ttu-id="bf96d-112">As zonas de quarentena podem corresponder a locais de estoque ou recursos de operações.</span><span class="sxs-lookup"><span data-stu-id="bf96d-112">The quarantine zones might correspond to inventory locations or operations resources.</span></span>

## <a name="examples-of-quarantine-zones"></a><span data-ttu-id="bf96d-113">Exemplos de zonas de quarentena</span><span class="sxs-lookup"><span data-stu-id="bf96d-113">Examples of quarantine zones</span></span>

### <a name="example-1"></a><span data-ttu-id="bf96d-114">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="bf96d-114">Example 1</span></span>

<span data-ttu-id="bf96d-115">Você trabalha em uma empresa de fabricação de eletrônicos que produz e distribui televisões, alto-falantes e players de mídia.</span><span class="sxs-lookup"><span data-stu-id="bf96d-115">You work at an electronics manufacturing company that produces and distributes televisions, speakers, and media players.</span></span> <span data-ttu-id="bf96d-116">Nesse caso, você pode configurar uma zona de quarentena para representar cada tipo de produto.</span><span class="sxs-lookup"><span data-stu-id="bf96d-116">In this case, you can configure a quarantine zone to represent each type of product.</span></span>

### <a name="example-2"></a><span data-ttu-id="bf96d-117">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="bf96d-117">Example 2</span></span>

<span data-ttu-id="bf96d-118">Três compartimentos e dois racks são usados para armazenar itens que não estão em conformidade.</span><span class="sxs-lookup"><span data-stu-id="bf96d-118">Three bins and two racks are used to store items that are nonconforming.</span></span> <span data-ttu-id="bf96d-119">Nesse caso, você pode configurar cinco zonas de quarentena, uma para cada compartimento e cada rack.</span><span class="sxs-lookup"><span data-stu-id="bf96d-119">In this case, you can configure five quarantine zones, one for each bin and each rack.</span></span>

## <a name="create-a-quarantine-zone"></a><span data-ttu-id="bf96d-120">Criar uma zona de quarentena</span><span class="sxs-lookup"><span data-stu-id="bf96d-120">Create a quarantine zone</span></span>

1. <span data-ttu-id="bf96d-121">Vá para **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Zonas de quarentena**.</span><span class="sxs-lookup"><span data-stu-id="bf96d-121">Go to **Inventory management \> Setup \> Quality management \> Quarantine zones**.</span></span>
1. <span data-ttu-id="bf96d-122">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="bf96d-122">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="bf96d-123">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="bf96d-123">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="bf96d-124">**Zona de quarentena** – Insira um nome ou uma ID exclusiva para a zona de quarentena.</span><span class="sxs-lookup"><span data-stu-id="bf96d-124">**Quarantine zone** – Enter a unique ID or name for the quarantine zone.</span></span>
    - <span data-ttu-id="bf96d-125">**Descrição** – Insira uma descrição detalhada da zona de quarentena.</span><span class="sxs-lookup"><span data-stu-id="bf96d-125">**Description** – Enter a detailed description of the quarantine zone.</span></span>

1. <span data-ttu-id="bf96d-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bf96d-126">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bf96d-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bf96d-127">Additional resources</span></span>

- [<span data-ttu-id="bf96d-128">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="bf96d-128">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="bf96d-129">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="bf96d-129">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="bf96d-130">Trabalhadores responsáveis por aprovar não conformidades</span><span class="sxs-lookup"><span data-stu-id="bf96d-130">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="bf96d-131">Tipos de problema para não conformidades</span><span class="sxs-lookup"><span data-stu-id="bf96d-131">Problem types for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="bf96d-132">Tipos de diagnóstico para não conformidades</span><span class="sxs-lookup"><span data-stu-id="bf96d-132">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="bf96d-133">Encargos de qualidade para não conformidades</span><span class="sxs-lookup"><span data-stu-id="bf96d-133">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="bf96d-134">Operações para não conformidades</span><span class="sxs-lookup"><span data-stu-id="bf96d-134">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="bf96d-135">Gerenciamento de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="bf96d-135">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
