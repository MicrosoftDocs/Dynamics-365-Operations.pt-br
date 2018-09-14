--- 
title: "Definir regras e políticas de qualificação para o benefício"
description: "O registro mostrará como é possível criar regras de qualificação e as diretivas de benefício e regras para atribuir benefícios."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: d346c3277e8f19020d6aa96cf6961c4c52ac28fb
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="97170-103">Definir regras e políticas de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="97170-103">Define benefit eligibility rules and policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="97170-104">O registro mostrará como é possível criar regras de qualificação e as diretivas de benefício e regras para atribuir benefícios.</span><span class="sxs-lookup"><span data-stu-id="97170-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="97170-105">A empresa de dados demo usada para criar este registro é USMF.</span><span class="sxs-lookup"><span data-stu-id="97170-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="97170-106">Crie tipos de regras de política de qualificação para benefícios</span><span class="sxs-lookup"><span data-stu-id="97170-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="97170-107">Vá para Recursos humanos > Benefícios > Qualificação > Tipos de regras de política de qualificação para o benefício.</span><span class="sxs-lookup"><span data-stu-id="97170-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="97170-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="97170-108">Click New.</span></span>
3. <span data-ttu-id="97170-109">No campo Nome da regra, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="97170-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="97170-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="97170-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="97170-111">No campo Nome da consulta, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="97170-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="97170-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="97170-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="97170-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="97170-113">Click Save.</span></span>
8. <span data-ttu-id="97170-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="97170-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="97170-115">Política de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="97170-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="97170-116">Vá para Recursos humanos > Benefícios > Qualificação > Políticas de qualificação para o benefício.</span><span class="sxs-lookup"><span data-stu-id="97170-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="97170-117">Selecione uma diretiva existente de benefício.</span><span class="sxs-lookup"><span data-stu-id="97170-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="97170-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="97170-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="97170-119">Ative/desative a expansão das seções de Organizações de política.</span><span class="sxs-lookup"><span data-stu-id="97170-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="97170-120">Aqui você pode adicionar ou remover todas as organizações que você deseja incluir na diretiva.</span><span class="sxs-lookup"><span data-stu-id="97170-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="97170-121">Expanda ou recolha a seção de regras de diretivas.</span><span class="sxs-lookup"><span data-stu-id="97170-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="97170-122">Na lista, localize a regra de política criada previamente.</span><span class="sxs-lookup"><span data-stu-id="97170-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="97170-123">Clique em Criar regra de política.</span><span class="sxs-lookup"><span data-stu-id="97170-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="97170-124">No campo Data efetiva, insira a data na qual a diretiva entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="97170-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="97170-125">Definir datas efetivas e finais permite que você faça as alterações futuras às regras de diretiva e remove a necessidade de voltar à diretiva quando desejar que essas alterações sejam aplicadas.</span><span class="sxs-lookup"><span data-stu-id="97170-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="97170-126">Por exemplo se você quis que a regra se aplicasse somente aos Gerentes de vendas, você pode criar a Cláusula onde dizendo: Onde a descrição de posição é igual ao Gerente de vendas.</span><span class="sxs-lookup"><span data-stu-id="97170-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="97170-127">Você pode E ou Ou multiplicar Onde declarações juntas na regra.</span><span class="sxs-lookup"><span data-stu-id="97170-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="97170-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="97170-128">Click OK.</span></span>
11. <span data-ttu-id="97170-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="97170-129">Close the page.</span></span>
12. <span data-ttu-id="97170-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="97170-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="97170-131">Atribuir regra ao benefício</span><span class="sxs-lookup"><span data-stu-id="97170-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="97170-132">Ir para Recursos humanos > Benefícios > Benefícios.</span><span class="sxs-lookup"><span data-stu-id="97170-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="97170-133">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="97170-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="97170-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="97170-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="97170-135">Expanda ou recolha a seção de qualificação de diretivas.</span><span class="sxs-lookup"><span data-stu-id="97170-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="97170-136">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="97170-136">Click Edit.</span></span>
6. <span data-ttu-id="97170-137">No campo Qualificação, selecione a Regra baseada na lista.</span><span class="sxs-lookup"><span data-stu-id="97170-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="97170-138">No campo Tipo de regra, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="97170-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="97170-139">Na lista, localize e selecione a regra que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="97170-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="97170-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="97170-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="97170-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="97170-141">Click Save.</span></span>
11. <span data-ttu-id="97170-142">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="97170-142">Close the form.</span></span>


