--- 
title: Criar uma ordem de compra para um fornecedor ocasional
description: Este procedimento mostra como criar uma ordem de compra de um fornecedor ocasional.
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e068105bcd5983220c43613569f80700922360e5
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="1a91a-103">Criar uma ordem de compra para um fornecedor ocasional</span><span class="sxs-lookup"><span data-stu-id="1a91a-103">Create a purchase order for a one-time supplier</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1a91a-104">Este procedimento mostra como criar uma ordem de compra de um fornecedor ocasional.</span><span class="sxs-lookup"><span data-stu-id="1a91a-104">This procedure shows you how to create a purchase order for a one-time supplier.</span></span> <span data-ttu-id="1a91a-105">O fornecedor é criado automaticamente com a ordem de compra, em vez de ter que criar manualmente a conta do vendedor.</span><span class="sxs-lookup"><span data-stu-id="1a91a-105">The supplier is created automatically with the purchase order, rather than having to create the vendor account manually.</span></span> <span data-ttu-id="1a91a-106">As ordens de compra geralmente são criadas com um agente de compra.</span><span class="sxs-lookup"><span data-stu-id="1a91a-106">Purchase orders are typically created by a purchasing agent.</span></span> <span data-ttu-id="1a91a-107">O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF.</span><span class="sxs-lookup"><span data-stu-id="1a91a-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="1a91a-108">É uma condição prévia que uma única conta do vendedor estabeleceu na página dos parâmetros da conta a pagar.</span><span class="sxs-lookup"><span data-stu-id="1a91a-108">It is a prerequisite that a one-time vendor account has been set up in the Account payable parameters page.</span></span>


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a><span data-ttu-id="1a91a-109">Criar uma ordem de compra para um fornecedor ocasional</span><span class="sxs-lookup"><span data-stu-id="1a91a-109">Create a purchase order for a one-time supplier</span></span>
1. <span data-ttu-id="1a91a-110">Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="1a91a-110">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="1a91a-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1a91a-111">Click New.</span></span>
3. <span data-ttu-id="1a91a-112">Selecione Sim no campo Fornecedor ocasional.</span><span class="sxs-lookup"><span data-stu-id="1a91a-112">Select Yes in the One-time supplier field.</span></span>
    * <span data-ttu-id="1a91a-113">Uma conta do vendedor automaticamente é criada e atribuída à ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="1a91a-113">A vendor account is automatically created and assigned to the purchase order.</span></span> <span data-ttu-id="1a91a-114">A conta do vendedor é criada com base no molde que é especificado na aba geral na página dos parâmetros das contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="1a91a-114">The vendor account is created based on the template that is specified on the General tab in the Accounts payable parameters page.</span></span>  
4. <span data-ttu-id="1a91a-115">No campo Nome, digite um nome para o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="1a91a-115">In the Name field, type a name for the supplier.</span></span>
5. <span data-ttu-id="1a91a-116">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1a91a-116">Click OK.</span></span>
    * <span data-ttu-id="1a91a-117">A ordem de compra pode agora ser concluída e processada como toda a outra ordem.</span><span class="sxs-lookup"><span data-stu-id="1a91a-117">The purchase order can now be completed and processed like any other order.</span></span> <span data-ttu-id="1a91a-118">Não há nenhuma característica especial relativa a como isto é feito.</span><span class="sxs-lookup"><span data-stu-id="1a91a-118">There are no special characteristics related to how this is done.</span></span> <span data-ttu-id="1a91a-119">A fatura explicará uma transação devida na conta do vendedor que foi criada com a ordem, e o pagamento será então processado.</span><span class="sxs-lookup"><span data-stu-id="1a91a-119">The invoice will account a due transaction on the vendor account that was created with the order, and payment will then be processed.</span></span> <span data-ttu-id="1a91a-120">Quando isto é concluído, a conta do vendedor pode ser suprimida.</span><span class="sxs-lookup"><span data-stu-id="1a91a-120">When this is completed, the vendor account can be deleted.</span></span> <span data-ttu-id="1a91a-121">Isto é feito tipicamente pelo departamento das contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="1a91a-121">This is typically done by the accounts payable department.</span></span>  


