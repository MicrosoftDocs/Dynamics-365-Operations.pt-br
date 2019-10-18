---
title: Planejar seu plano de contas
description: Este tópico fornece informações que o ajudarão a planejar o plano de contas para sua organização.
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 007b634c18ce897160aea38e05c9a73a64dd3917
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186362"
---
# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="2bb22-103">Planejar seu plano de contas</span><span class="sxs-lookup"><span data-stu-id="2bb22-103">Plan your chart of accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2bb22-104">Este tópico fornece informações que o ajudarão a planejar o plano de contas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2bb22-104">This topic provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="2bb22-105">Para rastrear e manter as informações financeiras em uma organização, você pode configurar um plano de contas.</span><span class="sxs-lookup"><span data-stu-id="2bb22-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="2bb22-106">Um plano de contas é um conjunto de contas que definem uma estrutura financeira.</span><span class="sxs-lookup"><span data-stu-id="2bb22-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="2bb22-107">Para rastrear outras transações nessas contas, você pode adicionar segmentos.</span><span class="sxs-lookup"><span data-stu-id="2bb22-107">To further track the transactions in these accounts, you can add segments.</span></span> <span data-ttu-id="2bb22-108">Esses segmentos são conhecidos como dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="2bb22-108">These segments are known as financial dimensions.</span></span> <span data-ttu-id="2bb22-109">Por exemplo, uma conta de despesas pode incluir as dimensões financeiras denominadas Departamento, Centro de custos e Finalidade.</span><span class="sxs-lookup"><span data-stu-id="2bb22-109">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="2bb22-110">As regras definidas pelo usuário determinam como as dimensões financeiras são anexadas às contas principais e às outras dimensões financeiras, e também como as transações podem ser inseridas.</span><span class="sxs-lookup"><span data-stu-id="2bb22-110">User-defined rules determine how financial dimensions are attached to the main accounts and to other financial dimensions, and also how transactions are entered.</span></span> <span data-ttu-id="2bb22-111">Essas regras definidas pelo usuário são conhecidas como estruturas de conta e regras avançadas.</span><span class="sxs-lookup"><span data-stu-id="2bb22-111">These user-defined rules are known as account structures and advanced rules.</span></span>

<span data-ttu-id="2bb22-112">O plano de contas é uma lista estruturada das contas da contabilidade de uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="2bb22-112">The chart of accounts is a structured list of a legal entity's general ledger accounts.</span></span> <span data-ttu-id="2bb22-113">A lista é utilizada para preparar relatórios financeiros para autoridades e proprietários.</span><span class="sxs-lookup"><span data-stu-id="2bb22-113">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="2bb22-114">As contas primeiro são agrupadas em tipos de contas e depois são agregadas em categorias maiores.</span><span class="sxs-lookup"><span data-stu-id="2bb22-114">The accounts are first grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="2bb22-115">No nível mais amplo, as contas são agrupadas como receitas e custos (contas operacionais), ativos e passivos (contas de saldo).</span><span class="sxs-lookup"><span data-stu-id="2bb22-115">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span>

<span data-ttu-id="2bb22-116">Um plano de contas pode ser compartilhado e usado por todas as entidades legais em uma organização.</span><span class="sxs-lookup"><span data-stu-id="2bb22-116">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="2bb22-117">O plano de contas usado por uma entidade legal é definido na página **Razão**.</span><span class="sxs-lookup"><span data-stu-id="2bb22-117">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span>

<span data-ttu-id="2bb22-118">Veja alguns dos fatores que você deve considerar ao planejar a estrutura do plano de contas para sua organização:</span><span class="sxs-lookup"><span data-stu-id="2bb22-118">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

