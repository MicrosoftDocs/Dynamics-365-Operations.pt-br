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
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a7b9d0c20a49996b4c8d45b030d9e587818de3d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216536"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="e4c99-103">Criar e atribuir estruturas de regras avançadas</span><span class="sxs-lookup"><span data-stu-id="e4c99-103">Create and assign advanced rule structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e4c99-104">Este tópico explica como criar e atribuir uma estrutura de regras avançada a uma estrutura de conta.</span><span class="sxs-lookup"><span data-stu-id="e4c99-104">This topic explains how to create and assign an advanced rule structure to an account structure.</span></span> <span data-ttu-id="e4c99-105">Este guia usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="e4c99-105">This guide uses the USMF demo company.</span></span>

## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="e4c99-106">Criar estrutura de regras avançada</span><span class="sxs-lookup"><span data-stu-id="e4c99-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="e4c99-107">Vá para **Painel de navegação > Módulos > Contabilidade > Plano de contas > Estruturas > Estruturas de regras avançadas**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span></span>
2. <span data-ttu-id="e4c99-108">Selecione **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e4c99-108">Select **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="e4c99-109">No campo **Estrutura de regras avançada**, digite um nome para descrever a estrutura de regras.</span><span class="sxs-lookup"><span data-stu-id="e4c99-109">In the **Advanced rule structure** field, type a name to describe the rule structure.</span></span>
4. <span data-ttu-id="e4c99-110">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-110">Select **OK**.</span></span>
5. <span data-ttu-id="e4c99-111">Selecione **Adicionar segmento**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-111">Select **Add segment**.</span></span>
6. <span data-ttu-id="e4c99-112">Na lista de segmentos, selecione uma dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="e4c99-112">In the list of segments, select a financial dimension.</span></span> <span data-ttu-id="e4c99-113">Por exemplo, **Loja**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-113">For example, **Store**.</span></span>  
7. <span data-ttu-id="e4c99-114">Selecione **Adicionar segmento**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-114">Select **Add segment**.</span></span>
8. <span data-ttu-id="e4c99-115">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-115">Select **Activate**.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="e4c99-116">Aplicar estrutura de regra avançada a uma estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="e4c99-116">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="e4c99-117">Vá para **Painel de navegação > Módulos > Contabilidade > Plano de contas > Estruturas > Configurar estruturas de conta**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-117">Go to **navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="e4c99-118">Na lista, localize e selecione a estrutura de conta à qual deseja aplicar a regra avançada.</span><span class="sxs-lookup"><span data-stu-id="e4c99-118">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
3. <span data-ttu-id="e4c99-119">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-119">Select **Edit**.</span></span> <span data-ttu-id="e4c99-120">Você também pode selecionar **Regras avançadas** e será solicitado a colocar a estrutura de conta no **Modo de rascunho**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-120">You can also select **Advanced rules** and you will be prompted to put the account structure in **Draft mode**.</span></span>  
4. <span data-ttu-id="e4c99-121">Selecione **Regras avançadas**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-121">Select **Advanced rules**.</span></span>
5. <span data-ttu-id="e4c99-122">Selecione **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e4c99-122">Select **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="e4c99-123">No campo **Regra avançada**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e4c99-123">In the **Advanced rule** field, type a value.</span></span>
7. <span data-ttu-id="e4c99-124">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e4c99-124">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="e4c99-125">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-125">Select **Create**.</span></span>
9. <span data-ttu-id="e4c99-126">Selecione **Adicionar novos critérios**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-126">Select **Add new criteria**.</span></span>
10. <span data-ttu-id="e4c99-127">No campo **Onde**, selecione uma conta principal ou uma dimensão financeira.</span><span class="sxs-lookup"><span data-stu-id="e4c99-127">In the **Where** field, select main account or a financial dimension.</span></span>
11. <span data-ttu-id="e4c99-128">No campo **Operador**, selecione uma opção, como **está entre** e **inclui**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-128">In the **Operator** field, select an option, such as **is between** and **includes**.</span></span>
12. <span data-ttu-id="e4c99-129">No campo **Valor**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e4c99-129">In the **Value** field, type a value.</span></span>
13. <span data-ttu-id="e4c99-130">No campo **por meio de**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e4c99-130">In the **through** field, type a value.</span></span>
14. <span data-ttu-id="e4c99-131">Selecione **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e4c99-131">Select **Add** to open the drop dialog.</span></span>
15. <span data-ttu-id="e4c99-132">Na lista, localize a estrutura de regra avançada que deseja usar quando os critérios inseridos forem atendidos.</span><span class="sxs-lookup"><span data-stu-id="e4c99-132">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
16. <span data-ttu-id="e4c99-133">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-133">Select **Add**.</span></span>
17. <span data-ttu-id="e4c99-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e4c99-134">Close the page.</span></span>
18. <span data-ttu-id="e4c99-135">Selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="e4c99-135">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]