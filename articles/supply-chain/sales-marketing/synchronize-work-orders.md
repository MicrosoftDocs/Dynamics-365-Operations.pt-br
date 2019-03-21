---
title: Sincronizar ordens de trabalho com um projeto do Field Service para o Finance and Operations
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho com um número de projeto do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 5ca01b085315d916a18c512af28fc7534ce76ee8
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2019
ms.locfileid: "836433"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="c1aaf-103">Sincronizar ordens de trabalho com um projeto do Field Service para o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c1aaf-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c1aaf-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho com um número de projeto do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c1aaf-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="c1aaf-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="c1aaf-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="c1aaf-106">O modelo **Ordens de trabalho com projeto (Field Service para Fin and Ops)** usado é baseado no modelo **Ordens de trabalho (Field Service para Fin and Ops)**.</span><span class="sxs-lookup"><span data-stu-id="c1aaf-106">The used **Work Orders with Project (Field Service to Fin and Ops)** template is based on the **Work Orders (Field Service to Fin and Ops)** template.</span></span> <span data-ttu-id="c1aaf-107">Para obter mais informações, consulte [Sincronizar ordens de trabalho no Field Service com ordens de venda no Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="c1aaf-107">For more information, see [Synchronize work orders in Field Service to sales orders in Finance and Operations](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

<span data-ttu-id="c1aaf-108">Este tópico descreve apenas as diferenças entre os dois métodos:</span><span class="sxs-lookup"><span data-stu-id="c1aaf-108">This topic only describes the differences between the two templates:</span></span>
- <span data-ttu-id="c1aaf-109">**Ordens de trabalho com projeto (Field Service para Fin and Ops)**</span><span class="sxs-lookup"><span data-stu-id="c1aaf-109">**Work Orders with Project (Field Service to Fin and Ops)**</span></span>
- <span data-ttu-id="c1aaf-110">**Ordens de trabalho (Field Service para Fin and Ops)**</span><span class="sxs-lookup"><span data-stu-id="c1aaf-110">**Work Orders (Field Service to Fin and Ops)**</span></span>

<span data-ttu-id="c1aaf-111">A principal diferença é que este modelo inclui mapeamento do número de projeto atribuído à ordem de trabalho no Field Service, garantindo que a ordem de venda criada no Finance and Operations inclua o número de projeto e que o faturamento possa ocorrer no projeto relacionado.</span><span class="sxs-lookup"><span data-stu-id="c1aaf-111">The main difference is that this template includes mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="c1aaf-112">Além disso, este método utiliza Filtragem e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="c1aaf-112">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c1aaf-113">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="c1aaf-113">Templates and tasks</span></span>

<span data-ttu-id="c1aaf-114">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="c1aaf-114">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="c1aaf-115">Ordens de trabalho com projeto (Field Service para Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="c1aaf-115">Work Orders with Project (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="c1aaf-116">**Nome da tarefa no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="c1aaf-116">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="c1aaf-117">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c1aaf-117">WorkOrderHeader</span></span>
- <span data-ttu-id="c1aaf-118">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c1aaf-118">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="c1aaf-119">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c1aaf-119">WorkOrderProduct</span></span>
- <span data-ttu-id="c1aaf-120">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c1aaf-120">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="c1aaf-121">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="c1aaf-121">Field Service CRM solution</span></span>
<span data-ttu-id="c1aaf-122">O campo **Projeto Externo** foi adicionado à entidade Ordem de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="c1aaf-122">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="c1aaf-123">Este campo é uma pesquisa e compra que marca sua ordem de trabalho com um projeto. A ordem de venda será conectada a um projeto no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c1aaf-123">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="c1aaf-124">Quando o **Status do Sistema** mudar de Aberto - Em Andamento (690.970.000) para a um status superior, o campo **Projeto Externo** será bloqueado e você não poderá adicionar, remover ou alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="c1aaf-124">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c1aaf-125">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="c1aaf-125">Template mapping in Data integration</span></span>

<span data-ttu-id="c1aaf-126">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="c1aaf-126">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a><span data-ttu-id="c1aaf-127">Ordens de trabalho com projeto (Field Service para Fin and Ops): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c1aaf-127">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeader</span></span>

<span data-ttu-id="c1aaf-128">[![Mapeamento de modelo na Integração de dados](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="c1aaf-128">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a><span data-ttu-id="c1aaf-129">Ordens de trabalho com projeto (Field Service para Fin and Ops): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c1aaf-129">Work Orders with Project (Field Service to Fin and Ops): WorkOrderHeaderProject</span></span>

<span data-ttu-id="c1aaf-130">[![Mapeamento de modelo na Integração de dados](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="c1aaf-130">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a><span data-ttu-id="c1aaf-131">Ordens de trabalho com projeto (Field Service para Fin and Ops): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c1aaf-131">Work Orders with Project (Field Service to Fin and Ops): WorkOrderProduct</span></span>

<span data-ttu-id="c1aaf-132">[![Mapeamento de modelo na Integração de dados](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="c1aaf-132">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a><span data-ttu-id="c1aaf-133">Ordens de trabalho com projeto (Field Service para Fin and Ops): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c1aaf-133">Work Orders with Project (Field Service to Fin and Ops): WorkOrderService</span></span>

<span data-ttu-id="c1aaf-134">[![Mapeamento de modelo na Integração de dados](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="c1aaf-134">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>
