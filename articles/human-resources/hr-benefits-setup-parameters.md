---
title: Definir parâmetros de gerenciamento de benefícios
description: Configure parâmetros para o gerenciamento de benefícios no Microsoft Dynamics 365 Human Resources.
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
ms.openlocfilehash: 9d6d463df08b9ae68047f09316f19e98740a8441
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229754"
---
# <a name="set-benefits-management-parameters"></a><span data-ttu-id="8bf3c-103">Definir parâmetros de gerenciamento de benefícios</span><span class="sxs-lookup"><span data-stu-id="8bf3c-103">Set Benefits management parameters</span></span>

<span data-ttu-id="8bf3c-104">Antes de configurar planos de licença no Microsoft Dynamics 365 Human Resources, você precisa configurar os parâmetros de gerenciamento de benefícios.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-104">Before you can set up leave plans in Microsoft Dynamics 365 Human Resources, you must configure Benefits management parameters.</span></span> <span data-ttu-id="8bf3c-105">Esses parâmetros definem valores padrão, códigos de motivo e outras opções.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-105">These parameters set default values, reason codes, and other options.</span></span>

## <a name="configure-general-parameters"></a><span data-ttu-id="8bf3c-106">Configurar parâmetros gerais</span><span class="sxs-lookup"><span data-stu-id="8bf3c-106">Configure general parameters</span></span>

1. <span data-ttu-id="8bf3c-107">No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-107">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="8bf3c-108">Na guia **Geral**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="8bf3c-108">In the **General** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="8bf3c-109">Campo</span><span class="sxs-lookup"><span data-stu-id="8bf3c-109">Field</span></span> | <span data-ttu-id="8bf3c-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="8bf3c-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="8bf3c-111">**País/região**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-111">**Country/region**</span></span> | <span data-ttu-id="8bf3c-112">O campo **País/região** determina a ordem de exibição de CEPs/estados.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-112">The **Country/region** field determines the display order of ZIP codes/states.</span></span> <span data-ttu-id="8bf3c-113">O país selecionado é exibido primeiro na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-113">The selected country displays first in the dropdown list.</span></span> |
   | <span data-ttu-id="8bf3c-114">**Código do motivo da inscrição**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-114">**Enrollment reason code**</span></span> | <span data-ttu-id="8bf3c-115">Selecione um código de motivo padrão a ser usado quando os planos do funcionário forem criados durante o processamento do inscrição aberta.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-115">Select a default reason code to use when employee plans are created during open enrollment processing.</span></span> |
   | <span data-ttu-id="8bf3c-116">**Código do motivo do cancelamento**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-116">**Cancellation reason code**</span></span> | <span data-ttu-id="8bf3c-117">O código de motivo a ser usado quando um plano de benefícios do funcionário é cancelado.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-117">The reason code to use when an employee benefit plan is canceled.</span></span> <span data-ttu-id="8bf3c-118">Ele é exibido em uma caixa de diálogo durante o processo de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-118">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="8bf3c-119">Os usuários podem alterar o **Código de motivo do cancelamento**, se necessário.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-119">Users can change it the **Cancellation reason code** if necessary.</span></span> |
   | <span data-ttu-id="8bf3c-120">**Código de motivo de reabertura**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-120">**Reopen reason code**</span></span> | <span data-ttu-id="8bf3c-121">O código de motivo a ser usado quando um plano de benefícios do funcionário é reaberto.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-121">The reason code to use when an employee benefit plan is reopened.</span></span> <span data-ttu-id="8bf3c-122">Ele é exibido em uma caixa de diálogo durante o processo de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-122">It displays in a dialog during the cancellation process.</span></span> <span data-ttu-id="8bf3c-123">Os usuários podem alterar o **Código de motivo de reabertura**, se necessário.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-123">Users can change the **Reopen reason code** if necessary.</span></span> | 
   | <span data-ttu-id="8bf3c-124">**Código do motivo do evento de vida**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-124">**Life event reason code**</span></span> | <span data-ttu-id="8bf3c-125">O código de motivo a ser usado quando ocorre um evento de vida.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-125">The reason code to use when a life event occurs.</span></span> |
   | <span data-ttu-id="8bf3c-126">**Código de motivo da alteração da taxa**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-126">**Rate change reason code**</span></span> | <span data-ttu-id="8bf3c-127">O código de motivo a ser usado ao cancelar e reabrir um plano de benefícios do funcionário durante o processo de atualização de alteração de taxa.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-127">The reason code to use when canceling and reopening an employee benefit plan during the rate change update process.</span></span> <span data-ttu-id="8bf3c-128">Ele indica quais registros foram alterados pelo processo de atualização da alteração de taxa.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-128">It indicates which records were changed by the rate change update process.</span></span> |
   | <span data-ttu-id="8bf3c-129">**Nova contratação qualificada**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-129">**New hire eligible**</span></span> | <span data-ttu-id="8bf3c-130">Especifica se novas contratações estão qualificadas.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-130">Specifies whether new hires are eligible.</span></span> |
   | <span data-ttu-id="8bf3c-131">**Período de inscrição de novas contratações**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-131">**New hire enrollment period**</span></span> | <span data-ttu-id="8bf3c-132">O período de tempo em que a nova inscrição de contratação é permitida.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-132">The period of time the new hire enrollment is allowed.</span></span></br></br><span data-ttu-id="8bf3c-133">**Observação**: esta configuração substitui qualquer novo período de inscrição de contratação definido na regra de qualificação para o plano.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-133">**Note**: This setting overrides any new hire enrollment period you set on the plan eligibility rule.</span></span> | 
   | <span data-ttu-id="8bf3c-134">**Eventos de vida habilitados**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-134">**Life events enabled**</span></span> | <span data-ttu-id="8bf3c-135">Habilita eventos de vida.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-135">Enables life events.</span></span> |
   | <span data-ttu-id="8bf3c-136">**Ocultar formulários de benefício herdados**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-136">**Hide legacy benefit forms**</span></span> | <span data-ttu-id="8bf3c-137">Permite ocultar formulários de benefícios herdados.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-137">Allows you to hide legacy benefit forms.</span></span> |

