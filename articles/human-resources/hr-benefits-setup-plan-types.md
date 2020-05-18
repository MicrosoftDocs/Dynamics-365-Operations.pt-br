---
title: Criar tipos de plano
description: Um tipo de plano no Microsoft Dynamics 365 Human Resources é um agrupamento de alto nível de tipos específicos de benefícios. Cada tipo de plano tem um código de tipo de plano que determina as regras para o tipo de plano.
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
ms.openlocfilehash: 06a36f9f3fef54e7e06d616c9179374db4ce7115
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229685"
---
# <a name="create-plan-types"></a><span data-ttu-id="ce790-104">Criar tipos de plano</span><span class="sxs-lookup"><span data-stu-id="ce790-104">Create plan types</span></span>

<span data-ttu-id="ce790-105">Um tipo de plano no Microsoft Dynamics 365 Human Resources é um agrupamento de alto nível de tipos específicos de benefícios.</span><span class="sxs-lookup"><span data-stu-id="ce790-105">A plan type in Microsoft Dynamics 365 Human Resources is a high-level grouping of specific types of benefits.</span></span> <span data-ttu-id="ce790-106">Cada tipo de plano tem um código de tipo de plano que determina as regras para o tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="ce790-106">Each plan type has a plan type code that determines rules for the plan type.</span></span> <span data-ttu-id="ce790-107">Por exemplo, a vida básica do tipo de plano teria a vida de código de tipo de plano porque é um tipo de plano de seguro de vida e deve seguir as regras estabelecidas para o código de tipo de plano de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-107">For example, the plan type Basic life would have the plan type code Life because it’s a kind of life insurance plan and must conform to rules established for the Life plan type code.</span></span> <span data-ttu-id="ce790-108">Outro tipo de plano pode ser vida complementar, também com vida de código de tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="ce790-108">Another plan type might be Supplemental life, also with plan type code Life.</span></span>

<span data-ttu-id="ce790-109">Cada tipo de plano indica se um funcionário pode se inscrever em um plano desse tipo ou em vários.</span><span class="sxs-lookup"><span data-stu-id="ce790-109">Each plan type indicates whether an employee can enroll in one plan of its type or multiple.</span></span> <span data-ttu-id="ce790-110">Por exemplo, um funcionário provavelmente poderá registrar tanto a vida básica quanto as políticas de vida suplementares do tipo de plano Vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-110">For example, an employee would likely be able to enroll in both the Basic life and the Supplemental life policies of plan type Life.</span></span> <span data-ttu-id="ce790-111">Um funcionário provavelmente terá permissão para inscrever-se em apenas uma política do tipo médico.</span><span class="sxs-lookup"><span data-stu-id="ce790-111">An employee would likely be allowed to enroll in only one policy of type Medical.</span></span>

<span data-ttu-id="ce790-112">Se um tipo de plano envolver contatos, o tipo de plano indicará se os contatos são beneficiários ou dependentes.</span><span class="sxs-lookup"><span data-stu-id="ce790-112">If a plan type involves contacts, the plan type indicates whether contacts are beneficiaries or dependents.</span></span> <span data-ttu-id="ce790-113">Por exemplo, um tipo de plano de vida básico teria os beneficiários, enquanto um tipo de plano médico básico teria dependentes.</span><span class="sxs-lookup"><span data-stu-id="ce790-113">For example, a Basic life plan type would have beneficiaries, while a Basic medical plan type would have dependents.</span></span> <span data-ttu-id="ce790-114">Em alguns casos, um plano pode não ter contatos pessoais.</span><span class="sxs-lookup"><span data-stu-id="ce790-114">In some cases, a plan may not have any personal contacts.</span></span> <span data-ttu-id="ce790-115">Por exemplo, uma conta de despesas flexível ou bonificação de estacionamento.</span><span class="sxs-lookup"><span data-stu-id="ce790-115">For example, a Flexible Spending Account or Parking allowance.</span></span>

