---
title: Solucionar problemas de criação de carga e remessas
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com a criação de cargas e remessas no Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: c7dc9cc9de4d5089d497c36759931669ee2e9e55
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259497"
---
# <a name="troubleshoot-load-building-and-shipments"></a><span data-ttu-id="85f45-103">Solucionar problemas de criação de carga e remessas</span><span class="sxs-lookup"><span data-stu-id="85f45-103">Troubleshoot load building and shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="85f45-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com a criação de cargas e remessas no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="85f45-104">This topic describes how to fix common issues that you might encounter while you work with load building and shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a><span data-ttu-id="85f45-105">Recebo a seguinte mensagem de erro: "Não é possível criar uma linha de carga para esta linha da ordem porque ela contém dimensões de estoque que são inválidas..."</span><span class="sxs-lookup"><span data-stu-id="85f45-105">I receive the following error message: "You can't create a load line for this order line because it contains inventory dimensions that are invalid..."</span></span>

### <a name="issue-description"></a><span data-ttu-id="85f45-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-106">Issue description</span></span>

<span data-ttu-id="85f45-107">Você recebe a seguinte mensagem de erro ao tentar liberar uma ordem de devolução para o depósito:</span><span class="sxs-lookup"><span data-stu-id="85f45-107">You receive the following error message when you try to release a return sales order to the warehouse:</span></span>

> <span data-ttu-id="85f45-108">Não é possível criar uma linha de carga para esta linha da ordem porque ela contém dimensões de estoque que são inválidas.</span><span class="sxs-lookup"><span data-stu-id="85f45-108">You can't create a load line for this order line because it contains inventory dimensions that are invalid.</span></span> <span data-ttu-id="85f45-109">Você não pode fazer referência às dimensões de estoque localizadas abaixo da dimensão do local na hierarquia de reserva.</span><span class="sxs-lookup"><span data-stu-id="85f45-109">You can't reference inventory dimensions that are located below the location dimension in the reservation hierarchy.</span></span> <span data-ttu-id="85f45-110">Remova as dimensões inválidas da linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="85f45-110">Remove the invalid dimensions from the order line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85f45-111">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-111">Issue resolution</span></span>

<span data-ttu-id="85f45-112">Infelizmente, o produto não oferece suporte ao processamento de carga para um processo de devolução de venda.</span><span class="sxs-lookup"><span data-stu-id="85f45-112">Unfortunately, the product doesn't support load processing for a sales return process.</span></span> <span data-ttu-id="85f45-113">Portanto, você não pode liberar a ordem de venda de devolução para o depósito.</span><span class="sxs-lookup"><span data-stu-id="85f45-113">Therefore, you can't release the return sales order to the warehouse.</span></span>

<span data-ttu-id="85f45-114">Em transações de ordens de venda, você não pode fazer referência a dimensões de estoque localizadas abaixo da dimensão do **local** na hierarquia de reserva.</span><span class="sxs-lookup"><span data-stu-id="85f45-114">On sales order transactions, you can't reference inventory dimensions that are located below the **Location** dimension in the reservation hierarchy.</span></span> <span data-ttu-id="85f45-115">A resolução consiste em remover as dimensões inválidas da linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="85f45-115">The resolution is to remove the invalid dimensions from the order line.</span></span>

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a><span data-ttu-id="85f45-116">Recebo a seguinte mensagem de erro: "Uma das linhas já está carregada.</span><span class="sxs-lookup"><span data-stu-id="85f45-116">I receive the following error message: "One of the lines is already on a load.</span></span> <span data-ttu-id="85f45-117">Não foi possível liberar para o depósito."</span><span class="sxs-lookup"><span data-stu-id="85f45-117">Unable to release to warehouse."</span></span>

### <a name="issue-description"></a><span data-ttu-id="85f45-118">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-118">Issue description</span></span>

