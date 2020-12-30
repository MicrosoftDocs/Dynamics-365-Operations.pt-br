---
title: Reduzir depreciação por declínio após uma divisão
description: Este tópico descreve o método usado em Ativos fixos para calcular a depreciação depois que um ativo é dividido usando o método por declínio.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 615d17c71b904d426081d4c57492ba7e95c2c749
ms.sourcegitcommit: 65f9e2584c0530b1a71655aae09101691726b47f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4650647"
---
# <a name="reduce-balance-depreciation-after-a-split"></a><span data-ttu-id="23147-103">Reduzir depreciação por declínio após uma divisão</span><span class="sxs-lookup"><span data-stu-id="23147-103">Reduce balance depreciation after a split</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23147-104">Este tópico descreve o método usado em Ativos fixos para calcular a depreciação depois que um ativo é dividido para outro ativo usando o método por declínio.</span><span class="sxs-lookup"><span data-stu-id="23147-104">This topic describes the method that is used in Fixed assets to calculate depreciation after an asset is split to another asset by using the reduce balance method.</span></span> <span data-ttu-id="23147-105">O ano de depreciação configurado no registro de ativos é o ano fiscal.</span><span class="sxs-lookup"><span data-stu-id="23147-105">The depreciation year that is configured in the asset book is the fiscal year.</span></span> <span data-ttu-id="23147-106">Para obter mais informações, consulte [Depreciação por declínio](reduce-balance-depreciation.md) e [Dividir um ativo fixo](tasks/split-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="23147-106">For more information, see [Reduce balance depreciation](reduce-balance-depreciation.md) and [Split a fixed asset](tasks/split-fixed-asset.md).</span></span>

<span data-ttu-id="23147-107">Se você dividir um ativo fixo durante um período fiscal posterior ao período em que o ativo foi adquirido, a depreciação de saldo reduzida contará como o valor líquido contábil (NBV) do ativo para o ano anterior.</span><span class="sxs-lookup"><span data-stu-id="23147-107">If you split a fixed asset during a fiscal period that is later than the period when the asset was acquired, the reduced balance depreciation will account for the asset's net book value (NBV) for the previous year.</span></span> <span data-ttu-id="23147-108">Também serão contabilizadas as transações de ajuste de aquisição e depreciação que foram geradas da transação que dividiu o ativo.</span><span class="sxs-lookup"><span data-stu-id="23147-108">It will also account for the acquisition and depreciation adjustment transactions that were generated from the transaction that split the asset.</span></span> <span data-ttu-id="23147-109">Esse comportamento supõe que o ativo foi adquirido em um ano fiscal e dividido em um ano fiscal posterior.</span><span class="sxs-lookup"><span data-stu-id="23147-109">This behavior assumes that the asset was acquired in one fiscal year and split in a later fiscal year.</span></span> <span data-ttu-id="23147-110">O valor que deve ser depreciado para o ativo original após a divisão reflete o NBV do ativo antes da divisão do ativo, e a transação de ajuste de aquisição e depreciação lançada para a divisão.</span><span class="sxs-lookup"><span data-stu-id="23147-110">The amount that must be depreciated for the original asset after the split reflects the asset's NBV before the asset was split, and the acquisition and depreciation adjustment transaction that was posted for the split.</span></span>

<span data-ttu-id="23147-111">Por exemplo, as seguintes condições estão em vigor:</span><span class="sxs-lookup"><span data-stu-id="23147-111">For example, the following conditions are in effect:</span></span>

- <span data-ttu-id="23147-112">O período fiscal vai de 30 de junho a 1º de julho.</span><span class="sxs-lookup"><span data-stu-id="23147-112">The fiscal period is from June 30 to July 1.</span></span>
- <span data-ttu-id="23147-113">A porcentagem do saldo decrescente é 18% e um ativo é adquirido em junho de 2019, a um preço de aquisição de US$ 10.000.</span><span class="sxs-lookup"><span data-stu-id="23147-113">The reducing balance percentage is 18 percent, and an asset is acquired in June 2019 at an acquisition price of $10,000.</span></span>
- <span data-ttu-id="23147-114">A depreciação do primeiro ano fiscal é igual a US$ 18.000, a depreciação mensal é igual a US$ 150 e o ativo é depreciado até novembro de 2019, no valor de US$ 738,75.</span><span class="sxs-lookup"><span data-stu-id="23147-114">The depreciation of the first fiscal year equals $18,000, the monthly depreciation equals $150, and the asset is then depreciated until November 2019, in the amount of $738.75.</span></span>
- <span data-ttu-id="23147-115">Em novembro de 2019, 80% do ativo é dividido para outro ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="23147-115">In November 2019, 80 percent of the asset is split to another fixed asset.</span></span>

<span data-ttu-id="23147-116">[![Reduzir depreciação por declínio após uma divisão](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span><span class="sxs-lookup"><span data-stu-id="23147-116">[![Reduce balance depreciation after a split](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span></span>

<span data-ttu-id="23147-117">O valor a ser depreciado para o ativo original é de US$ 1.822,25.</span><span class="sxs-lookup"><span data-stu-id="23147-117">The amount to depreciate for the original asset is $1,822.25.</span></span> <span data-ttu-id="23147-118">Esse valor é igual ao NBV antes da transação dividida ser lançada (US$ 9.111,25), além do ajuste de aquisição que é gerado durante o lançamento da transação dividida (-US$ 8.000), mais o ajuste de depreciação gerado durante a transação dividida (US$ 711).</span><span class="sxs-lookup"><span data-stu-id="23147-118">This amount equals the NBV before the split transaction is posted ($9,111.25), plus the acquisition adjustment that is generated during posting of the split transaction (-$8,000), plus the depreciation adjustment that is generated during the split transaction ($711).</span></span> <span data-ttu-id="23147-119">Portanto, a depreciação para o segundo ano é de (1.822,25 × 18%) ÷ 12 = US$ 27,33.</span><span class="sxs-lookup"><span data-stu-id="23147-119">Therefore, the depreciation for the second year is (1,822.25 × 18 percent) ÷ 12 = $27.33.</span></span>

<span data-ttu-id="23147-120">O valor a ser depreciado para o novo ativo fixo no primeiro ano é de (8.000 × 18%) ÷ 12 = US$ 120.</span><span class="sxs-lookup"><span data-stu-id="23147-120">The amount to depreciate for the new fixed asset in the first year is (8,000 × 18 percent) ÷ 12 = $120.</span></span>
