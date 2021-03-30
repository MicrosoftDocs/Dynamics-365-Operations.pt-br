---
title: Dimensões do elemento de custo
description: Como uma colunas principal na contabilização de custo estimado, as dimensões do elemento de custo previsto são usados para categorizar e rastrear o fluxo onde os custos.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: be2f984c1ce5c76e3f995108d25f57c29e8c8457
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226346"
---
# <a name="cost-element-dimensions"></a><span data-ttu-id="9a0ff-103">Dimensões do elemento de custo</span><span class="sxs-lookup"><span data-stu-id="9a0ff-103">Cost element dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a0ff-104">Como uma colunas principal na contabilização de custo estimado, as dimensões do elemento de custo previsto são usados para categorizar e rastrear o fluxo onde os custos.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-104">As one of the core pillars in Cost accounting, cost element dimensions are used to categorize and track where costs flow to.</span></span> 

<span data-ttu-id="9a0ff-105">Um elemento de custo previsto corresponde a um item de custo relevante no plano de contas.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-105">A cost element corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="9a0ff-106">Basicamente, pode ser qualquer tipo de elemento no nível mais baixo em uma empresa em que os custos podem fluxo.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-106">Basically, it can be any type of element at the lowest level in a business where costs can flow to.</span></span> <span data-ttu-id="9a0ff-107">Elementos de custo previsto como um conceito variam contábeis a todos os recursos para relevantes.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-107">Cost elements as a concept range from ledger accounts to all cost-relevant resources.</span></span> <span data-ttu-id="9a0ff-108">Atualmente, a contabilização de custo previsto suporta contas contábeis.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-108">Currently, Cost accounting supports ledger accounts.</span></span>

## <a name="two-types-of-cost-elements"></a><span data-ttu-id="9a0ff-109">Dois tipos de elementos de custo previsto</span><span class="sxs-lookup"><span data-stu-id="9a0ff-109">Two types of cost elements</span></span>
<span data-ttu-id="9a0ff-110">Há dois tipos de elementos de custo previsto: elementos de custo previsto e principais elementos de custo previsto secundárias.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-110">There are two types of cost elements: primary cost elements and secondary cost elements.</span></span> <span data-ttu-id="9a0ff-111">A tabela a seguir descreve a diferença entre os dois tipos.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-111">The following table describes the difference between the two types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9a0ff-112"><strong>Elementos de custo primário</strong></span><span class="sxs-lookup"><span data-stu-id="9a0ff-112"><strong>Primary cost elements</strong></span></span></td>
<td><span data-ttu-id="9a0ff-113"><strong>Elementos de custo secundários</strong></span><span class="sxs-lookup"><span data-stu-id="9a0ff-113"><strong>Secondary cost elements</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9a0ff-114">Elementos de custo previsto primários representam o fluxo de custo de conta financeira a contabilização de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-114">The primary cost elements represent the flow of costs from financial accounting to cost accounting.</span></span> <span data-ttu-id="9a0ff-115">A estrutura de elemento de custo previsto corresponde à estrutura da conta de lucros e perdas na contabilidade, no qual um elemento de custo previsto pode corresponder a uma conta principal.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-115">The cost element structure corresponds to the profit and loss account structure in the general ledger, where a cost element can correspond to a main account.</span></span> <span data-ttu-id="9a0ff-116">Nem todas as contas podem ser principais necessariamente representadas como os elementos de custo previsto dependendo das necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-116">Not all main accounts may necessarily be represented as cost elements depending on the business needs.</span></span> <span data-ttu-id="9a0ff-117">Exemplos de elementos de custo previsto primários incluem:</span><span class="sxs-lookup"><span data-stu-id="9a0ff-117">Examples of primary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="9a0ff-118">Custos dos produtos vendidos (COGs)</span><span class="sxs-lookup"><span data-stu-id="9a0ff-118">Costs of goods sold (COGs)</span></span></li>
<li><span data-ttu-id="9a0ff-119">Custos indiretos de material</span><span class="sxs-lookup"><span data-stu-id="9a0ff-119">Indirect material costs</span></span></li>
<li><span data-ttu-id="9a0ff-120">Custo da equipe</span><span class="sxs-lookup"><span data-stu-id="9a0ff-120">Personnel costs</span></span></li>
<li><span data-ttu-id="9a0ff-121">Custos de energia</span><span class="sxs-lookup"><span data-stu-id="9a0ff-121">Energy costs</span></span></li>
</ul></td>
<td><span data-ttu-id="9a0ff-122">Elementos de custo previsto secundários representam o fluxo de custo interna pois esses custos são criados e usados somente na contabilização de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-122">The secondary cost elements represent the flow of costs internally because these costs are created and used only in Cost accounting.</span></span> <span data-ttu-id="9a0ff-123">Seguro são usados para a fonte de custo pode ser rastreado.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-123">They are used to secure that the source of costs can be traced.</span></span> <span data-ttu-id="9a0ff-124">Esses elementos de custo são usados em alocações de custo e cálculos de despesas gerais.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-124">These cost elements are used in cost allocations and overhead calculations.</span></span> <span data-ttu-id="9a0ff-125">Exemplos de elementos de custo previsto secundários incluem:</span><span class="sxs-lookup"><span data-stu-id="9a0ff-125">Examples of secondary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="9a0ff-126">Custos da produção</span><span class="sxs-lookup"><span data-stu-id="9a0ff-126">Production costs</span></span></li>
<li><span data-ttu-id="9a0ff-127">Produção, material, e sobrecargas de marketing</span><span class="sxs-lookup"><span data-stu-id="9a0ff-127">Production, material, and marketing overheads</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a><span data-ttu-id="9a0ff-128">Dimensões de elemento de custo previsto e membros da dimensão do elemento de custo previsto</span><span class="sxs-lookup"><span data-stu-id="9a0ff-128">Cost element dimensions and cost element dimension members</span></span>
<span data-ttu-id="9a0ff-129">Elementos de custo previsto são referidos como *dimensões de elemento de custo previsto*.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-129">Cost elements are referred to as *cost element dimensions* .</span></span> <span data-ttu-id="9a0ff-130">Os valores de dimensão específicos são chamados de *membros da dimensão do elemento de custo previsto*.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-130">The individual dimension values are called *cost element dimension members*.</span></span> <span data-ttu-id="9a0ff-131">Por exemplo, você tem um gráfico. de E contracheques. estrutura de contas (COA) que é a base para seu relatório legal.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-131">For example, you have a US chart of accounts structure (COA) that is the base for your statutory reporting.</span></span> <span data-ttu-id="9a0ff-132">Este COA é usado como a dimensão do elemento de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-132">This COA is used as the cost element dimension.</span></span> <span data-ttu-id="9a0ff-133">Contas, as quais são elementos de custos principais, previsto são representadas como membros da dimensão do elemento de custo estimado na contabilização de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-133">The accounts, which are primary cost elements, are represented as the cost element dimension members in Cost accounting.</span></span> <span data-ttu-id="9a0ff-134">A captura de tela a seguir mostra um exemplo de como contas a dimensão do elemento de custo previsto com as listas principais real como membros da dimensão do elemento de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-134">The following screenshot shows an example of Main Accounts as the cost element dimension with its actual main accounts as the cost element dimension members.</span></span> 

