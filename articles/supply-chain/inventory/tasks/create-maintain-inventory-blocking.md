---
title: Criar e manter um bloqueio de estoque
description: Este procedimento mostra como evitar que o estoque físico disponível seja reservado para outros documentos de origem de saída usando o bloqueio de estoque.
author: perlynne
ms.date: 08/08/2019
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
ms.openlocfilehash: 319ae6da1e0e504316b2d96001d582e835cef20c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833992"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="ca2c0-103">Criar e manter um bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="ca2c0-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ca2c0-104">Este procedimento mostra como evitar que o estoque físico disponível seja reservado para outros documentos de origem de saída usando o bloqueio de estoque.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="ca2c0-105">Você pode executar o procedimento na empresa USMF de dados de demonstração usando os valores de exemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="ca2c0-106">Você precisa ter um item do estoque físico disponível antes de iniciar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="ca2c0-107">Criar um bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="ca2c0-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="ca2c0-108">No **Painel de Navegação**, vá para **Módulos > Gerenciamento de estoque > Tarefas periódicas > Bloqueio de estoque**.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-108">In the **Navigation pane**, go to **Modules > Inventory management > Periodic tasks > Inventory blocking**.</span></span>
2. <span data-ttu-id="ca2c0-109">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-109">Click **New**.</span></span>
3. <span data-ttu-id="ca2c0-110">No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-110">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ca2c0-111">Na lista, selecione o item que deseja escolher.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-111">In the list, select the item you want to choose.</span></span> <span data-ttu-id="ca2c0-112">Selecione um número de item com estoque físico disponível que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="ca2c0-113">Se você estiver usando USMF, você pode o item M9201.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-113">If you're using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="ca2c0-114">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="ca2c0-114">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="ca2c0-115">Se você estiver usando o item M9201, você precisará selecionar menos de 200.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-115">If you're using item M9201, you need to select less than 200.</span></span>
6. <span data-ttu-id="ca2c0-116">Expanda a Guia Rápida **Dimensões de estoque**.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-116">Expand the **Inventory dimensions** fastTab.</span></span>
7. <span data-ttu-id="ca2c0-117">No campo **Depósito**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-117">In the **Warehouse** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="ca2c0-118">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="ca2c0-119">Se você estiver usando o item M9201, você pode selecionar o depósito 51.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-119">If you're using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="ca2c0-120">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-120">Click **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="ca2c0-121">Atualizar as condições de bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="ca2c0-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="ca2c0-122">Na Guia Rápida **Geral**, no campo **Quantidade**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-122">In the **General** fastTab, in the **Quantity** field, enter a number.</span></span> <span data-ttu-id="ca2c0-123">Atualize o campo de quantidade em estoque para refletir a quantidade para bloquear.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="ca2c0-124">No campo **Data estimada**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-124">In the **Expected date** field, enter a date.</span></span> <span data-ttu-id="ca2c0-125">Você pode desejar indicar quando o estoque bloqueado deve ficar disponível para reserva atribuindo uma data esperada.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="ca2c0-126">Se a opção esperada de recebimentos é marcada para o bloqueio de estoque, como é por padrão ao criar manualmente um bloqueio, essa data será exibida na transação esperada.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="ca2c0-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-127">Click **Save**.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="ca2c0-128">Remover o bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="ca2c0-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="ca2c0-129">No **Painel de Ação**, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-129">On the **Action Pane**, click **Delete**.</span></span>
2. <span data-ttu-id="ca2c0-130">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-130">Click **Yes**.</span></span>
3. <span data-ttu-id="ca2c0-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ca2c0-131">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]