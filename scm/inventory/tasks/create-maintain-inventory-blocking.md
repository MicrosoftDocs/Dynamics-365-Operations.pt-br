---
title: Criar e manter bloqueio de estoque
description: "Este procedimento mostra como evitar que o estoque físico disponível seja reservado para outros documentos de origem de saída usando o bloqueio de estoque."
author: perlynne
manager: AnnBe
ms.date: 12/02/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 7272349cf16b9459823a752b8d3df915f42606ef
ms.contentlocale: pt-br
ms.lasthandoff: 09/12/2017

---
# <a name="create-and-maintain-inventory-blocking"></a><span data-ttu-id="a9958-103">Criar e manter bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="a9958-103">Create and maintain inventory blocking</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a9958-104">Este procedimento mostra como evitar que o estoque físico disponível seja reservado para outros documentos de origem de saída usando o bloqueio de estoque.</span><span class="sxs-lookup"><span data-stu-id="a9958-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="a9958-105">Você pode executar o procedimento na empresa USMF de dados de demonstração usando os valores de exemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="a9958-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="a9958-106">Você precisa ter um item do estoque físico disponível antes de iniciar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="a9958-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="a9958-107">Criar um bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="a9958-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="a9958-108">Vá para Gerenciamento de estoque > Tarefas periódicas > Bloqueio de estoque.</span><span class="sxs-lookup"><span data-stu-id="a9958-108">Go to Inventory management > Periodic tasks > Inventory blocking.</span></span>
2. <span data-ttu-id="a9958-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a9958-109">Click New.</span></span>
3. <span data-ttu-id="a9958-110">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a9958-110">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a9958-111">Na lista, selecione o item que deseja escolher.</span><span class="sxs-lookup"><span data-stu-id="a9958-111">In the list, select the item you want to choose.</span></span>
    * <span data-ttu-id="a9958-112">Selecione um número de item com estoque físico disponível que você deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="a9958-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="a9958-113">Se você estiver usando USMF, você pode o item M9201.</span><span class="sxs-lookup"><span data-stu-id="a9958-113">If you’re using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="a9958-114">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a9958-114">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="a9958-115">Se você estiver usando o item M9201, você precisará selecionar menos de 200.</span><span class="sxs-lookup"><span data-stu-id="a9958-115">If you’re using item M9201, you need to select less than 200.</span></span>  
6. <span data-ttu-id="a9958-116">Ative a expansão da seção Dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="a9958-116">Toggle the expansion of the Inventory dimensions section.</span></span>
7. <span data-ttu-id="a9958-117">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a9958-117">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="a9958-118">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a9958-118">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a9958-119">Se você estiver usando o item M9201, você pode selecionar o depósito 51.</span><span class="sxs-lookup"><span data-stu-id="a9958-119">If you’re using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="a9958-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a9958-120">Click Save.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="a9958-121">Atualizar as condições de bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="a9958-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="a9958-122">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="a9958-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="a9958-123">Atualize o campo de quantidade em estoque para refletir a quantidade para bloquear.</span><span class="sxs-lookup"><span data-stu-id="a9958-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="a9958-124">No campo Data estimada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="a9958-124">In the Expected date field, enter a date.</span></span>
    * <span data-ttu-id="a9958-125">Você pode desejar indicar quando o estoque bloqueado deve ficar disponível para reserva atribuindo uma data esperada.</span><span class="sxs-lookup"><span data-stu-id="a9958-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="a9958-126">Se a opção esperada de recebimentos é marcada para o bloqueio de estoque, como é por padrão ao criar manualmente um bloqueio, essa data será exibida na transação esperada.</span><span class="sxs-lookup"><span data-stu-id="a9958-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="a9958-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a9958-127">Click Save.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="a9958-128">Remover o bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="a9958-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="a9958-129">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="a9958-129">Click Delete.</span></span>
2. <span data-ttu-id="a9958-130">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="a9958-130">Click Yes.</span></span>
3. <span data-ttu-id="a9958-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a9958-131">Close the page.</span></span>

