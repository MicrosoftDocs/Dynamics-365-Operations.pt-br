---
title: "Opções de transações de ativo fixo"
description: "Este artigo descreve os métodos diferentes disponíveis para criar transações de ativo fixo."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 48364acbaa3fff4be9440256c6b337c0e2d2d9d0
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="fixed-asset-transaction-options"></a><span data-ttu-id="43189-103">Opções de transações de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="43189-103">Fixed asset transaction options</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43189-104">Este artigo descreve os métodos diferentes disponíveis para criar transações de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="43189-104">This article describes the different methods available to create fixed asset transactions.</span></span>

<span data-ttu-id="43189-105">Você pode configurar ativos fixos para integração com contas a pagar, contas a receber, Compras e contabilidade.</span><span class="sxs-lookup"><span data-stu-id="43189-105">You can set up Fixed assets for integration with Accounts payable, Accounts receivable, Procurement and sourcing, and General ledger.</span></span> <span data-ttu-id="43189-106">Também é possível transferir itens Gerenciamento de depósito para Ativos fixos caso você queira usar esses itens internamente.</span><span class="sxs-lookup"><span data-stu-id="43189-106">You can also transfer items in Inventory management to Fixed assets if you want to use those items internally.</span></span>

## <a name="accounts-payable"></a><span data-ttu-id="43189-107">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="43189-107">Accounts payable</span></span>
<span data-ttu-id="43189-108">Você pode inserir transações de ativos fixos na página Comprovante de diário.</span><span class="sxs-lookup"><span data-stu-id="43189-108">You can enter Fixed assets transactions in the Journal voucher page.</span></span> <span data-ttu-id="43189-109">Esta página pode ser aberta na página Diário de fatura.</span><span class="sxs-lookup"><span data-stu-id="43189-109">This page can be opened from the Invoice journal page.</span></span> <span data-ttu-id="43189-110">Você também pode abrir a página Comprovante de diário na página Diário de aprovação de fatura.</span><span class="sxs-lookup"><span data-stu-id="43189-110">You can also open the Journal voucher page from the Invoice approval journal page.</span></span> <span data-ttu-id="43189-111">No campo Tipo de contrapartida, selecione Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="43189-111">In the Offset account type field, select Fixed assets.</span></span> <span data-ttu-id="43189-112">Em seguida, no campo Contrapartida, selecione um número de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="43189-112">Then, in the Offset account field, select a fixed asset number.</span></span> <span data-ttu-id="43189-113">Na guia Ativos fixos, insira os valores nos campos Tipo de transação e Registro.</span><span class="sxs-lookup"><span data-stu-id="43189-113">On the Fixed assets tab, enter values in the Transaction type and Book fields.</span></span>

## <a name="accounts-receivable"></a><span data-ttu-id="43189-114">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="43189-114">Accounts receivable</span></span>
<span data-ttu-id="43189-115">Você pode inserir transações de ativos fixos na página Fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="43189-115">You can enter Fixed assets transactions in the Free text invoice page.</span></span>  <span data-ttu-id="43189-116">Na página Fatura de texto livre, na grade de linhas Fatura, selecione um item de linha.</span><span class="sxs-lookup"><span data-stu-id="43189-116">In the Free text invoice page, in the Invoice lines grid, select a line item.</span></span> <span data-ttu-id="43189-117">Clique a Guia Rápida Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="43189-117">Click the Line details FastTab.</span></span> <span data-ttu-id="43189-118">Insira o número do ativo fixo e o registro para a transação de alienação.</span><span class="sxs-lookup"><span data-stu-id="43189-118">Enter the fixed asset number and book for the disposal transaction.</span></span> <span data-ttu-id="43189-119">Na fatura de texto livre, o tipo de transação de ativo fixo é sempre Descarte - venda.</span><span class="sxs-lookup"><span data-stu-id="43189-119">For free text invoices, the fixed asset transaction type is always Disposal - sale.</span></span>

