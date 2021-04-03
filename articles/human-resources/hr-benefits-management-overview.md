---
title: Visão geral do Gerenciamento de benefícios
description: Visão geral do recurso de Gerenciamento de benefícios no Dynamics 365 Human Resources. Ofereça opções de benefícios estendidos aos seus funcionários com uma experiência online fácil de usar.
author: andreabichsel
manager: tfehr
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba6623102431eb45bf5d0c96b6583615663d1081
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464317"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="f6eaa-104">Visão geral do Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="f6eaa-104">Benefits management overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f6eaa-105">Para permanecer em um mercado competitivo, é necessário oferecer um conjunto amplo de benefícios para atrair e reter os melhores funcionários.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="f6eaa-106">Além dos benefícios padrão, como plano de saúde e odontológico, ofereça serviços expandidos, como assistência à adoção, programas de recreação e auxílio-vestimenta.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="f6eaa-107">O Gerenciamento de benefícios do Microsoft Dynamics 365 Human Resources oferece uma solução flexível compatível com uma ampla variedade de opções de benefícios.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="f6eaa-108">O Human Resources também inclui uma experiência para funcionários fácil de usar e que mostra as ofertas.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="f6eaa-109">Os planos de benefícios aprimorados permitem criar e gerenciar planos de benefícios exclusivos e oferecem suporte a tabelas de taxas de benefícios complexas e camadas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="f6eaa-110">Você pode facilmente criar programas e pacotes de benefícios, além de regras de inscrição automática nos benefícios para facilitar a experiência dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="f6eaa-111">Os programas de crédito flexível permitem ratear para oferecer suporte à aposentadoria e outros eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="f6eaa-112">As regras de elegibilidade extensivas garantem a disponibilização dos benefícios apropriados para os funcionários certos.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="f6eaa-113">A inscrição online nos benefícios permite uma experiência fácil para os funcionários.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="f6eaa-114">O processamento de eventos de vida útil é compatível com eventos de vida futuros.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="f6eaa-115">Se deseja acessar os dados de demonstração, será necessário implementar novamente o ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="f6eaa-116">Habilitar o Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="f6eaa-116">Enable Benefits management</span></span>

<span data-ttu-id="f6eaa-117">Este tópico descreve como acionar os recursos no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-117">This topic describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="f6eaa-118">Ele também informa quais recursos existentes no Human Resources são substituídos pelo Gerenciamento de benefícios ou quais são desabilitados após ativar o Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-118">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6eaa-119">Depois de habilitar o gerenciamento de benefícios em um ambiente de **Produção** você pode desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-119">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="f6eaa-120">É recomendável habilitar e testar o gerenciamento de benefícios em um ambiente de **Área restrita** antes de ativá-lo em um ambiente de **Produção**.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-120">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="f6eaa-121">Há diferenças significativas entre a funcionalidade de benefício herdada e a nova funcionalidade de gerenciamento de benefícios que exigem configuração adicional e devem ser testadas antes de serem colocadas em produção.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-121">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="f6eaa-122">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="f6eaa-122">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="f6eaa-123">Configurar informações do funcionário</span><span class="sxs-lookup"><span data-stu-id="f6eaa-123">Configure employee information</span></span>

<span data-ttu-id="f6eaa-124">Para poder inscrever funcionários em benefícios, você deve fornecer as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-124">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="f6eaa-125">Você deve registrar um funcionário em um **Plano de compensação fixa** em sua data de início, e você deve selecionar uma **Frequência de pagamento de benefício** em **Detalhes de emprego** no formulário **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-125">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="f6eaa-126">Se você tem um funcionário que recebe remuneração suplementar, como comissões, é possível adicionar um valor de **Salário de benefícios anual** do registro do funcionário.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-126">If you have an employee who receives supplemental compensation like commissions, you can add a **Benefits annual salary** amount from the employee record.</span></span> <span data-ttu-id="f6eaa-127">O Human Resources usará o valor do **Salário de benefícios anual** para determinar valores de cobertura em vez do valor anual da remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-127">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> <span data-ttu-id="f6eaa-128">O **Salário de benefícios anual** deve ser válido a partir da data de início do funcionário ou do início do período de benefício, dos dois o que for mais recente.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-128">The **Benefits annual salary** must be valid as of the employee’s start date or the beginning of the benefit period, whichever is latest.</span></span> <span data-ttu-id="f6eaa-129">Se um valor de salário de benefícios anual e remuneração fixa for registrado para um funcionário, o salário de benefícios anual será usado para determinar os valores de cobertura.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-129">If both a fixed compensation and benefits annual salary amount is recorded for an employee, the benefits annual salary will be used in determining coverage amounts.</span></span>

