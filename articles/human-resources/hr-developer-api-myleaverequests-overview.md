---
title: Visão geral de MyLeaveRequests
description: A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: c2c14a0cc935ad166a2c6600f1e96c3e09ab16ca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465501"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="01e06-103">Visão geral de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="01e06-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="01e06-104">A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.</span><span class="sxs-lookup"><span data-stu-id="01e06-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="01e06-105">Chave</span><span class="sxs-lookup"><span data-stu-id="01e06-105">Key</span></span>

  | <span data-ttu-id="01e06-106">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="01e06-106">Property Name</span></span> | <span data-ttu-id="01e06-107">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="01e06-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="01e06-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="01e06-108">dataAreaId</span></span>    | <span data-ttu-id="01e06-109">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e06-109">String</span></span>    |
  | <span data-ttu-id="01e06-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="01e06-110">RequestId</span></span>     | <span data-ttu-id="01e06-111">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e06-111">String</span></span>    |
  | <span data-ttu-id="01e06-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="01e06-112">LeaveType</span></span>     | <span data-ttu-id="01e06-113">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e06-113">String</span></span>    |
  | <span data-ttu-id="01e06-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="01e06-114">LeaveDate</span></span>     | <span data-ttu-id="01e06-115">Data </span><span class="sxs-lookup"><span data-stu-id="01e06-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="01e06-116">Propriedades</span><span class="sxs-lookup"><span data-stu-id="01e06-116">Properties</span></span>

  | <span data-ttu-id="01e06-117">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="01e06-117">Property Name</span></span>     | <span data-ttu-id="01e06-118">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="01e06-118">Data Type</span></span> | <span data-ttu-id="01e06-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="01e06-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="01e06-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="01e06-120">dataAreaId</span></span>        | <span data-ttu-id="01e06-121">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e06-121">String</span></span>    | <span data-ttu-id="01e06-122">X</span><span class="sxs-lookup"><span data-stu-id="01e06-122">X</span></span>        |
  | <span data-ttu-id="01e06-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="01e06-123">RequestId</span></span>         | <span data-ttu-id="01e06-124">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e06-124">String</span></span>    | <span data-ttu-id="01e06-125">X</span><span class="sxs-lookup"><span data-stu-id="01e06-125">X</span></span>        |
  | <span data-ttu-id="01e06-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="01e06-126">LeaveType</span></span>         | <span data-ttu-id="01e06-127">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e06-127">String</span></span>    | <span data-ttu-id="01e06-128">X</span><span class="sxs-lookup"><span data-stu-id="01e06-128">X</span></span>        |
  | <span data-ttu-id="01e06-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="01e06-129">LeaveDate</span></span>         | <span data-ttu-id="01e06-130">Data </span><span class="sxs-lookup"><span data-stu-id="01e06-130">Date</span></span>      | <span data-ttu-id="01e06-131">X</span><span class="sxs-lookup"><span data-stu-id="01e06-131">X</span></span>        |
  | <span data-ttu-id="01e06-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="01e06-132">ReasonCodeId</span></span>      | <span data-ttu-id="01e06-133">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e06-133">String</span></span>    |          |
  | <span data-ttu-id="01e06-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="01e06-134">PersonnelNumber</span></span>   | <span data-ttu-id="01e06-135">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e06-135">String</span></span>    | <span data-ttu-id="01e06-136">X</span><span class="sxs-lookup"><span data-stu-id="01e06-136">X</span></span>        |
  | <span data-ttu-id="01e06-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="01e06-137">RequestDate</span></span>       | <span data-ttu-id="01e06-138">Data </span><span class="sxs-lookup"><span data-stu-id="01e06-138">Date</span></span>      | <span data-ttu-id="01e06-139">X</span><span class="sxs-lookup"><span data-stu-id="01e06-139">X</span></span>        |
  | <span data-ttu-id="01e06-140">Comentário</span><span class="sxs-lookup"><span data-stu-id="01e06-140">Comment</span></span>           | <span data-ttu-id="01e06-141">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="01e06-141">String</span></span>    |          |
  | <span data-ttu-id="01e06-142">Status</span><span class="sxs-lookup"><span data-stu-id="01e06-142">Status</span></span>            | <span data-ttu-id="01e06-143">Enumeração</span><span class="sxs-lookup"><span data-stu-id="01e06-143">Enum</span></span>      | <span data-ttu-id="01e06-144">X</span><span class="sxs-lookup"><span data-stu-id="01e06-144">X</span></span>        |
  | <span data-ttu-id="01e06-145">Valor</span><span class="sxs-lookup"><span data-stu-id="01e06-145">Amount</span></span>            | <span data-ttu-id="01e06-146">Real</span><span class="sxs-lookup"><span data-stu-id="01e06-146">Real</span></span>      |          |
  | <span data-ttu-id="01e06-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="01e06-147">HalfDayDefinition</span></span> | <span data-ttu-id="01e06-148">Enumeração</span><span class="sxs-lookup"><span data-stu-id="01e06-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="01e06-149">Ações</span><span class="sxs-lookup"><span data-stu-id="01e06-149">Actions</span></span>

 | <span data-ttu-id="01e06-150">Nome da Ação</span><span class="sxs-lookup"><span data-stu-id="01e06-150">Action Name</span></span>                               | <span data-ttu-id="01e06-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="01e06-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="01e06-152">enviar</span><span class="sxs-lookup"><span data-stu-id="01e06-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="01e06-153">Envie a solicitação para ser processada pelo fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="01e06-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="01e06-154">Consulte também</span><span class="sxs-lookup"><span data-stu-id="01e06-154">See also</span></span>

- [<span data-ttu-id="01e06-155">Enviar uma solicitação de licença para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="01e06-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="01e06-156">Autenticação</span><span class="sxs-lookup"><span data-stu-id="01e06-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]