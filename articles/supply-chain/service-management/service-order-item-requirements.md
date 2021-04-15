---
title: Requisições de itens da ordem de serviço
description: Caso seja necessário reservar itens específicos para uma ordem de serviço, você poderá criar requisições de item de estoque para ele.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4bbd15ca83ab116286a3d681887f076896653c76
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810573"
---
# <a name="service-order-item-requirements"></a><span data-ttu-id="e693f-103">Requisições de itens da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="e693f-103">Service order item requirements</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e693f-104">Você pode criar uma ordem de serviço para rastrear e gerenciar os serviços que você presta para seus clientes.</span><span class="sxs-lookup"><span data-stu-id="e693f-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="e693f-105">Caso seja necessário reservar itens específicos para uma ordem de serviço, você poderá criar requisições de item de estoque para ele.</span><span class="sxs-lookup"><span data-stu-id="e693f-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="e693f-106">Uma requisição de item pode ser consumida imediatamente do estoque ou pode iniciar uma ordem de produção do item.</span><span class="sxs-lookup"><span data-stu-id="e693f-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="e693f-107">Usando uma requisição em vez de uma transação de itens, é possível planejar que entrega ocorra antes do item ser efetivamente usado, criar uma ordem de compra, incluir o item na estrutura do acordo comercial e incluir a requisição do item no planejamento da produção.</span><span class="sxs-lookup"><span data-stu-id="e693f-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="e693f-108">As requisições de itens para ordens de serviço são processadas através de um projeto.</span><span class="sxs-lookup"><span data-stu-id="e693f-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="e693f-109">Para criar uma requisição de itens em uma ordem de serviço, a ordem de serviço deve ser anexada a um projeto.</span><span class="sxs-lookup"><span data-stu-id="e693f-109">To create an item requirement on a service order, the service order must be attached to a project.</span></span>

<span data-ttu-id="e693f-110">Assim que uma requisição de itens é criada para uma ordem de serviço, ela pode ser exibida em **Projeto** na ordem de serviço individual ou através do formulário **Ordem de vendas**.</span><span class="sxs-lookup"><span data-stu-id="e693f-110">As soon as an item requirement is created for a service order, it can be viewed from **Project** in the individual service order or through the **Sales order** form.</span></span>

## <a name="view-an-item-requirement-from-a-service-order"></a><span data-ttu-id="e693f-111">Exibir uma requisição de itens de uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="e693f-111">View an item requirement from a service order</span></span>

1.  <span data-ttu-id="e693f-112">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e693f-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="e693f-113">Clique em **Expedição**, e depois clique em **Requisição de Itens** para abrir o formulário **Requisições de itens**.</span><span class="sxs-lookup"><span data-stu-id="e693f-113">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span>

3.  <span data-ttu-id="e693f-114">Clique na guia **Projeto** e verifique o campo **Ordem de serviço** para visualizar as ordens de serviço da requisição do item.</span><span class="sxs-lookup"><span data-stu-id="e693f-114">Click the **Project** tab, and check the **Service order** field to see the service orders of the item requirement.</span></span>

## <a name="delete-service-orders-with-item-requirements"></a><span data-ttu-id="e693f-115">Excluir ordens de serviço com requisições de itens</span><span class="sxs-lookup"><span data-stu-id="e693f-115">Delete service orders with item requirements</span></span>

<span data-ttu-id="e693f-116">Se uma requisição de itens for criada em uma ordem de serviço, não será possível excluir essa ordem.</span><span class="sxs-lookup"><span data-stu-id="e693f-116">If an item requirement is created on a service order, you cannot delete the service order.</span></span> <span data-ttu-id="e693f-117">Você deve excluir a requisição de item antes de excluir a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e693f-117">You must delete the item requirement before you can delete the service order.</span></span>

1.  <span data-ttu-id="e693f-118">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e693f-118">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="e693f-119">Clique em **Expedição**, e depois clique em **Requisição de Itens** para abrir o formulário **Requisições de itens**.</span><span class="sxs-lookup"><span data-stu-id="e693f-119">Click **Dispatch**, and then click **Item requirement** to open the **Item requirements** form.</span></span> <span data-ttu-id="e693f-120">Este formulário lista as requisições de item que são criadas na ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e693f-120">This form lists the item requirements that are created on the service order.</span></span>

3.  <span data-ttu-id="e693f-121">Selecione a requisição de item a ser excluída e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="e693f-121">Select the item requirement to delete, and then click **Delete**.</span></span>

<span data-ttu-id="e693f-122">–ou–</span><span class="sxs-lookup"><span data-stu-id="e693f-122">–or–</span></span>

1.  <span data-ttu-id="e693f-123">Clique em **Gerenciamento e contabilidade de projeto** \> **Comum** \> **Projetos** \> **Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="e693f-123">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="e693f-124">Abra o projeto que possui a ordem de serviço na qual uma requisição de item é criada.</span><span class="sxs-lookup"><span data-stu-id="e693f-124">Open the project that has the service order in which an item requirement is created.</span></span>

3.  <span data-ttu-id="e693f-125">No formulário **Projetos**, no painel direito, clique em **Requisições de itens**.</span><span class="sxs-lookup"><span data-stu-id="e693f-125">In the **Projects** form, in the right pane, click **Item requirements**.</span></span> <span data-ttu-id="e693f-126">O formulário **Requisições de itens** será aberto e listará as requisições de itens associadas ao projeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="e693f-126">The **Item requirements** form lists the item requirements that are associated with the selected project.</span></span>

4.  <span data-ttu-id="e693f-127">Selecione a requisição de item a ser excluída e clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="e693f-127">Select the item requirement to delete, and then click **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e693f-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e693f-128">See also</span></span>

<span data-ttu-id="e693f-129">[Requisições de itens (formulário)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="e693f-129">[Item requirements (form)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]