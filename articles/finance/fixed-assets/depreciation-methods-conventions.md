---
title: Métodos e convenções de depreciação
description: Este artigo oferece uma visão geral das convenções e dos métodos de depreciação com suporte no Microsoft Dynamics 365 Finance.
author: ShylaThompson
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: afd771f3f2f0434aa3663a9f99512f0c31adbb78
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826921"
---
# <a name="depreciation-methods-and-conventions"></a><span data-ttu-id="66687-103">Métodos e convenções de depreciação</span><span class="sxs-lookup"><span data-stu-id="66687-103">Depreciation methods and conventions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="66687-104">Este artigo oferece uma visão geral das convenções de depreciação e dos métodos de depreciação com suporte.</span><span class="sxs-lookup"><span data-stu-id="66687-104">This article provides an overview of the supported depreciation conventions and depreciation methods.</span></span>

<span data-ttu-id="66687-105">Você pode selecionar vários métodos de depreciação e convenções.</span><span class="sxs-lookup"><span data-stu-id="66687-105">You can select various depreciation methods and conventions.</span></span> <span data-ttu-id="66687-106">A finalidade dos métodos é alocar o valor depreciável do ativo fixo em períodos fiscais.</span><span class="sxs-lookup"><span data-stu-id="66687-106">The purpose of the methods is to allocate the depreciable value of the fixed asset into fiscal periods.</span></span> <span data-ttu-id="66687-107">O valor depreciável do ativo fixo é o preço de aquisição, reduzido por um valor de sucata, se houver.</span><span class="sxs-lookup"><span data-stu-id="66687-107">The depreciable value of the fixed asset is the acquisition price, reduced by a scrap value, if any.</span></span> 

<span data-ttu-id="66687-108">Se você estiver usando convenções de depreciação e modificar a última data de execução da depreciação para um ativo, o que ignora algumas depreciações, a depreciação do último ano poderá ser maior ou menor que o esperado.</span><span class="sxs-lookup"><span data-stu-id="66687-108">If you are using depreciation conventions and you modify the last depreciation run date for an asset, which then causes some depreciations to be skipped, the depreciation for the last year might be more than or less than is expected.</span></span> <span data-ttu-id="66687-109">A depreciação é ajustada pelo número de períodos de depreciação afetados pela modificação da última data de execução.</span><span class="sxs-lookup"><span data-stu-id="66687-109">The depreciation is adjusted by the number of depreciation periods affected by the modification of the last depreciation run date.</span></span>

<span data-ttu-id="66687-110">Por exemplo, se você estiver usando a convenção de depreciação de meio ano durante três anos, a depreciação normalmente ocorrerá em 3 1/2 anos.</span><span class="sxs-lookup"><span data-stu-id="66687-110">For example, if you are using the Half year depreciation convention over three years, depreciation ordinarily occurs over 3 1/2 years.</span></span> <span data-ttu-id="66687-111">Se você alterar a última data de execução de depreciação durante os 3 1/2 anos, o último ano de depreciação sairá do número de períodos afetados.</span><span class="sxs-lookup"><span data-stu-id="66687-111">If you change the last depreciation run date during the 3 1/2 years, the last year of depreciation moves out the number of periods affected.</span></span> <span data-ttu-id="66687-112">Se você mover a data em três meses, o último ano terá nove meses de depreciação, quando geralmente haveria seis meses de depreciação.</span><span class="sxs-lookup"><span data-stu-id="66687-112">If you move the date by three months, the last year will have nine months’ worth of depreciation, when ordinarily there would be six months’ worth of depreciation.</span></span>

<span data-ttu-id="66687-113">Você pode selecionar uma das convenções de depreciação a seguir.</span><span class="sxs-lookup"><span data-stu-id="66687-113">You can select from the following depreciation conventions.</span></span>


-   <span data-ttu-id="66687-114">Semestre</span><span class="sxs-lookup"><span data-stu-id="66687-114">Half year</span></span>
-   <span data-ttu-id="66687-115">Mês inteiro</span><span class="sxs-lookup"><span data-stu-id="66687-115">Full month</span></span>
-   <span data-ttu-id="66687-116">Meio do trimestre</span><span class="sxs-lookup"><span data-stu-id="66687-116">Mid quarter</span></span>
-   <span data-ttu-id="66687-117">Meio do mês (Primeiro Dia do Mês)</span><span class="sxs-lookup"><span data-stu-id="66687-117">Mid month (1st of month)</span></span>
-   <span data-ttu-id="66687-118">Meio do mês (Décimo quinto dia do Mês)</span><span class="sxs-lookup"><span data-stu-id="66687-118">Mid month (15th of month)</span></span>
-   <span data-ttu-id="66687-119">Semestre (início do ano)</span><span class="sxs-lookup"><span data-stu-id="66687-119">Half year (start of year)</span></span>
-   <span data-ttu-id="66687-120">Semestre (próximo ano)</span><span class="sxs-lookup"><span data-stu-id="66687-120">Half year (next year)</span></span>

