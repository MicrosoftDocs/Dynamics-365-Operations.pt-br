---
title: "Auditar violações de política e casos"
description: "O artigo explica como os casos de auditoria são gerados de violações de regras de diretiva de auditoria. Também inclui informações sobre as diversas maneiras das políticas de auditoria usarem o intervalo de datas de seleção de documento."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2376a1d6e86eba9f5021cc08dcfaea52f131a3d7
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="audit-policy-violations-and-cases"></a><span data-ttu-id="22a3c-104">Auditar violações de política e casos</span><span class="sxs-lookup"><span data-stu-id="22a3c-104">Audit policy violations and cases</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="22a3c-105">O artigo explica como os casos de auditoria são gerados de violações de regras de diretiva de auditoria.</span><span class="sxs-lookup"><span data-stu-id="22a3c-105">The article explains how audit cases are generated from violations of audit policy rules.</span></span> <span data-ttu-id="22a3c-106">Também inclui informações sobre as diversas maneiras das políticas de auditoria usarem o intervalo de datas de seleção de documento.</span><span class="sxs-lookup"><span data-stu-id="22a3c-106">It also includes information about the various ways that audit policies use the document selection date range.</span></span>

<a name="how-audit-cases-are-generated"></a><span data-ttu-id="22a3c-107">Como os casos de auditoria são gerados</span><span class="sxs-lookup"><span data-stu-id="22a3c-107">How audit cases are generated</span></span>
-----------------------------

<span data-ttu-id="22a3c-108">As políticas de auditoria são usadas para identificar relatórios de despesas, ordens de compra e faturas de fornecedor que não estão de acordo com as regras comerciais que você define e configura como regras de política de auditoria.</span><span class="sxs-lookup"><span data-stu-id="22a3c-108">Audit policies are used to identify expense reports, purchase orders, and vendor invoices that don't comply with business rules that you define and configure as audit policy rules.</span></span> 

<span data-ttu-id="22a3c-109">As políticas de auditoria são executadas em modo de lotes.</span><span class="sxs-lookup"><span data-stu-id="22a3c-109">Audit policies are run in batch mode.</span></span> <span data-ttu-id="22a3c-110">Quando você executa uma política de auditoria, todas as regras de política que fazem parte dela são executadas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="22a3c-110">When you run an audit policy, all the policy rules that are part of that policy are run at the same time.</span></span>

<span data-ttu-id="22a3c-111">Cada regra de política avalia um conjunto de documentos.</span><span class="sxs-lookup"><span data-stu-id="22a3c-111">Each policy rule evaluates a set of documents.</span></span> <span data-ttu-id="22a3c-112">A regra de política seleciona documentos que estão no intervalo de datas de seleção de documento e que correspondem aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="22a3c-112">The policy rule selects documents that are in the document selection date range and that match the specified criteria.</span></span> <span data-ttu-id="22a3c-113">Por exemplo, uma regra de política pode selecionar os relatórios de despesas com refeições acima de 50,00.</span><span class="sxs-lookup"><span data-stu-id="22a3c-113">For example, one policy rule might select expense reports that have meals that exceed 50.00.</span></span> <span data-ttu-id="22a3c-114">Outra regras de política podem selecionar faturas de fornecedor que podem ser pagas para um fornecedor específico.</span><span class="sxs-lookup"><span data-stu-id="22a3c-114">Another policy rule might select vendor invoices that are payable to a specific vendor.</span></span> <span data-ttu-id="22a3c-115">Para cada documento selecionado na definição, uma violação é gerada.</span><span class="sxs-lookup"><span data-stu-id="22a3c-115">For each document that is selected in the set, a violation is generated.</span></span> <span data-ttu-id="22a3c-116">Essa violação é um registro de que um documento específico, como uma fatura 12345, não atende às regras de política.</span><span class="sxs-lookup"><span data-stu-id="22a3c-116">That violation is a record that a particular document, such as invoice 12345, doesn't comply with the policy rule.</span></span> 

<span data-ttu-id="22a3c-117">Vários registros de violação de auditoria são agrupados e associados a casos de auditoria.</span><span class="sxs-lookup"><span data-stu-id="22a3c-117">Multiple audit violation records are grouped together and associated with audit cases.</span></span> <span data-ttu-id="22a3c-118">Por padrão, os casos de cada política de auditoria são agrupados por regra de política de auditoria.</span><span class="sxs-lookup"><span data-stu-id="22a3c-118">By default, cases for each audit policy are grouped by audit policy rule.</span></span> <span data-ttu-id="22a3c-119">Se você preferir, selecione outros critérios de agrupamento ao usar a página **Critérios de agrupamento de caso**.</span><span class="sxs-lookup"><span data-stu-id="22a3c-119">If you prefer, you can select other grouping criteria by using the **Case grouping criteria** page.</span></span> <span data-ttu-id="22a3c-120">Por exemplo, você pode agrupar os cabeçalhos de despesas pela ID do projeto e faturas por conta do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="22a3c-120">For example, you can group expense headers by project ID and vendor invoices by vendor account.</span></span> <span data-ttu-id="22a3c-121">Nesse caso, todas as violações do cabeçalho de despesas que têm a mesma ID do projeto serão agrupadas nos mesmos caso e todas as faturas de fornecedores que têm a mesma conta de fornecedor serão agrupadas no mesmo caso.</span><span class="sxs-lookup"><span data-stu-id="22a3c-121">In this case, all expense header violations that have the same project ID will be grouped in the same case, and all vendor invoices that have the same vendor account will be grouped in the same case.</span></span> 

