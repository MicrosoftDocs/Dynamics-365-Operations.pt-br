---
title: "Políticas de qualificação para benefícios"
description: "Este artigo fornece informações sobre as diretivas de qualificação de benefício, o que ajuda a definir quem está qualificado para benefícios específicos."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 682100881d6ea8c1e02db50629208c765600c49a
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="benefit-eligibility-policies"></a><span data-ttu-id="32a74-103">Políticas de qualificação para benefícios</span><span class="sxs-lookup"><span data-stu-id="32a74-103">Benefit eligibility policies</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="32a74-104">Este tópico fornece informações sobre as diretivas de qualificação de benefício, o que ajuda a definir quem está qualificado para benefícios específicos.</span><span class="sxs-lookup"><span data-stu-id="32a74-104">This topic provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="32a74-105">Quando você cria benefícios, você decide qual deles estarão disponíveis para quais funcionários.</span><span class="sxs-lookup"><span data-stu-id="32a74-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="32a74-106">A tabela a seguir mostra exemplos de benefícios que você pode disponibilizar para funcionários específicos.</span><span class="sxs-lookup"><span data-stu-id="32a74-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="32a74-107">Benefício</span><span class="sxs-lookup"><span data-stu-id="32a74-107">Benefit</span></span>          | <span data-ttu-id="32a74-108">Para quem o benefício está disponível</span><span class="sxs-lookup"><span data-stu-id="32a74-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="32a74-109">Seguro de saúde</span><span class="sxs-lookup"><span data-stu-id="32a74-109">Health insurance</span></span> | <span data-ttu-id="32a74-110">Todos os funcionários</span><span class="sxs-lookup"><span data-stu-id="32a74-110">All employees</span></span>                   |
| <span data-ttu-id="32a74-111">Telefone celular</span><span class="sxs-lookup"><span data-stu-id="32a74-111">Mobile phone</span></span>     | <span data-ttu-id="32a74-112">Equipe de vendas, executivos</span><span class="sxs-lookup"><span data-stu-id="32a74-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="32a74-113">Estacionamento</span><span class="sxs-lookup"><span data-stu-id="32a74-113">Parking passes</span></span>   | <span data-ttu-id="32a74-114">Executivos</span><span class="sxs-lookup"><span data-stu-id="32a74-114">Executives</span></span>                      |

<span data-ttu-id="32a74-115">Os seguintes componentes são usados para criar políticas de qualificação:</span><span class="sxs-lookup"><span data-stu-id="32a74-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="32a74-116">Tipos de regra de política</span><span class="sxs-lookup"><span data-stu-id="32a74-116">Policy rule types</span></span>
-   <span data-ttu-id="32a74-117">Políticas de qualificação para benefícios</span><span class="sxs-lookup"><span data-stu-id="32a74-117">Benefit eligibility policies</span></span>

<span data-ttu-id="32a74-118">Os tipos de regras de política definem os parâmetros de consulta que são usados quando você desenvolve regras de política específicas.</span><span class="sxs-lookup"><span data-stu-id="32a74-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="32a74-119">Depois de criar tipos de regras de política, você pode criar políticas de qualificação de benefícios.</span><span class="sxs-lookup"><span data-stu-id="32a74-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="32a74-120">As políticas permitem criar uma coleção de regras que se aplicam a uma ou mais entidades legais.</span><span class="sxs-lookup"><span data-stu-id="32a74-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="32a74-121">Em cada política, é possível visualizar qualquer um dos tipos de regras de política de qualificação de benefícios criados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="32a74-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="32a74-122">Você define o escopo da regra na política.</span><span class="sxs-lookup"><span data-stu-id="32a74-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="32a74-123">Por exemplo, se você criar um tipo de regras de política de qualificação de benefícios que foi nomeada como **Executivo**, você pode qual regra é essa nessa política.</span><span class="sxs-lookup"><span data-stu-id="32a74-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="32a74-124">Neste exemplo, a regra pode indicar que o título do trabalho que contenha a palavra “executivo” deve ser incluída na regra.</span><span class="sxs-lookup"><span data-stu-id="32a74-124">In this example, the rule might state that any job title that contains the word “executive” should be included in the rule.</span></span> <span data-ttu-id="32a74-125">Após definir os parâmetros da regra ou das regras que são incluídas na política, você pode atribuir uma regra específica ao benefício.</span><span class="sxs-lookup"><span data-stu-id="32a74-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>

<a name="see-also"></a><span data-ttu-id="32a74-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="32a74-126">See also</span></span>
--------

[<span data-ttu-id="32a74-127">Definir e gerenciar um programa de benefício</span><span class="sxs-lookup"><span data-stu-id="32a74-127">Defining and managing a benefit program</span></span>](manage-benefit-program.md)




