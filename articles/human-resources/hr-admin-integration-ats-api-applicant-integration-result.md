---
title: Resultado da integração do candidato
description: Este tópico descreve o conjunto de opções de resultados de integração do candidato para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8bef974abff18d7c07ecd679b7e01b31ea1459c4
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053890"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="e1cf2-103">Resultado da integração do candidato</span><span class="sxs-lookup"><span data-stu-id="e1cf2-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e1cf2-104">Este tópico descreve o conjunto de opções de resultados de integração do candidato para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e1cf2-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="e1cf2-105">Nome físico: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="e1cf2-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="e1cf2-106">Essa enumeração fornece o status de um registro de candidato.</span><span class="sxs-lookup"><span data-stu-id="e1cf2-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="e1cf2-107">Alíquota</span><span class="sxs-lookup"><span data-stu-id="e1cf2-107">Value</span></span> | <span data-ttu-id="e1cf2-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="e1cf2-108">Label</span></span> | <span data-ttu-id="e1cf2-109">descrição</span><span class="sxs-lookup"><span data-stu-id="e1cf2-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e1cf2-110">200000000</span><span class="sxs-lookup"><span data-stu-id="e1cf2-110">200000000</span></span> | <span data-ttu-id="e1cf2-111">Não processado</span><span class="sxs-lookup"><span data-stu-id="e1cf2-111">Not processed</span></span> | <span data-ttu-id="e1cf2-112">O candidato ainda está em análise.</span><span class="sxs-lookup"><span data-stu-id="e1cf2-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="e1cf2-113">200000001</span><span class="sxs-lookup"><span data-stu-id="e1cf2-113">200000001</span></span> | <span data-ttu-id="e1cf2-114">Contratado</span><span class="sxs-lookup"><span data-stu-id="e1cf2-114">Hired</span></span> | <span data-ttu-id="e1cf2-115">O candidato foi contratado.</span><span class="sxs-lookup"><span data-stu-id="e1cf2-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="e1cf2-116">200000002</span><span class="sxs-lookup"><span data-stu-id="e1cf2-116">200000002</span></span> | <span data-ttu-id="e1cf2-117">Não contratado</span><span class="sxs-lookup"><span data-stu-id="e1cf2-117">Not hired</span></span> | <span data-ttu-id="e1cf2-118">Foi decidido não contratar o candidato.</span><span class="sxs-lookup"><span data-stu-id="e1cf2-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="e1cf2-119">200000003</span><span class="sxs-lookup"><span data-stu-id="e1cf2-119">200000003</span></span> | <span data-ttu-id="e1cf2-120">Ignorado</span><span class="sxs-lookup"><span data-stu-id="e1cf2-120">Dismissed</span></span> | <span data-ttu-id="e1cf2-121">O candidato foi ignorado na análise.</span><span class="sxs-lookup"><span data-stu-id="e1cf2-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e1cf2-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e1cf2-122">See also</span></span>

[<span data-ttu-id="e1cf2-123">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="e1cf2-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="e1cf2-124">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="e1cf2-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]