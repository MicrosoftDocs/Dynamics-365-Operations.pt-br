--- 
title: "Definir políticas de auditoria para documentos de origem"
description: Este procedimento mostra como configurar e executar regras de diretiva de auditoria.
author: ryansandness
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a82c3e8e8787beb309b75b73cda36f4ca8031d6f
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="3e94d-103">Definir políticas de auditoria para documentos de origem</span><span class="sxs-lookup"><span data-stu-id="3e94d-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3e94d-104">Este procedimento mostra como configurar e executar regras de diretiva de auditoria.</span><span class="sxs-lookup"><span data-stu-id="3e94d-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="3e94d-105">O exemplo usa relatórios de despesas com o tipo de despesa do hotel.</span><span class="sxs-lookup"><span data-stu-id="3e94d-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="3e94d-106">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="3e94d-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="3e94d-107">A função do auditor contém as permissões corretas para executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="3e94d-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="3e94d-108">Vá para Bancada de auditoria > Configuração > Tipo de regra de política.</span><span class="sxs-lookup"><span data-stu-id="3e94d-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="3e94d-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3e94d-109">Click New.</span></span>
3. <span data-ttu-id="3e94d-110">No campo Nome da regra, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3e94d-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="3e94d-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3e94d-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3e94d-112">No campo nome da consulta, selecione Linha do relatório de despesas</span><span class="sxs-lookup"><span data-stu-id="3e94d-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="3e94d-113">No campo Tipo de consulta, selecione Agregar</span><span class="sxs-lookup"><span data-stu-id="3e94d-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="3e94d-114">No campo Entidade legal, selecione uma Entidade legal.</span><span class="sxs-lookup"><span data-stu-id="3e94d-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="3e94d-115">No campo de referência da data do documento, selecione a data e a hora da modificação</span><span class="sxs-lookup"><span data-stu-id="3e94d-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="3e94d-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="3e94d-116">Click Save.</span></span>
10. <span data-ttu-id="3e94d-117">Vá para Bancada de auditoria > Configuração > Políticas de auditoria.</span><span class="sxs-lookup"><span data-stu-id="3e94d-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="3e94d-118">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="3e94d-118">Click New.</span></span>
12. <span data-ttu-id="3e94d-119">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="3e94d-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="3e94d-120">Expanda a seção de organizações de diretivas.</span><span class="sxs-lookup"><span data-stu-id="3e94d-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="3e94d-121">Na árvore, selecione 'Contoso Entertainment System USA'.</span><span class="sxs-lookup"><span data-stu-id="3e94d-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="3e94d-122">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="3e94d-122">Click Add.</span></span>
16. <span data-ttu-id="3e94d-123">Na árvore, selecione 'Contoso Consulting USA'.</span><span class="sxs-lookup"><span data-stu-id="3e94d-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="3e94d-124">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="3e94d-124">Click Add.</span></span>
18. <span data-ttu-id="3e94d-125">Na árvore, selecione 'Contoso Retail USA'.</span><span class="sxs-lookup"><span data-stu-id="3e94d-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="3e94d-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="3e94d-126">Click Add.</span></span>
20. <span data-ttu-id="3e94d-127">Recolha a seção de organizações de diretivas.</span><span class="sxs-lookup"><span data-stu-id="3e94d-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="3e94d-128">Expanda a seção de regras de diretivas.</span><span class="sxs-lookup"><span data-stu-id="3e94d-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="3e94d-129">Na lista, localize e selecione as regras de diretiva que foram criadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3e94d-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="3e94d-130">Clique em Criar regra de política.</span><span class="sxs-lookup"><span data-stu-id="3e94d-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="3e94d-131">No campo de data efetiva, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="3e94d-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="3e94d-132">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="3e94d-132">Click Filter.</span></span>
26. <span data-ttu-id="3e94d-133">Na lista, selecione a linha para a categoria de despesa, e defina os detalhes ao hotel</span><span class="sxs-lookup"><span data-stu-id="3e94d-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="3e94d-134">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3e94d-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="3e94d-135">Clique na guia Agregado.</span><span class="sxs-lookup"><span data-stu-id="3e94d-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="3e94d-136">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="3e94d-136">Click Add.</span></span>
30. <span data-ttu-id="3e94d-137">Na lista, selecione um valor de campo do valor da transação</span><span class="sxs-lookup"><span data-stu-id="3e94d-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="3e94d-138">No campo Campo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3e94d-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="3e94d-139">No campo de AggregateFunction, selecione 'Soma'.</span><span class="sxs-lookup"><span data-stu-id="3e94d-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="3e94d-140">Clique no Grupo por Guia.</span><span class="sxs-lookup"><span data-stu-id="3e94d-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="3e94d-141">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="3e94d-141">Click Add.</span></span>
35. <span data-ttu-id="3e94d-142">Na lista, selecione um valor de Funcionário </span><span class="sxs-lookup"><span data-stu-id="3e94d-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="3e94d-143">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="3e94d-143">Click Add.</span></span>
37. <span data-ttu-id="3e94d-144">Na lista, selecione um valor de Categoria de despesa</span><span class="sxs-lookup"><span data-stu-id="3e94d-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="3e94d-145">No campo Campo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3e94d-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="3e94d-146">Clique na guia Ter.</span><span class="sxs-lookup"><span data-stu-id="3e94d-146">Click the Having tab.</span></span>
40. <span data-ttu-id="3e94d-147">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="3e94d-147">Click Add.</span></span>
41. <span data-ttu-id="3e94d-148">Selecione o valor da transação</span><span class="sxs-lookup"><span data-stu-id="3e94d-148">Select Transaction amount</span></span>
42. <span data-ttu-id="3e94d-149">No campo Campo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="3e94d-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="3e94d-150">No campo de AggregateFunction, selecione 'Soma'.</span><span class="sxs-lookup"><span data-stu-id="3e94d-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="3e94d-151">No campo Critérios, digite ">2000".</span><span class="sxs-lookup"><span data-stu-id="3e94d-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="3e94d-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="3e94d-152">Click OK.</span></span>
46. <span data-ttu-id="3e94d-153">Clique em Teste.</span><span class="sxs-lookup"><span data-stu-id="3e94d-153">Click Test.</span></span>
47. <span data-ttu-id="3e94d-154">No campo Data de início da seleção do documento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="3e94d-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="3e94d-155">No campo Data de fim da seleção do documento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="3e94d-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="3e94d-156">Clique em Executar teste.</span><span class="sxs-lookup"><span data-stu-id="3e94d-156">Click Run test.</span></span>
50. <span data-ttu-id="3e94d-157">No Painel de Ação, clique em Auditar política.</span><span class="sxs-lookup"><span data-stu-id="3e94d-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="3e94d-158">Clique em Opções adicionais.</span><span class="sxs-lookup"><span data-stu-id="3e94d-158">Click Additional options.</span></span>
52. <span data-ttu-id="3e94d-159">No campo de data Iniciar, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="3e94d-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="3e94d-160">No campo de data Finalizar, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="3e94d-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="3e94d-161">Clique em Lote.</span><span class="sxs-lookup"><span data-stu-id="3e94d-161">Click Batch.</span></span>
55. <span data-ttu-id="3e94d-162">Expanda a seção Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3e94d-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="3e94d-163">Selecione Sim no campo Processamento de lote.</span><span class="sxs-lookup"><span data-stu-id="3e94d-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="3e94d-164">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="3e94d-164">Click OK.</span></span>
58. <span data-ttu-id="3e94d-165">Vá para Bancada de auditoria > Casos de auditoria.</span><span class="sxs-lookup"><span data-stu-id="3e94d-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="3e94d-166">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="3e94d-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="3e94d-167">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3e94d-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="3e94d-168">Expanda a seção Associações.</span><span class="sxs-lookup"><span data-stu-id="3e94d-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="3e94d-169">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="3e94d-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="3e94d-170">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3e94d-170">In the list, click the link in the selected row.</span></span>


