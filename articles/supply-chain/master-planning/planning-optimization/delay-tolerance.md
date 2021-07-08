---
title: Tolerância de atraso (dias negativos)
description: Este tópico fornece informações sobre o cálculo de tolerância de atraso e como ele afeta a criação de ordens planejadas na Otimização de Planejamento.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 748e047e89747f2eabccc04a40c79bcb1e6f3dea
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306454"
---
# <a name="delay-tolerance-negative-days"></a><span data-ttu-id="7609f-103">Tolerância de atraso (dias negativos)</span><span class="sxs-lookup"><span data-stu-id="7609f-103">Delay tolerance (negative days)</span></span>

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="7609f-104">A funcionalidade de tolerância ao atraso permite que a Otimização de Planejamento considere o valor **Dias negativos** definido para grupos de cobertura.</span><span class="sxs-lookup"><span data-stu-id="7609f-104">The delay tolerance functionality enables Planning Optimization to consider the **Negative days** value that is set for coverage groups.</span></span> <span data-ttu-id="7609f-105">Ela é usada para estender o período de tolerância de atraso que é aplicado durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="7609f-105">It's used to extend the delay tolerance period that is applied during master planning.</span></span> <span data-ttu-id="7609f-106">Desta forma, você pode evitar a criação de novas ordens de suprimento se a oferta existente for capaz de cobrir a demanda após um curto atraso.</span><span class="sxs-lookup"><span data-stu-id="7609f-106">In this way, you can avoid creating new supply orders if existing supply will be able to cover the demand after a short delay.</span></span> <span data-ttu-id="7609f-107">O objetivo da funcionalidade é determinar se faz sentido criar uma nova ordem de suprimento para uma determinada demanda.</span><span class="sxs-lookup"><span data-stu-id="7609f-107">The purpose of the functionality is to determine whether it makes sense to create a new supply order for a given demand.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="7609f-108">Ative o recurso no seu sistema</span><span class="sxs-lookup"><span data-stu-id="7609f-108">Turn on the feature in your system</span></span>