## <a name="procurement-and-sourcing"></a><span data-ttu-id="43189-120">Compras</span><span class="sxs-lookup"><span data-stu-id="43189-120">Procurement and sourcing</span></span>
<span data-ttu-id="43189-121">Você pode inserir transações de ativos fixos na página Ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="43189-121">You can enter Fixed assets transactions in the Purchase order page.</span></span> <span data-ttu-id="43189-122">) Insira as informações necessárias para criar uma ordem de compra, clique em e em OK.</span><span class="sxs-lookup"><span data-stu-id="43189-122">Enter the required information to create a purchase order, and then click OK.</span></span> <span data-ttu-id="43189-123">Na página Ordem de compra, clique na Guia Rápida Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="43189-123">In the Purchase order page, click the Line details FastTab.</span></span> <span data-ttu-id="43189-124">Em, no guia Ativos fixos, insira as informações sobre o ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="43189-124">Then, on the Fixed assets tab, enter information about the fixed asset.</span></span> 

<span data-ttu-id="43189-125">Para lançar uma transação de aquisição para um ativo fixo existente o ativo, especifique o número do ativo fixo, se o registro, e o tipo de transação.</span><span class="sxs-lookup"><span data-stu-id="43189-125">To post an acquisition transaction for an existing fixed asset, specify the fixed asset number, book, and transaction type.</span></span> <span data-ttu-id="43189-126">O ativo fixo não pode ser lançado se algumas informações está ausente.</span><span class="sxs-lookup"><span data-stu-id="43189-126">The fixed asset cannot be posted if any of this information is missing.</span></span> <span data-ttu-id="43189-127">Para lançar uma transação de aquisição para um novo ativo fixo, selecione a opção Novo ativo fixo? e, em seguida, selecione o grupo de ativos fixos ao qual o novo ativo será atribuído.</span><span class="sxs-lookup"><span data-stu-id="43189-127">To post an acquisition transaction for a new fixed asset, select the New fixed asset? option, and then select the fixed asset group to assign the new asset to.</span></span> <span data-ttu-id="43189-128">Nenhum dos campos de ativos fixos para uma linha estará disponível se o item estiver em um grupo de modelos de estoque que usa um modelo de estoque de custo padrão.</span><span class="sxs-lookup"><span data-stu-id="43189-128">However, no fixed asset fields are available for a line if the item is in an inventory model group that uses a standard cost inventory model.</span></span> <span data-ttu-id="43189-129">Além disso, as opções definidas na página Parâmetros de ativos fixos determinam se você poderá lançar transações de aquisição os módulos de compra.</span><span class="sxs-lookup"><span data-stu-id="43189-129">Additionally, the options that are defined in the Fixed assets parameters page determine whether you can post acquisition transactions from the purchasing modules.</span></span> 

<span data-ttu-id="43189-130">Quando uma ordem compra ou o diário de estoque para ativos fixos é usado para a aquisição de ativos fixos, o valor do estoque é afetado.</span><span class="sxs-lookup"><span data-stu-id="43189-130">When a purchase order or the Inventory to fixed assets journal is used to acquire fixed assets, the inventory value is affected.</span></span>

## <a name="general-ledger"></a><span data-ttu-id="43189-131">Contabilidade</span><span class="sxs-lookup"><span data-stu-id="43189-131">General ledger</span></span>
<span data-ttu-id="43189-132">Qualquer tipo de transação de ativo fixo pode ser lançado na página Diário geral.</span><span class="sxs-lookup"><span data-stu-id="43189-132">Any fixed asset transaction type can be posted in the General journal page.</span></span> <span data-ttu-id="43189-133">Você também pode usar diários de ativos fixos para lançar transações de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="43189-133">You can also use journals in Fixed assets to post fixed asset transactions.</span></span>

## <a name="options-for-entering-fixed-asset-transaction-types"></a><span data-ttu-id="43189-134">Opções para inserir tipo de transações de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="43189-134">Options for entering fixed asset transaction types</span></span>


