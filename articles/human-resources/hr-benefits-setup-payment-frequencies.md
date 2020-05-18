---
title: Definir frequência de pagamento
description: O Microsoft Dynamics 365 Human Resources usa frequências de pagamento para calcular o salário anual de benefício, determinar o valor Premium do benefício que um funcionário paga a cada período de pagamento e com qual frequência os fornecedores são pagos.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 74ff97550ee5b47a28ff9815528677b6e685e25b
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229731"
---
# <a name="set-up-payment-frequencies"></a><span data-ttu-id="f26d9-103">Definir frequência de pagamento</span><span class="sxs-lookup"><span data-stu-id="f26d9-103">Set up payment frequencies</span></span>

<span data-ttu-id="f26d9-104">O Microsoft Dynamics 365 Human Resources usa frequências de pagamento para calcular o salário anual de benefício, determinar o valor Premium do benefício que um funcionário paga a cada período de pagamento e com qual frequência os fornecedores são pagos.</span><span class="sxs-lookup"><span data-stu-id="f26d9-104">Microsoft Dynamics 365 Human Resources uses payment frequencies to calculate the annual benefit salary, determine the benefit premium amount an employee pays each pay period, and how often providers are paid.</span></span>

<span data-ttu-id="f26d9-105">As frequências de pagamento de benefício usam os fatores de conversão para converter os períodos de pagamento de benefício entre frequências mensais, quinzenais, semanais e diárias.</span><span class="sxs-lookup"><span data-stu-id="f26d9-105">Benefit payment frequencies use conversion factors to convert benefit payment periods between monthly, semi-monthly, biweekly, weekly, and daily payment frequencies.</span></span> <span data-ttu-id="f26d9-106">Isso permite que as empresas definam a interdependência entre as frequências de pagamento em um plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="f26d9-106">This allows companies to define the interdependence between the payment frequencies within a benefit plan.</span></span>

<span data-ttu-id="f26d9-107">Os campos de fatores de conversão identificam o fator de conversão da frequência de pagamento para os períodos de pagamento padrão e permitem que o sistema faça cálculos entre frequências de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-107">The conversion factors fields identify the conversion factor from the payment frequency to the standard payment periods and allow the system to do calculations between payment frequencies.</span></span> <span data-ttu-id="f26d9-108">O valor do fator de conversão também determina o valor Premium do benefício que um funcionário deve pagar a cada frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-108">The conversion factor amount also determines the benefit premium amount that an employee should pay each pay frequency.</span></span>

1. <span data-ttu-id="f26d9-109">No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Frequências de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="f26d9-109">In the **Benefits management** workspace, under **Setup**, select **Payment frequencies**.</span></span>

2. <span data-ttu-id="f26d9-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f26d9-110">Select **New**.</span></span>

