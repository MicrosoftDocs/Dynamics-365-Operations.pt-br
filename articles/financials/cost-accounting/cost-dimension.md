---
title: "Criar dimensões e importar membros da dimensão"
description: "A contabilização de custos é um módulo independente que requer dados mestre de outros módulos."
author: YuyuScheller
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0012761b3aa8ce391b956329a9e249e5c9339db7
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="create-dimensions-and-import-dimension-members"></a><span data-ttu-id="3f783-103">Criar dimensões e importar membros da dimensão</span><span class="sxs-lookup"><span data-stu-id="3f783-103">Create dimensions and import dimension members</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="3f783-104">A contabilização de custos é um módulo independente que requer dados de outros módulos.</span><span class="sxs-lookup"><span data-stu-id="3f783-104">Cost accounting is an independent module that requires data from other modules.</span></span> <span data-ttu-id="3f783-105">Esses dados são classificados como segue:</span><span class="sxs-lookup"><span data-stu-id="3f783-105">This data is categorized into the following:</span></span>

-  <span data-ttu-id="3f783-106">Elementos de custo</span><span class="sxs-lookup"><span data-stu-id="3f783-106">Cost elements</span></span>
-  <span data-ttu-id="3f783-107">Objetos de custo</span><span class="sxs-lookup"><span data-stu-id="3f783-107">Cost objects</span></span>
-  <span data-ttu-id="3f783-108">Dimensões estatísticas</span><span class="sxs-lookup"><span data-stu-id="3f783-108">Statistical dimensions</span></span>

<span data-ttu-id="3f783-109">Um **Elemento de custo** corresponde a um item relevante a custo no plano de contas.</span><span class="sxs-lookup"><span data-stu-id="3f783-109">A **Cost element** corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="3f783-110">Um **Objeto de custo** corresponde a qualquer tipo de dimensão financeira, como produtos, centros de custos e projetos que você deseja estimar, alocar custos ou medir diretamente.</span><span class="sxs-lookup"><span data-stu-id="3f783-110">A **Cost object** corresponds to any type of financial dimension, such as products, cost centers, and projects that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="3f783-111">Uma **Dimensão estatística** e seus membros são usados para registrar entradas não monetárias.</span><span class="sxs-lookup"><span data-stu-id="3f783-111">A **Statistical dimension** and its members are used to register non-monetary entries.</span></span> <span data-ttu-id="3f783-112">Os membros da dimensão estatística podem ser utilizados como base de alocação na distribuição e alocação de custos</span><span class="sxs-lookup"><span data-stu-id="3f783-112">Statistical dimension members can be used as an allocation base in cost distribution and allocation</span></span> 

<span data-ttu-id="3f783-113">O diagrama a seguir ilustra as dimensões usadas na Contabilização de custos.</span><span class="sxs-lookup"><span data-stu-id="3f783-113">The following diagram illustrates the dimensions that are used in Cost accounting.</span></span>

<span data-ttu-id="3f783-114">[![Dimensões na contabilização de custos](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="3f783-114">[![Cost accounting dimensions](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)</span></span>

<span data-ttu-id="3f783-115">Depois que dados são importados para a Contabilização de custo, você pode usá-los para construir as várias perspectivas que fornecem ideias a gerentes em todos os níveis da organização.</span><span class="sxs-lookup"><span data-stu-id="3f783-115">After the data is imported into Cost accounting, you can use it to build various perspectives that provide insights to managers at all levels of the organization.</span></span> <span data-ttu-id="3f783-116">Os seguintes tópicos fornecem informações sobre a criação de dimensões e a importação de membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="3f783-116">The following topics provide information about creating dimensions and importing dimension members.</span></span> 

-  [<span data-ttu-id="3f783-117">Dimensões do elemento de custo</span><span class="sxs-lookup"><span data-stu-id="3f783-117">Cost element dimensions</span></span>](cost-elements.md)
-  [<span data-ttu-id="3f783-118">Criar elementos de custo (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="3f783-118">Create cost elements (Task guide)</span></span>](./tasks/create-cost-elements.md)
-  [<span data-ttu-id="3f783-119">Dimensões de objeto de custo</span><span class="sxs-lookup"><span data-stu-id="3f783-119">Cost object dimensions</span></span>](cost-objects.md)
-  [<span data-ttu-id="3f783-120">Criar elementos de custo (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="3f783-120">Create cost elements (Task guide)</span></span>](./tasks/create-cost-objects.md)
-  [<span data-ttu-id="3f783-121">Mapear membros de dimensão de elemento de custo para um conjunto comum de membros de dimensão</span><span class="sxs-lookup"><span data-stu-id="3f783-121">Map cost element dimension members to a common set of dimension members</span></span>](map-cost-elements-dimension-members.md)
-  [<span data-ttu-id="3f783-122">Mapear uma dimensão de elemento de custo (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="3f783-122">Map a cost element dimension (Task guide)</span></span>](./tasks/map-cost-element-dimension.md)
-  [<span data-ttu-id="3f783-123">Membros estatísticos de dimensões e modelos de fornecedores de medições estatísticas</span><span class="sxs-lookup"><span data-stu-id="3f783-123">Statistical dimension members and statistical measure provider templates</span></span>](statistical-measure-provider-template.md)







