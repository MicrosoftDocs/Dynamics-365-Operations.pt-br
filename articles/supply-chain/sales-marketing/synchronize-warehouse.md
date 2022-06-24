---
title: Sincronizar depósitos do Supply Chain Management com o Field Service
description: Este artigo discute os modelos e as tarefas subjacentes usadas para sincronizar depósitos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: Henrikan
ms.date: 03/13/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 7fac40ebd8a1f7994997e12f1231e5522a0c0e24
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865053"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a>Sincronizar depósitos do Supply Chain Management com o Field Service

[!include[banner](../includes/banner.md)]



Este artigo discute os modelos e as tarefas subjacentes usadas para sincronizar depósitos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.

[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service.](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização de depósitos do Supply Chain Management com o Field Service.

**Modelo na integração de dados**
- Depósitos (Supply Chain Management para Field Service)

**Tarefas no projeto de integração de dados**
- Depósito

## <a name="table-set"></a>Conjunto de tabelas
| Field Service    | Gerenciamento da Cadeia de Fornecedores                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Depósitos                             |

## <a name="table-flow"></a>Fluxo de tabelas
Os depósitos criados e mantidos no Supply Chain Management podem ser sincronizados com o Field Service por meio de um projeto de integração de dados do Microsoft Dataverse. Os depósitos que você quer sincronizar com o Field Service podem ser controlados com a Filtragem e consulta avançada no projeto. Os depósitos sincronizados do Supply Chain Management são criados no Field Service com a coluna **É mantido externamente** definida como **Sim**, e o registro é somente leitura.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
Para oferecer suporte à integração entre o Field Service e o Supply Chain Management, a funcionalidade adicional da solução Field Service CRM é necessária. Na solução, a coluna **É mantido externamente** foi adicionada à tabela **Depósito (msdyn_warehouses)**. Esta coluna ajuda a identificar se o depósito é tratado no Supply Chain Management ou se ele só existe no Field Service. As configurações dessa coluna são:
- **Sim** – O depósito foi originado do Supply Chain Management e não será editável no Sales.
- **Não** – o depósito foi inserido diretamente no Field Service e é mantido aqui.

A coluna **É mantido externamente** ajuda a controlar a sincronização de níveis, ajustes, transferências e uso de estoque em ordens de serviço. Somente os depósitos com **É mantido externamente** definido como **Sim** podem ser usados para sincronizar diretamente com o mesmo depósito no outro sistema. 

> [!NOTE]
> É possível criar vários depósitos no Field Service (com **É mantido externamente** = Não) e depois mapeá-los para um único depósito, com a funcionalidade Filtragem e consulta avançada. Isso é útil em situações em que você deseja que o Field Service domine o nível de estoque detalhado e apenas envie atualizações ao Supply Chain Management. Nesse caso, o Field Service não receberá atualizações em nível de estoque do Supply Chain Management. Para informações adicionais, consulte [Sincronizar ajustes de estoque do Field Service com o Finance and Operations](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizar ordens de trabalho no Field Service com as ordens de vendas vinculadas ao projeto no Finance and Operations](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento
### <a name="data-integration-project"></a>Projeto de integração de dados
Antes de sincronizar depósitos , verifique se você atualizou a Filtragem e consulta avançada no projeto para incluir apenas os depósitos que você deseja trazer do Supply Chain Management para o Field Service. Observe que você precisará do depósito no Field Service para aplicá-lo em ordens de trabalho, ajustes e transferências.  

Para garantir que a **Chave de integração** exista para **msdyn_warehouses**:
1. Acesse Integração de dados.
2. Selecione a guia **Conjunto de conexão**.
3. Selecione o conjunto de conexão usado para a sincronização da ordem de trabalho.
4. Selecione a guia **Chave de integração**.
5. Localize msdyn_warehouses e verifique se a chave **msdyn_name (nome)** foi adicionada. Se não for exibida, adicione-a clicando em **Adicionar chave** e clique em **Salvar**, na parte superior da página.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a>Depósitos (Supply Chain Management para Field Service): Depósito

[![Mapeamento de modelo na Integração de dados.](./media/Warehouse1.png)](./media/Warehouse1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]