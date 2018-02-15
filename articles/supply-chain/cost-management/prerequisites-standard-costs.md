---
title: "Pré-requisitos para custos padrão"
description: "Esse tópico descreve as etapas básicas para usar custos padrão."
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e63f2b4289b640e601492425331ea8f3804d139a
ms.openlocfilehash: 4f505a2de89863d1a12d415795fdfb82b3557bc0
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="prerequisites-for-standard-costs"></a><span data-ttu-id="91d5d-103">Pré-requisitos para custos padrão</span><span class="sxs-lookup"><span data-stu-id="91d5d-103">Prerequisites for standard costs</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="91d5d-104">Esse tópico descreve as etapas básicas para usar custos padrão.</span><span class="sxs-lookup"><span data-stu-id="91d5d-104">This topic describes the basic steps for using standard costs.</span></span> <span data-ttu-id="91d5d-105">As etapas subsequentes dependem das operações da empresa.</span><span class="sxs-lookup"><span data-stu-id="91d5d-105">Subsequent steps depend on the company's operations.</span></span> <span data-ttu-id="91d5d-106">Por exemplo, as etapas diferem para um ambiente de não fabricação, um ambiente de fabricação que não usa roteiros e um ambiente de fabricação que usa roteiros.</span><span class="sxs-lookup"><span data-stu-id="91d5d-106">For example, the steps differ for a nonmanufacturing environment, a manufacturing environment that doesn't use routings, and a manufacturing environment that uses routings.</span></span> 

<span data-ttu-id="91d5d-107">Para configurar custos padrão, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="91d5d-107">To set up standard costs, follow these steps.</span></span>

<span data-ttu-id="91d5d-108">**1. Crie um grupo de modelos de item para custos padrão.**</span><span class="sxs-lookup"><span data-stu-id="91d5d-108">**1. Create an item model group for standard costs.**</span></span>

<span data-ttu-id="91d5d-109">Use a página **Grupos de modelos de item** para criar um novo grupo para custos padrão e atribuir um modelo de estoque de **Custo padrão**.</span><span class="sxs-lookup"><span data-stu-id="91d5d-109">Use the **Item model groups** page to create a new group for standard costs, and assign an inventory model of **Standard cost**.</span></span> <span data-ttu-id="91d5d-110">O identificador para o grupo de modelos de item deve ser significativo, como **Custo padrão**.</span><span class="sxs-lookup"><span data-stu-id="91d5d-110">The identifier for the item model group should be meaningful, such as **Std Cost**.</span></span> <span data-ttu-id="91d5d-111">Marque as caixas de seleção para indicar que o grupo deve permitir estoque financeiro negativo e que deve lançar estoque físico e estoque financeiro.</span><span class="sxs-lookup"><span data-stu-id="91d5d-111">Select the check boxes to indicate that the group should allow financial negative inventory, and that it should post physical inventory and financial inventory.</span></span> <span data-ttu-id="91d5d-112">Esse grupo de custo padrão será atribuído aos itens.</span><span class="sxs-lookup"><span data-stu-id="91d5d-112">This standard cost group will be assigned to items.</span></span>

<span data-ttu-id="91d5d-113">**2. Defina contas contábeis relacionadas às variações de custo padrão.**</span><span class="sxs-lookup"><span data-stu-id="91d5d-113">**2. Define ledger accounts that are related to standard cost variances.**</span></span> 

<span data-ttu-id="91d5d-114">Use a página **Plano de contas** para definir contas contábeis relacionadas às variações de custo padrão.</span><span class="sxs-lookup"><span data-stu-id="91d5d-114">Use the **Chart of accounts** page to define ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="91d5d-115">Essas contas contábeis devem ser definidas antes que possam ser atribuídas na página **Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="91d5d-115">These ledger accounts must be defined before they can be assigned on the **Posting** page.</span></span> <span data-ttu-id="91d5d-116">As contas contábeis podem refletir grupos de itens e de custo.</span><span class="sxs-lookup"><span data-stu-id="91d5d-116">The ledger accounts can reflect item groups and cost groups.</span></span>

<span data-ttu-id="91d5d-117">**3. Atribua contas contábeis aos lançamentos de item relacionados às variações de custo padrão.**</span><span class="sxs-lookup"><span data-stu-id="91d5d-117">**3. Assign ledger accounts to item postings that are related to standard cost variances.**</span></span> 

