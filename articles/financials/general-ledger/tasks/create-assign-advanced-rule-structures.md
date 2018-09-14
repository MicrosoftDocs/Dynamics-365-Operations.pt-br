--- 
title: "Criar e atribuir estruturas de regras avançadas"
description: "Este guia de tarefas aborda a criação e atribuição de uma estrutura de regra avançada a uma estrutura de conta."
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: dd62254c20cf5d77677d03c7d7335fb793d7f5f2
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="19b22-103">Criar e atribuir estruturas de regras avançadas</span><span class="sxs-lookup"><span data-stu-id="19b22-103">Create and assign advanced rule structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="19b22-104">Este guia de tarefas aborda a criação e atribuição de uma estrutura de regra avançada a uma estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="19b22-104">This task guide steps through creating and assigning an advanced rule structure to an account structure.</span></span> <span data-ttu-id="19b22-105">Este guia usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="19b22-105">This guide uses the USMF demo company.</span></span>


## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="19b22-106">Criar estrutura de regras avançada</span><span class="sxs-lookup"><span data-stu-id="19b22-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="19b22-107">Vá para Contabilidade > Plano de contas > Estruturas > Estruturas de regra avançada.</span><span class="sxs-lookup"><span data-stu-id="19b22-107">Go to General ledger > Chart of accounts > Structures > Advanced rule structures.</span></span>
2. <span data-ttu-id="19b22-108">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="19b22-108">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="19b22-109">No campo Estrutura de regra avançada, digite um nome para descrever a estrutura da regra.</span><span class="sxs-lookup"><span data-stu-id="19b22-109">In the Advanced rule structure field, type a name to descritbe the rule structure.</span></span>
4. <span data-ttu-id="19b22-110">No campo Descrição, digite um valor para descrever a estrutura.</span><span class="sxs-lookup"><span data-stu-id="19b22-110">In the Description field, type a value to describe the structure.</span></span>
5. <span data-ttu-id="19b22-111">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="19b22-111">Click OK.</span></span>
6. <span data-ttu-id="19b22-112">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="19b22-112">Click Add segment.</span></span>
7. <span data-ttu-id="19b22-113">Na lista de segmentos, selecione uma dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="19b22-113">In the list of segments, select a financial dimension.</span></span>
    * <span data-ttu-id="19b22-114">Por exemplo, Loja.</span><span class="sxs-lookup"><span data-stu-id="19b22-114">For example, Store.</span></span>  
8. <span data-ttu-id="19b22-115">Clique em Adicionar segmento.</span><span class="sxs-lookup"><span data-stu-id="19b22-115">Click Add segment.</span></span>
9. <span data-ttu-id="19b22-116">Na lista, clique no link da estrutura de regra avançada para exibi-la.</span><span class="sxs-lookup"><span data-stu-id="19b22-116">In the list, click the link of the advanced rule structure to view it.</span></span>
10. <span data-ttu-id="19b22-117">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="19b22-117">Click Activate.</span></span>
11. <span data-ttu-id="19b22-118">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="19b22-118">Click Activate.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="19b22-119">Aplicar estrutura de regra avançada a uma estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="19b22-119">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="19b22-120">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="19b22-120">Close the form.</span></span>
2. <span data-ttu-id="19b22-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="19b22-121">Close the page.</span></span>
3. <span data-ttu-id="19b22-122">Vá para Contabilidade > Plano de contas > Estruturas > Configurar estruturas de conta.</span><span class="sxs-lookup"><span data-stu-id="19b22-122">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
4. <span data-ttu-id="19b22-123">Na lista, localize e selecione a estrutura de conta à qual deseja aplicar a regra avançada.</span><span class="sxs-lookup"><span data-stu-id="19b22-123">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
5. <span data-ttu-id="19b22-124">Clique no nome da estrutura de conta para abri-la.</span><span class="sxs-lookup"><span data-stu-id="19b22-124">Click the name of the account structure to open it.</span></span>
6. <span data-ttu-id="19b22-125">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="19b22-125">Click Edit.</span></span>
    * <span data-ttu-id="19b22-126">Você também pode clicar em Regras avançadas, e será solicitado que você coloque a estrutura de conta no modo de rascunho.</span><span class="sxs-lookup"><span data-stu-id="19b22-126">You can also click Advanced rules and you will be prompted to put the account structure in Draft mode.</span></span>  
7. <span data-ttu-id="19b22-127">Clique em Regras avançadas.</span><span class="sxs-lookup"><span data-stu-id="19b22-127">Click Advanced rules.</span></span>
8. <span data-ttu-id="19b22-128">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="19b22-128">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="19b22-129">No campo Regra avançada, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="19b22-129">In the Advanced rule field, type a value.</span></span>
10. <span data-ttu-id="19b22-130">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="19b22-130">In the Name field, type a value.</span></span>
11. <span data-ttu-id="19b22-131">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="19b22-131">Click Create.</span></span>
12. <span data-ttu-id="19b22-132">Clique em Adicionar novos critérios.</span><span class="sxs-lookup"><span data-stu-id="19b22-132">Click Add new criteria.</span></span>
13. <span data-ttu-id="19b22-133">No campo Onde, selecione uma conta principal ou uma dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="19b22-133">In the Where field, select main account or a financial dimension.</span></span>
14. <span data-ttu-id="19b22-134">No campo Operador, selecione uma opção, como está entre e inclui.</span><span class="sxs-lookup"><span data-stu-id="19b22-134">In the Operator field, select an option, such as is between and includes.</span></span>
15. <span data-ttu-id="19b22-135">No campo Valor, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="19b22-135">In the Value field, type a value.</span></span>
16. <span data-ttu-id="19b22-136">No campo por meio de, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="19b22-136">In the through field, type a value.</span></span>
17. <span data-ttu-id="19b22-137">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="19b22-137">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="19b22-138">Na lista, localize a estrutura de regra avançada que deseja usar quando os critérios inseridos forem atendidos.</span><span class="sxs-lookup"><span data-stu-id="19b22-138">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
19. <span data-ttu-id="19b22-139">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="19b22-139">Click Add.</span></span>
20. <span data-ttu-id="19b22-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="19b22-140">Close the page.</span></span>
21. <span data-ttu-id="19b22-141">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="19b22-141">Click Activate.</span></span>
22. <span data-ttu-id="19b22-142">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="19b22-142">Click Activate.</span></span>


