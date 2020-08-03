---
title: Visão geral do Gerenciamento de benefícios
description: Visão geral do recurso de Gerenciamento de benefícios no Dynamics 365 Human Resources. Ofereça opções de benefícios estendidos aos seus funcionários com uma experiência online fácil de usar.
author: andreabichsel
manager: AnnBe
ms.date: 07/16/2020
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
ms.openlocfilehash: 1043fb18c33e5ec0cde13008b168fd317c7c7be6
ms.sourcegitcommit: 9dc5c7dd5877cc6e7cd0059d173bcd8052ba13bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3599371"
---
# <a name="benefits-management-overview"></a><span data-ttu-id="fb741-104">Visão geral do Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="fb741-104">Benefits management overview</span></span>

<span data-ttu-id="fb741-105">Para permanecer em um mercado competitivo, é necessário oferecer um conjunto amplo de benefícios para atrair e reter os melhores funcionários.</span><span class="sxs-lookup"><span data-stu-id="fb741-105">To remain competitive, you must offer a rich set of benefits to attract and retain your best employees.</span></span> <span data-ttu-id="fb741-106">Além dos benefícios padrão, como plano de saúde e odontológico, ofereça serviços expandidos, como assistência à adoção, programas de recreação e auxílio-vestimenta.</span><span class="sxs-lookup"><span data-stu-id="fb741-106">In addition to standard benefits like medical and dental coverage, you might also want to offer expanded services like adoption assistance, recreation programs, and clothing allowances.</span></span> <span data-ttu-id="fb741-107">O Gerenciamento de benefícios do Microsoft Dynamics 365 Human Resources oferece uma solução flexível compatível com uma ampla variedade de opções de benefícios.</span><span class="sxs-lookup"><span data-stu-id="fb741-107">Benefits management in Microsoft Dynamics 365 Human Resources provides you with a flexible solution that supports a wide variety of benefit options.</span></span> <span data-ttu-id="fb741-108">O Human Resources também inclui uma experiência para funcionários fácil de usar e que mostra as ofertas.</span><span class="sxs-lookup"><span data-stu-id="fb741-108">Human Resources also includes an easy-to-use employee experience that showcases your offerings.</span></span>

- <span data-ttu-id="fb741-109">Os planos de benefícios aprimorados permitem criar e gerenciar planos de benefícios exclusivos e oferecem suporte a tabelas de taxas de benefícios complexas e camadas aninhadas.</span><span class="sxs-lookup"><span data-stu-id="fb741-109">Enhanced benefits plans let you create and manage unique benefit plans and support complex benefit rate tables and nested tiers.</span></span> <span data-ttu-id="fb741-110">Você pode facilmente criar programas e pacotes de benefícios, além de regras de inscrição automática nos benefícios para facilitar a experiência dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="fb741-110">You can easily create benefit programs, bundles, and auto-enrollment rules for an easier employee experience.</span></span>

- <span data-ttu-id="fb741-111">Os programas de crédito flexível permitem ratear para oferecer suporte à aposentadoria e outros eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="fb741-111">Flex credit programs let you prorate to support retirement and other life events.</span></span>

- <span data-ttu-id="fb741-112">As regras de elegibilidade extensivas garantem a disponibilização dos benefícios apropriados para os funcionários certos.</span><span class="sxs-lookup"><span data-stu-id="fb741-112">Extensive eligibility rules ensure you make the right benefits available to the right employees.</span></span>

- <span data-ttu-id="fb741-113">A inscrição online nos benefícios permite uma experiência fácil para os funcionários.</span><span class="sxs-lookup"><span data-stu-id="fb741-113">Online benefits enrollment provides an easy experience for your employees.</span></span>

- <span data-ttu-id="fb741-114">O processamento de eventos de vida útil é compatível com eventos de vida futuros.</span><span class="sxs-lookup"><span data-stu-id="fb741-114">Qualified life event processing supports future life events.</span></span>

