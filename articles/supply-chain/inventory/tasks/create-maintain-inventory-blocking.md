---
title: Criar e manter um bloqueio de estoque
description: Este tópico descreve como usar um bloqueio de estoque para evitar que o estoque físico disponível seja reservado por outros documentos de origem de saída.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9aa38ca52da577fff258bb330922ad7f4044330
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956149"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="f153a-103">Criar e manter um bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="f153a-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f153a-104">Este tópico descreve como usar um bloqueio de estoque para evitar que o estoque físico disponível seja reservado por outros documentos de origem de saída.</span><span class="sxs-lookup"><span data-stu-id="f153a-104">This topic describes how to use an inventory blocking to prevent physical on-hand inventory from being reserved by other outbound source documents.</span></span> <span data-ttu-id="f153a-105">Antes de iniciar os procedimentos deste tópico, você precisa ter um item do estoque físico disponível.</span><span class="sxs-lookup"><span data-stu-id="f153a-105">Before you start the procedures in this topic, you must have an item that physical on-hand inventory is available for.</span></span>

## <a name="block-inventory"></a><span data-ttu-id="f153a-106">Bloquear estoque</span><span class="sxs-lookup"><span data-stu-id="f153a-106">Block inventory</span></span>

<span data-ttu-id="f153a-107">Para criar um registro de bloqueio de estoque para que o estoque seja bloqueado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f153a-107">To create an inventory blocking record so that inventory is blocked, follow these steps.</span></span>

1. <span data-ttu-id="f153a-108">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Bloqueio de estoque**.</span><span class="sxs-lookup"><span data-stu-id="f153a-108">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="f153a-109">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f153a-109">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f153a-110">No cabeçalho do novo registro de bloqueio, defina o campo **Número do item** como o item que você deseja bloquear e digite uma descrição.</span><span class="sxs-lookup"><span data-stu-id="f153a-110">On the header of the new blocking record, set the **Item number** field to the item that you want to block, and enter a description.</span></span>
1. <span data-ttu-id="f153a-111">Na FastTab **Geral**, no campo **Quantidade**, insira o número de itens para bloquear.</span><span class="sxs-lookup"><span data-stu-id="f153a-111">On the **General** FastTab, in the **Quantity** field, enter the number of items to block.</span></span>
1. <span data-ttu-id="f153a-112">Na FastTab **Dimensões de estoque**, especifique o local e o depósito onde os itens que você deseja bloquear estão localizados no momento.</span><span class="sxs-lookup"><span data-stu-id="f153a-112">On the **Inventory dimensions** FastTab, specify the site and warehouse where the items that you want to block are currently located.</span></span>
1. <span data-ttu-id="f153a-113">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f153a-113">On the Action Pane, select **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="f153a-114">Atualizar as condições de bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="f153a-114">Update the conditions of the inventory blocking</span></span>

<span data-ttu-id="f153a-115">Para atualizar um registro de bloqueio de estoque, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f153a-115">To update an inventory blocking record, follow these steps.</span></span>

1. <span data-ttu-id="f153a-116">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Bloqueio de estoque**.</span><span class="sxs-lookup"><span data-stu-id="f153a-116">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="f153a-117">No painel de lista, selecione o registro de bloqueio relevante.</span><span class="sxs-lookup"><span data-stu-id="f153a-117">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="f153a-118">Edite o registro, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f153a-118">Edit the record as required.</span></span> <span data-ttu-id="f153a-119">Por exemplo, você pode alterar o valor do campo **Data esperada** para indicar quando o estoque bloqueado deve ficar disponível para reserva.</span><span class="sxs-lookup"><span data-stu-id="f153a-119">For example, you might change the value of the **Expected date** field to indicate when the blocked inventory is expected to become available for reservation.</span></span> <span data-ttu-id="f153a-120">Se a opção **Recebimentos esperados** for selecionada, a data aparecerá na transação esperada.</span><span class="sxs-lookup"><span data-stu-id="f153a-120">If the **Expected receipts** option is selected, the date will appear on the expected transaction.</span></span> <span data-ttu-id="f153a-121">(A opção **Recebimentos esperados** é selecionada por padrão quando você criar manualmente um registro de bloqueio.)</span><span class="sxs-lookup"><span data-stu-id="f153a-121">(The **Expected receipts** option is selected by default when you manually create a blocking record.)</span></span>
1. <span data-ttu-id="f153a-122">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f153a-122">On the Action Pane, select **Save**.</span></span>

## <a name="unblock-inventory"></a><span data-ttu-id="f153a-123">Desbloquear estoque</span><span class="sxs-lookup"><span data-stu-id="f153a-123">Unblock inventory</span></span>

<span data-ttu-id="f153a-124">Para remover um registro de bloqueio de estoque para que o estoque seja desbloqueado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f153a-124">To remove an inventory blocking record so that inventory is unblocked, follow these steps.</span></span>

1. <span data-ttu-id="f153a-125">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Bloqueio de estoque**.</span><span class="sxs-lookup"><span data-stu-id="f153a-125">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="f153a-126">No painel de lista, selecione o registro de bloqueio relevante.</span><span class="sxs-lookup"><span data-stu-id="f153a-126">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="f153a-127">No Painel de Ações, selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="f153a-127">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="f153a-128">Será solicitado que você confirme a operação.</span><span class="sxs-lookup"><span data-stu-id="f153a-128">You're prompted to confirm the operation.</span></span> <span data-ttu-id="f153a-129">Selecione **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="f153a-129">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="f153a-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f153a-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
