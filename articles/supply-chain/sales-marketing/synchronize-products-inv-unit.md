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
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Sincronizar produtos com unidade de estoque do Finance and Operations no Field Service

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos com unidades de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

O modelo **Produtos do Field Service com unidade de estoque (Finance and Operations para Field Service)** usado é baseado no modelo **Produtos do Field Service (Finance and Operations para Field Service)**. Para obter mais informações, consulte [Produtos do Field Service (Finance and Operations para Field Service)](field-service-product.md).

Este tópico descreve apenas as diferenças entre os dois métodos: 
- **Produtos do Field Service com unidade de estoque (Finance and Operations para Sales)**
- **Produtos do Field Service (Finance and Operations para Field Service)**. 

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
