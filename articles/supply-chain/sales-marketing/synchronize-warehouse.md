---
title: "Sincronizar depósitos do Finance and Operations para o Field Service"
description: "Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
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
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a>Sincronizar depósitos do Finance and Operations para o Field Service

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo e as tarefas subjacentes a seguir são usados para executar a sincronização de depósitos do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

**Nome do modelo na Integração de dados:**
- Depósitos (Finance and Operations para Field Service)

**Nomes das tarefas no projeto de Integração de dados:**
- Depósito

## <a name="entity-set"></a>Conjunto de entidades
| Field Service    | Finance and Operations                 |
|------------------|----------------------------------------|
| msdyn_warehouses | Depósitos                             |

## <a name="entity-flow"></a>Fluxo de entidades
Os depósitos criados e mantidos no Finance and Operations podem ser sincronizados com o Field Service por meio de um projeto de integração de dados CDS (Common Data Service). Os depósitos desejados que são sincronizados com o Field Service podem ser controlados com a Filtragem e consulta avançada no projeto. Os depósitos sincronizados do Finance and Operations são criados no Field Service com o campo mantido externamente definido como Sim e o registro torna-se somente leitura.
Solução Field Service CRM: Para dar suporte à integração entre o Field Service e o Finance and Operations, a funcionalidade adicional da solução Field Service CRM é necessária. A solução inclui as alterações a seguir.
O campo **É mantido externamente** foi adicionado à entidade **Depósito (msdyn_warehouses)**. Este campo ajuda a identificar se o depósito é tratado no Operations ou se ele só existe no Field Service.
- Sim – O depósito foi originado do Finance and Operations e não será editável no Sales.
- Nenhum – o depósito foi inserido diretamente no Field Service e é mantido aqui.

O campo **É mantido externamente** ajuda a controlar a sincronização dos níveis de estoque, ajustes, transferências e de uso em ordens de trabalho. Somente os depósitos com **É mantido externamente** = Sim podem ser usados para sincronizar diretamente para o mesmo depósito no outro sistema. 

Observação: É possível criar vários depósitos no Field Services (com **É mantido externamente** = Não) e depois mapeá-los para um único depósito no Finance and Operations, a funcionalidade Filtragem e consulta avançada. Isso é útil em situações em que você deseja que o Field service domine o nível de estoque detalhado e envie apenas atualizações para Finance and Operations. Nesse caso, o Field Service não receberá atualizações em nível de estoque do Finance and Operations. Consulte as informações adicionais em Sincronizar ajustes de inventário do Field Service para o Finance and Operations e Sincronizar ordens de trabalho no Field Service para ordens de venda vinculadas ao projeto no Finance and Operations.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento
### <a name="in-the-data-integration-project"></a>No Projeto de integração de dados
Antes de sincronizar depósitos , verifique se você atualizou Filtragem e consulta avançada no projeto para incluir apenas os depósitos que você deseja trazer do Finance and Operations para o Field Service. Observe que você precisará do depósito no Field Service para aplicá-lo em ordens de trabalho, ajustes e transferências.  

Verifique se **Chave de integração** existe para **msdyn_warehouses**
1. Vá para Integração de dados
2. Selecione a guia **Conjunto de conexão**
3. Selecione o Conjunto de conexão usado para sincronização da Ordem de trabalho
4. Selecione a guia **Chave de integração**
5. Localize msdyn_warehouses e verifique se a chave **msdyn_name (nome)** foi adicionada. Se não for exibida, adicione-a clicando em **Adicionar chave** e clique em **Salvar** na parte superior da página

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a>Depósitos (Finance and Operations para Field Service): Depósito

[![Mapeamento de modelo na Integração de dados](./media/Warehouse1.png)](./media/Warehouse1.png)