<span data-ttu-id="9a0ff-135">[![Captura de tela de Contas Principais como dimensão do elemento de custo](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="9a0ff-135">[![Screenshot of Main Accounts as cost element dimension](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span></span>

## <a name="import-cost-element-dimension-members-through-data-connectors"></a><span data-ttu-id="9a0ff-136">Membros de custo previsto de dimensão de elemento de importação em dos conectores de dados</span><span class="sxs-lookup"><span data-stu-id="9a0ff-136">Import cost element dimension members through data connectors</span></span>
<span data-ttu-id="9a0ff-137">Para facilitar o de instalação de membros da dimensão do elemento de custo estimado na contabilização de custo previsto, você pode usar os conectores de dados que são ou criados anteriormente a compilação personalizado para recuperar os elementos de custo previsto principais de um ou vários sistemas de origem.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-137">To ease the setup of cost element dimension members in Cost accounting, you can use data connectors that are either pre-built or your custom build to retrieve the primary cost elements from one or more source systems.</span></span>

## <a name="implementation-considerations"></a><span data-ttu-id="9a0ff-138">Considerações de implementação</span><span class="sxs-lookup"><span data-stu-id="9a0ff-138">Implementation considerations</span></span>
<span data-ttu-id="9a0ff-139">Porque os elementos de custo previsto representam o nível mais baixo de detalhes de e realizado, você deve garantir que todos os elementos de custo previsto necessário para que o relatório de administração são incluídos quando ao implementar estrutura de elementos de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-139">As cost elements represent the lowest level of cost details, you should make sure that all the cost elements required to make the managerial reporting are included when you implement the cost elements structure.</span></span> <span data-ttu-id="9a0ff-140">Pode ser um desafio para localizar um número adequado de elementos de custo estimado para o controle de custo.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-140">It can be a challenge to find an appropriate number of cost elements for cost control.</span></span> <span data-ttu-id="9a0ff-141">Milhares de usar elementos de custo previsto pode fazê-lo difícil controlar cada elemento de custo previsto.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-141">Having thousands of cost elements can make it difficult to control each cost element.</span></span> <span data-ttu-id="9a0ff-142">Como alternativa, você pode agrupar os elementos de custo previsto e gerenciar o controle de custo em um nível agregado.</span><span class="sxs-lookup"><span data-stu-id="9a0ff-142">As an alternative, you can group cost elements and manage cost control at an aggregated level.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]