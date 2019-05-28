---
title: Sincronizar produtos no Finance and Operations com produtos no Field Service
description: Este tópico discute os modelos e a tarefa subjacente que são usados para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 3f26240ec289f5ddcc2682e598bbf93f516b99af
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562686"
---
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a>Sincronizar produtos do Finance and Operations com produtos no Field Service

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e a tarefa subjacente que são usados para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

O modelo usado **Produtos do Field Service (Fin and Ops com o Field Service)** é baseado no modelo **Produtos (Fin and Ops com o Sales) – Direto** do Prospect to Cash. Para obter mais informações, consulte [Produtos (Fin and Ops com o Sales) – Direto](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Este tópico descreve somente as diferenças entre os modelos **Produtos do Field Service (Fin and Ops com o Field Service)** e **Produtos (Fin and Ops com o Sales) – Direto**.

## <a name="templates-and-tasks"></a>Modelos e tarefas

**Nome do modelo na Integração de dados:**

- Produtos do Field Service (Fin and Ops com o Field Service)

**Nome da tarefa no projeto de Integração de dados:**

- Produtos - Produtos

O modelo **Produtos do Field Service (Fin and Ops com o Field Service)** inclui um mapeamento que não está inlcuído no modelo **Produtos (Fin and Ops com o Sales) – Direto**. Esse mapeamento garante que o campo obrigatório **Tipo de produto de serviço** específico do Field Service seja definido corretamente.

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

O valor de mapeamento a seguir é usado.

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

No Finance and Operations, o valor **Tipo de produto do Field Service** na entidade de dados **Produtos liberados comercializáveis** é calculado da seguinte forma:

- **Estoque:** Tipo de produto = Produto and Grupo de modelo do item, Produto em estoque = Verdadeiro
- **Sem estoque:** Tipo de produto = Produto and Grupo de modelo do item, Produto em estoque = Falso
- **Serviço:** Tipo de produto = Serviço

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a>Produtos do Field Service (Fin and Ops com o Field Service): Produtos - Produtos

[![Mapeamento de modelo na Integração de dados](./media/FSProduct.png)](./media/FSProduct.png)
