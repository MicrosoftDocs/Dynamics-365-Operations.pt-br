---
title: Sincronizar depósitos do Supply Chain Management com o Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar depósitos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
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
ms.openlocfilehash: 0c0c1bafb5b36bb9ddc00061e0040a199c8c033d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010838"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a><span data-ttu-id="60dc8-103">Sincronizar depósitos do Supply Chain Management com o Field Service</span><span class="sxs-lookup"><span data-stu-id="60dc8-103">Synchronize warehouses from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="60dc8-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar depósitos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="60dc8-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="60dc8-105">[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="60dc8-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="60dc8-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="60dc8-106">Templates and tasks</span></span>
<span data-ttu-id="60dc8-107">O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização de depósitos do Supply Chain Management com o Field Service.</span><span class="sxs-lookup"><span data-stu-id="60dc8-107">The following template and underlying tasks are used to run synchronization of warehouses from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="60dc8-108">**Modelo na integração de dados**</span><span class="sxs-lookup"><span data-stu-id="60dc8-108">**Template in Data integration**</span></span>
- <span data-ttu-id="60dc8-109">Depósitos (Supply Chain Management para Field Service)</span><span class="sxs-lookup"><span data-stu-id="60dc8-109">Warehouses (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="60dc8-110">**Tarefas no projeto de integração de dados**</span><span class="sxs-lookup"><span data-stu-id="60dc8-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="60dc8-111">Depósito</span><span class="sxs-lookup"><span data-stu-id="60dc8-111">Warehouse</span></span>

## <a name="table-set"></a><span data-ttu-id="60dc8-112">Conjunto de tabelas</span><span class="sxs-lookup"><span data-stu-id="60dc8-112">Table set</span></span>
| <span data-ttu-id="60dc8-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="60dc8-113">Field Service</span></span>    | <span data-ttu-id="60dc8-114">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="60dc8-114">Supply Chain Management</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="60dc8-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="60dc8-115">msdyn_warehouses</span></span> | <span data-ttu-id="60dc8-116">Depósitos</span><span class="sxs-lookup"><span data-stu-id="60dc8-116">Warehouses</span></span>                             |

## <a name="table-flow"></a><span data-ttu-id="60dc8-117">Fluxo de tabelas</span><span class="sxs-lookup"><span data-stu-id="60dc8-117">Table flow</span></span>
<span data-ttu-id="60dc8-118">Os depósitos criados e mantidos no Supply Chain Management podem ser sincronizados com o Field Service por meio de um projeto de integração de dados do Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="60dc8-118">Warehouses that are created and maintained in Supply Chain Management can be synchronized to Field Service via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="60dc8-119">Os depósitos que você quer sincronizar com o Field Service podem ser controlados com a Filtragem e consulta avançada no projeto.</span><span class="sxs-lookup"><span data-stu-id="60dc8-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="60dc8-120">Os depósitos sincronizados do Supply Chain Management são criados no Field Service com a coluna **É mantido externamente** definida como **Sim**, e o registro é somente leitura.</span><span class="sxs-lookup"><span data-stu-id="60dc8-120">Warehouses that synchronize from Supply Chain Management are created in Field Service with the **Is maintained externally** column set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="60dc8-121">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="60dc8-121">Field Service CRM solution</span></span>
<span data-ttu-id="60dc8-122">Para oferecer suporte à integração entre o Field Service e o Supply Chain Management, a funcionalidade adicional da solução Field Service CRM é necessária.</span><span class="sxs-lookup"><span data-stu-id="60dc8-122">To support the integration between Field Service and Supply Chain Management, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="60dc8-123">Na solução, a coluna **É mantido externamente** foi adicionada à tabela **Depósito (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="60dc8-123">In the solution, the **Is Maintained Externally** column has been added to the **Warehouse (msdyn_warehouses)** table.</span></span> <span data-ttu-id="60dc8-124">Esta coluna ajuda a identificar se o depósito é tratado no Supply Chain Management ou se ele só existe no Field Service.</span><span class="sxs-lookup"><span data-stu-id="60dc8-124">This column helps to identify if the warehouse is handled from Supply Chain Management or if it only exists in Field Service.</span></span> <span data-ttu-id="60dc8-125">As configurações dessa coluna são:</span><span class="sxs-lookup"><span data-stu-id="60dc8-125">The settings for this column include:</span></span>
- <span data-ttu-id="60dc8-126">**Sim** – O depósito foi originado do Supply Chain Management e não será editável no Sales.</span><span class="sxs-lookup"><span data-stu-id="60dc8-126">**Yes** – The warehouse originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="60dc8-127">**Não** – o depósito foi inserido diretamente no Field Service e é mantido aqui.</span><span class="sxs-lookup"><span data-stu-id="60dc8-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="60dc8-128">A coluna **É mantido externamente** ajuda a controlar a sincronização de níveis, ajustes, transferências e uso de estoque em ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="60dc8-128">The **Is Externally Maintained** column helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="60dc8-129">Somente os depósitos com **É mantido externamente** definido como **Sim** podem ser usados para sincronizar diretamente com o mesmo depósito no outro sistema.</span><span class="sxs-lookup"><span data-stu-id="60dc8-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="60dc8-130">É possível criar vários depósitos no Field Service (com **É mantido externamente** = Não) e depois mapeá-los para um único depósito, com a funcionalidade Filtragem e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="60dc8-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="60dc8-131">Isso é útil em situações em que você deseja que o Field Service domine o nível de estoque detalhado e apenas envie atualizações ao Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="60dc8-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Supply Chain Management.</span></span> <span data-ttu-id="60dc8-132">Nesse caso, o Field Service não receberá atualizações em nível de estoque do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="60dc8-132">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="60dc8-133">Para informações adicionais, consulte [Sincronizar ajustes de estoque do Field Service com o Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizar ordens de trabalho no Field Service com as ordens de vendas vinculadas ao projeto no Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="60dc8-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="60dc8-134">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="60dc8-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="60dc8-135">Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="60dc8-135">Data Integration project</span></span>
<span data-ttu-id="60dc8-136">Antes de sincronizar depósitos , verifique se você atualizou a Filtragem e consulta avançada no projeto para incluir apenas os depósitos que você deseja trazer do Supply Chain Management para o Field Service.</span><span class="sxs-lookup"><span data-stu-id="60dc8-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Supply Chain Management to Field Service.</span></span> <span data-ttu-id="60dc8-137">Observe que você precisará do depósito no Field Service para aplicá-lo em ordens de trabalho, ajustes e transferências.</span><span class="sxs-lookup"><span data-stu-id="60dc8-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="60dc8-138">Para garantir que a **Chave de integração** exista para **msdyn_warehouses**:</span><span class="sxs-lookup"><span data-stu-id="60dc8-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="60dc8-139">Vá para Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="60dc8-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="60dc8-140">Selecione a guia **Conjunto de conexão**.</span><span class="sxs-lookup"><span data-stu-id="60dc8-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="60dc8-141">Selecione o conjunto de conexão usado para a sincronização da ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="60dc8-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="60dc8-142">Selecione a guia **Chave de integração**.</span><span class="sxs-lookup"><span data-stu-id="60dc8-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="60dc8-143">Localize msdyn_warehouses e verifique se a chave **msdyn_name (nome)** foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="60dc8-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="60dc8-144">Se não for exibida, adicione-a clicando em **Adicionar chave** e clique em **Salvar**, na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="60dc8-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="60dc8-145">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="60dc8-145">Template mapping in Data integration</span></span>

<span data-ttu-id="60dc8-146">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="60dc8-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a><span data-ttu-id="60dc8-147">Depósitos (Supply Chain Management para Field Service): Depósito</span><span class="sxs-lookup"><span data-stu-id="60dc8-147">Warehouses (Supply Chain Management to Field Service): Warehouse</span></span>

<span data-ttu-id="60dc8-148">[![Mapeamento de modelo na Integração de dados](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="60dc8-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
