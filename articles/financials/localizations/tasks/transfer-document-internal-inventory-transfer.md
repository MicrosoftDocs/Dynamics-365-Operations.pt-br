--- 
title: "Gerar um documento de transferência para uma transferência interna de estoque"
description: "Este procedimento mostra como criar documentos de transferência para a movimentação de mercadorias em uma empresa."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 699f7562f3b3a91f6544f85b892a55d371f4137f
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="generate-a-transfer-document-for-an-internal-inventory-transfer"></a><span data-ttu-id="15c1a-103">Gerar um documento de transferência para uma transferência interna de estoque</span><span class="sxs-lookup"><span data-stu-id="15c1a-103">Generate a transfer document for an internal inventory transfer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="15c1a-104">Este procedimento mostra como criar documentos de transferência para a movimentação de mercadorias em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="15c1a-104">This procedure shows how to create transfer documents for goods movement inside a company.</span></span> <span data-ttu-id="15c1a-105">Este procedimento está disponível somente para entidades legais com um endereço principal na Lituânia.</span><span class="sxs-lookup"><span data-stu-id="15c1a-105">This procedure is only available for legal entities with a primary address in Lithuania.</span></span> <span data-ttu-id="15c1a-106">O procedimento foi criado usando a empresa de dados de demonstração DEMF com endereço principal na Lituânia.</span><span class="sxs-lookup"><span data-stu-id="15c1a-106">The procedure was created using the demo data company DEMF with a primary address in Lithuania.</span></span> <span data-ttu-id="15c1a-107">Antes de concluir este procedimento, você deve concluir o procedimento "Configurar documentos de transferência para a movimentação de mercadorias em uma empresa".</span><span class="sxs-lookup"><span data-stu-id="15c1a-107">Before you can complete this procedure, you must complete the “Set up transfer documents for goods movement inside a company” procedure.</span></span> <span data-ttu-id="15c1a-108">Este procedimento é destinado a contadores de estoque.</span><span class="sxs-lookup"><span data-stu-id="15c1a-108">This procedure is intended for inventory accountants.</span></span> <span data-ttu-id="15c1a-109">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="15c1a-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-transfer-order"></a><span data-ttu-id="15c1a-110">Criar uma ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="15c1a-110">Create a transfer order</span></span>
1. <span data-ttu-id="15c1a-111">Vá para Gerenciamento de estoque > Ordens de entrada > Ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="15c1a-111">Go to Inventory management > Inbound orders > Transfer order.</span></span>
2. <span data-ttu-id="15c1a-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="15c1a-112">Click New.</span></span>
3. <span data-ttu-id="15c1a-113">No campo Depósito de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-113">In the From warehouse field, enter or select a value.</span></span>
4. <span data-ttu-id="15c1a-114">No campo Depósito de destino, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-114">In the To warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="15c1a-115">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="15c1a-115">Click Add.</span></span>
6. <span data-ttu-id="15c1a-116">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="15c1a-116">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="15c1a-117">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-117">In the Item number field, enter or select a value.</span></span>

## <a name="enter-transportation-details-for-the-transfer-order"></a><span data-ttu-id="15c1a-118">Inserir detalhes de transporte da ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="15c1a-118">Enter transportation details for the transfer order</span></span>
1. <span data-ttu-id="15c1a-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="15c1a-119">Click Save.</span></span>
2. <span data-ttu-id="15c1a-120">No Painel de Ação, clique em Remessa.</span><span class="sxs-lookup"><span data-stu-id="15c1a-120">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="15c1a-121">Clique em Detalhes de Transporte.</span><span class="sxs-lookup"><span data-stu-id="15c1a-121">Click Transportation details.</span></span>
4. <span data-ttu-id="15c1a-122">Selecione Sim no campo Imprimir detalhes de transporte.</span><span class="sxs-lookup"><span data-stu-id="15c1a-122">Select Yes in the Print transportation details field.</span></span>
5. <span data-ttu-id="15c1a-123">No campo Mercadorias emitidas por, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-123">In the Goods issued by field, enter or select a value.</span></span>
6. <span data-ttu-id="15c1a-124">No campo Pacote, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-124">In the Package field, type a value.</span></span>
7. <span data-ttu-id="15c1a-125">No campo Nível de risco da carga, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-125">In the Risk level of the load field, type a value.</span></span>
8. <span data-ttu-id="15c1a-126">No campo Transportadora, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-126">In the Carrier field, enter or select a value.</span></span>
9. <span data-ttu-id="15c1a-127">No campo Modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-127">In the Model field, enter or select a value.</span></span>
10. <span data-ttu-id="15c1a-128">No campo Número de registro, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-128">In the Registration number field, type a value.</span></span>
11. <span data-ttu-id="15c1a-129">No campo Número de registro da carroceria, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-129">In the Trailer registration number field, type a value.</span></span>
12. <span data-ttu-id="15c1a-130">No campo Motorista, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-130">In the Driver field, enter or select a value.</span></span>
13. <span data-ttu-id="15c1a-131">No campo Nome do motorista, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-131">In the Driver name field, type a value.</span></span>
14. <span data-ttu-id="15c1a-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="15c1a-132">Click Save.</span></span>
15. <span data-ttu-id="15c1a-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="15c1a-133">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a><span data-ttu-id="15c1a-134">Exibir a guia de remessa da ordem transferência não lançada</span><span class="sxs-lookup"><span data-stu-id="15c1a-134">View the packing slip for the unposted transfer order</span></span>
1. <span data-ttu-id="15c1a-135">Clique em Guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="15c1a-135">Click Packing slip.</span></span>
2. <span data-ttu-id="15c1a-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="15c1a-136">Click OK.</span></span>
3. <span data-ttu-id="15c1a-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="15c1a-137">Close the page.</span></span>

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a><span data-ttu-id="15c1a-138">Exibir a guia de remessa da ordem transferência lançada</span><span class="sxs-lookup"><span data-stu-id="15c1a-138">View the packing slip for the posted transfer order</span></span>
1. <span data-ttu-id="15c1a-139">No Painel de Ação, clique em Ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="15c1a-139">On the Action Pane, click Transfer order.</span></span>
2. <span data-ttu-id="15c1a-140">No Painel de Ação, clique em Remessa.</span><span class="sxs-lookup"><span data-stu-id="15c1a-140">On the Action Pane, click Ship.</span></span>
3. <span data-ttu-id="15c1a-141">Clique em Remeter ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="15c1a-141">Click Ship transfer order.</span></span>
4. <span data-ttu-id="15c1a-142">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="15c1a-142">Click the General tab.</span></span>
5. <span data-ttu-id="15c1a-143">No campo Atualizar, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="15c1a-143">In the Update field, select an option.</span></span>
6. <span data-ttu-id="15c1a-144">Clique na guia Visão geral.</span><span class="sxs-lookup"><span data-stu-id="15c1a-144">Click the Overview tab.</span></span>
7. <span data-ttu-id="15c1a-145">No campo Guia de remessa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="15c1a-145">In the Packing slip field, type a value.</span></span>
8. <span data-ttu-id="15c1a-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="15c1a-146">Click OK.</span></span>
9. <span data-ttu-id="15c1a-147">No Painel de Ação, clique em Remessa.</span><span class="sxs-lookup"><span data-stu-id="15c1a-147">On the Action Pane, click Ship.</span></span>
10. <span data-ttu-id="15c1a-148">Clique em Guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="15c1a-148">Click Packing slip.</span></span>
11. <span data-ttu-id="15c1a-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="15c1a-149">Click OK.</span></span>


