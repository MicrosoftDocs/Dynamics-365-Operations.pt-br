---
title: "Regras de alocação do razão"
description: "Este artigo oferece informações gerais sobre as regras de alocação do razão. Ele descreve os diversos componentes dessas regras de alocação e os métodos de alocação que podem ser usados para eles."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 63562cde3f2813fdcfc9df7ccbfc623aa2fbe9b1
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="ledger-allocation-rules"></a><span data-ttu-id="6ef6e-104">Regras de alocação do razão</span><span class="sxs-lookup"><span data-stu-id="6ef6e-104">Ledger allocation rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6ef6e-105">Este artigo oferece informações gerais sobre as regras de alocação do razão.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-105">This article provides information about ledger allocation rules.</span></span> <span data-ttu-id="6ef6e-106">Ele descreve os diversos componentes dessas regras de alocação e os métodos de alocação que podem ser usados para eles.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-106">It describes the various components of these allocation rules and the allocation methods that can be used for them.</span></span>

<span data-ttu-id="6ef6e-107">As regras de alocação do razão são usadas para calcular e gerar automaticamente os diários de alocação e entradas de conta da alocação dos saldos ou valores fixos do razão.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-107">Ledger allocation rules are used to automatically calculate and generate allocation journals and account entries for the allocation of ledger balances or fixed amounts.</span></span> <span data-ttu-id="6ef6e-108">Os métodos de alocação podem ser fixos ou variáveis.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-108">Allocation methods can be variable or fixed.</span></span> <span data-ttu-id="6ef6e-109">Os seguintes métodos de alocação podem ser usados para regras de alocação do razão:</span><span class="sxs-lookup"><span data-stu-id="6ef6e-109">The following allocation methods can be used for ledger allocation rules:</span></span>

-   <span data-ttu-id="6ef6e-110">**Base** – Este método de variável é usado quando a alocação depende do saldo real do razão, com base em critérios de filtragem.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-110">**Basis** – This variable method is used when the allocation depends on the actual ledger balance, based on filter criteria.</span></span> <span data-ttu-id="6ef6e-111">Por exemplo, as despesas publicitárias podem ser alocadas com base nas vendas de cada departamento em relação ao total das vendas departamentais.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-111">For example, advertising expenses can be allocated based on each department's sales in proportion to the total departmental sales.</span></span>
-   <span data-ttu-id="6ef6e-112">**Percentual fixo** e **Peso fixo** – Para esses métodos, a porcentagem ou peso de alocação é definido diretamente para a regra.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-112">**Fixed percentage** and **Fixed weight** – For these methods, the allocation percentage or weight is defined directly for the rule.</span></span> <span data-ttu-id="6ef6e-113">Por exemplo, as despesas publicitárias podem ser alocadas, de forma que o Departamento A receba 70 por cento de despesas publicitárias e o Departamento B receba 30 por cento.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-113">For example, advertising expenses can be allocated so that Department A receives 70 percent of the advertising expense and Department B receives 30 percent.</span></span>
-   <span data-ttu-id="6ef6e-114">**Igualmente** – Este método rateia o valor igualmente a cada meta definida.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-114">**Equally** – This method distributes the amount equally to each defined destination.</span></span> <span data-ttu-id="6ef6e-115">Por exemplo, se os destinos forem definidos para o departamento A e o Departamento B, as despesas publicitárias pode ser alocadas, de forma que o Departamento A e o Departamento B receba 50 por cento de despesas publicitárias.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-115">For example, if destinations are defined for Department A and Department B, advertising expenses can be allocated so that both Department A and Department B receive 50 percent of the advertising expense.</span></span>

<span data-ttu-id="6ef6e-116">Se a Base for usada como o método de alocação de uma regra de alocação você também deverá definir uma regras base de alocação do razão à parte.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-116">If Basis is used as the allocation method for an allocation rule, you must also define separate ledger allocation basis rules.</span></span> <span data-ttu-id="6ef6e-117">O processo "Solicitação de alocação do processo" permite que os usuários processem a regra de alocação do razão e exiba as entradas de diário de alocação resultantes antes de lançar ou excluir as alocações calculadas.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-117">The "Process allocation request" process lets users process the ledger allocation rule and preview the resulting allocation journal entries before they either post or delete the calculated allocations.</span></span>

