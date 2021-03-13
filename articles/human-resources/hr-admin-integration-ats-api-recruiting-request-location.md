---
title: Localização da solicitação de recrutamento
description: Este tópico descreve a entidade Localização de solicitação de recrutamento para Dynamics 365 Human Resources.
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
ms.openlocfilehash: fa153b1cfcbb70294ed6da3618c83396df04f8db
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125224"
---
# <a name="recruiting-request-location"></a><span data-ttu-id="19125-103">Localização da solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="19125-103">Recruiting request location</span></span>

<span data-ttu-id="19125-104">Este tópico descreve a entidade Localização de solicitação de recrutamento para Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="19125-104">This topic describes the Recruiting request location entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="19125-105">Nome físico: mshr_hcmrecruitingrequestlocationentity</span><span class="sxs-lookup"><span data-stu-id="19125-105">Physical name: mshr_hcmrecruitingrequestlocationentity</span></span>

### <a name="description"></a><span data-ttu-id="19125-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="19125-106">Description</span></span>

<span data-ttu-id="19125-107">A lista de locais definida como locais em que os funcionários recrutados trabalharão na contratação.</span><span class="sxs-lookup"><span data-stu-id="19125-107">The list of locations defined as locations where recruited employees will work upon hiring.</span></span> <span data-ttu-id="19125-108">Estes são locais criados entre as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="19125-108">These are locations created across legal entities.</span></span>

### <a name="json-representation"></a><span data-ttu-id="19125-109">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="19125-109">JSON representation</span></span>

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a><span data-ttu-id="19125-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="19125-110">Properties</span></span>

