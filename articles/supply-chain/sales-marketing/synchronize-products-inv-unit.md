---
title: Sincronizar produtos com unidade de estoque do Finance and Operations no Field Service
description: "Este tópico discute os modelos e a tarefa subjacente usados para sincronizar produtos com a unidade de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="cc145-103">Sincronizar produtos com unidade de estoque do Finance and Operations no Field Service</span><span class="sxs-lookup"><span data-stu-id="cc145-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cc145-104">Este tópico discute os modelos e a tarefa subjacente usados para sincronizar produtos com a unidade de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="cc145-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="cc145-105">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="cc145-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="cc145-106">O modelo usado **Produtos do Field Service (Finance and Operations para o Field Service)** é baseado no modelo **Produtos (Finance and Operations para o Sales) – Direto** do Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="cc145-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="cc145-107">Para obter mais informações, consulte [Produtos (Finance and Operations para o Sales) – Direto](products-template-mapping-direct.md).</span><span class="sxs-lookup"><span data-stu-id="cc145-107">For more information, see [Products (Finance and Operations to Sales) – Direct](products-template-mapping-direct.md).</span></span>

<span data-ttu-id="cc145-108">Este tópico descreve somente as diferenças entre os modelos **Produtos do Field Service (Finance and Operations para Field Service)** e **Produtos do Field Service (Finance and Operations para Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="cc145-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="cc145-109">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="cc145-109">Templates and tasks</span></span>

<span data-ttu-id="cc145-110">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="cc145-110">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="cc145-111">Produtos do Field Service com unidade de estoque (Finance and Operations para Sales)</span><span class="sxs-lookup"><span data-stu-id="cc145-111">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="cc145-112">**Nome da tarefa no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="cc145-112">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="cc145-113">Produtos</span><span class="sxs-lookup"><span data-stu-id="cc145-113">Products</span></span>

<span data-ttu-id="cc145-114">O modelo **Produtos do Field Service com unidade de estoque (Finance and Operations para Field Service)** inclui um mapeamento que não é incluído no modelo **Produtos do Field Service (Finance and Operations para Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="cc145-114">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="cc145-115">Esse mapeamento garante que a unidade de estoque necessária para a sincronização em nível de estoque seja incluída.</span><span class="sxs-lookup"><span data-stu-id="cc145-115">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="cc145-116">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="cc145-116">Template mapping in Data integration</span></span>

<span data-ttu-id="cc145-117">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="cc145-117">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="cc145-118">Produtos do Field Service com a unidade de estoque (Finance and Operations para Field Service): Produtos</span><span class="sxs-lookup"><span data-stu-id="cc145-118">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="cc145-119">[![Mapeamento de modelo na Integração de dados](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="cc145-119">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>