3. <span data-ttu-id="f26d9-111">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="f26d9-111">Specify values for the following fields:</span></span>

   | <span data-ttu-id="f26d9-112">Campo</span><span class="sxs-lookup"><span data-stu-id="f26d9-112">Field</span></span> | <span data-ttu-id="f26d9-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f26d9-113">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="f26d9-114">**Frequência de pagamento**</span><span class="sxs-lookup"><span data-stu-id="f26d9-114">**Payment frequency**</span></span> | <span data-ttu-id="f26d9-115">Um nome exclusivo da frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-115">A unique payment frequency name.</span></span> |
   | <span data-ttu-id="f26d9-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f26d9-116">**Description**</span></span> | <span data-ttu-id="f26d9-117">Uma descrição da frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-117">A description of the payment frequency.</span></span> |
   | <span data-ttu-id="f26d9-118">**Período**</span><span class="sxs-lookup"><span data-stu-id="f26d9-118">**Period**</span></span> | <span data-ttu-id="f26d9-119">O período apropriado que melhor corresponde ao provedor de benefícios e à frequência de pagamento do funcionário.</span><span class="sxs-lookup"><span data-stu-id="f26d9-119">The appropriate period that best matches the benefit provider’s and employee’s payment frequency.</span></span> <span data-ttu-id="f26d9-120">A lista de períodos é composta pelos períodos de pagamento padrão.</span><span class="sxs-lookup"><span data-stu-id="f26d9-120">The period list is composed of the standard payment periods.</span></span> |
   | <span data-ttu-id="f26d9-121">**Número de períodos de pagamento**</span><span class="sxs-lookup"><span data-stu-id="f26d9-121">**Number of pay periods**</span></span> | <span data-ttu-id="f26d9-122">O número de períodos de pagamento que representam a frequência com que os funcionários ou o fornecedor de benefícios são pagos.</span><span class="sxs-lookup"><span data-stu-id="f26d9-122">The number of pay periods that represents how often the benefit provider or employees are paid.</span></span> <span data-ttu-id="f26d9-123">Esse valor será usado para calcular o valor do salário do benefício anual do funcionário.</span><span class="sxs-lookup"><span data-stu-id="f26d9-123">This amount will be used to calculate the employee‘s annual benefit salary amount.</span></span> |
   | <span data-ttu-id="f26d9-124">**Fator de Conversão Anual**</span><span class="sxs-lookup"><span data-stu-id="f26d9-124">**Annual conversion factor**</span></span> | <span data-ttu-id="f26d9-125">O fator de conversão anual para a frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-125">The annual conversion factor for the payment frequency.</span></span> <span data-ttu-id="f26d9-126">Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é:</span><span class="sxs-lookup"><span data-stu-id="f26d9-126">For example, the annual conversion factor for the monthly pay frequency is:</span></span> </br></br><span data-ttu-id="f26d9-127">(12 pagamentos mensais/1 ano) = 12</span><span class="sxs-lookup"><span data-stu-id="f26d9-127">(12 monthly payments / 1 year) = 12</span></span> |
   | <span data-ttu-id="f26d9-128">**Fator de conversão semestral**</span><span class="sxs-lookup"><span data-stu-id="f26d9-128">**Semiannual conversion factor**</span></span> | <span data-ttu-id="f26d9-129">O fator de conversão semestral para a frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-129">The semiannual conversion factor for the payment frequency.</span></span> <span data-ttu-id="f26d9-130">Por exemplo, o fator de conversão semestral para a frequência de pagamento mensal é:</span><span class="sxs-lookup"><span data-stu-id="f26d9-130">For example, the semiannual conversion factor for the monthly pay frequency is:</span></span> </br></br><span data-ttu-id="f26d9-131">(12 pagamentos mensais / 2 vezes ao ano) = 6</span><span class="sxs-lookup"><span data-stu-id="f26d9-131">(12 monthly payments / 2 times a year) = 6</span></span> |
   | <span data-ttu-id="f26d9-132">**Fator de conversão trimestral**</span><span class="sxs-lookup"><span data-stu-id="f26d9-132">**Quarterly conversion factor**</span></span> | <span data-ttu-id="f26d9-133">O fator de conversão trimestral para a frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-133">The quarterly conversion factor for the payment frequency.</span></span> <span data-ttu-id="f26d9-134">Por exemplo, o fator de conversão trimestral para a frequência de pagamento mensal é:</span><span class="sxs-lookup"><span data-stu-id="f26d9-134">For example, the quarterly conversion factor for the monthly pay frequency is:</span></span> </br></br><span data-ttu-id="f26d9-135">(12 pagamentos mensais por 4 trimestres) = 3</span><span class="sxs-lookup"><span data-stu-id="f26d9-135">(12 monthly payments / 4 quarters) = 3</span></span> |
   | <span data-ttu-id="f26d9-136">**Fator de conversão mensal**</span><span class="sxs-lookup"><span data-stu-id="f26d9-136">**Monthly conversion factor**</span></span> | <span data-ttu-id="f26d9-137">O fator de conversão mensal para a frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-137">The monthly conversion factor for the payment frequency.</span></span> <span data-ttu-id="f26d9-138">Por exemplo, o fator de conversão mensal para a frequência de pagamento mensal é:</span><span class="sxs-lookup"><span data-stu-id="f26d9-138">For example, the monthly conversion factor for the monthly pay frequency is:</span></span> </br></br><span data-ttu-id="f26d9-139">(12 pagamentos mensais / 12 meses) = 1</span><span class="sxs-lookup"><span data-stu-id="f26d9-139">(12 monthly payments / 12 months) = 1</span></span> |
   | <span data-ttu-id="f26d9-140">**Fator de conversão quinzenal**</span><span class="sxs-lookup"><span data-stu-id="f26d9-140">**Semimonthly conversion factor**</span></span> | <span data-ttu-id="f26d9-141">O fator de conversão quinzenal para a frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-141">The semimonthly conversion factor for the payment frequency.</span></span> <span data-ttu-id="f26d9-142">Por exemplo, o fator de conversão quinzenal para a frequência de pagamento mensal é:</span><span class="sxs-lookup"><span data-stu-id="f26d9-142">For example, the semimonthly conversion factor for the monthly pay frequency is:</span></span> </br></br><span data-ttu-id="f26d9-143">(12 pagamentos mensais / 24 (2x ao mês)) = 0,5</span><span class="sxs-lookup"><span data-stu-id="f26d9-143">(12 monthly payments / 24 (2x a month)) = 0.5</span></span> | 
   | <span data-ttu-id="f26d9-144">**Fator de conversão quinzenal**</span><span class="sxs-lookup"><span data-stu-id="f26d9-144">**Biweekly conversion factor**</span></span> | <span data-ttu-id="f26d9-145">O fator de conversão anual para a frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-145">The annual conversion factor for the payment frequency.</span></span> <span data-ttu-id="f26d9-146">Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é:</span><span class="sxs-lookup"><span data-stu-id="f26d9-146">For example, the annual conversion factor for the monthly pay frequency is:</span></span> </br></br><span data-ttu-id="f26d9-147">(12 pagamentos mensais / 26 semanas) = 0,461538</span><span class="sxs-lookup"><span data-stu-id="f26d9-147">(12 monthly payments / 26 weeks) = 0.461538</span></span> |
   | <span data-ttu-id="f26d9-148">**Fator de conversão semanal**</span><span class="sxs-lookup"><span data-stu-id="f26d9-148">**Weekly conversion factor**</span></span> | <span data-ttu-id="f26d9-149">O fator de conversão anual para a frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-149">The annual conversion factor for the payment frequency.</span></span> <span data-ttu-id="f26d9-150">Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é:</span><span class="sxs-lookup"><span data-stu-id="f26d9-150">For example, the annual conversion factor for the monthly pay frequency is:</span></span> </br></br><span data-ttu-id="f26d9-151">(12 pagamentos mensais / 52 semanas) = 0,230769</span><span class="sxs-lookup"><span data-stu-id="f26d9-151">(12 monthly payments / 52 weeks) = 0.230769</span></span> |
   | <span data-ttu-id="f26d9-152">**Fator de conversão diário**</span><span class="sxs-lookup"><span data-stu-id="f26d9-152">**Daily conversion factor**</span></span> | <span data-ttu-id="f26d9-153">O fator de conversão anual para a frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-153">The annual conversion factor for the payment frequency.</span></span> <span data-ttu-id="f26d9-154">Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é:</span><span class="sxs-lookup"><span data-stu-id="f26d9-154">For example, the annual conversion factor for the monthly pay frequency is:</span></span> </br></br><span data-ttu-id="f26d9-155">(12 pagamentos mensais / 365 dias) = 0,032877</span><span class="sxs-lookup"><span data-stu-id="f26d9-155">(12 monthly payments / 365 days) = 0.032877</span></span> |
   | <span data-ttu-id="f26d9-156">**Fator de conversão por hora**</span><span class="sxs-lookup"><span data-stu-id="f26d9-156">**Hourly conversion factor**</span></span> | <span data-ttu-id="f26d9-157">O fator de conversão anual para a frequência de pagamento.</span><span class="sxs-lookup"><span data-stu-id="f26d9-157">The annual conversion factor for the payment frequency.</span></span> <span data-ttu-id="f26d9-158">Por exemplo, o fator de conversão anual para a frequência de pagamento mensal é:</span><span class="sxs-lookup"><span data-stu-id="f26d9-158">For example, the annual conversion factor for the monthly pay frequency is:</span></span> </br></br><span data-ttu-id="f26d9-159">(12 pagamentos mensais / 2080 horas) = 0,005769</span><span class="sxs-lookup"><span data-stu-id="f26d9-159">(12 monthly payments / 2080 hours) = 0.005769</span></span>

4. <span data-ttu-id="f26d9-160">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f26d9-160">Select **Save**.</span></span> 