<span data-ttu-id="66687-121">Você pode selecionar um dos seguintes métodos de depreciação.</span><span class="sxs-lookup"><span data-stu-id="66687-121">You can select from the following depreciation methods.</span></span>
-   <span data-ttu-id="66687-122">Vida útil linear</span><span class="sxs-lookup"><span data-stu-id="66687-122">Straight line service life</span></span>
-   <span data-ttu-id="66687-123">Saldo decrescente</span><span class="sxs-lookup"><span data-stu-id="66687-123">Reducing balance</span></span>
-   <span data-ttu-id="66687-124">Manual</span><span class="sxs-lookup"><span data-stu-id="66687-124">Manual</span></span>
-   <span data-ttu-id="66687-125">Fator</span><span class="sxs-lookup"><span data-stu-id="66687-125">Factor</span></span>
-   <span data-ttu-id="66687-126">Consumo</span><span class="sxs-lookup"><span data-stu-id="66687-126">Consumption</span></span>
-   <span data-ttu-id="66687-127">Vida útil linear restante</span><span class="sxs-lookup"><span data-stu-id="66687-127">Straight line life remaining</span></span>
-   <span data-ttu-id="66687-128">Declínio de 200%</span><span class="sxs-lookup"><span data-stu-id="66687-128">200% reducing balance</span></span>
-   <span data-ttu-id="66687-129">Declínio de 175%</span><span class="sxs-lookup"><span data-stu-id="66687-129">175% reducing balance</span></span>
-   <span data-ttu-id="66687-130">Declínio de 150%</span><span class="sxs-lookup"><span data-stu-id="66687-130">150% reducing balance</span></span>
-   <span data-ttu-id="66687-131">Declínio de 125%</span><span class="sxs-lookup"><span data-stu-id="66687-131">125% reducing balance</span></span>





<a name="additional-resources"></a><span data-ttu-id="66687-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="66687-132">Additional resources</span></span>
--------

[<span data-ttu-id="66687-133">Depreciação de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="66687-133">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)

[<span data-ttu-id="66687-134">Depreciação de vida útil linear</span><span class="sxs-lookup"><span data-stu-id="66687-134">Straight line service life depreciation</span></span>](Straight-line-service-life-depreciation.md)

[<span data-ttu-id="66687-135">Depreciação por declínio</span><span class="sxs-lookup"><span data-stu-id="66687-135">Reduce balance depreciation</span></span>](reduce-balance-depreciation.md)

[<span data-ttu-id="66687-136">Depreciação manual</span><span class="sxs-lookup"><span data-stu-id="66687-136">Manual depreciation</span></span>](manual-depreciation.md)

[<span data-ttu-id="66687-137">Depreciação por fator</span><span class="sxs-lookup"><span data-stu-id="66687-137">Factor depreciation</span></span>](factor-depreciation.md)

[<span data-ttu-id="66687-138">Depreciação de consumo</span><span class="sxs-lookup"><span data-stu-id="66687-138">Consumption depreciation</span></span>](consumption-depreciation.md)

[<span data-ttu-id="66687-139">Depreciação da vida útil linear restante</span><span class="sxs-lookup"><span data-stu-id="66687-139">Straight line life remaining depreciation</span></span>](straight-line-life-remaining-depreciation.md)

[<span data-ttu-id="66687-140">depreciação com declínio de 125%</span><span class="sxs-lookup"><span data-stu-id="66687-140">125 percent reducing balance depreciation</span></span>](125-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="66687-141">depreciação com declínio de 150%</span><span class="sxs-lookup"><span data-stu-id="66687-141">150 percent reducing balance depreciation</span></span>](150-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="66687-142">depreciação com declínio de 175%</span><span class="sxs-lookup"><span data-stu-id="66687-142">175 percent reducing balance depreciation</span></span>](175-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="66687-143">depreciação com declínio de 200%</span><span class="sxs-lookup"><span data-stu-id="66687-143">200 percent reducing balance depreciation</span></span>](200-percent-reducing-balance-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]