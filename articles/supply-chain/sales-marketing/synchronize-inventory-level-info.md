---
title: Sincronizar informações do nível de estoque do Supply Chain Management com o Field Service
description: Este artigo discute os modelos e as tarefas subjacentes usadas para sincronizar informações no nível do estoque do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: Henrikan
ms.date: 05/07/2019
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
ms.openlocfilehash: fc14fc63bc1a69a57b10f39b2cb9fb8014e6f70b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844783"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a>Sincronizar informações do nível de estoque do Supply Chain Management com o Field Service 

[!include[banner](../includes/banner.md)]



Este artigo discute os modelos e as tarefas subjacentes usadas para sincronizar informações no nível do estoque do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.

[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service.](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização dos níveis de estoque disponível do Supply Chain Management com o Field Service.

**Modelo na integração de dados**
- Estoque de produtos (Supply Chain Management para Field Service)
  
**Tarefas no projeto de integração de dados**
- Estoque de produtos

As seguintes tarefas de sincronização são necessárias antes da sincronização de níveis de estoque:
- Depósitos (Supply Chain Management para Field Service) 
- Produtos do Field Service com Unidade de estoque (Supply Chain Management para Sales) 

## <a name="entity-set"></a>Conjunto de entidades

| Field Service                      | Gerenciamento da Cadeia de Fornecedores                |
|------------------------------------|----------------------------------------|
| msdynce_externalproductinventories | Estoque disponível por depósito do Dataverse     |

## <a name="entity-flow"></a>Fluxo de entidades
As informações em nível de estoque do Finance and Operations são envidas para o Field Service para produtos selecionados. As informações em nível de estoque incluem: 
- Quantidade disponível (quantidade física atual registrada localizada no depósito)
- Na quantidade de ordem (quantidade total registrada na ordem, como ordens de venda)
- Quantidade solicitada (quantidade total solicitada registrada, como ordens de compra)

Essas informações são capturadas por produtos lançados para cada depósito e sincronizados com base no controle de alterações, quando o nível de estoque muda.

No Field Service, a solução de integração cria diários de estoque para o delta, para que os níveis no Field Service correspondam aos níveis no Supply Chain Management.

O Supply Chain Management funcionará como o mestre para níveis de estoque. Assim, é importante configurar a integração das ordens de serviço, transferências e ajustes do Field Service para o Supply Chain Management se essa funcionalidade for usada no Field Service, junto com a sincronização dos níveis de estoque do Supply Chain Management.

Os produtos e os depósitos em que níveis de estoque são dominados do Supply Chain Management podem ser controlados com a Filtragem e Consulta Avançada (Power Query).

> [!NOTE]
> É possível criar vários depósitos no Field Service (com **É mantido externamente = Não**) depois mapeá-los para um único depósito no Supply Chain Management, com a funcionalidade Filtragem e consulta avançada. Isso é útil em situações em que você deseja que o Field Service domine o nível de estoque detalhado e somente envie atualizações ao Supply Chain Management. Nesse caso, o Field Service não receberá atualizações em nível de estoque do Supply Chain Management. Para obter informações adicionais, consulte [Sincronizar ajustes de estoque do Field Service com o Supply Chain Management](/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) e [Sincronizar ordens de serviço no Field Service com as ordens de vendas vinculadas ao projeto no Supply Chain Management](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
A entidade **Estoque externo de produtos** é usada apenas para o back-end na integração. Essa entidade recebe os valores em nível de estoque do Supply Chain Management na integração e os transforma em diários de estoque manual, que altera os produtos de estoque no depósito.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

### <a name="data-integration"></a>Integração de dados
Para que o projeto funcione, você precisa garantir que a chave de integração está atualizada para msdynce_externalproductinventories.
1.  Acesse **Integração de dados > Conjuntos de conexão**.
2.  Selecione o Conjunto de conexão usado.
3.  Na guia **Chave de integração**, certifique-se de que as chaves a seguir são adicionadas ao msdynce_externalproductinventories:
      - msdynce_productnumber (Número do produto)
      - msdynce_warehouseid (ID do depósito)
      
### <a name="data-integration-project"></a>Projeto de integração de dados
Você pode aplicar filtros com a Filtragem e consulta avançada para que somente determinados produtos e depósitos enviem informações em nível de estoque do Supply Chain Management para o Field Service.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a>Estoque de produtos (Supply Chain Management para Field Service): Estoque de produtos

[![Mapeamento de modelo na Integração de dados.](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]