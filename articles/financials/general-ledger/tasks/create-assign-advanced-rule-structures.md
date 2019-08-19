---
title: Criar e atribuir estruturas de regras avançadas
description: Este tópico explica como criar e atribuir uma estrutura de regras avançada a uma estrutura de conta.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cff07c13553ea140f537160da7f93820d5e3f77a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834873"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="cc77d-103">Criar e atribuir estruturas de regras avançadas</span><span class="sxs-lookup"><span data-stu-id="cc77d-103">Create and assign advanced rule structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc77d-104">Este tópico explica como criar e atribuir uma estrutura de regras avançada a uma estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="cc77d-104">This topic explains how to create and assign an advanced rule structure to an account structure.</span></span> <span data-ttu-id="cc77d-105">Este guia usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="cc77d-105">This guide uses the USMF demo company.</span></span>

## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="cc77d-106">Criar estrutura de regras avançada</span><span class="sxs-lookup"><span data-stu-id="cc77d-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="cc77d-107">Vá para **Painel de navegação > Módulos > Contabilidade > Plano de contas > Estruturas > Estruturas de regras avançadas**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span></span>
2. <span data-ttu-id="cc77d-108">Selecione **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="cc77d-108">Select **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="cc77d-109">No campo **Estrutura de regras avançada**, digite um nome para descrever a estrutura de regras.</span><span class="sxs-lookup"><span data-stu-id="cc77d-109">In the **Advanced rule structure** field, type a name to describe the rule structure.</span></span>
4. <span data-ttu-id="cc77d-110">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-110">Select **OK**.</span></span>
5. <span data-ttu-id="cc77d-111">Selecione **Adicionar segmento**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-111">Select **Add segment**.</span></span>
6. <span data-ttu-id="cc77d-112">Na lista de segmentos, selecione uma dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="cc77d-112">In the list of segments, select a financial dimension.</span></span> <span data-ttu-id="cc77d-113">Por exemplo, **Loja**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-113">For example, **Store**.</span></span>  
7. <span data-ttu-id="cc77d-114">Selecione **Adicionar segmento**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-114">Select **Add segment**.</span></span>
8. <span data-ttu-id="cc77d-115">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-115">Select **Activate**.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="cc77d-116">Aplicar estrutura de regra avançada a uma estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="cc77d-116">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="cc77d-117">Vá para **Painel de navegação > Módulos > Contabilidade > Plano de contas > Estruturas > Configurar estruturas de conta**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-117">Go to **navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="cc77d-118">Na lista, localize e selecione a estrutura de conta à qual deseja aplicar a regra avançada.</span><span class="sxs-lookup"><span data-stu-id="cc77d-118">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
3. <span data-ttu-id="cc77d-119">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-119">Select **Edit**.</span></span> <span data-ttu-id="cc77d-120">Você também pode selecionar **Regras avançadas** e será solicitado a colocar a estrutura de conta no **Modo de rascunho**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-120">You can also select **Advanced rules** and you will be prompted to put the account structure in **Draft mode**.</span></span>  
4. <span data-ttu-id="cc77d-121">Selecione **Regras avançadas**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-121">Select **Advanced rules**.</span></span>
5. <span data-ttu-id="cc77d-122">Selecione **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="cc77d-122">Select **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="cc77d-123">No campo **Regra avançada**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cc77d-123">In the **Advanced rule** field, type a value.</span></span>
7. <span data-ttu-id="cc77d-124">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cc77d-124">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="cc77d-125">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-125">Select **Create**.</span></span>
9. <span data-ttu-id="cc77d-126">Selecione **Adicionar novos critérios**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-126">Select **Add new criteria**.</span></span>
10. <span data-ttu-id="cc77d-127">No campo **Onde**, selecione uma conta principal ou uma dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="cc77d-127">In the **Where** field, select main account or a financial dimension.</span></span>
11. <span data-ttu-id="cc77d-128">No campo **Operador**, selecione uma opção, como **está entre** e **inclui**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-128">In the **Operator** field, select an option, such as **is between** and **includes**.</span></span>
12. <span data-ttu-id="cc77d-129">No campo **Valor**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cc77d-129">In the **Value** field, type a value.</span></span>
13. <span data-ttu-id="cc77d-130">No campo **por meio de**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cc77d-130">In the **through** field, type a value.</span></span>
14. <span data-ttu-id="cc77d-131">Selecione **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="cc77d-131">Select **Add** to open the drop dialog.</span></span>
15. <span data-ttu-id="cc77d-132">Na lista, localize a estrutura de regra avançada que deseja usar quando os critérios inseridos forem atendidos.</span><span class="sxs-lookup"><span data-stu-id="cc77d-132">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
16. <span data-ttu-id="cc77d-133">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-133">Select **Add**.</span></span>
17. <span data-ttu-id="cc77d-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cc77d-134">Close the page.</span></span>
18. <span data-ttu-id="cc77d-135">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="cc77d-135">Select **Activate**.</span></span>

