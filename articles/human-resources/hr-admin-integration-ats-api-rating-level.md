---
title: Nível de avaliação
description: Este tópico descreve a entidade Nível de avaliação para o Dynamics 365 Human Resources.
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
ms.openlocfilehash: 8bbd10bcc47a928070da7cd82e6d996f71c65698
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054827"
---
# <a name="rating-level"></a><span data-ttu-id="f51b8-103">Nível de avaliação</span><span class="sxs-lookup"><span data-stu-id="f51b8-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f51b8-104">Este tópico descreve a entidade Nível de avaliação para o Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f51b8-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f51b8-105">Nome físico: mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="f51b8-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="f51b8-106">descrição</span><span class="sxs-lookup"><span data-stu-id="f51b8-106">Description</span></span>

<span data-ttu-id="f51b8-107">Esta entidade fornece os níveis de classificação disponíveis para as habilidades.</span><span class="sxs-lookup"><span data-stu-id="f51b8-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="f51b8-108">Os níveis de classificação se aplicam a todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="f51b8-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="f51b8-109">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="f51b8-109">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="f51b8-110">Propriedades</span><span class="sxs-lookup"><span data-stu-id="f51b8-110">Properties</span></span>

| <span data-ttu-id="f51b8-111">Propriedade</span><span class="sxs-lookup"><span data-stu-id="f51b8-111">Property</span></span><br><span data-ttu-id="f51b8-112">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="f51b8-112">**Physical name**</span></span><br><span data-ttu-id="f51b8-113">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="f51b8-113">**_Type_**</span></span> | <span data-ttu-id="f51b8-114">Uso</span><span class="sxs-lookup"><span data-stu-id="f51b8-114">Use</span></span> | <span data-ttu-id="f51b8-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="f51b8-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f51b8-116">**ID de entidade de nível de classificação**</span><span class="sxs-lookup"><span data-stu-id="f51b8-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="f51b8-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="f51b8-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="f51b8-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f51b8-118">*GUID*</span></span> | <span data-ttu-id="f51b8-119">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f51b8-119">Read-only</span></span><br><span data-ttu-id="f51b8-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="f51b8-120">Required</span></span><br><span data-ttu-id="f51b8-121">Gerado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="f51b8-121">System-generated</span></span> | <span data-ttu-id="f51b8-122">O identificador exclusivo gerado pelo sistema para o nível.</span><span class="sxs-lookup"><span data-stu-id="f51b8-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="f51b8-123">**ID de nível de classificação**</span><span class="sxs-lookup"><span data-stu-id="f51b8-123">**Rating Level ID**</span></span><br><span data-ttu-id="f51b8-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="f51b8-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="f51b8-125">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f51b8-125">*String*</span></span> | <span data-ttu-id="f51b8-126">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="f51b8-126">Read/write</span></span><br><span data-ttu-id="f51b8-127">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="f51b8-127">Required</span></span> | <span data-ttu-id="f51b8-128">Identificador exclusivo legível pelo usuário para o nível.</span><span class="sxs-lookup"><span data-stu-id="f51b8-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="f51b8-129">**ID do modelo de classificação**</span><span class="sxs-lookup"><span data-stu-id="f51b8-129">**Rating Model ID**</span></span><br><span data-ttu-id="f51b8-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="f51b8-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="f51b8-131">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f51b8-131">*String*</span></span> | <span data-ttu-id="f51b8-132">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="f51b8-132">Read/write</span></span><br><span data-ttu-id="f51b8-133">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="f51b8-133">Required</span></span> | <span data-ttu-id="f51b8-134">O modelo de avaliação ao qual o nível de classificação pertence.</span><span class="sxs-lookup"><span data-stu-id="f51b8-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="f51b8-135">**ID de entidade de modelo de classificação**</span><span class="sxs-lookup"><span data-stu-id="f51b8-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="f51b8-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="f51b8-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="f51b8-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f51b8-137">*GUID*</span></span> | <span data-ttu-id="f51b8-138">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f51b8-138">Read-only</span></span><br><span data-ttu-id="f51b8-139">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="f51b8-139">Required</span></span><br><span data-ttu-id="f51b8-140">Chave estrangeira: mshr_hcmratingmodelentityid de mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="f51b8-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="f51b8-141">O identificador gerado pelo sistema para o modelo de avaliação ao qual o nível de classificação pertence.</span><span class="sxs-lookup"><span data-stu-id="f51b8-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="f51b8-142">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f51b8-142">**Description**</span></span><br><span data-ttu-id="f51b8-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="f51b8-143">mshr_description</span></span><br><span data-ttu-id="f51b8-144">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f51b8-144">*String*</span></span> | <span data-ttu-id="f51b8-145">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="f51b8-145">Read/write</span></span><br><span data-ttu-id="f51b8-146">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="f51b8-146">Required</span></span> | <span data-ttu-id="f51b8-147">A descrição do nível de classificação.</span><span class="sxs-lookup"><span data-stu-id="f51b8-147">The description of the rating level.</span></span> |
| <span data-ttu-id="f51b8-148">**Fator**</span><span class="sxs-lookup"><span data-stu-id="f51b8-148">**Factor**</span></span><br><span data-ttu-id="f51b8-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="f51b8-149">mshr_factor</span></span><br><span data-ttu-id="f51b8-150">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="f51b8-150">*Integer*</span></span> | <span data-ttu-id="f51b8-151">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="f51b8-151">Read/write</span></span><br><span data-ttu-id="f51b8-152">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="f51b8-152">Required</span></span> | <span data-ttu-id="f51b8-153">O fator para o nível de classificação.</span><span class="sxs-lookup"><span data-stu-id="f51b8-153">The factor for the rating level.</span></span> <span data-ttu-id="f51b8-154">Ao comparar itens com um número diferente de níveis de classificação, o fator é usado para normalizar as pontuações.</span><span class="sxs-lookup"><span data-stu-id="f51b8-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="f51b8-155">O valor deve ser um inteiro entre 0 e 9.</span><span class="sxs-lookup"><span data-stu-id="f51b8-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="f51b8-156">**Nota**</span><span class="sxs-lookup"><span data-stu-id="f51b8-156">**Note**</span></span><br><span data-ttu-id="f51b8-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="f51b8-157">mshr_note</span></span><br><span data-ttu-id="f51b8-158">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f51b8-158">*String*</span></span> | <span data-ttu-id="f51b8-159">Ler/gravar</span><span class="sxs-lookup"><span data-stu-id="f51b8-159">Read/write</span></span><br><span data-ttu-id="f51b8-160">Opcional</span><span class="sxs-lookup"><span data-stu-id="f51b8-160">Optional</span></span> | <span data-ttu-id="f51b8-161">Qualquer nota associada ao nível de classificação.</span><span class="sxs-lookup"><span data-stu-id="f51b8-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="f51b8-162">**Campo principal**</span><span class="sxs-lookup"><span data-stu-id="f51b8-162">**Primary Field**</span></span><br><span data-ttu-id="f51b8-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="f51b8-163">mshr_primaryfield</span></span><br><span data-ttu-id="f51b8-164">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="f51b8-164">*String*</span></span> | <span data-ttu-id="f51b8-165">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="f51b8-165">Read-only</span></span><br><span data-ttu-id="f51b8-166">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="f51b8-166">Required</span></span> | <span data-ttu-id="f51b8-167">Campo a ser usado como identificador do registro de entidade.</span><span class="sxs-lookup"><span data-stu-id="f51b8-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="f51b8-168">Combinação de ID do nível de classificação e ID do modelo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f51b8-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f51b8-169">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f51b8-169">See also</span></span>

[<span data-ttu-id="f51b8-170">Introdução da API de integração do sistema de acompanhamento de candidatos</span><span class="sxs-lookup"><span data-stu-id="f51b8-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f51b8-171">Exemplo de consulta de candidato a ser contratado</span><span class="sxs-lookup"><span data-stu-id="f51b8-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]