<span data-ttu-id="85f45-119">Se você criar cargas manualmente ou configurar o processo de forma que as cargas já sejam criadas antes que a entrada da linha da ordem de vendas ocorra, a suposição é que a liberação subsequente será feita manualmente e que a rota e a classificação da carga serão usadas.</span><span class="sxs-lookup"><span data-stu-id="85f45-119">If you manually create loads, or if you set up the process so that loads are already created before sales order line entry occurs, the assumption is that the subsequent release will be done manually, and that the route and rating from the load will be used.</span></span>

<span data-ttu-id="85f45-120">Em outro cenário possível, você está tentando fazer uma liberação automática para o depósito, mas houve falha no processo de ciclo durante a criação do trabalho.</span><span class="sxs-lookup"><span data-stu-id="85f45-120">In another possible scenario, you're trying to do an automatic release to the warehouse, but the wave process failed to create work.</span></span> <span data-ttu-id="85f45-121">Portanto, uma remessa ou carga aberta ainda será criada.</span><span class="sxs-lookup"><span data-stu-id="85f45-121">Therefore, an open shipment or load is still created.</span></span> <span data-ttu-id="85f45-122">Essa remessa ou carga aberta bloqueia as tentativas subsequentes de liberar automaticamente a ordem até que você exclua a remessa ou carga aberta ou reprocesse manualmente o ciclo.</span><span class="sxs-lookup"><span data-stu-id="85f45-122">This open shipment or load then blocks subsequent attempts to automatically release the order until you either delete the open shipment or load, or manually reprocess the wave.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85f45-123">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-123">Issue resolution</span></span>

<span data-ttu-id="85f45-124">É possível liberar na página de ordem de venda ou a liberação automática pode ser feita na página de liberação de ordem de venda, somente se não houver carga antes da liberação para o depósito.</span><span class="sxs-lookup"><span data-stu-id="85f45-124">You can release from the sales order page, or automatic release can be done from the release sales order page, only if no load exists before the release to the warehouse.</span></span> <span data-ttu-id="85f45-125">A carga será criada automaticamente após o processamento da onda.</span><span class="sxs-lookup"><span data-stu-id="85f45-125">The load will automatically be created after the wave is processed.</span></span>

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a><span data-ttu-id="85f45-126">Recebo a seguinte mensagem de erro: "A correção da nota de entrega não pode ser processada.</span><span class="sxs-lookup"><span data-stu-id="85f45-126">I receive the following error message: "The delivery note correction can't be processed.</span></span> <span data-ttu-id="85f45-127">A nota de entrega contém apenas itens que estão sujeitos a processos de gerenciamento de depósito, uma vez que eles não são compatíveis com a correção de nota de entrega."</span><span class="sxs-lookup"><span data-stu-id="85f45-127">The delivery note only contains items that are subject to warehouse management processes, as these are not supported by Delivery Note correction."</span></span>

### <a name="issue-description"></a><span data-ttu-id="85f45-128">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-128">Issue description</span></span>

<span data-ttu-id="85f45-129">Depois de postar uma nota de entrega, você não poderá cancelá-la, porque o botão **Cancelar** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="85f45-129">After you post a delivery note, you can't cancel it, because the **Cancel** button is unavailable.</span></span> <span data-ttu-id="85f45-130">Você também não poderá corrigir a nota de entrega.</span><span class="sxs-lookup"><span data-stu-id="85f45-130">You also can't correct the delivery note.</span></span> <span data-ttu-id="85f45-131">Se você tentar, receberá esta mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="85f45-131">If you try, you receive this error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85f45-132">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-132">Issue resolution</span></span>

<span data-ttu-id="85f45-133">Para corrigir guias de remessa lançadas para itens habilitados para gerenciamento avançado de depósito (WMS), você deve fazer o lançamento da carga, não diretamente usando a ordem.</span><span class="sxs-lookup"><span data-stu-id="85f45-133">To correct posted packing slips for items that are enabled for advanced warehouse management (WMS), you must do the posting from the load, not directly from the order.</span></span>

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a><span data-ttu-id="85f45-134">Como posso criar trabalho usando cargas de saída em vez de ciclos?</span><span class="sxs-lookup"><span data-stu-id="85f45-134">How can I create work from outbound loads instead of waves?</span></span>

