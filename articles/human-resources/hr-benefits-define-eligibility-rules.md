---
title: Definir regras e políticas de qualificação para o benefício
description: O artigo mostra como é possível criar regras e políticas de qualificação para o benefício e atribuir regras a benefícios.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 046b045fbdda125c5a2259783c0347f687453528
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053144"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="195a1-103">Definir regras e políticas de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="195a1-103">Define benefit eligibility rules and policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="195a1-104">O tópico mostra como é possível criar regras e políticas de qualificação para o benefício e atribuir regras a benefícios.</span><span class="sxs-lookup"><span data-stu-id="195a1-104">This topic shows you how you can create benefit eligibility rules and policies and then assign rules to benefits.</span></span>  

## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="195a1-105">Crie tipos de regras de política de qualificação para benefícios</span><span class="sxs-lookup"><span data-stu-id="195a1-105">Create benefit eligibility policy rule type</span></span>

1. <span data-ttu-id="195a1-106">Vá para **Recursos humanos > Benefícios > Qualificação > Tipos de regras de política de qualificação para o benefício**.</span><span class="sxs-lookup"><span data-stu-id="195a1-106">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policy rule types**.</span></span>
2. <span data-ttu-id="195a1-107">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="195a1-107">Select **New**.</span></span>
3. <span data-ttu-id="195a1-108">No campo **Nome da regra**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="195a1-108">In the **Rule name** field, enter a value.</span></span>
4. <span data-ttu-id="195a1-109">No campo **Descrição**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="195a1-109">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="195a1-110">No campo **Nome da consulta**, selecione o botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="195a1-110">In the **Query name** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="195a1-111">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="195a1-111">In the list, select the link in the selected row.</span></span>
7. <span data-ttu-id="195a1-112">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="195a1-112">Select **Save**.</span></span>
8. <span data-ttu-id="195a1-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="195a1-113">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="195a1-114">Política de qualificação para o benefício</span><span class="sxs-lookup"><span data-stu-id="195a1-114">Benefit eligibility policy</span></span>

1. <span data-ttu-id="195a1-115">Vá para **Recursos humanos > Benefícios > Qualificação > Políticas de qualificação para o benefício**.</span><span class="sxs-lookup"><span data-stu-id="195a1-115">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policies**.</span></span>
2. <span data-ttu-id="195a1-116">Selecione uma diretiva existente de benefício.</span><span class="sxs-lookup"><span data-stu-id="195a1-116">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="195a1-117">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="195a1-117">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="195a1-118">Alterne a expansão das seções de **Organizações de política**.</span><span class="sxs-lookup"><span data-stu-id="195a1-118">Toggle the expansion of the **Policy organizations** sections.</span></span> <span data-ttu-id="195a1-119">Você poderá adicionar ou remover as organizações que desejar incluir na política.</span><span class="sxs-lookup"><span data-stu-id="195a1-119">You can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="195a1-120">Expanda ou recolha a seção de **Regras de política**.</span><span class="sxs-lookup"><span data-stu-id="195a1-120">Expand or collapse the **Policy rules** section.</span></span>
6. <span data-ttu-id="195a1-121">Na lista, localize a regra de política criada previamente.</span><span class="sxs-lookup"><span data-stu-id="195a1-121">In the list, find the policy rule previously created.</span></span>
7. <span data-ttu-id="195a1-122">Selecione **Criar regra de política**.</span><span class="sxs-lookup"><span data-stu-id="195a1-122">Select **Create policy rule**.</span></span>
8. <span data-ttu-id="195a1-123">No campo **Data efetiva**, insira a data na qual deseja que a política entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="195a1-123">In the **Effective date** field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="195a1-124">Definir datas finais efetivas permite que você faça alterações futuras em regras de política para que não precise voltar à política quando desejar que essas alterações sejam aplicadas.</span><span class="sxs-lookup"><span data-stu-id="195a1-124">Setting effective end dates allows you to make future changes to policy rules so you don't need to come back to the policy when you want those changes to take effect.</span></span>  
9. <span data-ttu-id="195a1-125">Se necessário, adicione uma cláusula where ao campo **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="195a1-125">If needed, add a where clause to the **Add condition** field.</span></span>
    * <span data-ttu-id="195a1-126">Por exemplo, para que a regra se aplicasse somente aos Gerentes de vendas, você poderia criar a cláusula where para indicar: a descrição da posição de where equivale ao Gerente de vendas.</span><span class="sxs-lookup"><span data-stu-id="195a1-126">For example if you wanted the rule to only apply to Sales Managers you could create the where clause to say: Where position description equals Sales Manager.</span></span> <span data-ttu-id="195a1-127">Você pode adicionar várias instruções where juntas na regra.</span><span class="sxs-lookup"><span data-stu-id="195a1-127">You can add multiple where statements together in the rule.</span></span>  
10. <span data-ttu-id="195a1-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="195a1-128">Select **OK**.</span></span>
11. <span data-ttu-id="195a1-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="195a1-129">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="195a1-130">Atribuir regra ao benefício</span><span class="sxs-lookup"><span data-stu-id="195a1-130">Assign rule to benefit</span></span>

1. <span data-ttu-id="195a1-131">Acesse **Recursos humanos > Benefícios > Benefícios**.</span><span class="sxs-lookup"><span data-stu-id="195a1-131">Go to **Human resources > Benefits > Benefits**.</span></span>
2. <span data-ttu-id="195a1-132">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="195a1-132">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="195a1-133">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="195a1-133">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="195a1-134">Expanda ou recolha a seção **Regras de qualificação**.</span><span class="sxs-lookup"><span data-stu-id="195a1-134">Expand or collapse the **Eligibility rules** section.</span></span>
5. <span data-ttu-id="195a1-135">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="195a1-135">Select **Edit**.</span></span>
6. <span data-ttu-id="195a1-136">No campo **Qualificação**, selecione a regra.</span><span class="sxs-lookup"><span data-stu-id="195a1-136">In the **Eligibility** field, select the rule.</span></span>
7. <span data-ttu-id="195a1-137">No campo **Tipo de regra**, selecione a regra que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="195a1-137">In the **Rule type** field, select the rule you previously created.</span></span>
9. <span data-ttu-id="195a1-138">Na lista, selecione o link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="195a1-138">In the list, select the link in the selected row.</span></span>
10. <span data-ttu-id="195a1-139">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="195a1-139">Select **Save**.</span></span>
11. <span data-ttu-id="195a1-140">Feche o formulário.</span><span class="sxs-lookup"><span data-stu-id="195a1-140">Close the form.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]