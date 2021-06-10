---
title: API de detalhes do trabalho
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Detalhes do trabalho no Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 562b9f505311b6cfe505a76fc5c0a384eb641936
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054755"
---
# <a name="job-detail-api"></a><span data-ttu-id="db2a4-103">API de detalhes do trabalho</span><span class="sxs-lookup"><span data-stu-id="db2a4-103">Job detail API</span></span>

<span data-ttu-id="db2a4-104">Este tópico fornece detalhes e um exemplo de consulta da entidade Detalhes do trabalho no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="db2a4-104">This topic provides details and an example query for the Job detail entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="db2a4-105">Propriedades</span><span class="sxs-lookup"><span data-stu-id="db2a4-105">Properties</span></span>

| <span data-ttu-id="db2a4-106">Propriedade</span><span class="sxs-lookup"><span data-stu-id="db2a4-106">Property</span></span><br><span data-ttu-id="db2a4-107">**Nome físico**</span><span class="sxs-lookup"><span data-stu-id="db2a4-107">**Physical name**</span></span><br><span data-ttu-id="db2a4-108">**_Tipo_**</span><span class="sxs-lookup"><span data-stu-id="db2a4-108">**_Type_**</span></span> | <span data-ttu-id="db2a4-109">Usar</span><span class="sxs-lookup"><span data-stu-id="db2a4-109">Use</span></span> | <span data-ttu-id="db2a4-110">descrição</span><span class="sxs-lookup"><span data-stu-id="db2a4-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="db2a4-111">**ID do trabalho**</span><span class="sxs-lookup"><span data-stu-id="db2a4-111">**Job ID**</span></span><br><span data-ttu-id="db2a4-112">mshr_jobid</span><span class="sxs-lookup"><span data-stu-id="db2a4-112">mshr_jobid</span></span><br><span data-ttu-id="db2a4-113">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="db2a4-113">*String*</span></span> | <span data-ttu-id="db2a4-114">Somente leitura</span><span class="sxs-lookup"><span data-stu-id="db2a4-114">Read-only</span></span><br><span data-ttu-id="db2a4-115">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="db2a4-115">Required</span></span> | <span data-ttu-id="db2a4-116">ID exclusiva de um trabalho.</span><span class="sxs-lookup"><span data-stu-id="db2a4-116">Unique ID for a job.</span></span> |
| <span data-ttu-id="db2a4-117">**Limite de preço de mercado baixo**</span><span class="sxs-lookup"><span data-stu-id="db2a4-117">**Market price low threshold**</span></span><br><span data-ttu-id="db2a4-118">mshr_marketpricelowthreshold</span><span class="sxs-lookup"><span data-stu-id="db2a4-118">mshr_marketpricelowthreshold</span></span><br><span data-ttu-id="db2a4-119">*Decimal*</span><span class="sxs-lookup"><span data-stu-id="db2a4-119">*Decimal*</span></span> | | <span data-ttu-id="db2a4-120">Um valor GUID gerado pelo sistema para identificar exclusivamente a posição.</span><span class="sxs-lookup"><span data-stu-id="db2a4-120">A system-generated GUID value to uniquely identify the position.</span></span>  |
