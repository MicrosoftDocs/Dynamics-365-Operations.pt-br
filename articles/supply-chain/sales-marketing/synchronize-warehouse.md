---
title: Sincronizar depósitos do Finance and Operations para o Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 7e6d7626c00b9d7d98ce872652653c36ce7bc975
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "842524"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="611e6-103">Sincronizar depósitos do Finance and Operations no Field Service</span><span class="sxs-lookup"><span data-stu-id="611e6-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="611e6-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="611e6-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="611e6-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="611e6-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="611e6-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="611e6-106">Templates and tasks</span></span>
<span data-ttu-id="611e6-107">O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização de depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="611e6-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="611e6-108">**Modelo na integração de dados**</span><span class="sxs-lookup"><span data-stu-id="611e6-108">**Template in Data integration**</span></span>
- <span data-ttu-id="611e6-109">Depósitos (Fin and Ops com o Field Service)</span><span class="sxs-lookup"><span data-stu-id="611e6-109">Warehouses (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="611e6-110">**Tarefas no projeto de integração de dados**</span><span class="sxs-lookup"><span data-stu-id="611e6-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="611e6-111">Depósito</span><span class="sxs-lookup"><span data-stu-id="611e6-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="611e6-112">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="611e6-112">Entity set</span></span>
| <span data-ttu-id="611e6-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="611e6-113">Field Service</span></span>    | <span data-ttu-id="611e6-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="611e6-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="611e6-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="611e6-115">msdyn_warehouses</span></span> | <span data-ttu-id="611e6-116">Depósitos</span><span class="sxs-lookup"><span data-stu-id="611e6-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="611e6-117">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="611e6-117">Entity flow</span></span>
<span data-ttu-id="611e6-118">Os depósitos criados e mantidos no Finance and Operations podem ser sincronizados com o Field Service por meio de um projeto de integração de dados CDS (Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="611e6-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="611e6-119">Os depósitos que você quer sincronizar com o Field Service podem ser controlados com a Filtragem e consulta avançada no projeto.</span><span class="sxs-lookup"><span data-stu-id="611e6-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="611e6-120">Os depósitos sincronizados do Finance and Operations são criados no Field Service com o campo **É mantido externamente** definido como **Sim** e o registro torna-se somente leitura.</span><span class="sxs-lookup"><span data-stu-id="611e6-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="611e6-121">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="611e6-121">Field Service CRM solution</span></span>
<span data-ttu-id="611e6-122">Para oferecer suporte à integração entre o Field Service e o Finance and Operations, a funcionalidade adicional da solução Field Service do CRM é necessária.</span><span class="sxs-lookup"><span data-stu-id="611e6-122">To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="611e6-123">Na solução, o campo **É mantido externamente** foi adicionado à entidade **Depósito (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="611e6-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="611e6-124">Este campo ajuda a identificar se o depósito é tratado no Finance and Operations ou se ele só existe no Field Service.</span><span class="sxs-lookup"><span data-stu-id="611e6-124">This field helps to identify if the warehouse is handled from Finance and Operations or if it only exists in Field Service.</span></span> <span data-ttu-id="611e6-125">As configurações desse campo são:</span><span class="sxs-lookup"><span data-stu-id="611e6-125">The settings for this field include:</span></span>
- <span data-ttu-id="611e6-126">**Sim** – O depósito foi originado do Finance and Operations e não será editável no Sales.</span><span class="sxs-lookup"><span data-stu-id="611e6-126">**Yes** – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="611e6-127">**Não** – o depósito foi inserido diretamente no Field Service e é mantido aqui.</span><span class="sxs-lookup"><span data-stu-id="611e6-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="611e6-128">O campo **É mantido externamente** ajuda a controlar a sincronização dos níveis de estoque, ajustes, transferências e uso em ordens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="611e6-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="611e6-129">Somente os depósitos com **É mantido externamente** definido como **Sim** podem ser usados para sincronizar diretamente com o mesmo depósito no outro sistema.</span><span class="sxs-lookup"><span data-stu-id="611e6-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="611e6-130">É possível criar vários depósitos no Field Service (com **É mantido externamente** = Não) e depois mapeá-los para um único depósito no Finance and Operations, com a funcionalidade Filtragem e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="611e6-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="611e6-131">Isso é útil em situações em que você deseja que o Field Service domine o nível de estoque detalhado e envie apenas atualizações ao Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="611e6-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="611e6-132">Nesse caso, o Field Service não receberá atualizações em nível de estoque do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="611e6-132">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="611e6-133">Para informações adicionais, consulte [Sincronizar ajustes de estoque do Field Service com o Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizar ordens de trabalho no Field Service com as ordens de vendas vinculadas ao projeto no Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="611e6-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="611e6-134">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="611e6-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="611e6-135">Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="611e6-135">Data Integration project</span></span>
<span data-ttu-id="611e6-136">Antes de sincronizar depósitos , verifique se você atualizou a Filtragem e consulta avançada no projeto para incluir apenas os depósitos que você deseja trazer do Finance and Operations para o Field Service.</span><span class="sxs-lookup"><span data-stu-id="611e6-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="611e6-137">Observe que você precisará do depósito no Field Service para aplicá-lo em ordens de trabalho, ajustes e transferências.</span><span class="sxs-lookup"><span data-stu-id="611e6-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="611e6-138">Para garantir que a **Chave de integração** exista para **msdyn_warehouses**:</span><span class="sxs-lookup"><span data-stu-id="611e6-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="611e6-139">Vá para Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="611e6-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="611e6-140">Selecione a guia **Conjunto de conexão**.</span><span class="sxs-lookup"><span data-stu-id="611e6-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="611e6-141">Selecione o conjunto de conexão usado para a sincronização da ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="611e6-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="611e6-142">Selecione a guia **Chave de integração**.</span><span class="sxs-lookup"><span data-stu-id="611e6-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="611e6-143">Localize msdyn_warehouses e verifique se a chave **msdyn_name (nome)** foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="611e6-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="611e6-144">Se não for exibida, adicione-a clicando em **Adicionar chave** e clique em **Salvar**, na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="611e6-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="611e6-145">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="611e6-145">Template mapping in Data integration</span></span>

<span data-ttu-id="611e6-146">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="611e6-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-fin-and-ops-to-field-service-warehouse"></a><span data-ttu-id="611e6-147">Depósitos (Fin and Ops com o Field Service): Depósito</span><span class="sxs-lookup"><span data-stu-id="611e6-147">Warehouses (Fin and Ops to Field Service): Warehouse</span></span>

<span data-ttu-id="611e6-148">[![Mapeamento de modelo na Integração de dados](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="611e6-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