### <a name="issue-description"></a><span data-ttu-id="85f45-135">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-135">Issue description</span></span>

<span data-ttu-id="85f45-136">Aqui está uma maneira de reproduzir esse problema.</span><span class="sxs-lookup"><span data-stu-id="85f45-136">Here is one way to reproduce this issue.</span></span>

1. <span data-ttu-id="85f45-137">Crie uma carga de saída usando uma ordem de venda ou ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="85f45-137">Create an outbound load by using a sales order or transfer order.</span></span>
2. <span data-ttu-id="85f45-138">Libere a carga para o depósito.</span><span class="sxs-lookup"><span data-stu-id="85f45-138">Release the load to the warehouse.</span></span>
3. <span data-ttu-id="85f45-139">Observe que nenhum trabalho de separação foi gerado ainda.</span><span class="sxs-lookup"><span data-stu-id="85f45-139">Notice that no picking work has yet been generated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85f45-140">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-140">Issue resolution</span></span>

<span data-ttu-id="85f45-141">Se o trabalho deve ser gerado imediatamente quando a carga é liberada, você deve configurar o modelo de ciclo adequadamente.</span><span class="sxs-lookup"><span data-stu-id="85f45-141">If work must be generated immediately when the load is released, you must configure the wave template accordingly.</span></span> <span data-ttu-id="85f45-142">No modelo de ciclo, defina as seguintes opções como *Sim*:</span><span class="sxs-lookup"><span data-stu-id="85f45-142">On the wave template, set the following options to *Yes*:</span></span>

- <span data-ttu-id="85f45-143">Automatizar criação da onda</span><span class="sxs-lookup"><span data-stu-id="85f45-143">Automate wave creation</span></span>
- <span data-ttu-id="85f45-144">Processar onda na liberação para o depósito</span><span class="sxs-lookup"><span data-stu-id="85f45-144">Process wave at release to warehouse</span></span>
- <span data-ttu-id="85f45-145">Automatizar liberação da onda</span><span class="sxs-lookup"><span data-stu-id="85f45-145">Automate wave release</span></span>

## <a name="i-cant-re-release-a-partially-shipped-load"></a><span data-ttu-id="85f45-146">Não consigo liberar de novo uma carga parcialmente enviada.</span><span class="sxs-lookup"><span data-stu-id="85f45-146">I can't re-release a partially shipped load.</span></span>

### <a name="issue-description"></a><span data-ttu-id="85f45-147">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-147">Issue description</span></span>

<span data-ttu-id="85f45-148">Não é possível liberar uma carga parcialmente enviada para o depósito.</span><span class="sxs-lookup"><span data-stu-id="85f45-148">You can't release a partially shipped load to the warehouse.</span></span> <span data-ttu-id="85f45-149">Quando você realiza a liberação para o depósito, uma mensagem "Operação concluída" aparece, mas nada acontece e nenhum trabalho é criado para a quantidade restante.</span><span class="sxs-lookup"><span data-stu-id="85f45-149">When you do the release to the warehouse, an "Operation complete" message appears, but nothing happens, and no work is created for the remaining quantity.</span></span> <span data-ttu-id="85f45-150">Esse problema ocorre quando você usa a funcionalidade de carregamento de transporte e há uma reserva incompleta.</span><span class="sxs-lookup"><span data-stu-id="85f45-150">This issue occurs when you use transport load functionality and there is an incomplete reservation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="85f45-151">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="85f45-151">Issue resolution</span></span>

<span data-ttu-id="85f45-152">O [problema do KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Cargas parcialmente enviadas podem ser colocadas em ciclo e processadas de novo") foi corrigido na [versão 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span><span class="sxs-lookup"><span data-stu-id="85f45-152">[KB issue 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Partially shipped loads can be re-waved and re-processed") is fixed in [release 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]