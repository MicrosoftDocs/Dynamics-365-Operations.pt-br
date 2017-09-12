---
title: Planejar seu plano de contas
description: "Este artigo fornece informações as quais o ajudarão a planejar o gráfico para sua organização."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 848da7ec8f4a7915f3b78945b808b564f4510434
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="c6779-103">Planejar seu plano de contas</span><span class="sxs-lookup"><span data-stu-id="c6779-103">Plan your chart of accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c6779-104">Este artigo fornece informações as quais o ajudarão a planejar o gráfico para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c6779-104">This article provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="c6779-105">Para rastrear e manter as informações financeiras em uma organização, você pode configurar um plano de contas.</span><span class="sxs-lookup"><span data-stu-id="c6779-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="c6779-106">Um plano de contas é um conjunto de contas que definem uma estrutura financeira.</span><span class="sxs-lookup"><span data-stu-id="c6779-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="c6779-107">Para rastrear outras transações nessas contas, você pode adicionar segmentos, que são conhecidos como dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="c6779-107">To further track the transactions in these accounts, you can add segments, which are known as financial dimensions.</span></span> <span data-ttu-id="c6779-108">Por exemplo, uma conta de despesas pode incluir as dimensões financeiras denominadas Departamento, Centro de custos e Finalidade.</span><span class="sxs-lookup"><span data-stu-id="c6779-108">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="c6779-109">As regras definidas pelo usuário, conhecidas como estruturas de conta e regras avançadas, determinam como essas dimensões financeiras são anexadas às contas principais e outras dimensões financeiras, e também como as transações podem ser inseridas.</span><span class="sxs-lookup"><span data-stu-id="c6779-109">User-defined rules, which are known as account structures and advanced rules, determine how financial dimensions are attached to the main accounts and other financial dimensions, and also how transactions are entered.</span></span> 

<span data-ttu-id="c6779-110">O plano de contas é uma lista estruturada das contas da contabilidade de uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="c6779-110">The chart of accounts is a structured list of a legal entity’s general ledger accounts.</span></span> <span data-ttu-id="c6779-111">A lista é utilizada para preparar relatórios financeiros para autoridades e proprietários.</span><span class="sxs-lookup"><span data-stu-id="c6779-111">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="c6779-112">As contas são agrupadas em tipos de contas e então agregadas em categorias maiores.</span><span class="sxs-lookup"><span data-stu-id="c6779-112">The accounts are grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="c6779-113">No nível mais amplo, as contas são agrupadas como receitas e custos (contas operacionais), ativos e passivos (contas de saldo).</span><span class="sxs-lookup"><span data-stu-id="c6779-113">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span> 

<span data-ttu-id="c6779-114">Um plano de contas pode ser compartilhado e usado por todas as entidades legais em uma organização.</span><span class="sxs-lookup"><span data-stu-id="c6779-114">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="c6779-115">O plano de contas usado por uma entidade legal é definido na página **Razão**.</span><span class="sxs-lookup"><span data-stu-id="c6779-115">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span> 

<span data-ttu-id="c6779-116">Veja alguns dos fatores que você deve considerar ao planejar a estrutura do plano de contas para sua organização:</span><span class="sxs-lookup"><span data-stu-id="c6779-116">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