<span data-ttu-id="91d5d-118">Use a página **Lançamento** para atribuir as contas contábeis relacionadas às variações de custo padrão.</span><span class="sxs-lookup"><span data-stu-id="91d5d-118">Use the **Posting** page to assign the ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="91d5d-119">Você pode especificar a conta contábil de uma variação por item (ou grupo de item) e por grupo de custos (ou tipo de grupo de custos) ou especificar que a conta contábil se aplica a todos os itens e grupos de custos.</span><span class="sxs-lookup"><span data-stu-id="91d5d-119">You can specify a variance's ledger account by item (or item group) and by cost group (or cost group type), or you can specify that the ledger account applies to all items and all cost groups.</span></span> <span data-ttu-id="91d5d-120">Essas opções correspondem a relações de custo para tabelas, grupos e tudo.</span><span class="sxs-lookup"><span data-stu-id="91d5d-120">These options correspond to cost relations for tables, groups, and all.</span></span> 

<span data-ttu-id="91d5d-121">Antes de definir as regras de lançamento de item, use a página **Combinações de transações** para habilitar relações de custo (para tabelas, grupos e tudo).</span><span class="sxs-lookup"><span data-stu-id="91d5d-121">Before you define the item posting rules, use the **Transaction combinations** page to enable cost relations (for tables, groups, and all).</span></span>

<span data-ttu-id="91d5d-122">**4. Defina parâmetros de estoque relacionados a custos padrão.**</span><span class="sxs-lookup"><span data-stu-id="91d5d-122">**4. Define inventory parameters that are related to standard costs.**</span></span> 

-  <span data-ttu-id="91d5d-123">Use a guia **Listas de materiais** na página **Parâmetros de estoque** para definir dois parâmetros de controle de custo relacionados a custos padrão.</span><span class="sxs-lookup"><span data-stu-id="91d5d-123">Use the **Bills of materials** tab on the **Inventory parameters** page to define two cost control parameters that are related to standard costs.</span></span> 

    -  <span data-ttu-id="91d5d-124">No campo **Divisão de custo**, selecione **Nenhum** ou **Sub-razão**.</span><span class="sxs-lookup"><span data-stu-id="91d5d-124">In the **Cost breakdown** field, select **None** or **Sub ledger**.</span></span> <span data-ttu-id="91d5d-125">Se você selecionar **Sub-razão**, a divisão de custo é do tipo *ativa*.</span><span class="sxs-lookup"><span data-stu-id="91d5d-125">If you select **Sub ledger**, the cost breakdown is an *active* cost breakdown.</span></span> <span data-ttu-id="91d5d-126">Uma divisão de custo ativa é crítica para calcular, reter e exibir segmentações de grupo de custo em uma estrutura de produto de vários níveis para itens de custo padrão.</span><span class="sxs-lookup"><span data-stu-id="91d5d-126">An active cost breakdown is critical for calculating, retaining, and viewing cost group segmentation across a multilevel product structure for standard cost items.</span></span> <span data-ttu-id="91d5d-127">Quando a divisão de custo é ativa, você pode relatar e analisar estoque, trabalho em andamento (WIP) e custo dos produtos vendidos (COGS) por grupo de custos em um formato de nível único, vários níveis ou total.</span><span class="sxs-lookup"><span data-stu-id="91d5d-127">When the cost breakdown is active, you can report and analyze inventory, work in process (WIP), and cost of goods sold (COGS) per cost group in a single-level, multilevel, or total format.</span></span> <span data-ttu-id="91d5d-128">Quando a divisão de custo é ativa, se você ativar o custo de um item fabricado, a segmentação de grupo de custos será armazenada no registro de custo do item.</span><span class="sxs-lookup"><span data-stu-id="91d5d-128">When the cost breakdown is active, if you activate a manufactured item's cost, the cost group segmentation will be stored in the item's cost record.</span></span> 

    -  <span data-ttu-id="91d5d-129">Se você selecionar **Nenhum**, a segmentação de grupo de custos não será mantida para itens de custo padrão.</span><span class="sxs-lookup"><span data-stu-id="91d5d-129">If you select **None**, cost group segmentation won't be maintained for standard cost items.</span></span> <span data-ttu-id="91d5d-130">Em outras palavras, o custo padrão de um item fabricado será calculado e mantido como um valor único, sem a segmentação de grupo de custos.</span><span class="sxs-lookup"><span data-stu-id="91d5d-130">In other words, a manufactured item's standard cost will be calculated and maintained as a single amount, without cost group segmentation.</span></span> <span data-ttu-id="91d5d-131">As contribuições de custo de componentes fabricados serão agregadas ao valor único.</span><span class="sxs-lookup"><span data-stu-id="91d5d-131">The cost contributions of manufactured components will be aggregated into the single amount.</span></span>

