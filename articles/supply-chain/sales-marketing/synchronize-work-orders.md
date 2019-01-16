---
title: Sincronizar ordens de trabalho do Finance and Operations no Field Service
description: "Este tópico discute os modelos e a tarefa subjacente usados para sincronizar ordens de trabalho com um número de projeto do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: f5bd6b8c554688d0d1b2bfd93a34a60a95412bf3
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a><span data-ttu-id="c0b57-103">Sincronizar ordens de trabalho com um projeto do Field Service para o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c0b57-103">Synchronize work orders with project from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c0b57-104">Este tópico discute os modelos e a tarefa subjacente usados para sincronizar ordens de trabalho com um número de projeto do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c0b57-104">This topic discusses the templates and underlying task that are used to synchronize work orders with a project number from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="c0b57-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span><span class="sxs-lookup"><span data-stu-id="c0b57-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)</span></span>

<span data-ttu-id="c0b57-106">O modelo usado **Produtos do Field Service (Finance and Operations para o Field Service)** é baseado no modelo **Produtos (Finance and Operations para o Sales) – Direto** do Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="c0b57-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="c0b57-107">Para obter mais informações, consulte [Produtos (Finance and Operations para o Sales) – Direto](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="c0b57-107">For more information, see [Products (Finance and Operations to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="c0b57-108">Este tópico descreve somente as diferenças entre os modelos **Produtos do Field Service (Finance and Operations para Field Service)** e **Produtos do Field Service (Finance and Operations para Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="c0b57-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

<span data-ttu-id="c0b57-109">A principal diferença é que este modelo inclui mapeamento do número de projeto atribuído à ordem de trabalho no Field Service, garantindo que a ordem de venda criada no Finance and Operations inclua o número de projeto e que o faturamento possa ocorrer no projeto relacionado.</span><span class="sxs-lookup"><span data-stu-id="c0b57-109">The main difference is that this template include mapping of the project number asigned to the Work order in Field Service, ensuring that the Sales order created in Finance and Operations include the project number and that invoicing can happen on the related project.</span></span> <span data-ttu-id="c0b57-110">Além disso, este método utiliza Filtragem e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="c0b57-110">Besides this the template use Advanced Query and Filtering.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c0b57-111">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="c0b57-111">Templates and tasks</span></span>

<span data-ttu-id="c0b57-112">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="c0b57-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="c0b57-113">Ordens de trabalho com projeto (Field Service para Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="c0b57-113">Work Orders with Project (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="c0b57-114">**Nome da tarefa no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="c0b57-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="c0b57-115">WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c0b57-115">WorkOrderHeader</span></span>
- <span data-ttu-id="c0b57-116">WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c0b57-116">WorkOrderHeaderProject</span></span>
- <span data-ttu-id="c0b57-117">WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c0b57-117">WorkOrderProduct</span></span>
- <span data-ttu-id="c0b57-118">WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c0b57-118">WorkOrderService</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="c0b57-119">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="c0b57-119">Field Service CRM solution</span></span>
<span data-ttu-id="c0b57-120">O campo **Projeto Externo** foi adicionado à entidade Ordem de Trabalho.</span><span class="sxs-lookup"><span data-stu-id="c0b57-120">The **External Project** field has been added to the Work Order entity.</span></span> <span data-ttu-id="c0b57-121">Este campo é uma pesquisa e compra que marca sua ordem de trabalho com um projeto. A ordem de venda será conectada a um projeto no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c0b57-121">This field is a lookup and buy tagging your Work Order with a project the Sales Order will then be connected to a Project within Finance and Operations.</span></span> <span data-ttu-id="c0b57-122">Quando o **Status do Sistema** mudar de Aberto - Em Andamento (690,970,000) para a um status superior, o campo **Projeto Externo** será bloqueado e você não poderá adicionar, remover ou alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="c0b57-122">Ones the **System Status** changes from Open – In Progress(690,970,000) to a higher status the **External Project** field will be locked and you can't add, remove or change the value.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c0b57-123">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="c0b57-123">Template mapping in Data integration</span></span>

<span data-ttu-id="c0b57-124">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="c0b57-124">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a><span data-ttu-id="c0b57-125">Ordens de trabalho com projeto (Field Service para Finance and Operations): WorkOrderHeader</span><span class="sxs-lookup"><span data-stu-id="c0b57-125">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeader</span></span>

<span data-ttu-id="c0b57-126">[![Mapeamento de modelo na Integração de dados](./media/FSWOP1.png)](./media/FSWOP1.png)</span><span class="sxs-lookup"><span data-stu-id="c0b57-126">[![Template mapping in Data integration](./media/FSWOP1.png)](./media/FSWOP1.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a><span data-ttu-id="c0b57-127">Ordens de trabalho com projeto (Field Service para Finance and Operations): WorkOrderHeaderProject</span><span class="sxs-lookup"><span data-stu-id="c0b57-127">Work Orders with Project (Field Service to Finance and Operations): WorkOrderHeaderProject</span></span>

<span data-ttu-id="c0b57-128">[![Mapeamento de modelo na Integração de dados](./media/FSWOP2.png)](./media/FSWOP2.png)</span><span class="sxs-lookup"><span data-stu-id="c0b57-128">[![Template mapping in Data integration](./media/FSWOP2.png)](./media/FSWOP2.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a><span data-ttu-id="c0b57-129">Ordens de trabalho com projeto (Field Service para Finance and Operations): WorkOrderProduct</span><span class="sxs-lookup"><span data-stu-id="c0b57-129">Work Orders with Project (Field Service to Finance and Operations): WorkOrderProduct</span></span>

<span data-ttu-id="c0b57-130">[![Mapeamento de modelo na Integração de dados](./media/FSWOP3.png)](./media/FSWOP3.png)</span><span class="sxs-lookup"><span data-stu-id="c0b57-130">[![Template mapping in Data integration](./media/FSWOP3.png)](./media/FSWOP3.png)</span></span>

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a><span data-ttu-id="c0b57-131">Ordens de trabalho com projeto (Field Service para Finance and Operations): WorkOrderService</span><span class="sxs-lookup"><span data-stu-id="c0b57-131">Work Orders with Project (Field Service to Finance and Operations): WorkOrderService</span></span>

<span data-ttu-id="c0b57-132">[![Mapeamento de modelo na Integração de dados](./media/FSWOP4.png)](./media/FSWOP4.png)</span><span class="sxs-lookup"><span data-stu-id="c0b57-132">[![Template mapping in Data integration](./media/FSWOP4.png)](./media/FSWOP4.png)</span></span>

