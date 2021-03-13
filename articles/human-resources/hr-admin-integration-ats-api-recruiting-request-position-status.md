---
title: Status da posição da solicitação de recrutamento
description: Este tópico descreve o conjunto de opções de status de posição da solicitação de recrutamento para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126041"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="ebd24-103">Status da posição da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="ebd24-103">Recruiting request position status</span></span>

<span data-ttu-id="ebd24-104">Este tópico descreve o conjunto de opções de status de posição da solicitação de recrutamento para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ebd24-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="ebd24-105">Nome físico: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="ebd24-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="ebd24-106">Essa enumeração fornece o conjunto de opções para os valores de status de cada posição em uma solicitação de recrutamento na entidade RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="ebd24-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="ebd24-107">Alíquota</span><span class="sxs-lookup"><span data-stu-id="ebd24-107">Value</span></span> | <span data-ttu-id="ebd24-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="ebd24-108">Label</span></span> | <span data-ttu-id="ebd24-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="ebd24-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="ebd24-110">200000000</span><span class="sxs-lookup"><span data-stu-id="ebd24-110">200000000</span></span> | <span data-ttu-id="ebd24-111">Em Aberto</span><span class="sxs-lookup"><span data-stu-id="ebd24-111">Open</span></span> | <span data-ttu-id="ebd24-112">A posição na solicitação de recrutamento está aberta para recrutamento.</span><span class="sxs-lookup"><span data-stu-id="ebd24-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="ebd24-113">Isso não indica que não há atribuição de posição ativa no momento para a posição.</span><span class="sxs-lookup"><span data-stu-id="ebd24-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="ebd24-114">Pode haver um funcionário na posição no momento do recrutamento.</span><span class="sxs-lookup"><span data-stu-id="ebd24-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="ebd24-115">Isso indica apenas que a posição está disponível para recrutamento no contexto da solicitação de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="ebd24-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="ebd24-116">200000001</span><span class="sxs-lookup"><span data-stu-id="ebd24-116">200000001</span></span> | <span data-ttu-id="ebd24-117">Preenchida</span><span class="sxs-lookup"><span data-stu-id="ebd24-117">Filled</span></span> | <span data-ttu-id="ebd24-118">Um trabalhador foi selecionado para atribuição à posição.</span><span class="sxs-lookup"><span data-stu-id="ebd24-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="ebd24-119">200000002</span><span class="sxs-lookup"><span data-stu-id="ebd24-119">200000002</span></span> | <span data-ttu-id="ebd24-120">Cancelado</span><span class="sxs-lookup"><span data-stu-id="ebd24-120">Canceled</span></span> | <span data-ttu-id="ebd24-121">A solicitação de recrutamento para essa posição foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="ebd24-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ebd24-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ebd24-122">See also</span></span>

[<span data-ttu-id="ebd24-123">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="ebd24-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="ebd24-124">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="ebd24-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
