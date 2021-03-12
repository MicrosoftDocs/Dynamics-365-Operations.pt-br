---
title: Solucionar problemas de operações de estoque
description: Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com operações de estoque.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3a22229106753d265a90f0ef05f5ac82dc745bbd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967146"
---
# <a name="troubleshoot-inventory-operations"></a><span data-ttu-id="172cf-103">Solucionar problemas de operações de estoque</span><span class="sxs-lookup"><span data-stu-id="172cf-103">Troubleshoot inventory operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="172cf-104">Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com operações de estoque.</span><span class="sxs-lookup"><span data-stu-id="172cf-104">This topic describes how to fix issues that you might encounter while you work with inventory operations.</span></span>

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a><span data-ttu-id="172cf-105">Não consigo localizar a caixa de diálogo suspensa "Fluxo de trabalho" para diários de estoque.</span><span class="sxs-lookup"><span data-stu-id="172cf-105">I can't find the "Workflow" drop-down dialog box for inventory journals.</span></span>

### <a name="issue-description"></a><span data-ttu-id="172cf-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-106">Issue description</span></span>

<span data-ttu-id="172cf-107">Você não consegue localizar a caixa de diálogo suspensa **Fluxo de trabalho** na página do diário ou as operações de fluxo de trabalho relacionadas não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="172cf-107">You can't find the **Workflow** drop-down dialog box on the journal page, or related workflow operations aren't available.</span></span>

<span data-ttu-id="172cf-108">Esse problema pode ocorrer por três motivos, conforme descrito nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="172cf-108">This issue can occur for three reasons, as described in the following subsections.</span></span>

### <a name="issue-resolution-1"></a><span data-ttu-id="172cf-109">Resolução de problema 1</span><span class="sxs-lookup"><span data-stu-id="172cf-109">Issue resolution 1</span></span>

<span data-ttu-id="172cf-110">Se o problema se aplica a todos os usuários, ele pode estar ocorrendo porque o fluxo de trabalho de aprovação não foi atribuído ao nome de diário.</span><span class="sxs-lookup"><span data-stu-id="172cf-110">If the issue applies to all users, it might be occurring because the approval workflow hasn't been assigned to the journal name.</span></span> <span data-ttu-id="172cf-111">Para corrigir o problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="172cf-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="172cf-112">Vá para **Gerenciamento de estoque &gt; Configuração &gt; Nomes de diário &gt; Estoque**.</span><span class="sxs-lookup"><span data-stu-id="172cf-112">Go to **Inventory Management &gt; Setup &gt; Journal names &gt; Inventory**.</span></span>
1. <span data-ttu-id="172cf-113">No painel de lista, selecione um nome de diário para abrir suas configurações.</span><span class="sxs-lookup"><span data-stu-id="172cf-113">In the list pane, select a journal name to open its settings.</span></span>
1. <span data-ttu-id="172cf-114">Na FastTab **Geral**, defina a opção **Fluxo de trabalho de aprovação** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="172cf-114">On the **General** FastTab, set the **Approval workflow** option to *Yes*.</span></span> <span data-ttu-id="172cf-115">Se você for solicitado a confirmar a alteração, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="172cf-115">If you're prompted to confirm the change, select **Yes**.</span></span>
1. <span data-ttu-id="172cf-116">No campo **Fluxo de trabalho**, selecione o fluxo de trabalho que você deseja usar para o nome de diário selecionado.</span><span class="sxs-lookup"><span data-stu-id="172cf-116">In the **Workflow** field, select the workflow that you want to use for the selected journal name.</span></span>

### <a name="issue-resolution-2"></a><span data-ttu-id="172cf-117">Resolução de problema 2</span><span class="sxs-lookup"><span data-stu-id="172cf-117">Issue resolution 2</span></span>

<span data-ttu-id="172cf-118">Se o seu fluxo de trabalho usa código personalizado, podem ocorrer problemas após a atualização do sistema.</span><span class="sxs-lookup"><span data-stu-id="172cf-118">If your workflow uses customized code, issues might occur after you upgrade the system.</span></span> <span data-ttu-id="172cf-119">Por exemplo, no fluxo de trabalho do diário, o botão **Enviar** pode estar esmaecido, assim, não é possível selecioná-lo para aprovar um envio.</span><span class="sxs-lookup"><span data-stu-id="172cf-119">For example, in the journal workflow, the **Submit** button might be grayed out so you can't select it to approve a submission.</span></span>

