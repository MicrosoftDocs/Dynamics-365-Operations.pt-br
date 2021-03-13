---
title: Sincronizar informações do nível de estoque do Supply Chain Management com o Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar informações no nível do estoque do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 828dd1324c2692b7b3f4bc15c5e50b3dbee8b72c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010913"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a><span data-ttu-id="225ba-103">Sincronizar informações do nível de estoque do Supply Chain Management com o Field Service</span><span class="sxs-lookup"><span data-stu-id="225ba-103">Synchronize inventory level information from Supply Chain Management to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="225ba-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar informações no nível do estoque do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="225ba-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="225ba-105">[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="225ba-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="225ba-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="225ba-106">Templates and tasks</span></span>
<span data-ttu-id="225ba-107">O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização dos níveis de estoque disponível do Supply Chain Management com o Field Service.</span><span class="sxs-lookup"><span data-stu-id="225ba-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="225ba-108">**Modelo na integração de dados**</span><span class="sxs-lookup"><span data-stu-id="225ba-108">**Template in Data integration**</span></span>
- <span data-ttu-id="225ba-109">Estoque de produtos (Supply Chain Management para Field Service)</span><span class="sxs-lookup"><span data-stu-id="225ba-109">Product Inventory (Supply Chain Management to Field Service)</span></span>
  
<span data-ttu-id="225ba-110">**Tarefas no projeto de integração de dados**</span><span class="sxs-lookup"><span data-stu-id="225ba-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="225ba-111">Estoque de produtos</span><span class="sxs-lookup"><span data-stu-id="225ba-111">Product inventory</span></span>

