---
title: "Sincronizar informações em nível de estoque do Finance and Operations no Field Service"
description: "Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar informações em nível de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 3ccc4d406fa4f9800dcdf8697a91892408783196
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="7fc41-103">Sincronizar informações em nível de estoque do Finance and Operations no Field Service</span><span class="sxs-lookup"><span data-stu-id="7fc41-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7fc41-104">Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar informações em nível de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="7fc41-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="7fc41-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="7fc41-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7fc41-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="7fc41-106">Templates and tasks</span></span>
<span data-ttu-id="7fc41-107">O modelo e as tarefas subjacentes a seguir são usados para executar a sincronização de níveis de estoque disponíveis do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="7fc41-107">The following template and underlying tasks are used to run synchronization of inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="7fc41-108">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="7fc41-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="7fc41-109">Estoque de produtos (Finance and Operations para Field Service)</span><span class="sxs-lookup"><span data-stu-id="7fc41-109">Product Inventory (Finance and Operations to Field Service)</span></span>
  
<span data-ttu-id="7fc41-110">**Nomes das tarefas no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="7fc41-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="7fc41-111">Estoque de produtos</span><span class="sxs-lookup"><span data-stu-id="7fc41-111">Product inventory</span></span>

<span data-ttu-id="7fc41-112">As seguintes tarefas de sincronização são necessárias antes da sincronização de níveis de estoque:</span><span class="sxs-lookup"><span data-stu-id="7fc41-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="7fc41-113">Depósitos (Finance and Operations para Field Service)</span><span class="sxs-lookup"><span data-stu-id="7fc41-113">Warehouses (Finance and Operations to Field Service)</span></span> 
- <span data-ttu-id="7fc41-114">Produtos do Field Service com unidade de estoque (Finance and Operations para Sales)</span><span class="sxs-lookup"><span data-stu-id="7fc41-114">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="7fc41-115">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="7fc41-115">Entity set</span></span>

| <span data-ttu-id="7fc41-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="7fc41-116">Field Service</span></span>                      | <span data-ttu-id="7fc41-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7fc41-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="7fc41-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="7fc41-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="7fc41-119">Estoque disponível por depósito do CDS</span><span class="sxs-lookup"><span data-stu-id="7fc41-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="7fc41-120">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="7fc41-120">Entity flow</span></span>
<span data-ttu-id="7fc41-121">As informações em nível de estoque do Finance and Operations são envidas para o Field Service para produtos selecionados.</span><span class="sxs-lookup"><span data-stu-id="7fc41-121">Inventory level information from Finance and Operation is send to Field Service for selected products.</span></span> <span data-ttu-id="7fc41-122">As informações em nível de estoque incluem:</span><span class="sxs-lookup"><span data-stu-id="7fc41-122">The inventory level information include:</span></span> 
- <span data-ttu-id="7fc41-123">Quantidade disponível (quantidade física atual registrada localizada no depósito)</span><span class="sxs-lookup"><span data-stu-id="7fc41-123">On hand quantity (current recorded physically quantity located in the warehouse)</span></span>
- <span data-ttu-id="7fc41-124">Na quantidade de ordem (quantidade total registrada na ordem, ou seja, ordens de venda)</span><span class="sxs-lookup"><span data-stu-id="7fc41-124">On order quantity (total recorded quantity on order - i.e. sales orders)</span></span>
- <span data-ttu-id="7fc41-125">Quantidade solicitada (quantidade total solicitada registrada, ou seja, ordens de compra)</span><span class="sxs-lookup"><span data-stu-id="7fc41-125">Ordered quantity (total recorded ordered quantity - i.e. purchase orders)</span></span>

<span data-ttu-id="7fc41-126">Essas informações são capturadas por produtos lançados para cada depósito e sincronizados com base no controle de alterações, quando o nível de estoque muda.</span><span class="sxs-lookup"><span data-stu-id="7fc41-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="7fc41-127">No Field Service, a solução de integração cria diários de estoque para o delta, a fim de obter níveis no Field Service para corresponder aos níveis no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7fc41-127">In Field Service the integration solution create inventory journals for the delta, to get the levels in Field Service to match the levels in Finance and Operations.</span></span>

<span data-ttu-id="7fc41-128">O Finance and Operations funcionará como o mestre para níveis de estoque.</span><span class="sxs-lookup"><span data-stu-id="7fc41-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="7fc41-129">Isso é importante para a integração de instalação para ordens de trabalho, transferências e ajustes do Field Service to Finance and Operations se essa funcionalidade for usada no Field Service, junto com a sincronização dos níveis de estoque do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7fc41-129">So it is important to setup integration for workorders, transfers and adjustments from Field Service to Finance and Operations if the this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="7fc41-130">Os produtos e os depósitos em que níveis de estoque são dominados do Finance and Operations podem ser controlados com a Filtragem e Consulta Avançada (Power Query).</span><span class="sxs-lookup"><span data-stu-id="7fc41-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

<span data-ttu-id="7fc41-131">Observação: É possível criar vários depósitos no Field Services (com É mantido externamente = Não) e depois mapeá-los para um único depósito no Finance and Operations, a funcionalidade Filtragem e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="7fc41-131">Note: It is possible to create multiple warehouses in Field Services (with Is Externally Maintained = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="7fc41-132">Isso é útil em situações em que você deseja que o Field service domine o nível de estoque detalhado e envie apenas atualizações para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7fc41-132">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="7fc41-133">Nesse caso, o Field Service não receberá atualizações em nível de estoque do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7fc41-133">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="7fc41-134">Consulte as informações adicionais em Sincronizar ajustes de inventário do Field Service para o Finance and Operations e Sincronizar ordens de trabalho no Field Service para ordens de venda vinculadas ao projeto no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7fc41-134">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="7fc41-135">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="7fc41-135">Field Service CRM solution</span></span>
<span data-ttu-id="7fc41-136">A entidade Estoque Externo de Produtos é uma nova entidade que é usada apenas para o back-end na integração.</span><span class="sxs-lookup"><span data-stu-id="7fc41-136">The External Product Inventory entity is a new entity that’s only used for backend in the integration.</span></span> <span data-ttu-id="7fc41-137">Ela recebe os valores em nível de estoque do Finance and Operations na integração e transforma esses valores em diários de Estoque Manual, que altera os produtos de estoque no depósito.</span><span class="sxs-lookup"><span data-stu-id="7fc41-137">It receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manuel Inventory journals, that then changes the Inventory Products on the Warehouse.</span></span> 

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="7fc41-138">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="7fc41-138">Prerequisites and mapping setup</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="7fc41-139">No Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="7fc41-139">In the Data Integration project</span></span>
<span data-ttu-id="7fc41-140">Aplique filtros à Filtragem e Consulta Avançada para controlar que somente produtos e depósitos desejados enviam informações em nível de estoque do Finance and Operations para o Field Service.</span><span class="sxs-lookup"><span data-stu-id="7fc41-140">Apply filters with the Advanced  Query and Filtering to control that only desired products and warehouses send inventory level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7fc41-141">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="7fc41-141">Template mapping in Data integration</span></span>

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a><span data-ttu-id="7fc41-142">Estoque de produtos (Finance and Operations para Field Service): estoque de produtos</span><span class="sxs-lookup"><span data-stu-id="7fc41-142">Product Inventory (Finance and Operations to Field Service): Product inventory</span></span>

<span data-ttu-id="7fc41-143">[![Mapeamento de modelo na Integração de dados](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="7fc41-143">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>

