--- 
title: "Criar um número de produtos de grades de produto predefinidas"
description: "Este guia mostra como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado."
author: BibiSp
manager: AnnBe
ms.date: 09/26/2016
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
ms.openlocfilehash: 6294e4608b31c37aa713e3a7a2028b409b5a8366
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a><span data-ttu-id="ac495-103">Criar um número de produtos de grades de produto predefinidas</span><span class="sxs-lookup"><span data-stu-id="ac495-103">Create a product number for predefined product variants</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ac495-104">Este guia mostra como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.</span><span class="sxs-lookup"><span data-stu-id="ac495-104">This guide shows you how to set up a product number nomenclature for predefined product variants, and how you assign it to the appropriate product dimension group.</span></span> <span data-ttu-id="ac495-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="ac495-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ac495-106">A nova nomenclatura de número de produto é atribuída ao grupo de dimensão de produto Cor e Tamanho.</span><span class="sxs-lookup"><span data-stu-id="ac495-106">The new product number nomenclature is assigned to the Color and Size product dimension group.</span></span> <span data-ttu-id="ac495-107">A tarefa geralmente seria realizada por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="ac495-107">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="ac495-108">Criar uma nomenclatura de número de produto</span><span class="sxs-lookup"><span data-stu-id="ac495-108">Create a product number nomenclature</span></span>
1. <span data-ttu-id="ac495-109">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="ac495-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="ac495-110">Clique em Nomenclatura de produto.</span><span class="sxs-lookup"><span data-stu-id="ac495-110">Click Product nomenclature.</span></span>
3. <span data-ttu-id="ac495-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ac495-111">Click New.</span></span>
4. <span data-ttu-id="ac495-112">No campo Nome, digite um nome de nomenclatura que ajude a identificar o grupo de dimensões do produto de destino, por exemplo, ColorSize.</span><span class="sxs-lookup"><span data-stu-id="ac495-112">In the Name field, enter a nomenclature name that helps to identify the target product dimension group, for example, ColorSize..</span></span>
5. <span data-ttu-id="ac495-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ac495-113">In the Description field, type a value.</span></span>
6. <span data-ttu-id="ac495-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ac495-114">Click Add.</span></span>
7. <span data-ttu-id="ac495-115">Clique em Número do produto mestre.</span><span class="sxs-lookup"><span data-stu-id="ac495-115">Click Product master number.</span></span>
8. <span data-ttu-id="ac495-116">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ac495-116">Click Add.</span></span>
9. <span data-ttu-id="ac495-117">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="ac495-117">Click Text constant.</span></span>
10. <span data-ttu-id="ac495-118">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ac495-118">In the Text field, type a value.</span></span>
11. <span data-ttu-id="ac495-119">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ac495-119">Click Add.</span></span>
12. <span data-ttu-id="ac495-120">Clique em Cor.</span><span class="sxs-lookup"><span data-stu-id="ac495-120">Click Color.</span></span>
13. <span data-ttu-id="ac495-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ac495-121">Click Add.</span></span>
14. <span data-ttu-id="ac495-122">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="ac495-122">Click Text constant.</span></span>
15. <span data-ttu-id="ac495-123">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ac495-123">In the Text field, type a value.</span></span>
16. <span data-ttu-id="ac495-124">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ac495-124">Click Add.</span></span>
17. <span data-ttu-id="ac495-125">Clique em Tamanho.</span><span class="sxs-lookup"><span data-stu-id="ac495-125">Click Size.</span></span>
18. <span data-ttu-id="ac495-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ac495-126">Close the page.</span></span>

## <a name="assign-the-nomenclature-to-a-product-master"></a><span data-ttu-id="ac495-127">Atribuir a nomenclatura a um produto mestre</span><span class="sxs-lookup"><span data-stu-id="ac495-127">Assign the nomenclature to a product master</span></span>
1. <span data-ttu-id="ac495-128">Clique em Grupos de dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="ac495-128">Click Product dimension groups.</span></span>
2. <span data-ttu-id="ac495-129">Selecione o grupo de dimensões do produto SizeCol.</span><span class="sxs-lookup"><span data-stu-id="ac495-129">Select the SizeCol product dimension group.</span></span>
3. <span data-ttu-id="ac495-130">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="ac495-130">Click Edit.</span></span>
4. <span data-ttu-id="ac495-131">Selecione Sim no campo Usar nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="ac495-131">Select Yes in the Use nomenclature field.</span></span>
5. <span data-ttu-id="ac495-132">No campo Nomenclatura de número de grade de produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ac495-132">In the Product variant number nomenclature field, enter or select a value.</span></span>
6. <span data-ttu-id="ac495-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ac495-133">Close the page.</span></span>


