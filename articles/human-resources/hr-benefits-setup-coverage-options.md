---
title: Criar opções de cobertura
description: As opções de cobertura no Microsoft Dynamics 365 Human Resources são níveis de cobertura para a eleição de um participante em um plano ou programa de benefícios, como Somente Funcionários de um plano médico ou 2x Salário de um plano de seguro de vida.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 0af2b6ae0853b4c7f64c4d4f04299c87089d622b
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092697"
---
# <a name="create-coverage-options"></a><span data-ttu-id="c8005-103">Criar opções de cobertura</span><span class="sxs-lookup"><span data-stu-id="c8005-103">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="c8005-104">As opções de cobertura no Microsoft Dynamics 365 Human Resources são níveis de cobertura para a eleição de um participante em um plano ou programa de benefícios, como Somente Funcionários de um plano médico ou 2x Salário de um plano de seguro de vida.</span><span class="sxs-lookup"><span data-stu-id="c8005-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="c8005-105">Depois de definidas, as opções de cobertura de benefícios são reutilizáveis e você pode associar uma opção a um ou mais planos.</span><span class="sxs-lookup"><span data-stu-id="c8005-105">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="c8005-106">Depois da definição das opções de cobertura, anexe as opções de cobertura a um tipo de plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="c8005-106">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="c8005-107">O tipo de plano é então associado a um plano ou programa de benefícios.</span><span class="sxs-lookup"><span data-stu-id="c8005-107">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="c8005-108">As opções de cobertura associadas a um tipo de plano estarão disponíveis para todos os planos criados com esse tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="c8005-108">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="c8005-109">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Opções de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="c8005-109">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="c8005-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c8005-110">Select **New**.</span></span>

