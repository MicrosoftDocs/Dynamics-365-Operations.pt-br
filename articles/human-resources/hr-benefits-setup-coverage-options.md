---
title: Criar opções de cobertura
description: ''
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
ms.openlocfilehash: 27b43d858a92beac526ac0fc40b544649ef658b0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008036"
---
# <a name="create-coverage-options"></a><span data-ttu-id="427a0-102">Criar opções de cobertura</span><span class="sxs-lookup"><span data-stu-id="427a0-102">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="427a0-103">As opções de cobertura no Microsoft Dynamics 365 Human Resources são níveis de cobertura para a eleição de um participante em um plano ou programa de benefícios, como Somente Funcionários de um plano médico ou 2x Salário de um plano de seguro de vida.</span><span class="sxs-lookup"><span data-stu-id="427a0-103">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="427a0-104">Depois de definidas, as opções de cobertura de benefícios são reutilizáveis e você pode associar uma opção a um ou mais planos.</span><span class="sxs-lookup"><span data-stu-id="427a0-104">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="427a0-105">Depois da definição das opções de cobertura, anexe as opções de cobertura a um tipo de plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="427a0-105">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="427a0-106">O tipo de plano é então associado a um plano ou programa de benefícios.</span><span class="sxs-lookup"><span data-stu-id="427a0-106">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="427a0-107">As opções de cobertura associadas a um tipo de plano estarão disponíveis para todos os planos criados com esse tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="427a0-107">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="427a0-108">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Opções de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="427a0-108">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="427a0-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="427a0-109">Select **New**.</span></span>

