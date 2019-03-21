---
title: Sincronizar produtos com unidade de estoque do Finance and Operations no Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos com unidades de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 8e421be79fde6103be6344040b6ae6cda0626c5a
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2019
ms.locfileid: "836293"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="49293-103">Sincronizar produtos com unidade de estoque do Finance and Operations no Field Service</span><span class="sxs-lookup"><span data-stu-id="49293-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="49293-104">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos com unidades de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="49293-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="49293-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="49293-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="49293-106">O modelo **Produtos do Field Service com unidade de estoque (Finance and Operations para Field Service)** usado é baseado no modelo **Produtos do Field Service (Finance and Operations para Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="49293-106">The used **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template is based on the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="49293-107">Para obter mais informações, consulte [Produtos do Field Service (Finance and Operations para Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="49293-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="49293-108">Este tópico descreve apenas as diferenças entre os dois métodos:</span><span class="sxs-lookup"><span data-stu-id="49293-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="49293-109">**Produtos do Field Service com unidade de estoque (Finance and Operations para Sales)**</span><span class="sxs-lookup"><span data-stu-id="49293-109">**Field Service Products with Inventory unit (Finance and Operations to Sales)**</span></span>
- <span data-ttu-id="49293-110">**Produtos do Field Service (Finance and Operations para Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="49293-110">**Field Service Products (Finance and Operations to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="49293-111">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="49293-111">Templates and tasks</span></span>

<span data-ttu-id="49293-112">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="49293-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="49293-113">Produtos do Field Service com unidade de estoque (Finance and Operations para Sales)</span><span class="sxs-lookup"><span data-stu-id="49293-113">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="49293-114">**Nome da tarefa no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="49293-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="49293-115">Produtos</span><span class="sxs-lookup"><span data-stu-id="49293-115">Products</span></span>

<span data-ttu-id="49293-116">O modelo **Produtos do Field Service com unidade de estoque (Finance and Operations para Field Service)** inclui um mapeamento que não é incluído no modelo **Produtos do Field Service (Finance and Operations para Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="49293-116">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="49293-117">Esse mapeamento garante que a unidade de estoque necessária para a sincronização em nível de estoque seja incluída.</span><span class="sxs-lookup"><span data-stu-id="49293-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="49293-118">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="49293-118">Template mapping in Data integration</span></span>

<span data-ttu-id="49293-119">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="49293-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="49293-120">Produtos do Field Service com a unidade de estoque (Finance and Operations para Field Service): Produtos</span><span class="sxs-lookup"><span data-stu-id="49293-120">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="49293-121">[![Mapeamento de modelo na Integração de dados](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="49293-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
