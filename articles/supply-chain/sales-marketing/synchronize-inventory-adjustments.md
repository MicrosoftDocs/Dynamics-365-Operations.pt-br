---
title: Sincronizar transferências e ajustes de estoque do Field Service com o Supply Chain Management
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes e transferências de estoque do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 04/30/2019
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
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 9f3bfe950446a6e87e34c32d2593cba0af84d8e8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838972"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a>Sincronizar transferências e ajustes de estoque do Field Service com o Supply Chain Management

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ajustes e transferências de estoque do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.

[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização das transferências e ajustes de estoque do Field Service com o Supply Chain Management.

**Modelo na integração de dados**
- Ajustes de Estoque (Field Service com o Supply Chain Management)
- Transferências de Estoque (Field Service com o Supply Chain Management)

**Tarefas nos projetos de integração de dados**
- Ajustes de estoque
- Transferências de estoque

## <a name="table-set"></a>Conjunto de tabelas
| Field Service                     | Gerenciamento da Cadeia de Fornecedores                          |
|-----------------------------------|----------------------------------------------------|
| msdyn_inventoryadjustmentproducts | Cabeçalhos e linhas do diário de ajuste de estoque do Dataverse |
| msdyn_inventoryadjustmentproducts | Cabeçalhos e linhas do diário de transferência de estoque do Dataverse   |

## <a name="table-flow"></a>Fluxo de tabelas
Os ajustes e transferências de estoque realizados no Field Service serão sincronizados com o Supply Chain Management depois que o **Status de lançamento** mudar de **Criado** para **Lançado**. Quando isso ocorre, o ajuste ou a ordem de transferência será bloqueado para se tornar somente leitura. Isso significa que os ajustes e as transferências podem ser lançados no Supply Chain Management, mas não podem ser alterados. No Supply Chain Management, você pode configurar um trabalho em lotes para lançar automaticamente ajustes e transferir diários de estoque gerados com a integração. Veja os pré-requisitos a seguir para obter detalhes sobre como habilitar o trabalho em lotes.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM 
A coluna **Unidade de estoque** foi adicionada à tabela **Produto**. Esta coluna é necessária, pois a unidade de Vendas e Estoque não é sempre a mesma no Supply Chain Management e a Unidade de Estoque é necessária para o Estoque do Depósito no Supply Chain Management.
Quando você definir o produto em um produto de ajuste de estoque para os ajustes de estoque e as transferências de estoque, a unidade será obtida do valor de produto do estoque. Se um valor for encontrado, a coluna **Unidade** será bloqueada no Produto de ajuste de estoque.

A coluna **Status de lançamento** foi adicionada à tabela **Ajuste de estoque** e à tabela **Transferência de estoque**. Esta coluna é usada como filtro quando um ajuste ou uma transferência é enviada para o Supply Chain Management. O padrão dessa coluna é Criado (1), no entanto, ela não é enviada para o Supply Chain Management. Quando você atualiza o valor para Lançado (2), ele será enviado para o Supply Chain Management, mas depois disso você não poderá mais fazer alterações no ajuste nem na transferência, nem adicionar novas linhas.

A coluna **Sequência numérica** foi adicionada à tabela **Produto de ajuste de estoque**. Esta coluna garante que a integração tenha um número exclusivo, assim, a integração pode criar e atualizar o ajuste. Quando você criar seu primeiro produto de ajuste de estoque, ela criará um novo registro na tabela **P2C AutoNumber** para manter a série de números e o prefixo usados.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

### <a name="supply-chain-management"></a>Gerenciamento da Cadeia de Fornecedores
Os diários de estoque de integração gerados pela integração podem ser lançados automaticamente usando um trabalho em lotes. Isso é habilitado em **Gerenciamento de estoque > Tarefas periódicas > Integração do Dataverse > Diários de estoque após a integração**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a>Ajuste de estoque (Field Service com o Supply Chain Management): Ajuste de estoque

[![Mapeamento de modelo na Integração de dados](./media/FSAdj1.png)](./media/FSAdj1.png)


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a>Transferência de estoque (Field Service com o Supply Chain Management): Transferência de estoque

[![Mapeamento de modelo na Integração de dados](./media/FSTrans1.png)](./media/FSTrans1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]