> [!NOTE]
> <span data-ttu-id="22a3c-122">Para as regras de política com base em um tipo de consulta **Duplicar**, as violações não são agrupadas por regra de política ou pelo critério especificado na página **Critérios de agrupamento de caso**.</span><span class="sxs-lookup"><span data-stu-id="22a3c-122">For audit policy rules that are based on a **Duplicate** query type, violations aren't grouped by policy rule or by the criteria that are specified on the **Case grouping criteria** page.</span></span> <span data-ttu-id="22a3c-123">Em vez de isso, são agrupados pelos critérios criados na regra de política de auditoria.</span><span class="sxs-lookup"><span data-stu-id="22a3c-123">Instead, they are grouped by the criteria that are built into the audit policy rule.</span></span> <span data-ttu-id="22a3c-124">Por exemplo, se uma regra de política avaliar relatórios de despesas em busca de despesas duplicadas de mesmo valor, ID do mercado e data, todas as despesas que têm os mesmos valores nesses campos seriam um caso.</span><span class="sxs-lookup"><span data-stu-id="22a3c-124">For example, if a policy rule evaluates expense reports for duplicate expenses of the same amount, merchant ID, and date, all expenses that have the same values in those fields will be one case.</span></span> <span data-ttu-id="22a3c-125">As despesas que têm valores diferentes serão um caso separado.</span><span class="sxs-lookup"><span data-stu-id="22a3c-125">Any expenses that have different values will be a separate case.</span></span>

<span data-ttu-id="22a3c-126">Depois que os casos de auditoria foram gerados, serão processados usando os processos típicos do gerenciamento dos casos.</span><span class="sxs-lookup"><span data-stu-id="22a3c-126">After the audit cases have been generated, they are handled by using the typical processes for case management.</span></span>

## <a name="document-selection-date-ranges"></a><span data-ttu-id="22a3c-127">Intervalos de datas para seleção de documento</span><span class="sxs-lookup"><span data-stu-id="22a3c-127">Document selection date ranges</span></span>
<span data-ttu-id="22a3c-128">Quando uma política de auditoria for executada, cada regras de política seleciona os documentos do tipo especificado que têm uma data dentro do intervalo de datas de seleção de documento.</span><span class="sxs-lookup"><span data-stu-id="22a3c-128">When an audit policy is run, each policy rule selects documents of the specified type that have a date that is in the document selection date range.</span></span> <span data-ttu-id="22a3c-129">O intervalo de datas de seleção de documentos é especificado na página **Opções adicionais**.</span><span class="sxs-lookup"><span data-stu-id="22a3c-129">The document selection date range is specified on the **Additional options** page.</span></span> <span data-ttu-id="22a3c-130">Vários documentos têm mais de uma data associada a eles.</span><span class="sxs-lookup"><span data-stu-id="22a3c-130">Many documents have more than one date associated with them.</span></span> <span data-ttu-id="22a3c-131">O campo de data que a regra de política de auditoria usa é especificado na página **Tipo de regras de política**.</span><span class="sxs-lookup"><span data-stu-id="22a3c-131">The date field that the audit policy rule uses is specified on the **Policy rule type** page.</span></span>

<span data-ttu-id="22a3c-132">Veja aqui outras formas que a política de auditoria usa o intervalo de datas da seleção de documentos:</span><span class="sxs-lookup"><span data-stu-id="22a3c-132">Here are some other ways that an audit policy uses the document selection date range:</span></span>

-   <span data-ttu-id="22a3c-133">A política usa a versão de cada regra de política que estará em vigor no último dia do intervalo de datas de seleção de documentos.</span><span class="sxs-lookup"><span data-stu-id="22a3c-133">The policy uses the version of each policy rule that is effective on the last day of the document selection date range.</span></span> <span data-ttu-id="22a3c-134">Você pode visualizar as datas para cada regra de política na página da lista **Políticas de auditoria**.</span><span class="sxs-lookup"><span data-stu-id="22a3c-134">You can view the effective dates for each policy rule on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="22a3c-135">A política usa os nós de organização que são associados à política no último dia do intervalo de datas de seleção de documento.</span><span class="sxs-lookup"><span data-stu-id="22a3c-135">The policy uses the organization nodes that are associated with the policy on the last day of the document selection date range.</span></span> <span data-ttu-id="22a3c-136">Somente os nós da organização que são associados à política são exibidos na página da lista **Políticas de auditoria**.</span><span class="sxs-lookup"><span data-stu-id="22a3c-136">Only the organization nodes that are currently associated with the policy appear on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="22a3c-137">Para as regras de política se baseiam em um tipo de consulta **Pesquisa da lista**, a política avalia documentos para entidades monitoradas em vigor no último dia do intervalo de datas de seleção de documento.</span><span class="sxs-lookup"><span data-stu-id="22a3c-137">For policy rules that are based on a **List search** query type, the policy evaluates documents for monitored entities that are effective on the last day of the document selection date range.</span></span>


<span data-ttu-id="22a3c-138">Para obter mais informações, consulte [Auditar regras da política](audit-policy-rules.md)</span><span class="sxs-lookup"><span data-stu-id="22a3c-138">For more information, see [Audit policy rules](audit-policy-rules.md)</span></span>




