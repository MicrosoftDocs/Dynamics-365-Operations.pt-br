---
title: Sincronizar produtos no Supply Chain Management com produtos no Field Service
description: Este artigo discute os modelos e a tarefa subjacente que são usados para sincronizar produtos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: Henrikan
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 114550f01f3aed197480fb6830fe913dbfa7b570
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860541"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Sincronizar produtos no Supply Chain Management com produtos no Field Service

[!include[banner](../includes/banner.md)]

Este artigo discute os modelos e as tarefas subjacentes usados para sincronizar produtos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.

O modelo usado **Produtos do Field Service (Supply Chain Management para Field Service)** é baseado no modelo **Produtos (Supply Chain Management para Sales) – Direto** do Prospect to Cash. Para obter mais informações, consulte [Produtos (Supply Chain Management para Sales) – Direto](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

Este artigo descreve somente as diferenças entre os modelos **Produtos do Field Service (Supply Chain Management para Field Service)** e **Produtos (Supply Chain Management para Sales) – Direto**.

## <a name="templates-and-tasks"></a>Modelos e tarefas

**Nome do modelo na Integração de dados**

- Produtos do Field Service (Supply Chain Management para Field Service)

**Nome da tarefa no projeto de Integração de dados**

- Produtos - Produtos

O modelo usado **Produtos do Field Service (Supply Chain Management para Field Service)** inclui um mapeamento que não está incluído no modelo **Produtos (Supply Chain Management para Sales) – Direto**. Esse mapeamento garante que o campo obrigatório **Tipo de produto de serviço** específico do Field Service seja definido corretamente.

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

O valor de mapeamento a seguir é usado.

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

No Supply Chain Management, o valor de **Tipo de produto do Field Service** na entidade de dados **Produtos liberados comercializáveis** é calculado da seguinte forma:

- **Estoque:** Tipo de produto = Produto and Grupo de modelo do item, Produto em estoque = Verdadeiro
- **Sem estoque:** Tipo de produto = Produto and Grupo de modelo do item, Produto em estoque = Falso
- **Serviço:** Tipo de produto = Serviço

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Produtos do Field Service (Supply Chain Management para Field Service): Produtos - Produtos

[![Mapeamento de modelo na Integração de dados.](./media/FSProduct.png)](./media/FSProduct.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]