-  <span data-ttu-id="91d5d-132">No campo **Variações do Padrão**, selecione **Resumido** ou **Por grupo de custos**.</span><span class="sxs-lookup"><span data-stu-id="91d5d-132">In the **Variances to standard** field, select **Summarized** or **Per cost group**.</span></span> <span data-ttu-id="91d5d-133">Se selecionar **Por grupo de custos**, você poderá identificar variações de preço de compra e variações de produção por grupo de custos.</span><span class="sxs-lookup"><span data-stu-id="91d5d-133">If you select **Per cost group**, you can identify purchase price variances and production variances by cost group.</span></span> <span data-ttu-id="91d5d-134">Você também poderá identificar os quatro tipos de variações de produção: o tamanho do lote, a quantidade, o preço e as variações de substituição.</span><span class="sxs-lookup"><span data-stu-id="91d5d-134">You can also identify the four types of production variances: the lot size, quantity, price, and substitution variances.</span></span> <span data-ttu-id="91d5d-135">Se selecionar **Resumido**, não será possível identificar variações por grupo de custos e você não poderá identificar os quatro tipos de variações de produção.</span><span class="sxs-lookup"><span data-stu-id="91d5d-135">If you select **Summarized**, you can't identify variances by cost group, and you can't identify the four types of production variances.</span></span> <span data-ttu-id="91d5d-136">Poderá visualizar somente uma variação de produção resumida.</span><span class="sxs-lookup"><span data-stu-id="91d5d-136">You can just view a summarized production variance.</span></span>

-  <span data-ttu-id="91d5d-137">A diretiva sobre variação para padrão funciona independente da diretiva de divisão de custo.</span><span class="sxs-lookup"><span data-stu-id="91d5d-137">The policy about variance to standard works independently of the cost breakdown policy.</span></span> <span data-ttu-id="91d5d-138">Em outras palavras, você pode selecionar uma política de divisão de custo de **Nenhum** e selecionar variações por grupo de custos, de forma que as variações de produção por grupo de custos ainda sejam capturadas.</span><span class="sxs-lookup"><span data-stu-id="91d5d-138">In other words, you can select a cost breakdown policy of **None** and select variances per cost group, so that production variances by cost group will still be captured.</span></span>

<span data-ttu-id="91d5d-139">**5. Crie versões de avaliação de custo para custos padrão.**</span><span class="sxs-lookup"><span data-stu-id="91d5d-139">**5. Create costing versions for standard costs.**</span></span> 

<span data-ttu-id="91d5d-140">Use a página **Configuração de versão de avaliação de custo** para criar uma ou mais versões de avaliação de custo para custos padrão.</span><span class="sxs-lookup"><span data-stu-id="91d5d-140">Use the **Costing version setup** page to create one or more costing versions for standard costs.</span></span> <span data-ttu-id="91d5d-141">Cada versão de avaliação de custo deve ser designada por um tipo de avaliação de custo **Custo padrão** e permitir que o conteúdo inclua dados de custo.</span><span class="sxs-lookup"><span data-stu-id="91d5d-141">Each costing version must be designated by a costing type of **Standard cost** and must allow content to include cost data.</span></span>

<span data-ttu-id="91d5d-142">**6. Prepare um cliente existente para usar custos padrão.**</span><span class="sxs-lookup"><span data-stu-id="91d5d-142">**6. Prepare an existing customer to use standard costs.**</span></span> 

<span data-ttu-id="91d5d-143">Os clientes que desejarem alterar os itens existentes para um modelo de estoque de custo padrão devem usar a página **Conversões em custo padrão**.</span><span class="sxs-lookup"><span data-stu-id="91d5d-143">Customers who want to change their existing items to a standard cost inventory model must use the **Standard cost conversions** page.</span></span>


<a name="related-topics"></a><span data-ttu-id="91d5d-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="91d5d-144">Related topics</span></span>
--------

[<span data-ttu-id="91d5d-145">Visão geral de conversão de custo padrão</span><span class="sxs-lookup"><span data-stu-id="91d5d-145">Standard cost conversion overview</span></span>](standard-cost-conversion-overview.md)


