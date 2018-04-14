---
title: "Planejar cargas de consolidação de hub"
description: "Este artigo descreve o recurso para consolidar remessas em um hub quando entregar mercadorias em depósitos diferentes para o mesmo cliente ou quando mercadorias são recebidas de vários fornecedores no mesmo depósito."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 159410e7c1f04ee9a057c7d9dc9a2527c522b85b
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="plan-loads-using-hub-consolidation"></a><span data-ttu-id="8eefa-103">Planejar cargas de consolidação de hub</span><span class="sxs-lookup"><span data-stu-id="8eefa-103">Plan loads using hub consolidation</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="8eefa-104">Este artigo descreve o recurso para consolidar remessas em um hub quando entregar mercadorias em depósitos diferentes para o mesmo cliente ou quando mercadorias são recebidas de vários fornecedores no mesmo depósito.</span><span class="sxs-lookup"><span data-stu-id="8eefa-104">This article describes the feature for consolidating shipments in a hub when you deliver goods from different warehouses to the same customer, or when you receive goods from multiple vendors in the same warehouse.</span></span>

<span data-ttu-id="8eefa-105">Pode ser útil consolidar as remessas em um hub quando entregar mercadorias em depósitos diferentes para o mesmo cliente ou quando mercadorias são entregues de vários fornecedores para o mesmo depósito.</span><span class="sxs-lookup"><span data-stu-id="8eefa-105">It can be useful to consolidate shipments in a hub when you deliver goods from different warehouses to the same customer, or when goods are delivered from multiple vendors to the same warehouse.</span></span>

## <a name="building-loads"></a><span data-ttu-id="8eefa-106">Criando cargas</span><span class="sxs-lookup"><span data-stu-id="8eefa-106">Building loads</span></span>
<span data-ttu-id="8eefa-107">Antes de usar a consolidação de hub, você deve habilitar a opção **Planejamento em trânsito**na página **Parâmetros de gerenciamento de transporte**.</span><span class="sxs-lookup"><span data-stu-id="8eefa-107">Before you can use hub consolidation, you must enable the **In transit planning** option on the **Transportation management parameters** page.</span></span> <span data-ttu-id="8eefa-108">Você também deve criar os hubs onde ocorrerá a consolidação.</span><span class="sxs-lookup"><span data-stu-id="8eefa-108">You must also create the hubs where consolidation will occur.</span></span> <span data-ttu-id="8eefa-109">O diagrama a seguir mostra um exemplo de consolidação de hub.</span><span class="sxs-lookup"><span data-stu-id="8eefa-109">The following diagram shows an example of hub consolidation.</span></span> <span data-ttu-id="8eefa-110">Nesse caso, ordens de venda de depósitos diferentes irão para o mesmo cliente.</span><span class="sxs-lookup"><span data-stu-id="8eefa-110">In this case, sales orders from different warehouses are going to the same customer.</span></span> <span data-ttu-id="8eefa-111">Cargas básicas são criadas com base em ordens de venda de maneira normal, usando a página **Bancada de planejamento de carga**.</span><span class="sxs-lookup"><span data-stu-id="8eefa-111">The basic loads are created based on sales orders in the usual way, by using the **Load planning workbench** page.</span></span> <span data-ttu-id="8eefa-112">Para consolidar as duas cargas em um hub antes que sejam enviadas para o cliente, na página **Bancada de planejamento de carga**, no campo **Transporte**, selecione **Consolidação de hub**.</span><span class="sxs-lookup"><span data-stu-id="8eefa-112">To consolidate the two loads in a hub before they are delivered to the customer, on the **Load planning workbench** page, in the **Transportation** field, select **Hub consolidation**.</span></span> <span data-ttu-id="8eefa-113">Quando você seleciona o hub correto para cada carregamento, os carregamentos terão o hub com o destino "entregar".</span><span class="sxs-lookup"><span data-stu-id="8eefa-113">When you select the correct hub for each load, the loads will have the hub as the “drop off” destination.</span></span> <span data-ttu-id="8eefa-114">Você também terá duas "linhas de solicitação de transporte" na seção **Fornecimento e demanda** na página **Bancada do planejamento de carga**.</span><span class="sxs-lookup"><span data-stu-id="8eefa-114">You will also have two “transportation request lines” in the **Supply and Demand** section on the **Load planning workbench** page.</span></span> <span data-ttu-id="8eefa-115">Você pode então adicionar estas duas linhas para uma nova carga.</span><span class="sxs-lookup"><span data-stu-id="8eefa-115">You can then add these two lines to a new load.</span></span> <span data-ttu-id="8eefa-116">Essa nova carga terá ambas as linhas de ordem de venda e também terá o hub como o endereço de "pegar" e o cliente como o destino "entregar".</span><span class="sxs-lookup"><span data-stu-id="8eefa-116">This new load will have both sales order lines, and will also have the hub as the “pick up” address and customer A as the “drop off” destination.</span></span> <span data-ttu-id="8eefa-117">As três cargas estão prontas para serem classificadas e roteadas como qualquer outra carga.</span><span class="sxs-lookup"><span data-stu-id="8eefa-117">The three loads are then ready to be rated and routed like any other load.</span></span> <span data-ttu-id="8eefa-118">Você pode selecionar qual transportadora o sistema sugere para cada carga.</span><span class="sxs-lookup"><span data-stu-id="8eefa-118">You can select whatever shipping carrier the system suggests for each load.</span></span> <span data-ttu-id="8eefa-119">[![Consolidação de hub](./media/hubconsol.jpg)](./media/hubconsol.jpg) Você também pode usar o mesmo método para consolidar cargas de várias ordens de transferência.</span><span class="sxs-lookup"><span data-stu-id="8eefa-119">[![Hub consolidation](./media/hubconsol.jpg)](./media/hubconsol.jpg) You can also use the same method to consolidate loads for multiple transfer orders.</span></span> <span data-ttu-id="8eefa-120">Nesse caso, o cliente A no diagrama anterior é um depósito.</span><span class="sxs-lookup"><span data-stu-id="8eefa-120">In this case, customer A in the preceding diagram is a warehouse.</span></span> <span data-ttu-id="8eefa-121">Como alternativa, você pode consolidar cargas de várias ordens de compra, onde as cargas são entregues de fornecedores diferentes para o mesmo depósito.</span><span class="sxs-lookup"><span data-stu-id="8eefa-121">Alternatively, you can consolidate loads for multiple purchase orders, where the loads are delivered from different vendors to the same warehouse.</span></span> <span data-ttu-id="8eefa-122">Você pode ter mais de um hub de consolidação e pode consolidar vários hubs para cargas mais provenientes de depósitos diferentes.</span><span class="sxs-lookup"><span data-stu-id="8eefa-122">You can have more than one consolidation hub, and can consolidate in multiple hubs for more loads that come from different warehouses.</span></span> <span data-ttu-id="8eefa-123">Depois de criar as cargas básicas e usar a opção de consolidação do hub, você cria os novos carregamentos usando as linhas de solicitação de transporte consolidado.</span><span class="sxs-lookup"><span data-stu-id="8eefa-123">After you build your basic loads and use the hub consolidation option, you build the new loads by using the consolidated transportation request lines.</span></span> <span data-ttu-id="8eefa-124">Em seguida, taxar e rotear as cargas.</span><span class="sxs-lookup"><span data-stu-id="8eefa-124">You then rate and route your loads.</span></span>




