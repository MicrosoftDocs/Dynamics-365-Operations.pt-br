---
title: Sincronizar produtos com a unidade de estoque do Supply Chain Management com o Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos com unidades de estoque do Dynamics 365 Supply Chain Management para o Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 741b823d6cc5dbd23cda4f07e463f28d6bbe77d6
ms.sourcegitcommit: a2f9dce06322dada6b5f1c82051ef2359f8c0f12
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "3081855"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a><span data-ttu-id="60832-103">Sincronizar produtos com a unidade de estoque do Supply Chain Management com o Field Service</span><span class="sxs-lookup"><span data-stu-id="60832-103">Synchronize products with inventory unit from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="60832-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos com unidades de estoque do Dynamics 365 Supply Chain Management para o Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="60832-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="60832-105">[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="60832-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="60832-106">O modelo **Produtos do Field Service com Unidade de estoque (Supply Chain Management para Field Service)** usado é baseado no modelo **Produtos do Field Service (Supply Chain Management para Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="60832-106">The used **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template is based on the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="60832-107">Para obter mais informações, consulte [Sincronizar produtos no Supply Chain Management com produtos no Field Service](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="60832-107">For more information, see [Synchronize products in Supply Chain Management to products in Field Service](field-service-product.md).</span></span>

<span data-ttu-id="60832-108">Este tópico descreve apenas as diferenças entre os dois métodos:</span><span class="sxs-lookup"><span data-stu-id="60832-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="60832-109">**Produtos do Field Service com Unidade de estoque (Supply Chain Management para Sales)**</span><span class="sxs-lookup"><span data-stu-id="60832-109">**Field Service Products with Inventory unit (Supply Chain Management to Sales)**</span></span>
- <span data-ttu-id="60832-110">**Produtos do Field Service (Supply Chain Management para Field Service)**</span><span class="sxs-lookup"><span data-stu-id="60832-110">**Field Service Products (Supply Chain Management to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="60832-111">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="60832-111">Templates and tasks</span></span>

<span data-ttu-id="60832-112">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="60832-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="60832-113">Produtos do Field Service com Unidade de estoque (Supply Chain Management para Sales)</span><span class="sxs-lookup"><span data-stu-id="60832-113">Field Service Products with Inventory unit (Supply Chain Management to Sales)</span></span>

<span data-ttu-id="60832-114">**Nome da tarefa no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="60832-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="60832-115">Produtos</span><span class="sxs-lookup"><span data-stu-id="60832-115">Products</span></span>

<span data-ttu-id="60832-116">O modelo **Produtos do Field Service com Unidade de estoque (Supply Chain Management para Field Service)** inclui um mapeamento que não está incluído nos **Produtos do Field Service (Supply Chain Management para Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="60832-116">The **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Supply Chain Managementto Field Service)** template.</span></span> <span data-ttu-id="60832-117">Esse mapeamento garante que a unidade de estoque necessária para a sincronização em nível de estoque seja incluída.</span><span class="sxs-lookup"><span data-stu-id="60832-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```Text
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="60832-118">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="60832-118">Template mapping in Data integration</span></span>

<span data-ttu-id="60832-119">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="60832-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a><span data-ttu-id="60832-120">Produtos do Field Service com Unidade de estoque (Supply Chain Management para Field Service): Produtos</span><span class="sxs-lookup"><span data-stu-id="60832-120">Field Service Products with Inventory unit (Supply Chain Management to Field Service): Products</span></span>

<span data-ttu-id="60832-121">[![Mapeamento de modelo na Integração de dados](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="60832-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
