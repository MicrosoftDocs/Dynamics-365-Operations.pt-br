---
title: Status de isenção de trabalho
description: Este tópico descreve o conjunto de opções de estado de isenção de trabalho para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1f211002468384227acb2343ed6cbc6ae2a215d1
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464443"
---
# <a name="job-exempt-status"></a><span data-ttu-id="d3adb-103">Status de isenção de trabalho</span><span class="sxs-lookup"><span data-stu-id="d3adb-103">Job exempt status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d3adb-104">Este tópico descreve o conjunto de opções de estado de isenção de trabalho para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d3adb-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="d3adb-105">Nome físico: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="d3adb-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="d3adb-106">Esta enumeração especifica o conjunto de opções de valores de status de isenção de trabalho do FLSA.</span><span class="sxs-lookup"><span data-stu-id="d3adb-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="d3adb-107">Isso é fornecido no conjunto de opções de cdm_jobexemptstatus existentes.</span><span class="sxs-lookup"><span data-stu-id="d3adb-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="d3adb-108">Alíquota</span><span class="sxs-lookup"><span data-stu-id="d3adb-108">Value</span></span> | <span data-ttu-id="d3adb-109">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="d3adb-109">Label</span></span> | <span data-ttu-id="d3adb-110">descrição</span><span class="sxs-lookup"><span data-stu-id="d3adb-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="d3adb-111">200000000</span><span class="sxs-lookup"><span data-stu-id="d3adb-111">200000000</span></span> | <span data-ttu-id="d3adb-112">Isenção</span><span class="sxs-lookup"><span data-stu-id="d3adb-112">Exempt</span></span> | <span data-ttu-id="d3adb-113">O trabalho tem um status de isenção baseado em diretrizes de FLSA.</span><span class="sxs-lookup"><span data-stu-id="d3adb-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="d3adb-114">200000001</span><span class="sxs-lookup"><span data-stu-id="d3adb-114">200000001</span></span> | <span data-ttu-id="d3adb-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="d3adb-115">NonExempt</span></span> | <span data-ttu-id="d3adb-116">O trabalho tem um status de não isenção baseado em diretrizes de FLSA.</span><span class="sxs-lookup"><span data-stu-id="d3adb-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="d3adb-117">200000002</span><span class="sxs-lookup"><span data-stu-id="d3adb-117">200000002</span></span> | <span data-ttu-id="d3adb-118">Não se Aplica</span><span class="sxs-lookup"><span data-stu-id="d3adb-118">Does Not Apply</span></span> | <span data-ttu-id="d3adb-119">As diretrizes de status FLSA não se aplicam ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="d3adb-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d3adb-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d3adb-120">See also</span></span>

[<span data-ttu-id="d3adb-121">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="d3adb-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="d3adb-122">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="d3adb-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]