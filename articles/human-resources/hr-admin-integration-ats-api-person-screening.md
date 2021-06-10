---
title: Triagem da pessoa
description: Este tópico descreve a entidade Triagem da pessoa para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 9d29b26094e307c3f68d57f297ab3614f3a5ccae
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059271"
---
# <a name="person-screening"></a><span data-ttu-id="01fbf-103">Triagem da pessoa</span><span class="sxs-lookup"><span data-stu-id="01fbf-103">Person screening</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="01fbf-104">Este tópico descreve a entidade Triagem da pessoa para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="01fbf-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="01fbf-105">Nome físico: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="01fbf-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="01fbf-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="01fbf-106">Description</span></span>

<span data-ttu-id="01fbf-107">Esta entidade descreve as triagens que um candidato passou ou deve passar para o emprego.</span><span class="sxs-lookup"><span data-stu-id="01fbf-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="01fbf-108">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="01fbf-108">JSON representation</span></span>

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a><span data-ttu-id="01fbf-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="01fbf-109">Properties</span></span>

| <span data-ttu-id="01fbf-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="01fbf-110">Property</span></span><br><span data-ttu-id="01fbf-111">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="01fbf-111">**Physical name**</span></span><br><span data-ttu-id="01fbf-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="01fbf-112">**_Type_**</span></span> | <span data-ttu-id="01fbf-113">Uso</span><span class="sxs-lookup"><span data-stu-id="01fbf-113">Use</span></span> | <span data-ttu-id="01fbf-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="01fbf-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="01fbf-115">**ID da entidade de triagem da pessoa**</span><span class="sxs-lookup"><span data-stu-id="01fbf-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="01fbf-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="01fbf-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="01fbf-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="01fbf-117">*GUID*</span></span> | <span data-ttu-id="01fbf-118">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="01fbf-118">Read-only</span></span><br><span data-ttu-id="01fbf-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="01fbf-119">Required</span></span><br><span data-ttu-id="01fbf-120">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="01fbf-120">System-generated</span></span> | <span data-ttu-id="01fbf-121">Identificador principal exclusivo do registro de triagem da pessoa.</span><span class="sxs-lookup"><span data-stu-id="01fbf-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="01fbf-122">**Número do participante**</span><span class="sxs-lookup"><span data-stu-id="01fbf-122">**Party Number**</span></span><br><span data-ttu-id="01fbf-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="01fbf-123">mshr_partynumber</span></span><br><span data-ttu-id="01fbf-124">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="01fbf-124">*String*</span></span> | <span data-ttu-id="01fbf-125">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="01fbf-125">Read/write</span></span><br><span data-ttu-id="01fbf-126">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="01fbf-126">Required</span></span> | <span data-ttu-id="01fbf-127">O número do participante (pessoa) associado ao candidato.</span><span class="sxs-lookup"><span data-stu-id="01fbf-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="01fbf-128">**Valor da ID da pessoa**</span><span class="sxs-lookup"><span data-stu-id="01fbf-128">**Person ID Value**</span></span><br><span data-ttu-id="01fbf-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="01fbf-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="01fbf-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="01fbf-130">*GUID*</span></span> | <span data-ttu-id="01fbf-131">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="01fbf-131">Read-only</span></span><br><span data-ttu-id="01fbf-132">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="01fbf-132">Required</span></span><br><span data-ttu-id="01fbf-133">Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="01fbf-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="01fbf-134">O identificador gerado pelo sistema do registro da entidade de participante (pessoa).</span><span class="sxs-lookup"><span data-stu-id="01fbf-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="01fbf-135">**ID de tipo de triagem**</span><span class="sxs-lookup"><span data-stu-id="01fbf-135">**Screening Type ID**</span></span><br><span data-ttu-id="01fbf-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="01fbf-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="01fbf-137">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="01fbf-137">*String*</span></span> | <span data-ttu-id="01fbf-138">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="01fbf-138">Read/write</span></span><br><span data-ttu-id="01fbf-139">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="01fbf-139">Required</span></span><br><span data-ttu-id="01fbf-140">Chave estrangeira: ScreeningType</span><span class="sxs-lookup"><span data-stu-id="01fbf-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="01fbf-141">O identificador do tipo de triagem definido em Human Resources.</span><span class="sxs-lookup"><span data-stu-id="01fbf-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="01fbf-142">**Valor de ID do tipo de triagem**</span><span class="sxs-lookup"><span data-stu-id="01fbf-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="01fbf-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="01fbf-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="01fbf-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="01fbf-144">*GUID*</span></span> | <span data-ttu-id="01fbf-145">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="01fbf-145">Read-only</span></span><br><span data-ttu-id="01fbf-146">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="01fbf-146">Required</span></span><br><span data-ttu-id="01fbf-147">Chave estrangeira: mshr_hcmscreeningtypeentityid de mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="01fbf-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="01fbf-148">Identificador gerado pelo sistema do registro de tipo de triagem na entidade associada.</span><span class="sxs-lookup"><span data-stu-id="01fbf-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="01fbf-149">**Exigido por**</span><span class="sxs-lookup"><span data-stu-id="01fbf-149">**Required By**</span></span><br><span data-ttu-id="01fbf-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="01fbf-150">mshr_requiredby</span></span><br><span data-ttu-id="01fbf-151">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="01fbf-151">*Datetime*</span></span> | <span data-ttu-id="01fbf-152">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="01fbf-152">Read/write</span></span><br><span data-ttu-id="01fbf-153">Opcional</span><span class="sxs-lookup"><span data-stu-id="01fbf-153">Optional</span></span> | <span data-ttu-id="01fbf-154">A data na qual a triagem deve ser concluída.</span><span class="sxs-lookup"><span data-stu-id="01fbf-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="01fbf-155">**Status**</span><span class="sxs-lookup"><span data-stu-id="01fbf-155">**Status**</span></span><br><span data-ttu-id="01fbf-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="01fbf-156">mshr_status</span></span><br><span data-ttu-id="01fbf-157">*conjunto de opções mshr_hcmcompletionstatus*</span><span class="sxs-lookup"><span data-stu-id="01fbf-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="01fbf-158">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="01fbf-158">Read/write</span></span><br><span data-ttu-id="01fbf-159">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="01fbf-159">Required</span></span> | <span data-ttu-id="01fbf-160">Fornece o status do candidato para a triagem.</span><span class="sxs-lookup"><span data-stu-id="01fbf-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="01fbf-161">**Data de conclusão**</span><span class="sxs-lookup"><span data-stu-id="01fbf-161">**Completed Date**</span></span><br><span data-ttu-id="01fbf-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="01fbf-162">mshr_completeddate</span></span><br><span data-ttu-id="01fbf-163">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="01fbf-163">*Datetime*</span></span> | <span data-ttu-id="01fbf-164">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="01fbf-164">Read/write</span></span><br><span data-ttu-id="01fbf-165">Opcional</span><span class="sxs-lookup"><span data-stu-id="01fbf-165">Optional</span></span> | <span data-ttu-id="01fbf-166">A data em que a triagem foi concluída.</span><span class="sxs-lookup"><span data-stu-id="01fbf-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="01fbf-167">**Observação**</span><span class="sxs-lookup"><span data-stu-id="01fbf-167">**Notes**</span></span><br><span data-ttu-id="01fbf-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="01fbf-168">mshr_note</span></span><br><span data-ttu-id="01fbf-169">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="01fbf-169">*String*</span></span> | <span data-ttu-id="01fbf-170">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="01fbf-170">Read/write</span></span><br><span data-ttu-id="01fbf-171">Opcional</span><span class="sxs-lookup"><span data-stu-id="01fbf-171">Optional</span></span> | <span data-ttu-id="01fbf-172">Observações para uso por gerentes e recrutadores de contratação.</span><span class="sxs-lookup"><span data-stu-id="01fbf-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="01fbf-173">Consulte também</span><span class="sxs-lookup"><span data-stu-id="01fbf-173">See also</span></span>

[<span data-ttu-id="01fbf-174">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="01fbf-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="01fbf-175">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="01fbf-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]