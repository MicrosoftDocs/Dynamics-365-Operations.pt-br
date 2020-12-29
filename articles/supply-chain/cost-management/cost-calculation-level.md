---
title: Nível de cálculo de custo
description: Este tópico descreve o nível de BOM (lista de materiais) denominado Nível de cálculo de custos. Esse nível de BOM exclui as ordens de produção e de lotes dos cálculos.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 52b77e794ee38add556ac01d62c973b38c48a548
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422094"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="7d092-104">Nível de cálculo de custo</span><span class="sxs-lookup"><span data-stu-id="7d092-104">Cost calculation level</span></span>

<span data-ttu-id="7d092-105">O nível da BOM (lista de materiais) denominado **Nível de cálculo de custos** exclui ordens de produção e ordens de lotes dos cálculos.</span><span class="sxs-lookup"><span data-stu-id="7d092-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="7d092-106">O sistema usa esse nível quando executa cálculos de custo em versões de custo.</span><span class="sxs-lookup"><span data-stu-id="7d092-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="7d092-107">Em processos como recálculo e fechamento do estoque, o sistema usa o nível de BOM **Nível de custo**.</span><span class="sxs-lookup"><span data-stu-id="7d092-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="7d092-108">O cenário simples a seguir mostra as diferenças entre os níveis de BOM **Nível de cálculo de custo** e **Nível de custo**.</span><span class="sxs-lookup"><span data-stu-id="7d092-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="7d092-109">Você tem três produtos: A, B e C. O produto C é o componente do produto B e o produto B é o componente do produto A.</span><span class="sxs-lookup"><span data-stu-id="7d092-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="7d092-110">O **Nível de custo** atribui os seguintes níveis de BOM:</span><span class="sxs-lookup"><span data-stu-id="7d092-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="7d092-111">**Produto A:** 0</span><span class="sxs-lookup"><span data-stu-id="7d092-111">**Product A:** 0</span></span>
    - <span data-ttu-id="7d092-112">**Produto B:** 1</span><span class="sxs-lookup"><span data-stu-id="7d092-112">**Product B:** 1</span></span>
    - <span data-ttu-id="7d092-113">**Produto C:** 2</span><span class="sxs-lookup"><span data-stu-id="7d092-113">**Product C:** 2</span></span>

- <span data-ttu-id="7d092-114">O **Nível de cálculo de custo** atribui os seguintes níveis de BOM:</span><span class="sxs-lookup"><span data-stu-id="7d092-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="7d092-115">**Produto A:** 0</span><span class="sxs-lookup"><span data-stu-id="7d092-115">**Product A:** 0</span></span>
    - <span data-ttu-id="7d092-116">**Produto B:** 1</span><span class="sxs-lookup"><span data-stu-id="7d092-116">**Product B:** 1</span></span>
    - <span data-ttu-id="7d092-117">**Produto C:** 2</span><span class="sxs-lookup"><span data-stu-id="7d092-117">**Product C:** 2</span></span>

<span data-ttu-id="7d092-118">Uma ordem de produção do produto C é criada e o produto A é adicionado à BOM da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="7d092-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="7d092-119">Depois que a ordem for estimada, os níveis de BOM serão atualizados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7d092-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="7d092-120">O **Nível de custo** atribui os seguintes níveis de BOM:</span><span class="sxs-lookup"><span data-stu-id="7d092-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="7d092-121">**Produto B:** 1</span><span class="sxs-lookup"><span data-stu-id="7d092-121">**Product B:** 1</span></span>
    - <span data-ttu-id="7d092-122">**Produto C:** 2</span><span class="sxs-lookup"><span data-stu-id="7d092-122">**Product C:** 2</span></span>
    - <span data-ttu-id="7d092-123">**Produto A:** 3</span><span class="sxs-lookup"><span data-stu-id="7d092-123">**Product A:** 3</span></span>

- <span data-ttu-id="7d092-124">O **Nível de cálculo de custo** atribui os seguintes níveis de BOM:</span><span class="sxs-lookup"><span data-stu-id="7d092-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="7d092-125">**Produto A:** 0</span><span class="sxs-lookup"><span data-stu-id="7d092-125">**Product A:** 0</span></span>
    - <span data-ttu-id="7d092-126">**Produto B:** 1</span><span class="sxs-lookup"><span data-stu-id="7d092-126">**Product B:** 1</span></span>
    - <span data-ttu-id="7d092-127">**Produto C:** 2</span><span class="sxs-lookup"><span data-stu-id="7d092-127">**Product C:** 2</span></span>

<span data-ttu-id="7d092-128">Esse comportamento garante que as alterações em BOMs da ordem de produção não afetem os cálculos de custo subsequentes.</span><span class="sxs-lookup"><span data-stu-id="7d092-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>