<span data-ttu-id="ce790-116">Um tipo de plano pode definir opções de cobertura.</span><span class="sxs-lookup"><span data-stu-id="ce790-116">A plan type may define coverage options.</span></span> <span data-ttu-id="ce790-117">As opções de cobertura são definidas no formulário opção de cobertura.</span><span class="sxs-lookup"><span data-stu-id="ce790-117">The coverage options are defined in the Coverage option form.</span></span> <span data-ttu-id="ce790-118">Uma opção de cobertura pode especificar o valor do benefício ou os contatos qualificados para o tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="ce790-118">A coverage option can specify the amount of the benefit or the contacts who are eligible for the plan type.</span></span> <span data-ttu-id="ce790-119">Por exemplo, se o tipo de contato for beneficiário, a opção de cobertura deverá definir os termos do que o beneficiário está qualificado para receber quando o benefício é utilizado.</span><span class="sxs-lookup"><span data-stu-id="ce790-119">For example, if the contact type is Beneficiary, the coverage option should define the terms of what the beneficiary is eligible to receive when the benefit is utilized.</span></span> <span data-ttu-id="ce790-120">Se o tipo de contato for dependente, a opção de cobertura deverá definir o relacionamento entre o dependente e o funcionário.</span><span class="sxs-lookup"><span data-stu-id="ce790-120">If the contact type is Dependent, the coverage option should define the relationship between the dependent and employee.</span></span> 

1. <span data-ttu-id="ce790-121">No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Tipos de plano**.</span><span class="sxs-lookup"><span data-stu-id="ce790-121">In the **Benefits management** workspace, under **Setup**, select **Plan types**.</span></span>

2. <span data-ttu-id="ce790-122">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ce790-122">Select **New**.</span></span>

3. <span data-ttu-id="ce790-123">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="ce790-123">Specify values for the following fields:</span></span>

   | <span data-ttu-id="ce790-124">Campo</span><span class="sxs-lookup"><span data-stu-id="ce790-124">Field</span></span> | <span data-ttu-id="ce790-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="ce790-125">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="ce790-126">**Tipo de plano**</span><span class="sxs-lookup"><span data-stu-id="ce790-126">**Plan type**</span></span> | <span data-ttu-id="ce790-127">Um nome exclusivo que identifica o tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="ce790-127">A unique name that identifies the plan type.</span></span> |
   | <span data-ttu-id="ce790-128">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ce790-128">**Description**</span></span> | <span data-ttu-id="ce790-129">Uma descrição do tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="ce790-129">A description of the plan type.</span></span> |
   | <span data-ttu-id="ce790-130">**Código do tipo de plano**</span><span class="sxs-lookup"><span data-stu-id="ce790-130">**Plan type code**</span></span> | <span data-ttu-id="ce790-131">Selecione um código do tipo de plano na lista suspensa de valores.</span><span class="sxs-lookup"><span data-stu-id="ce790-131">Select a plan type code from the drop-down list of values.</span></span> <span data-ttu-id="ce790-132">A lista de códigos do tipo de plano exibe todos os tipos de plano que têm suporte na versão atual.</span><span class="sxs-lookup"><span data-stu-id="ce790-132">The plan type code list displays all the plan types that are supported in the current version.</span></span> |
   | <span data-ttu-id="ce790-133">**Inscrição simultânea**</span><span class="sxs-lookup"><span data-stu-id="ce790-133">**Concurrent enrollment**</span></span> | <span data-ttu-id="ce790-134">Especifica se um funcionário pode se inscrever em vários planos de benefícios do mesmo tipo de plano ou somente um plano de benefício por tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="ce790-134">Specifies whether an employee can enroll in multiple benefit plans of the same plan type or only one benefit plan per plan type.</span></span> |
   | <span data-ttu-id="ce790-135">**Tipo de contato**</span><span class="sxs-lookup"><span data-stu-id="ce790-135">**Contact type**</span></span> | <span data-ttu-id="ce790-136">Especifica a função do contato pessoal.</span><span class="sxs-lookup"><span data-stu-id="ce790-136">Specifies the role of the personal contact.</span></span> <span data-ttu-id="ce790-137">Os valores são em branco, dependente e beneficiário.</span><span class="sxs-lookup"><span data-stu-id="ce790-137">The values are blank, Dependent, and Beneficiary.</span></span> <span data-ttu-id="ce790-138">Você poderá deixar o **Tipo de contato** em branco se o tipo de plano não exigir um dependente ou beneficiário com base na opção de cobertura.</span><span class="sxs-lookup"><span data-stu-id="ce790-138">You can leave **Contact type** blank if their plan type does not require a dependent or beneficiary based on the coverage option.</span></span> |

