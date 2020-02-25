---
title: Visão geral de MyLeaveRequests
description: ''
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
ms.openlocfilehash: 66f161d6736b1bb544d02871d9d51b2949b1cfa0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008087"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="94bb2-102">Visão geral de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="94bb2-102">MyLeaveRequests overview</span></span>

<span data-ttu-id="94bb2-103">A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.</span><span class="sxs-lookup"><span data-stu-id="94bb2-103">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="94bb2-104">Chave</span><span class="sxs-lookup"><span data-stu-id="94bb2-104">Key</span></span>

  | <span data-ttu-id="94bb2-105">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="94bb2-105">Property Name</span></span> | <span data-ttu-id="94bb2-106">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="94bb2-106">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="94bb2-107">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="94bb2-107">dataAreaId</span></span>    | <span data-ttu-id="94bb2-108">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="94bb2-108">String</span></span>    |
  | <span data-ttu-id="94bb2-109">RequestId</span><span class="sxs-lookup"><span data-stu-id="94bb2-109">RequestId</span></span>     | <span data-ttu-id="94bb2-110">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="94bb2-110">String</span></span>    |
  | <span data-ttu-id="94bb2-111">LeaveType</span><span class="sxs-lookup"><span data-stu-id="94bb2-111">LeaveType</span></span>     | <span data-ttu-id="94bb2-112">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="94bb2-112">String</span></span>    |
  | <span data-ttu-id="94bb2-113">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="94bb2-113">LeaveDate</span></span>     | <span data-ttu-id="94bb2-114">Data </span><span class="sxs-lookup"><span data-stu-id="94bb2-114">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="94bb2-115">Propriedades</span><span class="sxs-lookup"><span data-stu-id="94bb2-115">Properties</span></span>

  | <span data-ttu-id="94bb2-116">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="94bb2-116">Property Name</span></span>     | <span data-ttu-id="94bb2-117">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="94bb2-117">Data Type</span></span> | <span data-ttu-id="94bb2-118">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="94bb2-118">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="94bb2-119">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="94bb2-119">dataAreaId</span></span>        | <span data-ttu-id="94bb2-120">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="94bb2-120">String</span></span>    | <span data-ttu-id="94bb2-121">X</span><span class="sxs-lookup"><span data-stu-id="94bb2-121">X</span></span>        |
  | <span data-ttu-id="94bb2-122">RequestId</span><span class="sxs-lookup"><span data-stu-id="94bb2-122">RequestId</span></span>         | <span data-ttu-id="94bb2-123">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="94bb2-123">String</span></span>    | <span data-ttu-id="94bb2-124">X</span><span class="sxs-lookup"><span data-stu-id="94bb2-124">X</span></span>        |
  | <span data-ttu-id="94bb2-125">LeaveType</span><span class="sxs-lookup"><span data-stu-id="94bb2-125">LeaveType</span></span>         | <span data-ttu-id="94bb2-126">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="94bb2-126">String</span></span>    | <span data-ttu-id="94bb2-127">X</span><span class="sxs-lookup"><span data-stu-id="94bb2-127">X</span></span>        |
  | <span data-ttu-id="94bb2-128">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="94bb2-128">LeaveDate</span></span>         | <span data-ttu-id="94bb2-129">Data </span><span class="sxs-lookup"><span data-stu-id="94bb2-129">Date</span></span>      | <span data-ttu-id="94bb2-130">X</span><span class="sxs-lookup"><span data-stu-id="94bb2-130">X</span></span>        |
  | <span data-ttu-id="94bb2-131">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="94bb2-131">ReasonCodeId</span></span>      | <span data-ttu-id="94bb2-132">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="94bb2-132">String</span></span>    |          |
  | <span data-ttu-id="94bb2-133">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="94bb2-133">PersonnelNumber</span></span>   | <span data-ttu-id="94bb2-134">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="94bb2-134">String</span></span>    | <span data-ttu-id="94bb2-135">X</span><span class="sxs-lookup"><span data-stu-id="94bb2-135">X</span></span>        |
  | <span data-ttu-id="94bb2-136">RequestDate</span><span class="sxs-lookup"><span data-stu-id="94bb2-136">RequestDate</span></span>       | <span data-ttu-id="94bb2-137">Data </span><span class="sxs-lookup"><span data-stu-id="94bb2-137">Date</span></span>      | <span data-ttu-id="94bb2-138">X</span><span class="sxs-lookup"><span data-stu-id="94bb2-138">X</span></span>        |
  | <span data-ttu-id="94bb2-139">Comentário</span><span class="sxs-lookup"><span data-stu-id="94bb2-139">Comment</span></span>           | <span data-ttu-id="94bb2-140">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="94bb2-140">String</span></span>    |          |
  | <span data-ttu-id="94bb2-141">Status</span><span class="sxs-lookup"><span data-stu-id="94bb2-141">Status</span></span>            | <span data-ttu-id="94bb2-142">Enumeração</span><span class="sxs-lookup"><span data-stu-id="94bb2-142">Enum</span></span>      | <span data-ttu-id="94bb2-143">X</span><span class="sxs-lookup"><span data-stu-id="94bb2-143">X</span></span>        |
  | <span data-ttu-id="94bb2-144">Valor</span><span class="sxs-lookup"><span data-stu-id="94bb2-144">Amount</span></span>            | <span data-ttu-id="94bb2-145">Real</span><span class="sxs-lookup"><span data-stu-id="94bb2-145">Real</span></span>      |          |
  | <span data-ttu-id="94bb2-146">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="94bb2-146">HalfDayDefinition</span></span> | <span data-ttu-id="94bb2-147">Enumeração</span><span class="sxs-lookup"><span data-stu-id="94bb2-147">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="94bb2-148">Ações</span><span class="sxs-lookup"><span data-stu-id="94bb2-148">Actions</span></span>

 | <span data-ttu-id="94bb2-149">Nome da Ação</span><span class="sxs-lookup"><span data-stu-id="94bb2-149">Action Name</span></span>                               | <span data-ttu-id="94bb2-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="94bb2-150">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="94bb2-151">enviar</span><span class="sxs-lookup"><span data-stu-id="94bb2-151">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="94bb2-152">Envie a solicitação para ser processada pelo fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="94bb2-152">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="94bb2-153">Consulte também</span><span class="sxs-lookup"><span data-stu-id="94bb2-153">See also</span></span>

- [<span data-ttu-id="94bb2-154">Enviar uma solicitação de licença para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="94bb2-154">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="94bb2-155">Autenticação</span><span class="sxs-lookup"><span data-stu-id="94bb2-155">Authentication</span></span>](hr-developer-api-authentication.md)