<span data-ttu-id="225ba-112">As seguintes tarefas de sincronização são necessárias antes da sincronização de níveis de estoque:</span><span class="sxs-lookup"><span data-stu-id="225ba-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="225ba-113">Depósitos (Supply Chain Management para Field Service)</span><span class="sxs-lookup"><span data-stu-id="225ba-113">Warehouses (Supply Chain Management to Field Service)</span></span> 
- <span data-ttu-id="225ba-114">Produtos do Field Service com Unidade de estoque (Supply Chain Management para Sales)</span><span class="sxs-lookup"><span data-stu-id="225ba-114">Field Service products with Inventory unit (Supply Chain Management to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="225ba-115">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="225ba-115">Entity set</span></span>

| <span data-ttu-id="225ba-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="225ba-116">Field Service</span></span>                      | <span data-ttu-id="225ba-117">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="225ba-117">Supply Chain Management</span></span>                |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="225ba-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="225ba-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="225ba-119">Estoque disponível por depósito do Dataverse</span><span class="sxs-lookup"><span data-stu-id="225ba-119">Dataverse inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="225ba-120">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="225ba-120">Entity flow</span></span>
<span data-ttu-id="225ba-121">As informações em nível de estoque do Finance and Operations são envidas para o Field Service para produtos selecionados.</span><span class="sxs-lookup"><span data-stu-id="225ba-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="225ba-122">As informações em nível de estoque incluem:</span><span class="sxs-lookup"><span data-stu-id="225ba-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="225ba-123">Quantidade disponível (quantidade física atual registrada localizada no depósito)</span><span class="sxs-lookup"><span data-stu-id="225ba-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="225ba-124">Na quantidade de ordem (quantidade total registrada na ordem, como ordens de venda)</span><span class="sxs-lookup"><span data-stu-id="225ba-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="225ba-125">Quantidade solicitada (quantidade total solicitada registrada, como ordens de compra)</span><span class="sxs-lookup"><span data-stu-id="225ba-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="225ba-126">Essas informações são capturadas por produtos lançados para cada depósito e sincronizados com base no controle de alterações, quando o nível de estoque muda.</span><span class="sxs-lookup"><span data-stu-id="225ba-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="225ba-127">No Field Service, a solução de integração cria diários de estoque para o delta, para que os níveis no Field Service correspondam aos níveis no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="225ba-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Supply Chain Management.</span></span>

<span data-ttu-id="225ba-128">O Supply Chain Management funcionará como o mestre para níveis de estoque.</span><span class="sxs-lookup"><span data-stu-id="225ba-128">Supply Chain Management will act as the master for inventory levels.</span></span> <span data-ttu-id="225ba-129">Assim, é importante configurar a integração das ordens de serviço, transferências e ajustes do Field Service para o Supply Chain Management se essa funcionalidade for usada no Field Service, junto com a sincronização dos níveis de estoque do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="225ba-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Supply Chain Management if this functionality is used in Field Service, together with synchronization of inventory levels from Supply Chain Management.</span></span>

<span data-ttu-id="225ba-130">Os produtos e os depósitos em que níveis de estoque são dominados do Supply Chain Management podem ser controlados com a Filtragem e Consulta Avançada (Power Query).</span><span class="sxs-lookup"><span data-stu-id="225ba-130">The products and warehouses where inventory levels are mastered from Supply Chain Management can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="225ba-131">É possível criar vários depósitos no Field Service (com **É mantido externamente = Não**) depois mapeá-los para um único depósito no Supply Chain Management, com a funcionalidade Filtragem e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="225ba-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Supply Chain Management, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="225ba-132">Isso é útil em situações em que você deseja que o Field Service domine o nível de estoque detalhado e somente envie atualizações ao Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="225ba-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Supply Chain Management.</span></span> <span data-ttu-id="225ba-133">Nesse caso, o Field Service não receberá atualizações em nível de estoque do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="225ba-133">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="225ba-134">Para obter informações adicionais, consulte [Sincronizar ajustes de estoque do Field Service com o Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizar ordens de serviço no Field Service com as ordens de vendas vinculadas ao projeto no Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="225ba-134">For additional information, see [Synchronize inventory adjustments from Field Service to Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="225ba-135">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="225ba-135">Field Service CRM solution</span></span>
<span data-ttu-id="225ba-136">A entidade **Estoque externo de produtos** é usada apenas para o back-end na integração.</span><span class="sxs-lookup"><span data-stu-id="225ba-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="225ba-137">Essa entidade recebe os valores em nível de estoque do Supply Chain Management na integração e os transforma em diários de estoque manual, que altera os produtos de estoque no depósito.</span><span class="sxs-lookup"><span data-stu-id="225ba-137">This entity receives the inventory level values from Supply Chain Management in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="225ba-138">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="225ba-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="225ba-139">Integração de dados</span><span class="sxs-lookup"><span data-stu-id="225ba-139">Data integration</span></span>
<span data-ttu-id="225ba-140">Para que o projeto funcione, você precisa garantir que a chave de integração está atualizada para msdynce_externalproductinventories.</span><span class="sxs-lookup"><span data-stu-id="225ba-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="225ba-141">Acesse **Integração de dados > Conjuntos de conexão**.</span><span class="sxs-lookup"><span data-stu-id="225ba-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="225ba-142">Selecione o Conjunto de conexão usado.</span><span class="sxs-lookup"><span data-stu-id="225ba-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="225ba-143">Na guia **Chave de integração**, certifique-se de que as chaves a seguir são adicionadas ao msdynce_externalproductinventories:</span><span class="sxs-lookup"><span data-stu-id="225ba-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="225ba-144">msdynce_productnumber (Número do produto)</span><span class="sxs-lookup"><span data-stu-id="225ba-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="225ba-145">msdynce_warehouseid (ID do depósito)</span><span class="sxs-lookup"><span data-stu-id="225ba-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="225ba-146">Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="225ba-146">Data integration project</span></span>
<span data-ttu-id="225ba-147">Você pode aplicar filtros com a Filtragem e consulta avançada para que somente determinados produtos e depósitos enviem informações em nível de estoque do Supply Chain Management para o Field Service.</span><span class="sxs-lookup"><span data-stu-id="225ba-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Supply Chain Management to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="225ba-148">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="225ba-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a><span data-ttu-id="225ba-149">Estoque de produtos (Supply Chain Management para Field Service): Estoque de produtos</span><span class="sxs-lookup"><span data-stu-id="225ba-149">Product inventory (Supply Chain Management to Field Service): Product inventory</span></span>

<span data-ttu-id="225ba-150">[![Mapeamento de modelo na Integração de dados](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="225ba-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
