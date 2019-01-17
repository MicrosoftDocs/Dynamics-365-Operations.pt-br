---
title: "Sincronizar informações em nível de estoque do Finance and Operations no Field Service"
description: "Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar informações em nível de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 3ccc4d406fa4f9800dcdf8697a91892408783196
ms.contentlocale: pt-br
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a>Sincronizar informações em nível de estoque do Finance and Operations no Field Service 

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar informações em nível de estoque do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo e as tarefas subjacentes a seguir são usados para executar a sincronização de níveis de estoque disponíveis do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Field Service.

**Nome do modelo na Integração de dados:**
- Estoque de produtos (Finance and Operations para Field Service)
  
**Nomes das tarefas no projeto de Integração de dados:**
- Estoque de produtos

As seguintes tarefas de sincronização são necessárias antes da sincronização de níveis de estoque:
- Depósitos (Finance and Operations para Field Service) 
- Produtos do Field Service com unidade de estoque (Finance and Operations para Sales) 

## <a name="entity-set"></a>Conjunto de entidades

| Field Service                      | Finance and Operations                 |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Estoque disponível por depósito do CDS     |

## <a name="entity-flow"></a>Fluxo de entidades
As informações em nível de estoque do Finance and Operations são envidas para o Field Service para produtos selecionados. As informações em nível de estoque incluem: 
- Quantidade disponível (quantidade física atual registrada localizada no depósito)
- Na quantidade de ordem (quantidade total registrada na ordem, ou seja, ordens de venda)
- Quantidade solicitada (quantidade total solicitada registrada, ou seja, ordens de compra)

Essas informações são capturadas por produtos lançados para cada depósito e sincronizados com base no controle de alterações, quando o nível de estoque muda.

No Field Service, a solução de integração cria diários de estoque para o delta, a fim de obter níveis no Field Service para corresponder aos níveis no Finance and Operations.

O Finance and Operations funcionará como o mestre para níveis de estoque. Isso é importante para a integração de instalação para ordens de trabalho, transferências e ajustes do Field Service to Finance and Operations se essa funcionalidade for usada no Field Service, junto com a sincronização dos níveis de estoque do Finance and Operations.

Os produtos e os depósitos em que níveis de estoque são dominados do Finance and Operations podem ser controlados com a Filtragem e Consulta Avançada (Power Query).

Observação: É possível criar vários depósitos no Field Services (com É mantido externamente = Não) e depois mapeá-los para um único depósito no Finance and Operations, a funcionalidade Filtragem e consulta avançada. Isso é útil em situações em que você deseja que o Field service domine o nível de estoque detalhado e envie apenas atualizações para Finance and Operations. Nesse caso, o Field Service não receberá atualizações em nível de estoque do Finance and Operations. Consulte as informações adicionais em Sincronizar ajustes de inventário do Field Service para o Finance and Operations e Sincronizar ordens de trabalho no Field Service para ordens de venda vinculadas ao projeto no Finance and Operations.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
A entidade Estoque Externo de Produtos é uma nova entidade que é usada apenas para o back-end na integração. Ela recebe os valores em nível de estoque do Finance and Operations na integração e transforma esses valores em diários de Estoque Manual, que altera os produtos de estoque no depósito. 

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

### <a name="in-the-data-integration-project"></a>No Projeto de integração de dados
Aplique filtros à Filtragem e Consulta Avançada para controlar que somente produtos e depósitos desejados enviam informações em nível de estoque do Finance and Operations para o Field Service.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a>Estoque de produtos (Finance and Operations para Field Service): estoque de produtos

[![Mapeamento de modelo na Integração de dados](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)