3. <span data-ttu-id="427a0-110">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="427a0-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="427a0-111">Campo</span><span class="sxs-lookup"><span data-stu-id="427a0-111">Field</span></span> | <span data-ttu-id="427a0-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="427a0-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="427a0-113">**Opção de cobertura**</span><span class="sxs-lookup"><span data-stu-id="427a0-113">**Coverage option**</span></span> | <span data-ttu-id="427a0-114">Um nome de opção de cobertura exclusivo.</span><span class="sxs-lookup"><span data-stu-id="427a0-114">A unique coverage option name.</span></span> |
   | <span data-ttu-id="427a0-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="427a0-115">**Description**</span></span> | <span data-ttu-id="427a0-116">Uma descrição da opção de cobertura.</span><span class="sxs-lookup"><span data-stu-id="427a0-116">A description of the coverage option.</span></span> |
   | <span data-ttu-id="427a0-117">**Código de cobertura**</span><span class="sxs-lookup"><span data-stu-id="427a0-117">**Coverage code**</span></span> | <span data-ttu-id="427a0-118">Os códigos de cobertura atribuem valores mínimos e máximos para cada tipo de pessoa coberta elegível.</span><span class="sxs-lookup"><span data-stu-id="427a0-118">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="427a0-119">Um código de cobertura indica quem está coberto ou o valor da cobertura permitida para um tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="427a0-119">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="427a0-120">É possível expressar o valor da cobertura como um valor em dólar ou uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="427a0-120">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="427a0-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="427a0-121">For example:</span></span></br></br><span data-ttu-id="427a0-122">- **Emp+1** – para ser qualificado, o funcionário deve ter um dependente selecionado (se mais de um for selecionado, a qualificação não será possível).</span><span class="sxs-lookup"><span data-stu-id="427a0-122">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="427a0-123">- **Emp+family** – para ser qualificado, o funcionário deve ter pelo menos dois dependentes selecionados.</span><span class="sxs-lookup"><span data-stu-id="427a0-123">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="427a0-124">**Número máximo**</span><span class="sxs-lookup"><span data-stu-id="427a0-124">**Maximum number**</span></span> | <span data-ttu-id="427a0-125">O número máximo de dependentes.</span><span class="sxs-lookup"><span data-stu-id="427a0-125">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="427a0-126">**Status**</span><span class="sxs-lookup"><span data-stu-id="427a0-126">**Status**</span></span> | <span data-ttu-id="427a0-127">O status da opção de cobertura.</span><span class="sxs-lookup"><span data-stu-id="427a0-127">The status of the coverage option.</span></span> <span data-ttu-id="427a0-128">Se o status da opção Cobertura estiver definido como Inativo, a opção Cobertura não poderá ser selecionada nos tipos de plano.</span><span class="sxs-lookup"><span data-stu-id="427a0-128">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="427a0-129">**Porcentagem**</span><span class="sxs-lookup"><span data-stu-id="427a0-129">**Percent**</span></span> | <span data-ttu-id="427a0-130">O valor percentual.</span><span class="sxs-lookup"><span data-stu-id="427a0-130">The percent amount.</span></span> <span data-ttu-id="427a0-131">Este campo estará ativo apenas se %x Salário tiver sido selecionado no campo Código de cobertura.</span><span class="sxs-lookup"><span data-stu-id="427a0-131">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="427a0-132">**Divisor**</span><span class="sxs-lookup"><span data-stu-id="427a0-132">**Divisor**</span></span> | <span data-ttu-id="427a0-133">O divisor a ser usado no cálculo quando você seleciona o código de cobertura %x Salário.</span><span class="sxs-lookup"><span data-stu-id="427a0-133">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="427a0-134">**Porcentagem mínima**</span><span class="sxs-lookup"><span data-stu-id="427a0-134">**Percent minimum**</span></span> | <span data-ttu-id="427a0-135">A porcentagem mínima quando você seleciona o código de cobertura Porcentagem.</span><span class="sxs-lookup"><span data-stu-id="427a0-135">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="427a0-136">**Porcentagem máxima**</span><span class="sxs-lookup"><span data-stu-id="427a0-136">**Percent maximum**</span></span> | <span data-ttu-id="427a0-137">A porcentagem máximo quando você seleciona o código de cobertura Porcentagem.</span><span class="sxs-lookup"><span data-stu-id="427a0-137">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="427a0-138">Em **Opções de qualificação para contato pessoal**, anexe a opção de qualificação para contato pessoal apropriada a cada opção de cobertura.</span><span class="sxs-lookup"><span data-stu-id="427a0-138">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="427a0-139">Em **Autoatendimento**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="427a0-139">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="427a0-140">Campo</span><span class="sxs-lookup"><span data-stu-id="427a0-140">Field</span></span> | <span data-ttu-id="427a0-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="427a0-141">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="427a0-142">**Permitir valor de contribuição do funcionário**</span><span class="sxs-lookup"><span data-stu-id="427a0-142">**Allow employee contribution amount**</span></span> | <span data-ttu-id="427a0-143">Especifica se os funcionários devem modificar o valor da contribuição no autoatendimento de benefícios quando selecionam benefícios.</span><span class="sxs-lookup"><span data-stu-id="427a0-143">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="427a0-144">Se você marcar esta caixa de seleção, o sistema calculará os parâmetros do plano de benefícios com base no valor da contribuição que o empregado insere no autoatendimento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="427a0-144">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="427a0-145">**Permitir valor de cobertura do funcionário**</span><span class="sxs-lookup"><span data-stu-id="427a0-145">**Allow employee coverage amount**</span></span> | <span data-ttu-id="427a0-146">Especifica se os funcionários devem modificar o valor da cobertura no autoatendimento de benefícios quando selecionam benefícios.</span><span class="sxs-lookup"><span data-stu-id="427a0-146">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="427a0-147">Se você marcar esta caixa de seleção, o sistema calculará os parâmetros do plano de benefícios com base no valor da cobertura que o empregado insere no autoatendimento para funcionários.</span><span class="sxs-lookup"><span data-stu-id="427a0-147">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="427a0-148">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="427a0-148">Select **Save**.</span></span> 
