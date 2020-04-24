---
title: Visão geral do Gerenciamento de benefícios
description: Visão geral do recurso de Gerenciamento de benefícios no Dynamics 365 Human Resources. Ofereça opções de benefícios estendidos aos seus funcionários com uma experiência online fácil de usar.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 91a4425b4f020f90843bb3b0b280b7ee28463670
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230145"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="2b06a-104">Visão geral do Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="2b06a-104">Benefits management overview</span></span>

<span data-ttu-id="2b06a-105">Para permanecer em um mercado competitivo, é necessário oferecer um conjunto amplo de benefícios para atrair e reter os melhores funcionários.</span><span class="sxs-lookup"><span data-stu-id="2b06a-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="2b06a-106">Além dos benefícios padrão, como plano de saúde e odontológico, ofereça serviços expandidos, como assistência à adoção, programas de recreação e auxílio-vestimenta.</span><span class="sxs-lookup"><span data-stu-id="2b06a-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="2b06a-107">O Gerenciamento de benefícios do Microsoft Dynamics 365 Human Resources oferece uma solução flexível compatível com uma ampla variedade de opções de benefícios.</span><span class="sxs-lookup"><span data-stu-id="2b06a-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="2b06a-108">O Human Resources também inclui uma experiência para funcionários fácil de usar e que mostra as ofertas.</span><span class="sxs-lookup"><span data-stu-id="2b06a-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="2b06a-109">Os planos de benefícios aprimorados permitem criar e gerenciar planos de benefícios exclusivos e oferecem suporte a tabelas de taxas de benefícios complexas e camadas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="2b06a-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="2b06a-110">Você pode facilmente criar programas e pacotes de benefícios, além de regras de inscrição automática nos benefícios para facilitar a experiência dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="2b06a-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="2b06a-111">Os programas de crédito flexível permitem ratear para oferecer suporte à aposentadoria e outros eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="2b06a-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="2b06a-112">As regras de elegibilidade extensivas garantem a disponibilização dos benefícios apropriados para os funcionários certos.</span><span class="sxs-lookup"><span data-stu-id="2b06a-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="2b06a-113">A inscrição online nos benefícios permite uma experiência fácil para os funcionários.</span><span class="sxs-lookup"><span data-stu-id="2b06a-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="2b06a-114">O processamento de eventos de vida útil é compatível com eventos de vida futuros.</span><span class="sxs-lookup"><span data-stu-id="2b06a-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="2b06a-115">Se deseja acessar os dados de demonstração, será necessário implementar novamente o ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="2b06a-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="2b06a-116">Problemas conhecidos do gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="2b06a-116">Benefits management known issues</span></span>

### <a name="flex-credit-programs"></a><span data-ttu-id="2b06a-117">Programas de crédito flexível</span><span class="sxs-lookup"><span data-stu-id="2b06a-117">Flex credit programs</span></span>

<span data-ttu-id="2b06a-118">O valor de crédito total definido para um programa de crédito flexível não é exibido no formulário **Planos de benefícios do trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="2b06a-118">The total credit value defined for a flex credit program doesn't display in the **Worker benefit plans** form.</span></span> <span data-ttu-id="2b06a-119">Além disso, se você definir um programa de crédito flexível para ter uma regra de rateio de **Nenhum**, você recebe um erro no formulário **Plano de benefício do trabalhador** ao selecionar e confirmar planos.</span><span class="sxs-lookup"><span data-stu-id="2b06a-119">Also, if you set a flex credit program to have a proration rule of **None**, you get an error in the **Worker benefit plan** form when selecting and confirming plans.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="2b06a-120">Habilitar o Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="2b06a-120">Enable Benefits management</span></span>

<span data-ttu-id="2b06a-121">Este artigo descreve como acionar os recursos no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2b06a-121">This article describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="2b06a-122">Ele também informa quais recursos existentes no Human Resources são substituídos pelo Gerenciamento de benefícios ou quais são desabilitados após ativar o Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="2b06a-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b06a-123">Depois de habilitar o gerenciamento de benefícios em um ambiente de **Produção** você pode desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="2b06a-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="2b06a-124">É recomendável habilitar e testar o gerenciamento de benefícios em um ambiente de **Área restrita** antes de ativá-lo em um ambiente de **Produção**.</span><span class="sxs-lookup"><span data-stu-id="2b06a-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="2b06a-125">Há diferenças significativas entre a funcionalidade de benefício herdada e a nova funcionalidade de gerenciamento de benefícios que exigem configuração adicional e devem ser testadas antes de serem colocadas em produção.</span><span class="sxs-lookup"><span data-stu-id="2b06a-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="2b06a-126">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="2b06a-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="2b06a-127">Configurar informações do funcionário</span><span class="sxs-lookup"><span data-stu-id="2b06a-127">Configure employee information</span></span>