<span data-ttu-id="7609f-109">Para disponibilizar a funcionalidade de tolerância de atraso no sistema, acesse [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Dias negativos para Otimização de Planejamento*.</span><span class="sxs-lookup"><span data-stu-id="7609f-109">To make the delay tolerance functionality available in your system, go to [Feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Negative days for Planning Optimization* feature.</span></span>

## <a name="delay-tolerance-in-planning-optimization"></a><span data-ttu-id="7609f-110">Tolerância de atraso na Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="7609f-110">Delay tolerance in Planning Optimization</span></span>

<span data-ttu-id="7609f-111">A tolerância de atraso representa o número de dias fora do prazo que você está disposto a esperar antes de encomendar um novo reabastecimento quando a oferta existente já está planejada.</span><span class="sxs-lookup"><span data-stu-id="7609f-111">Delay tolerance represents the number of days beyond the lead time that you're willing to wait before you order new replenishment when existing supply is already planned.</span></span> <span data-ttu-id="7609f-112">A tolerância de atraso é definida usando dias corridos, e não dias úteis.</span><span class="sxs-lookup"><span data-stu-id="7609f-112">Delay tolerance is defined by using calendar days, not business days.</span></span>

<span data-ttu-id="7609f-113">No momento do planejamento mestre, quando o sistema calcula a tolerância de atraso, ele considera a configuração **Dias negativos**.</span><span class="sxs-lookup"><span data-stu-id="7609f-113">At the time of master planning, when the system calculates the delay tolerance, it considers the **Negative days** setting.</span></span> <span data-ttu-id="7609f-114">Você pode definir o valor de **Dias negativos** nas páginas **Grupos de cobertura** ou **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="7609f-114">You can set the **Negative days** value on either the **Coverage groups** page or the **Item coverage** page.</span></span>

<span data-ttu-id="7609f-115">O sistema vincula o cálculo de tolerância de atraso à *data de reabastecimento mais antiga*, que equivale à data de hoje mais o tempo de início.</span><span class="sxs-lookup"><span data-stu-id="7609f-115">The system links the delay tolerance calculation to the *earliest replenishment date*, which equals today's date plus the lead time.</span></span> <span data-ttu-id="7609f-116">A tolerância de atraso é calculada usando a seguinte fórmula, na qual *max()* encontra o maior de dois valores:</span><span class="sxs-lookup"><span data-stu-id="7609f-116">The delay tolerance is calculated by using following formula, where *max()* finds the larger of two values:</span></span>

<span data-ttu-id="7609f-117">*max (Data de reabastecimento mais antiga, data de conclusão da demanda)* – *Data de conclusão da demanda* + *Dias negativos*</span><span class="sxs-lookup"><span data-stu-id="7609f-117">*max(Earliest replenishment date, Demand due date)* – *Demand due date* + *Negative days*</span></span>

<span data-ttu-id="7609f-118">Esta fórmula garante que o planejamento mestre não crie novas ordens de suprimento quando existir suprimento suficiente durante o prazo do produto.</span><span class="sxs-lookup"><span data-stu-id="7609f-118">This formula ensures that master planning doesn't create new supply orders when enough supply exists during the product lead time.</span></span>

> [!NOTE]
> <span data-ttu-id="7609f-119">O cálculo de tolerância de atraso na Otimização de Planejamento sempre utiliza o cálculo dinâmico de dias negativos do planejamento mestre incorporado.</span><span class="sxs-lookup"><span data-stu-id="7609f-119">The delay tolerance calculation in Planning Optimization always uses the dynamic negative days calculation from built-in master planning.</span></span> <span data-ttu-id="7609f-120">A configuração **Usar dias negativos dinâmicos** na página **Parâmetros de planejamento Mestre não tem efeito** sobre esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="7609f-120">The **Use dynamic negative days** setting on the **Master planning parameters** page has no effect on this behavior.</span></span>

<span data-ttu-id="7609f-121">Se a oferta existente implicar um atraso de demanda menor ou igual à tolerância de atraso calculada, a Otimização de Planejamento associará a oferta existente com a demanda.</span><span class="sxs-lookup"><span data-stu-id="7609f-121">If the existing supply implies a demand delay that is less than or equal to the calculated delay tolerance, Planning Optimization pegs existing supply with the demand.</span></span> <span data-ttu-id="7609f-122">Em alguns casos, é melhor atrasar a demanda do que acabar com o excesso de oferta.</span><span class="sxs-lookup"><span data-stu-id="7609f-122">In some cases, it's better to delay the demand than to end up with oversupply.</span></span>

<span data-ttu-id="7609f-123">As seguintes subseções fornecem exemplos que mostram como a tolerância de atraso afeta a criação de ordens planejadas na Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="7609f-123">The following subsections provide examples that show how delay tolerance affects the creation of planned orders in Planning Optimization.</span></span>

### <a name="example-1"></a><span data-ttu-id="7609f-124">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="7609f-124">Example 1</span></span>

<span data-ttu-id="7609f-125">Um produto tem a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="7609f-125">A product has the following configuration:</span></span>

- <span data-ttu-id="7609f-126">**Prazo:** *10*</span><span class="sxs-lookup"><span data-stu-id="7609f-126">**Lead time:** *10*</span></span>
- <span data-ttu-id="7609f-127">**Dias negativos:** *2*</span><span class="sxs-lookup"><span data-stu-id="7609f-127">**Negative days:** *2*</span></span>

<span data-ttu-id="7609f-128">Existem a seguinte oferta e demanda para o produto:</span><span class="sxs-lookup"><span data-stu-id="7609f-128">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="7609f-129">**Demanda para hoje:** Uma ordem de vendas para uma quantidade de 10</span><span class="sxs-lookup"><span data-stu-id="7609f-129">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="7609f-130">**Suprimento em 12 dias:** Uma ordem de compra para uma quantidade de 10</span><span class="sxs-lookup"><span data-stu-id="7609f-130">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="7609f-131">A oferta existente pode cobrir a demanda dentro de 12 dias, e esse período é igual à tolerância de atraso.</span><span class="sxs-lookup"><span data-stu-id="7609f-131">Existing supply can cover the demand within 12 days, and that period equals the delay tolerance.</span></span> <span data-ttu-id="7609f-132">Portanto, quando o planejamento mestre é executado, nenhuma ordem planejada é criada.</span><span class="sxs-lookup"><span data-stu-id="7609f-132">Therefore, when master planning runs, no planned orders are created.</span></span>

### <a name="example-2"></a><span data-ttu-id="7609f-133">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="7609f-133">Example 2</span></span>

<span data-ttu-id="7609f-134">Um produto tem a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="7609f-134">A product has the following configuration:</span></span>

- <span data-ttu-id="7609f-135">**Prazo:** *10*</span><span class="sxs-lookup"><span data-stu-id="7609f-135">**Lead time:** *10*</span></span>
- <span data-ttu-id="7609f-136">**Dias negativos:** *0*</span><span class="sxs-lookup"><span data-stu-id="7609f-136">**Negative days:** *0*</span></span>

<span data-ttu-id="7609f-137">Existem a seguinte oferta e demanda para o produto:</span><span class="sxs-lookup"><span data-stu-id="7609f-137">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="7609f-138">**Demanda para hoje:** Uma ordem de vendas para uma quantidade de 10</span><span class="sxs-lookup"><span data-stu-id="7609f-138">**Demand for today:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="7609f-139">**Suprimento em 12 dias:** Uma ordem de compra para uma quantidade de 10</span><span class="sxs-lookup"><span data-stu-id="7609f-139">**Supply in 12 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="7609f-140">A oferta existente só pode cobrir a demanda após 12 dias.</span><span class="sxs-lookup"><span data-stu-id="7609f-140">Existing supply can cover the demand only after 12 days.</span></span> <span data-ttu-id="7609f-141">No entanto, a tolerância de atraso é de 10 dias.</span><span class="sxs-lookup"><span data-stu-id="7609f-141">However, the delay tolerance is 10 days.</span></span> <span data-ttu-id="7609f-142">Portanto, quando o planejamento mestre é executado, uma ordem planejada para uma quantidade de 10 é criada.</span><span class="sxs-lookup"><span data-stu-id="7609f-142">Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>

### <a name="example-3"></a><span data-ttu-id="7609f-143">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="7609f-143">Example 3</span></span>

<span data-ttu-id="7609f-144">Um produto tem a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="7609f-144">A product has the following configuration:</span></span>

- <span data-ttu-id="7609f-145">**Prazo:** *10*</span><span class="sxs-lookup"><span data-stu-id="7609f-145">**Lead time:** *10*</span></span>
- <span data-ttu-id="7609f-146">**Dias negativos:** *2*</span><span class="sxs-lookup"><span data-stu-id="7609f-146">**Negative days:** *2*</span></span>

<span data-ttu-id="7609f-147">Existem a seguinte oferta e demanda para o produto:</span><span class="sxs-lookup"><span data-stu-id="7609f-147">The following supply and demand exist for the product:</span></span>

- <span data-ttu-id="7609f-148">**Demanda em 11 dias:** Uma ordem de venda para uma quantidade de 10</span><span class="sxs-lookup"><span data-stu-id="7609f-148">**Demand in 11 days:** A sales order for a quantity of 10</span></span>
- <span data-ttu-id="7609f-149">**Suprimento em 14 dias:** Uma ordem de compra para uma quantidade de 10</span><span class="sxs-lookup"><span data-stu-id="7609f-149">**Supply in 14 days:** A purchase order for a quantity of 10</span></span>

<span data-ttu-id="7609f-150">A oferta existente só pode cobrir a demanda após três dias.</span><span class="sxs-lookup"><span data-stu-id="7609f-150">Existing supply can cover the demand only after three days.</span></span> <span data-ttu-id="7609f-151">No entanto, a tolerância de atraso é de dois dias.</span><span class="sxs-lookup"><span data-stu-id="7609f-151">However, the delay tolerance is two days.</span></span> <span data-ttu-id="7609f-152">(Neste caso, a tolerância de atraso inclui apenas os dois dias negativos.</span><span class="sxs-lookup"><span data-stu-id="7609f-152">(In this case, the delay tolerance includes only the two negative days.</span></span> <span data-ttu-id="7609f-153">A data da demanda não está incluída porque ela é posterior ao prazo do produto.) Portanto, quando o planejamento mestre é executado, uma ordem planejada para uma quantidade de 10 é criada.</span><span class="sxs-lookup"><span data-stu-id="7609f-153">The demand date isn't included because it's after the product lead time.) Therefore, when master planning runs, a planned order for a quantity of 10 is created.</span></span>
