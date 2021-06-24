---
title: Auditar regras da política
description: Você pode usar as políticas para avaliar relatórios de despesas, faturas de fornecedor e ordens de compra para garantir que eles estejam em conformidade com as regras de política criadas. Todas as regras associadas a uma política de auditoria são executadas em modo de lotes de acordo com uma agenda especificada.  Cada regra de política é uma instância de um tipo de regra de política. Para cada tipo de regra de política, somente uma regra de política pode ficar ativa de cada vez.
author: panolte
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f57c3405e03651798b7e0aaf1fab84d25f33f7cc
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187859"
---
# <a name="audit-policy-rules"></a><span data-ttu-id="6e9d0-106">Auditar regras da política</span><span class="sxs-lookup"><span data-stu-id="6e9d0-106">Audit policy rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e9d0-107">Você pode usar as políticas para avaliar relatórios de despesas, faturas de fornecedor e ordens de compra para garantir que eles estejam em conformidade com as regras de política criadas.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-107">You can use audit policies to evaluate expense reports, vendor invoices, and purchase orders to make sure that they comply with policy rules that you create.</span></span> <span data-ttu-id="6e9d0-108">Todas as regras associadas a uma política de auditoria são executadas em modo de lotes de acordo com uma agenda especificada.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-108">All of the rules that are associated with an audit policy are run in batch mode, according to a schedule that you specify.</span></span>  <span data-ttu-id="6e9d0-109">Cada regra de política é uma instância de um tipo de regra de política.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-109">Each policy rule is an instance of a policy rule type.</span></span> <span data-ttu-id="6e9d0-110">Para cada tipo de regra de política, somente uma regra de política pode ficar ativa de cada vez.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-110">For each policy rule type, only one policy rule can be active at a time.</span></span> 

## <a name="queries-and-query-types"></a><span data-ttu-id="6e9d0-111">Consultas e tipos de consulta</span><span class="sxs-lookup"><span data-stu-id="6e9d0-111">Queries and query types</span></span>

