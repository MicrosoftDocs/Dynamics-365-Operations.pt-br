---
title: Definir parâmetros de gerenciamento de benefícios e autoatendimento para funcionários para todas as empresas
description: Configure parâmetros de gerenciamento de benefícios e autoatendimento para funcionários no Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
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
ms.openlocfilehash: b50c4f71789c34f08ce810312f3c3198303b031e
ms.sourcegitcommit: fd097f6f76f0d8428038fa3655b3188bf093b517
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692688"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a><span data-ttu-id="ff471-103">Definir parâmetros de gerenciamento de benefícios e autoatendimento para funcionários para todas as empresas</span><span class="sxs-lookup"><span data-stu-id="ff471-103">Set Benefits management and Employee self-service parameters for all companies</span></span>

<span data-ttu-id="ff471-104">Antes de configurar planos de benefícios no Microsoft Dynamics 365 Human Resources, você precisa configurar os parâmetros de gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="ff471-104">Before you can set up benefit plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="ff471-105">Esses parâmetros definem valores padrão, códigos de motivo e outras opções.</span><span class="sxs-lookup"><span data-stu-id="ff471-105">These parameters set default values, reason codes, and other options.</span></span> 

## <a name="configure-general-parameters"></a><span data-ttu-id="ff471-106">Configurar parâmetros gerais</span><span class="sxs-lookup"><span data-stu-id="ff471-106">Configure general parameters</span></span>

1. <span data-ttu-id="ff471-107">No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros Compartilhados do Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="ff471-107">In the **Benefits management** workspace, under **Setup**, select **Human Resources Shared Parameters**.</span></span>