4. <span data-ttu-id="ce790-139">Para configurar opções de evento de vida, selecione **Ações**e **Opções de evento de vida**.</span><span class="sxs-lookup"><span data-stu-id="ce790-139">To configure life event options, select **Actions**, and then select **Life event options**.</span></span> <span data-ttu-id="ce790-140">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="ce790-140">Specify values for the following fields:</span></span>

   | <span data-ttu-id="ce790-141">Campo</span><span class="sxs-lookup"><span data-stu-id="ce790-141">Field</span></span> | <span data-ttu-id="ce790-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="ce790-142">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="ce790-143">**Tipo de plano**</span><span class="sxs-lookup"><span data-stu-id="ce790-143">**Plan type**</span></span> | <span data-ttu-id="ce790-144">O tipo de plano no qual configurar opções de evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-144">The plan type to configure life event options for.</span></span> |
   | <span data-ttu-id="ce790-145">**ID do tipo de evento de vida**</span><span class="sxs-lookup"><span data-stu-id="ce790-145">**Life event type ID**</span></span> | <span data-ttu-id="ce790-146">A ID do tipo de evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-146">The ID of the life event type.</span></span> |
   | <span data-ttu-id="ce790-147">**Permitir cancelamento**</span><span class="sxs-lookup"><span data-stu-id="ce790-147">**Allow cancellation**</span></span> | <span data-ttu-id="ce790-148">Especifica se um funcionário pode cancelar um plano de benefícios durante o evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-148">Specifies whether an employee can cancel a benefits plan during the life event.</span></span> |
   | <span data-ttu-id="ce790-149">**Alterar opção de cobertura**</span><span class="sxs-lookup"><span data-stu-id="ce790-149">**Change coverage option**</span></span> | <span data-ttu-id="ce790-150">Especifica se um funcionário pode alterar opções de cobertura durante o evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-150">Specifies whether an employee can change coverage options during the life event.</span></span> |
   | <span data-ttu-id="ce790-151">**Alterar para um novo plano**</span><span class="sxs-lookup"><span data-stu-id="ce790-151">**Change to a new plan**</span></span> | <span data-ttu-id="ce790-152">Especifica se um funcionário pode alterar planos durante o evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-152">Specifies whether an employee can change plans during the life event.</span></span> |
   | <span data-ttu-id="ce790-153">**Cancelar plano automaticamente**</span><span class="sxs-lookup"><span data-stu-id="ce790-153">**Auto cancel plan**</span></span> | <span data-ttu-id="ce790-154">Especifica se o plano deve ser cancelado automaticamente durante o evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-154">Specifies whether to automatically cancel the plan during the life event.</span></span> |
   | <span data-ttu-id="ce790-155">**Verificação de qualificação para reabertura automática**</span><span class="sxs-lookup"><span data-stu-id="ce790-155">**Auto reopen eligibility check**</span></span> | <span data-ttu-id="ce790-156">Especifica se a verificação de qualificação de inscrição no benefício será reaberta automaticamente durante o evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-156">Specifies whether to automatically reopen the benefits enrollment eligibility check during the life event.</span></span> |
   | <span data-ttu-id="ce790-157">**Janela do relatório**</span><span class="sxs-lookup"><span data-stu-id="ce790-157">**Reporting window**</span></span> | <span data-ttu-id="ce790-158">Especifica a janela do relatório, em dias, do evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-158">Specifies the reporting window, in days, of the life event.</span></span> <span data-ttu-id="ce790-159">**Observação**: se você não inserir um valor, o sistema assumirá que a janela de relatório é zero e não processará o evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ce790-159">**Note**: If you don't enter an amount, the system assumes the reporting window to be zero and won't process the life event.</span></span> |

5. <span data-ttu-id="ce790-160">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce790-160">Select **Save**.</span></span> 