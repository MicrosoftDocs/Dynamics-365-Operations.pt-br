---
title: Receber itens na ordem de compra da requisição de itens
description: Este tópico explica como receber itens em uma ordem de compra de uma requisição de itens.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7afdae65c5ae7e3196c6b9f142dd87aec39b5ea3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174411"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="e6a5d-103">Receber itens na ordem de compra da requisição de itens</span><span class="sxs-lookup"><span data-stu-id="e6a5d-103">Receive items on purchase order from item requirement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e6a5d-104">Este tópico explica como receber itens em uma ordem de compra de uma requisição de itens.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-104">This topic explains how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="e6a5d-105">Usando uma requisição em vez de uma transação de itens, é possível planejar que entrega ocorra antes do item ser efetivamente usado, criar uma ordem de compra, incluir o item na estrutura do acordo comercial e incluir a requisição do item no planejamento da produção.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="e6a5d-106">Essa tarefa usa o conjunto de dados de USSI.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="e6a5d-107">No Painel de navegação, acesse **Módulos > Gerenciamento e contabilidade do projeto > Projetos > Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-107">In the navigation pane, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="e6a5d-108">Na lista, selecione o link na linha desejada.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-108">In the list, select the link in the desired row.</span></span>
3. <span data-ttu-id="e6a5d-109">No Painel de Ações, selecione **Plano**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-109">On the Action Pane, select **Plan**.</span></span>
4. <span data-ttu-id="e6a5d-110">Selecione **Requisições de itens**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-110">Select **Item requirements**.</span></span>
5. <span data-ttu-id="e6a5d-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-111">Select **New**.</span></span>
6. <span data-ttu-id="e6a5d-112">Na nova linha, insira ou selecione um valor no campo **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-112">In the new row, enter or select a value in the **Item number** field.</span></span>
7. <span data-ttu-id="e6a5d-113">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="e6a5d-113">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="e6a5d-114">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-114">Select **Save**.</span></span>
9. <span data-ttu-id="e6a5d-115">No Painel de Ação, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-115">On the Action Pane, select **Manage**.</span></span>
10. <span data-ttu-id="e6a5d-116">Selecione **Funções**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-116">Select **Functions**.</span></span>
11. <span data-ttu-id="e6a5d-117">Selecione **Criar ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-117">Select **Create purchase order**.</span></span>
12. <span data-ttu-id="e6a5d-118">Selecione a caixa de seleção **Incluir tudo**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-118">Select the **Include all** check box.</span></span>
13. <span data-ttu-id="e6a5d-119">No campo **Conta de fornecedor**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-119">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="e6a5d-120">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-120">Select **OK**.</span></span>
15. <span data-ttu-id="e6a5d-121">No painel de navegação, vá para **Módulos > Contas a pagar > Ordens de compra > Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-121">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
16. <span data-ttu-id="e6a5d-122">Na lista, selecione o link na linha desejada.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-122">In the list, select the link in the desired row.</span></span>
17. <span data-ttu-id="e6a5d-123">No Painel de Ação, selecione **Compra**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-123">On the Action Pane, select **Purchase**.</span></span>
18. <span data-ttu-id="e6a5d-124">Selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-124">Select **Confirm**.</span></span>
19. <span data-ttu-id="e6a5d-125">No Painel de Ação, selecione **Receber**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-125">On the Action Pane, select **Receive**.</span></span>
20. <span data-ttu-id="e6a5d-126">Selecione **Recebimento de produtos**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-126">Select **Product receipt**.</span></span>
21. <span data-ttu-id="e6a5d-127">No campo **Recebimento de produtos**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-127">In the **Product receipt** field, type a value.</span></span>
22. <span data-ttu-id="e6a5d-128">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6a5d-128">Select **OK**.</span></span>

