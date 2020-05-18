---
title: Criar um fluxo de trabalho de solicitação de licença
description: Crie um fluxo de trabalho de solicitação de licença e ausência para gerenciar as solicitações de licença consistentemente no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 05/08/2020
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
ms.openlocfilehash: c2e994d11bbd45907a48c1f3955fa751a676a327
ms.sourcegitcommit: e69cfc74e9dbce64ae0e1ab7cd441e5ae6efd4c9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "3353679"
---
# <a name="create-a-leave-request-workflow"></a><span data-ttu-id="826f9-103">Criar um fluxo de trabalho de solicitação de licença</span><span class="sxs-lookup"><span data-stu-id="826f9-103">Create a leave request workflow</span></span>

<span data-ttu-id="826f9-104">Você pode criar um fluxo de trabalho no Dynamics 365 Human Resources para gerenciar as solicitações de licença e ausência de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="826f9-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your leave and absence requests.</span></span> <span data-ttu-id="826f9-105">Um fluxo de trabalho de **Licença e ausência** permite:</span><span class="sxs-lookup"><span data-stu-id="826f9-105">A **Leave and absence** workflow lets you:</span></span>

- <span data-ttu-id="826f9-106">Definir tarefas</span><span class="sxs-lookup"><span data-stu-id="826f9-106">Define tasks</span></span>
- <span data-ttu-id="826f9-107">Determinar quem deve concluir as tarefas</span><span class="sxs-lookup"><span data-stu-id="826f9-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="826f9-108">Especificar quem pode aprovar ou rejeitar solicitações</span><span class="sxs-lookup"><span data-stu-id="826f9-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-leave-and-absence-request-workflow"></a><span data-ttu-id="826f9-109">Criar um fluxo de trabalho de solicitação de licenças e ausências</span><span class="sxs-lookup"><span data-stu-id="826f9-109">Create a Leave and absence request workflow</span></span>

1. <span data-ttu-id="826f9-110">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="826f9-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="826f9-111">Em **Configuração**, selecione **Fluxos de trabalho de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="826f9-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="826f9-112">Selecione **Novo** e **Solicitação de licença e ausência**.</span><span class="sxs-lookup"><span data-stu-id="826f9-112">Select **New**, and then select **Leave and absence request**.</span></span> 

