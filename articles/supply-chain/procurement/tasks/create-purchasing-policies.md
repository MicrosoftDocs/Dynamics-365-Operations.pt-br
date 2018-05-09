--- 
title: "Criar políticas de compras"
description: "Este procedimento mostra-lhe como criar políticas de compra para alinhar com seus processos de negócios de compra."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: dd5a62dc1459f1768104eeaea3e71780431e8e79
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-purchasing-policies"></a><span data-ttu-id="ba2b8-103">Criar políticas de compras</span><span class="sxs-lookup"><span data-stu-id="ba2b8-103">Create purchasing policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ba2b8-104">Este procedimento mostra-lhe como criar políticas de compra para alinhar com seus processos de negócios de compra.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-104">This procedure shows you how to create purchasing policies to align with your business processes for purchasing.</span></span> <span data-ttu-id="ba2b8-105">Para que você possa criar políticas de compras, você deve configurar os parâmetros da política de compras.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-105">Before you can create purchasing policies, you must set up the purchasing policy parameters.</span></span> <span data-ttu-id="ba2b8-106">É possível criar, alterar e aposentar uma política de compra, mas você não pode suprimir uma política de compra.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-106">It’s possible to create, modify, and retire a purchasing policy, but you can’t delete a purchasing policy.</span></span> <span data-ttu-id="ba2b8-107">Normalmente essa procedimento é realizado por um Gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-107">This procedure would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="ba2b8-108">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-108">You can use this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-policy-parameters"></a><span data-ttu-id="ba2b8-109">Configurar parâmetros de política</span><span class="sxs-lookup"><span data-stu-id="ba2b8-109">Set up policy parameters</span></span>
1. <span data-ttu-id="ba2b8-110">Vá para Políticas de compra.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-110">Go to Purchasing policies.</span></span>
2. <span data-ttu-id="ba2b8-111">Clique em Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-111">Click Parameters.</span></span>
    * <span data-ttu-id="ba2b8-112">As regras de precedência da política aplicam-se aos níveis diferentes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-112">Policy precedence rules apply to different levels in your organization.</span></span> <span data-ttu-id="ba2b8-113">As unidades de organização em que são mostrados dependem de sua hierarquia de organização, e em que níveis na hierarquia foram atribuídos a finalidade do controle interno da obtenção.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-113">The organizational units that are shown depend on your organizational hierarchy, and on which levels in the hierarchy have been assigned the purpose of Procurement internal control.</span></span> <span data-ttu-id="ba2b8-114">Por exemplo, sua organização pode ter entidades legais, centros de custo, regiões e departamentos, mas pode ser que somente alguma destes tenha uma finalidade da hierarquia do controle interno da obtenção.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-114">For example, your organization might have legal entities, cost centers, regions, and departments, but it may be that only some of these have a hierarchy purpose of Procurement internal control.</span></span> <span data-ttu-id="ba2b8-115">Como padrão, a organização do tipo empresa está disponível.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-115">As a default, the organization of type Company is available.</span></span>  
3. <span data-ttu-id="ba2b8-116">Clique na guia Parâmetros do tipo de regra de política.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-116">Click the Policy rule type parameters tab.</span></span>
4. <span data-ttu-id="ba2b8-117">Na árvore, selecione "política de compras/regra de controle de requisição de compra".</span><span class="sxs-lookup"><span data-stu-id="ba2b8-117">In the tree, select 'Purchasing policy\Purchase requisition control rule'.</span></span>
    * <span data-ttu-id="ba2b8-118">Você define a ordem de precedência da resolução da política no nível da política.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-118">You define the order of precedence for policy resolution at the policy level.</span></span> <span data-ttu-id="ba2b8-119">No entanto, para alguns tipos de política, você pode substituir a ordem de precedência para tipos de regras de política individuais.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-119">However, for some policy types, you can override the order of precedence for individual policy rule types.</span></span> <span data-ttu-id="ba2b8-120">Por exemplo, você definiu precedência de políticas de compras nesta ordem: centro de custo, departamento, empresa.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-120">For example, you might define the order of precedence for purchasing policies to be: cost center, department, company.</span></span> <span data-ttu-id="ba2b8-121">Para a regra de política de catálogo, você deseja que a ordem de precedência esteja nesta ordem: departamento, centro de custo, empresa.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-121">For the catalog policy rule, you might want the order of precedence to be: department, cost center, company.</span></span> <span data-ttu-id="ba2b8-122">Você pode alterar a ordem de precedência para a regra de política de catálogo.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-122">You can change the order of precedence for the Catalog policy rule.</span></span> <span data-ttu-id="ba2b8-123">Quando um trabalhador cria uma requisição, o catálogo que é indicado está determinado pelas políticas que são associadas com o departamento do trabalhador, então seu centro de custo, e então sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-123">When a worker creates a requisition, the catalog that is displayed is determined by the policies that are associated with the worker’s department, then their cost center, and then their company.</span></span>  
    * <span data-ttu-id="ba2b8-124">Se há mais de um nível de organização alistado, você pode usar as setas para cima/baixo para ajustar a ordem de precedência para a regra do controle da requisição da compra.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-124">If there’s more than one organizational level listed, you can use the Up/Down arrows to set the order of precedence for the Purchase requisition control rule.</span></span>  
