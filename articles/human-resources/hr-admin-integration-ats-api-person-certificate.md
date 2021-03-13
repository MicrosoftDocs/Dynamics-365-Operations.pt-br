---
title: Certificado de pessoa
description: Este tópico descreve a entidade Certificado de pessoa para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: fa4582dc00341a647f1ea43ed16d9dce8bfcf688
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125344"
---
# <a name="person-certificate"></a><span data-ttu-id="0d7b2-103">Certificado de pessoa</span><span class="sxs-lookup"><span data-stu-id="0d7b2-103">Person certificate</span></span>

<span data-ttu-id="0d7b2-104">Este tópico descreve a entidade Certificado de pessoa para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="0d7b2-105">Nome físico: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="0d7b2-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="0d7b2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="0d7b2-106">Description</span></span>

<span data-ttu-id="0d7b2-107">Esta entidade descreve os certificados profissionais de um candidato.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="0d7b2-108">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="0d7b2-108">JSON representation</span></span>

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="0d7b2-109">Propriedades</span><span class="sxs-lookup"><span data-stu-id="0d7b2-109">Properties</span></span>

| <span data-ttu-id="0d7b2-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="0d7b2-110">Property</span></span><br><span data-ttu-id="0d7b2-111">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-111">**Physical name**</span></span><br><span data-ttu-id="0d7b2-112">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-112">**_Type_**</span></span> | <span data-ttu-id="0d7b2-113">Uso</span><span class="sxs-lookup"><span data-stu-id="0d7b2-113">Use</span></span> | <span data-ttu-id="0d7b2-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="0d7b2-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="0d7b2-115">**ID da entidade do certificado da pessoa**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="0d7b2-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="0d7b2-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="0d7b2-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="0d7b2-117">*GUID*</span></span> | <span data-ttu-id="0d7b2-118">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0d7b2-118">Read-only</span></span><br><span data-ttu-id="0d7b2-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="0d7b2-119">Required</span></span> | <span data-ttu-id="0d7b2-120">Identificador exclusivo gerado pelo sistema para o registro de entidade do certificado da pessoa.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="0d7b2-121">**Número do participante**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-121">**Party Number**</span></span><br><span data-ttu-id="0d7b2-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="0d7b2-122">mshr_partynumber</span></span><br><span data-ttu-id="0d7b2-123">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="0d7b2-123">*String*</span></span> | <span data-ttu-id="0d7b2-124">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="0d7b2-124">Read/write</span></span><br><span data-ttu-id="0d7b2-125">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="0d7b2-125">Required</span></span> | <span data-ttu-id="0d7b2-126">A ID de participante (pessoa) do candidato.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="0d7b2-127">**Valor da ID da pessoa**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-127">**Person ID Value**</span></span><br><span data-ttu-id="0d7b2-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="0d7b2-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="0d7b2-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="0d7b2-129">*GUID*</span></span> | <span data-ttu-id="0d7b2-130">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0d7b2-130">Read-only</span></span><br><span data-ttu-id="0d7b2-131">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="0d7b2-131">Required</span></span><br><span data-ttu-id="0d7b2-132">Chave estrangeira: mshr_dirpersonentityid de mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="0d7b2-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="0d7b2-133">O identificador gerado pelo sistema do registro da entidade de participante (pessoa).</span><span class="sxs-lookup"><span data-stu-id="0d7b2-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="0d7b2-134">**ID de tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-134">**Certificate Type ID**</span></span><br><span data-ttu-id="0d7b2-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="0d7b2-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="0d7b2-136">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="0d7b2-136">*String*</span></span> | <span data-ttu-id="0d7b2-137">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="0d7b2-137">Read/write</span></span><br><span data-ttu-id="0d7b2-138">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="0d7b2-138">Required</span></span> |  <span data-ttu-id="0d7b2-139">O identificador do tipo de certificado definido em Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="0d7b2-140">**Valor de ID de tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="0d7b2-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="0d7b2-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="0d7b2-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="0d7b2-142">*GUID*</span></span> | <span data-ttu-id="0d7b2-143">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0d7b2-143">Read-only</span></span><br><span data-ttu-id="0d7b2-144">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="0d7b2-144">Required</span></span><br><span data-ttu-id="0d7b2-145">Chave estrangeira: mshr_hcmcertificatetypeentityid de mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="0d7b2-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="0d7b2-146">Identificador exclusivo gerado pelo sistema do tipo de certificado da entidade associada.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="0d7b2-147">**Data de início**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-147">**Start Date**</span></span><br><span data-ttu-id="0d7b2-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="0d7b2-148">mshr_startdate</span></span><br><span data-ttu-id="0d7b2-149">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="0d7b2-149">*Datetime*</span></span> | <span data-ttu-id="0d7b2-150">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="0d7b2-150">Read/write</span></span><br><span data-ttu-id="0d7b2-151">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="0d7b2-151">Required</span></span> | <span data-ttu-id="0d7b2-152">A data em que o certificado foi emitido.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="0d7b2-153">**Data de término**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-153">**End Date**</span></span><br><span data-ttu-id="0d7b2-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="0d7b2-154">mshr_enddate</span></span><br><span data-ttu-id="0d7b2-155">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="0d7b2-155">*Datetime*</span></span> | <span data-ttu-id="0d7b2-156">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="0d7b2-156">Read/write</span></span><br><span data-ttu-id="0d7b2-157">Opcional</span><span class="sxs-lookup"><span data-stu-id="0d7b2-157">Optional</span></span> | <span data-ttu-id="0d7b2-158">A data em que o certificado expirará.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="0d7b2-159">**Observações**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-159">**Notes**</span></span><br><span data-ttu-id="0d7b2-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="0d7b2-160">mshr_notes</span></span><br><span data-ttu-id="0d7b2-161">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="0d7b2-161">*String*</span></span> | <span data-ttu-id="0d7b2-162">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="0d7b2-162">Read/write</span></span><br><span data-ttu-id="0d7b2-163">Opcional</span><span class="sxs-lookup"><span data-stu-id="0d7b2-163">Optional</span></span> | <span data-ttu-id="0d7b2-164">Observações para uso por gerentes e recrutadores de contratação.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="0d7b2-165">**Campo principal**</span><span class="sxs-lookup"><span data-stu-id="0d7b2-165">**Primary Field**</span></span><br><span data-ttu-id="0d7b2-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="0d7b2-166">mshr_primaryfield</span></span><br><span data-ttu-id="0d7b2-167">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="0d7b2-167">*String*</span></span> | <span data-ttu-id="0d7b2-168">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="0d7b2-168">Read-only</span></span><br><span data-ttu-id="0d7b2-169">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="0d7b2-169">Required</span></span> |  <span data-ttu-id="0d7b2-170">Campo a ser usado como identificador do registro de entidade.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="0d7b2-171">Combinação de número de participante, ID de tipo de certificado e data de início.</span><span class="sxs-lookup"><span data-stu-id="0d7b2-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0d7b2-172">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0d7b2-172">See also</span></span>

[<span data-ttu-id="0d7b2-173">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="0d7b2-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="0d7b2-174">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="0d7b2-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
