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
ms.openlocfilehash: d3a45d802ab6b574338a09e77d432357cb9df507
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465909"
---
# <a name="screening-types"></a><span data-ttu-id="5c2b3-103">Tipos de triagem</span><span class="sxs-lookup"><span data-stu-id="5c2b3-103">Screening types</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="5c2b3-104">Este tópico descreve a entidade Tipos de triagem para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5c2b3-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="5c2b3-105">Nome físico: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="5c2b3-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="5c2b3-106">descrição</span><span class="sxs-lookup"><span data-stu-id="5c2b3-106">Description</span></span>

<span data-ttu-id="5c2b3-107">Esta entidade descreve os tipos de triagem configurados pela empresa para processos de pré-contratação e triagem de funcionário em andamento.</span><span class="sxs-lookup"><span data-stu-id="5c2b3-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="5c2b3-108">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="5c2b3-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="5c2b3-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="5c2b3-109">Properties</span></span>

| <span data-ttu-id="5c2b3-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="5c2b3-110">Property</span></span><br><span data-ttu-id="5c2b3-111">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="5c2b3-111">**Physical name**</span></span><br><span data-ttu-id="5c2b3-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="5c2b3-112">**_Type_**</span></span> | <span data-ttu-id="5c2b3-113">Uso</span><span class="sxs-lookup"><span data-stu-id="5c2b3-113">Use</span></span> | <span data-ttu-id="5c2b3-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c2b3-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="5c2b3-115">**ID da entidade do tipo de triagem**</span><span class="sxs-lookup"><span data-stu-id="5c2b3-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="5c2b3-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="5c2b3-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="5c2b3-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="5c2b3-117">*GUID*</span></span> | <span data-ttu-id="5c2b3-118">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="5c2b3-118">Read-only</span></span><br><span data-ttu-id="5c2b3-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5c2b3-119">Required</span></span><br><span data-ttu-id="5c2b3-120">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="5c2b3-120">System-generated</span></span> | <span data-ttu-id="5c2b3-121">Identificador principal exclusivo do registro de tipo de triagem.</span><span class="sxs-lookup"><span data-stu-id="5c2b3-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="5c2b3-122">**ID de tipo de triagem**</span><span class="sxs-lookup"><span data-stu-id="5c2b3-122">**Screening Type ID**</span></span><br><span data-ttu-id="5c2b3-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="5c2b3-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="5c2b3-124">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="5c2b3-124">*String*</span></span> | <span data-ttu-id="5c2b3-125">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="5c2b3-125">Read/write</span></span><br><span data-ttu-id="5c2b3-126">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5c2b3-126">Required</span></span> | <span data-ttu-id="5c2b3-127">Identificador exclusivo definido pelo usuário de tipo de triagem.</span><span class="sxs-lookup"><span data-stu-id="5c2b3-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="5c2b3-128">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5c2b3-128">**Description**</span></span><br><span data-ttu-id="5c2b3-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="5c2b3-129">mshr_description</span></span><br><span data-ttu-id="5c2b3-130">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="5c2b3-130">*String*</span></span> | <span data-ttu-id="5c2b3-131">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="5c2b3-131">Read/write</span></span><br><span data-ttu-id="5c2b3-132">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5c2b3-132">Required</span></span> | <span data-ttu-id="5c2b3-133">A descrição do tipo de triagem.</span><span class="sxs-lookup"><span data-stu-id="5c2b3-133">The description of the screening type.</span></span> |
| <span data-ttu-id="5c2b3-134">**Unidade de frequência**</span><span class="sxs-lookup"><span data-stu-id="5c2b3-134">**Frequency Unit**</span></span><br><span data-ttu-id="5c2b3-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="5c2b3-135">mshr_frequencyunit</span></span><br><span data-ttu-id="5c2b3-136">*conjunto de opções mshr_hcmfrequencyunit*</span><span class="sxs-lookup"><span data-stu-id="5c2b3-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="5c2b3-137">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="5c2b3-137">Read/write</span></span><br><span data-ttu-id="5c2b3-138">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5c2b3-138">Required</span></span> | <span data-ttu-id="5c2b3-139">Descreve a frequência com que a triagem deve ser concluída para a pessoa atribuída.</span><span class="sxs-lookup"><span data-stu-id="5c2b3-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="5c2b3-140">**Gerar de**</span><span class="sxs-lookup"><span data-stu-id="5c2b3-140">**Generate From**</span></span><br><span data-ttu-id="5c2b3-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="5c2b3-141">mshr_generatefrom</span></span><br><span data-ttu-id="5c2b3-142">*conjunto de opções mshr_hcmfrequencygeneratefrom*</span><span class="sxs-lookup"><span data-stu-id="5c2b3-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="5c2b3-143">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="5c2b3-143">Read-write</span></span><br><span data-ttu-id="5c2b3-144">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5c2b3-144">Required</span></span> | <span data-ttu-id="5c2b3-145">Se o valor de frequência for qualquer valor diferente de "Apenas ocasional", o valor GenerateFrom determinará a data a partir da qual o próximo evento de triagem será calculado.</span><span class="sxs-lookup"><span data-stu-id="5c2b3-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="5c2b3-146">**Intervalo de frequência**</span><span class="sxs-lookup"><span data-stu-id="5c2b3-146">**Frequency Interval**</span></span><br><span data-ttu-id="5c2b3-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="5c2b3-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="5c2b3-148">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="5c2b3-148">*Integer*</span></span> | <span data-ttu-id="5c2b3-149">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="5c2b3-149">Read-write</span></span><br><span data-ttu-id="5c2b3-150">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="5c2b3-150">Required</span></span> | <span data-ttu-id="5c2b3-151">Se o valor de frequência for qualquer valor diferente de "Apenas ocasional", você deverá definir um intervalo para as unidades de tempo entre cada evento de triagem.</span><span class="sxs-lookup"><span data-stu-id="5c2b3-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="5c2b3-152">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5c2b3-152">See also</span></span>

[<span data-ttu-id="5c2b3-153">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="5c2b3-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="5c2b3-154">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="5c2b3-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]