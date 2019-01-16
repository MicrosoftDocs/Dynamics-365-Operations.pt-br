---
title: "Sincronizar depósitos do Finance and Operations para o Field Service"
description: "Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
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
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="c2c23-103">Sincronizar depósitos do Finance and Operations para o Field Service</span><span class="sxs-lookup"><span data-stu-id="c2c23-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c2c23-104">Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="c2c23-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="c2c23-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="c2c23-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c2c23-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="c2c23-106">Templates and tasks</span></span>
<span data-ttu-id="c2c23-107">O modelo e as tarefas subjacentes a seguir são usados para executar a sincronização de depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="c2c23-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="c2c23-108">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="c2c23-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="c2c23-109">Depósitos (Finance and Operations para Field Service)</span><span class="sxs-lookup"><span data-stu-id="c2c23-109">Warehouses (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="c2c23-110">**Nomes das tarefas no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="c2c23-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="c2c23-111">Depósito</span><span class="sxs-lookup"><span data-stu-id="c2c23-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="c2c23-112">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="c2c23-112">Entity set</span></span>
| <span data-ttu-id="c2c23-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="c2c23-113">Field Service</span></span>    | <span data-ttu-id="c2c23-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c2c23-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="c2c23-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="c2c23-115">msdyn_warehouses</span></span> | <span data-ttu-id="c2c23-116">Depósitos</span><span class="sxs-lookup"><span data-stu-id="c2c23-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="c2c23-117">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="c2c23-117">Entity flow</span></span>
<span data-ttu-id="c2c23-118">Os depósitos criados e mantidos no Finance and Operations podem ser sincronizados com o Field Service por meio de um projeto de integração de dados CDS (Common Data Service).</span><span class="sxs-lookup"><span data-stu-id="c2c23-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="c2c23-119">Os depósitos desejados que são sincronizados com o Field Service podem ser controlados com a Filtragem e consulta avançada no projeto.</span><span class="sxs-lookup"><span data-stu-id="c2c23-119">The desired warehouses that synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="c2c23-120">Os depósitos sincronizados do Finance and Operations são criados no Field Service com o campo mantido externamente definido como Sim e o registro torna-se somente leitura.</span><span class="sxs-lookup"><span data-stu-id="c2c23-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the field Is maintained externally set to Yes and the record is made read only.</span></span>
<span data-ttu-id="c2c23-121">Solução Field Service CRM: Para dar suporte à integração entre o Field Service e o Finance and Operations, a funcionalidade adicional da solução Field Service CRM é necessária.</span><span class="sxs-lookup"><span data-stu-id="c2c23-121">Field Service CRM solution To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="c2c23-122">A solução inclui as alterações a seguir.</span><span class="sxs-lookup"><span data-stu-id="c2c23-122">The solution includes the following changes.</span></span>
<span data-ttu-id="c2c23-123">O campo **É mantido externamente** foi adicionado à entidade **Depósito (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="c2c23-123">The field **Is Maintained Externally** has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="c2c23-124">Este campo ajuda a identificar se o depósito é tratado no Operations ou se ele só existe no Field Service.</span><span class="sxs-lookup"><span data-stu-id="c2c23-124">This field helps to identify If the Warehouse is handled from Operations or if It only exists in Field Service.</span></span>
- <span data-ttu-id="c2c23-125">Sim – O depósito foi originado do Finance and Operations e não será editável no Sales.</span><span class="sxs-lookup"><span data-stu-id="c2c23-125">Yes – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="c2c23-126">Nenhum – o depósito foi inserido diretamente no Field Service e é mantido aqui.</span><span class="sxs-lookup"><span data-stu-id="c2c23-126">No – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="c2c23-127">O campo **É mantido externamente** ajuda a controlar a sincronização dos níveis de estoque, ajustes, transferências e de uso em ordens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c2c23-127">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers and usage on work orders.</span></span> <span data-ttu-id="c2c23-128">Somente os depósitos com **É mantido externamente** = Sim podem ser usados para sincronizar diretamente para o mesmo depósito no outro sistema.</span><span class="sxs-lookup"><span data-stu-id="c2c23-128">Only warehouses with **Is Externally Maintained** = Yes can be used to synchronize directly to the same warehouse in the other system.</span></span> 

<span data-ttu-id="c2c23-129">Observação: É possível criar vários depósitos no Field Services (com **É mantido externamente** = Não) e depois mapeá-los para um único depósito no Finance and Operations, a funcionalidade Filtragem e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="c2c23-129">Note: It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="c2c23-130">Isso é útil em situações em que você deseja que o Field service domine o nível de estoque detalhado e envie apenas atualizações para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c2c23-130">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="c2c23-131">Nesse caso, o Field Service não receberá atualizações em nível de estoque do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c2c23-131">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="c2c23-132">Consulte as informações adicionais em Sincronizar ajustes de inventário do Field Service para o Finance and Operations e Sincronizar ordens de trabalho no Field Service para ordens de venda vinculadas ao projeto no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c2c23-132">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="c2c23-133">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="c2c23-133">Prerequisites and mapping setup</span></span>
### <a name="in-the-data-integration-project"></a><span data-ttu-id="c2c23-134">No Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="c2c23-134">In the Data Integration project</span></span>
<span data-ttu-id="c2c23-135">Antes de sincronizar depósitos , verifique se você atualizou Filtragem e consulta avançada no projeto para incluir apenas os depósitos que você deseja trazer do Finance and Operations para o Field Service.</span><span class="sxs-lookup"><span data-stu-id="c2c23-135">Before synchronization of the warehouses make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="c2c23-136">Observe que você precisará do depósito no Field Service para aplicá-lo em ordens de trabalho, ajustes e transferências.</span><span class="sxs-lookup"><span data-stu-id="c2c23-136">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments and transfers.</span></span>  

<span data-ttu-id="c2c23-137">Verifique se **Chave de integração** existe para **msdyn_warehouses**</span><span class="sxs-lookup"><span data-stu-id="c2c23-137">Ensure the **Integration key** exist for **msdyn_warehouses**</span></span>
1. <span data-ttu-id="c2c23-138">Vá para Integração de dados</span><span class="sxs-lookup"><span data-stu-id="c2c23-138">Go to Data Integration</span></span>
2. <span data-ttu-id="c2c23-139">Selecione a guia **Conjunto de conexão**</span><span class="sxs-lookup"><span data-stu-id="c2c23-139">Select **Connection Set** tab</span></span>
3. <span data-ttu-id="c2c23-140">Selecione o Conjunto de conexão usado para sincronização da Ordem de trabalho</span><span class="sxs-lookup"><span data-stu-id="c2c23-140">Select the Connection set used for Work order synchronization</span></span>
4. <span data-ttu-id="c2c23-141">Selecione a guia **Chave de integração**</span><span class="sxs-lookup"><span data-stu-id="c2c23-141">Select **Integration key** tab</span></span>
5. <span data-ttu-id="c2c23-142">Localize msdyn_warehouses e verifique se a chave **msdyn_name (nome)** foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="c2c23-142">Find msdyn_warehouses and check that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="c2c23-143">Se não for exibida, adicione-a clicando em **Adicionar chave** e clique em **Salvar** na parte superior da página</span><span class="sxs-lookup"><span data-stu-id="c2c23-143">If it is not shown, add it by click **Add key** and click **Save** in the top of the page</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c2c23-144">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="c2c23-144">Template mapping in Data integration</span></span>

<span data-ttu-id="c2c23-145">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="c2c23-145">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a><span data-ttu-id="c2c23-146">Depósitos (Finance and Operations para Field Service): Depósito</span><span class="sxs-lookup"><span data-stu-id="c2c23-146">Warehouses (Finance and Operations to Field Service): Warehouse</span></span>

<span data-ttu-id="c2c23-147">[![Mapeamento de modelo na Integração de dados](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="c2c23-147">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>

