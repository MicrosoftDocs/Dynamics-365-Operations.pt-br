---
title: Sincronizar transferências e ajustes de estoque do Field Service com o Supply Chain Management
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes e transferências de estoque do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/30/2019
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
ms.openlocfilehash: fce407a66c339f2ece4bbc37b30243a2ed172d0a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251880"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a><span data-ttu-id="77ea1-103">Sincronizar transferências e ajustes de estoque do Field Service com o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="77ea1-103">Synchronize inventory transfers and adjustments from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="77ea1-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes e transferências de estoque do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="77ea1-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="77ea1-105">[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="77ea1-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="77ea1-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="77ea1-106">Templates and tasks</span></span>
<span data-ttu-id="77ea1-107">O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização das transferências e ajustes de estoque do Field Service com o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="77ea1-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Field Service to Supply Chain Management.</span></span>

<span data-ttu-id="77ea1-108">**Modelo na integração de dados**</span><span class="sxs-lookup"><span data-stu-id="77ea1-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="77ea1-109">Ajustes de Estoque (Field Service com o Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="77ea1-109">Inventory Adjustment (Field Service to Supply Chain Management)</span></span>
- <span data-ttu-id="77ea1-110">Transferências de Estoque (Field Service com o Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="77ea1-110">Inventory Transfers (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="77ea1-111">**Tarefas nos projetos de integração de dados**</span><span class="sxs-lookup"><span data-stu-id="77ea1-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="77ea1-112">Ajustes de estoque</span><span class="sxs-lookup"><span data-stu-id="77ea1-112">Inventory Adjustments</span></span>
- <span data-ttu-id="77ea1-113">Transferências de estoque</span><span class="sxs-lookup"><span data-stu-id="77ea1-113">Inventory Transfers</span></span>

## <a name="table-set"></a><span data-ttu-id="77ea1-114">Conjunto de tabelas</span><span class="sxs-lookup"><span data-stu-id="77ea1-114">Table set</span></span>
| <span data-ttu-id="77ea1-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="77ea1-115">Field Service</span></span>                     | <span data-ttu-id="77ea1-116">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="77ea1-116">Supply Chain Management</span></span>                          |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="77ea1-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="77ea1-117">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="77ea1-118">Cabeçalhos e linhas do diário de ajuste de estoque do Dataverse</span><span class="sxs-lookup"><span data-stu-id="77ea1-118">Dataverse Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="77ea1-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="77ea1-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="77ea1-120">Cabeçalhos e linhas do diário de transferência de estoque do Dataverse</span><span class="sxs-lookup"><span data-stu-id="77ea1-120">Dataverse inventory transfer journal headers and lines</span></span>   |

## <a name="table-flow"></a><span data-ttu-id="77ea1-121">Fluxo de tabelas</span><span class="sxs-lookup"><span data-stu-id="77ea1-121">Table flow</span></span>
<span data-ttu-id="77ea1-122">Os ajustes e transferências de estoque realizados no Field Service serão sincronizados com o Supply Chain Management depois que o **Status de lançamento** mudar de **Criado** para **Lançado**.</span><span class="sxs-lookup"><span data-stu-id="77ea1-122">Inventory adjustments and transfers made in Field Service will synchronize to Supply Chain Management after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="77ea1-123">Quando isso ocorre, o ajuste ou a ordem de transferência será bloqueado para se tornar somente leitura.</span><span class="sxs-lookup"><span data-stu-id="77ea1-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="77ea1-124">Isso significa que os ajustes e as transferências podem ser lançados no Supply Chain Management, mas não podem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="77ea1-124">This means that adjustments and transfers can be posted in Supply Chain Management, but cannot be modified.</span></span> <span data-ttu-id="77ea1-125">No Supply Chain Management, você pode configurar um trabalho em lotes para lançar automaticamente ajustes e transferir diários de estoque gerados com a integração.</span><span class="sxs-lookup"><span data-stu-id="77ea1-125">In Supply Chain Management, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="77ea1-126">Veja os pré-requisitos a seguir para obter detalhes sobre como habilitar o trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="77ea1-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="77ea1-127">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="77ea1-127">Field Service CRM solution</span></span> 
<span data-ttu-id="77ea1-128">A coluna **Unidade de estoque** foi adicionada à tabela **Produto**.</span><span class="sxs-lookup"><span data-stu-id="77ea1-128">The **Inventory unit** column has been added to the **Product** table.</span></span> <span data-ttu-id="77ea1-129">Esta coluna é necessária, pois a unidade de Vendas e Estoque não é sempre a mesma no Supply Chain Management e a Unidade de Estoque é necessária para o Estoque do Depósito no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="77ea1-129">This column is needed because the Sales and Inventory unit is not always the same in Supply Chain Management, and the Inventory Unit is needed for the Warehouse Inventory in Supply Chain Management.</span></span>
<span data-ttu-id="77ea1-130">Quando você definir o produto em um produto de ajuste de estoque para os ajustes de estoque e as transferências de estoque, a unidade será obtida do valor de produto do estoque.</span><span class="sxs-lookup"><span data-stu-id="77ea1-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="77ea1-131">Se um valor for encontrado, a coluna **Unidade** será bloqueada no Produto de ajuste de estoque.</span><span class="sxs-lookup"><span data-stu-id="77ea1-131">If a value is found, the **Unit** column will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="77ea1-132">A coluna **Status de lançamento** foi adicionada à tabela **Ajuste de estoque** e à tabela **Transferência de estoque**.</span><span class="sxs-lookup"><span data-stu-id="77ea1-132">The **Post status** column has been added to both the **Inventory adjustment** table and the **Inventory transfer** table.</span></span> <span data-ttu-id="77ea1-133">Esta coluna é usada como filtro quando um ajuste ou uma transferência é enviada para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="77ea1-133">This column is used as a filter when an adjustment or transfer is sent to Supply Chain Management.</span></span> <span data-ttu-id="77ea1-134">O padrão dessa coluna é Criado (1), no entanto, ela não é enviada para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="77ea1-134">The default for this column is Created (1), however it is not sent to Supply Chain Management.</span></span> <span data-ttu-id="77ea1-135">Quando você atualiza o valor para Lançado (2), ele será enviado para o Supply Chain Management, mas depois disso você não poderá mais fazer alterações no ajuste nem na transferência, nem adicionar novas linhas.</span><span class="sxs-lookup"><span data-stu-id="77ea1-135">When you update the value to Posted (2), it is sent to Supply Chain Management, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="77ea1-136">A coluna **Sequência numérica** foi adicionada à tabela **Produto de ajuste de estoque**.</span><span class="sxs-lookup"><span data-stu-id="77ea1-136">The **Number sequence** column has been added to the **Inventory adjustment product** table.</span></span> <span data-ttu-id="77ea1-137">Esta coluna garante que a integração tenha um número exclusivo, assim, a integração pode criar e atualizar o ajuste.</span><span class="sxs-lookup"><span data-stu-id="77ea1-137">This column ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="77ea1-138">Quando você criar seu primeiro produto de ajuste de estoque, ela criará um novo registro na tabela **P2C AutoNumber** para manter a série de números e o prefixo usados.</span><span class="sxs-lookup"><span data-stu-id="77ea1-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** table to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="77ea1-139">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="77ea1-139">Prerequisites and mapping setup</span></span>

### <a name="supply-chain-management"></a><span data-ttu-id="77ea1-140">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="77ea1-140">Supply Chain Management</span></span>
<span data-ttu-id="77ea1-141">Os diários de estoque de integração gerados pela integração podem ser lançados automaticamente usando um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="77ea1-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="77ea1-142">Isso é habilitado em **Gerenciamento de estoque > Tarefas periódicas > Integração do Dataverse > Diários de estoque após a integração**.</span><span class="sxs-lookup"><span data-stu-id="77ea1-142">This is enabled from **Inventory management > Periodic tasks > Dataverse integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="77ea1-143">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="77ea1-143">Template mapping in Data integration</span></span>

<span data-ttu-id="77ea1-144">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="77ea1-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a><span data-ttu-id="77ea1-145">Ajuste de estoque (Field Service com o Supply Chain Management): Ajuste de estoque</span><span class="sxs-lookup"><span data-stu-id="77ea1-145">Inventory adjustment (Field Service to Supply Chain Management): Inventory adjustment</span></span>

<span data-ttu-id="77ea1-146">[![Mapeamento de modelo na Integração de dados](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="77ea1-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a><span data-ttu-id="77ea1-147">Transferência de estoque (Field Service com o Supply Chain Management): Transferência de estoque</span><span class="sxs-lookup"><span data-stu-id="77ea1-147">Inventory transfer (Field Service to Supply Chain Management): Inventory transfer</span></span>

<span data-ttu-id="77ea1-148">[![Mapeamento de modelo na Integração de dados](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="77ea1-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]