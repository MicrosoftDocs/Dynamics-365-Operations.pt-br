---
title: Criar um fluxo de trabalho de solicitação de licença
description: Crie um fluxo de trabalho de solicitação de licença e ausência para gerenciar as solicitações de licença consistentemente no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 05/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5580b4b07b2d335ad9444a064c726bc4aca1db6a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056531"
---
# <a name="create-a-leave-request-workflow"></a><span data-ttu-id="576ed-103">Criar um fluxo de trabalho de solicitação de licença</span><span class="sxs-lookup"><span data-stu-id="576ed-103">Create a leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="576ed-104">Você pode criar um fluxo de trabalho no Dynamics 365 Human Resources para gerenciar as solicitações de licença e ausência de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="576ed-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your leave and absence requests.</span></span> <span data-ttu-id="576ed-105">Um fluxo de trabalho de **Licença e ausência** permite:</span><span class="sxs-lookup"><span data-stu-id="576ed-105">A **Leave and absence** workflow lets you:</span></span>

- <span data-ttu-id="576ed-106">Definir tarefas</span><span class="sxs-lookup"><span data-stu-id="576ed-106">Define tasks</span></span>
- <span data-ttu-id="576ed-107">Determinar quem deve concluir as tarefas</span><span class="sxs-lookup"><span data-stu-id="576ed-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="576ed-108">Especificar quem pode aprovar ou rejeitar solicitações</span><span class="sxs-lookup"><span data-stu-id="576ed-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-leave-and-absence-request-workflow"></a><span data-ttu-id="576ed-109">Criar um fluxo de trabalho de solicitação de licenças e ausências</span><span class="sxs-lookup"><span data-stu-id="576ed-109">Create a Leave and absence request workflow</span></span>

1. <span data-ttu-id="576ed-110">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="576ed-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="576ed-111">Em **Configuração**, selecione **Fluxos de trabalho de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="576ed-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="576ed-112">Selecione **Novo** e **Solicitação de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="576ed-112">Select **New**, and then select **Leave and absence request**.</span></span> 