<span data-ttu-id="172cf-120">Se o botão **Enviar** estiver esmaecido, seu fluxo de trabalho pode ter sido personalizado, o que significa que o método do fluxo de trabalho, `canSubmitToWorkflow()` em `FormDataUtil`, foi estendido.</span><span class="sxs-lookup"><span data-stu-id="172cf-120">If the **Submit** button is grayed out, your workflow might have been customized, which means the method of the workflow, `canSubmitToWorkflow()` in `FormDataUtil`, has been extended.</span></span> <span data-ttu-id="172cf-121">Para corrigir esse problema, altere a forma como você estende o método do `canSubmitToWorkflow()` para usar a estrutura no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="172cf-121">To fix this issue, change the way that you extend the method of the `canSubmitToWorkflow()` to use the structure in the following example.</span></span>

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a><span data-ttu-id="172cf-122">Resolução de problema 3</span><span class="sxs-lookup"><span data-stu-id="172cf-122">Issue resolution 3</span></span>

<span data-ttu-id="172cf-123">Se o problema se aplica somente a alguns usuários específicos, esses usuários talvez não tenham os privilégios de segurança necessários para executar operações de fluxo de trabalho em diários de estoque.</span><span class="sxs-lookup"><span data-stu-id="172cf-123">If the issue applies only to a few specific users, those users might not have the security privileges that are required to run workflow operations on inventory journals.</span></span> <span data-ttu-id="172cf-124">Verifique se cada usuário afetado tem o privilégio de segurança *Manter fluxo de trabalho do diário de estoque*.</span><span class="sxs-lookup"><span data-stu-id="172cf-124">Verify that each affected user has the *Maintain inventory journal workflow* security privilege.</span></span> <span data-ttu-id="172cf-125">Por padrão, esse privilégio é atribuído a um direito que tem o mesmo nome e esse direito é aplicado às funções *Trabalhador de depósito* e *Gerente de depósito*.</span><span class="sxs-lookup"><span data-stu-id="172cf-125">By default, this privilege is assigned to a duty that has same name, and that duty is applied to the *Warehouse worker* and *Warehouse manager* roles.</span></span>

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a><span data-ttu-id="172cf-126">Meu diário de estoque permanece no status bloqueado pelo sistema e o trabalho em lotes do fluxo de trabalho não funciona.</span><span class="sxs-lookup"><span data-stu-id="172cf-126">My inventory journal remains in system-locked status, and the workflow batch job doesn't work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="172cf-127">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-127">Issue description</span></span>

<span data-ttu-id="172cf-128">Um dos diários de estoque está bloqueado por alguma operação e não está sendo liberado.</span><span class="sxs-lookup"><span data-stu-id="172cf-128">One of your inventory journals is locked by some operation and isn't being released.</span></span> <span data-ttu-id="172cf-129">Por exemplo, se um erro desconhecido ocorrer durante o lançamento (que é uma operação de bloqueio do sistema), o diário poderá permanecer no status bloqueado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="172cf-129">For example, if an unknown error occurs during posting (which is a system lock operation), the journal might remain in system-locked status.</span></span> <span data-ttu-id="172cf-130">Nesse caso, o manipulador de itens de trabalho do fluxo de trabalho lançará um erro enquanto realiza a validação do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="172cf-130">In this case, the workflow work item handler will throw an error while it does lock validation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="172cf-131">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-131">Issue resolution</span></span>