<span data-ttu-id="fb741-115">Se deseja acessar os dados de demonstração, será necessário implementar novamente o ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="fb741-115">If you would like to access the demo data, you'll need to redeploy your sandbox environment.</span></span>

## <a name="benefits-management-known-issues"></a><span data-ttu-id="fb741-116">Problemas conhecidos do gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="fb741-116">Benefits management known issues</span></span>

### <a name="flex-credit-programs"></a><span data-ttu-id="fb741-117">Programas de crédito flexível</span><span class="sxs-lookup"><span data-stu-id="fb741-117">Flex credit programs</span></span>

<span data-ttu-id="fb741-118">O valor de crédito total definido para um programa de crédito flexível não é exibido no formulário **Planos de benefícios do trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="fb741-118">The total credit value defined for a flex credit program doesn't display in the **Worker benefit plans** form.</span></span> <span data-ttu-id="fb741-119">Além disso, se você definir um programa de crédito flexível para ter uma regra de rateio de **Nenhum**, você recebe um erro no formulário **Plano de benefício do trabalhador** ao selecionar e confirmar planos.</span><span class="sxs-lookup"><span data-stu-id="fb741-119">Also, if you set a flex credit program to have a proration rule of **None**, you get an error in the **Worker benefit plan** form when selecting and confirming plans.</span></span>

## <a name="enable-benefits-management"></a><span data-ttu-id="fb741-120">Habilitar o Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="fb741-120">Enable Benefits management</span></span>

<span data-ttu-id="fb741-121">Este artigo descreve como acionar os recursos no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fb741-121">This article describes how to turn on features in Human Resources.</span></span> <span data-ttu-id="fb741-122">Ele também informa quais recursos existentes no Human Resources são substituídos pelo Gerenciamento de benefícios ou quais são desabilitados após ativar o Gerenciamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="fb741-122">It also tells which existing features in Human Resources that Benefits management replaces or are disabled once you turn on Benefits management.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb741-123">Depois de habilitar o gerenciamento de benefícios em um ambiente de **Produção** você pode desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="fb741-123">After you enable Benefits management in a **Production** environment, you can't disable it.</span></span> <span data-ttu-id="fb741-124">É recomendável habilitar e testar o gerenciamento de benefícios em um ambiente de **Área restrita** antes de ativá-lo em um ambiente de **Produção**.</span><span class="sxs-lookup"><span data-stu-id="fb741-124">We recommend enabling and testing Benefits management in a **Sandbox** environment before enabling it in a **Production** environment.</span></span> <span data-ttu-id="fb741-125">Há diferenças significativas entre a funcionalidade de benefício herdada e a nova funcionalidade de gerenciamento de benefícios que exigem configuração adicional e devem ser testadas antes de serem colocadas em produção.</span><span class="sxs-lookup"><span data-stu-id="fb741-125">There are significant differences between the legacy Benefit functionality and new Benefits management functionality that require additional setup and should be tested prior to being placed into production.</span></span>

