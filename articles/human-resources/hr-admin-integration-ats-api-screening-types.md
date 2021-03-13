---
title: Tipos de triagem
description: Este tópico descreve a entidade Tipos de triagem para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 227c15acb44e020ea9858961e45c11ad07e18a74
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126161"
---
# <a name="screening-types"></a><span data-ttu-id="96c85-103">Tipos de triagem</span><span class="sxs-lookup"><span data-stu-id="96c85-103">Screening types</span></span>

<span data-ttu-id="96c85-104">Este tópico descreve a entidade Tipos de triagem para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96c85-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="96c85-105">Nome físico: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="96c85-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="96c85-106">descrição</span><span class="sxs-lookup"><span data-stu-id="96c85-106">Description</span></span>

<span data-ttu-id="96c85-107">Esta entidade descreve os tipos de triagem configurados pela empresa para processos de pré-contratação e triagem de funcionário em andamento.</span><span class="sxs-lookup"><span data-stu-id="96c85-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="96c85-108">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="96c85-108">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="96c85-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="96c85-109">Properties</span></span>

| <span data-ttu-id="96c85-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="96c85-110">Property</span></span><br><span data-ttu-id="96c85-111">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="96c85-111">**Physical name**</span></span><br><span data-ttu-id="96c85-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="96c85-112">**_Type_**</span></span> | <span data-ttu-id="96c85-113">Uso</span><span class="sxs-lookup"><span data-stu-id="96c85-113">Use</span></span> | <span data-ttu-id="96c85-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="96c85-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96c85-115">**ID da entidade do tipo de triagem**</span><span class="sxs-lookup"><span data-stu-id="96c85-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="96c85-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="96c85-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="96c85-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="96c85-117">*GUID*</span></span> | <span data-ttu-id="96c85-118">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="96c85-118">Read-only</span></span><br><span data-ttu-id="96c85-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="96c85-119">Required</span></span><br><span data-ttu-id="96c85-120">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="96c85-120">System-generated</span></span> | <span data-ttu-id="96c85-121">Identificador principal exclusivo do registro de tipo de triagem.</span><span class="sxs-lookup"><span data-stu-id="96c85-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="96c85-122">**ID de tipo de triagem**</span><span class="sxs-lookup"><span data-stu-id="96c85-122">**Screening Type ID**</span></span><br><span data-ttu-id="96c85-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="96c85-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="96c85-124">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="96c85-124">*String*</span></span> | <span data-ttu-id="96c85-125">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="96c85-125">Read/write</span></span><br><span data-ttu-id="96c85-126">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="96c85-126">Required</span></span> | <span data-ttu-id="96c85-127">Identificador exclusivo definido pelo usuário de tipo de triagem.</span><span class="sxs-lookup"><span data-stu-id="96c85-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="96c85-128">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="96c85-128">**Description**</span></span><br><span data-ttu-id="96c85-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="96c85-129">mshr_description</span></span><br><span data-ttu-id="96c85-130">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="96c85-130">*String*</span></span> | <span data-ttu-id="96c85-131">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="96c85-131">Read/write</span></span><br><span data-ttu-id="96c85-132">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="96c85-132">Required</span></span> | <span data-ttu-id="96c85-133">A descrição do tipo de triagem.</span><span class="sxs-lookup"><span data-stu-id="96c85-133">The description of the screening type.</span></span> |
| <span data-ttu-id="96c85-134">**Unidade de frequência**</span><span class="sxs-lookup"><span data-stu-id="96c85-134">**Frequency Unit**</span></span><br><span data-ttu-id="96c85-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="96c85-135">mshr_frequencyunit</span></span><br><span data-ttu-id="96c85-136">*conjunto de opções mshr_hcmfrequencyunit*</span><span class="sxs-lookup"><span data-stu-id="96c85-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="96c85-137">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="96c85-137">Read/write</span></span><br><span data-ttu-id="96c85-138">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="96c85-138">Required</span></span> | <span data-ttu-id="96c85-139">Descreve a frequência com que a triagem deve ser concluída para a pessoa atribuída.</span><span class="sxs-lookup"><span data-stu-id="96c85-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="96c85-140">**Gerar de**</span><span class="sxs-lookup"><span data-stu-id="96c85-140">**Generate From**</span></span><br><span data-ttu-id="96c85-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="96c85-141">mshr_generatefrom</span></span><br><span data-ttu-id="96c85-142">*conjunto de opções mshr_hcmfrequencygeneratefrom*</span><span class="sxs-lookup"><span data-stu-id="96c85-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="96c85-143">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="96c85-143">Read-write</span></span><br><span data-ttu-id="96c85-144">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="96c85-144">Required</span></span> | <span data-ttu-id="96c85-145">Se o valor de frequência for qualquer valor diferente de "Apenas ocasional", o valor GenerateFrom determinará a data a partir da qual o próximo evento de triagem será calculado.</span><span class="sxs-lookup"><span data-stu-id="96c85-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="96c85-146">**Intervalo de frequência**</span><span class="sxs-lookup"><span data-stu-id="96c85-146">**Frequency Interval**</span></span><br><span data-ttu-id="96c85-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="96c85-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="96c85-148">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="96c85-148">*Integer*</span></span> | <span data-ttu-id="96c85-149">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="96c85-149">Read-write</span></span><br><span data-ttu-id="96c85-150">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="96c85-150">Required</span></span> | <span data-ttu-id="96c85-151">Se o valor de frequência for qualquer valor diferente de "Apenas ocasional", você deverá definir um intervalo para as unidades de tempo entre cada evento de triagem.</span><span class="sxs-lookup"><span data-stu-id="96c85-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="96c85-152">Consulte também</span><span class="sxs-lookup"><span data-stu-id="96c85-152">See also</span></span>

[<span data-ttu-id="96c85-153">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="96c85-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="96c85-154">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="96c85-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