4. <span data-ttu-id="826f9-113">Quando aparecer a caixa de mensagem **Abrir este arquivo?**, selecione **Abrir** e faça login com as credenciais da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="826f9-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="826f9-114">Use o editor de fluxo de trabalho para criar um fluxo de trabalho para suas solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="826f9-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="826f9-115">Para obter mais informações sobre como trabalhar com fluxos de trabalho, consulte [Visão geral de criação de fluxos de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="826f9-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="826f9-116">Elementos de dados de fluxo de trabalho de solicitação de licenças e ausências</span><span class="sxs-lookup"><span data-stu-id="826f9-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="826f9-117">Você pode usar os elementos de dados a seguir para criar aprovações condicionais ou automáticas em fluxos de trabalho para solicitações de licença e ausência:</span><span class="sxs-lookup"><span data-stu-id="826f9-117">You can use the following data elements to create conditional or automatic approvals in workflows for leave and absence requests:</span></span>

- <span data-ttu-id="826f9-118">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="826f9-118">**Comment**</span></span>
- <span data-ttu-id="826f9-119">**Empresa**</span><span class="sxs-lookup"><span data-stu-id="826f9-119">**Company**</span></span>
- <span data-ttu-id="826f9-120">**Criação de**</span><span class="sxs-lookup"><span data-stu-id="826f9-120">**Created by**</span></span>
- <span data-ttu-id="826f9-121">**Data e hora de criação**</span><span class="sxs-lookup"><span data-stu-id="826f9-121">**Created date and time**</span></span>
- <span data-ttu-id="826f9-122">**Data Final**</span><span class="sxs-lookup"><span data-stu-id="826f9-122">**End date**</span></span>
- <span data-ttu-id="826f9-123">**Tipo de licença**</span><span class="sxs-lookup"><span data-stu-id="826f9-123">**Leave type**</span></span>
- <span data-ttu-id="826f9-124">**Modificação de**</span><span class="sxs-lookup"><span data-stu-id="826f9-124">**Modified by**</span></span>
- <span data-ttu-id="826f9-125">**Data e hora da modificação**</span><span class="sxs-lookup"><span data-stu-id="826f9-125">**Modified date and time**</span></span>
- <span data-ttu-id="826f9-126">**Código do motivo**</span><span class="sxs-lookup"><span data-stu-id="826f9-126">**Reason code**</span></span>
- <span data-ttu-id="826f9-127">**ID da Solicitação**</span><span class="sxs-lookup"><span data-stu-id="826f9-127">**Request ID**</span></span>
- <span data-ttu-id="826f9-128">**Data inicial**</span><span class="sxs-lookup"><span data-stu-id="826f9-128">**Start date**</span></span>
- <span data-ttu-id="826f9-129">**Status**</span><span class="sxs-lookup"><span data-stu-id="826f9-129">**Status**</span></span> 
- <span data-ttu-id="826f9-130">**Data de envio**</span><span class="sxs-lookup"><span data-stu-id="826f9-130">**Submission date**</span></span>
- <span data-ttu-id="826f9-131">**Envio feito por**</span><span class="sxs-lookup"><span data-stu-id="826f9-131">**Submitted by**</span></span>
- <span data-ttu-id="826f9-132">**Enviado pelo Recursos Humanos**</span><span class="sxs-lookup"><span data-stu-id="826f9-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="826f9-133">**Enviado pelo gerente**</span><span class="sxs-lookup"><span data-stu-id="826f9-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="826f9-134">**Enviado em nome de**</span><span class="sxs-lookup"><span data-stu-id="826f9-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="826f9-135">**Trabalhador**</span><span class="sxs-lookup"><span data-stu-id="826f9-135">**Worker**</span></span>
- <span data-ttu-id="826f9-136">**Tipo de trabalhador**</span><span class="sxs-lookup"><span data-stu-id="826f9-136">**Worker type**</span></span>

<span data-ttu-id="826f9-137">Esses exemplos mostram como é possível criar diferentes tipos de condições de fluxo de trabalho usando esses elementos de dados:</span><span class="sxs-lookup"><span data-stu-id="826f9-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="826f9-138">Use o **Código do motivo** em uma instrução condicional para rotear solicitações de licença de doença com o código de motivo **Cirurgia** para HR para aprovação, enquanto roteia todos os outros códigos de motivo para o gerente.</span><span class="sxs-lookup"><span data-stu-id="826f9-138">Use **Reason code** in a conditional statement to route sick leave requests with the reason code **Surgery** to HR for approval, while routing all other reason codes to the manager.</span></span> <span data-ttu-id="826f9-139">Para obter mais informações sobre instruções condicionais, consulte [Configurar decisões condicionais em um fluxo de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span><span class="sxs-lookup"><span data-stu-id="826f9-139">For more information about conditional statements, see [Configure conditional decisions in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span></span> 

- <span data-ttu-id="826f9-140">Use **Enviado por Human resources** e **Enviado pelo gerente** em uma ação automática para aprovar automaticamente solicitações de licença que essas funções submetem em nome dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="826f9-140">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="826f9-141">Para obter mais informações sobre ações automáticas, consulte [Configurar processos de aprovação em um fluxo de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="826f9-141">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="826f9-142">Use o **Tipo de licença** em uma instrução condicional ou ação automática para controlar como o fluxo de trabalho encaminha solicitações com certos tipos de licença.</span><span class="sxs-lookup"><span data-stu-id="826f9-142">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="826f9-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="826f9-143">See also</span></span>

- [<span data-ttu-id="826f9-144">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="826f9-144">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
