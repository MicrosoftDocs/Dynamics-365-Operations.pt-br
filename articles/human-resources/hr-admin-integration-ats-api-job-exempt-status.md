---
title: Status de isenção de trabalho
description: Este tópico descreve o conjunto de opções de estado de isenção de trabalho para o Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4765858f389f28467ae2ac71084c15d2ba0cbe8b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798288"
---
# <a name="job-exempt-status"></a><span data-ttu-id="364f9-103">Status de isenção de trabalho</span><span class="sxs-lookup"><span data-stu-id="364f9-103">Job exempt status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="364f9-104">Este tópico descreve o conjunto de opções de estado de isenção de trabalho para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="364f9-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="364f9-105">Nome físico: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="364f9-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="364f9-106">Esta enumeração especifica o conjunto de opções de valores de status de isenção de trabalho do FLSA.</span><span class="sxs-lookup"><span data-stu-id="364f9-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="364f9-107">Isso é fornecido no conjunto de opções de cdm_jobexemptstatus existentes.</span><span class="sxs-lookup"><span data-stu-id="364f9-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="364f9-108">Alíquota</span><span class="sxs-lookup"><span data-stu-id="364f9-108">Value</span></span> | <span data-ttu-id="364f9-109">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="364f9-109">Label</span></span> | <span data-ttu-id="364f9-110">descrição</span><span class="sxs-lookup"><span data-stu-id="364f9-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="364f9-111">200000000</span><span class="sxs-lookup"><span data-stu-id="364f9-111">200000000</span></span> | <span data-ttu-id="364f9-112">Isenção</span><span class="sxs-lookup"><span data-stu-id="364f9-112">Exempt</span></span> | <span data-ttu-id="364f9-113">O trabalho tem um status de isenção baseado em diretrizes de FLSA.</span><span class="sxs-lookup"><span data-stu-id="364f9-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="364f9-114">200000001</span><span class="sxs-lookup"><span data-stu-id="364f9-114">200000001</span></span> | <span data-ttu-id="364f9-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="364f9-115">NonExempt</span></span> | <span data-ttu-id="364f9-116">O trabalho tem um status de não isenção baseado em diretrizes de FLSA.</span><span class="sxs-lookup"><span data-stu-id="364f9-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="364f9-117">200000002</span><span class="sxs-lookup"><span data-stu-id="364f9-117">200000002</span></span> | <span data-ttu-id="364f9-118">Não se Aplica</span><span class="sxs-lookup"><span data-stu-id="364f9-118">Does Not Apply</span></span> | <span data-ttu-id="364f9-119">As diretrizes de status FLSA não se aplicam ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="364f9-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="364f9-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="364f9-120">See also</span></span>

[<span data-ttu-id="364f9-121">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="364f9-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="364f9-122">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="364f9-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]