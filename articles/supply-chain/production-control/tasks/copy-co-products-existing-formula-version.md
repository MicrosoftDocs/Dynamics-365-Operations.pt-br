--- 
title: "Copiar coprodutos de uma versão de fórmula existente"
description: "Este procedimento mostra como copiar coprodutos de uma versão de fórmula existente para uma versão da fórmula diferente para um produto liberado."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, PmfFormulaCoBy, BOMRouteCopyDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 91212851a011536f17acef57e842587be1934e3e
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="copy-co-products-from-an-existing-formula-version"></a><span data-ttu-id="f533d-103">Copiar coprodutos de uma versão de fórmula existente</span><span class="sxs-lookup"><span data-stu-id="f533d-103">Copy co-products from an existing formula version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f533d-104">Este procedimento mostra como copiar coprodutos de uma versão de fórmula existente para uma versão da fórmula diferente para um produto liberado.</span><span class="sxs-lookup"><span data-stu-id="f533d-104">This procedure shows how to copy co-products from an existing formula version to a different formula version for a released product.</span></span> <span data-ttu-id="f533d-105">É um pré-requisito que haja pelo menos uma versão de fórmula associada aos coprodutos.</span><span class="sxs-lookup"><span data-stu-id="f533d-105">It is a prerequisite that there is at least one formula version associated with co-products.</span></span> <span data-ttu-id="f533d-106">A empresa de dados de demonstração USP2 é utilizada para criar esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="f533d-106">The demo data company USP2 is used to create this procedure.</span></span>


## <a name="find-a-released-product"></a><span data-ttu-id="f533d-107">Localize um produto lançado</span><span class="sxs-lookup"><span data-stu-id="f533d-107">Find a released product</span></span>
1. <span data-ttu-id="f533d-108">Vá para Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="f533d-108">Go to Released products.</span></span>
2. <span data-ttu-id="f533d-109">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="f533d-109">Click Show filters.</span></span>
    * <span data-ttu-id="f533d-110">Você está prestes a adicionar o campo Tipo de produção na caixa de diálogo do filtro.</span><span class="sxs-lookup"><span data-stu-id="f533d-110">You are about to add the field Production type in the filter dialog box.</span></span>  
3. <span data-ttu-id="f533d-111">Clique no campo Adicionar filtro para adicionar o campo Tipo de produção.</span><span class="sxs-lookup"><span data-stu-id="f533d-111">Click Add a filter field to add the field Production type.</span></span>
    * <span data-ttu-id="f533d-112">Na próxima etapa, você precisa especificar manualmente a Fórmula no campo Tipo de produção antes de selecionar Aplicar.</span><span class="sxs-lookup"><span data-stu-id="f533d-112">In the next step, you need to manually enter Formula in the Production type field before you select Apply.</span></span> <span data-ttu-id="f533d-113">Isso definirá o filtro na lista de produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="f533d-113">This sets the filter on the list of released products.</span></span>  
4. <span data-ttu-id="f533d-114">Insira manualmente a fórmula no campo Tipo de produção.</span><span class="sxs-lookup"><span data-stu-id="f533d-114">Manually enter Formula in the Production type field.</span></span>
5. <span data-ttu-id="f533d-115">Clique em Aplicar.</span><span class="sxs-lookup"><span data-stu-id="f533d-115">Click Apply.</span></span>

## <a name="select-a-released-product"></a><span data-ttu-id="f533d-116">Selecione um produto liberado</span><span class="sxs-lookup"><span data-stu-id="f533d-116">Select a released product</span></span>
1. <span data-ttu-id="f533d-117">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="f533d-117">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="f533d-118">Clique em Versões da fórmula.</span><span class="sxs-lookup"><span data-stu-id="f533d-118">Click Formula versions.</span></span>
    * <span data-ttu-id="f533d-119">No Painel de Ação Engenharia, clique em versões da fórmula.</span><span class="sxs-lookup"><span data-stu-id="f533d-119">On the Engineering Action Pane, click Formula versions.</span></span>  

## <a name="copy-co-products"></a><span data-ttu-id="f533d-120">Copiar coprodutos</span><span class="sxs-lookup"><span data-stu-id="f533d-120">Copy co-products</span></span>
1. <span data-ttu-id="f533d-121">No Painel de Ação, clique em Versão da fórmula.</span><span class="sxs-lookup"><span data-stu-id="f533d-121">On the Action Pane, click Formula version.</span></span>
2. <span data-ttu-id="f533d-122">Clique em Co-produtos.</span><span class="sxs-lookup"><span data-stu-id="f533d-122">Click Co-products.</span></span>
3. <span data-ttu-id="f533d-123">Clique em Copiar.</span><span class="sxs-lookup"><span data-stu-id="f533d-123">Click Copy.</span></span>
4. <span data-ttu-id="f533d-124">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f533d-124">In the Item number field, enter or select a value.</span></span>
5. <span data-ttu-id="f533d-125">No campo Versão da fórmula, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f533d-125">In the Formula version field, enter or select a value.</span></span>
6. <span data-ttu-id="f533d-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f533d-126">Click OK.</span></span>
7. <span data-ttu-id="f533d-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f533d-127">Close the page.</span></span>


