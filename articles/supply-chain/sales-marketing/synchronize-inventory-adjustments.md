---
title: Sincronizar transferências e ajustes de estoque do Field Service para o Finance and Operations
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes e transferências de estoque do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/30/2019
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
ms.openlocfilehash: e94fa87c2f8b66574d6c5b2930cebf2e1b144fea
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1536287"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a>Sincronizar ajustes de estoque do Field Service para o Finance and Operations

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes e transferências de estoque do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização dos ajustes e transferências de estoque do Microsoft Dynamics 365 for Field Service com o Microsoft Dynamics 365 for Finance and Operations.

**Modelo na integração de dados**
- Ajuste de Estoque (Field Service para Fin and Ops)
- Transferências de Estoque (Field Service para Fin and Ops)

**Tarefas nos projetos de integração de dados**
- Ajustes de estoque
- Transferências de estoque

## <a name="entity-set"></a>Conjunto de entidades
| Field Service                     | Finance and Operations                             |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts |   Cabeçalhos e linhas do diário de ajuste de estoque do CDS |
| msdyn_inventoryadjustmentproducts | Cabeçalhos e linhas do diário de transferência de estoque do CDS   |

## <a name="entity-flow"></a>Fluxo de entidades
Os ajustes e transferências de estoque realizados no Field Service serão sincronizados com o Finance and Operations depois que o **Status de lançamento** mudar de **Criado** para **Lançado**. Quando isso ocorre, o ajuste ou a ordem de transferência será bloqueado para se tornar somente leitura. Isso significa que os ajustes e as transferências podem ser lançados no Finance and Operations, mas não podem ser alterados. No Finance and Operations, você pode configurar um trabalho em lotes para lançar automaticamente ajustes e transferir diários de estoque gerados com a integração. Veja os pré-requisitos a seguir para obter detalhes sobre como habilitar o trabalho em lotes.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM 
O campo **Unidade de estoque** foi adicionado à entidade **Produto**. Este campo é necessário pois a unidade de vendas e estoque não é sempre a mesma no Finance and Operations, e a unidade de estoque é necessária para o estoque do depósito no Finance and Operations.
Quando você definir o produto em um produto de ajuste de estoque para os ajustes de estoque e as transferências de estoque, a unidade será obtida do valor de produto do estoque. Se um valor for encontrado, o campo **Unidade** será bloqueado no produto de ajuste de estoque

O campo **Status de lançamento** foi adicionado à entidade **Ajuste de estoque** e à entidade **Transferência de estoque**. Este campo é usado como um filtro quando um ajuste ou uma transferência é enviada para o Finance and Operations. O padrão desse campo é Criado (1), porém ele não é enviado para o Finance and Operations. Quando você atualiza o valor para Lançado (2), ele será enviado para o Finance and Operations, mas depois disso você não poderá mais fazer alterações no ajuste nem na transferência, nem adicionar novas linhas.

O campo **Sequência numérica** foi adicionado à entidade **Produto de ajuste de estoque**. Este campo garante que a integração tenha um número exclusivo, assim a integração pode criar e atualizar o ajuste. Quando você criar seu primeiro produto de ajuste de estoque, ele criará um novo registro na entidade **P2C AutoNumber** para manter a série de número e o prefixo usado.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

### <a name="finance-and-operations"></a>Finance and Operations
Os diários de estoque de integração gerados pela integração podem ser lançados automaticamente usando um trabalho em lotes. Isso é habilitado em **Gerenciamento de estoque > Tarefas periódicas > Integração de CDs > Diários de estoque após a integração**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="inventory-adjustment-field-service-to-fin-and-ops-inventory-adjustment"></a>Ajuste de estoque (Field Service para Fin and Ops): Ajuste de estoque

[![Mapeamento de modelo na Integração de dados](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-fin-and-ops-inventory-transfer"></a>Transferência de estoque (Field Service para Fin and Ops): Transferência de estoque

[![Mapeamento de modelo na Integração de dados](./media/FSTrans1.png)](./media/FSTrans1.png)