- <span data-ttu-id="2bb22-119">Os requisitos de relatório do país ou da região em que sua organização está sediada</span><span class="sxs-lookup"><span data-stu-id="2bb22-119">The reporting requirements of the country or region where your organization is based</span></span>
- <span data-ttu-id="2bb22-120">Os requisitos de relatórios da entidade legal</span><span class="sxs-lookup"><span data-stu-id="2bb22-120">The reporting requirements of your legal entity</span></span>
- <span data-ttu-id="2bb22-121">O grau de especificação é necessário para as duas organizações externas e a sua organização</span><span class="sxs-lookup"><span data-stu-id="2bb22-121">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="2bb22-122">Você cria o plano de contas na página **Plano de contas**.</span><span class="sxs-lookup"><span data-stu-id="2bb22-122">You create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="2bb22-123">Você pode criar as contas principais na página **Plano de contas** ou na página **Contas principais**.</span><span class="sxs-lookup"><span data-stu-id="2bb22-123">You can create main accounts from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="2bb22-124">Suas contas principais não devem usar caracteres especiais que são utilizados como delimitadores do plano de contas.</span><span class="sxs-lookup"><span data-stu-id="2bb22-124">Your main accounts shouldn't use any special characters that are used as delimiters for chart of accounts.</span></span> <span data-ttu-id="2bb22-125">Caso contrário, você pode se deparar com instabilidade, ou pode ser necessário sempre usar pesquisas ou a caixa de diálogo, ao inserir combinações de contas e dimensões.</span><span class="sxs-lookup"><span data-stu-id="2bb22-125">Otherwise, you might experience instability, or you might always have to use lookups or the dialog box when you enter combinations of accounts and dimensions.</span></span> <span data-ttu-id="2bb22-126">Para saber mais, consulte [Criar uma conta principal](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="2bb22-126">For more information, see [Create a main account](tasks/create-main-account.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2bb22-127">No Dynamics 365 for Finance and Operations versão 8.0 (Abril 2018), você pode modificar o delimitador de plano de contas da página **Parâmetros de contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="2bb22-127">In Dynamics 365 for Finance and Operations version 8.0 (April 2018), you can modify the chart of accounts delimiter from the **General ledger parameters** page.</span></span>

<span data-ttu-id="2bb22-128">É recomendável vincular as contas principais a categorias de conta principal, de forma que você possa aproveitar as vantagens dos relatórios financeiros padrão sem ter que fazer modificações.</span><span class="sxs-lookup"><span data-stu-id="2bb22-128">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="2bb22-129">Consequentemente, você poderá projetar e manter relatórios de forma mais rápida e fácil.</span><span class="sxs-lookup"><span data-stu-id="2bb22-129">Therefore, you can more quickly and easily design and maintain reports.</span></span>

<span data-ttu-id="2bb22-130">Você criar estruturas de conta na página **Configurar estruturas de conta**.</span><span class="sxs-lookup"><span data-stu-id="2bb22-130">You create account structures on the **Configure account structures** page.</span></span> <span data-ttu-id="2bb22-131">As estruturas de conta definem as combinações válidas.</span><span class="sxs-lookup"><span data-stu-id="2bb22-131">Account structures define valid combinations.</span></span> <span data-ttu-id="2bb22-132">Essas combinações, juntamente com as contas principais, formam um plano de contas.</span><span class="sxs-lookup"><span data-stu-id="2bb22-132">These combinations, together with main accounts, form a chart of accounts.</span></span> <span data-ttu-id="2bb22-133">Para saber mais, consulte [Criar estruturas de conta](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="2bb22-133">For more information, see [Create account structures](tasks/create-account-structures.md).</span></span>

<span data-ttu-id="2bb22-134">**Substituições de entidade legal**</span><span class="sxs-lookup"><span data-stu-id="2bb22-134">**Legal entity overrides**</span></span>

<span data-ttu-id="2bb22-135">Nem todas as contas principais são válidas para todas as entidades legais, e algumas podem ser relevantes apenas por um período específico.</span><span class="sxs-lookup"><span data-stu-id="2bb22-135">Not all main accounts are valid for all legal entities, and some main account might be relevant only for a specific period.</span></span> <span data-ttu-id="2bb22-136">Neste cenário, você pode usar a seção **Substituições da entidade legal** para identificar as empresas para a qual a conta principal deve ser suspensa, o proprietário, e o período no qual a dimensão está ativa.</span><span class="sxs-lookup"><span data-stu-id="2bb22-136">In this scenario, you can use the **Legal entity overrides** section to identify the companies that the main account should be suspended for, the owner, and the period when the dimension is active.</span></span> <span data-ttu-id="2bb22-137">As substituições no nível compartilhado não podem ser mais restritivas do que as substituições no nível da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="2bb22-137">The overrides at the shared level can't be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="2bb22-138">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="2bb22-138">For more information, see the following topics:</span></span>

- [<span data-ttu-id="2bb22-139">Dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="2bb22-139">Financial dimensions</span></span>](financial-dimensions.md)
- [<span data-ttu-id="2bb22-140">Criar e atribuir estruturas de regras avançadas</span><span class="sxs-lookup"><span data-stu-id="2bb22-140">Create and assign advanced rule structures</span></span>](tasks/create-assign-advanced-rule-structures.md)
