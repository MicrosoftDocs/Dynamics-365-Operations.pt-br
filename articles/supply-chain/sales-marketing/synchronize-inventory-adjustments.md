---
title: Sincronizar transferências e ajustes de estoque do Field Service para o Finance and Operations
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes e transferências de estoque do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/30/2019
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
ms.openlocfilehash: e94fa87c2f8b66574d6c5b2930cebf2e1b144fea
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1536287"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="eda74-103">Sincronizar ajustes de estoque do Field Service para o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="eda74-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="eda74-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes e transferências de estoque do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="eda74-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="eda74-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="eda74-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="eda74-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="eda74-106">Templates and tasks</span></span>
<span data-ttu-id="eda74-107">O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização dos ajustes e transferências de estoque do Microsoft Dynamics 365 for Field Service com o Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="eda74-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="eda74-108">**Modelo na integração de dados**</span><span class="sxs-lookup"><span data-stu-id="eda74-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="eda74-109">Ajuste de Estoque (Field Service para Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="eda74-109">Inventory Adjustment (Field Service to Fin and Ops)</span></span>
- <span data-ttu-id="eda74-110">Transferências de Estoque (Field Service para Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="eda74-110">Inventory Transfers (Field Service to Fin and Ops)</span></span>

<span data-ttu-id="eda74-111">**Tarefas nos projetos de integração de dados**</span><span class="sxs-lookup"><span data-stu-id="eda74-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="eda74-112">Ajustes de estoque</span><span class="sxs-lookup"><span data-stu-id="eda74-112">Inventory Adjustments</span></span>
- <span data-ttu-id="eda74-113">Transferências de estoque</span><span class="sxs-lookup"><span data-stu-id="eda74-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="eda74-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="eda74-114">Entity set</span></span>
| <span data-ttu-id="eda74-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="eda74-115">Field Service</span></span>                     | <span data-ttu-id="eda74-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="eda74-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="eda74-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="eda74-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="eda74-118">Cabeçalhos e linhas do diário de ajuste de estoque do CDS</span><span class="sxs-lookup"><span data-stu-id="eda74-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="eda74-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="eda74-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="eda74-120">Cabeçalhos e linhas do diário de transferência de estoque do CDS</span><span class="sxs-lookup"><span data-stu-id="eda74-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="eda74-121">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="eda74-121">Entity flow</span></span>
<span data-ttu-id="eda74-122">Os ajustes e transferências de estoque realizados no Field Service serão sincronizados com o Finance and Operations depois que o **Status de lançamento** mudar de **Criado** para **Lançado**.</span><span class="sxs-lookup"><span data-stu-id="eda74-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="eda74-123">Quando isso ocorre, o ajuste ou a ordem de transferência será bloqueado para se tornar somente leitura.</span><span class="sxs-lookup"><span data-stu-id="eda74-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="eda74-124">Isso significa que os ajustes e as transferências podem ser lançados no Finance and Operations, mas não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="eda74-124">This means that adjustments and transfers can be posted in Finance and Operations, but cannot be modified.</span></span> <span data-ttu-id="eda74-125">No Finance and Operations, você pode configurar um trabalho em lotes para lançar automaticamente ajustes e transferir diários de estoque gerados com a integração.</span><span class="sxs-lookup"><span data-stu-id="eda74-125">In Finance and Operations, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="eda74-126">Veja os pré-requisitos a seguir para obter detalhes sobre como habilitar o trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="eda74-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="eda74-127">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="eda74-127">Field Service CRM solution</span></span> 
<span data-ttu-id="eda74-128">O campo **Unidade de estoque** foi adicionado à entidade **Produto**.</span><span class="sxs-lookup"><span data-stu-id="eda74-128">The **Inventory unit** field has been added to the **Product** entity.</span></span> <span data-ttu-id="eda74-129">Este campo é necessário pois a unidade de vendas e estoque não é sempre a mesma no Finance and Operations, e a unidade de estoque é necessária para o estoque do depósito no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="eda74-129">This field is needed because the Sales and Inventory unit is not always the same in Finance and Operations, and the Inventory Unit is needed for the Warehouse Inventory in Finance and Operations.</span></span>
<span data-ttu-id="eda74-130">Quando você definir o produto em um produto de ajuste de estoque para os ajustes de estoque e as transferências de estoque, a unidade será obtida do valor de produto do estoque.</span><span class="sxs-lookup"><span data-stu-id="eda74-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="eda74-131">Se um valor for encontrado, o campo **Unidade** será bloqueado no produto de ajuste de estoque</span><span class="sxs-lookup"><span data-stu-id="eda74-131">If a value is found, the **Unit** field will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="eda74-132">O campo **Status de lançamento** foi adicionado à entidade **Ajuste de estoque** e à entidade **Transferência de estoque**.</span><span class="sxs-lookup"><span data-stu-id="eda74-132">The **Post status** field has been added to both the **Inventory adjustment** entity and the **Inventory transfer** entity.</span></span> <span data-ttu-id="eda74-133">Este campo é usado como um filtro quando um ajuste ou uma transferência é enviada para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="eda74-133">This field is used as a filter when an adjustment or transfer is sent to Finance and Operations.</span></span> <span data-ttu-id="eda74-134">O padrão desse campo é Criado (1), porém ele não é enviado para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="eda74-134">The default for this field is Created (1), however it is not sent to Finance and Operations.</span></span> <span data-ttu-id="eda74-135">Quando você atualiza o valor para Lançado (2), ele será enviado para o Finance and Operations, mas depois disso você não poderá mais fazer alterações no ajuste nem na transferência, nem adicionar novas linhas.</span><span class="sxs-lookup"><span data-stu-id="eda74-135">When you update the value to Posted (2), it is sent to Finance and Operations, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="eda74-136">O campo **Sequência numérica** foi adicionado à entidade **Produto de ajuste de estoque**.</span><span class="sxs-lookup"><span data-stu-id="eda74-136">The **Number sequence** field has been added to the **Inventory adjustment product** entity.</span></span> <span data-ttu-id="eda74-137">Este campo garante que a integração tenha um número exclusivo, assim a integração pode criar e atualizar o ajuste.</span><span class="sxs-lookup"><span data-stu-id="eda74-137">This field ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="eda74-138">Quando você criar seu primeiro produto de ajuste de estoque, ele criará um novo registro na entidade **P2C AutoNumber** para manter a série de número e o prefixo usado.</span><span class="sxs-lookup"><span data-stu-id="eda74-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="eda74-139">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="eda74-139">Prerequisites and mapping setup</span></span>

### <a name="finance-and-operations"></a><span data-ttu-id="eda74-140">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="eda74-140">Finance and Operations</span></span>
<span data-ttu-id="eda74-141">Os diários de estoque de integração gerados pela integração podem ser lançados automaticamente usando um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="eda74-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="eda74-142">Isso é habilitado em **Gerenciamento de estoque > Tarefas periódicas > Integração de CDs > Diários de estoque após a integração**.</span><span class="sxs-lookup"><span data-stu-id="eda74-142">This is enabled from **Inventory management > Periodic tasks > CDS integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="eda74-143">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="eda74-143">Template mapping in Data integration</span></span>

<span data-ttu-id="eda74-144">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="eda74-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-fin-and-ops-inventory-adjustment"></a><span data-ttu-id="eda74-145">Ajuste de estoque (Field Service para Fin and Ops): Ajuste de estoque</span><span class="sxs-lookup"><span data-stu-id="eda74-145">Inventory adjustment (Field Service to Fin and Ops): Inventory adjustment</span></span>

<span data-ttu-id="eda74-146">[![Mapeamento de modelo na Integração de dados](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="eda74-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-fin-and-ops-inventory-transfer"></a><span data-ttu-id="eda74-147">Transferência de estoque (Field Service para Fin and Ops): Transferência de estoque</span><span class="sxs-lookup"><span data-stu-id="eda74-147">Inventory transfer (Field Service to Fin and Ops): Inventory transfer</span></span>

<span data-ttu-id="eda74-148">[![Mapeamento de modelo na Integração de dados](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="eda74-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>