<span data-ttu-id="f6eaa-130">Quando você cria um plano de benefícios que usa taxas baseadas em sexo ou idade, você deve inserir uma data de nascimento e um sexo para que o funcionário calcule o custo de benefício.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="f6eaa-131">Configurar Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="f6eaa-131">Configure Benefits management</span></span>

<span data-ttu-id="f6eaa-132">Antes de criar os planos de benefícios para seus funcionários, é necessário configurar as opções dos planos.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="f6eaa-133">Definir parâmetros de gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="f6eaa-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="f6eaa-134">Configurar regras e opções de qualificação</span><span class="sxs-lookup"><span data-stu-id="f6eaa-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="f6eaa-135">Configurar opções de qualificação para contato pessoal</span><span class="sxs-lookup"><span data-stu-id="f6eaa-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="f6eaa-136">Criar opções de cobertura</span><span class="sxs-lookup"><span data-stu-id="f6eaa-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="f6eaa-137">Definir frequência de pagamento</span><span class="sxs-lookup"><span data-stu-id="f6eaa-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="f6eaa-138">Configurar tipos de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="f6eaa-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="f6eaa-139">Criar tipos de plano</span><span class="sxs-lookup"><span data-stu-id="f6eaa-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="f6eaa-140">Configurar códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="f6eaa-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="f6eaa-141">Configurar códigos de camada</span><span class="sxs-lookup"><span data-stu-id="f6eaa-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="f6eaa-142">Configurar taxas</span><span class="sxs-lookup"><span data-stu-id="f6eaa-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="f6eaa-143">Configurar deduções</span><span class="sxs-lookup"><span data-stu-id="f6eaa-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="f6eaa-144">Configurar dias de espera</span><span class="sxs-lookup"><span data-stu-id="f6eaa-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="f6eaa-145">Configurar períodos de espera</span><span class="sxs-lookup"><span data-stu-id="f6eaa-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="f6eaa-146">Configurar regras de arredondamento</span><span class="sxs-lookup"><span data-stu-id="f6eaa-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="f6eaa-147">Criar categorias de emprego</span><span class="sxs-lookup"><span data-stu-id="f6eaa-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="f6eaa-148">Configurar tipos de emprego</span><span class="sxs-lookup"><span data-stu-id="f6eaa-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="f6eaa-149">Configurar autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="f6eaa-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="f6eaa-150">Criar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="f6eaa-150">Create benefit plans</span></span>

<span data-ttu-id="f6eaa-151">Esses artigos mostram como criar planos de benefícios, incluindo pacotes e programas de crédito flexível.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="f6eaa-152">Configurar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="f6eaa-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="f6eaa-153">Configurar programas de crédito flexível</span><span class="sxs-lookup"><span data-stu-id="f6eaa-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="f6eaa-154">Processar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="f6eaa-154">Process benefit plans</span></span>

<span data-ttu-id="f6eaa-155">É necessário processar algumas alterações para ativá-las.</span><span class="sxs-lookup"><span data-stu-id="f6eaa-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="f6eaa-156">Processar qualificação da inscrição</span><span class="sxs-lookup"><span data-stu-id="f6eaa-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="f6eaa-157">Processar eventos de vida</span><span class="sxs-lookup"><span data-stu-id="f6eaa-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="f6eaa-158">Processar alterações de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="f6eaa-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="f6eaa-159">Processar qualificação para eventos de vida</span><span class="sxs-lookup"><span data-stu-id="f6eaa-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="f6eaa-160">Processar alterações de taxa</span><span class="sxs-lookup"><span data-stu-id="f6eaa-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]