<span data-ttu-id="2b06a-128">Para poder inscrever funcionários em benefícios, você deve fornecer as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="2b06a-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="2b06a-129">Você deve registrar um funcionário em um **Plano de compensação fixa** em sua data de início, e você deve selecionar uma **Frequência de pagamento de benefício** em **Detalhes de emprego** no formulário **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="2b06a-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="2b06a-130">Quando você cria um plano de benefícios que usa taxas baseadas em sexo ou idade, você deve inserir uma data de nascimento e um sexo para que o funcionário calcule o custo de benefício.</span><span class="sxs-lookup"><span data-stu-id="2b06a-130">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="2b06a-131">Configurar Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="2b06a-131">Configure Benefits management</span></span>

<span data-ttu-id="2b06a-132">Antes de criar os planos de benefícios para seus funcionários, é necessário configurar as opções dos planos.</span><span class="sxs-lookup"><span data-stu-id="2b06a-132">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="2b06a-133">Definir parâmetros de gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="2b06a-133">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="2b06a-134">Configurar regras e opções de qualificação</span><span class="sxs-lookup"><span data-stu-id="2b06a-134">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="2b06a-135">Configurar opções de qualificação para contato pessoal</span><span class="sxs-lookup"><span data-stu-id="2b06a-135">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="2b06a-136">Criar opções de cobertura</span><span class="sxs-lookup"><span data-stu-id="2b06a-136">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="2b06a-137">Definir frequência de pagamento</span><span class="sxs-lookup"><span data-stu-id="2b06a-137">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="2b06a-138">Configurar tipos de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="2b06a-138">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="2b06a-139">Criar tipos de plano</span><span class="sxs-lookup"><span data-stu-id="2b06a-139">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="2b06a-140">Configurar códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="2b06a-140">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="2b06a-141">Configurar códigos de camada</span><span class="sxs-lookup"><span data-stu-id="2b06a-141">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="2b06a-142">Configurar taxas</span><span class="sxs-lookup"><span data-stu-id="2b06a-142">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="2b06a-143">Configurar deduções</span><span class="sxs-lookup"><span data-stu-id="2b06a-143">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="2b06a-144">Configurar dias de espera</span><span class="sxs-lookup"><span data-stu-id="2b06a-144">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="2b06a-145">Configurar períodos de espera</span><span class="sxs-lookup"><span data-stu-id="2b06a-145">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="2b06a-146">Configurar regras de arredondamento</span><span class="sxs-lookup"><span data-stu-id="2b06a-146">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="2b06a-147">Criar categorias de emprego</span><span class="sxs-lookup"><span data-stu-id="2b06a-147">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="2b06a-148">Configurar tipos de emprego</span><span class="sxs-lookup"><span data-stu-id="2b06a-148">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="2b06a-149">Configurar autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="2b06a-149">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="2b06a-150">Criar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="2b06a-150">Create benefit plans</span></span>

<span data-ttu-id="2b06a-151">Esses artigos mostram como criar planos de benefícios, incluindo pacotes e programas de crédito flexível.</span><span class="sxs-lookup"><span data-stu-id="2b06a-151">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="2b06a-152">Configurar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="2b06a-152">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="2b06a-153">Configurar programas de crédito flexível</span><span class="sxs-lookup"><span data-stu-id="2b06a-153">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="2b06a-154">Processar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="2b06a-154">Process benefit plans</span></span>

<span data-ttu-id="2b06a-155">É necessário processar algumas alterações para ativá-las.</span><span class="sxs-lookup"><span data-stu-id="2b06a-155">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="2b06a-156">Processar qualificação da inscrição</span><span class="sxs-lookup"><span data-stu-id="2b06a-156">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="2b06a-157">Processar eventos de vida</span><span class="sxs-lookup"><span data-stu-id="2b06a-157">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="2b06a-158">Processar alterações de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="2b06a-158">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="2b06a-159">Processar qualificação para eventos de vida</span><span class="sxs-lookup"><span data-stu-id="2b06a-159">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="2b06a-160">Processar alterações de taxa</span><span class="sxs-lookup"><span data-stu-id="2b06a-160">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

