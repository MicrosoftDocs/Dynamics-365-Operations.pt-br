---
title: Criar um fluxo de trabalho de solicitação de compra e venda de licenças
description: Cria um fluxo de trabalho de solicitação de compra e venda de licenças para gerenciar as solicitações de licença de compra e venda de forma consistente no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d490e0c36ea0e854c5d7afc5b3bf75f6b65e542c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417339"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="5543b-103">Criar um fluxo de trabalho de solicitação de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="5543b-103">Create a buy and sell leave request workflow</span></span>

<span data-ttu-id="5543b-104">Você pode criar um fluxo de trabalho no Dynamics 365 Human Resources para gerenciar as solicitações de compra e venda de licença de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="5543b-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your buy and sell leave requests.</span></span> <span data-ttu-id="5543b-105">Um fluxo de trabalho **Comprar e vender licença** permite:</span><span class="sxs-lookup"><span data-stu-id="5543b-105">A **Buy and sell leave** workflow lets you:</span></span>

- <span data-ttu-id="5543b-106">Definir tarefas</span><span class="sxs-lookup"><span data-stu-id="5543b-106">Define tasks</span></span>
- <span data-ttu-id="5543b-107">Determinar quem deve concluir as tarefas</span><span class="sxs-lookup"><span data-stu-id="5543b-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="5543b-108">Especificar quem pode aprovar ou rejeitar solicitações</span><span class="sxs-lookup"><span data-stu-id="5543b-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="5543b-109">Criar um fluxo de trabalho de solicitação de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="5543b-109">Create a buy and sell leave request workflow</span></span>

1. <span data-ttu-id="5543b-110">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="5543b-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="5543b-111">Em **Configuração**, selecione **Fluxos de trabalho de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="5543b-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="5543b-112">Selecione **Novo** e **Solicitação de compra e venda de licença**.</span><span class="sxs-lookup"><span data-stu-id="5543b-112">Select **New**, and then select **Buy and sell leave request**.</span></span> 

4. <span data-ttu-id="5543b-113">Quando aparecer a caixa de mensagem **Abrir este arquivo?**, selecione **Abrir** e faça login com as credenciais da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="5543b-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="5543b-114">Use o editor de fluxo de trabalho para criar um fluxo de trabalho para suas solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="5543b-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="5543b-115">Para obter mais informações sobre como trabalhar com fluxos de trabalho, consulte [Visão geral de criação de fluxos de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="5543b-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="5543b-116">Elementos de dados de fluxo de trabalho de solicitação de licenças e ausências</span><span class="sxs-lookup"><span data-stu-id="5543b-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="5543b-117">Você pode usar os elementos de dados a seguir para criar aprovações condicionais ou automáticas em fluxos de trabalho para solicitações de compra e venda de licença:</span><span class="sxs-lookup"><span data-stu-id="5543b-117">You can use the following data elements to create conditional or automatic approvals in workflows for buy and sell leave requests:</span></span>

- <span data-ttu-id="5543b-118">**Valor**</span><span class="sxs-lookup"><span data-stu-id="5543b-118">**Amount**</span></span>
- <span data-ttu-id="5543b-119">**Política de compra e venda de licenças**</span><span class="sxs-lookup"><span data-stu-id="5543b-119">**Buy and sell leave policy**</span></span>
- <span data-ttu-id="5543b-120">**Empresa**</span><span class="sxs-lookup"><span data-stu-id="5543b-120">**Company**</span></span>
- <span data-ttu-id="5543b-121">**Criado por**</span><span class="sxs-lookup"><span data-stu-id="5543b-121">**Created by**</span></span>
- <span data-ttu-id="5543b-122">**Data e hora de criação**</span><span class="sxs-lookup"><span data-stu-id="5543b-122">**Created date and time**</span></span>
- <span data-ttu-id="5543b-123">**Data de término**</span><span class="sxs-lookup"><span data-stu-id="5543b-123">**End date**</span></span>
- <span data-ttu-id="5543b-124">**Tipo de licença**</span><span class="sxs-lookup"><span data-stu-id="5543b-124">**Leave type**</span></span>
- <span data-ttu-id="5543b-125">**Modificação de**</span><span class="sxs-lookup"><span data-stu-id="5543b-125">**Modified by**</span></span>
- <span data-ttu-id="5543b-126">**Data e hora da modificação**</span><span class="sxs-lookup"><span data-stu-id="5543b-126">**Modified date and time**</span></span>
- <span data-ttu-id="5543b-127">**ID da Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5543b-127">**Request ID**</span></span>
- <span data-ttu-id="5543b-128">**Data inicial:**</span><span class="sxs-lookup"><span data-stu-id="5543b-128">**Start date**</span></span>
- <span data-ttu-id="5543b-129">**Status**</span><span class="sxs-lookup"><span data-stu-id="5543b-129">**Status**</span></span> 
- <span data-ttu-id="5543b-130">**Data de envio**</span><span class="sxs-lookup"><span data-stu-id="5543b-130">**Submission date**</span></span>
- <span data-ttu-id="5543b-131">**Envio feito por**</span><span class="sxs-lookup"><span data-stu-id="5543b-131">**Submitted by**</span></span>
- <span data-ttu-id="5543b-132">**Enviado pelo Recursos Humanos**</span><span class="sxs-lookup"><span data-stu-id="5543b-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="5543b-133">**Enviado pelo gerente**</span><span class="sxs-lookup"><span data-stu-id="5543b-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="5543b-134">**Enviado em nome de**</span><span class="sxs-lookup"><span data-stu-id="5543b-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="5543b-135">**Trabalhador**</span><span class="sxs-lookup"><span data-stu-id="5543b-135">**Worker**</span></span>

## <a name="workflow-examples"></a><span data-ttu-id="5543b-136">Exemplos de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="5543b-136">Workflow examples</span></span>

<span data-ttu-id="5543b-137">Esses exemplos mostram como é possível criar diferentes tipos de condições de fluxo de trabalho usando esses elementos de dados:</span><span class="sxs-lookup"><span data-stu-id="5543b-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="5543b-138">Use **Enviado pelo Recursos Humanos** e **Enviado pelo gerente** em uma ação automática para aprovar automaticamente solicitações de compra e venda de licença que essas funções enviam em nome dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="5543b-138">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve buy and sell leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="5543b-139">Para obter mais informações sobre ações automáticas, consulte [Configurar processos de aprovação em um fluxo de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="5543b-139">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="5543b-140">Use o **Tipo de licença** em uma instrução condicional ou ação automática para controlar como o fluxo de trabalho encaminha solicitações com certos tipos de licença.</span><span class="sxs-lookup"><span data-stu-id="5543b-140">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="5543b-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5543b-141">See also</span></span>

[<span data-ttu-id="5543b-142">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="5543b-142">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)<br>
[<span data-ttu-id="5543b-143">Gerenciar políticas de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="5543b-143">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)

