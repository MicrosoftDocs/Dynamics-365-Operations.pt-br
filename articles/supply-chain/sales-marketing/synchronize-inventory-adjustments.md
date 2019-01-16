---
title: "Sincronizar transferências e ajustes de estoque do Field Service para o Finance and Operations"
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes de inventário e transferências do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="64601-103">Sincronizar ajustes de estoque do Field Service para o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="64601-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="64601-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes de inventário e transferências do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="64601-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="64601-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="64601-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="64601-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="64601-106">Templates and tasks</span></span>
<span data-ttu-id="64601-107">O modelo e as tarefas subjacentes a seguir são usados para executar a sincronização de ajustes e transferências de estoque do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="64601-107">The following template and underlying tasks are used to run synchronization of inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="64601-108">**Nome dos modelos na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="64601-108">**Name of the templates in Data integration:**</span></span>
- <span data-ttu-id="64601-109">Ajuste de inventário (Field Service para Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="64601-109">Inventory Adjustment (Field Service to Finance and Operations)</span></span>
- <span data-ttu-id="64601-110">Transferências de inventário (Field Service para Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="64601-110">Inventory Transfers (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="64601-111">**Nomes das tarefas em projetos de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="64601-111">**Names of the tasks in the Data integration projects:**</span></span>
- <span data-ttu-id="64601-112">Ajustes de estoque</span><span class="sxs-lookup"><span data-stu-id="64601-112">Inventory Adjustments</span></span>
- <span data-ttu-id="64601-113">Transferências de estoque</span><span class="sxs-lookup"><span data-stu-id="64601-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="64601-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="64601-114">Entity set</span></span>
| <span data-ttu-id="64601-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="64601-115">Field Service</span></span>                     | <span data-ttu-id="64601-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="64601-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="64601-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="64601-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="64601-118">Cabeçalhos e linhas do diário de ajuste de estoque do CDS</span><span class="sxs-lookup"><span data-stu-id="64601-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="64601-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="64601-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="64601-120">Cabeçalhos e linhas do diário de transferência de estoque do CDS</span><span class="sxs-lookup"><span data-stu-id="64601-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="64601-121">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="64601-121">Entity flow</span></span>
<span data-ttu-id="64601-122">Os ajustes e transferências de estoque realizados no Field Service serão sincronizados para o Finance and Operations, após o **Status de lançamento** mudar para Criado para Lançado.</span><span class="sxs-lookup"><span data-stu-id="64601-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations, once the **Post status** is changed from Created to Posted.</span></span> <span data-ttu-id="64601-123">Quando isso acontecer, a ordem de ajuste ou de transferência será bloqueada e ficará somente leitura, pois os ajustes e as transferências podem ser lançados no Finance and Operations e, portanto, não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="64601-123">When this happen the adjustment or transfer order will be locked and become read-only, as adjustments and transfers might be posted in Finance and Operations and therefor can't be modified.</span></span>
<span data-ttu-id="64601-124">No Finance and Operations, é possível configurar um trabalho em lotes para lançar automaticamente os ajustes e transferir diários de estoque gerados com a integração.</span><span class="sxs-lookup"><span data-stu-id="64601-124">In Finance and Operations you can setup a batch job to automatically post the adjustments and transfer inventory journals generated with the integration.</span></span> <span data-ttu-id="64601-125">Veja os pré-requisitos a seguir para obter detalhes sobre como habilitar o trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="64601-125">See prerequisite below for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="64601-126">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="64601-126">Field Service CRM solution</span></span> 
<span data-ttu-id="64601-127">O campo Unidade de estoque foi adicionado à entidade Produto.</span><span class="sxs-lookup"><span data-stu-id="64601-127">The Inventory Unit field has been added to the Product entity.</span></span> <span data-ttu-id="64601-128">Este campo é necessário pois a unidade de vendas e estoque não é sempre na mesma em Operations. Para o estoque de depósito em operações, precisamos da unidade de estoque.</span><span class="sxs-lookup"><span data-stu-id="64601-128">This field is needed since the Sales and Inventory Unit is not always the same in Operations, and for the Warehouse Inventory in operations we need the Inventory Unit.</span></span>
<span data-ttu-id="64601-129">Quando você definir o produto em um produto de ajuste de estoque para os ajustes de estoque e as transferências de estoque, a unidade será obtida do valor de produto do estoque do produto.</span><span class="sxs-lookup"><span data-stu-id="64601-129">When you set the Product on an Inventory Adjustment Product for both Inventory Adjustments and Inventory Transfers the Unit will be fetched from the Products Inventory Product value.</span></span> <span data-ttu-id="64601-130">Se um valor for encontrado, o campo Unidade será bloqueado no produto de ajuste de estoque</span><span class="sxs-lookup"><span data-stu-id="64601-130">If a value is found the Unit field will be locked on the Inventory Adjustment Product</span></span>

<span data-ttu-id="64601-131">O campo de status de lançamento foi adicionado à entidade de ajuste estoque e à entidade de transferência de estoque.</span><span class="sxs-lookup"><span data-stu-id="64601-131">The Post Status field has been added to both the Inventory Adjustment entity and the Inventory Transfer entity.</span></span> <span data-ttu-id="64601-132">Este campo é usado como um filtro para quando um ajuste ou uma transferência é enviada para Operations.</span><span class="sxs-lookup"><span data-stu-id="64601-132">This field is used as a filter for when a adjustment or transfer is sent to Operations.</span></span> <span data-ttu-id="64601-133">O campo é usado como padrão para Criado (1) e não é enviado para Operations.</span><span class="sxs-lookup"><span data-stu-id="64601-133">The field is defaulted to Created (1) and its then not sent over to Operations.</span></span> <span data-ttu-id="64601-134">Se você mudar para Lançado (2), ele será enviado para operações, mas você não poderá mais fazer alterações no ajuste ou na transferência, nem adicionar novas linhas.</span><span class="sxs-lookup"><span data-stu-id="64601-134">Ones you change is to Posted (2) It is sent over to operations, but you will then no longer be able to change anything in the Adjustment or Transfer or add any new lines to it.</span></span>
<span data-ttu-id="64601-135">O campo Sequência Numérica foi adicionado à entidade Produto de Ajuste de Estoque.</span><span class="sxs-lookup"><span data-stu-id="64601-135">The Number Sequence field has been added to the Inventory Adjustment Product entity.</span></span> <span data-ttu-id="64601-136">Este campo ajuda a integração a ter um número exclusivo; assim, a integração sabe quando criar e quando fazer atualizações.</span><span class="sxs-lookup"><span data-stu-id="64601-136">This field helps the integration to have a Unique number, so the integration knows when to do creates and when to do updates.</span></span> <span data-ttu-id="64601-137">Quando você criar o primeiro produto de ajuste de estoque, ele criará um registro na entidade P2C AutoNumber para manter a série de número e o prefixo usado.</span><span class="sxs-lookup"><span data-stu-id="64601-137">When you create your first Inventory Adjustment Product it will create a new record in the P2C AutoNumber entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="64601-138">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="64601-138">Prerequisites and mapping setup</span></span>

### <a name="in-finance-and-operations"></a><span data-ttu-id="64601-139">No Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="64601-139">In Finance and Operations</span></span>
<span data-ttu-id="64601-140">Os diários de estoque de integração gerados pela integração podem ser lançados automaticamente com um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="64601-140">The integration inventory journals generated by the integration can automatically be posted with a batch job.</span></span> <span data-ttu-id="64601-141">Isso é habilitado de: Gerenciamento de estoque > Tarefas periódicas > Integração de CDs > Diários de estoque após a integração</span><span class="sxs-lookup"><span data-stu-id="64601-141">This is enabled from: Inventory management > Periodic tasks > CDS integration > Post integration inventory journals</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="64601-142">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="64601-142">Template mapping in Data integration</span></span>

<span data-ttu-id="64601-143">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="64601-143">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a><span data-ttu-id="64601-144">Ajuste de estoque (Field Service para Finance and Operations): ajuste de estoque</span><span class="sxs-lookup"><span data-stu-id="64601-144">Inventory Adjustment (Field Service to Finance and Operations): Inventory Adjustment</span></span>

<span data-ttu-id="64601-145">[![Mapeamento de modelo na Integração de dados](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="64601-145">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a><span data-ttu-id="64601-146">Transferência de estoque (Field Service para Finance and Operations): transferência de estoque</span><span class="sxs-lookup"><span data-stu-id="64601-146">Inventory Transfer (Field Service to Finance and Operations): Inventory Transfer</span></span>

<span data-ttu-id="64601-147">[![Mapeamento de modelo na Integração de dados](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="64601-147">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>

