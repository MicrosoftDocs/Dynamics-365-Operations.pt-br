---
title: Sincronizar produtos com a unidade de estoque do Supply Chain Management com o Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos com unidades de estoque do Dynamics 365 Supply Chain Management para o Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
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
ms.openlocfilehash: c5be622d6f62d54bcec053b93700ce0c234b8308
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010888"
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

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Produtos do Field Service com Unidade de estoque (Supply Chain Management para Field Service): Produtos

[![Mapeamento de modelo na Integração de dados](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]