2. <span data-ttu-id="ff471-108">Na guia **Gerenciamento de benefícios**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="ff471-108">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="ff471-109">Campo</span><span class="sxs-lookup"><span data-stu-id="ff471-109">Field</span></span> | <span data-ttu-id="ff471-110">descrição</span><span class="sxs-lookup"><span data-stu-id="ff471-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="ff471-111">**País/região**</span><span class="sxs-lookup"><span data-stu-id="ff471-111">**Country/region**</span></span> | <span data-ttu-id="ff471-112">O campo **País/região** determina a ordem de exibição de CEPs/estados.</span><span class="sxs-lookup"><span data-stu-id="ff471-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="ff471-113">O país/região selecionado é exibido primeiro na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ff471-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="ff471-114">**Código do motivo da inscrição**</span><span class="sxs-lookup"><span data-stu-id="ff471-114">**Enrollment reason code**</span></span> | <span data-ttu-id="ff471-115">Selecione um código de motivo padrão a ser usado quando os planos do funcionário forem criados durante o processamento do inscrição aberta.</span><span class="sxs-lookup"><span data-stu-id="ff471-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="ff471-116">**Código do motivo do cancelamento**</span><span class="sxs-lookup"><span data-stu-id="ff471-116">**Cancellation reason code**</span></span> | <span data-ttu-id="ff471-117">O código de motivo a ser usado quando um plano de benefícios do funcionário é cancelado.</span><span class="sxs-lookup"><span data-stu-id="ff471-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="ff471-118">Ele é exibido em uma caixa de diálogo durante o processo de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="ff471-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="ff471-119">Os usuários podem alterar o **Código de motivo do cancelamento**, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ff471-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="ff471-120">**Código de motivo de reabertura**</span><span class="sxs-lookup"><span data-stu-id="ff471-120">**Reopen reason code**</span></span> | <span data-ttu-id="ff471-121">O código de motivo a ser usado quando um plano de benefícios do funcionário é reaberto.</span><span class="sxs-lookup"><span data-stu-id="ff471-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="ff471-122">Ele é exibido em uma caixa de diálogo durante o processo de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="ff471-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="ff471-123">Os usuários podem alterar o **Código de motivo de reabertura**, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ff471-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="ff471-124">**Código do motivo do evento de vida**</span><span class="sxs-lookup"><span data-stu-id="ff471-124">**Life event reason code**</span></span> | <span data-ttu-id="ff471-125">O código de motivo a ser usado quando ocorre um evento de vida.</span><span class="sxs-lookup"><span data-stu-id="ff471-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="ff471-126">**Código de motivo da alteração da taxa**</span><span class="sxs-lookup"><span data-stu-id="ff471-126">**Rate change reason code**</span></span> | <span data-ttu-id="ff471-127">O código de motivo a ser usado ao cancelar e reabrir um plano de benefícios do funcionário durante o processo de atualização de alteração de taxa.</span><span class="sxs-lookup"><span data-stu-id="ff471-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="ff471-128">Ele indica quais registros foram alterados pelo processo de atualização da alteração de taxa.</span><span class="sxs-lookup"><span data-stu-id="ff471-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="ff471-129">**Salário anual do benefício**</span><span class="sxs-lookup"><span data-stu-id="ff471-129">**Benefits annual salary**</span></span> | <span data-ttu-id="ff471-130">Permite definir um valor de **Salário de benefícios anual** para um funcionário.</span><span class="sxs-lookup"><span data-stu-id="ff471-130">Enables you to set a **Benefits annual salary** amount for an employee.</span></span> <span data-ttu-id="ff471-131">O Human Resources usará o valor do **Salário de benefícios anual** para determinar valores de cobertura em vez do valor anual da remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="ff471-131">Human Resources will use the **Benefits annual salary** amount when determining coverage amounts, instead of the fixed compensation annual amount.</span></span> |
   | <span data-ttu-id="ff471-132">**Nova contratação qualificada**</span><span class="sxs-lookup"><span data-stu-id="ff471-132">**New hire eligible**</span></span> | <span data-ttu-id="ff471-133">Especifica se novas contratações estão qualificadas.</span><span class="sxs-lookup"><span data-stu-id="ff471-133">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="ff471-134">**Período de inscrição de novas contratações**</span><span class="sxs-lookup"><span data-stu-id="ff471-134">**New hire enrollment period**</span></span> | <span data-ttu-id="ff471-135">O período de tempo em que a nova inscrição de contratação é permitida.</span><span class="sxs-lookup"><span data-stu-id="ff471-135">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="ff471-136">**Observação**: esta configuração substitui qualquer novo período de inscrição de contratação definido na regra de qualificação para o plano.</span><span class="sxs-lookup"><span data-stu-id="ff471-136">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> |
   | <span data-ttu-id="ff471-137">**Frequência de pagamento padrão**</span><span class="sxs-lookup"><span data-stu-id="ff471-137">**Default pay frequency**</span></span> | <span data-ttu-id="ff471-138">A frequência de pagamento padrão a ser usada quando novos trabalhadores são adicionados.</span><span class="sxs-lookup"><span data-stu-id="ff471-138">The default pay frequency to use when new workers are added.</span></span> |
   | <span data-ttu-id="ff471-139">**Eventos de vida habilitados**</span><span class="sxs-lookup"><span data-stu-id="ff471-139">**Life events enabled**</span></span> | <span data-ttu-id="ff471-140">Habilita eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="ff471-140">Enables life events.</span></span> |
   | <span data-ttu-id="ff471-141">**Ocultar formulários de benefício herdados**</span><span class="sxs-lookup"><span data-stu-id="ff471-141">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="ff471-142">Permite ocultar formulários de benefícios herdados.</span><span class="sxs-lookup"><span data-stu-id="ff471-142">Allows you to hide legacy benefit forms.</span></span> |
   | <span data-ttu-id="ff471-143">**Verificação de benefício**</span><span class="sxs-lookup"><span data-stu-id="ff471-143">**Benefit verification**</span></span> | <span data-ttu-id="ff471-144">O texto de verificação a ser usado durante o check-out de benefícios de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="ff471-144">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="ff471-145">**Seleção automática de representantes**</span><span class="sxs-lookup"><span data-stu-id="ff471-145">**Auto select designees**</span></span> | <span data-ttu-id="ff471-146">Especifica se os dependentes e os beneficiários devem ser selecionados automaticamente, com base na qualificação para opções de plano.</span><span class="sxs-lookup"><span data-stu-id="ff471-146">Specifies whether to automatically select dependents and beneficiaries, based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="ff471-147">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ff471-147">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="ff471-148">Configurar parâmetros de autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="ff471-148">Configure Employee self-service parameters</span></span>

1. <span data-ttu-id="ff471-149">No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros do Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="ff471-149">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="ff471-150">Na guia **Gerenciamento de benefícios**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="ff471-150">In the **Benefits management** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="ff471-151">Campo</span><span class="sxs-lookup"><span data-stu-id="ff471-151">Field</span></span> | <span data-ttu-id="ff471-152">descrição</span><span class="sxs-lookup"><span data-stu-id="ff471-152">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="ff471-153">**Verificação de benefício**</span><span class="sxs-lookup"><span data-stu-id="ff471-153">**Benefit verification**</span></span> | <span data-ttu-id="ff471-154">O texto de verificação a ser usado durante o check-out de benefícios de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="ff471-154">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="ff471-155">**Seleção automática de representantes**</span><span class="sxs-lookup"><span data-stu-id="ff471-155">**Auto select designees**</span></span> | <span data-ttu-id="ff471-156">Especifica se os dependentes e os beneficiários devem ser selecionados automaticamente com base na sua qualificação para opções de plano.</span><span class="sxs-lookup"><span data-stu-id="ff471-156">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="ff471-157">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ff471-157">Select **Save**.</span></span>


