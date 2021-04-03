---
title: Configurar opções de qualificação para contato pessoal
description: Configure opções de qualificação para contatos pessoais no Microsoft Dynamics 365 Human Resources. Contatos pessoais podem ser beneficiários ou dependentes.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f300ac917ac21db9fffbffcc6eb8589357c0a3e
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466197"
---
# <a name="configure-personal-contact-eligibility-options"></a><span data-ttu-id="7221e-104">Configurar opções de qualificação para contato pessoal</span><span class="sxs-lookup"><span data-stu-id="7221e-104">Configure personal contact eligibility options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7221e-105">Este artigo mostra como configurar tipos de contatos pessoais para usar em benefícios no Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7221e-105">This article shows you how to configure types of personal contacts to use in benefits in Microsoft Dynamics 365 Human Resources.</span></span> <span data-ttu-id="7221e-106">Contatos pessoais podem ser beneficiários ou dependentes.</span><span class="sxs-lookup"><span data-stu-id="7221e-106">Personal contacts can be beneficiaries or dependents.</span></span> 

1. <span data-ttu-id="7221e-107">No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Opções de qualificação para contato pessoal**.</span><span class="sxs-lookup"><span data-stu-id="7221e-107">In the **Benefits management** workspace, under **Setup**, select **Personal contact eligibility options**.</span></span>

2. <span data-ttu-id="7221e-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7221e-108">Select **New**.</span></span>

3. <span data-ttu-id="7221e-109">Especifique valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="7221e-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="7221e-110">Campo</span><span class="sxs-lookup"><span data-stu-id="7221e-110">Field</span></span> | <span data-ttu-id="7221e-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="7221e-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="7221e-112">**Opção de qualificação**</span><span class="sxs-lookup"><span data-stu-id="7221e-112">**Eligibility option**</span></span> | <span data-ttu-id="7221e-113">Um nome ou código exclusivo da opção de qualificação para identificar a opção de qualificação.</span><span class="sxs-lookup"><span data-stu-id="7221e-113">A unique eligibility option name or code to identify the eligibility option.</span></span> |
   | <span data-ttu-id="7221e-114">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7221e-114">**Description**</span></span> | <span data-ttu-id="7221e-115">Uma breve descrição da opção de qualificação.</span><span class="sxs-lookup"><span data-stu-id="7221e-115">A brief description of the eligibility option.</span></span> |
   | <span data-ttu-id="7221e-116">**Código de qualificação do contato**</span><span class="sxs-lookup"><span data-stu-id="7221e-116">**Contact eligibility code**</span></span> | <span data-ttu-id="7221e-117">O código do sistema que melhor descreve a opção de qualificação pessoal.</span><span class="sxs-lookup"><span data-stu-id="7221e-117">The system code that best describes the personal eligibility option.</span></span> <span data-ttu-id="7221e-118">As opções são:</span><span class="sxs-lookup"><span data-stu-id="7221e-118">You can choose from:</span></span> <ul><li><span data-ttu-id="7221e-119">Relacionamento</span><span class="sxs-lookup"><span data-stu-id="7221e-119">Relationship</span></span></li><li><span data-ttu-id="7221e-120">Estudante</span><span class="sxs-lookup"><span data-stu-id="7221e-120">Student</span></span></li><li><span data-ttu-id="7221e-121">Dependente excedente</span><span class="sxs-lookup"><span data-stu-id="7221e-121">Overage dependent</span></span></li><li><span data-ttu-id="7221e-122">Dependente incapaz maior de idade</span><span class="sxs-lookup"><span data-stu-id="7221e-122">Over-aged disabled dependent</span></span></li></ul> |
   | <span data-ttu-id="7221e-123">**Status**</span><span class="sxs-lookup"><span data-stu-id="7221e-123">**Status**</span></span> | <span data-ttu-id="7221e-124">O status da opção de qualificação.</span><span class="sxs-lookup"><span data-stu-id="7221e-124">The status of the eligibility option.</span></span> <span data-ttu-id="7221e-125">Se o status de uma opção de qualificação estiver definido como inativo, você não poderá selecionar essa opção de qualificação de contato pessoal para contatos pessoais.</span><span class="sxs-lookup"><span data-stu-id="7221e-125">If the status for an eligibility option is set to inactive, then you can’t select that personal contact eligibility option for personal contacts.</span></span> |
   | <span data-ttu-id="7221e-126">**Relacionamento**</span><span class="sxs-lookup"><span data-stu-id="7221e-126">**Relationship**</span></span> | <span data-ttu-id="7221e-127">Especifica o relacionamento entre o contato pessoal e o funcionário.</span><span class="sxs-lookup"><span data-stu-id="7221e-127">Specifies the relationship between the personal contact and the employee.</span></span> <span data-ttu-id="7221e-128">Esse campo estará ativo apenas se o código de qualificação do contato estiver definido como Relacionamento.</span><span class="sxs-lookup"><span data-stu-id="7221e-128">This field is only active if the contact eligibility code is set to Relationship.</span></span> |
   | <span data-ttu-id="7221e-129">**Classificar por vencimento**</span><span class="sxs-lookup"><span data-stu-id="7221e-129">**Age**</span></span> | <span data-ttu-id="7221e-130">A idade máxima de um contato pessoal qualificado para o plano de benefícios.</span><span class="sxs-lookup"><span data-stu-id="7221e-130">The maximum age of an eligible personal contact for the benefit plan.</span></span> <span data-ttu-id="7221e-131">Esse campo estará ativo apenas se você selecionar um relacionamento.</span><span class="sxs-lookup"><span data-stu-id="7221e-131">This field is only active if you select a relationship.</span></span> <span data-ttu-id="7221e-132">Essa idade é comparada com a idade calculada do contato pessoal.</span><span class="sxs-lookup"><span data-stu-id="7221e-132">This age is compared with the calculated age of the personal contact.</span></span> <span data-ttu-id="7221e-133">A idade calculada é: (data de cobertura – data de nascimento do contato pessoal/365).</span><span class="sxs-lookup"><span data-stu-id="7221e-133">Calculated age is: (Coverage date – personal contact birth date / 365).</span></span> <span data-ttu-id="7221e-134">Esse número é sempre um inteiro.</span><span class="sxs-lookup"><span data-stu-id="7221e-134">This number is always an integer.</span></span> |

4. <span data-ttu-id="7221e-135">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7221e-135">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]