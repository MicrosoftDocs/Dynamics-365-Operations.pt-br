---
title: Sincronizar ordens de serviço com projetos do Field Service com o Supply Chain Management
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho com um número de projeto do Dynamics 365 Field Service para o Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 3678fbca8244ae6dcd050f6a91ff3b35d90e1064
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251698"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a><span data-ttu-id="6b3ff-103">Sincronizar ordens de serviço com projetos do Field Service com o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="6b3ff-103">Synchronize work orders with project from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6b3ff-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho com um número de projeto do Dynamics 365 Field Service para o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Dynamics 365 Field Service to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="6b3ff-105">[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="6b3ff-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="6b3ff-106">O modelo **Ordens de serviço com projeto (Field Service para Supply Chain Management)** usado é baseado no modelo **Ordens de serviço (Field Service para Supply Chain Management)**.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-106">The used **Work Orders with Project (Field Service to Supply Chain Management)** template is based on the **Work Orders (Field Service to Supply Chain Management)** template.</span></span> <span data-ttu-id="6b3ff-107">Para obter mais informações, consulte [Sincronizar ordens de serviço no Field Service com ordens de venda no Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="6b3ff-107">For more information, see [Synchronize work orders in Field Service to sales orders in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="6b3ff-108">Este tópico descreve apenas as diferenças entre os dois métodos:</span><span class="sxs-lookup"><span data-stu-id="6b3ff-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="6b3ff-109">**Ordens de serviço com projeto (Field Service para Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="6b3ff-109">**Work Orders with Project (Field Service to Supply Chain Management)**</span></span>
- <span data-ttu-id="6b3ff-110">**Ordens de serviço (Field Service para Supply Chain Management)**</span><span class="sxs-lookup"><span data-stu-id="6b3ff-110">**Work Orders (Field Service to Supply Chain Management)**</span></span>

<span data-ttu-id="6b3ff-111">A principal diferença é que este modelo inclui mapeamento do número de projeto atribuído à ordem de serviço no Field Service, garantindo que a ordem de venda criada no Supply Chain Management inclua o número de projeto e que o faturamento possa ocorrer no projeto relacionado.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-111">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Supply Chain Management include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="6b3ff-112">Além disso, este método utiliza Filtragem e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="6b3ff-113">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="6b3ff-113">Templates and tasks</span></span>

<span data-ttu-id="6b3ff-114">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="6b3ff-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="6b3ff-115">Ordens de serviço com projeto (Field Service para Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="6b3ff-115">Work Orders with Project (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="6b3ff-116">**Nome da tarefa no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="6b3ff-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="6b3ff-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="6b3ff-117">WorkOrderHeader</span></span>
- <span data-ttu-id="6b3ff-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="6b3ff-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="6b3ff-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="6b3ff-119">WorkOrderProduct</span></span>
- <span data-ttu-id="6b3ff-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="6b3ff-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="6b3ff-121">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="6b3ff-121">Field Service CRM solution</span></span>
<span data-ttu-id="6b3ff-122">O campo **Projeto Externo** foi adicionado à entidade Ordem de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="6b3ff-123">Este campo é uma pesquisa e compra que marca sua ordem de serviço com um projeto. A ordem de venda será conectada a um projeto no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Supply Chain Management.</span></span> <span data-ttu-id="6b3ff-124">Quando o **Status do Sistema** mudar de Aberto - Em Andamento (690.970.000) para um status superior, o campo **Projeto Externo** será bloqueado, e você não poderá adicionar, remover ou alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-124">When the **System Status** changes from Open – In Progress(690,970,000) to a higher status, the **External Project** field will be locked and you can't add, remove, or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="6b3ff-125">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="6b3ff-125">Template mapping in Data integration</span></span>

<span data-ttu-id="6b3ff-126">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="6b3ff-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a><span data-ttu-id="6b3ff-127">Ordens de serviço com projeto (Field Service para Supply Chain Management): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="6b3ff-127">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeader</span></span>

<span data-ttu-id="6b3ff-128">[![Mapeamento de modelo na Integração de dados](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="6b3ff-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a><span data-ttu-id="6b3ff-129">Ordens de serviço com projeto (Field Service para Supply Chain Management): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="6b3ff-129">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderHeaderProject</span></span>

<span data-ttu-id="6b3ff-130">[![Mapeamento de modelo na Integração de dados](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="6b3ff-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a><span data-ttu-id="6b3ff-131">Ordens de serviço com projeto (Field Service para Supply Chain Management): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="6b3ff-131">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderProduct</span></span>

<span data-ttu-id="6b3ff-132">[![Mapeamento de modelo na Integração de dados](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="6b3ff-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a><span data-ttu-id="6b3ff-133">Ordens de serviço com projeto (Field Service para Supply Chain Management): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="6b3ff-133">Work Orders with Project (Field Service to Supply Chain Management): WorkOrderService</span></span>

<span data-ttu-id="6b3ff-134">[![Mapeamento de modelo na Integração de dados](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="6b3ff-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
