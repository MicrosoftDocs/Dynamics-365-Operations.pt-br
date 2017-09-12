--- 
title: Criar um produto acabado (apenas fevereiro de 2016)
description: Esta tarefa tem como foco criar um produto finalizado.
author: BibiSp
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 9d1718c5e9c98c77fbc274de1bf94f7f0e5eccb4
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-finished-product-february-2016-only"></a><span data-ttu-id="2547c-103">Criar um produto acabado (apenas fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="2547c-103">Create a finished product (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2547c-104">Esta tarefa tem como foco criar um produto finalizado.</span><span class="sxs-lookup"><span data-stu-id="2547c-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="2547c-105">Trata-se da primeira tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="2547c-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="2547c-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="2547c-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="2547c-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="2547c-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="2547c-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2547c-108">Click New.</span></span>
3. <span data-ttu-id="2547c-109">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2547c-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="2547c-110">Para a demonstração, digite BOM_1.</span><span class="sxs-lookup"><span data-stu-id="2547c-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="2547c-111">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2547c-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="2547c-112">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="2547c-112">Select STD.</span></span> <span data-ttu-id="2547c-113">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="2547c-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="2547c-114">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2547c-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="2547c-115">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="2547c-115">For example, select Audio.</span></span> <span data-ttu-id="2547c-116">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="2547c-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="2547c-117">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2547c-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="2547c-118">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="2547c-118">Select SiteWH.</span></span> <span data-ttu-id="2547c-119">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="2547c-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="2547c-120">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2547c-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="2547c-121">A dimensão de rastreamento não será usada neste exemplo. Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2547c-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="2547c-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2547c-122">Click OK.</span></span>
9. <span data-ttu-id="2547c-123">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="2547c-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="2547c-124">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="2547c-124">Click Default order settings.</span></span>
11. <span data-ttu-id="2547c-125">No campo Tipo de ordem padrão, selecione "Produção".</span><span class="sxs-lookup"><span data-stu-id="2547c-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="2547c-126">Como se trata de um produto finalizado que será produzido, selecione Produção.</span><span class="sxs-lookup"><span data-stu-id="2547c-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="2547c-127">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2547c-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="2547c-128">Para a demonstração, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="2547c-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="2547c-129">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2547c-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="2547c-130">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="2547c-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="2547c-131">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2547c-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="2547c-132">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="2547c-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="2547c-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2547c-133">Close the page.</span></span>


