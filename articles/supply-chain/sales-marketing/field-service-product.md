---
title: Sincronizar produtos no Finance and Operations com produtos no Field Service
description: "Este tópico discute os modelos e a tarefa subjacente usados para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: ace66c037953f4b1b2e8b93a315faefdb090b1eb
ms.openlocfilehash: bf5de13fee6db1b467c1cf4d5cc65b46c67b29fe
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a><span data-ttu-id="7c357-103">Sincronizar produtos no Finance and Operations com produtos no Field Service</span><span class="sxs-lookup"><span data-stu-id="7c357-103">Synchronize products in Finance and Operations to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7c357-104">Este tópico discute os modelos e a tarefa subjacente usados para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="7c357-104">This topic discusses the templates and underlying task that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="7c357-105">O modelo usado **Produtos do Field Service (Fin and Ops com o Field Service)** é baseado no modelo **Produtos (Fin and Ops com o Sales) – Direto** do Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="7c357-105">The used **Field Service Products (Fin and Ops to Field Service)** template is based on the **Products (Fin and Ops to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="7c357-106">Para obter mais informações, consulte [Produtos (Fin and Ops com o Sales) – Direto](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="7c357-106">For more information, see [Products (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="7c357-107">Este tópico descreve somente as diferenças entre os modelos **Produtos do Field Service (Fin and Ops com o Field Service)** e **Produtos (Fin and Ops com o Sales) – Direto**.</span><span class="sxs-lookup"><span data-stu-id="7c357-107">This topic only describes the differences between the **Field Service Products (Fin and Ops to Field Service)** and **Products (Fin and Ops to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7c357-108">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="7c357-108">Templates and tasks</span></span>

<span data-ttu-id="7c357-109">**Nome do modelo na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="7c357-109">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="7c357-110">Produtos do Field Service (Fin and Ops com o Field Service)</span><span class="sxs-lookup"><span data-stu-id="7c357-110">Field Service Products (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="7c357-111">**Nome da tarefa no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="7c357-111">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="7c357-112">Produtos - Produtos</span><span class="sxs-lookup"><span data-stu-id="7c357-112">Products - Products</span></span>

<span data-ttu-id="7c357-113">O modelo **Produtos do Field Service (Fin and Ops com o Field Service)** inclui um mapeamento que não está inlcuído no modelo **Produtos (Fin and Ops com o Sales) – Direto**.</span><span class="sxs-lookup"><span data-stu-id="7c357-113">The **Field Service Products (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Products (Fin and Ops to Sales) – Direct** template.</span></span> <span data-ttu-id="7c357-114">Esse mapeamento garante que o campo obrigatório **Tipo de produto de serviço** específico do Field Service seja definido corretamente.</span><span class="sxs-lookup"><span data-stu-id="7c357-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="7c357-115">O valor de mapeamento a seguir é usado.</span><span class="sxs-lookup"><span data-stu-id="7c357-115">The following value mapping is used.</span></span>

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="7c357-116">No Finance and Operations, o valor **Tipo de produto do Field Service** na entidade de dados **Produtos liberados comercializáveis** é calculado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="7c357-116">In Finance and Operations, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="7c357-117">**Estoque:** Tipo de produto = Produto and Grupo de modelo do item, Produto em estoque = Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="7c357-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="7c357-118">**Sem estoque:** Tipo de produto = Produto and Grupo de modelo do item, Produto em estoque = Falso</span><span class="sxs-lookup"><span data-stu-id="7c357-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="7c357-119">**Serviço:** Tipo de produto = Serviço</span><span class="sxs-lookup"><span data-stu-id="7c357-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7c357-120">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="7c357-120">Template mapping in Data integration</span></span>

<span data-ttu-id="7c357-121">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="7c357-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a><span data-ttu-id="7c357-122">Produtos do Field Service (Fin and Ops com o Field Service): Produtos - Produtos</span><span class="sxs-lookup"><span data-stu-id="7c357-122">Field Service Products (Fin and Ops to Field Service): Products - Products</span></span>

<span data-ttu-id="7c357-123">[![Mapeamento de modelo na Integração de dados](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="7c357-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>

