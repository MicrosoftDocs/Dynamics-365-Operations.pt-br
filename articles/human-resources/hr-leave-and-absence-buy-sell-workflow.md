---
title: Criar um fluxo de trabalho de solicitação de compra e venda de licenças
description: Cria um fluxo de trabalho de solicitação de compra e venda de licenças para gerenciar as solicitações de licença de compra e venda de forma consistente no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 08/20/2020
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
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5bc31740218e3f171d89debace339dee0177d826
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053962"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="72dea-103">Criar um fluxo de trabalho de solicitação de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="72dea-103">Create a buy and sell leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="72dea-104">Você pode criar um fluxo de trabalho no Dynamics 365 Human Resources para gerenciar as solicitações de compra e venda de licença de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="72dea-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your buy and sell leave requests.</span></span> <span data-ttu-id="72dea-105">Um fluxo de trabalho **Comprar e vender licença** permite:</span><span class="sxs-lookup"><span data-stu-id="72dea-105">A **Buy and sell leave** workflow lets you:</span></span>

- <span data-ttu-id="72dea-106">Definir tarefas</span><span class="sxs-lookup"><span data-stu-id="72dea-106">Define tasks</span></span>
- <span data-ttu-id="72dea-107">Determinar quem deve concluir as tarefas</span><span class="sxs-lookup"><span data-stu-id="72dea-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="72dea-108">Especificar quem pode aprovar ou rejeitar solicitações</span><span class="sxs-lookup"><span data-stu-id="72dea-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="72dea-109">Criar um fluxo de trabalho de solicitação de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="72dea-109">Create a buy and sell leave request workflow</span></span>

1. <span data-ttu-id="72dea-110">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="72dea-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="72dea-111">Em **Configuração**, selecione **Fluxos de trabalho de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="72dea-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="72dea-112">Selecione **Novo** e **Solicitação de compra e venda de licença**.</span><span class="sxs-lookup"><span data-stu-id="72dea-112">Select **New**, and then select **Buy and sell leave request**.</span></span> 

4. <span data-ttu-id="72dea-113">Quando aparecer a caixa de mensagem **Abrir este arquivo?**, selecione **Abrir** e faça login com as credenciais da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="72dea-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="72dea-114">Use o editor de fluxo de trabalho para criar um fluxo de trabalho para suas solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="72dea-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="72dea-115">Para obter mais informações sobre como trabalhar com fluxos de trabalho, consulte [Visão geral de criação de fluxos de trabalho](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span><span class="sxs-lookup"><span data-stu-id="72dea-115">For more information about working with workflows, see [Create workflows overview](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="72dea-116">Elementos de dados de fluxo de trabalho de solicitação de licenças e ausências</span><span class="sxs-lookup"><span data-stu-id="72dea-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="72dea-117">Você pode usar os elementos de dados a seguir para criar aprovações condicionais ou automáticas em fluxos de trabalho para solicitações de compra e venda de licença:</span><span class="sxs-lookup"><span data-stu-id="72dea-117">You can use the following data elements to create conditional or automatic approvals in workflows for buy and sell leave requests:</span></span>

- <span data-ttu-id="72dea-118">**Valor**</span><span class="sxs-lookup"><span data-stu-id="72dea-118">**Amount**</span></span>
- <span data-ttu-id="72dea-119">**Política de compra e venda de licenças**</span><span class="sxs-lookup"><span data-stu-id="72dea-119">**Buy and sell leave policy**</span></span>
- <span data-ttu-id="72dea-120">**Empresa**</span><span class="sxs-lookup"><span data-stu-id="72dea-120">**Company**</span></span>
- <span data-ttu-id="72dea-121">**Criado por**</span><span class="sxs-lookup"><span data-stu-id="72dea-121">**Created by**</span></span>
- <span data-ttu-id="72dea-122">**Data e hora de criação**</span><span class="sxs-lookup"><span data-stu-id="72dea-122">**Created date and time**</span></span>
- <span data-ttu-id="72dea-123">**Data de término**</span><span class="sxs-lookup"><span data-stu-id="72dea-123">**End date**</span></span>
- <span data-ttu-id="72dea-124">**Tipo de licença**</span><span class="sxs-lookup"><span data-stu-id="72dea-124">**Leave type**</span></span>
- <span data-ttu-id="72dea-125">**Modificação de**</span><span class="sxs-lookup"><span data-stu-id="72dea-125">**Modified by**</span></span>
- <span data-ttu-id="72dea-126">**Data e hora da modificação**</span><span class="sxs-lookup"><span data-stu-id="72dea-126">**Modified date and time**</span></span>
- <span data-ttu-id="72dea-127">**ID da Solicitação**</span><span class="sxs-lookup"><span data-stu-id="72dea-127">**Request ID**</span></span>
- <span data-ttu-id="72dea-128">**Data inicial:**</span><span class="sxs-lookup"><span data-stu-id="72dea-128">**Start date**</span></span>
- <span data-ttu-id="72dea-129">**Status**</span><span class="sxs-lookup"><span data-stu-id="72dea-129">**Status**</span></span> 
- <span data-ttu-id="72dea-130">**Data de envio**</span><span class="sxs-lookup"><span data-stu-id="72dea-130">**Submission date**</span></span>
- <span data-ttu-id="72dea-131">**Envio feito por**</span><span class="sxs-lookup"><span data-stu-id="72dea-131">**Submitted by**</span></span>
- <span data-ttu-id="72dea-132">**Enviado pelo Recursos Humanos**</span><span class="sxs-lookup"><span data-stu-id="72dea-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="72dea-133">**Enviado pelo gerente**</span><span class="sxs-lookup"><span data-stu-id="72dea-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="72dea-134">**Enviado em nome de**</span><span class="sxs-lookup"><span data-stu-id="72dea-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="72dea-135">**Trabalhador**</span><span class="sxs-lookup"><span data-stu-id="72dea-135">**Worker**</span></span>

## <a name="workflow-examples"></a><span data-ttu-id="72dea-136">Exemplos de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="72dea-136">Workflow examples</span></span>

<span data-ttu-id="72dea-137">Esses exemplos mostram como é possível criar diferentes tipos de condições de fluxo de trabalho usando esses elementos de dados:</span><span class="sxs-lookup"><span data-stu-id="72dea-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="72dea-138">Use **Enviado pelo Recursos Humanos** e **Enviado pelo gerente** em uma ação automática para aprovar automaticamente solicitações de compra e venda de licença que essas funções enviam em nome dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="72dea-138">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve buy and sell leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="72dea-139">Para obter mais informações sobre ações automáticas, consulte [Configurar processos de aprovação em um fluxo de trabalho](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="72dea-139">For more information about automatic actions, see [Configure approval processes in a workflow](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).</span></span>

- <span data-ttu-id="72dea-140">Use o **Tipo de licença** em uma instrução condicional ou ação automática para controlar como o fluxo de trabalho encaminha solicitações com certos tipos de licença.</span><span class="sxs-lookup"><span data-stu-id="72dea-140">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="72dea-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="72dea-141">See also</span></span>

[<span data-ttu-id="72dea-142">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="72dea-142">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)<br>
[<span data-ttu-id="72dea-143">Gerenciar políticas de compra e venda de licenças</span><span class="sxs-lookup"><span data-stu-id="72dea-143">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]