- [<span data-ttu-id="fb741-126">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="fb741-126">Manage features</span></span>](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a><span data-ttu-id="fb741-127">Configurar informações do funcionário</span><span class="sxs-lookup"><span data-stu-id="fb741-127">Configure employee information</span></span>

<span data-ttu-id="fb741-128">Para poder inscrever funcionários em benefícios, você deve fornecer as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="fb741-128">Before you can enroll employees in benefits, you must provide required information.</span></span> <span data-ttu-id="fb741-129">Você deve registrar um funcionário em um **Plano de compensação fixa** em sua data de início, e você deve selecionar uma **Frequência de pagamento de benefício** em **Detalhes de emprego** no formulário **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="fb741-129">You must enroll an employee in a **Fixed compensation plan** on their start date, and you must select a **Benefit pay frequency** in **Employment details** on the **Worker** form.</span></span>

<span data-ttu-id="fb741-130">Se você tem um funcionário que recebe remuneração suplementar, como comissões, é possível adicionar um valor de **Salário de benefícios anual** do registro do funcionário.</span><span class="sxs-lookup"><span data-stu-id="fb741-130">If you have an employee who receives supplemental compensation like commissions, you can add a **Benefits annual salary** amount from the employee record.</span></span> <span data-ttu-id="fb741-131">O Human Resources usará o valor do **Salário de benefícios anual** para determinar valores de cobertura em vez do valor anual da remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="fb741-131">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> <span data-ttu-id="fb741-132">O **Salário de benefícios anual** deve ser válido a partir da data de início do funcionário ou do início do período de benefício, dos dois o que for mais recente.</span><span class="sxs-lookup"><span data-stu-id="fb741-132">The **Benefits annual salary** must be valid as of the employee’s start date or the beginning of the benefit period, whichever is latest.</span></span> <span data-ttu-id="fb741-133">Se um valor de salário de benefícios anual e remuneração fixa for registrado para um funcionário, o salário de benefícios anual será usado para determinar os valores de cobertura.</span><span class="sxs-lookup"><span data-stu-id="fb741-133">If both a fixed compensation and benefits annual salary amount is recorded for an employee, the benefits annual salary will be used in determining coverage amounts.</span></span>

<span data-ttu-id="fb741-134">Quando você cria um plano de benefícios que usa taxas baseadas em sexo ou idade, você deve inserir uma data de nascimento e um sexo para que o funcionário calcule o custo de benefício.</span><span class="sxs-lookup"><span data-stu-id="fb741-134">When you create a benefit plan that uses rates that are based on gender or age, you must enter a birth date and gender for the employee to calculate the benefit cost.</span></span>

## <a name="configure-benefits-management"></a><span data-ttu-id="fb741-135">Configurar Gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="fb741-135">Configure Benefits management</span></span>

<span data-ttu-id="fb741-136">Antes de criar os planos de benefícios para seus funcionários, é necessário configurar as opções dos planos.</span><span class="sxs-lookup"><span data-stu-id="fb741-136">Before you can create benefit plans for your employees, you need to configure options for the plans.</span></span>

- [<span data-ttu-id="fb741-137">Definir parâmetros de gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="fb741-137">Set Benefits management parameters</span></span>](hr-benefits-setup-parameters.md)
- [<span data-ttu-id="fb741-138">Configurar regras e opções de qualificação</span><span class="sxs-lookup"><span data-stu-id="fb741-138">Configure eligibility rules and options</span></span>](hr-benefits-setup-eligibility-rules.md)
- [<span data-ttu-id="fb741-139">Configurar opções de qualificação para contato pessoal</span><span class="sxs-lookup"><span data-stu-id="fb741-139">Configure personal contact eligibility options</span></span>](hr-benefits-setup-contact-eligibility-options.md)
- [<span data-ttu-id="fb741-140">Criar opções de cobertura</span><span class="sxs-lookup"><span data-stu-id="fb741-140">Create coverage options</span></span>](hr-benefits-setup-coverage-options.md)
- [<span data-ttu-id="fb741-141">Definir frequência de pagamento</span><span class="sxs-lookup"><span data-stu-id="fb741-141">Set up payment frequencies</span></span>](hr-benefits-setup-payment-frequencies.md)
- [<span data-ttu-id="fb741-142">Configurar tipos de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="fb741-142">Configure life event types</span></span>](hr-benefits-setup-life-event-types.md)
- [<span data-ttu-id="fb741-143">Criar tipos de plano</span><span class="sxs-lookup"><span data-stu-id="fb741-143">Create plan types</span></span>](hr-benefits-setup-plan-types.md)
- [<span data-ttu-id="fb741-144">Configurar códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="fb741-144">Set up reason codes</span></span>](hr-benefits-setup-reason-codes.md)
- [<span data-ttu-id="fb741-145">Configurar códigos de camada</span><span class="sxs-lookup"><span data-stu-id="fb741-145">Set up tier codes</span></span>](hr-benefits-setup-tier-codes.md)
- [<span data-ttu-id="fb741-146">Configurar taxas</span><span class="sxs-lookup"><span data-stu-id="fb741-146">Configure rates</span></span>](hr-benefits-setup-rates.md)
- [<span data-ttu-id="fb741-147">Configurar deduções</span><span class="sxs-lookup"><span data-stu-id="fb741-147">Configure deductions</span></span>](hr-benefits-setup-deductions.md)
- [<span data-ttu-id="fb741-148">Configurar dias de espera</span><span class="sxs-lookup"><span data-stu-id="fb741-148">Configure waiting days</span></span>](hr-benefits-setup-waiting-days.md)
- [<span data-ttu-id="fb741-149">Configurar períodos de espera</span><span class="sxs-lookup"><span data-stu-id="fb741-149">Configure waiting periods</span></span>](hr-benefits-setup-waiting-periods.md)
- [<span data-ttu-id="fb741-150">Configurar regras de arredondamento</span><span class="sxs-lookup"><span data-stu-id="fb741-150">Set up rounding rules</span></span>](hr-benefits-setup-rounding-rules.md)
- [<span data-ttu-id="fb741-151">Criar categorias de emprego</span><span class="sxs-lookup"><span data-stu-id="fb741-151">Create employment categories</span></span>](hr-benefits-setup-employment-categories.md)
- [<span data-ttu-id="fb741-152">Configurar tipos de emprego</span><span class="sxs-lookup"><span data-stu-id="fb741-152">Set up employment types</span></span>](hr-benefits-setup-employment-types.md)
- [<span data-ttu-id="fb741-153">Configurar autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="fb741-153">Configure employee self service</span></span>](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a><span data-ttu-id="fb741-154">Criar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="fb741-154">Create benefit plans</span></span>

<span data-ttu-id="fb741-155">Esses artigos mostram como criar planos de benefícios, incluindo pacotes e programas de crédito flexível.</span><span class="sxs-lookup"><span data-stu-id="fb741-155">These articles show how to create benefit plans, including bundles and flex credit programs.</span></span>

- [<span data-ttu-id="fb741-156">Configurar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="fb741-156">Set up benefit plans</span></span>](hr-benefits-plans-setup.md)
- [<span data-ttu-id="fb741-157">Configurar programas de crédito flexível</span><span class="sxs-lookup"><span data-stu-id="fb741-157">Set up flex credit programs</span></span>](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a><span data-ttu-id="fb741-158">Processar planos de benefícios</span><span class="sxs-lookup"><span data-stu-id="fb741-158">Process benefit plans</span></span>

<span data-ttu-id="fb741-159">É necessário processar algumas alterações para ativá-las.</span><span class="sxs-lookup"><span data-stu-id="fb741-159">You need to process some of your changes to make them active.</span></span>

- [<span data-ttu-id="fb741-160">Processar qualificação da inscrição</span><span class="sxs-lookup"><span data-stu-id="fb741-160">Process enrollment eligibility</span></span>](hr-benefits-process-enrollment-eligibility.md)
- [<span data-ttu-id="fb741-161">Processar eventos de vida</span><span class="sxs-lookup"><span data-stu-id="fb741-161">Process life events</span></span>](hr-benefits-process-life-events.md)
- [<span data-ttu-id="fb741-162">Processar alterações de eventos de vida</span><span class="sxs-lookup"><span data-stu-id="fb741-162">Process life event changes</span></span>](hr-benefits-process-life-event-changes.md)
- [<span data-ttu-id="fb741-163">Processar qualificação para eventos de vida</span><span class="sxs-lookup"><span data-stu-id="fb741-163">Process life event eligibility</span></span>](hr-benefits-process-life-event-eligibility.md)
- [<span data-ttu-id="fb741-164">Processar alterações de taxa</span><span class="sxs-lookup"><span data-stu-id="fb741-164">Process rate changes</span></span>](hr-benefits-process-rate-changes.md)

