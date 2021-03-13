---
title: Geração de frequência de triagem de
description: Este tópico descreve o conjunto de opções de Geração de frequência de triagem de para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: f291e28584dadc465092d99a1354fda793ff7560
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126137"
---
# <a name="screening-frequency-generate-from"></a><span data-ttu-id="e41ea-103">Geração de frequência de triagem de</span><span class="sxs-lookup"><span data-stu-id="e41ea-103">Screening frequency generate from</span></span>

<span data-ttu-id="e41ea-104">Este tópico descreve o conjunto de opções de Geração de frequência de triagem de para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e41ea-104">This topic describes the Screening frequency generate from option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="e41ea-105">Nome físico: mshr_hcmfrequencygeneratefrom</span><span class="sxs-lookup"><span data-stu-id="e41ea-105">Physical name: mshr_hcmfrequencygeneratefrom</span></span>

<span data-ttu-id="e41ea-106">Essa enumeração fornece o conjunto de opções de valores para determinar a data de início do cálculo para a próxima triagem necessária.</span><span class="sxs-lookup"><span data-stu-id="e41ea-106">This enumeration provides the option set of values for determining the start date of the calculation for the next required screening.</span></span>

| <span data-ttu-id="e41ea-107">Valor</span><span class="sxs-lookup"><span data-stu-id="e41ea-107">Value</span></span> | <span data-ttu-id="e41ea-108">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="e41ea-108">Label</span></span> | <span data-ttu-id="e41ea-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e41ea-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e41ea-110">200000000 Não selecionado</span><span class="sxs-lookup"><span data-stu-id="e41ea-110">200000000 Not selected</span></span> | <span data-ttu-id="e41ea-111">Nenhum valor foi selecionado.</span><span class="sxs-lookup"><span data-stu-id="e41ea-111">No value has been selected.</span></span> |
| <span data-ttu-id="e41ea-112">200000001 Data de conclusão</span><span class="sxs-lookup"><span data-stu-id="e41ea-112">200000001 Date completed</span></span> | <span data-ttu-id="e41ea-113">O cálculo é feito a partir da última data de triagem concluída.</span><span class="sxs-lookup"><span data-stu-id="e41ea-113">Calculation is done from the last screening date completed.</span></span> |
| <span data-ttu-id="e41ea-114">200000002 A data é obrigatória</span><span class="sxs-lookup"><span data-stu-id="e41ea-114">200000002 Date required</span></span> | <span data-ttu-id="e41ea-115">O cálculo é feito a partir da última data de triagem necessária.</span><span class="sxs-lookup"><span data-stu-id="e41ea-115">Calculation is done from the last screening date required.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e41ea-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e41ea-116">See also</span></span>

[<span data-ttu-id="e41ea-117">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="e41ea-117">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="e41ea-118">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="e41ea-118">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)