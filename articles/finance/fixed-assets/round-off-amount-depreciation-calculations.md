---
title: Valor de arredondamento para cálculos de depreciação
description: Este artigo discute o campo Arredondar depreciação, encontrado nas páginas no registro de depreciações.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40fd019b1b5900fbd15866d9d3c32ed6d88147b4
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187075"
---
# <a name="round-off-amount-for-depreciation-calculations"></a><span data-ttu-id="aef40-103">Valor de arredondamento para cálculos de depreciação</span><span class="sxs-lookup"><span data-stu-id="aef40-103">Round-off amount for depreciation calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aef40-104">Este artigo discute o campo Arredondar depreciação, encontrado nas páginas no registro de depreciações.</span><span class="sxs-lookup"><span data-stu-id="aef40-104">This article discusses the Round-off depreciation field that is found on the Book setup pages.</span></span>

<span data-ttu-id="aef40-105">Montantes de amortização arredondados são definidos para cada livro.</span><span class="sxs-lookup"><span data-stu-id="aef40-105">Round-off depreciation amounts are set for each book.</span></span> <span data-ttu-id="aef40-106">Os valores de depreciação arredondados são usados no perfil de depreciação de ativo fixo que mostra a depreciação e o valor futuro do ativo fixo, e também nas propostas de depreciação.</span><span class="sxs-lookup"><span data-stu-id="aef40-106">Round-off depreciation amounts are used in the fixed asset depreciation profile that shows the future depreciation and value of the fixed asset, and also in depreciation proposals.</span></span> <span data-ttu-id="aef40-107">Insira o menor valor de depreciação que é permitido para o registro.</span><span class="sxs-lookup"><span data-stu-id="aef40-107">Enter the lowest depreciation amount that is allowed for the book.</span></span> 

<span data-ttu-id="aef40-108">Independentemente de arredondamento configurado, o valor de depreciação no último período de depreciação não é arredondado.</span><span class="sxs-lookup"><span data-stu-id="aef40-108">Regardless of the rounding that is set up, the depreciation amount in the last depreciation period isn't rounded.</span></span> <span data-ttu-id="aef40-109">No final do último período de depreciação, o valor do ativo fixo deve ser 0 (zero) ou o valor de sucata, se o valor de sucata é usado.</span><span class="sxs-lookup"><span data-stu-id="aef40-109">At the end of the last depreciation period, the value of the fixed asset must be 0 (zero) or the scrap value, if scrap value is used.</span></span>

### <a name="example"></a><span data-ttu-id="aef40-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="aef40-110">Example</span></span>

<span data-ttu-id="aef40-111">Depreciação sem arredondamento é calculada como 2.444,44.</span><span class="sxs-lookup"><span data-stu-id="aef40-111">Depreciation without rounding is calculated as 2,444.44.</span></span> <span data-ttu-id="aef40-112">Como mostrado na tabela a seguir, os valores sugeridos variam dependendo da configuração do arredondamento.</span><span class="sxs-lookup"><span data-stu-id="aef40-112">As the following table shows, the amounts that are suggested vary, depending on how rounding is set up.</span></span>

| <span data-ttu-id="aef40-113">Método de arredondamento</span><span class="sxs-lookup"><span data-stu-id="aef40-113">Rounding method</span></span> | <span data-ttu-id="aef40-114">Valor de depreciação</span><span class="sxs-lookup"><span data-stu-id="aef40-114">Depreciation amount</span></span> |
|-----------------|---------------------|
| <span data-ttu-id="aef40-115">Arredondar 0,1</span><span class="sxs-lookup"><span data-stu-id="aef40-115">Rounding 0.1</span></span>    | <span data-ttu-id="aef40-116">2.444,40</span><span class="sxs-lookup"><span data-stu-id="aef40-116">2,444.40</span></span>            |
| <span data-ttu-id="aef40-117">Arredondar 1,00</span><span class="sxs-lookup"><span data-stu-id="aef40-117">Rounding 1.00</span></span>   | <span data-ttu-id="aef40-118">2.444,00</span><span class="sxs-lookup"><span data-stu-id="aef40-118">2,444.00</span></span>            |
| <span data-ttu-id="aef40-119">Arredondar 10,00</span><span class="sxs-lookup"><span data-stu-id="aef40-119">Rounding 10.00</span></span>  | <span data-ttu-id="aef40-120">2.440,00</span><span class="sxs-lookup"><span data-stu-id="aef40-120">2,440.00</span></span>            |
| <span data-ttu-id="aef40-121">Arredondar 100,00</span><span class="sxs-lookup"><span data-stu-id="aef40-121">Rounding 100.00</span></span> | <span data-ttu-id="aef40-122">2.400,00</span><span class="sxs-lookup"><span data-stu-id="aef40-122">2,400.00</span></span>            |