-   <span data-ttu-id="c6779-117">Os requisitos de relatório do país/região no qual sua organização está sediada</span><span class="sxs-lookup"><span data-stu-id="c6779-117">The reporting requirements of the country/region where your organization is based</span></span>
-   <span data-ttu-id="c6779-118">Os requisitos de relatórios da entidade legal</span><span class="sxs-lookup"><span data-stu-id="c6779-118">The reporting requirements of your legal entity</span></span>
-   <span data-ttu-id="c6779-119">O grau de especificação é necessário para as duas organizações externas e a sua organização</span><span class="sxs-lookup"><span data-stu-id="c6779-119">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="c6779-120">Crie o plano de contas na página **Plano de contas**.</span><span class="sxs-lookup"><span data-stu-id="c6779-120">Create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="c6779-121">As contas principais podem ser criadas na página **Plano de contas** ou na página **Contas principais**.</span><span class="sxs-lookup"><span data-stu-id="c6779-121">Main accounts can be created from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="c6779-122">Sus contas principais não devem usar caracteres especiais utilizados como delimitadores de plano de contas.</span><span class="sxs-lookup"><span data-stu-id="c6779-122">Your main accounts shouldn't use any special characters that are used as chart of accounts delimiters.</span></span> <span data-ttu-id="c6779-123">Se você tiver um caractere especial igual ao delimitador do seu plano de contas, talvez experimente instabilidade ou precise sempre usar pesquisas ou o submenu ao inserir combinações de contas e de dimensões.</span><span class="sxs-lookup"><span data-stu-id="c6779-123">If you do have a special character that is the same as your chart of accounts delimiter, you may experience instability, or the need to always use lookups or the flyout when entering account and dimension combinations.</span></span> <span data-ttu-id="c6779-124">Para saber mais, consulte [Criar uma conta principal](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="c6779-124">For more information, see [Create a main account](tasks/create-account-structures.md).</span></span>


<span data-ttu-id="c6779-125">É recomendável vincular as contas principais a categorias de conta principal, de forma que você possa aproveitar as vantagens dos relatórios financeiros padrão sem ter que fazer modificações.</span><span class="sxs-lookup"><span data-stu-id="c6779-125">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="c6779-126">Consequentemente, você poderá projetar e manter relatórios de forma mais rápida e fácil.</span><span class="sxs-lookup"><span data-stu-id="c6779-126">Therefore, you can more quickly and easily design and maintain reports.</span></span> 

<span data-ttu-id="c6779-127">Use a página **Configurar estruturas de conta** para criar estruturas de conta.</span><span class="sxs-lookup"><span data-stu-id="c6779-127">Use the **Configure account structures** page to create account structures.</span></span> <span data-ttu-id="c6779-128">As estruturas de conta definem as combinações válidas.</span><span class="sxs-lookup"><span data-stu-id="c6779-128">Account structures define valid combinations.</span></span> <span data-ttu-id="c6779-129">As combinações, juntamente com as contas principais, formam um plano de contas.</span><span class="sxs-lookup"><span data-stu-id="c6779-129">The combinations, together with main accounts, form a chart of accounts.</span></span>  <span data-ttu-id="c6779-130">Para saber mais, consulte [Criar estruturas de conta](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="c6779-130">For more information, see [Create account structures](tasks/create-main-account.md).</span></span>

<span data-ttu-id="c6779-131">**Substituições de entidade legal**</span><span class="sxs-lookup"><span data-stu-id="c6779-131">**Legal entity overrides**</span></span> 

<span data-ttu-id="c6779-132">Nem todas as contas principais são válidas para todas as entidades legais e algumas podem ser relevantes apenas por um período específico.</span><span class="sxs-lookup"><span data-stu-id="c6779-132">Not all main accounts are valid for all legal entities and some may only be relevant for a specific time period.</span></span> <span data-ttu-id="c6779-133">Neste cenário, a seção Substituições da entidade legal pode ser usada para identificar para quais empresas a conta principal deve ser suspensa, quem é o proprietário e há quanto tempo a dimensão está ativa.</span><span class="sxs-lookup"><span data-stu-id="c6779-133">In this scenario the Legal entity overrides section can be used to identify which companies the main account should be suspended for, who the owner is and the time period the dimension is active.</span></span> <span data-ttu-id="c6779-134">As substituições no nível compartilhado não podem ser mais restritivas do que as substituições no nível da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="c6779-134">The overrides at the shared level cannot be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="c6779-135">Para saber mais, consulte os seguintes tópicos: [Dimensões financeiras](financial-dimensions.md)
[Criar e atribuir estruturas de regra avançadas](tasks/create-assign-advanced-rule-structures.md)</span><span class="sxs-lookup"><span data-stu-id="c6779-135">For more information, see the following topics: [Financial dimensions](financial-dimensions.md)
[Create and assign advanced rule structures](tasks/create-assign-advanced-rule-structures.md)</span></span>