3. <span data-ttu-id="8bf3c-138">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-138">Select **Save**.</span></span>

## <a name="configure-employee-self-service-parameters"></a><span data-ttu-id="8bf3c-139">Configurar parâmetros de autoatendimento para funcionários</span><span class="sxs-lookup"><span data-stu-id="8bf3c-139">Configure Employee self service parameters</span></span>

1. <span data-ttu-id="8bf3c-140">No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-140">In the **Benefits management** workspace, under **Setup**, select **Parameters**.</span></span>

2. <span data-ttu-id="8bf3c-141">Na guia **Autoatendimento de funcionário**, especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="8bf3c-141">In the **Employee self service** tab, specify values for the following fields:</span></span>

   | <span data-ttu-id="8bf3c-142">Campo</span><span class="sxs-lookup"><span data-stu-id="8bf3c-142">Field</span></span> | <span data-ttu-id="8bf3c-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="8bf3c-143">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="8bf3c-144">**Verificação de benefício**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-144">**Benefit verification**</span></span> | <span data-ttu-id="8bf3c-145">O texto de verificação a ser usado durante o check-out de benefícios de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-145">The verification text to use during self-service benefits checkout.</span></span> |
   | <span data-ttu-id="8bf3c-146">**Seleção automática de representantes**</span><span class="sxs-lookup"><span data-stu-id="8bf3c-146">**Auto select designees**</span></span> | <span data-ttu-id="8bf3c-147">Especifica se os dependentes e os beneficiários devem ser selecionados automaticamente com base na sua qualificação para opções de plano.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-147">Specifies whether to automatically select dependents and beneficiaries based on their eligibility for plan options.</span></span> |

3. <span data-ttu-id="8bf3c-148">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8bf3c-148">Select **Save**.</span></span>
