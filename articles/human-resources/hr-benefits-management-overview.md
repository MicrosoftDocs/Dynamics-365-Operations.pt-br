---
title: Visão geral do Gerenciamento de benefícios
description: Visão geral da versão prévia do recurso de Gerenciamento de benefícios no Dynamics 365 Human Resources. Ofereça opções de benefícios estendidos aos seus funcionários com uma experiência online fácil de usar.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029454"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="b780f-104">Visão geral do Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="b780f-104">Benefits management overview</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="b780f-105">Para permanecer em um mercado competitivo, é necessário oferecer um conjunto amplo de benefícios para atrair e reter os melhores funcionários.</span><span class="sxs-lookup"><span data-stu-id="b780f-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="b780f-106">Além dos benefícios padrão, como plano de saúde e odontológico, ofereça serviços expandidos, como assistência à adoção, programas de recreação e auxílio-vestimenta.</span><span class="sxs-lookup"><span data-stu-id="b780f-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="b780f-107">A versão prévia do recurso de Gerenciamento de benefícios do Microsoft Dynamics 365 Human Resources oferece uma solução flexível compatível com uma ampla variedade de opções de benefícios.</span><span class="sxs-lookup"><span data-stu-id="b780f-107">The Benefits management preview feature in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="b780f-108">O Human Resources também inclui uma experiência para funcionários fácil de usar e que mostra as ofertas.</span><span class="sxs-lookup"><span data-stu-id="b780f-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="b780f-109">Os planos de benefícios aprimorados permitem criar e gerenciar planos de benefícios exclusivos e oferecem suporte a tabelas de taxas de benefícios complexas e camadas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="b780f-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="b780f-110">Você pode facilmente criar programas e pacotes de benefícios, além de regras de inscrição automática nos benefícios para facilitar a experiência dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="b780f-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="b780f-111">Os programas de crédito flexível permitem ratear para oferecer suporte à aposentadoria e outros eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="b780f-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="b780f-112">As regras de elegibilidade extensivas garantem a disponibilização dos benefícios apropriados para os funcionários certos.</span><span class="sxs-lookup"><span data-stu-id="b780f-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="b780f-113">A inscrição online nos benefícios permite uma experiência fácil para os funcionários.</span><span class="sxs-lookup"><span data-stu-id="b780f-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="b780f-114">O processamento de evento de vida qualificado é integrado ao Autoatendimento para funcionários e também oferece suporte para eventos de vida futuros.</span><span class="sxs-lookup"><span data-stu-id="b780f-114">Qualified life event processing integrates with Employee self service, and also supports future life events.</span></span>

<span data-ttu-id="b780f-115">Se deseja acessar os dados de demonstração, será necessário implementar novamente o ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="b780f-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

<span data-ttu-id="b780f-116">Você pode fornecer um feedback direto ou relatar problemas em: D365BenefitsPreview@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b780f-116">You can provide direct feedback or report issues to:  D365BenefitsPreview@microsoft.com.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="b780f-117">Problemas conhecidos do gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="b780f-117">Benefits management known issues</span></span>

### <a name="eligibility-processing"></a><span data-ttu-id="b780f-118">Processamento de elegibilidade</span><span class="sxs-lookup"><span data-stu-id="b780f-118">Eligibility processing</span></span>

