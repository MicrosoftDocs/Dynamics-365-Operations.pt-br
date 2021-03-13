---
title: Definir políticas de auditoria para documentos de origem
description: Este tópico explica como configurar e executar regras de diretiva de auditoria.
author: panolte
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e020a9e82ff18055e40e3e0ddc7bbed1068c886c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021420"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="4fb2f-103">Definir políticas de auditoria para documentos de origem</span><span class="sxs-lookup"><span data-stu-id="4fb2f-103">Define audit policies for source documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4fb2f-104">Este tópico explica como configurar e executar regras de diretiva de auditoria.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-104">This topic explains how to set up and run audit policy rules.</span></span> <span data-ttu-id="4fb2f-105">O exemplo usa relatórios de despesas com o tipo de despesa do hotel.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="4fb2f-106">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="4fb2f-107">A função do auditor contém as permissões corretas para executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="4fb2f-108">No Painel de Navegação, vá para **Módulos > Bancada de auditoria > Configuração > Tipo de regra de política**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-108">In the navigation pane, go to **Modules > Audit workbench > Setup > Policy rule type**.</span></span>
2. <span data-ttu-id="4fb2f-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-109">Select **New**.</span></span>
3. <span data-ttu-id="4fb2f-110">No campo **Nome da regra**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-110">In the **Rule name** field, type a value.</span></span>
4. <span data-ttu-id="4fb2f-111">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="4fb2f-112">No campo **Nome da consulta**, selecione **Linha do relatório de despesas**</span><span class="sxs-lookup"><span data-stu-id="4fb2f-112">In the **Query name** field, select **Expense report line**</span></span>
6. <span data-ttu-id="4fb2f-113">No campo **tipo de consulta**, selecione **Agregar**</span><span class="sxs-lookup"><span data-stu-id="4fb2f-113">In the **query type** field, select **Aggregate**</span></span>
7. <span data-ttu-id="4fb2f-114">No campo **Entidade legal**, selecione **Entidade legal**</span><span class="sxs-lookup"><span data-stu-id="4fb2f-114">In the **Legal entity** field, select **Legal entity**</span></span>
8. <span data-ttu-id="4fb2f-115">No campo **Referência da data do documento**, selecione **Data e hora da modificação**</span><span class="sxs-lookup"><span data-stu-id="4fb2f-115">In the **Document date reference** field, select **Modified date and time**</span></span>
9. <span data-ttu-id="4fb2f-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-116">Select **Save**.</span></span>
10. <span data-ttu-id="4fb2f-117">No Painel de Navegação, vá para **Módulos > Bancada de auditoria > Configuração > Políticas de auditoria**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-117">In the navigation pane, go to **Modules > Audit workbench > Setup > Audit policies**.</span></span>
11. <span data-ttu-id="4fb2f-118">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-118">Select **New**.</span></span>
12. <span data-ttu-id="4fb2f-119">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-119">In the **Name** field, type a value.</span></span>
13. <span data-ttu-id="4fb2f-120">Expanda a seção **Organizações de política**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-120">Expand the **Policy organizations** section.</span></span>
14. <span data-ttu-id="4fb2f-121">Na árvore, selecione **Contoso Entertainment System USA** e **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-121">In the tree, select **Contoso Entertainment System USA**, then select **Add**.</span></span>
15. <span data-ttu-id="4fb2f-122">Na árvore, selecione **Contoso Consulting USA** e **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-122">In the tree, select **Contoso Consulting USA**, then select **Add**.</span></span>
16. <span data-ttu-id="4fb2f-123">Na árvore, selecione **Contoso Retail USA** e **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-123">In the tree, select **Contoso Retail USA**, then select **Add**.</span></span>
17. <span data-ttu-id="4fb2f-124">Recolha a seção **Organizações de política**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-124">Collapse the **Policy organizations** section.</span></span>
18. <span data-ttu-id="4fb2f-125">Expanda a seção **Regras de política**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-125">Expand the **Policy rules** section.</span></span>
19. <span data-ttu-id="4fb2f-126">Na lista, localize e selecione as regras de diretiva que foram criadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-126">In the list, find and select the Policy Rule that was created previously.</span></span>
20. <span data-ttu-id="4fb2f-127">Selecione **Criar regra de política**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-127">Select **Create policy rule**.</span></span>
21. <span data-ttu-id="4fb2f-128">No campo **Data de efetivação**, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-128">In the **Effective date** field, enter a date and time.</span></span>
22. <span data-ttu-id="4fb2f-129">Selecione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-129">Select **Filter**.</span></span>
23. <span data-ttu-id="4fb2f-130">Na lista, selecione a linha da **Categoria de despesa** e defina os detalhes como **Hotel**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-130">In the list, select the row for **Expense category**, and set the details to **Hotel**.</span></span>
24. <span data-ttu-id="4fb2f-131">No campo **Critérios**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-131">In the **Criteria** field, enter or select a value.</span></span>
25. <span data-ttu-id="4fb2f-132">Selecione a guia **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-132">Select the **Aggregate** tab.</span></span>
26. <span data-ttu-id="4fb2f-133">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-133">Select **Add**.</span></span>
27. <span data-ttu-id="4fb2f-134">Na lista, selecione um valor de campo do **Valor da transação**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-134">In the list, select a field value of **Transaction amount**.</span></span>
28. <span data-ttu-id="4fb2f-135">No campo **Campo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-135">In the **Field** field, enter or select a value.</span></span>
29. <span data-ttu-id="4fb2f-136">No campo **AggregateFunction**, selecione **Soma**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-136">In the **AggregateFunction** field, select **Sum**.</span></span>
30. <span data-ttu-id="4fb2f-137">Selecione a guia **Agrupar por**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-137">Select the **Group by** tab.</span></span>
31. <span data-ttu-id="4fb2f-138">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-138">Select **Add**.</span></span>
32. <span data-ttu-id="4fb2f-139">Na lista, selecione um valor de **Funcionário**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-139">In the list, select a value of **Employee** .</span></span>
33. <span data-ttu-id="4fb2f-140">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-140">Select **Add**.</span></span>
34. <span data-ttu-id="4fb2f-141">Na lista, selecione um valor de **Categoria de despesa**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-141">In the list, select a value of **Expense category**.</span></span>
35. <span data-ttu-id="4fb2f-142">No campo **Campo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-142">In the **Field** field, enter or select a value.</span></span>
36. <span data-ttu-id="4fb2f-143">Selecione a guia **Ter**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-143">Select the **Having** tab.</span></span>
37. <span data-ttu-id="4fb2f-144">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-144">Select **Add**.</span></span>
38. <span data-ttu-id="4fb2f-145">Selecione **Valor da transação**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-145">Select **Transaction amount**.</span></span>
39. <span data-ttu-id="4fb2f-146">No campo **Campo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-146">In the **Field** field, enter or select a value.</span></span>
40. <span data-ttu-id="4fb2f-147">No campo **AggregateFunction**, selecione **Soma**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-147">In the **AggregateFunction** field, select **Sum**.</span></span>
41. <span data-ttu-id="4fb2f-148">No campo **Critérios**, digite `>2000`.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-148">In the **Criteria** field, type `>2000`.</span></span>
42. <span data-ttu-id="4fb2f-149">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-149">Select **OK**.</span></span>
43. <span data-ttu-id="4fb2f-150">Selecione **Teste**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-150">Select **Test**.</span></span>
44. <span data-ttu-id="4fb2f-151">No campo **Data de início da seleção do documento**, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-151">In the **Document selection starting date** field, enter a date and time.</span></span>
45. <span data-ttu-id="4fb2f-152">No campo **Data de fim da seleção do documento**, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-152">In the **Document selection ending date** field, enter a date and time.</span></span>
46. <span data-ttu-id="4fb2f-153">Selecione **Executar teste**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-153">Select **Run test**.</span></span>
47. <span data-ttu-id="4fb2f-154">No Painel de Ações, selecione **Política de auditoria**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-154">On the Action Pane, select **Audit policy**.</span></span>
48. <span data-ttu-id="4fb2f-155">Selecione **Opções adicionais**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-155">Select **Additional options**.</span></span>
49. <span data-ttu-id="4fb2f-156">No campo **Data inicial**, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-156">In the **Starting date** field, enter a date and time.</span></span>
50. <span data-ttu-id="4fb2f-157">No campo **Data final**, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-157">In the **Ending date** field, enter a date and time.</span></span>
51. <span data-ttu-id="4fb2f-158">Selecione **Lote**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-158">Select **Batch**.</span></span>
52. <span data-ttu-id="4fb2f-159">Expanda a seção **Executar em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-159">Expand the **Run in the background** section.</span></span>
53. <span data-ttu-id="4fb2f-160">Selecione **Sim** no campo **Processamento em lotes**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-160">Select **Yes** in the **Batch processing** field.</span></span>
54. <span data-ttu-id="4fb2f-161">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-161">Select **OK**.</span></span>
55. <span data-ttu-id="4fb2f-162">No Painel de Navegação, vá para **Módulos > Bancada de auditoria > Configuração > Casos de auditoria**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-162">In the navigation pane, go to **Modules > Audit workbench > Audit cases**.</span></span>
56. <span data-ttu-id="4fb2f-163">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-163">In the list, find and select the desired record.</span></span>
57. <span data-ttu-id="4fb2f-164">Expanda a seção **Associações**.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-164">Expand the **Associations** section.</span></span>
58. <span data-ttu-id="4fb2f-165">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="4fb2f-165">In the list, find and select the desired record.</span></span>

