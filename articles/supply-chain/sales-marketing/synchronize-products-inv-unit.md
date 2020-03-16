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
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Sincronizar produtos com a unidade de estoque do Supply Chain Management com o Field Service

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos com unidades de estoque do Dynamics 365 Supply Chain Management para o Dynamics 365 Field Service.

[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

O modelo **Produtos do Field Service com Unidade de estoque (Supply Chain Management para Field Service)** usado é baseado no modelo **Produtos do Field Service (Supply Chain Management para Field Service)**. Para obter mais informações, consulte [Sincronizar produtos no Supply Chain Management com produtos no Field Service](field-service-product.md).

Este tópico descreve apenas as diferenças entre os dois métodos: 
- **Produtos do Field Service com Unidade de estoque (Supply Chain Management para Sales)**
- **Produtos do Field Service (Supply Chain Management para Field Service)** 

## <a name="templates-and-tasks"></a>Modelos e tarefas

**Nome do modelo na Integração de dados:**

- Produtos do Field Service com Unidade de estoque (Supply Chain Management para Sales)

**Nome da tarefa no projeto de Integração de dados:**

- Produtos

O modelo **Produtos do Field Service com Unidade de estoque (Supply Chain Management para Field Service)** inclui um mapeamento que não está incluído nos **Produtos do Field Service (Supply Chain Management para Field Service)**. Esse mapeamento garante que a unidade de estoque necessária para a sincronização em nível de estoque seja incluída.

```Text
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Produtos do Field Service com Unidade de estoque (Supply Chain Management para Field Service): Produtos

[![Mapeamento de modelo na Integração de dados](./media/FSProduct1.png)](./media/FSProduct1.png)
