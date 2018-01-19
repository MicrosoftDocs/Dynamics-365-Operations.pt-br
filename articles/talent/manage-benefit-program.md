---
title: "Definir e gerenciar um programa de benefícios"
description: "O RH fornece um conjunto de ferramentas que podem ser usadas para configurar e manter benefícios, deduções e planos de compensação de trabalhadores que uma empresa oferece ou processa para os trabalhadores. Este artigo fornece informações sobre como configurar e gerenciar benefícios."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 3097bd52377a6c431cef6344a6b504fda9f85550
ms.contentlocale: pt-br
ms.lasthandoff: 01/19/2018

---

# <a name="define-and-manage-a-benefits-program"></a><span data-ttu-id="387c2-104">Definir e gerenciar um programa de benefícios</span><span class="sxs-lookup"><span data-stu-id="387c2-104">Define and manage a benefits program</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="387c2-105">O RH fornece um conjunto de ferramentas que podem ser usadas para configurar e manter benefícios, deduções e planos de compensação de trabalhadores que uma empresa oferece ou processa para os trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="387c2-105">Human resources provides a set of tools that can be used to set up and maintain benefits, deductions, and workers' compensation plans that an organization offers or processes for its workers.</span></span> <span data-ttu-id="387c2-106">Este tópico fornece informações sobre como configurar e gerenciar benefícios.</span><span class="sxs-lookup"><span data-stu-id="387c2-106">This topic provides information about how to set up and manage benefits.</span></span>

<a name="benefit-setup"></a><span data-ttu-id="387c2-107">Configuração de benefício</span><span class="sxs-lookup"><span data-stu-id="387c2-107">Benefit setup</span></span>
-------------

<span data-ttu-id="387c2-108">Para que os trabalhadores sejam inscritos nos benefícios, você deve criar os elementos de cada benefício.</span><span class="sxs-lookup"><span data-stu-id="387c2-108">Before workers can be enrolled in benefits, you must create the elements of each benefit.</span></span> <span data-ttu-id="387c2-109">Esses elementos combinam planos de benefícios semelhantes e definem as configurações padrão, como taxas de dedução e detalhes da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="387c2-109">These elements combine similar benefit plans and define default settings, such as deduction rates and accounting details.</span></span> <span data-ttu-id="387c2-110">Muitas dessas configurações podem ser ajustadas quando os trabalhadores são inscritos posteriormente no benefício.</span><span class="sxs-lookup"><span data-stu-id="387c2-110">Many of these settings can be adjusted when workers are later enrolled in the benefit.</span></span> <span data-ttu-id="387c2-111">Para cada plano de benefícios, uma organização pode oferecer várias opções de inscrição, ou um trabalhador pode cancelar a inscrição no plano.</span><span class="sxs-lookup"><span data-stu-id="387c2-111">For each benefit plan, an organization can offer several enrollment options, or a worker can waive enrollment in the plan.</span></span> 