3. <span data-ttu-id="c8005-111">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="c8005-111">Specify values for the following fields:</span></span>

   | <span data-ttu-id="c8005-112">Campo</span><span class="sxs-lookup"><span data-stu-id="c8005-112">Field</span></span> | <span data-ttu-id="c8005-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8005-113">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c8005-114">**Opção de cobertura**</span><span class="sxs-lookup"><span data-stu-id="c8005-114">**Coverage option**</span></span> | <span data-ttu-id="c8005-115">Um nome de opção de cobertura exclusivo.</span><span class="sxs-lookup"><span data-stu-id="c8005-115">A unique coverage option name.</span></span> |
   | <span data-ttu-id="c8005-116">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c8005-116">**Description**</span></span> | <span data-ttu-id="c8005-117">Uma descrição da opção de cobertura.</span><span class="sxs-lookup"><span data-stu-id="c8005-117">A description of the coverage option.</span></span> |
   | <span data-ttu-id="c8005-118">**Código de cobertura**</span><span class="sxs-lookup"><span data-stu-id="c8005-118">**Coverage code**</span></span> | <span data-ttu-id="c8005-119">Os códigos de cobertura atribuem valores mínimos e máximos para cada tipo de pessoa coberta elegível.</span><span class="sxs-lookup"><span data-stu-id="c8005-119">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="c8005-120">Um código de cobertura indica quem está coberto ou o valor da cobertura permitida para um tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="c8005-120">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="c8005-121">É possível expressar o valor da cobertura como um valor em dólar ou uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="c8005-121">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="c8005-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c8005-122">For example:</span></span></br></br><span data-ttu-id="c8005-123">- **Emp+1** – para ser qualificado, o funcionário deve ter um dependente selecionado (se mais de um for selecionado, a qualificação não será possível).</span><span class="sxs-lookup"><span data-stu-id="c8005-123">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="c8005-124">- **Emp+family** – para ser qualificado, o funcionário deve ter pelo menos dois dependentes selecionados.</span><span class="sxs-lookup"><span data-stu-id="c8005-124">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="c8005-125">**Número máximo**</span><span class="sxs-lookup"><span data-stu-id="c8005-125">**Maximum number**</span></span> | <span data-ttu-id="c8005-126">O número máximo de dependentes.</span><span class="sxs-lookup"><span data-stu-id="c8005-126">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="c8005-127">**Status**</span><span class="sxs-lookup"><span data-stu-id="c8005-127">**Status**</span></span> | <span data-ttu-id="c8005-128">O status da opção de cobertura.</span><span class="sxs-lookup"><span data-stu-id="c8005-128">The status of the coverage option.</span></span> <span data-ttu-id="c8005-129">Se o status da opção Cobertura estiver definido como Inativo, a opção Cobertura não poderá ser selecionada nos tipos de plano.</span><span class="sxs-lookup"><span data-stu-id="c8005-129">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="c8005-130">**Porcentagem**</span><span class="sxs-lookup"><span data-stu-id="c8005-130">**Percent**</span></span> | <span data-ttu-id="c8005-131">O valor percentual.</span><span class="sxs-lookup"><span data-stu-id="c8005-131">The percent amount.</span></span> <span data-ttu-id="c8005-132">Este campo estará ativo apenas se %x Salário tiver sido selecionado no campo Código de cobertura.</span><span class="sxs-lookup"><span data-stu-id="c8005-132">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="c8005-133">**Divisor**</span><span class="sxs-lookup"><span data-stu-id="c8005-133">**Divisor**</span></span> | <span data-ttu-id="c8005-134">O divisor a ser usado no cálculo quando você seleciona o código de cobertura %x Salário.</span><span class="sxs-lookup"><span data-stu-id="c8005-134">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="c8005-135">**Porcentagem mínima**</span><span class="sxs-lookup"><span data-stu-id="c8005-135">**Percent minimum**</span></span> | <span data-ttu-id="c8005-136">A porcentagem mínima quando você seleciona o código de cobertura Porcentagem.</span><span class="sxs-lookup"><span data-stu-id="c8005-136">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="c8005-137">**Porcentagem máxima**</span><span class="sxs-lookup"><span data-stu-id="c8005-137">**Percent maximum**</span></span> | <span data-ttu-id="c8005-138">A porcentagem máximo quando você seleciona o código de cobertura Porcentagem.</span><span class="sxs-lookup"><span data-stu-id="c8005-138">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="c8005-139">Em **Opções de qualificação para contato pessoal**, anexe a opção de qualificação para contato pessoal apropriada a cada opção de cobertura.</span><span class="sxs-lookup"><span data-stu-id="c8005-139">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="c8005-140">Em **Autoatendimento**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="c8005-140">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="c8005-141">Campo</span><span class="sxs-lookup"><span data-stu-id="c8005-141">Field</span></span> | <span data-ttu-id="c8005-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="c8005-142">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c8005-143">**Permitir valor de contribuição do funcionário**</span><span class="sxs-lookup"><span data-stu-id="c8005-143">**Allow employee contribution amount**</span></span> | <span data-ttu-id="c8005-144">Especifica se os funcionários devem modificar o valor da contribuição no autoatendimento de benefícios quando selecionam benefícios.</span><span class="sxs-lookup"><span data-stu-id="c8005-144">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="c8005-145">Se você marcar esta caixa de seleção, o sistema calculará os parâmetros do plano de benefícios com base no valor da contribuição que o empregado insere no autoatendimento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="c8005-145">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="c8005-146">**Permitir valor de cobertura do funcionário**</span><span class="sxs-lookup"><span data-stu-id="c8005-146">**Allow employee coverage amount**</span></span> | <span data-ttu-id="c8005-147">Especifica se os funcionários devem modificar o valor da cobertura no autoatendimento de benefícios quando selecionam benefícios.</span><span class="sxs-lookup"><span data-stu-id="c8005-147">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="c8005-148">Se você marcar esta caixa de seleção, o sistema calculará os parâmetros do plano de benefícios com base no valor da cobertura que o empregado insere no autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="c8005-148">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="c8005-149">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8005-149">Select **Save**.</span></span> 
