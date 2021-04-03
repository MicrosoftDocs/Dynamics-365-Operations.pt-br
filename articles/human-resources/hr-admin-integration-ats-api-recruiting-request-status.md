---
title: Status da solicitação de recrutamento
description: Este tópico descreve o conjunto de opções de Status da solicitação de recrutamento para o Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0032e6bfdbfd2792dafda8bf24a1b0cbc551740d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464637"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="a8a2e-103">Status da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="a8a2e-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a8a2e-104">Este tópico descreve o conjunto de opções de Status da solicitação de recrutamento para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="a8a2e-105">Nome físico: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="a8a2e-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="a8a2e-106">Essa enumeração fornece o conjunto de opções dos valores de status de um RecruitingRequest.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="a8a2e-107">Alíquota</span><span class="sxs-lookup"><span data-stu-id="a8a2e-107">Value</span></span> | <span data-ttu-id="a8a2e-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="a8a2e-108">Label</span></span> | <span data-ttu-id="a8a2e-109">descrição</span><span class="sxs-lookup"><span data-stu-id="a8a2e-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a8a2e-110">200000000</span><span class="sxs-lookup"><span data-stu-id="a8a2e-110">200000000</span></span> | <span data-ttu-id="a8a2e-111">Preliminar</span><span class="sxs-lookup"><span data-stu-id="a8a2e-111">Draft</span></span> | <span data-ttu-id="a8a2e-112">A solicitação está em rascunho e não está pronta para recrutamento ativo.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="a8a2e-113">200000001</span><span class="sxs-lookup"><span data-stu-id="a8a2e-113">200000001</span></span> | <span data-ttu-id="a8a2e-114">Em Revisão</span><span class="sxs-lookup"><span data-stu-id="a8a2e-114">In Review</span></span> | <span data-ttu-id="a8a2e-115">A solicitação foi enviada e está sendo roteada para aprovação por fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="a8a2e-116">Disponível apenas quando o fluxo de trabalho está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="a8a2e-117">200000002</span><span class="sxs-lookup"><span data-stu-id="a8a2e-117">200000002</span></span> | <span data-ttu-id="a8a2e-118">Pendente</span><span class="sxs-lookup"><span data-stu-id="a8a2e-118">Pending</span></span> | <span data-ttu-id="a8a2e-119">A solicitação é uma ação de fluxo de trabalho pendente.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-119">The request is pending workflow action.</span></span> <span data-ttu-id="a8a2e-120">Disponível apenas quando o fluxo de trabalho está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="a8a2e-121">200000003</span><span class="sxs-lookup"><span data-stu-id="a8a2e-121">200000003</span></span> | <span data-ttu-id="a8a2e-122">Cancelados(as)</span><span class="sxs-lookup"><span data-stu-id="a8a2e-122">Canceled</span></span> | <span data-ttu-id="a8a2e-123">A solicitação foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-123">The request has been canceled.</span></span> <span data-ttu-id="a8a2e-124">Disponível apenas quando o fluxo de trabalho está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="a8a2e-125">200000004</span><span class="sxs-lookup"><span data-stu-id="a8a2e-125">200000004</span></span> | <span data-ttu-id="a8a2e-126">Negada</span><span class="sxs-lookup"><span data-stu-id="a8a2e-126">Denied</span></span> | <span data-ttu-id="a8a2e-127">A solicitação foi negada.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-127">The request has been denied.</span></span> <span data-ttu-id="a8a2e-128">Disponível apenas quando o fluxo de trabalho está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="a8a2e-129">200000005</span><span class="sxs-lookup"><span data-stu-id="a8a2e-129">200000005</span></span> | <span data-ttu-id="a8a2e-130">Com atividade</span><span class="sxs-lookup"><span data-stu-id="a8a2e-130">Active</span></span> | <span data-ttu-id="a8a2e-131">Qualquer fluxo de trabalho é concluído e aprovado, e a solicitação está pronta para o recrutamento ativo.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="a8a2e-132">200000006</span><span class="sxs-lookup"><span data-stu-id="a8a2e-132">200000006</span></span> | <span data-ttu-id="a8a2e-133">Fechadas</span><span class="sxs-lookup"><span data-stu-id="a8a2e-133">Closed</span></span> | <span data-ttu-id="a8a2e-134">A solicitação de recrutamento está fechada.</span><span class="sxs-lookup"><span data-stu-id="a8a2e-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a8a2e-135">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a8a2e-135">See also</span></span>

[<span data-ttu-id="a8a2e-136">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="a8a2e-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="a8a2e-137">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="a8a2e-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]