---
title: Sincronizar produtos com unidade de estoque do Finance and Operations no Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos com unidades de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "359235"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Sincronizar produtos com unidade de estoque do Finance and Operations no Field Service

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos com unidades de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

O modelo usado **Produtos do Field Service (Finance and Operations para o Field Service)** é baseado no modelo **Produtos (Finance and Operations para o Sales) – Direto** do Prospect to Cash. Para obter mais informações, consulte [Produtos (Finance and Operations para o Sales) – Direto](products-template-mapping-direct.md).

Este tópico descreve somente as diferenças entre os modelos **Produtos do Field Service (Finance and Operations para Field Service)** e **Produtos do Field Service (Finance and Operations para Field Service)**.

## <a name="templates-and-tasks"></a>Modelos e tarefas

**Nome do modelo na Integração de dados:**

- Produtos do Field Service com unidade de estoque (Finance and Operations para Sales)

**Nome da tarefa no projeto de Integração de dados:**

- Produtos

O modelo **Produtos do Field Service com unidade de estoque (Finance and Operations para Field Service)** inclui um mapeamento que não é incluído no modelo **Produtos do Field Service (Finance and Operations para Field Service)**. Esse mapeamento garante que a unidade de estoque necessária para a sincronização em nível de estoque seja incluída.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a>Produtos do Field Service com a unidade de estoque (Finance and Operations para Field Service): Produtos

[![Mapeamento de modelo na Integração de dados](./media/FSProduct1.png)](./media/FSProduct1.png)
