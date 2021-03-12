---
title: Solucionar problemas de configuração do depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao configurar o Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 09b5770190fea9591f422b61ce6deedb2b9fa790
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993994"
---
# <a name="troubleshoot-warehouse-configuration"></a><span data-ttu-id="4e4d2-103">Solucionar problemas de configuração do depósito</span><span class="sxs-lookup"><span data-stu-id="4e4d2-103">Troubleshoot warehouse configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4e4d2-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao configurar o Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-104">This topic describes how to fix common issues that you might encounter while you configure Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a><span data-ttu-id="4e4d2-105">Recebo a seguinte mensagem de erro: "A placa de licença ou local não é válido."</span><span class="sxs-lookup"><span data-stu-id="4e4d2-105">I receive the following error message: "The license plate or location is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e4d2-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-106">Issue description</span></span>

<span data-ttu-id="4e4d2-107">Você recebe essa mensagem de erro ao verificar uma ID de placa de licença ou local.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-107">You receive this error message when you scan a license plate ID or location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e4d2-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-108">Issue resolution</span></span>

<span data-ttu-id="4e4d2-109">Certifique-se de que a ID da placa de licença não foi reservada por outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-109">Make sure that the license plate ID isn't reserved by something else.</span></span> <span data-ttu-id="4e4d2-110">Esse problema costumava ocorrer quando o valor que um usuário verificava no aplicativo de depósito era um local e uma ID de placa de licença válidos.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-110">This issue used to occur when the value that a user scanned in the warehouse app was both a valid location and a valid license plate ID.</span></span> <span data-ttu-id="4e4d2-111">Contudo, esse problema foi resolvido na versão 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-111">However, this issue was resolved in version 10.0.11.</span></span>

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a><span data-ttu-id="4e4d2-112">Recebo a seguinte mensagem de erro: "A placa de licença deve ser especificada para este local."</span><span class="sxs-lookup"><span data-stu-id="4e4d2-112">I receive the following error message: "License plate must be specified for this location."</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e4d2-113">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-113">Issue description</span></span>

<span data-ttu-id="4e4d2-114">Você receberá essa mensagem de erro se criar uma ordem de transferência usando um depósito habilitado para gerenciamento avançado de depósito (WMS) e, depois que o trabalho for concluído, você tenta confirmar a remessa.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-114">You receive this error message if you create a transfer order by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e4d2-115">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-115">Issue resolution</span></span>

<span data-ttu-id="4e4d2-116">O campo **Local de recebimento padrão** está em branco para um depósito de trânsito do depósito "de".</span><span class="sxs-lookup"><span data-stu-id="4e4d2-116">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="4e4d2-117">Para corrigir esse problema, especifique um local de recebimento padrão no depósito de trânsito.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-117">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="4e4d2-118">Certifique-se de que esse local seja controlado por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-118">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a><span data-ttu-id="4e4d2-119">Recebo a seguinte mensagem de erro: "Você não pode criar uma linha de modelo de trabalho para a mudança de status de estoque porque o tipo de trabalho não é válido.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-119">I receive the following error message: "You can't create a work template line for Inventory status change because the work type is not valid.</span></span> <span data-ttu-id="4e4d2-120">Selecione um tipo de trabalho diferente."</span><span class="sxs-lookup"><span data-stu-id="4e4d2-120">Select a different work type."</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e4d2-121">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-121">Issue description</span></span>

<span data-ttu-id="4e4d2-122">Para um modelo de trabalho, você não pode selecionar *Alteração do status do estoque* na coluna **Tipo de trabalho** da seção **Detalhes do modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-122">For a work template, you can't select *Inventory status change* in the **Work type** column of the **Work template details** section.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e4d2-123">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-123">Issue resolution</span></span>

<span data-ttu-id="4e4d2-124">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-124">This behavior is by design.</span></span> <span data-ttu-id="4e4d2-125">O tipo de trabalho *Alteração do status do estoque* é usado apenas por processos do sistema.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-125">The *Inventory status change* work type is used only by system processes.</span></span> <span data-ttu-id="4e4d2-126">Ele não pode ser configurado.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-126">It can't be configured.</span></span> <span data-ttu-id="4e4d2-127">Como a lista de tipos de trabalho é fixada como uma enumeração, as entradas extras não podem ser filtradas do menu suspenso **Tipo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-127">Because the list of work types is fixed as an enumeration, the extra entries can't be filtered out of the **Work type** drop-down menu.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="4e4d2-128">Recebo a seguinte mensagem de erro: "A quantidade não é válida para a unidade 1%."</span><span class="sxs-lookup"><span data-stu-id="4e4d2-128">I receive the following error message: "The Quantity is not valid for unit 1%."</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e4d2-129">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-129">Issue description</span></span>

<span data-ttu-id="4e4d2-130">A quantidade não é válida para a unidade *ea* quando há trabalhos de separação com várias placas de licença em um local.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-130">The quantity isn't valid for the *ea* unit when there is picking work that has multiple license plates in one location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e4d2-131">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-131">Issue resolution</span></span>

<span data-ttu-id="4e4d2-132">Verifique se os campos **ID do grupo de sequências de unidade** e **Conversões de unidades** no produto lançado ou na variante do produto estão definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-132">Verify that the **Unit sequence group ID** and **Unit conversions** fields on the released product or product variant are set correctly.</span></span>

