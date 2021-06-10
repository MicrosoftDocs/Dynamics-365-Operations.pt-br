---
title: Tipo de certificado
description: Este tópico descreve a entidade de tipo Certificado para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: b8e979f242eb689b730b7f8a8684b3e697adbee6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054683"
---
# <a name="certificate-type"></a><span data-ttu-id="12c7a-103">Tipo de certificado</span><span class="sxs-lookup"><span data-stu-id="12c7a-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="12c7a-104">Este tópico descreve a entidade de tipo Certificado para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="12c7a-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="12c7a-105">Nome físico: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="12c7a-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="12c7a-106">descrição</span><span class="sxs-lookup"><span data-stu-id="12c7a-106">Description</span></span>

<span data-ttu-id="12c7a-107">Esta entidade define a lista de tipos de certificados profissionais configurados no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="12c7a-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="12c7a-108">A entidade não é específica de uma entidade legal (empresa).</span><span class="sxs-lookup"><span data-stu-id="12c7a-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="12c7a-109">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="12c7a-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="12c7a-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="12c7a-110">Properties</span></span>

| <span data-ttu-id="12c7a-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="12c7a-111">Property</span></span><br><span data-ttu-id="12c7a-112">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="12c7a-112">**Physical name**</span></span><br><span data-ttu-id="12c7a-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="12c7a-113">**_Type_**</span></span> | <span data-ttu-id="12c7a-114">Usar</span><span class="sxs-lookup"><span data-stu-id="12c7a-114">Use</span></span> | <span data-ttu-id="12c7a-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="12c7a-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="12c7a-116">**ID da entidade do tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="12c7a-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="12c7a-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="12c7a-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="12c7a-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="12c7a-118">*GUID*</span></span> | <span data-ttu-id="12c7a-119">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="12c7a-119">Read-only</span></span><br><span data-ttu-id="12c7a-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="12c7a-120">Required</span></span> 
<span data-ttu-id="12c7a-121">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="12c7a-121">System-generated</span></span> | <span data-ttu-id="12c7a-122">Identificador principal exclusivo do tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="12c7a-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="12c7a-123">**Tipo de certificado**</span><span class="sxs-lookup"><span data-stu-id="12c7a-123">**Certificate Type**</span></span><br><span data-ttu-id="12c7a-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="12c7a-124">mshr_certificatetype</span></span><br><span data-ttu-id="12c7a-125">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="12c7a-125">*String*</span></span> | <span data-ttu-id="12c7a-126">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="12c7a-126">Read/write</span></span><br><span data-ttu-id="12c7a-127">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="12c7a-127">Required</span></span> | <span data-ttu-id="12c7a-128">Identificador exclusivo legível pelo usuário do tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="12c7a-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="12c7a-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="12c7a-129">**Description**</span></span><br><span data-ttu-id="12c7a-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="12c7a-130">mshr_description</span></span><br><span data-ttu-id="12c7a-131">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="12c7a-131">*String*</span></span> | <span data-ttu-id="12c7a-132">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="12c7a-132">Read/write</span></span><br><span data-ttu-id="12c7a-133">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="12c7a-133">Required</span></span> | <span data-ttu-id="12c7a-134">Descrição do tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="12c7a-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="12c7a-135">**Exigir renovação**</span><span class="sxs-lookup"><span data-stu-id="12c7a-135">**Require Renewal**</span></span><br><span data-ttu-id="12c7a-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="12c7a-136">mshr_requirerenewal</span></span><br><span data-ttu-id="12c7a-137">*opção mshr_noyes definida*</span><span class="sxs-lookup"><span data-stu-id="12c7a-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="12c7a-138">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="12c7a-138">Read/write</span></span><br><span data-ttu-id="12c7a-139">Opcional</span><span class="sxs-lookup"><span data-stu-id="12c7a-139">Optional</span></span> | <span data-ttu-id="12c7a-140">Indica se a renovação é necessária para o certificado.</span><span class="sxs-lookup"><span data-stu-id="12c7a-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="12c7a-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="12c7a-141">See also</span></span>

[<span data-ttu-id="12c7a-142">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="12c7a-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="12c7a-143">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="12c7a-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]