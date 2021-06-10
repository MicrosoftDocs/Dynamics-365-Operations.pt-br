---
title: Status de isenção de trabalho
description: Este tópico descreve o conjunto de opções de estado de isenção de trabalho para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8e91fbb420009d5131e2faa7dbea8a302a027e0a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053842"
---
# <a name="job-exempt-status"></a><span data-ttu-id="eccff-103">Status de isenção de trabalho</span><span class="sxs-lookup"><span data-stu-id="eccff-103">Job exempt status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="eccff-104">Este tópico descreve o conjunto de opções de estado de isenção de trabalho para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="eccff-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="eccff-105">Nome físico: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="eccff-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="eccff-106">Esta enumeração especifica o conjunto de opções de valores de status de isenção de trabalho do FLSA.</span><span class="sxs-lookup"><span data-stu-id="eccff-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="eccff-107">Isso é fornecido no conjunto de opções de cdm_jobexemptstatus existentes.</span><span class="sxs-lookup"><span data-stu-id="eccff-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="eccff-108">Alíquota</span><span class="sxs-lookup"><span data-stu-id="eccff-108">Value</span></span> | <span data-ttu-id="eccff-109">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="eccff-109">Label</span></span> | <span data-ttu-id="eccff-110">descrição</span><span class="sxs-lookup"><span data-stu-id="eccff-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="eccff-111">200000000</span><span class="sxs-lookup"><span data-stu-id="eccff-111">200000000</span></span> | <span data-ttu-id="eccff-112">Isenção</span><span class="sxs-lookup"><span data-stu-id="eccff-112">Exempt</span></span> | <span data-ttu-id="eccff-113">O trabalho tem um status de isenção baseado em diretrizes de FLSA.</span><span class="sxs-lookup"><span data-stu-id="eccff-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="eccff-114">200000001</span><span class="sxs-lookup"><span data-stu-id="eccff-114">200000001</span></span> | <span data-ttu-id="eccff-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="eccff-115">NonExempt</span></span> | <span data-ttu-id="eccff-116">O trabalho tem um status de não isenção baseado em diretrizes de FLSA.</span><span class="sxs-lookup"><span data-stu-id="eccff-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="eccff-117">200000002</span><span class="sxs-lookup"><span data-stu-id="eccff-117">200000002</span></span> | <span data-ttu-id="eccff-118">Não se Aplica</span><span class="sxs-lookup"><span data-stu-id="eccff-118">Does Not Apply</span></span> | <span data-ttu-id="eccff-119">As diretrizes de status FLSA não se aplicam ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="eccff-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="eccff-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="eccff-120">See also</span></span>

[<span data-ttu-id="eccff-121">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="eccff-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="eccff-122">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="eccff-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]