---
title: Nível de avaliação
description: Este tópico descreve a entidade Nível de avaliação para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2dbdbea7087d8bca8563da10d1bf9a97df24e8b3
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464733"
---
# <a name="rating-level"></a><span data-ttu-id="a875a-103">Nível de avaliação</span><span class="sxs-lookup"><span data-stu-id="a875a-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a875a-104">Este tópico descreve a entidade Nível de avaliação para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a875a-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="a875a-105">Nome físico: mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="a875a-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="a875a-106">descrição</span><span class="sxs-lookup"><span data-stu-id="a875a-106">Description</span></span>

<span data-ttu-id="a875a-107">Esta entidade fornece os níveis de classificação disponíveis para as habilidades.</span><span class="sxs-lookup"><span data-stu-id="a875a-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="a875a-108">Os níveis de classificação se aplicam a todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="a875a-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="a875a-109">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="a875a-109">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="a875a-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="a875a-110">Properties</span></span>

| <span data-ttu-id="a875a-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="a875a-111">Property</span></span><br><span data-ttu-id="a875a-112">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="a875a-112">**Physical name**</span></span><br><span data-ttu-id="a875a-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="a875a-113">**_Type_**</span></span> | <span data-ttu-id="a875a-114">Uso</span><span class="sxs-lookup"><span data-stu-id="a875a-114">Use</span></span> | <span data-ttu-id="a875a-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="a875a-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a875a-116">**ID de entidade de nível de classificação**</span><span class="sxs-lookup"><span data-stu-id="a875a-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="a875a-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="a875a-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="a875a-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a875a-118">*GUID*</span></span> | <span data-ttu-id="a875a-119">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a875a-119">Read-only</span></span><br><span data-ttu-id="a875a-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a875a-120">Required</span></span><br><span data-ttu-id="a875a-121">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="a875a-121">System-generated</span></span> | <span data-ttu-id="a875a-122">O identificador exclusivo gerado pelo sistema para o nível.</span><span class="sxs-lookup"><span data-stu-id="a875a-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="a875a-123">**ID de nível de classificação**</span><span class="sxs-lookup"><span data-stu-id="a875a-123">**Rating Level ID**</span></span><br><span data-ttu-id="a875a-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="a875a-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="a875a-125">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a875a-125">*String*</span></span> | <span data-ttu-id="a875a-126">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="a875a-126">Read/write</span></span><br><span data-ttu-id="a875a-127">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a875a-127">Required</span></span> | <span data-ttu-id="a875a-128">Identificador exclusivo legível pelo usuário para o nível.</span><span class="sxs-lookup"><span data-stu-id="a875a-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="a875a-129">**ID do modelo de classificação**</span><span class="sxs-lookup"><span data-stu-id="a875a-129">**Rating Model ID**</span></span><br><span data-ttu-id="a875a-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="a875a-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="a875a-131">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a875a-131">*String*</span></span> | <span data-ttu-id="a875a-132">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="a875a-132">Read/write</span></span><br><span data-ttu-id="a875a-133">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a875a-133">Required</span></span> | <span data-ttu-id="a875a-134">O modelo de avaliação ao qual o nível de classificação pertence.</span><span class="sxs-lookup"><span data-stu-id="a875a-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="a875a-135">**ID de entidade de modelo de classificação**</span><span class="sxs-lookup"><span data-stu-id="a875a-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="a875a-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="a875a-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="a875a-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a875a-137">*GUID*</span></span> | <span data-ttu-id="a875a-138">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a875a-138">Read-only</span></span><br><span data-ttu-id="a875a-139">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a875a-139">Required</span></span><br><span data-ttu-id="a875a-140">Chave estrangeira: mshr_hcmratingmodelentityid de mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="a875a-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="a875a-141">O identificador gerado pelo sistema para o modelo de avaliação ao qual o nível de classificação pertence.</span><span class="sxs-lookup"><span data-stu-id="a875a-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="a875a-142">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a875a-142">**Description**</span></span><br><span data-ttu-id="a875a-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="a875a-143">mshr_description</span></span><br><span data-ttu-id="a875a-144">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a875a-144">*String*</span></span> | <span data-ttu-id="a875a-145">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="a875a-145">Read/write</span></span><br><span data-ttu-id="a875a-146">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a875a-146">Required</span></span> | <span data-ttu-id="a875a-147">A descrição do nível de classificação.</span><span class="sxs-lookup"><span data-stu-id="a875a-147">The description of the rating level.</span></span> |
| <span data-ttu-id="a875a-148">**Fator**</span><span class="sxs-lookup"><span data-stu-id="a875a-148">**Factor**</span></span><br><span data-ttu-id="a875a-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="a875a-149">mshr_factor</span></span><br><span data-ttu-id="a875a-150">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="a875a-150">*Integer*</span></span> | <span data-ttu-id="a875a-151">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="a875a-151">Read/write</span></span><br><span data-ttu-id="a875a-152">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a875a-152">Required</span></span> | <span data-ttu-id="a875a-153">O fator para o nível de classificação.</span><span class="sxs-lookup"><span data-stu-id="a875a-153">The factor for the rating level.</span></span> <span data-ttu-id="a875a-154">Ao comparar itens com um número diferente de níveis de classificação, o fator é usado para normalizar as pontuações.</span><span class="sxs-lookup"><span data-stu-id="a875a-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="a875a-155">O valor deve ser um inteiro entre 0 e 9.</span><span class="sxs-lookup"><span data-stu-id="a875a-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="a875a-156">**Nota**</span><span class="sxs-lookup"><span data-stu-id="a875a-156">**Note**</span></span><br><span data-ttu-id="a875a-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="a875a-157">mshr_note</span></span><br><span data-ttu-id="a875a-158">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a875a-158">*String*</span></span> | <span data-ttu-id="a875a-159">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="a875a-159">Read/write</span></span><br><span data-ttu-id="a875a-160">Opcional</span><span class="sxs-lookup"><span data-stu-id="a875a-160">Optional</span></span> | <span data-ttu-id="a875a-161">Qualquer nota associada ao nível de classificação.</span><span class="sxs-lookup"><span data-stu-id="a875a-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="a875a-162">**Campo principal**</span><span class="sxs-lookup"><span data-stu-id="a875a-162">**Primary Field**</span></span><br><span data-ttu-id="a875a-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="a875a-163">mshr_primaryfield</span></span><br><span data-ttu-id="a875a-164">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="a875a-164">*String*</span></span> | <span data-ttu-id="a875a-165">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="a875a-165">Read-only</span></span><br><span data-ttu-id="a875a-166">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a875a-166">Required</span></span> | <span data-ttu-id="a875a-167">Campo a ser usado como identificador do registro de entidade.</span><span class="sxs-lookup"><span data-stu-id="a875a-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="a875a-168">Combinação de ID do nível de classificação e ID do modelo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="a875a-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a875a-169">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a875a-169">See also</span></span>

[<span data-ttu-id="a875a-170">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="a875a-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="a875a-171">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="a875a-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]