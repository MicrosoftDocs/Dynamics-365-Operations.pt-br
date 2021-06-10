---
title: Status da posição da solicitação de recrutamento
description: Este tópico descreve o conjunto de opções de status de posição da solicitação de recrutamento para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: e287ec4b9b78194b76ef3c993c6ce32f808e26f9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051872"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="67f1d-103">Status da posição da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="67f1d-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="67f1d-104">Este tópico descreve o conjunto de opções de status de posição da solicitação de recrutamento para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="67f1d-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="67f1d-105">Nome físico: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="67f1d-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="67f1d-106">Essa enumeração fornece o conjunto de opções para os valores de status de cada posição em uma solicitação de recrutamento na entidade RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="67f1d-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="67f1d-107">Alíquota</span><span class="sxs-lookup"><span data-stu-id="67f1d-107">Value</span></span> | <span data-ttu-id="67f1d-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="67f1d-108">Label</span></span> | <span data-ttu-id="67f1d-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="67f1d-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="67f1d-110">200000000</span><span class="sxs-lookup"><span data-stu-id="67f1d-110">200000000</span></span> | <span data-ttu-id="67f1d-111">Em Aberto</span><span class="sxs-lookup"><span data-stu-id="67f1d-111">Open</span></span> | <span data-ttu-id="67f1d-112">A posição na solicitação de recrutamento está aberta para recrutamento.</span><span class="sxs-lookup"><span data-stu-id="67f1d-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="67f1d-113">Isso não indica que não há atribuição de posição ativa no momento para a posição.</span><span class="sxs-lookup"><span data-stu-id="67f1d-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="67f1d-114">Pode haver um funcionário na posição no momento do recrutamento.</span><span class="sxs-lookup"><span data-stu-id="67f1d-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="67f1d-115">Isso indica apenas que a posição está disponível para recrutamento no contexto da solicitação de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="67f1d-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="67f1d-116">200000001</span><span class="sxs-lookup"><span data-stu-id="67f1d-116">200000001</span></span> | <span data-ttu-id="67f1d-117">Preenchida</span><span class="sxs-lookup"><span data-stu-id="67f1d-117">Filled</span></span> | <span data-ttu-id="67f1d-118">Um trabalhador foi selecionado para atribuição à posição.</span><span class="sxs-lookup"><span data-stu-id="67f1d-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="67f1d-119">200000002</span><span class="sxs-lookup"><span data-stu-id="67f1d-119">200000002</span></span> | <span data-ttu-id="67f1d-120">Cancelado</span><span class="sxs-lookup"><span data-stu-id="67f1d-120">Canceled</span></span> | <span data-ttu-id="67f1d-121">A solicitação de recrutamento para essa posição foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="67f1d-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="67f1d-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="67f1d-122">See also</span></span>

[<span data-ttu-id="67f1d-123">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="67f1d-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="67f1d-124">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="67f1d-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]