<span data-ttu-id="172cf-132">Entre na instância do SQL Server para Supply Chain Management e verifique se **InventJournalTable.SystemBlocked** está definido como *1*.</span><span class="sxs-lookup"><span data-stu-id="172cf-132">Sign in to the SQL Server instance for Supply Chain Management, and check whether **InventJournalTable.SystemBlocked** is set to *1*.</span></span> <span data-ttu-id="172cf-133">Se estiver, verifique se o diário não deve estar no status bloqueado e redefina **InventJournalTable.SystemBlocked** como *0*.</span><span class="sxs-lookup"><span data-stu-id="172cf-133">If it is, make sure that the journal should not be in locked status, and then reset **InventJournalTable.SystemBlocked** to *0*.</span></span>

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a><span data-ttu-id="172cf-134">O fluxo de trabalho do meu diário de estoque nunca é concluído e o diário não pode ser editado ou lançado.</span><span class="sxs-lookup"><span data-stu-id="172cf-134">My inventory journal workflow is never completed, and the journal can't be edited or posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="172cf-135">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-135">Issue description</span></span>

<span data-ttu-id="172cf-136">Após o envio de um fluxo de trabalho de aprovação de diário, o processamento do fluxo de trabalho para de responder e não é possível editar ou processar os diários.</span><span class="sxs-lookup"><span data-stu-id="172cf-136">After you submit a journal approval workflow, workflow processing stops responding, and you can't edit or process your journals.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="172cf-137">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-137">Issue resolution</span></span>

<span data-ttu-id="172cf-138">Há vários motivos pelos quais o processamento do fluxo de trabalho pode não ser concluído.</span><span class="sxs-lookup"><span data-stu-id="172cf-138">There are several reasons why workflow processing might not be completed.</span></span> <span data-ttu-id="172cf-139">Verifique se há os seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="172cf-139">Check for the following issues:</span></span>