<span data-ttu-id="6e9d0-112">Quando você cria uma regra de política de auditoria, seleciona primeiro um tipo de regra de política.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-112">When you create an audit policy rule, you first select a policy rule type.</span></span> <span data-ttu-id="6e9d0-113">O tipo de regra de política especifica o aplicativo AOT (Árvore de objetos de aplicativo) para usar como ponto de partida para criar a regra de política.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-113">The policy rule type specifies the Application Object Tree (AOT) query to use as the starting point for creating the policy rule.</span></span> <span data-ttu-id="6e9d0-114">Também especifica o tipo de consulta a ser usado para a regra de política.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-114">It also specifies the query type to use for the policy rule.</span></span> <span data-ttu-id="6e9d0-115">A consulta determina o documento de origem que a regra de política avalia.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-115">The query determines the source document that the policy rule evaluates.</span></span> <span data-ttu-id="6e9d0-116">Também especifica os campos no documento de origem que identificam a entidade legal e data a ser usada quando os documentos forem selecionados para auditoria.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-116">It also specifies the fields in the source document that identify both the legal entity and the date to use when documents are selected for audit.</span></span> <span data-ttu-id="6e9d0-117">O tipo de consulta controla os campos padrão na página de consulta e na página Auditar regra de política.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-117">The query type controls the default fields in the query page and in the Audit policy rule page.</span></span> <span data-ttu-id="6e9d0-118">A tabela a seguir mostra os tipos de consulta disponíveis para as regras de política de auditoria.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-118">The following table shows the query types that are available for audit policy rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e9d0-119">Tipo de consulta</span><span class="sxs-lookup"><span data-stu-id="6e9d0-119">Query type</span></span></th>
<th><span data-ttu-id="6e9d0-120">Finalidade</span><span class="sxs-lookup"><span data-stu-id="6e9d0-120">Purpose</span></span></th>
<th><span data-ttu-id="6e9d0-121">Mais informações</span><span class="sxs-lookup"><span data-stu-id="6e9d0-121">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6e9d0-122">Condicional</span><span class="sxs-lookup"><span data-stu-id="6e9d0-122">Conditional</span></span></td>
<td><span data-ttu-id="6e9d0-123">Avaliar atributos do documento de origem com valores especificados.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-123">Evaluate source document attributes against specified values.</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6e9d0-124">Agregado</span><span class="sxs-lookup"><span data-stu-id="6e9d0-124">Aggregate</span></span></td>
<td><span data-ttu-id="6e9d0-125">Avaliar vários documentos de origem ou linhas do documento de origem para uma regra de política agregando valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-125">Evaluate multiple source documents or source document lines against a policy rule by aggregating numeric values.</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6e9d0-126">Amostragem</span><span class="sxs-lookup"><span data-stu-id="6e9d0-126">Sampling</span></span></td>
<td><span data-ttu-id="6e9d0-127">Selecionar aleatoriamente uma porcentagem específica de documentos de origem para avaliar as violações de política.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-127">Randomly select a specified percentage of the source documents to evaluate for policy violations.</span></span></td>
<td><span data-ttu-id="6e9d0-128">Quando você selecionar essa opção, use a página Auditar regra de política para especificar a porcentagem de documentos a serem aleatoriamente selecionados para auditoria.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-128">When you select this option, use the Audit policy rule page to specify the percentage of documents to randomly select for audit.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6e9d0-129">Duplicata</span><span class="sxs-lookup"><span data-stu-id="6e9d0-129">Duplicate</span></span></td>
<td><span data-ttu-id="6e9d0-130">Avaliar documentos de origem para determinar se eles contêm entradas duplicadas nos campos especificados.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-130">Evaluate source documents to determine whether they contain duplicate entries in specified fields.</span></span></td>
<td><span data-ttu-id="6e9d0-131">Quando você selecionar essa opção, use o a página Auditar regra da política para especificar o número de dias a serem adicionados ao início do intervalo de datas da seleção de documento quando os documentos são avaliados para entradas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-131">When you select this option, use the Audit policy rule page to specify the number of days to add to the start of the document selection date range when documents are evaluated for duplicate entries.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6e9d0-132">Pesquisa de lista</span><span class="sxs-lookup"><span data-stu-id="6e9d0-132">List search</span></span></td>
<td><span data-ttu-id="6e9d0-133">Avaliar documentos de origem para entidades específicas.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-133">Evaluate source documents for specific entities.</span></span></td>
<td><span data-ttu-id="6e9d0-134">O documento raiz de consulta define o documento que está sendo auditado.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-134">The root document of the query defines the document that is being audited.</span></span> <span data-ttu-id="6e9d0-135">A consulta deve ser uma consulta na lista que contenha uma referência à tabela dirpartytable.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-135">The query must be a list query that includes a reference to the dirpartytable table.</span></span> <span data-ttu-id="6e9d0-136">Esta opção só pode ser usada com as seguintes consultas da AOT:</span><span class="sxs-lookup"><span data-stu-id="6e9d0-136">This option can be used only with the following AOT queries:</span></span>
<ul>
<li><span data-ttu-id="6e9d0-137"><span class="ui">AuditPolicyExpenseList</span> (Funcionários monitorados por relatório de despesas)</span><span class="sxs-lookup"><span data-stu-id="6e9d0-137"><span class="ui">AuditPolicyExpenseList</span> (Expense report monitored employees)</span></span></li>
<li><span data-ttu-id="6e9d0-138"><span class="ui">AuditPolicyPurchList</span> (Fornecedores monitorados por ordem de compra)</span><span class="sxs-lookup"><span data-stu-id="6e9d0-138"><span class="ui">AuditPolicyPurchList</span> (Purchase order monitored vendors)</span></span></li>
<li><span data-ttu-id="6e9d0-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Fornecedores monitorados por fatura de fornecedor)</span><span class="sxs-lookup"><span data-stu-id="6e9d0-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Vendor invoice monitored vendors)</span></span></li>
</ul>
<span data-ttu-id="6e9d0-140">Quando você selecionar essa opção, especifique as entidades monitoradas na página Auditar regra de política.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-140">When you select this option, specify the monitored entities in the Audit policy rule page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6e9d0-141">Pesquisa por palavra-chave</span><span class="sxs-lookup"><span data-stu-id="6e9d0-141">Keyword search</span></span></td>
<td><span data-ttu-id="6e9d0-142">Avaliar documentos de origem para determinar se eles contêm determinadas palavras.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-142">Evaluate source documents to determine whether they contain certain words.</span></span></td>
<td><span data-ttu-id="6e9d0-143">Quando você selecionar essa opção, insira as palavras para procurar na página Auditar regra de política.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-143">When you select this option, enter the words to look for in the Audit policy rule page.</span></span> <span data-ttu-id="6e9d0-144">A página Auditar regra de política também inclui opções que permitem a especificação de tabelas e campos para avaliar as palavras inseridas.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-144">The Audit policy rule page also includes options that let you specify the tables and fields to evaluate for the words you entered.</span></span></td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a><span data-ttu-id="6e9d0-145">Parâmetros comuns</span><span class="sxs-lookup"><span data-stu-id="6e9d0-145">Common parameters</span></span>
<span data-ttu-id="6e9d0-146">Todas as regras de política para uma política de auditoria específica compartilham os mesmos parâmetros de lote e o mesmo intervalo de datas da seleção de documento.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-146">All of the policy rules for a particular audit policy share the same batch parameters and the same document selection date range.</span></span> <span data-ttu-id="6e9d0-147">Esses parâmetros são especificados para a política na página Opções adicionais.</span><span class="sxs-lookup"><span data-stu-id="6e9d0-147">These parameters are specified for the policy in the Additional options page.</span></span>



## <a name="additional-resources"></a><span data-ttu-id="6e9d0-148">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6e9d0-148">Additional resources</span></span>

<span data-ttu-id="6e9d0-149">[Auditar violações de política e casos](audit-policy-violations-cases.md)
[Definir políticas de auditoria para documentos de origem](tasks/define-audit-policies-source-documents.md)</span><span class="sxs-lookup"><span data-stu-id="6e9d0-149">[Audit policy violations and cases](audit-policy-violations-cases.md)
[Define audit policies for source documents](tasks/define-audit-policies-source-documents.md)</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]