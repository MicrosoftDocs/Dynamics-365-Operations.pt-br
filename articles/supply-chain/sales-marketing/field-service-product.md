---
title: Sincronizar produtos no Supply Chain Management com produtos no Field Service
description: Este tópico discute os modelos e a tarefa subjacente que são usados para sincronizar produtos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: d96d1cd91bad4f950868074d9558cb403821d73f
ms.sourcegitcommit: 137e2bd30f0a85bd2e1baf1cf16b993edd2094f9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "3546353"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="4b7fb-103">Sincronizar produtos no Supply Chain Management com produtos no Field Service</span><span class="sxs-lookup"><span data-stu-id="4b7fb-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4b7fb-104">Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar produtos do Dynamics 365 Supply Chain Management para o Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="4b7fb-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="4b7fb-105">O modelo usado **Produtos do Field Service (Supply Chain Management para Field Service)** é baseado no modelo **Produtos (Supply Chain Management para Sales) – Direto** do Prospect to Cash.</span><span class="sxs-lookup"><span data-stu-id="4b7fb-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="4b7fb-106">Para obter mais informações, consulte [Produtos (Supply Chain Management para Sales) – Direto](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="4b7fb-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="4b7fb-107">Este tópico descreve somente as diferenças entre os modelos **Produtos do Field Service (Supply Chain Management para Field Service)** e **Produtos (Supply Chain Management para Sales) – Direto**.</span><span class="sxs-lookup"><span data-stu-id="4b7fb-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="4b7fb-108">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="4b7fb-108">Templates and tasks</span></span>

<span data-ttu-id="4b7fb-109">**Nome do modelo na Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="4b7fb-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="4b7fb-110">Produtos do Field Service (Supply Chain Management para Field Service)</span><span class="sxs-lookup"><span data-stu-id="4b7fb-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="4b7fb-111">**Nome da tarefa no projeto de Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="4b7fb-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="4b7fb-112">Produtos - Produtos</span><span class="sxs-lookup"><span data-stu-id="4b7fb-112">Products - Products</span></span>

<span data-ttu-id="4b7fb-113">O modelo usado **Produtos do Field Service (Supply Chain Management para Field Service)** inclui um mapeamento que não está incluído no modelo **Produtos (Supply Chain Management para Sales) – Direto**.</span><span class="sxs-lookup"><span data-stu-id="4b7fb-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="4b7fb-114">Esse mapeamento garante que o campo obrigatório **Tipo de produto de serviço** específico do Field Service seja definido corretamente.</span><span class="sxs-lookup"><span data-stu-id="4b7fb-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="4b7fb-115">O valor de mapeamento a seguir é usado.</span><span class="sxs-lookup"><span data-stu-id="4b7fb-115">The following value mapping is used.</span></span>

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="4b7fb-116">No Supply Chain Management, o valor de **Tipo de produto do Field Service** na entidade de dados **Produtos liberados comercializáveis** é calculado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4b7fb-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="4b7fb-117">**Estoque:** Tipo de produto = Produto and Grupo de modelo do item, Produto em estoque = Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="4b7fb-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="4b7fb-118">**Sem estoque:** Tipo de produto = Produto and Grupo de modelo do item, Produto em estoque = Falso</span><span class="sxs-lookup"><span data-stu-id="4b7fb-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="4b7fb-119">**Serviço:** Tipo de produto = Serviço</span><span class="sxs-lookup"><span data-stu-id="4b7fb-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4b7fb-120">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="4b7fb-120">Template mapping in Data integration</span></span>

<span data-ttu-id="4b7fb-121">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="4b7fb-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="4b7fb-122">Produtos do Field Service (Supply Chain Management para Field Service): Produtos - Produtos</span><span class="sxs-lookup"><span data-stu-id="4b7fb-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="4b7fb-123">[![Mapeamento de modelo na Integração de dados](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="4b7fb-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
