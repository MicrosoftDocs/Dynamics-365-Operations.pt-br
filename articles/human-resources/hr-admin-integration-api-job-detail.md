---
title: API de detalhes do trabalho
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Detalhes do trabalho no Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4f15282bf72340cb1a832ff3264361472d0a6c70
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881925"
---
# <a name="job-detail-api"></a><span data-ttu-id="15441-103">API de detalhes do trabalho</span><span class="sxs-lookup"><span data-stu-id="15441-103">Job detail API</span></span>

<span data-ttu-id="15441-104">Este tópico fornece detalhes e um exemplo de consulta da entidade Detalhes do trabalho no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="15441-104">This topic provides details and an example query for the Job detail entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="15441-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="15441-105">Properties</span></span>

| <span data-ttu-id="15441-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="15441-106">Property</span></span><br><span data-ttu-id="15441-107">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="15441-107">**Physical name**</span></span><br><span data-ttu-id="15441-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="15441-108">**_Type_**</span></span> | <span data-ttu-id="15441-109">Usar</span><span class="sxs-lookup"><span data-stu-id="15441-109">Use</span></span> | <span data-ttu-id="15441-110">descrição</span><span class="sxs-lookup"><span data-stu-id="15441-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="15441-111">**ID do trabalho**</span><span class="sxs-lookup"><span data-stu-id="15441-111">**Job ID**</span></span><br><span data-ttu-id="15441-112">mshr_jobid</span><span class="sxs-lookup"><span data-stu-id="15441-112">mshr_jobid</span></span><br><span data-ttu-id="15441-113">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="15441-113">*String*</span></span> | <span data-ttu-id="15441-114">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="15441-114">Read-only</span></span><br><span data-ttu-id="15441-115">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="15441-115">Required</span></span> | <span data-ttu-id="15441-116">ID exclusiva de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="15441-116">Unique ID for a job.</span></span> |
| <span data-ttu-id="15441-117">**Limite de preço de mercado baixo**</span><span class="sxs-lookup"><span data-stu-id="15441-117">**Market price low threshold**</span></span><br><span data-ttu-id="15441-118">mshr_marketpricelowthreshold</span><span class="sxs-lookup"><span data-stu-id="15441-118">mshr_marketpricelowthreshold</span></span><br><span data-ttu-id="15441-119">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="15441-119">*Decimal*</span></span> | | <span data-ttu-id="15441-120">Um valor GUID gerado pelo sistema para identificar exclusivamente a posição.</span><span class="sxs-lookup"><span data-stu-id="15441-120">A system-generated GUID value to uniquely identify the position.</span></span>  |