- <span data-ttu-id="172cf-140">Vá para **Gerenciamento de estoque &gt; Configuração &gt; Fluxos de trabalho de gerenciamento de estoque** e revise a configuração do fluxo de trabalho afetado.</span><span class="sxs-lookup"><span data-stu-id="172cf-140">Go to **Inventory management &gt; Setup &gt; Inventory management workflows**, and review the configuration of the affected workflow.</span></span> <span data-ttu-id="172cf-141">Para obter mais informações, consulte [Fluxos de trabalho de aprovação de diário de estoque](inventory-journal-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="172cf-141">For more information, see [Inventory journal approval workflows](inventory-journal-workflow.md).</span></span>
- <span data-ttu-id="172cf-142">O fluxo de trabalho pode estar encontrando uma exceção ou um erro.</span><span class="sxs-lookup"><span data-stu-id="172cf-142">The workflow might be encountering an exception or error.</span></span> <span data-ttu-id="172cf-143">Analise o histórico do item de trabalho do fluxo de trabalho afetado para ver se ele inclui um erro de aplicativo que encerra o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="172cf-143">Review the work item history of the affected workflow to see whether it includes an application error that terminates the workflow.</span></span>
- <span data-ttu-id="172cf-144">O diário de estoque pode ser atualizado ou editado somente se for aprovado.</span><span class="sxs-lookup"><span data-stu-id="172cf-144">The inventory journal can be updated or edited only if it's approved.</span></span> <span data-ttu-id="172cf-145">Se o cancelamento estiver ativo, você poderá tentar cancelar o diário.</span><span class="sxs-lookup"><span data-stu-id="172cf-145">If recall is active, you can try to recall the journal.</span></span> <span data-ttu-id="172cf-146">A execução do trabalho em lotes do fluxo de trabalho pode ser suspensa por vários motivos.</span><span class="sxs-lookup"><span data-stu-id="172cf-146">Execution of the workflow batch job might be suspended for multiple reasons.</span></span> <span data-ttu-id="172cf-147">Alguns desses motivos podem ser causados pelo problema de estrutura do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="172cf-147">Some of these reasons might be caused by the workflow framework issue.</span></span>

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a><span data-ttu-id="172cf-148">As condições de fluxo de trabalho do diário de estoque se aplicam apenas no nível do diário, não no nível da linha</span><span class="sxs-lookup"><span data-stu-id="172cf-148">Inventory journal workflow conditions apply only at the journal level, not at the line level</span></span>

### <a name="issue-description"></a><span data-ttu-id="172cf-149">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-149">Issue description</span></span>

<span data-ttu-id="172cf-150">Você pode enfrentar esse problema se, por exemplo, tentar configurar uma condição de fluxo de trabalho do diário de estoque no valor de custo.</span><span class="sxs-lookup"><span data-stu-id="172cf-150">You might experience this issue if, for example, you try to set up an inventory journal workflow condition on the cost amount.</span></span> <span data-ttu-id="172cf-151">Configure a condição de forma que a etapa 1 seja executada apenas quando o valor de custo for menor do que 100.</span><span class="sxs-lookup"><span data-stu-id="172cf-151">You set up the condition so that step 1 is run only when the cost amount is less than 100.</span></span> <span data-ttu-id="172cf-152">Depois, configure outra condição de forma que a etapa 2 seja executada apenas quando o valor de custo for maior do que ou igual a 100.</span><span class="sxs-lookup"><span data-stu-id="172cf-152">You then set up another condition so that step 2 is run only when the cost amount is more than or equal to 100.</span></span> <span data-ttu-id="172cf-153">Então, quando o fluxo de trabalho for executado, seu histórico mostrará somente uma linha, e a primeira condição será sempre avaliada como *verdadeira*, independentemente do valor enviado.</span><span class="sxs-lookup"><span data-stu-id="172cf-153">Then, when the workflow is run, the workflow history shows only one line, and the first condition is always evaluated as *true*, regardless of the value that is submitted.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="172cf-154">Solução alternativa do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-154">Issue workaround</span></span>

<span data-ttu-id="172cf-155">Na versão atual, as condições de fluxo de trabalho de estoque se aplicam apenas no nível do diário, não no nível da linha.</span><span class="sxs-lookup"><span data-stu-id="172cf-155">In the current release, inventory workflow conditions apply only at the journal level, not at the line level.</span></span> <span data-ttu-id="172cf-156">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="172cf-156">This behavior is by design.</span></span> <span data-ttu-id="172cf-157">É recomendável definir seus critérios de condição somente em atributos no nível do diário.</span><span class="sxs-lookup"><span data-stu-id="172cf-157">We recommend that you set your condition criteria only on journal-level attributes.</span></span>

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a><span data-ttu-id="172cf-158">O painel de filtros na página Lista disponível não filtra os resultados conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="172cf-158">The filter pane on the On-hand list page doesn't filter results as I expect.</span></span>

### <a name="issue-description"></a><span data-ttu-id="172cf-159">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-159">Issue description</span></span>

<span data-ttu-id="172cf-160">Os filtros no painel de filtros na página **Lista disponível** não filtram os resultados conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="172cf-160">The filters in the filter pane on the **On-hand list** page don't filter results as you expect.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="172cf-161">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-161">Issue resolution</span></span>

<span data-ttu-id="172cf-162">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="172cf-162">This behavior is by design.</span></span>

<span data-ttu-id="172cf-163">A página  **Lista disponível**  é montada com base em uma tabela de estoque disponível detalhada que inclui todas as dimensões disponíveis.</span><span class="sxs-lookup"><span data-stu-id="172cf-163">The **On-hand list** page is assembled from a detailed on-hand inventory table that includes all available dimensions.</span></span> <span data-ttu-id="172cf-164">No entanto, a lista nesta página é um resumo.</span><span class="sxs-lookup"><span data-stu-id="172cf-164">However, the list on this page is a summary.</span></span> <span data-ttu-id="172cf-165">Portanto, é possível combinar linhas da tabela de origem, agregando valores de acordo com as dimensões que são mostradas.</span><span class="sxs-lookup"><span data-stu-id="172cf-165">Therefore, it might combine rows from the source table by aggregating values according to the dimensions that are shown.</span></span>

<span data-ttu-id="172cf-166">Os filtros configurados no painel de filtros se aplicam à tabela de origem, não à lista agregada.</span><span class="sxs-lookup"><span data-stu-id="172cf-166">Filters that are set up in the filter pane apply to the source table, not to the aggregated list.</span></span> <span data-ttu-id="172cf-167">Às vezes, esse comportamento pode produzir resultados inesperados, como mostrado [nestes exemplos](inventory-on-hand-list.md#examples).</span><span class="sxs-lookup"><span data-stu-id="172cf-167">This behavior can sometimes produce unexpected results, as shown in [these examples](inventory-on-hand-list.md#examples).</span></span>

<span data-ttu-id="172cf-168">No entanto, os [filtros fornecidos na grade](inventory-on-hand-list.md#grid-filters) *se aplicam*  à lista agregada.</span><span class="sxs-lookup"><span data-stu-id="172cf-168">However, the [filters that are provided in the grid](inventory-on-hand-list.md#grid-filters) *do* apply to the aggregated list.</span></span> <span data-ttu-id="172cf-169">Esses filtros incluem filtro rápido na parte superior da grade e o filtro para cada título de coluna.</span><span class="sxs-lookup"><span data-stu-id="172cf-169">These filters include both the QuickFilter at the top of the grid and the filter for each column heading.</span></span>

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a><span data-ttu-id="172cf-170">A unidade e a quantidade de unidades não estão funcionando corretamente no diário de estoque.</span><span class="sxs-lookup"><span data-stu-id="172cf-170">The unit and unit quantity aren't working correctly in the inventory journal.</span></span>

### <a name="issue-description"></a><span data-ttu-id="172cf-171">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-171">Issue description</span></span>

<span data-ttu-id="172cf-172">Você pode encontrar um ou ambos os problemas a seguir ao trabalhar com unidades e quantidades em um diário de estoque:</span><span class="sxs-lookup"><span data-stu-id="172cf-172">You might encounter one or both of the following issues when you work with units and quantities in an inventory journal:</span></span>

- <span data-ttu-id="172cf-173">Você não vê unidades ou quantidades de unidades no diário de estoque enquanto uma unidade de conversão é configurada para o produto liberado e você não consegue alterar a unidade no diário de estoque.</span><span class="sxs-lookup"><span data-stu-id="172cf-173">You don't see units or unit quantities in the inventory journal while a unit of conversion is set up for the released product, and you can't change the unit in the inventory journal.</span></span>
- <span data-ttu-id="172cf-174">Você vê os campos **Quantidade** e **Unidade** no diário de estoque, mas não vê o campo **Quantidade de unidades**.</span><span class="sxs-lookup"><span data-stu-id="172cf-174">You see the **Quantity** and **Unit** fields in the inventory journal, but you don't see the **Unit quantity** field.</span></span> <span data-ttu-id="172cf-175">Se você alterar a unidade, inserir uma quantidade e lançar o diário, ele ainda mostrará a unidade de medida original para essa quantidade.</span><span class="sxs-lookup"><span data-stu-id="172cf-175">If you change the unit, enter a quantity, and post the journal, the journal still shows the original unit of measurement for that quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="172cf-176">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-176">Issue resolution</span></span>

<span data-ttu-id="172cf-177">Para corrigir esse problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="172cf-177">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="172cf-178">No espaço de trabalho **Gerenciamento de recursos**, verifique se o recurso *Usar unidade de medida e quantidade de unidades em diários de estoque* está ativado.</span><span class="sxs-lookup"><span data-stu-id="172cf-178">In the **Feature management** workspace, make sure that the *Using unit of measure and unit quantity in inventory journals* feature is turned on.</span></span> <span data-ttu-id="172cf-179">Esse recurso adiciona os campos **Unidade** e **Quantidade de unidades** ao diário.</span><span class="sxs-lookup"><span data-stu-id="172cf-179">This feature adds the **Unit** and **Unit quantity** fields to the journal.</span></span>
1. <span data-ttu-id="172cf-180">Após a ativação do recurso, use os campos **Quantidade**, **Quantidade de unidades** e **Unidade** da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="172cf-180">After the feature is turned on, use the **Quantity**, **Unit quantity**, and **Unit** fields in the following way:</span></span>

    - <span data-ttu-id="172cf-181">**Quantidade** – Especifique a quantidade usando a unidade padrão definida para o produto liberado.</span><span class="sxs-lookup"><span data-stu-id="172cf-181">**Quantity** – Specify the quantity by using the default unit that is defined for the released product.</span></span> <span data-ttu-id="172cf-182">No entanto, a unidade padrão em si não é mostrada aqui.</span><span class="sxs-lookup"><span data-stu-id="172cf-182">However, the default unit itself isn't shown here.</span></span> <span data-ttu-id="172cf-183">Se uma conversão for configurada entre a unidade padrão e a unidade selecionada no campo **Unidade**, o campo **Quantidade** será atualizado automaticamente com base nas seleções nos campos **Quantidade de unidades** e **Unidade**.</span><span class="sxs-lookup"><span data-stu-id="172cf-183">If a conversion is set up between the default unit and the unit that is selected in the **Unit** field, the **Quantity** field is automatically updated, based on the selections in the **Unit quantity** and **Unit** fields.</span></span>
    - <span data-ttu-id="172cf-184">**Quantidade de unidades** – Especifique a quantidade usando a unidade selecionada no campo **Unidade**.</span><span class="sxs-lookup"><span data-stu-id="172cf-184">**Unit quantity** – Specify the quantity by using the unit that is selected in the **Unit** field.</span></span>
    - <span data-ttu-id="172cf-185">**Unidade** – Selecione a unidade a ser aplicada ao valor no campo **Quantidade de unidades**.</span><span class="sxs-lookup"><span data-stu-id="172cf-185">**Unit** – Select the unit to apply to the value in the **Unit quantity** field.</span></span>

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a><span data-ttu-id="172cf-186">Recebo a seguinte mensagem de erro: "O número máximo de decimais para a unidade de manutenção de estoque é 0."</span><span class="sxs-lookup"><span data-stu-id="172cf-186">I receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

### <a name="issue-description"></a><span data-ttu-id="172cf-187">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-187">Issue description</span></span>

<span data-ttu-id="172cf-188">Ao tentar lançar uma transação de estoque ou uma reserva de estoque, você recebe a seguinte mensagem de erro: "O número máximo de decimais para a unidade de manutenção de estoque é 0."</span><span class="sxs-lookup"><span data-stu-id="172cf-188">When you try to post an inventory transaction or an inventory reservation, you receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

<span data-ttu-id="172cf-189">Esse problema ocorre quando a quantidade da transação de estoque é especificada como um valor decimal que está abaixo do nível de precisão ao qual o campo oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="172cf-189">This issue occurs when the inventory transaction quantity is specified as a decimal value that is below the level of precision that the field supports.</span></span> <span data-ttu-id="172cf-190">Por exemplo, uma quantidade de *0,5* foi especificada para uma transação de estoque, mas só há suporte para quantidades inteiras.</span><span class="sxs-lookup"><span data-stu-id="172cf-190">For example, a quantity of *0.5* has been specified for an inventory transaction, but only integer quantities are supported.</span></span> <span data-ttu-id="172cf-191">Portanto, o valor deve ser *1* em vez de *0,5*.</span><span class="sxs-lookup"><span data-stu-id="172cf-191">Therefore, the value should be *1* instead of *0.5*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="172cf-192">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="172cf-192">Issue resolution</span></span>

1. <span data-ttu-id="172cf-193">Execute o script a seguir na sua instância do SQL Server para arredondar quantidades nas transações de estoque.</span><span class="sxs-lookup"><span data-stu-id="172cf-193">Run the following script on your SQL Server instance to round quantities in the inventory transactions.</span></span> <span data-ttu-id="172cf-194">Esse script corrigirá os valores na tabela **inventTrans**.</span><span class="sxs-lookup"><span data-stu-id="172cf-194">This script will correct values in the **inventTrans** table.</span></span>

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. <span data-ttu-id="172cf-195">Execute uma verificação de consistência disponível na qual a opção **corrigir erro** esteja ativada.</span><span class="sxs-lookup"><span data-stu-id="172cf-195">Run an on-hand consistency check where the **fix error** option is turned on.</span></span> <span data-ttu-id="172cf-196">Essa verificação corrigirá os valores na tabela **inventSum**.</span><span class="sxs-lookup"><span data-stu-id="172cf-196">This check will correct values in the **inventSum** table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="172cf-197">É altamente recomendável editar o script com cuidado conforme necessário para o seu ambiente, testá-lo em um ambiente de teste e verificar os dados resultantes antes de executá-lo em um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="172cf-197">We strongly recommend that you carefully edit the script as required for your environment, test it in a test environment, and then check the resulting data before you run the script in a production environment.</span></span>
