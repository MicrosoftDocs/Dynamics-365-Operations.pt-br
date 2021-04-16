---
title: Resultado da integração do candidato
description: Este tópico descreve o conjunto de opções de resultados de integração do candidato para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: e8e41fe485cc70a668d4610ce6eabba5cd16ac86
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795108"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="89f07-103">Resultado da integração do candidato</span><span class="sxs-lookup"><span data-stu-id="89f07-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="89f07-104">Este tópico descreve o conjunto de opções de resultados de integração do candidato para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="89f07-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="89f07-105">Nome físico: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="89f07-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="89f07-106">Essa enumeração fornece o status de um registro de candidato.</span><span class="sxs-lookup"><span data-stu-id="89f07-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="89f07-107">Alíquota</span><span class="sxs-lookup"><span data-stu-id="89f07-107">Value</span></span> | <span data-ttu-id="89f07-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="89f07-108">Label</span></span> | <span data-ttu-id="89f07-109">descrição</span><span class="sxs-lookup"><span data-stu-id="89f07-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="89f07-110">200000000</span><span class="sxs-lookup"><span data-stu-id="89f07-110">200000000</span></span> | <span data-ttu-id="89f07-111">Não processado</span><span class="sxs-lookup"><span data-stu-id="89f07-111">Not processed</span></span> | <span data-ttu-id="89f07-112">O candidato ainda está em análise.</span><span class="sxs-lookup"><span data-stu-id="89f07-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="89f07-113">200000001</span><span class="sxs-lookup"><span data-stu-id="89f07-113">200000001</span></span> | <span data-ttu-id="89f07-114">Contratado</span><span class="sxs-lookup"><span data-stu-id="89f07-114">Hired</span></span> | <span data-ttu-id="89f07-115">O candidato foi contratado.</span><span class="sxs-lookup"><span data-stu-id="89f07-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="89f07-116">200000002</span><span class="sxs-lookup"><span data-stu-id="89f07-116">200000002</span></span> | <span data-ttu-id="89f07-117">Não contratado</span><span class="sxs-lookup"><span data-stu-id="89f07-117">Not hired</span></span> | <span data-ttu-id="89f07-118">Foi decidido não contratar o candidato.</span><span class="sxs-lookup"><span data-stu-id="89f07-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="89f07-119">200000003</span><span class="sxs-lookup"><span data-stu-id="89f07-119">200000003</span></span> | <span data-ttu-id="89f07-120">Ignorado</span><span class="sxs-lookup"><span data-stu-id="89f07-120">Dismissed</span></span> | <span data-ttu-id="89f07-121">O candidato foi ignorado na análise.</span><span class="sxs-lookup"><span data-stu-id="89f07-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="89f07-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="89f07-122">See also</span></span>

[<span data-ttu-id="89f07-123">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="89f07-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="89f07-124">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="89f07-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]