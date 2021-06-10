---
title: Visão geral de MyLeaveRequests
description: A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f29d5cf1469b58b4ea1837dc82b9513f5c002609
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054947"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="ccf8a-103">Visão geral de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="ccf8a-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ccf8a-104">A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.</span><span class="sxs-lookup"><span data-stu-id="ccf8a-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="ccf8a-105">Chave</span><span class="sxs-lookup"><span data-stu-id="ccf8a-105">Key</span></span>

  | <span data-ttu-id="ccf8a-106">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="ccf8a-106">Property Name</span></span> | <span data-ttu-id="ccf8a-107">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="ccf8a-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="ccf8a-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="ccf8a-108">dataAreaId</span></span>    | <span data-ttu-id="ccf8a-109">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="ccf8a-109">String</span></span>    |
  | <span data-ttu-id="ccf8a-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="ccf8a-110">RequestId</span></span>     | <span data-ttu-id="ccf8a-111">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="ccf8a-111">String</span></span>    |
  | <span data-ttu-id="ccf8a-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="ccf8a-112">LeaveType</span></span>     | <span data-ttu-id="ccf8a-113">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="ccf8a-113">String</span></span>    |
  | <span data-ttu-id="ccf8a-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="ccf8a-114">LeaveDate</span></span>     | <span data-ttu-id="ccf8a-115">Data </span><span class="sxs-lookup"><span data-stu-id="ccf8a-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="ccf8a-116">Propriedades</span><span class="sxs-lookup"><span data-stu-id="ccf8a-116">Properties</span></span>

  | <span data-ttu-id="ccf8a-117">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="ccf8a-117">Property Name</span></span>     | <span data-ttu-id="ccf8a-118">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="ccf8a-118">Data Type</span></span> | <span data-ttu-id="ccf8a-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="ccf8a-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="ccf8a-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="ccf8a-120">dataAreaId</span></span>        | <span data-ttu-id="ccf8a-121">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="ccf8a-121">String</span></span>    | <span data-ttu-id="ccf8a-122">X</span><span class="sxs-lookup"><span data-stu-id="ccf8a-122">X</span></span>        |
  | <span data-ttu-id="ccf8a-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="ccf8a-123">RequestId</span></span>         | <span data-ttu-id="ccf8a-124">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="ccf8a-124">String</span></span>    | <span data-ttu-id="ccf8a-125">X</span><span class="sxs-lookup"><span data-stu-id="ccf8a-125">X</span></span>        |
  | <span data-ttu-id="ccf8a-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="ccf8a-126">LeaveType</span></span>         | <span data-ttu-id="ccf8a-127">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="ccf8a-127">String</span></span>    | <span data-ttu-id="ccf8a-128">X</span><span class="sxs-lookup"><span data-stu-id="ccf8a-128">X</span></span>        |
  | <span data-ttu-id="ccf8a-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="ccf8a-129">LeaveDate</span></span>         | <span data-ttu-id="ccf8a-130">Data </span><span class="sxs-lookup"><span data-stu-id="ccf8a-130">Date</span></span>      | <span data-ttu-id="ccf8a-131">X</span><span class="sxs-lookup"><span data-stu-id="ccf8a-131">X</span></span>        |
  | <span data-ttu-id="ccf8a-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="ccf8a-132">ReasonCodeId</span></span>      | <span data-ttu-id="ccf8a-133">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="ccf8a-133">String</span></span>    |          |
  | <span data-ttu-id="ccf8a-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="ccf8a-134">PersonnelNumber</span></span>   | <span data-ttu-id="ccf8a-135">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="ccf8a-135">String</span></span>    | <span data-ttu-id="ccf8a-136">X</span><span class="sxs-lookup"><span data-stu-id="ccf8a-136">X</span></span>        |
  | <span data-ttu-id="ccf8a-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="ccf8a-137">RequestDate</span></span>       | <span data-ttu-id="ccf8a-138">Data </span><span class="sxs-lookup"><span data-stu-id="ccf8a-138">Date</span></span>      | <span data-ttu-id="ccf8a-139">X</span><span class="sxs-lookup"><span data-stu-id="ccf8a-139">X</span></span>        |
  | <span data-ttu-id="ccf8a-140">Comentário</span><span class="sxs-lookup"><span data-stu-id="ccf8a-140">Comment</span></span>           | <span data-ttu-id="ccf8a-141">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="ccf8a-141">String</span></span>    |          |
  | <span data-ttu-id="ccf8a-142">Status</span><span class="sxs-lookup"><span data-stu-id="ccf8a-142">Status</span></span>            | <span data-ttu-id="ccf8a-143">Enumeração</span><span class="sxs-lookup"><span data-stu-id="ccf8a-143">Enum</span></span>      | <span data-ttu-id="ccf8a-144">X</span><span class="sxs-lookup"><span data-stu-id="ccf8a-144">X</span></span>        |
  | <span data-ttu-id="ccf8a-145">Valor</span><span class="sxs-lookup"><span data-stu-id="ccf8a-145">Amount</span></span>            | <span data-ttu-id="ccf8a-146">Real</span><span class="sxs-lookup"><span data-stu-id="ccf8a-146">Real</span></span>      |          |
  | <span data-ttu-id="ccf8a-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="ccf8a-147">HalfDayDefinition</span></span> | <span data-ttu-id="ccf8a-148">Enumeração</span><span class="sxs-lookup"><span data-stu-id="ccf8a-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="ccf8a-149">Ações</span><span class="sxs-lookup"><span data-stu-id="ccf8a-149">Actions</span></span>

 | <span data-ttu-id="ccf8a-150">Nome da Ação</span><span class="sxs-lookup"><span data-stu-id="ccf8a-150">Action Name</span></span>                               | <span data-ttu-id="ccf8a-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="ccf8a-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="ccf8a-152">enviar</span><span class="sxs-lookup"><span data-stu-id="ccf8a-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="ccf8a-153">Envie a solicitação para ser processada pelo fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ccf8a-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ccf8a-154">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ccf8a-154">See also</span></span>

- [<span data-ttu-id="ccf8a-155">Enviar uma solicitação de licença para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="ccf8a-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="ccf8a-156">Autenticação</span><span class="sxs-lookup"><span data-stu-id="ccf8a-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]