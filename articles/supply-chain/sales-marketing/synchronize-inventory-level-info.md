---
title: Sincronizar informações em nível de estoque do Finance and Operations no Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar informações no nível do estoque do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: 6b56eb545f87c31ef30d6a897f48539068583486
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843424"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="22687-103">Sincronizar informações do nível de estoque do Finance and Operations no Field Service</span><span class="sxs-lookup"><span data-stu-id="22687-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="22687-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar informações no nível do estoque do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="22687-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="22687-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="22687-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="22687-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="22687-106">Templates and tasks</span></span>
<span data-ttu-id="22687-107">O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização dos níveis de estoque disponível do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="22687-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="22687-108">**Modelo na integração de dados**</span><span class="sxs-lookup"><span data-stu-id="22687-108">**Template in Data integration**</span></span>
- <span data-ttu-id="22687-109">Inventário de Produtos (Fin and Ops com o Field Service)</span><span class="sxs-lookup"><span data-stu-id="22687-109">Product Inventory (Fin and Ops to Field Service)</span></span>
  
<span data-ttu-id="22687-110">**Tarefas no projeto de integração de dados**</span><span class="sxs-lookup"><span data-stu-id="22687-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="22687-111">Estoque de produtos</span><span class="sxs-lookup"><span data-stu-id="22687-111">Product inventory</span></span>

<span data-ttu-id="22687-112">As seguintes tarefas de sincronização são necessárias antes da sincronização de níveis de estoque:</span><span class="sxs-lookup"><span data-stu-id="22687-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="22687-113">Depósitos (Fin and Ops com o Field Service)</span><span class="sxs-lookup"><span data-stu-id="22687-113">Warehouses (Fin and Ops to Field Service)</span></span> 
- <span data-ttu-id="22687-114">Produtos do Field Service com Unidade de estoque (Fin and Ops com o Sales)</span><span class="sxs-lookup"><span data-stu-id="22687-114">Field Service products with Inventory unit (Fin and Ops to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="22687-115">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="22687-115">Entity set</span></span>

| <span data-ttu-id="22687-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="22687-116">Field Service</span></span>                      | <span data-ttu-id="22687-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="22687-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="22687-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="22687-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="22687-119">Estoque disponível por depósito do CDS</span><span class="sxs-lookup"><span data-stu-id="22687-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="22687-120">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="22687-120">Entity flow</span></span>
<span data-ttu-id="22687-121">As informações em nível de estoque do Finance and Operations são envidas para o Field Service para produtos selecionados.</span><span class="sxs-lookup"><span data-stu-id="22687-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="22687-122">As informações em nível de estoque incluem:</span><span class="sxs-lookup"><span data-stu-id="22687-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="22687-123">Quantidade disponível (quantidade física atual registrada localizada no depósito)</span><span class="sxs-lookup"><span data-stu-id="22687-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="22687-124">Na quantidade de ordem (quantidade total registrada na ordem, como ordens de venda)</span><span class="sxs-lookup"><span data-stu-id="22687-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="22687-125">Quantidade solicitada (quantidade total solicitada registrada, como ordens de compra)</span><span class="sxs-lookup"><span data-stu-id="22687-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="22687-126">Essas informações são capturadas por produtos lançados para cada depósito e sincronizados com base no controle de alterações, quando o nível de estoque muda.</span><span class="sxs-lookup"><span data-stu-id="22687-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="22687-127">No Field Service, a solução de integração cria diários de estoque para o delta, para que os níveis no Field Service correspondam aos níveis no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22687-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Finance and Operations.</span></span>

<span data-ttu-id="22687-128">O Finance and Operations funcionará como o mestre para níveis de estoque.</span><span class="sxs-lookup"><span data-stu-id="22687-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="22687-129">Assim, é importante configurar a integração das ordens de trabalho, transferências e ajustes do Field Service para o Finance and Operations se essa funcionalidade for usada no Field Service, junto com a sincronização dos níveis de estoque do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22687-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Finance and Operations if this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="22687-130">Os produtos e os depósitos em que níveis de estoque são dominados do Finance and Operations podem ser controlados com a Filtragem e Consulta Avançada (Power Query).</span><span class="sxs-lookup"><span data-stu-id="22687-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="22687-131">É possível criar vários depósitos no Field Service (com **É mantido externamente = Não**) depois mapeá-los para um único depósito no Finance and Operations, com a funcionalidade Filtragem e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="22687-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="22687-132">Isso é útil em situações em que você deseja que o Field Service domine o nível de estoque detalhado e somente envie atualizações ao Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22687-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Finance and Operations.</span></span> <span data-ttu-id="22687-133">Nesse caso, o Field Service não receberá atualizações em nível de estoque do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22687-133">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="22687-134">Para informações adicionais, consulte [Sincronizar ajustes de estoque do Field Service com o Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizar ordens de trabalho no Field Service com as ordens de vendas vinculadas ao projeto no Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="22687-134">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="22687-135">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="22687-135">Field Service CRM solution</span></span>
<span data-ttu-id="22687-136">A entidade **Estoque externo de produtos** é usada apenas para o back-end na integração.</span><span class="sxs-lookup"><span data-stu-id="22687-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="22687-137">Essa entidade recebe os valores em nível de estoque do Finance and Operations na integração e os transforma em diários de estoque manual, que altera os produtos de estoque no depósito.</span><span class="sxs-lookup"><span data-stu-id="22687-137">This entity receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="22687-138">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="22687-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="22687-139">Integração de dados</span><span class="sxs-lookup"><span data-stu-id="22687-139">Data integration</span></span>
<span data-ttu-id="22687-140">Para que o projeto funcione, você precisa garantir que a chave de integração está atualizada para msdynce_externalproductinventories.</span><span class="sxs-lookup"><span data-stu-id="22687-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="22687-141">Acesse **Integração de dados > Conjuntos de conexão**.</span><span class="sxs-lookup"><span data-stu-id="22687-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="22687-142">Selecione o Conjunto de conexão usado.</span><span class="sxs-lookup"><span data-stu-id="22687-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="22687-143">Na guia **Chave de integração**, certifique-se de que as chaves a seguir são adicionadas ao msdynce_externalproductinventories:</span><span class="sxs-lookup"><span data-stu-id="22687-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="22687-144">msdynce_productnumber (Número do produto)</span><span class="sxs-lookup"><span data-stu-id="22687-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="22687-145">msdynce_warehouseid (ID do depósito)</span><span class="sxs-lookup"><span data-stu-id="22687-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="22687-146">Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="22687-146">Data integration project</span></span>
<span data-ttu-id="22687-147">Você pode aplicar filtros com a Filtragem e Consulta Avançada para que somente determinados produtos e depósitos enviem informações em nível de estoque do Finance and Operations para o Field Service.</span><span class="sxs-lookup"><span data-stu-id="22687-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="22687-148">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="22687-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-fin-and-ops-to-field-service-product-inventory"></a><span data-ttu-id="22687-149">Inventário de produtos (Fin and Ops com o Field Service): Inventário de produtos</span><span class="sxs-lookup"><span data-stu-id="22687-149">Product inventory (Fin and Ops to Field Service): Product inventory</span></span>

<span data-ttu-id="22687-150">[![Mapeamento de modelo na Integração de dados](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="22687-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