4. <span data-ttu-id="576ed-113">Quando aparecer a caixa de mensagem **Abrir este arquivo?**, selecione **Abrir** e faça login com as credenciais da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="576ed-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="576ed-114">Use o editor de fluxo de trabalho para criar um fluxo de trabalho para suas solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="576ed-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="576ed-115">Para obter mais informações sobre como trabalhar com fluxos de trabalho, consulte [Visão geral de criação de fluxos de trabalho](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span><span class="sxs-lookup"><span data-stu-id="576ed-115">For more information about working with workflows, see [Create workflows overview](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="576ed-116">Elementos de dados de fluxo de trabalho de solicitação de licenças e ausências</span><span class="sxs-lookup"><span data-stu-id="576ed-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="576ed-117">Você pode usar os elementos de dados a seguir para criar aprovações condicionais ou automáticas em fluxos de trabalho para solicitações de licença e ausência:</span><span class="sxs-lookup"><span data-stu-id="576ed-117">You can use the following data elements to create conditional or automatic approvals in workflows for leave and absence requests:</span></span>

- <span data-ttu-id="576ed-118">**Valor**</span><span class="sxs-lookup"><span data-stu-id="576ed-118">**Amount**</span></span>
- <span data-ttu-id="576ed-119">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="576ed-119">**Comment**</span></span>
- <span data-ttu-id="576ed-120">**Empresa**</span><span class="sxs-lookup"><span data-stu-id="576ed-120">**Company**</span></span>
- <span data-ttu-id="576ed-121">**Criação de**</span><span class="sxs-lookup"><span data-stu-id="576ed-121">**Created by**</span></span>
- <span data-ttu-id="576ed-122">**Data e hora de criação**</span><span class="sxs-lookup"><span data-stu-id="576ed-122">**Created date and time**</span></span>
- <span data-ttu-id="576ed-123">**Data Final**</span><span class="sxs-lookup"><span data-stu-id="576ed-123">**End date**</span></span>
- <span data-ttu-id="576ed-124">**Tipo de licença**</span><span class="sxs-lookup"><span data-stu-id="576ed-124">**Leave type**</span></span>
- <span data-ttu-id="576ed-125">**Modificação de**</span><span class="sxs-lookup"><span data-stu-id="576ed-125">**Modified by**</span></span>
- <span data-ttu-id="576ed-126">**Data e hora da modificação**</span><span class="sxs-lookup"><span data-stu-id="576ed-126">**Modified date and time**</span></span>
- <span data-ttu-id="576ed-127">**Código do motivo**</span><span class="sxs-lookup"><span data-stu-id="576ed-127">**Reason code**</span></span>
- <span data-ttu-id="576ed-128">**ID da Solicitação**</span><span class="sxs-lookup"><span data-stu-id="576ed-128">**Request ID**</span></span>
- <span data-ttu-id="576ed-129">**Data inicial**</span><span class="sxs-lookup"><span data-stu-id="576ed-129">**Start date**</span></span>
- <span data-ttu-id="576ed-130">**Status**</span><span class="sxs-lookup"><span data-stu-id="576ed-130">**Status**</span></span> 
- <span data-ttu-id="576ed-131">**Data de envio**</span><span class="sxs-lookup"><span data-stu-id="576ed-131">**Submission date**</span></span>
- <span data-ttu-id="576ed-132">**Envio feito por**</span><span class="sxs-lookup"><span data-stu-id="576ed-132">**Submitted by**</span></span>
- <span data-ttu-id="576ed-133">**Enviado pelo Recursos Humanos**</span><span class="sxs-lookup"><span data-stu-id="576ed-133">**Submitted by Human resources**</span></span>
- <span data-ttu-id="576ed-134">**Enviado pelo gerente**</span><span class="sxs-lookup"><span data-stu-id="576ed-134">**Submitted by Manager**</span></span>
- <span data-ttu-id="576ed-135">**Enviado em nome de**</span><span class="sxs-lookup"><span data-stu-id="576ed-135">**Submitted on behalf**</span></span>
- <span data-ttu-id="576ed-136">**Trabalhador**</span><span class="sxs-lookup"><span data-stu-id="576ed-136">**Worker**</span></span>
- <span data-ttu-id="576ed-137">**Tipo de trabalhador**</span><span class="sxs-lookup"><span data-stu-id="576ed-137">**Worker type**</span></span>

<span data-ttu-id="576ed-138">Esses exemplos mostram como é possível criar diferentes tipos de condições de fluxo de trabalho usando esses elementos de dados:</span><span class="sxs-lookup"><span data-stu-id="576ed-138">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="576ed-139">Use o **Código do motivo** em uma instrução condicional para rotear solicitações de licença de doença com o código de motivo **Cirurgia** para HR para aprovação, enquanto roteia todos os outros códigos de motivo para o gerente.</span><span class="sxs-lookup"><span data-stu-id="576ed-139">Use **Reason code** in a conditional statement to route sick leave requests with the reason code **Surgery** to HR for approval, while routing all other reason codes to the manager.</span></span> <span data-ttu-id="576ed-140">Para obter mais informações sobre instruções condicionais, consulte [Configurar decisões condicionais em um fluxo de trabalho](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="576ed-140">For more information about conditional statements, see [Configure conditional decisions in a workflow](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md).</span></span> 

- <span data-ttu-id="576ed-141">Use **Enviado por Human resources** e **Enviado pelo gerente** em uma ação automática para aprovar automaticamente solicitações de licença que essas funções submetem em nome dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="576ed-141">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="576ed-142">Para obter mais informações sobre ações automáticas, consulte [Configurar processos de aprovação em um fluxo de trabalho](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="576ed-142">For more information about automatic actions, see [Configure approval processes in a workflow](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span></span>

- <span data-ttu-id="576ed-143">Use o **Tipo de licença** em uma instrução condicional ou ação automática para controlar como o fluxo de trabalho encaminha solicitações com certos tipos de licença.</span><span class="sxs-lookup"><span data-stu-id="576ed-143">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="576ed-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="576ed-144">See also</span></span>

- [<span data-ttu-id="576ed-145">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="576ed-145">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]