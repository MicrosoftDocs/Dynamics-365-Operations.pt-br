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
ms.openlocfilehash: 01e8aa5157d0ad1c01f996886e7845e49ab97603
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464709"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="0aef7-103">Status da posição da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="0aef7-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0aef7-104">Este tópico descreve o conjunto de opções de status de posição da solicitação de recrutamento para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0aef7-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="0aef7-105">Nome físico: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="0aef7-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="0aef7-106">Essa enumeração fornece o conjunto de opções para os valores de status de cada posição em uma solicitação de recrutamento na entidade RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="0aef7-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="0aef7-107">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0aef7-107">Value</span></span> | <span data-ttu-id="0aef7-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="0aef7-108">Label</span></span> | <span data-ttu-id="0aef7-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="0aef7-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="0aef7-110">200000000</span><span class="sxs-lookup"><span data-stu-id="0aef7-110">200000000</span></span> | <span data-ttu-id="0aef7-111">Em Aberto</span><span class="sxs-lookup"><span data-stu-id="0aef7-111">Open</span></span> | <span data-ttu-id="0aef7-112">A posição na solicitação de recrutamento está aberta para recrutamento.</span><span class="sxs-lookup"><span data-stu-id="0aef7-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="0aef7-113">Isso não indica que não há atribuição de posição ativa no momento para a posição.</span><span class="sxs-lookup"><span data-stu-id="0aef7-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="0aef7-114">Pode haver um funcionário na posição no momento do recrutamento.</span><span class="sxs-lookup"><span data-stu-id="0aef7-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="0aef7-115">Isso indica apenas que a posição está disponível para recrutamento no contexto da solicitação de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="0aef7-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="0aef7-116">200000001</span><span class="sxs-lookup"><span data-stu-id="0aef7-116">200000001</span></span> | <span data-ttu-id="0aef7-117">Preenchida</span><span class="sxs-lookup"><span data-stu-id="0aef7-117">Filled</span></span> | <span data-ttu-id="0aef7-118">Um trabalhador foi selecionado para atribuição à posição.</span><span class="sxs-lookup"><span data-stu-id="0aef7-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="0aef7-119">200000002</span><span class="sxs-lookup"><span data-stu-id="0aef7-119">200000002</span></span> | <span data-ttu-id="0aef7-120">Cancelado</span><span class="sxs-lookup"><span data-stu-id="0aef7-120">Canceled</span></span> | <span data-ttu-id="0aef7-121">A solicitação de recrutamento para essa posição foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="0aef7-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0aef7-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0aef7-122">See also</span></span>

[<span data-ttu-id="0aef7-123">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="0aef7-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="0aef7-124">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="0aef7-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]