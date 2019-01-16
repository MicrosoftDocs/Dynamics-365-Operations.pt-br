---
title: "Sincronizar transferências e ajustes de estoque do Field Service para o Finance and Operations"
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes de inventário e transferências do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Sincronizar ajustes de estoque do Field Service para o Finance and Operations

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes de inventário e transferências do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo e as tarefas subjacentes a seguir são usados para executar a sincronização de ajustes e transferências de estoque do Microsoft Dynamics 365 for Field Service para o Microsoft Dynamics 365 for Finance and Operations.

**Nome dos modelos na Integração de dados:**
- Ajuste de inventário (Field Service para Finance and Operations)
- Transferências de inventário (Field Service para Finance and Operations)

**Nomes das tarefas em projetos de Integração de dados:**
- Ajustes de estoque
- Transferências de estoque

## <a name="entity-set"></a>Conjunto de entidades
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   Cabeçalhos e linhas do diário de ajuste de estoque do CDS |
| msdyn_inventoryadjustmentproducts | Cabeçalhos e linhas do diário de transferência de estoque do CDS   |

## <a name="entity-flow"></a>Fluxo de entidades
Os ajustes e transferências de estoque realizados no Field Service serão sincronizados para o Finance and Operations, após o **Status de lançamento** mudar para Criado para Lançado. Quando isso acontecer, a ordem de ajuste ou de transferência será bloqueada e ficará somente leitura, pois os ajustes e as transferências podem ser lançados no Finance and Operations e, portanto, não podem ser modificados.
No Finance and Operations, é possível configurar um trabalho em lotes para lançar automaticamente os ajustes e transferir diários de estoque gerados com a integração. Veja os pré-requisitos a seguir para obter detalhes sobre como habilitar o trabalho em lotes.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM 
O campo Unidade de estoque foi adicionado à entidade Produto. Este campo é necessário pois a unidade de vendas e estoque não é sempre na mesma em Operations. Para o estoque de depósito em operações, precisamos da unidade de estoque.
Quando você definir o produto em um produto de ajuste de estoque para os ajustes de estoque e as transferências de estoque, a unidade será obtida do valor de produto do estoque do produto. Se um valor for encontrado, o campo Unidade será bloqueado no produto de ajuste de estoque

O campo de status de lançamento foi adicionado à entidade de ajuste estoque e à entidade de transferência de estoque. Este campo é usado como um filtro para quando um ajuste ou uma transferência é enviada para Operations. O campo é usado como padrão para Criado (1) e não é enviado para Operations. Se você mudar para Lançado (2), ele será enviado para operações, mas você não poderá mais fazer alterações no ajuste ou na transferência, nem adicionar novas linhas.
O campo Sequência Numérica foi adicionado à entidade Produto de Ajuste de Estoque. Este campo ajuda a integração a ter um número exclusivo; assim, a integração sabe quando criar e quando fazer atualizações. Quando você criar o primeiro produto de ajuste de estoque, ele criará um registro na entidade P2C AutoNumber para manter a série de número e o prefixo usado.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

### <a name="in-finance-and-operations"></a>No Finance and Operations
Os diários de estoque de integração gerados pela integração podem ser lançados automaticamente com um trabalho em lotes. Isso é habilitado de: Gerenciamento de estoque > Tarefas periódicas > Integração de CDs > Diários de estoque após a integração

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a>Ajuste de estoque (Field Service para Finance and Operations): ajuste de estoque

[![Mapeamento de modelo na Integração de dados](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a>Transferência de estoque (Field Service para Finance and Operations): transferência de estoque

[![Mapeamento de modelo na Integração de dados](./media/FSTrans1.png)](./media/FSTrans1.png)

