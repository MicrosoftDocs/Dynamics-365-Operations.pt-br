--- 
title: "Receber itens na ordem de compra da requisição de itens"
description: "Este procedimento mostra como receber itens em uma ordem de compra de uma requisição de itens."
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7c9093439c4c0c4645d96ad97ba56f31026ec334
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="98e27-103">Receber itens na ordem de compra da requisição de itens</span><span class="sxs-lookup"><span data-stu-id="98e27-103">Receive items on purchase order from item requirement</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98e27-104">Este procedimento mostra como receber itens em uma ordem de compra de uma requisição de itens.</span><span class="sxs-lookup"><span data-stu-id="98e27-104">This procedure shows how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="98e27-105">Usando uma requisição em vez de uma transação de itens, é possível planejar que entrega ocorra antes do item ser efetivamente usado, criar uma ordem de compra, incluir o item na estrutura do acordo comercial e incluir a requisição do item no planejamento da produção.</span><span class="sxs-lookup"><span data-stu-id="98e27-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="98e27-106">Essa tarefa usa o conjunto de dados de USSI.</span><span class="sxs-lookup"><span data-stu-id="98e27-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="98e27-107">Vá para Gerenciamento e contabilidade de projeto > Projetos > Todos os projetos.</span><span class="sxs-lookup"><span data-stu-id="98e27-107">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="98e27-108">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="98e27-108">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="98e27-109">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="98e27-109">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="98e27-110">Clique em Requisições de itens.</span><span class="sxs-lookup"><span data-stu-id="98e27-110">Click Item requirements.</span></span>
5. <span data-ttu-id="98e27-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="98e27-111">Click New.</span></span>
6. <span data-ttu-id="98e27-112">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="98e27-112">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="98e27-113">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="98e27-113">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="98e27-114">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="98e27-114">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="98e27-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="98e27-115">Click Save.</span></span>
10. <span data-ttu-id="98e27-116">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="98e27-116">On the Action Pane, click Manage.</span></span>
11. <span data-ttu-id="98e27-117">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="98e27-117">Click Functions.</span></span>
12. <span data-ttu-id="98e27-118">Clique em Criar ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="98e27-118">Click Create purchase order.</span></span>
13. <span data-ttu-id="98e27-119">Selecione a caixa de seleção Incluir.</span><span class="sxs-lookup"><span data-stu-id="98e27-119">Select the Include check box.</span></span>
14. <span data-ttu-id="98e27-120">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="98e27-120">In the Vendor account field, enter or select a value.</span></span>
15. <span data-ttu-id="98e27-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="98e27-121">Click OK.</span></span>
16. <span data-ttu-id="98e27-122">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="98e27-122">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
17. <span data-ttu-id="98e27-123">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="98e27-123">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="98e27-124">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="98e27-124">On the Action Pane, click Purchase.</span></span>
19. <span data-ttu-id="98e27-125">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="98e27-125">Click Confirm.</span></span>
20. <span data-ttu-id="98e27-126">No Painel de Ação, clique em Receber.</span><span class="sxs-lookup"><span data-stu-id="98e27-126">On the Action Pane, click Receive.</span></span>
21. <span data-ttu-id="98e27-127">Clique em Recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="98e27-127">Click Product receipt.</span></span>
22. <span data-ttu-id="98e27-128">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="98e27-128">In the list, mark the selected row.</span></span>
23. <span data-ttu-id="98e27-129">No campo Recebimento de produtos, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="98e27-129">In the Product receipt field, type a value.</span></span>
24. <span data-ttu-id="98e27-130">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="98e27-130">Click OK.</span></span>


