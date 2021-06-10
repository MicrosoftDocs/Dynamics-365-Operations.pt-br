---
title: Status da solicitação de recrutamento
description: Este tópico descreve o conjunto de opções de Status da solicitação de recrutamento para o Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3b05cc531a84144708ff52913927bbd04574a3b2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059175"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="b0ecf-103">Status da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="b0ecf-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b0ecf-104">Este tópico descreve o conjunto de opções de Status da solicitação de recrutamento para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="b0ecf-105">Nome físico: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="b0ecf-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="b0ecf-106">Essa enumeração fornece o conjunto de opções dos valores de status de um RecruitingRequest.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="b0ecf-107">Alíquota</span><span class="sxs-lookup"><span data-stu-id="b0ecf-107">Value</span></span> | <span data-ttu-id="b0ecf-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="b0ecf-108">Label</span></span> | <span data-ttu-id="b0ecf-109">descrição</span><span class="sxs-lookup"><span data-stu-id="b0ecf-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b0ecf-110">200000000</span><span class="sxs-lookup"><span data-stu-id="b0ecf-110">200000000</span></span> | <span data-ttu-id="b0ecf-111">Preliminar</span><span class="sxs-lookup"><span data-stu-id="b0ecf-111">Draft</span></span> | <span data-ttu-id="b0ecf-112">A solicitação está em rascunho e não está pronta para recrutamento ativo.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="b0ecf-113">200000001</span><span class="sxs-lookup"><span data-stu-id="b0ecf-113">200000001</span></span> | <span data-ttu-id="b0ecf-114">Em Revisão</span><span class="sxs-lookup"><span data-stu-id="b0ecf-114">In Review</span></span> | <span data-ttu-id="b0ecf-115">A solicitação foi enviada e está sendo roteada para aprovação por fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="b0ecf-116">Disponível apenas quando o fluxo de trabalho está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="b0ecf-117">200000002</span><span class="sxs-lookup"><span data-stu-id="b0ecf-117">200000002</span></span> | <span data-ttu-id="b0ecf-118">Pendente</span><span class="sxs-lookup"><span data-stu-id="b0ecf-118">Pending</span></span> | <span data-ttu-id="b0ecf-119">A solicitação é uma ação de fluxo de trabalho pendente.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-119">The request is pending workflow action.</span></span> <span data-ttu-id="b0ecf-120">Disponível apenas quando o fluxo de trabalho está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="b0ecf-121">200000003</span><span class="sxs-lookup"><span data-stu-id="b0ecf-121">200000003</span></span> | <span data-ttu-id="b0ecf-122">Cancelados(as)</span><span class="sxs-lookup"><span data-stu-id="b0ecf-122">Canceled</span></span> | <span data-ttu-id="b0ecf-123">A solicitação foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-123">The request has been canceled.</span></span> <span data-ttu-id="b0ecf-124">Disponível apenas quando o fluxo de trabalho está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="b0ecf-125">200000004</span><span class="sxs-lookup"><span data-stu-id="b0ecf-125">200000004</span></span> | <span data-ttu-id="b0ecf-126">Negada</span><span class="sxs-lookup"><span data-stu-id="b0ecf-126">Denied</span></span> | <span data-ttu-id="b0ecf-127">A solicitação foi negada.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-127">The request has been denied.</span></span> <span data-ttu-id="b0ecf-128">Disponível apenas quando o fluxo de trabalho está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="b0ecf-129">200000005</span><span class="sxs-lookup"><span data-stu-id="b0ecf-129">200000005</span></span> | <span data-ttu-id="b0ecf-130">Com atividade</span><span class="sxs-lookup"><span data-stu-id="b0ecf-130">Active</span></span> | <span data-ttu-id="b0ecf-131">Qualquer fluxo de trabalho é concluído e aprovado, e a solicitação está pronta para o recrutamento ativo.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="b0ecf-132">200000006</span><span class="sxs-lookup"><span data-stu-id="b0ecf-132">200000006</span></span> | <span data-ttu-id="b0ecf-133">Fechadas</span><span class="sxs-lookup"><span data-stu-id="b0ecf-133">Closed</span></span> | <span data-ttu-id="b0ecf-134">A solicitação de recrutamento está fechada.</span><span class="sxs-lookup"><span data-stu-id="b0ecf-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b0ecf-135">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b0ecf-135">See also</span></span>

[<span data-ttu-id="b0ecf-136">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="b0ecf-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="b0ecf-137">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="b0ecf-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]