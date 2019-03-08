---
title: Criar requisições de itens para ordens de serviço
description: Caso seja necessário reservar itens específicos para uma ordem de serviço, você poderá criar requisições de item de estoque para ele.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5a730ae945af15c7bd4020c734bac971d8186e2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "312200"
---
# <a name="create-item-requirements-for-service-orders"></a><span data-ttu-id="8448c-103">Criar requisições de itens para ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="8448c-103">Create item requirements for service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="8448c-104">Você pode criar uma ordem de serviço para rastrear e gerenciar os serviços que você presta para seus clientes.</span><span class="sxs-lookup"><span data-stu-id="8448c-104">You can create a service order to track and manage services that you provide to your customers.</span></span> <span data-ttu-id="8448c-105">Caso seja necessário reservar itens específicos para uma ordem de serviço, você poderá criar requisições de item de estoque para ele.</span><span class="sxs-lookup"><span data-stu-id="8448c-105">If you need to reserve specific items for a service order, you can create inventory item requirements for it.</span></span> <span data-ttu-id="8448c-106">Uma requisição de item pode ser consumida imediatamente do estoque ou pode iniciar uma ordem de produção do item.</span><span class="sxs-lookup"><span data-stu-id="8448c-106">An item requirement can be immediately consumed from inventory, or it can initiate a production order for the item.</span></span>

<span data-ttu-id="8448c-107">Usando uma requisição em vez de uma transação de itens, é possível planejar que entrega ocorra antes do item ser efetivamente usado, criar uma ordem de compra, incluir o item na estrutura do acordo comercial e incluir a requisição do item no planejamento da produção.</span><span class="sxs-lookup"><span data-stu-id="8448c-107">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span>

<span data-ttu-id="8448c-108">As requisições de itens para ordens de serviço são processadas através de um projeto.</span><span class="sxs-lookup"><span data-stu-id="8448c-108">Item requirements for service orders are processed through a project.</span></span> <span data-ttu-id="8448c-109">Para criar uma requisição de item em uma ordem de serviço, a ordem de serviço deverá ser atribuída a um projeto.</span><span class="sxs-lookup"><span data-stu-id="8448c-109">To create an item requirement on a service order, the service order must be assigned to a project.</span></span> <span data-ttu-id="8448c-110">Depois de criar uma requisição de item para uma ordem de serviço, você poderá exibir a requisição de item no formulário **Projetos** do projeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="8448c-110">After you create an item requirement for a service order, you can view the item requirement in the **Projects** form for the selected project.</span></span>

## <a name="create-an-item-requirement-for-a-service-order"></a><span data-ttu-id="8448c-111">Criar uma requisição de itens para uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="8448c-111">Create an item requirement for a service order</span></span>

1.  <span data-ttu-id="8448c-112">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="8448c-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="8448c-113">Selecione a ordem de serviço para a qual você deseja criar uma requisição de item.</span><span class="sxs-lookup"><span data-stu-id="8448c-113">Select the service order that you want to create an item requirement for.</span></span>

3.  <span data-ttu-id="8448c-114">No **Painel de Ação**, na guia **Expedição**, clique em **Requisição de itens**.</span><span class="sxs-lookup"><span data-stu-id="8448c-114">On the **Action Pane**, on the **Dispatch** tab, click **Item requirement**.</span></span>

4.  <span data-ttu-id="8448c-115">No formulário **Requisição de itens**, insira informações sobre o item requisitado.</span><span class="sxs-lookup"><span data-stu-id="8448c-115">In the **Item requirements** form, enter information for the required item.</span></span> <span data-ttu-id="8448c-116">Para obter informações sobre os campos específicos, consulte [Requisição de itens (formulário)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\)).</span><span class="sxs-lookup"><span data-stu-id="8448c-116">For more information about the specific fields, see [Item requirements (form)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\)).</span></span>

## <a name="create-an-item-requirement-for-a-service-agreement"></a><span data-ttu-id="8448c-117">Criar uma requisição de item para um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="8448c-117">Create an item requirement for a service agreement</span></span>

1.  <span data-ttu-id="8448c-118">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="8448c-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="8448c-119">Abra o contrato de serviço para o qual você deseja criar uma requisição de item.</span><span class="sxs-lookup"><span data-stu-id="8448c-119">Open the service agreement for which you want to create an item requirement.</span></span>

3.  <span data-ttu-id="8448c-120">Na Guia Rápida **Linhas**, clique em **Adicionar** para criar uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="8448c-120">On the **Lines** FastTab, click **Add** to create a new line.</span></span>

4.  <span data-ttu-id="8448c-121">No campo **Tipo de transação**, selecione **Item**.</span><span class="sxs-lookup"><span data-stu-id="8448c-121">In the **Transaction type** field, select **Item**.</span></span>

5.  <span data-ttu-id="8448c-122">No campo **Configuração de item**, selecione **Requisição de itens**.</span><span class="sxs-lookup"><span data-stu-id="8448c-122">In the **Item setup** field, select **Item requirement**.</span></span>

6.  <span data-ttu-id="8448c-123">No campo **Número de item**, selecione o item necessário ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="8448c-123">In the **Item number** field, select the item that is required for the service agreement.</span></span>

7.  <span data-ttu-id="8448c-124">Na Guia Rápida **Detalhes de linha**, na guia **Dimensões de produto**, no campo **Local**, selecione o local de estoque do item.</span><span class="sxs-lookup"><span data-stu-id="8448c-124">On the **Line details** FastTab, on the **Product dimensions** tab, in the **Site** field, select the inventory site for the item.</span></span>

8.  <span data-ttu-id="8448c-125">Para criar uma ordem de serviço da linha do contrato, na Guia Rápida **Linhas**, clique em **Criar ordens de serviço**, e insira as informações relevantes ao formulário **Criar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="8448c-125">To create a service order from the agreement line, on the **Lines** FastTab, click **Create service orders**, and then enter the relevant information in the **Create service orders** form.</span></span> 


## <a name="see-also"></a><span data-ttu-id="8448c-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8448c-126">See also</span></span>

<span data-ttu-id="8448c-127">[Criar ordens de serviço automaticamente](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="8448c-127">[Create service orders automatically](create-service-orders-automatically.md).</span></span>

  


