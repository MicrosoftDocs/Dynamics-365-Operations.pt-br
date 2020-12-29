---
title: Resolver problemas de separação e embalagem
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao separar e embalar no Microsoft Dynamics 365 Supply Chain Management.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 74854fa95837dd8a133860e2a017be4c92ff84a3
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645468"
---
# <a name="troubleshoot-picking-and-packing"></a><span data-ttu-id="3a139-103">Resolver problemas de separação e embalagem</span><span class="sxs-lookup"><span data-stu-id="3a139-103">Troubleshoot picking and packing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a139-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao separar e embalar no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3a139-104">This topic describes how to fix common issues that you might encounter while you pick and pack in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a><span data-ttu-id="3a139-105">Recebo a seguinte mensagem de erro: "O local da dimensão não pode ser deixado em branco se o número de série da dimensão estiver definido."</span><span class="sxs-lookup"><span data-stu-id="3a139-105">I receive the following error message: "Dimension location can't be left blank if dimension serial number is set."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a139-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-106">Issue description</span></span>

<span data-ttu-id="3a139-107">Você receberá essa mensagem de erro se criar uma ordem de transferência para um item de série usando um depósito habilitado para gerenciamento avançado de depósito (WMS) e, depois que o trabalho for concluído, você tenta confirmar a remessa.</span><span class="sxs-lookup"><span data-stu-id="3a139-107">You receive this error message if you create a transfer order for a serial item by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a139-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-108">Issue resolution</span></span>

<span data-ttu-id="3a139-109">O campo **Local de recebimento padrão** está em branco para um depósito de trânsito do depósito "de".</span><span class="sxs-lookup"><span data-stu-id="3a139-109">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="3a139-110">Para corrigir esse problema, especifique um local de recebimento padrão no depósito de trânsito.</span><span class="sxs-lookup"><span data-stu-id="3a139-110">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="3a139-111">Certifique-se de que esse local seja controlado por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="3a139-111">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a><span data-ttu-id="3a139-112">Recebo a seguinte mensagem de erro: "Placa de licença inválida."</span><span class="sxs-lookup"><span data-stu-id="3a139-112">I receive the following error message: "Invalid license plate."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a139-113">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-113">Issue description</span></span>

<span data-ttu-id="3a139-114">Você recebe essa mensagem de erro no aplicativo de depósito ao verificar a ID de uma placa de licença.</span><span class="sxs-lookup"><span data-stu-id="3a139-114">You receive this error message in the warehouse app when you scan a license plate ID.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a139-115">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-115">Issue resolution</span></span>