<span data-ttu-id="b780f-119">Ao executar a elegibilidade para benefícios que usam 1-5X Salário, % do Salário e o valor de cobertura do Valor Simples, é necessário definir a data dos **Detalhes dos benefícios** como a **Data de início do funcionário** no **Histórico de empregos**.</span><span class="sxs-lookup"><span data-stu-id="b780f-119">When running eligibility for benefits that use a 1-5X Salary, % of Salary, and Flat Amount coverage amount, you must set the **Benefit details** date to the **Employee start date** in **Employment history**.</span></span> <span data-ttu-id="b780f-120">Também é necessário incluir **Horas trabalhadas**, **Frequência de pagamento** e **Valor do salário de benefícios anual**.</span><span class="sxs-lookup"><span data-stu-id="b780f-120">You must also include **Hours worked**, **Payment frequency**, and **Annual benefits salary amount**.</span></span> <span data-ttu-id="b780f-121">Se o trabalhador tiver uma remuneração fixa, insira **Horas trabalhadas** e **Frequência de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="b780f-121">If the worker has fixed compensation, enter **Hours worked** and **Payment frequency**.</span></span> <span data-ttu-id="b780f-122">O valor do salário anual será calculado.</span><span class="sxs-lookup"><span data-stu-id="b780f-122">The annual salary amount will calculate.</span></span> <span data-ttu-id="b780f-123">Se o funcionário for assalariado, não será necessário inserir **Horas trabalhadas**.</span><span class="sxs-lookup"><span data-stu-id="b780f-123">If the employee is salaried, you don't need to enter **Hours worked**.</span></span> <span data-ttu-id="b780f-124">Recomendamos que, ao criar novos trabalhadores, insira a remuneração fixa primeiro.</span><span class="sxs-lookup"><span data-stu-id="b780f-124">We recommend that when creating new workers, enter fixed compensation first.</span></span> <span data-ttu-id="b780f-125">Para atualizar o registro dos detalhes dos benefícios, navegue até **Trabalhador > Histórico do trabalhador > Detalhes do emprego**.</span><span class="sxs-lookup"><span data-stu-id="b780f-125">To update the benefit details record, navigate to **Worker > Worker history > Employment details**.</span></span> <span data-ttu-id="b780f-126">Ajuste a data para a data de início do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="b780f-126">Adjust the date to the worker's start date.</span></span>

### <a name="employee-self-service"></a><span data-ttu-id="b780f-127">Autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="b780f-127">Employee self-service</span></span>

<span data-ttu-id="b780f-128">O valor do funcionário não é calculado ao atualizar o valor da cobertura do seguro de vida.</span><span class="sxs-lookup"><span data-stu-id="b780f-128">Employee amount doesn't calculate when updating the coverage amount for life insurance.</span></span> <span data-ttu-id="b780f-129">Por exemplo, quando um funcionário é oferecido a um plano de seguro de vida, ele pode selecionar até US$ 50.000 em cobertura a um custo de US$ 0,36 por US$ 1.000 de cobertura.</span><span class="sxs-lookup"><span data-stu-id="b780f-129">For example, when an employee is offered a life insurance plan, they can select up to $50,000 in coverage at a cost of $.36 per $1,000 of coverage.</span></span>  <span data-ttu-id="b780f-130">Quando o funcionário atualiza o valor da cobertura, o custo associado do funcionário permanece em zero.</span><span class="sxs-lookup"><span data-stu-id="b780f-130">When the employee updates the coverage amount, the employee’s associated cost remains at zero.</span></span>

<span data-ttu-id="b780f-131">Para um plano de benefícios que permite somente uma única seleção desse tipo de plano, o usuário receberá uma mensagem de erro se tentar cancelar um plano após selecioná-lo.</span><span class="sxs-lookup"><span data-stu-id="b780f-131">For a benefit plan that only allows a single selection of that plan type, the user receives an error if they attempt to waive a plan after selecting a plan.</span></span> <span data-ttu-id="b780f-132">Por exemplo, um usuário seleciona um plano médico e o coloca em seu carrinho.</span><span class="sxs-lookup"><span data-stu-id="b780f-132">For example, a user selects a medical plan and places it in their cart.</span></span> <span data-ttu-id="b780f-133">O usuário seleciona **Renunciar** a outro plano médico.</span><span class="sxs-lookup"><span data-stu-id="b780f-133">The user then selects **Waive** for another medical plan.</span></span> <span data-ttu-id="b780f-134">O usuário receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="b780f-134">The user will receive an error.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="b780f-135">Habilitar o Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="b780f-135">Enable Benefits management</span></span>

<span data-ttu-id="b780f-136">O Gerenciamento de benefícios é uma versão prévia do recurso e está disponível somente em ambientes de **Área restrita**.</span><span class="sxs-lookup"><span data-stu-id="b780f-136">Benefits management is a preview feature, and is only available in **Sandbox** environments.</span></span> <span data-ttu-id="b780f-137">Esses artigos descrevem como acionar a versão prévia de recursos no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b780f-137">These articles describe how to turn on preview features in Human Resources.</span></span> <span data-ttu-id="b780f-138">Eles também informam quais recursos existentes no Human Resources são substituídos pelo Gerenciamento de benefícios ou quais são desabilitados após ativar o Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="b780f-138">They also tell which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

