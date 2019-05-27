---
title: Sincronizar depósitos do Finance and Operations para o Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 7e6d7626c00b9d7d98ce872652653c36ce7bc975
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1535666"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a>Sincronizar depósitos do Finance and Operations no Field Service

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização de depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

**Modelo na integração de dados**
- Depósitos (Fin and Ops com o Field Service)

**Tarefas no projeto de integração de dados**
- Depósito

## <a name="entity-set"></a>Conjunto de entidades
| Field Service    | Finance and Operations                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Depósitos                             |

## <a name="entity-flow"></a>Fluxo de entidades
Os depósitos criados e mantidos no Finance and Operations podem ser sincronizados com o Field Service por meio de um projeto de integração de dados CDS (Common Data Service). Os depósitos que você quer sincronizar com o Field Service podem ser controlados com a Filtragem e consulta avançada no projeto. Os depósitos sincronizados do Finance and Operations são criados no Field Service com o campo **É mantido externamente** definido como **Sim** e o registro torna-se somente leitura.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
Para oferecer suporte à integração entre o Field Service e o Finance and Operations, a funcionalidade adicional da solução Field Service do CRM é necessária. Na solução, o campo **É mantido externamente** foi adicionado à entidade **Depósito (msdyn_warehouses)**. Este campo ajuda a identificar se o depósito é tratado no Finance and Operations ou se ele só existe no Field Service. As configurações desse campo são:
- **Sim** – O depósito foi originado do Finance and Operations e não será editável no Sales.
- **Não** – o depósito foi inserido diretamente no Field Service e é mantido aqui.

O campo **É mantido externamente** ajuda a controlar a sincronização dos níveis de estoque, ajustes, transferências e uso em ordens de trabalho. Somente os depósitos com **É mantido externamente** definido como **Sim** podem ser usados para sincronizar diretamente com o mesmo depósito no outro sistema. 

> [!NOTE]
> É possível criar vários depósitos no Field Service (com **É mantido externamente** = Não) e depois mapeá-los para um único depósito no Finance and Operations, com a funcionalidade Filtragem e consulta avançada. Isso é útil em situações em que você deseja que o Field Service domine o nível de estoque detalhado e envie apenas atualizações ao Finance and Operations. Nesse caso, o Field Service não receberá atualizações em nível de estoque do Finance and Operations. Para informações adicionais, consulte [Sincronizar ajustes de estoque do Field Service com o Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizar ordens de trabalho no Field Service com as ordens de vendas vinculadas ao projeto no Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento
### <a name="data-integration-project"></a>Projeto de integração de dados
Antes de sincronizar depósitos , verifique se você atualizou a Filtragem e consulta avançada no projeto para incluir apenas os depósitos que você deseja trazer do Finance and Operations para o Field Service. Observe que você precisará do depósito no Field Service para aplicá-lo em ordens de trabalho, ajustes e transferências.  

Para garantir que a **Chave de integração** exista para **msdyn_warehouses**:
1. Vá para Integração de dados.
2. Selecione a guia **Conjunto de conexão**.
3. Selecione o conjunto de conexão usado para a sincronização da ordem de trabalho.
4. Selecione a guia **Chave de integração**.
5. Localize msdyn_warehouses e verifique se a chave **msdyn_name (nome)** foi adicionada. Se não for exibida, adicione-a clicando em **Adicionar chave** e clique em **Salvar**, na parte superior da página.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="warehouses-fin-and-ops-to-field-service-warehouse"></a>Depósitos (Fin and Ops com o Field Service): Depósito

[![Mapeamento de modelo na Integração de dados](./media/Warehouse1.png)](./media/Warehouse1.png)