| <span data-ttu-id="43189-135">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="43189-135">Transaction type</span></span>                    | <span data-ttu-id="43189-136">Módulo</span><span class="sxs-lookup"><span data-stu-id="43189-136">Module</span></span>                   | <span data-ttu-id="43189-137">Opções</span><span class="sxs-lookup"><span data-stu-id="43189-137">Options</span></span>                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| <span data-ttu-id="43189-138">Aquisição, ajuste de aquisição</span><span class="sxs-lookup"><span data-stu-id="43189-138">Acquisition, Acquisition adjustment</span></span> | <span data-ttu-id="43189-139">Ativos fixos</span><span class="sxs-lookup"><span data-stu-id="43189-139">Fixed assets</span></span>             | <span data-ttu-id="43189-140">Ativos fixos, estoque para ativos fixos</span><span class="sxs-lookup"><span data-stu-id="43189-140">Fixed assets, Inventory to fixed assets</span></span>   |
|                                     | <span data-ttu-id="43189-141">Contabilidade</span><span class="sxs-lookup"><span data-stu-id="43189-141">General ledger</span></span>           | <span data-ttu-id="43189-142">Diário geral</span><span class="sxs-lookup"><span data-stu-id="43189-142">General journal</span></span>                           |
|                                     | <span data-ttu-id="43189-143">Contas a Pagar</span><span class="sxs-lookup"><span data-stu-id="43189-143">Accounts payable</span></span>         | <span data-ttu-id="43189-144">Diário de fatura, diário de aprovação de faturas</span><span class="sxs-lookup"><span data-stu-id="43189-144">Invoice journal, Invoice approval journal</span></span> |
|                                     | <span data-ttu-id="43189-145">Compras</span><span class="sxs-lookup"><span data-stu-id="43189-145">Procurement and sourcing</span></span> | <span data-ttu-id="43189-146">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="43189-146">Purchase order</span></span>                            |
| <span data-ttu-id="43189-147">Depreciação</span><span class="sxs-lookup"><span data-stu-id="43189-147">Depreciation</span></span>                        | <span data-ttu-id="43189-148">Ativos fixos</span><span class="sxs-lookup"><span data-stu-id="43189-148">Fixed assets</span></span>             | <span data-ttu-id="43189-149">Ativos fixos</span><span class="sxs-lookup"><span data-stu-id="43189-149">Fixed assets</span></span>                              |
|                                     | <span data-ttu-id="43189-150">Contabilidade</span><span class="sxs-lookup"><span data-stu-id="43189-150">General ledger</span></span>           | <span data-ttu-id="43189-151">Diário geral</span><span class="sxs-lookup"><span data-stu-id="43189-151">General journal</span></span>                           |
| <span data-ttu-id="43189-152">Alienação</span><span class="sxs-lookup"><span data-stu-id="43189-152">Disposal</span></span>                            | <span data-ttu-id="43189-153">Ativos Fixos</span><span class="sxs-lookup"><span data-stu-id="43189-153">Fixed assets</span></span>             | <span data-ttu-id="43189-154">Ativos Fixos</span><span class="sxs-lookup"><span data-stu-id="43189-154">Fixed assets</span></span>                              |
| <span data-ttu-id="43189-155">** **</span><span class="sxs-lookup"><span data-stu-id="43189-155">** **</span></span>                               | <span data-ttu-id="43189-156">Contabilidade</span><span class="sxs-lookup"><span data-stu-id="43189-156">General ledger</span></span>           | <span data-ttu-id="43189-157">Diário geral</span><span class="sxs-lookup"><span data-stu-id="43189-157">General journal</span></span>                           |
| <span data-ttu-id="43189-158">** **</span><span class="sxs-lookup"><span data-stu-id="43189-158">** **</span></span>                               | <span data-ttu-id="43189-159">Contas a Receber</span><span class="sxs-lookup"><span data-stu-id="43189-159">Accounts receivable</span></span>      | <span data-ttu-id="43189-160">Fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="43189-160">Free text invoice</span></span>                         |



<span data-ttu-id="43189-161">Para obter mais informações, consulte [Integração de ativos fixos](fixed-asset-integration.md).</span><span class="sxs-lookup"><span data-stu-id="43189-161">For more information, see [Fixed assets integration](fixed-asset-integration.md).</span></span>