## <a name="components-of-ledger-allocation-rules"></a><span data-ttu-id="6ef6e-118">Componentes de regras de alocação do razão</span><span class="sxs-lookup"><span data-stu-id="6ef6e-118">Components of ledger allocation rules</span></span>
<span data-ttu-id="6ef6e-119">Cada regra de alocação possui quatro componentes: geral, origem, destino e compensação.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-119">Each allocation rule has four components: general, source, destination, and offset.</span></span> <span data-ttu-id="6ef6e-120">Um componente adicional, regras básicas de alocação do razão, é necessário se a Base for usada como o método de alocação.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-120">An additional component, ledger allocation bases rules, is required if Basis is used as the allocation method.</span></span> <span data-ttu-id="6ef6e-121">Cada componente fornece as informações críticas necessárias para processar as alocações.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-121">Each component provides a critical piece of the information that is required in order to process allocations.</span></span>

-   <span data-ttu-id="6ef6e-122">**Geral** – Este componente é onde o usuário especifica opções, como o método de alocação, configurações de regras intercompanhia e se a regra está ativa.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-122">**General** – This component is where the user specifies options such as the allocation method, intercompany rule settings, and whether the rule is active.</span></span>
-   <span data-ttu-id="6ef6e-123">**Origem** – Esse componente é onde o usuário especifica os dados de origem da alocação.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-123">**Source** – This component is where the user specifies the source data for the allocation.</span></span> <span data-ttu-id="6ef6e-124">A alocação pode ser feita com base nos saldos do razão (**Fonte de dados** = **Razão**) ou valores fixos (**Fonte de dados** = **Valor fixo**).</span><span class="sxs-lookup"><span data-stu-id="6ef6e-124">Allocation can be based on ledger balances (**Data source** = **Ledger**) or fixed amounts (**Data source** = **Fixed value**).</span></span> <span data-ttu-id="6ef6e-125">Quando a **Fonte de dados** estiver definida como **Razão**, os critérios de filtragem de origem devem ser definidos para a regra de alocação do razão (por exemplo, para as despesas publicitárias).</span><span class="sxs-lookup"><span data-stu-id="6ef6e-125">When **Data source** is set to **Ledger**, source filter criteria must be defined for the ledger allocation rule (for example, for the advertising expenses).</span></span>
-   <span data-ttu-id="6ef6e-126">**Destino** – Esse componente define como o resultado do cálculo de alocação deve ser distribuído e contabilizado.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-126">**Destination** – This component defines how the result of the allocation calculation should be distributed and accounted for.</span></span> <span data-ttu-id="6ef6e-127">Por exemplo, pode haver uma linha de destino para cada departamento.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-127">For example, there can be one destination line for each department.</span></span>
-   <span data-ttu-id="6ef6e-128">**Compensação** – Esse componente define como as contas principais e as dimensões devem ser determinadas para as entradas de compensação que equilibram as entradas de destino.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-128">**Offset** – This component defines how main accounts and dimensions should be determined for the offset entries that balance the destination entries.</span></span> <span data-ttu-id="6ef6e-129">As opções definidas pelo usuário normalmente são usadas no lugar das contas e dimensões baseadas na origem.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-129">User-defined options are typically used instead of accounts and dimensions that are based on the source.</span></span> <span data-ttu-id="6ef6e-130">Quando a **Fonte de dados** for definida como **Valor fixo**, a **Origem** não poderá ser usada como padrão.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-130">When **Data source** is set to **Fixed value**, **Source** can't be used as an option.</span></span>
-   <span data-ttu-id="6ef6e-131">**Regras de base de alocação do razão** – Essas regras usam seus próprios critérios de filtragem de origem para determinar quais saldos do razão devem ser usados para a alocação (por exemplo, a receita por departamento.)</span><span class="sxs-lookup"><span data-stu-id="6ef6e-131">**Ledger allocation basis rules** – These rules use their own source filter criteria to determine which ledger balances should be used for allocation (for example, the revenue per department).</span></span> <span data-ttu-id="6ef6e-132">Cada regra básica de alocação pode ser usada com várias regras de alocação.</span><span class="sxs-lookup"><span data-stu-id="6ef6e-132">Each allocation basis rule can be used with multiple allocation rules.</span></span>





