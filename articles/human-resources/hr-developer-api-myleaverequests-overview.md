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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803624"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="6aeb5-103">Visão geral de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="6aeb5-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6aeb5-104">A entidade MyLeaveRequests no Microsoft Dynamics 365 Human Resources fornece a lista de solicitações de licença no sistema, com escopo (limitado) para as solicitações acessíveis ao usuário atual que consulta a entidade.</span><span class="sxs-lookup"><span data-stu-id="6aeb5-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="6aeb5-105">Chave</span><span class="sxs-lookup"><span data-stu-id="6aeb5-105">Key</span></span>

  | <span data-ttu-id="6aeb5-106">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="6aeb5-106">Property Name</span></span> | <span data-ttu-id="6aeb5-107">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="6aeb5-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="6aeb5-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="6aeb5-108">dataAreaId</span></span>    | <span data-ttu-id="6aeb5-109">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6aeb5-109">String</span></span>    |
  | <span data-ttu-id="6aeb5-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="6aeb5-110">RequestId</span></span>     | <span data-ttu-id="6aeb5-111">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6aeb5-111">String</span></span>    |
  | <span data-ttu-id="6aeb5-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="6aeb5-112">LeaveType</span></span>     | <span data-ttu-id="6aeb5-113">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6aeb5-113">String</span></span>    |
  | <span data-ttu-id="6aeb5-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="6aeb5-114">LeaveDate</span></span>     | <span data-ttu-id="6aeb5-115">Data </span><span class="sxs-lookup"><span data-stu-id="6aeb5-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="6aeb5-116">Propriedades</span><span class="sxs-lookup"><span data-stu-id="6aeb5-116">Properties</span></span>

  | <span data-ttu-id="6aeb5-117">Nome da Propriedade</span><span class="sxs-lookup"><span data-stu-id="6aeb5-117">Property Name</span></span>     | <span data-ttu-id="6aeb5-118">Tipo de Dados</span><span class="sxs-lookup"><span data-stu-id="6aeb5-118">Data Type</span></span> | <span data-ttu-id="6aeb5-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="6aeb5-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="6aeb5-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="6aeb5-120">dataAreaId</span></span>        | <span data-ttu-id="6aeb5-121">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6aeb5-121">String</span></span>    | <span data-ttu-id="6aeb5-122">X</span><span class="sxs-lookup"><span data-stu-id="6aeb5-122">X</span></span>        |
  | <span data-ttu-id="6aeb5-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="6aeb5-123">RequestId</span></span>         | <span data-ttu-id="6aeb5-124">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6aeb5-124">String</span></span>    | <span data-ttu-id="6aeb5-125">X</span><span class="sxs-lookup"><span data-stu-id="6aeb5-125">X</span></span>        |
  | <span data-ttu-id="6aeb5-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="6aeb5-126">LeaveType</span></span>         | <span data-ttu-id="6aeb5-127">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6aeb5-127">String</span></span>    | <span data-ttu-id="6aeb5-128">X</span><span class="sxs-lookup"><span data-stu-id="6aeb5-128">X</span></span>        |
  | <span data-ttu-id="6aeb5-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="6aeb5-129">LeaveDate</span></span>         | <span data-ttu-id="6aeb5-130">Data </span><span class="sxs-lookup"><span data-stu-id="6aeb5-130">Date</span></span>      | <span data-ttu-id="6aeb5-131">X</span><span class="sxs-lookup"><span data-stu-id="6aeb5-131">X</span></span>        |
  | <span data-ttu-id="6aeb5-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="6aeb5-132">ReasonCodeId</span></span>      | <span data-ttu-id="6aeb5-133">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6aeb5-133">String</span></span>    |          |
  | <span data-ttu-id="6aeb5-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="6aeb5-134">PersonnelNumber</span></span>   | <span data-ttu-id="6aeb5-135">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6aeb5-135">String</span></span>    | <span data-ttu-id="6aeb5-136">X</span><span class="sxs-lookup"><span data-stu-id="6aeb5-136">X</span></span>        |
  | <span data-ttu-id="6aeb5-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="6aeb5-137">RequestDate</span></span>       | <span data-ttu-id="6aeb5-138">Data </span><span class="sxs-lookup"><span data-stu-id="6aeb5-138">Date</span></span>      | <span data-ttu-id="6aeb5-139">X</span><span class="sxs-lookup"><span data-stu-id="6aeb5-139">X</span></span>        |
  | <span data-ttu-id="6aeb5-140">Comentário</span><span class="sxs-lookup"><span data-stu-id="6aeb5-140">Comment</span></span>           | <span data-ttu-id="6aeb5-141">Sequência de caracteres</span><span class="sxs-lookup"><span data-stu-id="6aeb5-141">String</span></span>    |          |
  | <span data-ttu-id="6aeb5-142">Status</span><span class="sxs-lookup"><span data-stu-id="6aeb5-142">Status</span></span>            | <span data-ttu-id="6aeb5-143">Enumeração</span><span class="sxs-lookup"><span data-stu-id="6aeb5-143">Enum</span></span>      | <span data-ttu-id="6aeb5-144">X</span><span class="sxs-lookup"><span data-stu-id="6aeb5-144">X</span></span>        |
  | <span data-ttu-id="6aeb5-145">Valor</span><span class="sxs-lookup"><span data-stu-id="6aeb5-145">Amount</span></span>            | <span data-ttu-id="6aeb5-146">Real</span><span class="sxs-lookup"><span data-stu-id="6aeb5-146">Real</span></span>      |          |
  | <span data-ttu-id="6aeb5-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="6aeb5-147">HalfDayDefinition</span></span> | <span data-ttu-id="6aeb5-148">Enumeração</span><span class="sxs-lookup"><span data-stu-id="6aeb5-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="6aeb5-149">Ações</span><span class="sxs-lookup"><span data-stu-id="6aeb5-149">Actions</span></span>

 | <span data-ttu-id="6aeb5-150">Nome da Ação</span><span class="sxs-lookup"><span data-stu-id="6aeb5-150">Action Name</span></span>                               | <span data-ttu-id="6aeb5-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="6aeb5-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="6aeb5-152">enviar</span><span class="sxs-lookup"><span data-stu-id="6aeb5-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="6aeb5-153">Envie a solicitação para ser processada pelo fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6aeb5-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="6aeb5-154">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6aeb5-154">See also</span></span>

- [<span data-ttu-id="6aeb5-155">Enviar uma solicitação de licença para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="6aeb5-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="6aeb5-156">Autenticação</span><span class="sxs-lookup"><span data-stu-id="6aeb5-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]