<span data-ttu-id="4e4d2-133">Observe que a mensagem de erro foi melhorada na versão 10.0.15 (consulte [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span><span class="sxs-lookup"><span data-stu-id="4e4d2-133">Note that the error message has been improved in version 10.0.15 (see [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span></span> <span data-ttu-id="4e4d2-134">A nova mensagem de erro é: "A quantidade não é válida.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-134">The new error message is, "The quantity is not valid.</span></span> <span data-ttu-id="4e4d2-135">Espera-se %1 %2."</span><span class="sxs-lookup"><span data-stu-id="4e4d2-135">Expected %1 %2."</span></span>

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a><span data-ttu-id="4e4d2-136">Em diretivas de local para execução de ordem de venda, a opção de SKU múltiplo não avalia várias ações de diretiva de local.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-136">In location directives for sales order put work, the multiple SKU option doesn't evaluate multiple location directive actions.</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e4d2-137">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-137">Issue description</span></span>

<span data-ttu-id="4e4d2-138">As diretivas de local do tipo de ordem de trabalho *Ordens de venda* e do tipo de trabalho *Colocar* não avaliam várias ações da diretiva de local quando a opção **Várias SKUs** é selecionada.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-138">Location directives of the *Sales orders* work order type and the *Put* work type don't evaluate multiple location directive actions when the **Multiple SKU** option is selected.</span></span> <span data-ttu-id="4e4d2-139">Somente a primeira ação da diretiva de local é avaliada.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-139">Only the first location directive action is evaluated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e4d2-140">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-140">Issue resolution</span></span>

<span data-ttu-id="4e4d2-141">Um novo recurso, *Avaliar todas as ações para diretivas de local Várias SKUs*, foi adicionado na versão 10.0.15 (consulte [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span><span class="sxs-lookup"><span data-stu-id="4e4d2-141">A new feature, *Evaluate all actions for Multi SKU location directives*, has been added in version 10.0.15 (see [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span></span> <span data-ttu-id="4e4d2-142">Esse recurso avalia todas as ações para diretivas de local Várias SKUs.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-142">This feature evaluates all actions for multi-SKU location directives.</span></span> <span data-ttu-id="4e4d2-143">Se você precisar desse recurso, use o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-143">If you require this feature, use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn it on.</span></span>

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a><span data-ttu-id="4e4d2-144">Não consigo usar o aplicativo de depósito para fazer separação parcial.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-144">I can't use the warehouse app to do partial picking.</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e4d2-145">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-145">Issue description</span></span>

<span data-ttu-id="4e4d2-146">Em vendas e ordens de transferência, não é possível ignorar itens e fazer a separação parcial.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-146">For sales and transfer orders, you can't skip items and do partial picking.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e4d2-147">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-147">Issue resolution</span></span>

<span data-ttu-id="4e4d2-148">Na página **Itens de menu do dispositivo móvel**, para cada item de menu configurado para processar ordens de venda ou ordens de transferência, defina a opção **Permitir divisão de trabalho** na FastTab **Geral** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-148">On the **Mobile device menu items** page, for each menu item that is set up to process sales orders or transfer orders, set the **Allow splitting of work** option on the **General** FastTab to *Yes*.</span></span>

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a><span data-ttu-id="4e4d2-149">Como posso fazer uma mudança de status de estoque para trabalho de quantidade parcial?</span><span class="sxs-lookup"><span data-stu-id="4e4d2-149">How can I do an inventory status change for partial quantity work?</span></span>

### <a name="issue-description"></a><span data-ttu-id="4e4d2-150">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-150">Issue description</span></span>

<span data-ttu-id="4e4d2-151">Você deseja fazer uma mudança de status de estoque para uma quantidade parcial de um lote.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-151">You want to do an inventory status change for a partial quantity of a batch.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4e4d2-152">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="4e4d2-152">Issue resolution</span></span>

<span data-ttu-id="4e4d2-153">Para permitir que os trabalhadores façam essa mudança, é possível criar um item de menu para o aplicativo de depósito.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-153">To enable workers to make this change, you can create a menu item for the warehouse app.</span></span> <span data-ttu-id="4e4d2-154">Na página **Itens de menu do dispositivo móvel**, crie (ou edite) um item de menu que tenha as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="4e4d2-154">On the **Mobile device menu items** page, create (or edit) a menu item that has the following settings:</span></span>

- <span data-ttu-id="4e4d2-155">**Modo:** *Trabalho*</span><span class="sxs-lookup"><span data-stu-id="4e4d2-155">**Mode:** *Work*</span></span>
- <span data-ttu-id="4e4d2-156">**Usar trabalho existente:** *Não*</span><span class="sxs-lookup"><span data-stu-id="4e4d2-156">**Use existing work:** *No*</span></span>
- <span data-ttu-id="4e4d2-157">**Processo de criação de trabalho:** *Movimento*</span><span class="sxs-lookup"><span data-stu-id="4e4d2-157">**Work creation process:** *Movement*</span></span>
- <span data-ttu-id="4e4d2-158">**Exibir status do estoque:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="4e4d2-158">**Display inventory status:** *Yes*</span></span>

<span data-ttu-id="4e4d2-159">Você pode definir outros campos na página conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4e4d2-159">You can set other fields on the page as you require.</span></span>
