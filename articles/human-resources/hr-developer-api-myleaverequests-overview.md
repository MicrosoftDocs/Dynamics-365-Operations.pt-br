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
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092028"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="f7281-103">Visão geral de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="f7281-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="f7281-104">A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.</span><span class="sxs-lookup"><span data-stu-id="f7281-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="f7281-105">Chave</span><span class="sxs-lookup"><span data-stu-id="f7281-105">Key</span></span>

  | <span data-ttu-id="f7281-106">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="f7281-106">Property Name</span></span> | <span data-ttu-id="f7281-107">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="f7281-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="f7281-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="f7281-108">dataAreaId</span></span>    | <span data-ttu-id="f7281-109">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="f7281-109">String</span></span>    |
  | <span data-ttu-id="f7281-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="f7281-110">RequestId</span></span>     | <span data-ttu-id="f7281-111">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="f7281-111">String</span></span>    |
  | <span data-ttu-id="f7281-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="f7281-112">LeaveType</span></span>     | <span data-ttu-id="f7281-113">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="f7281-113">String</span></span>    |
  | <span data-ttu-id="f7281-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="f7281-114">LeaveDate</span></span>     | <span data-ttu-id="f7281-115">Data </span><span class="sxs-lookup"><span data-stu-id="f7281-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="f7281-116">Propriedades</span><span class="sxs-lookup"><span data-stu-id="f7281-116">Properties</span></span>

  | <span data-ttu-id="f7281-117">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="f7281-117">Property Name</span></span>     | <span data-ttu-id="f7281-118">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="f7281-118">Data Type</span></span> | <span data-ttu-id="f7281-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="f7281-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="f7281-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="f7281-120">dataAreaId</span></span>        | <span data-ttu-id="f7281-121">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="f7281-121">String</span></span>    | <span data-ttu-id="f7281-122">X</span><span class="sxs-lookup"><span data-stu-id="f7281-122">X</span></span>        |
  | <span data-ttu-id="f7281-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="f7281-123">RequestId</span></span>         | <span data-ttu-id="f7281-124">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="f7281-124">String</span></span>    | <span data-ttu-id="f7281-125">X</span><span class="sxs-lookup"><span data-stu-id="f7281-125">X</span></span>        |
  | <span data-ttu-id="f7281-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="f7281-126">LeaveType</span></span>         | <span data-ttu-id="f7281-127">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="f7281-127">String</span></span>    | <span data-ttu-id="f7281-128">X</span><span class="sxs-lookup"><span data-stu-id="f7281-128">X</span></span>        |
  | <span data-ttu-id="f7281-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="f7281-129">LeaveDate</span></span>         | <span data-ttu-id="f7281-130">Data </span><span class="sxs-lookup"><span data-stu-id="f7281-130">Date</span></span>      | <span data-ttu-id="f7281-131">X</span><span class="sxs-lookup"><span data-stu-id="f7281-131">X</span></span>        |
  | <span data-ttu-id="f7281-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="f7281-132">ReasonCodeId</span></span>      | <span data-ttu-id="f7281-133">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="f7281-133">String</span></span>    |          |
  | <span data-ttu-id="f7281-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="f7281-134">PersonnelNumber</span></span>   | <span data-ttu-id="f7281-135">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="f7281-135">String</span></span>    | <span data-ttu-id="f7281-136">X</span><span class="sxs-lookup"><span data-stu-id="f7281-136">X</span></span>        |
  | <span data-ttu-id="f7281-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="f7281-137">RequestDate</span></span>       | <span data-ttu-id="f7281-138">Data </span><span class="sxs-lookup"><span data-stu-id="f7281-138">Date</span></span>      | <span data-ttu-id="f7281-139">X</span><span class="sxs-lookup"><span data-stu-id="f7281-139">X</span></span>        |
  | <span data-ttu-id="f7281-140">Comentário</span><span class="sxs-lookup"><span data-stu-id="f7281-140">Comment</span></span>           | <span data-ttu-id="f7281-141">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="f7281-141">String</span></span>    |          |
  | <span data-ttu-id="f7281-142">Status</span><span class="sxs-lookup"><span data-stu-id="f7281-142">Status</span></span>            | <span data-ttu-id="f7281-143">Enumeração</span><span class="sxs-lookup"><span data-stu-id="f7281-143">Enum</span></span>      | <span data-ttu-id="f7281-144">X</span><span class="sxs-lookup"><span data-stu-id="f7281-144">X</span></span>        |
  | <span data-ttu-id="f7281-145">Valor</span><span class="sxs-lookup"><span data-stu-id="f7281-145">Amount</span></span>            | <span data-ttu-id="f7281-146">Real</span><span class="sxs-lookup"><span data-stu-id="f7281-146">Real</span></span>      |          |
  | <span data-ttu-id="f7281-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="f7281-147">HalfDayDefinition</span></span> | <span data-ttu-id="f7281-148">Enumeração</span><span class="sxs-lookup"><span data-stu-id="f7281-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="f7281-149">Ações</span><span class="sxs-lookup"><span data-stu-id="f7281-149">Actions</span></span>

 | <span data-ttu-id="f7281-150">Nome da Ação</span><span class="sxs-lookup"><span data-stu-id="f7281-150">Action Name</span></span>                               | <span data-ttu-id="f7281-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="f7281-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="f7281-152">enviar</span><span class="sxs-lookup"><span data-stu-id="f7281-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="f7281-153">Envie a solicitação para ser processada pelo fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f7281-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f7281-154">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f7281-154">See also</span></span>

- [<span data-ttu-id="f7281-155">Enviar uma solicitação de licença para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f7281-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="f7281-156">Autenticação</span><span class="sxs-lookup"><span data-stu-id="f7281-156">Authentication</span></span>](hr-developer-api-authentication.md)