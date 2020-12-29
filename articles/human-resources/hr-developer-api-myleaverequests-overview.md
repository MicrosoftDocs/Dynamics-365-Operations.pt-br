---
title: Visão geral de MyLeaveRequests
description: A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417215"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="6eeb0-103">Visão geral de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="6eeb0-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="6eeb0-104">A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.</span><span class="sxs-lookup"><span data-stu-id="6eeb0-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="6eeb0-105">Chave</span><span class="sxs-lookup"><span data-stu-id="6eeb0-105">Key</span></span>

  | <span data-ttu-id="6eeb0-106">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="6eeb0-106">Property Name</span></span> | <span data-ttu-id="6eeb0-107">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="6eeb0-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="6eeb0-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="6eeb0-108">dataAreaId</span></span>    | <span data-ttu-id="6eeb0-109">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6eeb0-109">String</span></span>    |
  | <span data-ttu-id="6eeb0-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="6eeb0-110">RequestId</span></span>     | <span data-ttu-id="6eeb0-111">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6eeb0-111">String</span></span>    |
  | <span data-ttu-id="6eeb0-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="6eeb0-112">LeaveType</span></span>     | <span data-ttu-id="6eeb0-113">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6eeb0-113">String</span></span>    |
  | <span data-ttu-id="6eeb0-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="6eeb0-114">LeaveDate</span></span>     | <span data-ttu-id="6eeb0-115">Data </span><span class="sxs-lookup"><span data-stu-id="6eeb0-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="6eeb0-116">Propriedades</span><span class="sxs-lookup"><span data-stu-id="6eeb0-116">Properties</span></span>

  | <span data-ttu-id="6eeb0-117">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="6eeb0-117">Property Name</span></span>     | <span data-ttu-id="6eeb0-118">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="6eeb0-118">Data Type</span></span> | <span data-ttu-id="6eeb0-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="6eeb0-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="6eeb0-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="6eeb0-120">dataAreaId</span></span>        | <span data-ttu-id="6eeb0-121">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6eeb0-121">String</span></span>    | <span data-ttu-id="6eeb0-122">X</span><span class="sxs-lookup"><span data-stu-id="6eeb0-122">X</span></span>        |
  | <span data-ttu-id="6eeb0-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="6eeb0-123">RequestId</span></span>         | <span data-ttu-id="6eeb0-124">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6eeb0-124">String</span></span>    | <span data-ttu-id="6eeb0-125">X</span><span class="sxs-lookup"><span data-stu-id="6eeb0-125">X</span></span>        |
  | <span data-ttu-id="6eeb0-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="6eeb0-126">LeaveType</span></span>         | <span data-ttu-id="6eeb0-127">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6eeb0-127">String</span></span>    | <span data-ttu-id="6eeb0-128">X</span><span class="sxs-lookup"><span data-stu-id="6eeb0-128">X</span></span>        |
  | <span data-ttu-id="6eeb0-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="6eeb0-129">LeaveDate</span></span>         | <span data-ttu-id="6eeb0-130">Data </span><span class="sxs-lookup"><span data-stu-id="6eeb0-130">Date</span></span>      | <span data-ttu-id="6eeb0-131">X</span><span class="sxs-lookup"><span data-stu-id="6eeb0-131">X</span></span>        |
  | <span data-ttu-id="6eeb0-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="6eeb0-132">ReasonCodeId</span></span>      | <span data-ttu-id="6eeb0-133">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6eeb0-133">String</span></span>    |          |
  | <span data-ttu-id="6eeb0-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="6eeb0-134">PersonnelNumber</span></span>   | <span data-ttu-id="6eeb0-135">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6eeb0-135">String</span></span>    | <span data-ttu-id="6eeb0-136">X</span><span class="sxs-lookup"><span data-stu-id="6eeb0-136">X</span></span>        |
  | <span data-ttu-id="6eeb0-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="6eeb0-137">RequestDate</span></span>       | <span data-ttu-id="6eeb0-138">Data </span><span class="sxs-lookup"><span data-stu-id="6eeb0-138">Date</span></span>      | <span data-ttu-id="6eeb0-139">X</span><span class="sxs-lookup"><span data-stu-id="6eeb0-139">X</span></span>        |
  | <span data-ttu-id="6eeb0-140">Comentário</span><span class="sxs-lookup"><span data-stu-id="6eeb0-140">Comment</span></span>           | <span data-ttu-id="6eeb0-141">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6eeb0-141">String</span></span>    |          |
  | <span data-ttu-id="6eeb0-142">Status</span><span class="sxs-lookup"><span data-stu-id="6eeb0-142">Status</span></span>            | <span data-ttu-id="6eeb0-143">Enumeração</span><span class="sxs-lookup"><span data-stu-id="6eeb0-143">Enum</span></span>      | <span data-ttu-id="6eeb0-144">X</span><span class="sxs-lookup"><span data-stu-id="6eeb0-144">X</span></span>        |
  | <span data-ttu-id="6eeb0-145">Valor</span><span class="sxs-lookup"><span data-stu-id="6eeb0-145">Amount</span></span>            | <span data-ttu-id="6eeb0-146">Real</span><span class="sxs-lookup"><span data-stu-id="6eeb0-146">Real</span></span>      |          |
  | <span data-ttu-id="6eeb0-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="6eeb0-147">HalfDayDefinition</span></span> | <span data-ttu-id="6eeb0-148">Enumeração</span><span class="sxs-lookup"><span data-stu-id="6eeb0-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="6eeb0-149">Ações</span><span class="sxs-lookup"><span data-stu-id="6eeb0-149">Actions</span></span>

 | <span data-ttu-id="6eeb0-150">Nome da Ação</span><span class="sxs-lookup"><span data-stu-id="6eeb0-150">Action Name</span></span>                               | <span data-ttu-id="6eeb0-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="6eeb0-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="6eeb0-152">enviar</span><span class="sxs-lookup"><span data-stu-id="6eeb0-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="6eeb0-153">Envie a solicitação para ser processada pelo fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6eeb0-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="6eeb0-154">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6eeb0-154">See also</span></span>

- [<span data-ttu-id="6eeb0-155">Enviar uma solicitação de licença para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="6eeb0-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="6eeb0-156">Autenticação</span><span class="sxs-lookup"><span data-stu-id="6eeb0-156">Authentication</span></span>](hr-developer-api-authentication.md)