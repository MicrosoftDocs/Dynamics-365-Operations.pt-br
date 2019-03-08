---
title: Sincronizar informações em nível de estoque do Finance and Operations no Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar informações no nível do estoque do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
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
ms.openlocfilehash: b81694f1ed56d8542de46203ac5faf5fae2b6645
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "356774"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a>Sincronizar informações do nível de estoque do Finance and Operations no Field Service 

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar informações no nível do estoque do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização dos níveis de estoque disponível do Microsoft Dynamics 365 for Finance and Operations com o Microsoft Dynamics 365 for Field Service.

**Modelo na integração de dados**
- Estoque de produtos (Finance and Operations para Field Service)
  
**Tarefas no projeto de integração de dados**
- Estoque de produtos

As seguintes tarefas de sincronização são necessárias antes da sincronização de níveis de estoque:
- Depósitos (Finance and Operations para Field Service) 
- Produtos do Field Service com unidade de estoque (Finance and Operations para Sales) 

## <a name="entity-set"></a>Conjunto de entidades

| Field Service                      | Finance and Operations                 |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Estoque disponível por depósito do CDS     |

## <a name="entity-flow"></a>Fluxo de entidades
As informações em nível de estoque do Finance and Operations são envidas para o Field Service para produtos selecionados. As informações em nível de estoque incluem: 
- Quantidade disponível (quantidade física atual registrada localizada no depósito)
- Na quantidade de ordem (quantidade total registrada na ordem, como ordens de venda)
- Quantidade solicitada (quantidade total solicitada registrada, como ordens de compra)

Essas informações são capturadas por produtos lançados para cada depósito e sincronizados com base no controle de alterações, quando o nível de estoque muda.

No Field Service, a solução de integração cria diários de estoque para o delta, para que os níveis no Field Service correspondam aos níveis no Finance and Operations.

O Finance and Operations funcionará como o mestre para níveis de estoque. Assim, é importante configurar a integração das ordens de trabalho, transferências e ajustes do Field Service para o Finance and Operations se essa funcionalidade for usada no Field Service, junto com a sincronização dos níveis de estoque do Finance and Operations.

Os produtos e os depósitos em que níveis de estoque são dominados do Finance and Operations podem ser controlados com a Filtragem e Consulta Avançada (Power Query).

> [!NOTE]
> É possível criar vários depósitos no Field Service (com **É mantido externamente = Não**) depois mapeá-los para um único depósito no Finance and Operations, com a funcionalidade Filtragem e consulta avançada. Isso é útil em situações em que você deseja que o Field Service domine o nível de estoque detalhado e somente envie atualizações ao Finance and Operations. Nesse caso, o Field Service não receberá atualizações em nível de estoque do Finance and Operations. Para informações adicionais, consulte [Sincronizar ajustes de estoque do Field Service com o Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizar ordens de trabalho no Field Service com as ordens de vendas vinculadas ao projeto no Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
A entidade **Estoque externo de produtos** é usada apenas para o back-end na integração. Essa entidade recebe os valores em nível de estoque do Finance and Operations na integração e os transforma em diários de estoque manual, que altera os produtos de estoque no depósito.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

### <a name="data-integration-project"></a>Projeto de integração de dados
Você pode aplicar filtros com a Filtragem e Consulta Avançada para que somente determinados produtos e depósitos enviem informações em nível de estoque do Finance and Operations para o Field Service.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a>Estoque de produtos (Finance and Operations para Field Service): estoque de produtos

[![Mapeamento de modelo na Integração de dados](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)