<span data-ttu-id="387c2-112">[![Fluxo do processo de benefício](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span><span class="sxs-lookup"><span data-stu-id="387c2-112">[![Benefit process flow](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)</span></span>

## <a name="benefit-elements"></a><span data-ttu-id="387c2-113">Elementos do benefício</span><span class="sxs-lookup"><span data-stu-id="387c2-113">Benefit elements</span></span>
<span data-ttu-id="387c2-114">Antes de começar a criar benefícios e inscrever trabalhadores neles, você deve definir os elementos que constituem um benefício: o tipo, o plano e as opções.</span><span class="sxs-lookup"><span data-stu-id="387c2-114">Before you begin to create to create benefits and enroll workers in them, you must define the elements that make up a benefit: the type, plan, and options.</span></span>

-   <span data-ttu-id="387c2-115">**Tipo** – Um conjunto de planos para um benefício específico, como médico ou estacionamento.</span><span class="sxs-lookup"><span data-stu-id="387c2-115">**Type** – A collection of plans for a specific benefit, such as medical or parking.</span></span>
-   <span data-ttu-id="387c2-116">**Plano** – Um benefício específico que é contratado por um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="387c2-116">**Plan** – A specific benefit that is contracted from a provider.</span></span>
-   <span data-ttu-id="387c2-117">**Opção** – O nível de cobertura, como apenas do funcionário, ou do funcionário e do cônjuge/parceiro.</span><span class="sxs-lookup"><span data-stu-id="387c2-117">**Option** – The coverage level, such as employee only, or employee and spouse/partner.</span></span>

<span data-ttu-id="387c2-118">Para cada tipo de benefício, como oftalmológico ou dentário, uma organização pode oferecer um ou mais planos para os trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="387c2-118">For each type of benefit, such as vision or dental, an organization can offer one or more plans to its workers.</span></span> <span data-ttu-id="387c2-119">Para cada plano, a organização pode oferecer opções diferentes.</span><span class="sxs-lookup"><span data-stu-id="387c2-119">For each plan, the organization can offer different options.</span></span> <span data-ttu-id="387c2-120">Por exemplo, os trabalhadores podem comprar cobertura adicional de seguro de vida temporário em uma, duas ou três vezes o salário anual.</span><span class="sxs-lookup"><span data-stu-id="387c2-120">For example, workers can buy additional term life insurance coverage at one, two, or three times their yearly salary.</span></span> <span data-ttu-id="387c2-121">Cada combinação de um plano e opções se torna um benefício no qual os trabalhadores podem se inscrever.</span><span class="sxs-lookup"><span data-stu-id="387c2-121">Each combination of a plan and options becomes a benefit that workers can enroll in.</span></span> 

<span data-ttu-id="387c2-122">[![pic de benefício](./media/benefit-pic.png)](./media/benefit-pic.png)</span><span class="sxs-lookup"><span data-stu-id="387c2-122">[![benefit pic](./media/benefit-pic.png)](./media/benefit-pic.png)</span></span>

## <a name="eligibility"></a><span data-ttu-id="387c2-123">Qualificação</span><span class="sxs-lookup"><span data-stu-id="387c2-123">Eligibility</span></span>
<span data-ttu-id="387c2-124">Muitos fatores determinam a qualificação do trabalhador para os vários tipos de benefícios oferecidos por um empregador.</span><span class="sxs-lookup"><span data-stu-id="387c2-124">Many factors determine worker eligibility for the various types of benefits that an employer offers.</span></span> <span data-ttu-id="387c2-125">Quando você cria um benefício no Microsoft Talent, pode definir o tipo de qualificação que se aplica a esse benefício.</span><span class="sxs-lookup"><span data-stu-id="387c2-125">When you create a benefit in Microsoft Talent, you can set the type of eligibility that applies to that benefit.</span></span> 

<span data-ttu-id="387c2-126">Você pode tornar um benefício disponível a todos os funcionários.</span><span class="sxs-lookup"><span data-stu-id="387c2-126">You can make a benefit available to all workers.</span></span> <span data-ttu-id="387c2-127">Por exemplo, algumas empresas oferecem estacionamento a todos os funcionários como um benefício adicional.</span><span class="sxs-lookup"><span data-stu-id="387c2-127">For example, some companies offer parking passes to all employees as a fringe benefit.</span></span> <span data-ttu-id="387c2-128">Ao criar esse benefício, você define a qualificação como **Todos os trabalhadores estão qualificados**.</span><span class="sxs-lookup"><span data-stu-id="387c2-128">When you create this benefit, you set the eligibility to **All workers are eligible**.</span></span> 

<span data-ttu-id="387c2-129">Para outros benefícios, como consignações e arrecadações de imposto, a qualificação não se aplica.</span><span class="sxs-lookup"><span data-stu-id="387c2-129">For other benefits, such as garnishments and tax levies, eligibility doesn't apply.</span></span> <span data-ttu-id="387c2-130">Ao criar esses tipos de benefícios, você definiu a qualificação para **Ignorar processo de qualificação**.</span><span class="sxs-lookup"><span data-stu-id="387c2-130">Whey you create these types of benefits, you set the eligibility to **Bypass eligibility process**.</span></span> 

<span data-ttu-id="387c2-131">Por fim, a qualificação de benefícios pode ser baseada na regra.</span><span class="sxs-lookup"><span data-stu-id="387c2-131">Finally, benefit eligibility can be rule-based.</span></span> <span data-ttu-id="387c2-132">Por exemplo, uma empresa oferece dois tipos de benefícios de seguro de vida aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="387c2-132">For example, a company offers two types of life insurance benefit to employees.</span></span> <span data-ttu-id="387c2-133">Os funcionários executivos estão qualificados para um plano de seguro de vida, enquanto que todos os funcionários em tempo integral que estão qualificados para outro plano de seguro de vida.</span><span class="sxs-lookup"><span data-stu-id="387c2-133">Executive employees are eligible for one life insurance plan, whereas all other full-time employees are eligible for the other life insurance plan.</span></span> <span data-ttu-id="387c2-134">No Talent, você poderá criar uma regra de qualificação para o benefício para localizar todos os funcionários executivos e outra regra para localizar todos os outros funcionários de tempo integral e, em seguida, aplicar essas regras ao benefício apropriado.</span><span class="sxs-lookup"><span data-stu-id="387c2-134">In Talent, you can create a benefit eligibility rule to find all executive employees and another rule to find all other full-time employees, and then apply those rules to the appropriate benefit.</span></span>

## <a name="enrollment"></a><span data-ttu-id="387c2-135">Inscrição</span><span class="sxs-lookup"><span data-stu-id="387c2-135">Enrollment</span></span>
<span data-ttu-id="387c2-136">Após criar os benefícios oferecidos por sua empresa e determinar a qualificação, você poderá inscrever os trabalhadores em benefícios.</span><span class="sxs-lookup"><span data-stu-id="387c2-136">After you've created the benefits that your organization offers and determined eligibility, you can enroll your workers in benefits.</span></span> <span data-ttu-id="387c2-137">Você pode inscrever um único trabalhador em benefícios, ou pode inscrever vários trabalhadores em um ou mais benefícios durante um único processo.</span><span class="sxs-lookup"><span data-stu-id="387c2-137">You can enroll a single worker in benefits, or you can enroll many workers in one or more benefits during a single process.</span></span> 

<span data-ttu-id="387c2-138">Às vezes, uma organização deixa de oferecer alguns benefícios.</span><span class="sxs-lookup"><span data-stu-id="387c2-138">Sometimes, an organization stops offering certain benefits.</span></span> <span data-ttu-id="387c2-139">Nesse caso, você deve atualizar o benefício e os trabalhadores que estão incluídos nele.</span><span class="sxs-lookup"><span data-stu-id="387c2-139">In this case, you must update the benefit and the workers who are enrolled in.</span></span> <span data-ttu-id="387c2-140">O vencimento de benefício em massa permite que você altere a data de vencimento de um benefício e as inscrições de trabalhadores desse benefício ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="387c2-140">Mass benefit expiration lets you change the expiration date of both a benefit and the worker enrollments for that benefit at the same time.</span></span> <span data-ttu-id="387c2-141">Você também pode selecionar vários trabalhadores inscritos em um benefício e alterar a data final da cobertura.</span><span class="sxs-lookup"><span data-stu-id="387c2-141">You can also select multiple workers who are enrolled in a benefit and change the ending date of their coverage.</span></span> 

<span data-ttu-id="387c2-142">Da mesma forma, a extensão do benefício em massa permite que você estenda a data de vencimento de um benefício e de inscrições de trabalhadores para esse benefício, caso você opte por oferecer um benefício por mais tempo do que planejado originalmente.</span><span class="sxs-lookup"><span data-stu-id="387c2-142">Similarly, mass benefit extension lets you extend the expiration date of both a benefit and the worker enrollments for that benefit if you decide to offer a benefit longer than you originally planned.</span></span>

<a name="see-also"></a><span data-ttu-id="387c2-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="387c2-143">See also</span></span>
--------

[<span data-ttu-id="387c2-144">Políticas de qualificação para benefícios</span><span class="sxs-lookup"><span data-stu-id="387c2-144">Benefit eligibility policies</span></span>](benefit-eligibility-policies.md)