<span data-ttu-id="3a139-116">Certifique-se de que a ID de placa de licença exista na tabela de placas de licença e que os itens e quantidades na placa estejam disponíveis (em outras palavras, eles não estão bloqueados).</span><span class="sxs-lookup"><span data-stu-id="3a139-116">Make sure that the license plate ID exists in the license plates table, and that the items and quantities on the license plate are available (in other words, they aren't blocked).</span></span>

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a><span data-ttu-id="3a139-117">Recebo a seguinte mensagem de erro: "O campo 'Peso da carga' (= -%1) só pode conter números positivos.</span><span class="sxs-lookup"><span data-stu-id="3a139-117">I receive the following error message: "Field 'Load weight'(=-%1) can only contain positive numbers.</span></span> <span data-ttu-id="3a139-118">A atualização foi cancelada."</span><span class="sxs-lookup"><span data-stu-id="3a139-118">Update has been canceled."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a139-119">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-119">Issue description</span></span>

<span data-ttu-id="3a139-120">Você recebe essa mensagem de erro se houver trabalho aberto ao processar o trabalho de locais de embalagem para locais de preparo ou de locais de preparo para locais de doca.</span><span class="sxs-lookup"><span data-stu-id="3a139-120">You receive this error message if there is open work when you process work from packing locations to staging locations, or from staging locations to dock locations.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a139-121">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-121">Issue resolution</span></span>

<span data-ttu-id="3a139-122">Para corrigir esse problema, acesso **Administração do sistema \> Tarefas periódicas \> Banco de dados \> Verificação de consistência** e execute o processo para **Verificação de consistência do peso da carga do depósito**.</span><span class="sxs-lookup"><span data-stu-id="3a139-122">To fix this issue, go to **System administration \> Periodic tasks \> Database \> Consistency check**, and run the process for **Warehouse load weight consistency check**.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="3a139-123">Recebo a seguinte mensagem de erro: "A quantidade não é válida para a unidade %1."</span><span class="sxs-lookup"><span data-stu-id="3a139-123">I receive the following error message: "The quantity is not valid for unit %1."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a139-124">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-124">Issue description</span></span>

<span data-ttu-id="3a139-125">Você recebe essa mensagem de erro ao tentar executar uma *separação dividida* em vários lotes.</span><span class="sxs-lookup"><span data-stu-id="3a139-125">You receive this error message when you try to perform a *split pick* across multiple batches.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a139-126">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-126">Issue resolution</span></span>

<span data-ttu-id="3a139-127">O funcionário do depósito deve usar o processo *Separação insuficiente* no aplicativo de depósito.</span><span class="sxs-lookup"><span data-stu-id="3a139-127">The warehouse worker must use the *Short picking* process in the warehouse app.</span></span> <span data-ttu-id="3a139-128">Se você estiver tentando selecionar vários lotes do mesmo local, também pode usar a opção **Completo** no aplicativo de depósito.</span><span class="sxs-lookup"><span data-stu-id="3a139-128">If you're trying to pick multiple batches from the same location, you can also use the **Full** option in the warehouse app.</span></span>

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a><span data-ttu-id="3a139-129">Não consigo mover o estoque para um local controlado por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="3a139-129">I can't move inventory to a location that is license plate–controlled.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a139-130">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-130">Issue description</span></span>

<span data-ttu-id="3a139-131">Você não consegue reduzir as quantidades selecionadas em uma carga.</span><span class="sxs-lookup"><span data-stu-id="3a139-131">You can't reduce picked quantities on a load.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a139-132">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-132">Issue resolution</span></span>

<span data-ttu-id="3a139-133">Em versões anteriores, você não consegue reduzir as quantidades selecionadas em uma carga.</span><span class="sxs-lookup"><span data-stu-id="3a139-133">In earlier versions, you can't reduce picked quantities on a load.</span></span> <span data-ttu-id="3a139-134">Contudo, agora você pode desfazer a separação em um local controlado por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="3a139-134">However, you can now unpick to a license plate–controlled location.</span></span> <span data-ttu-id="3a139-135">Você deve especificar um valor **Local** e um valor **Placa de licença** para a linha de carga na página **Reduzir quantidade separada**.</span><span class="sxs-lookup"><span data-stu-id="3a139-135">You must specify both a **Location** value and a **License plate** value for the load line on the **Reduce picked quantity** page.</span></span>

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a><span data-ttu-id="3a139-136">Posso imprimir uma nota de entrega ou conteúdo de embalagem por depósito?</span><span class="sxs-lookup"><span data-stu-id="3a139-136">Can I print a delivery note or packing content by warehouse?</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a139-137">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-137">Issue description</span></span>

<span data-ttu-id="3a139-138">Você deseja imprimir uma nota de entrega ou conteúdo de embalagem por depósito ou local na página **Atualização de linha de modelo de auditoria de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="3a139-138">You want to print a delivery note or packing content by warehouse or site on the **Work audit template line update** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a139-139">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-139">Issue resolution</span></span>

<span data-ttu-id="3a139-140">Ao imprimir um documento usando as configurações de gerenciamento de impressão, limite o escopo (local/depósito) por meio do gerenciamento de impressão em vez de selecionar **Editar configurações de impressão** na página **Atualização de linha de modelo de auditoria de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="3a139-140">When you print a document by using Print management settings, limit the scope (site/warehouse) through Print management instead of by selecting **Edit print settings** on the **Work audit template line update** page.</span></span>

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a><span data-ttu-id="3a139-141">Não consigo cancelar uma guia de remessa depois de lançada em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="3a139-141">I can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a139-142">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-142">Issue description</span></span>

<span data-ttu-id="3a139-143">Quando os processos de separação e remessa são habilitados para WMS, você não consegue cancelar uma guia de remessa depois de lançada em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="3a139-143">When picking and shipping processes are enabled for WMS, you can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a139-144">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-144">Issue resolution</span></span>

<span data-ttu-id="3a139-145">Para corrigir guias de remessa lançadas para itens habilitados para WMS, o lançamento deve ocorrer a partir da carga, não a partir da ordem.</span><span class="sxs-lookup"><span data-stu-id="3a139-145">To correct posted packing slips for items that are enabled for WMS, the posting must occur from the load, not from the order.</span></span> <span data-ttu-id="3a139-146">A Microsoft avaliou esse problema e determinou que é uma limitação de recurso.</span><span class="sxs-lookup"><span data-stu-id="3a139-146">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="3a139-147">Em geral, uma ordem de venda que foi separada e enviada por meio de processos de gerenciamento de depósito pode ser atualizado em relação à guia de remessa a partir da carga ou remessa e do próprio documento de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="3a139-147">In general, a sales order that has been picked and shipped through warehouse management processes can be packing slip–updated from the load or shipment and the sales order document itself.</span></span> <span data-ttu-id="3a139-148">Contudo, se você atualizar a guia de remessa a partir do documento de ordem de venda, a reversão da guia de remessa ainda não poderá ser feita a partir da carga ou da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="3a139-148">However, if you packing slip–update the sales order from the sales order document, packing slip reversal still can't be done from the load or sales order.</span></span> <span data-ttu-id="3a139-149">Portanto, recomendamos que você use a guia de remessa a partir da carga.</span><span class="sxs-lookup"><span data-stu-id="3a139-149">Therefore, we recommend that you use the packing slip posting from the load.</span></span> <span data-ttu-id="3a139-150">Nesse caso, será habilitada a reversão que deve ser feita a partir da carga.</span><span class="sxs-lookup"><span data-stu-id="3a139-150">In this case, the reversal that must be done from the load will be enabled.</span></span>

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a><span data-ttu-id="3a139-151">Recebo a seguinte mensagem de erro: "Não é possível encontrar um trabalho suficiente para o cluster."</span><span class="sxs-lookup"><span data-stu-id="3a139-151">I receive the following error message: "Not enough work can be found for cluster."</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a139-152">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-152">Issue description</span></span>

<span data-ttu-id="3a139-153">Quando você usa o processo *Separação de cluster direcionada pelo sistema*, se você configurar um perfil de cluster em que, por exemplo, 10 posições podem ser separadas, o processo funciona conforme planejado quando há trabalho suficiente para separar até 10 posições.</span><span class="sxs-lookup"><span data-stu-id="3a139-153">When you use the *System directed cluster picking* process, if you configure a cluster profile where, for example, 10 positions can be picked, the process works as planned when there is enough work to pick to 10 positions.</span></span> <span data-ttu-id="3a139-154">Entretanto, se houver apenas oito posições para separar, você receberá essa mensagem de erro porque não há trabalho suficiente para um cluster.</span><span class="sxs-lookup"><span data-stu-id="3a139-154">However, if there are only eight positions to pick, you receive this error message, because there isn't enough work for one cluster.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a139-155">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a139-155">Issue resolution</span></span>

<span data-ttu-id="3a139-156">Para corrigir esse problema, edite o perfil do cluster e defina a opção **Ativar posições** como *Não*.</span><span class="sxs-lookup"><span data-stu-id="3a139-156">To fix this issue, edit the cluster profile, and set the **Activate positions** option to *No*.</span></span>
