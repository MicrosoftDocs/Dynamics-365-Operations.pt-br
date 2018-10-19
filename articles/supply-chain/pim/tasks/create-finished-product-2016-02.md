--- 
title: Criar um produto finalizado (Fevereiro de 2016)
description: Esta tarefa tem como foco criar um produto finalizado.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 44b3bf17c69f37e7a96c75345a3e4f27ba9eab50
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-finished-product-february-2016"></a><span data-ttu-id="23376-103">Criar um produto finalizado (Fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="23376-103">Create a finished product (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="23376-104">Esta tarefa tem como foco criar um produto finalizado.</span><span class="sxs-lookup"><span data-stu-id="23376-104">This task focuses on creating a finished product.</span></span> <span data-ttu-id="23376-105">Trata-se da primeira tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="23376-105">It is the first task in the BOM calculation series.</span></span> <span data-ttu-id="23376-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="23376-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="23376-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="23376-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="23376-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="23376-108">Click New.</span></span>
3. <span data-ttu-id="23376-109">No campo Número do produto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="23376-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="23376-110">Para a demonstração, digite BOM_1.</span><span class="sxs-lookup"><span data-stu-id="23376-110">For the demonstration, type BOM_1.</span></span>  
4. <span data-ttu-id="23376-111">No campo Grupo de modelos do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="23376-111">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="23376-112">Selecione STD.</span><span class="sxs-lookup"><span data-stu-id="23376-112">Select STD.</span></span> <span data-ttu-id="23376-113">STD significa "custo padrão" e é o modelo mais comumente utilizado ao se trabalhar com cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="23376-113">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="23376-114">No campo Grupo de itens, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="23376-114">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="23376-115">Por exemplo, selecione Áudio.</span><span class="sxs-lookup"><span data-stu-id="23376-115">For example, select Audio.</span></span> <span data-ttu-id="23376-116">Isso não tem impacto sobre os cálculos de custo.</span><span class="sxs-lookup"><span data-stu-id="23376-116">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="23376-117">No campo Grupo de dimensões de armazenamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="23376-117">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="23376-118">Selecione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="23376-118">Select SiteWH.</span></span> <span data-ttu-id="23376-119">Apenas Site e Depósito serão usados na demonstração.</span><span class="sxs-lookup"><span data-stu-id="23376-119">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="23376-120">No campo Grupo de dimensões de rastreamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="23376-120">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="23376-121">A dimensão de rastreamento não será usada neste exemplo. Selecione Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="23376-121">Tracking dimensions will not be used for this example, select None.</span></span>  
8. <span data-ttu-id="23376-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="23376-122">Click OK.</span></span>
9. <span data-ttu-id="23376-123">No Painel de Ação, clique em Gerenciar estoque.</span><span class="sxs-lookup"><span data-stu-id="23376-123">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="23376-124">Clique em Configurações de ordem padrão.</span><span class="sxs-lookup"><span data-stu-id="23376-124">Click Default order settings.</span></span>
11. <span data-ttu-id="23376-125">No campo Tipo de ordem padrão, selecione "Produção".</span><span class="sxs-lookup"><span data-stu-id="23376-125">In the Default order type field, select 'Production'.</span></span>
    * <span data-ttu-id="23376-126">Como se trata de um produto finalizado que será produzido, selecione Produção.</span><span class="sxs-lookup"><span data-stu-id="23376-126">Because this is a finished product that will be produced, select Production.</span></span>  
12. <span data-ttu-id="23376-127">No campo Site de compra, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="23376-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="23376-128">Para a demonstração, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="23376-128">For the demonstration, select Site 1.</span></span>  
13. <span data-ttu-id="23376-129">No campo Site de estoque, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="23376-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="23376-130">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="23376-130">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="23376-131">No campo Site de vendas, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="23376-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="23376-132">Neste exemplo, selecione Site 1.</span><span class="sxs-lookup"><span data-stu-id="23376-132">For this example, select Site 1.</span></span>  
15. <span data-ttu-id="23376-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="23376-133">Close the page.</span></span>