| <span data-ttu-id="19125-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="19125-111">Property</span></span><br><span data-ttu-id="19125-112">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="19125-112">**Physical name**</span></span><br><span data-ttu-id="19125-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="19125-113">**_Type_**</span></span> | <span data-ttu-id="19125-114">Usar</span><span class="sxs-lookup"><span data-stu-id="19125-114">Use</span></span> | <span data-ttu-id="19125-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="19125-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="19125-116">**ID da localização**</span><span class="sxs-lookup"><span data-stu-id="19125-116">**Location ID**</span></span><br><span data-ttu-id="19125-117">mshr_locationid</span><span class="sxs-lookup"><span data-stu-id="19125-117">mshr_locationid</span></span><br><span data-ttu-id="19125-118">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-118">*String*</span></span> | <span data-ttu-id="19125-119">Gravação única</span><span class="sxs-lookup"><span data-stu-id="19125-119">Write-once</span></span><br><span data-ttu-id="19125-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="19125-120">Required</span></span> | <span data-ttu-id="19125-121">O identificador gerado pelo sistema, legível pelo usuário, para o local de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="19125-121">The system-generated, user-readable identifier for the recruiting location.</span></span> |
| <span data-ttu-id="19125-122">**Local da solicitação de recrutamento**</span><span class="sxs-lookup"><span data-stu-id="19125-122">**Recruiting Request Location**</span></span><br><span data-ttu-id="19125-123">mshr_recruitingrequestlocationid</span><span class="sxs-lookup"><span data-stu-id="19125-123">mshr_recruitingrequestlocationid</span></span><br><span data-ttu-id="19125-124">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-124">*String*</span></span> | <span data-ttu-id="19125-125">Gravação única</span><span class="sxs-lookup"><span data-stu-id="19125-125">Write-once</span></span><br><span data-ttu-id="19125-126">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="19125-126">Required</span></span> | <span data-ttu-id="19125-127">Identificador exclusivo definido pelo usuário para o local de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="19125-127">User-defined unique identifier for the recruiting location.</span></span> |
| <span data-ttu-id="19125-128">**ID de entidade de local de solicitação de recrutamento**</span><span class="sxs-lookup"><span data-stu-id="19125-128">**Recruiting Request Location Entity ID**</span></span><br><span data-ttu-id="19125-129">mshr_hcmrecruitingrequestlocationentityid</span><span class="sxs-lookup"><span data-stu-id="19125-129">mshr_hcmrecruitingrequestlocationentityid</span></span><br><span data-ttu-id="19125-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="19125-130">*GUID*</span></span> | <span data-ttu-id="19125-131">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19125-131">Read-only</span></span><br><span data-ttu-id="19125-132">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="19125-132">Required</span></span> | <span data-ttu-id="19125-133">Identificador exclusivo gerado pelo sistema para o registro de local da solicitação de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="19125-133">System-generated unique identifier for the recruiting request location record.</span></span> |
| <span data-ttu-id="19125-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="19125-134">**Description**</span></span><br><span data-ttu-id="19125-135">mshr_description</span><span class="sxs-lookup"><span data-stu-id="19125-135">mshr_description</span></span><br><span data-ttu-id="19125-136">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-136">*String*</span></span> | <span data-ttu-id="19125-137">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="19125-137">Read/write</span></span><br><span data-ttu-id="19125-138">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="19125-138">Required</span></span> | <span data-ttu-id="19125-139">Descrição da localização.</span><span class="sxs-lookup"><span data-stu-id="19125-139">Description of the location.</span></span> |
| <span data-ttu-id="19125-140">**ID de país/região**</span><span class="sxs-lookup"><span data-stu-id="19125-140">**Country/Region ID**</span></span><br><span data-ttu-id="19125-141">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="19125-141">mshr_countryregionid</span></span><br><span data-ttu-id="19125-142">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-142">*String*</span></span> | <span data-ttu-id="19125-143">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19125-143">Read-only</span></span><br><span data-ttu-id="19125-144">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-144">Optional</span></span> | <span data-ttu-id="19125-145">Especifica o país ou a região em que o candidato tem cidadania.</span><span class="sxs-lookup"><span data-stu-id="19125-145">Specifies the country or region where the candidate has citizenship.</span></span> |
| <span data-ttu-id="19125-146">**ID de valor de país/região**</span><span class="sxs-lookup"><span data-stu-id="19125-146">**Country/Region ID Value**</span></span><br><span data-ttu-id="19125-147">_mshr_fk_countriregion_id_value</span><span class="sxs-lookup"><span data-stu-id="19125-147">_mshr_fk_countriregion_id_value</span></span><br><span data-ttu-id="19125-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="19125-148">*GUID*</span></span> | <span data-ttu-id="19125-149">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19125-149">Read-only</span></span><br><span data-ttu-id="19125-150">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-150">Optional</span></span><br><span data-ttu-id="19125-151">Chave estrangeira: mshr_logisticaddresscountryregionentityid de mshr_logisticsaddresscountryregionentity</span><span class="sxs-lookup"><span data-stu-id="19125-151">Foreign key: mshr_logisticaddresscountryregionentityid of mshr_logisticsaddresscountryregionentity</span></span> | <span data-ttu-id="19125-152">O identificador exclusivo gerado pelo sistema do país/região do endereço.</span><span class="sxs-lookup"><span data-stu-id="19125-152">System-generated unique identifier of the country/region of the address.</span></span> |
| <span data-ttu-id="19125-153">**ZipCode**</span><span class="sxs-lookup"><span data-stu-id="19125-153">**ZipCode**</span></span><br><span data-ttu-id="19125-154">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="19125-154">mshr_zipcode</span></span><br><span data-ttu-id="19125-155">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-155">*String*</span></span> | <span data-ttu-id="19125-156">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19125-156">Read-only</span></span><br><span data-ttu-id="19125-157">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-157">Optional</span></span> | <span data-ttu-id="19125-158">CEP/código postal.</span><span class="sxs-lookup"><span data-stu-id="19125-158">Zip/postal code.</span></span> |
| <span data-ttu-id="19125-159">**Rua**</span><span class="sxs-lookup"><span data-stu-id="19125-159">**Street**</span></span><br><span data-ttu-id="19125-160">mshr_street</span><span class="sxs-lookup"><span data-stu-id="19125-160">mshr_street</span></span><br><span data-ttu-id="19125-161">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-161">*String*</span></span> | <span data-ttu-id="19125-162">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19125-162">Read-only</span></span><br><span data-ttu-id="19125-163">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-163">Optional</span></span> | <span data-ttu-id="19125-164">Endereço.</span><span class="sxs-lookup"><span data-stu-id="19125-164">Street address.</span></span> |
| <span data-ttu-id="19125-165">**Cidade**</span><span class="sxs-lookup"><span data-stu-id="19125-165">**City**</span></span><br><span data-ttu-id="19125-166">mshr_city</span><span class="sxs-lookup"><span data-stu-id="19125-166">mshr_city</span></span><br><span data-ttu-id="19125-167">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-167">*String*</span></span> | <span data-ttu-id="19125-168">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19125-168">Read-only</span></span><br><span data-ttu-id="19125-169">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-169">Optional</span></span> | <span data-ttu-id="19125-170">Cidade.</span><span class="sxs-lookup"><span data-stu-id="19125-170">City.</span></span> |
| <span data-ttu-id="19125-171">**Estado**</span><span class="sxs-lookup"><span data-stu-id="19125-171">**State**</span></span><br><span data-ttu-id="19125-172">mshr_state</span><span class="sxs-lookup"><span data-stu-id="19125-172">mshr_state</span></span><br><span data-ttu-id="19125-173">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-173">*String*</span></span> | <span data-ttu-id="19125-174">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19125-174">Read-only</span></span><br><span data-ttu-id="19125-175">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-175">Optional</span></span> | <span data-ttu-id="19125-176">Estado ou província.</span><span class="sxs-lookup"><span data-stu-id="19125-176">State or province.</span></span> |
| <span data-ttu-id="19125-177">**Município**</span><span class="sxs-lookup"><span data-stu-id="19125-177">**County**</span></span><br><span data-ttu-id="19125-178">mshr_county</span><span class="sxs-lookup"><span data-stu-id="19125-178">mshr_county</span></span><br><span data-ttu-id="19125-179">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-179">*String*</span></span> | <span data-ttu-id="19125-180">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19125-180">Read-only</span></span><br><span data-ttu-id="19125-181">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-181">Optional</span></span> | <span data-ttu-id="19125-182">Município.</span><span class="sxs-lookup"><span data-stu-id="19125-182">County.</span></span> |
| <span data-ttu-id="19125-183">**Telefone**</span><span class="sxs-lookup"><span data-stu-id="19125-183">**Telephone**</span></span><br><span data-ttu-id="19125-184">mshr_telephone</span><span class="sxs-lookup"><span data-stu-id="19125-184">mshr_telephone</span></span><br><span data-ttu-id="19125-185">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-185">*String*</span></span> | <span data-ttu-id="19125-186">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="19125-186">Read/write</span></span><br><span data-ttu-id="19125-187">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-187">Optional</span></span> | <span data-ttu-id="19125-188">Número de telefone do local.</span><span class="sxs-lookup"><span data-stu-id="19125-188">Telephone number for the location.</span></span> |
| <span data-ttu-id="19125-189">**Email**</span><span class="sxs-lookup"><span data-stu-id="19125-189">**Email**</span></span><br><span data-ttu-id="19125-190">mshr_email</span><span class="sxs-lookup"><span data-stu-id="19125-190">mshr_email</span></span><br><span data-ttu-id="19125-191">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-191">*String*</span></span> | <span data-ttu-id="19125-192">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="19125-192">Read/write</span></span><br><span data-ttu-id="19125-193">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-193">Optional</span></span> | <span data-ttu-id="19125-194">Endereço de email.</span><span class="sxs-lookup"><span data-stu-id="19125-194">Email address.</span></span> |
| <span data-ttu-id="19125-195">**Endereço na Internet**</span><span class="sxs-lookup"><span data-stu-id="19125-195">**InternetAddress**</span></span><br><span data-ttu-id="19125-196">mshr_internetaddress</span><span class="sxs-lookup"><span data-stu-id="19125-196">mshr_internetaddress</span></span><br><span data-ttu-id="19125-197">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-197">*String*</span></span> | <span data-ttu-id="19125-198">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="19125-198">Read/write</span></span><br><span data-ttu-id="19125-199">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-199">Optional</span></span> | <span data-ttu-id="19125-200">URL do site do local.</span><span class="sxs-lookup"><span data-stu-id="19125-200">URL for the location website.</span></span> |
| <span data-ttu-id="19125-201">**ID da área de dados**</span><span class="sxs-lookup"><span data-stu-id="19125-201">**Data Area ID**</span></span><br><span data-ttu-id="19125-202">mshr_dataareaid</span><span class="sxs-lookup"><span data-stu-id="19125-202">mshr_dataareaid</span></span><br><span data-ttu-id="19125-203">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="19125-203">*String*</span></span> | <span data-ttu-id="19125-204">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="19125-204">Read/write</span></span><br><span data-ttu-id="19125-205">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-205">Optional</span></span> | <span data-ttu-id="19125-206">Especifica a entidade legal (empresa).</span><span class="sxs-lookup"><span data-stu-id="19125-206">Specifies the legal entity (company).</span></span> |
| <span data-ttu-id="19125-207">**Valor da ID da área de dados**</span><span class="sxs-lookup"><span data-stu-id="19125-207">**Data Area ID Value**</span></span><br><span data-ttu-id="19125-208">_mshr_dataareaid_id_value</span><span class="sxs-lookup"><span data-stu-id="19125-208">_mshr_dataareaid_id_value</span></span><br><span data-ttu-id="19125-209">*GUID*</span><span class="sxs-lookup"><span data-stu-id="19125-209">*GUID*</span></span> | <span data-ttu-id="19125-210">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="19125-210">Read-only</span></span><br><span data-ttu-id="19125-211">Opcional</span><span class="sxs-lookup"><span data-stu-id="19125-211">Optional</span></span><br><span data-ttu-id="19125-212">Chave estrangeira: cdm_companyid da entidade cdm_company</span><span class="sxs-lookup"><span data-stu-id="19125-212">Foreign key: cdm_companyid of cdm_company entity</span></span> | <span data-ttu-id="19125-213">Valor GUID gerado pelo sistema identificando a entidade legal (empresa).</span><span class="sxs-lookup"><span data-stu-id="19125-213">System-generated GUID value identifying the legal entity (company).</span></span> |

## <a name="see-also"></a><span data-ttu-id="19125-214">Consulte também</span><span class="sxs-lookup"><span data-stu-id="19125-214">See also</span></span>

[<span data-ttu-id="19125-215">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="19125-215">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="19125-216">Consulta de exemplo de solicitação de recrutamento</span><span class="sxs-lookup"><span data-stu-id="19125-216">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