5. <span data-ttu-id="ba2b8-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-125">Close the page.</span></span>

## <a name="create-a-new-policy"></a><span data-ttu-id="ba2b8-126">Criar uma nova política</span><span class="sxs-lookup"><span data-stu-id="ba2b8-126">Create a new policy</span></span>
1. <span data-ttu-id="ba2b8-127">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-127">Click New.</span></span>
2. <span data-ttu-id="ba2b8-128">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-128">In the Name field, type a value.</span></span>
3. <span data-ttu-id="ba2b8-129">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-129">In the Description field, type a value.</span></span>
    * <span data-ttu-id="ba2b8-130">Uma política de compras individual pode ser aplicada apenas a uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-130">A single purchasing policy can only apply to one organization hierarchy.</span></span> <span data-ttu-id="ba2b8-131">Por exemplo, você poderia ter uma hierarquia chamada “geográfica” e uma chamada “departamento”, e uma política de compras diferente para cada uma.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-131">For example, you could have one hierarchy called “Geographic” and one called “Department”, and have a different purchasing policy for each.</span></span>  
    * <span data-ttu-id="ba2b8-132">Selecione uma organização a que a política deva se aplicar.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-132">Select an organization that the policy should apply to.</span></span>  
4. <span data-ttu-id="ba2b8-133">Clique na seta para adicionar a organização selecionada.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-133">Click the arrow to add the selected organization.</span></span>
    * <span data-ttu-id="ba2b8-134">Você pode repetir este processo para adicionar mais organizações.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-134">You can repeat this process to add more organizations.</span></span>  

## <a name="add-a-policy-rule"></a><span data-ttu-id="ba2b8-135">Adicionar uma regra de política</span><span class="sxs-lookup"><span data-stu-id="ba2b8-135">Add a policy rule</span></span>
1. <span data-ttu-id="ba2b8-136">Na lista Tipo de regra de política, selecione Regra de objetivo de requisição.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-136">In the Policy rule type list, select Requisition purpose rule.</span></span>
    * <span data-ttu-id="ba2b8-137">Você criará uma regra que ajuste a finalidade da requisição padrão para inserir Consumo, mas permite que o tipo do reabastecimento seja selecionado em vez disso.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-137">You’ll create a rule that sets the default requisition purpose to type Consumption but allows the Replenishment type to be selected instead.</span></span>  
2. <span data-ttu-id="ba2b8-138">Clique em Criar regra de política.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-138">Click Create policy rule.</span></span>
3. <span data-ttu-id="ba2b8-139">Selecione Sim no campo Permitir substituição manual.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-139">Select Yes in the Allow manual override field.</span></span>
4. <span data-ttu-id="ba2b8-140">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-140">Click Close.</span></span>
    * <span data-ttu-id="ba2b8-141">Agora você pode estabelecer outras regras da política para a política de compras.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-141">Now you can set up other policy rules for the purchasing policy.</span></span>   <span data-ttu-id="ba2b8-142">Note que um tipo da regra da política não pode ter as regras de sobreposição que são ativas ao mesmo tempo dentro de uma única política de obtenção.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-142">Note that a Policy rule type cannot have overlapping rules that are active at the same time within a single procurement policy.</span></span>  
5. <span data-ttu-id="ba2b8-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-143">Close the page.</span></span>
6. <span data-ttu-id="ba2b8-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ba2b8-144">Close the page.</span></span>


