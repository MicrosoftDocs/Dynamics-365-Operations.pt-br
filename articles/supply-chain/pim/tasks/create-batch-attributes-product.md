---
title: Criar atributos de lote para um produto
description: Este procedimento mostra como criar um atributo de lote, atribuir faixas padrões de valores, e incluir o atributo em um grupo.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsBatchAttrib
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d874b6b6e53164c00d9b4656d27b1060f4e3ba06
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934926"
---
# <a name="create-batch-attributes-for-a-product"></a><span data-ttu-id="75b8f-103">Criar atributos de lote para um produto</span><span class="sxs-lookup"><span data-stu-id="75b8f-103">Create batch attributes for a product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="75b8f-104">Este procedimento mostra como criar um atributo de lote, atribuir faixas padrões de valores, e incluir o atributo em um grupo.</span><span class="sxs-lookup"><span data-stu-id="75b8f-104">This procedure shows how to create a batch attribute, assign default value ranges, and include the attribute in a group.</span></span> <span data-ttu-id="75b8f-105">A empresa de dados demonstrativos utilizada para criar este procedimento é a empresa USP2.</span><span class="sxs-lookup"><span data-stu-id="75b8f-105">The demo data company used to create this procedure is the USP2 Company.</span></span>

1. <span data-ttu-id="75b8f-106">Vá para Gerenciamento de estoque > Configuração > Lote > Atributos de lote.</span><span class="sxs-lookup"><span data-stu-id="75b8f-106">Go to Inventory management > Setup > Batch > Batch attributes.</span></span>
2. <span data-ttu-id="75b8f-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="75b8f-107">Click New.</span></span>
3. <span data-ttu-id="75b8f-108">No campo Atributo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="75b8f-108">In the Attribute field, type a value.</span></span>
4. <span data-ttu-id="75b8f-109">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="75b8f-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="75b8f-110">No campo Tipo de atributo, selecione 'Fração'.</span><span class="sxs-lookup"><span data-stu-id="75b8f-110">In the Attribute type field, select 'Fraction'.</span></span>
    * <span data-ttu-id="75b8f-111">Este procedimento usa o tipo Fração para habilitar valores decimais.</span><span class="sxs-lookup"><span data-stu-id="75b8f-111">This procedure uses the Fraction type to enable decimal values.</span></span> <span data-ttu-id="75b8f-112">Você pode selecionar outros tipos de atributo.</span><span class="sxs-lookup"><span data-stu-id="75b8f-112">You can select other attribute types.</span></span> <span data-ttu-id="75b8f-113">Se você selecionar o tipo Enumeração, você deve inserir valores na lista de enumeração para que possa inserir um valor no campo Destino.</span><span class="sxs-lookup"><span data-stu-id="75b8f-113">If you select the Enumeration type, you must enter values in the enumeration list before you can enter a value in the Target field.</span></span>  
6. <span data-ttu-id="75b8f-114">No campo Mínimo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="75b8f-114">In the Minimum field, enter a number.</span></span>
7. <span data-ttu-id="75b8f-115">No campo Máximo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="75b8f-115">In the Maximum field, enter a number.</span></span>
8. <span data-ttu-id="75b8f-116">No campo Incremento, insira um número.</span><span class="sxs-lookup"><span data-stu-id="75b8f-116">In the Increment field, enter a number.</span></span>
9. <span data-ttu-id="75b8f-117">No campo Destino, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="75b8f-117">In the Target field, type a value.</span></span>
10. <span data-ttu-id="75b8f-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="75b8f-118">Click Save.</span></span>
11. <span data-ttu-id="75b8f-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="75b8f-119">Close the page.</span></span>
12. <span data-ttu-id="75b8f-120">Vá para Gerenciamento de estoque > Configuração > Lote > Grupos de atributos de lote.</span><span class="sxs-lookup"><span data-stu-id="75b8f-120">Go to Inventory management > Setup > Batch > Batch attribute groups.</span></span>
13. <span data-ttu-id="75b8f-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="75b8f-121">Click New.</span></span>
14. <span data-ttu-id="75b8f-122">No campo Grupo de atributos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="75b8f-122">In the Attribute group field, type a value.</span></span>
15. <span data-ttu-id="75b8f-123">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="75b8f-123">In the Description field, type a value.</span></span>
16. <span data-ttu-id="75b8f-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="75b8f-124">Click Save.</span></span>
17. <span data-ttu-id="75b8f-125">Clique em Atributos de grupo.</span><span class="sxs-lookup"><span data-stu-id="75b8f-125">Click Group attributes.</span></span>
18. <span data-ttu-id="75b8f-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="75b8f-126">Click New.</span></span>
19. <span data-ttu-id="75b8f-127">No campo Atributo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="75b8f-127">In the Attribute field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="75b8f-128">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="75b8f-128">In the list, find and select the desired record.</span></span>
21. <span data-ttu-id="75b8f-129">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="75b8f-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="75b8f-130">Um atributo pode ser incluído em qualquer um dos grupos.</span><span class="sxs-lookup"><span data-stu-id="75b8f-130">An attribute can be included in any of the groups.</span></span>  
22. <span data-ttu-id="75b8f-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="75b8f-131">Click Save.</span></span>
23. <span data-ttu-id="75b8f-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="75b8f-132">Close the page.</span></span>