- [<span data-ttu-id="b780f-139">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="b780f-139">Manage features</span></span>](hr-admin-manage-features.md)
- [<span data-ttu-id="b780f-140">Recurso de visualização: Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="b780f-140">Preview feature: Benefits management</span></span>](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a><span data-ttu-id="b780f-141">Configurar Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="b780f-141">Configure Benefits management</span></span>

<span data-ttu-id="b780f-142">Antes de criar os planos de benefícios para seus funcionários, é necessário configurar as opções dos planos.</span><span class="sxs-lookup"><span data-stu-id="b780f-142">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="b780f-143">Definir parâmetros de gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="b780f-143">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="b780f-144">Configurar regras e opções de qualificação</span><span class="sxs-lookup"><span data-stu-id="b780f-144">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="b780f-145">Configurar opções de qualificação para contato pessoal</span><span class="sxs-lookup"><span data-stu-id="b780f-145">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="b780f-146">Criar opções de cobertura</span><span class="sxs-lookup"><span data-stu-id="b780f-146">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="b780f-147">Definir frequência de pagamento</span><span class="sxs-lookup"><span data-stu-id="b780f-147">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="b780f-148">Configurar tipos de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="b780f-148">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="b780f-149">Criar tipos de plano</span><span class="sxs-lookup"><span data-stu-id="b780f-149">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="b780f-150">Configurar códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="b780f-150">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="b780f-151">Configurar códigos de camada</span><span class="sxs-lookup"><span data-stu-id="b780f-151">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="b780f-152">Configurar taxas</span><span class="sxs-lookup"><span data-stu-id="b780f-152">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="b780f-153">Configurar deduções</span><span class="sxs-lookup"><span data-stu-id="b780f-153">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="b780f-154">Configurar dias de espera</span><span class="sxs-lookup"><span data-stu-id="b780f-154">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="b780f-155">Configurar períodos de espera</span><span class="sxs-lookup"><span data-stu-id="b780f-155">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="b780f-156">Configurar regras de arredondamento</span><span class="sxs-lookup"><span data-stu-id="b780f-156">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="b780f-157">Criar categorias de emprego</span><span class="sxs-lookup"><span data-stu-id="b780f-157">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="b780f-158">Configurar tipos de emprego</span><span class="sxs-lookup"><span data-stu-id="b780f-158">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="b780f-159">Configurar autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="b780f-159">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="b780f-160">Criar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="b780f-160">Create benefit plans</span></span>

<span data-ttu-id="b780f-161">Esses artigos mostram como criar planos de benefícios, incluindo pacotes e programas de crédito flexível.</span><span class="sxs-lookup"><span data-stu-id="b780f-161">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="b780f-162">Configurar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="b780f-162">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="b780f-163">Criar planos de benefícios do trabalhador</span><span class="sxs-lookup"><span data-stu-id="b780f-163">Create worker benefit plans</span></span>](hr-benefits-plans-worker.md)
- [<span data-ttu-id="b780f-164">Configurar programas de crédito flexível</span><span class="sxs-lookup"><span data-stu-id="b780f-164">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)
- [<span data-ttu-id="b780f-165">Configurar eventos de vida futuros</span><span class="sxs-lookup"><span data-stu-id="b780f-165">Configure future life events</span></span>](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="b780f-166">Processar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="b780f-166">Process benefit plans</span></span>

<span data-ttu-id="b780f-167">É necessário processar algumas alterações para ativá-las.</span><span class="sxs-lookup"><span data-stu-id="b780f-167">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="b780f-168">Processar qualificação da inscrição</span><span class="sxs-lookup"><span data-stu-id="b780f-168">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="b780f-169">Processar eventos de vida</span><span class="sxs-lookup"><span data-stu-id="b780f-169">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="b780f-170">Processar alterações de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="b780f-170">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="b780f-171">Processar qualificação para eventos de vida</span><span class="sxs-lookup"><span data-stu-id="b780f-171">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="b780f-172">Processar alterações de taxa</span><span class="sxs-lookup"><span data-stu-id="b780f-172">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

