---
title: Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos do Dynamics 365 Supply Chain Management para o Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: ecee843b6c09c86b4e40ab34cc113e5a7e7c76f8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977678"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a>Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Microsoft Dataverse para Aplicativos](https://docs.microsoft.com/powerapps/administrator/data-integrator).

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos diretamente do Dynamics 365 Supply Chain Management para o Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales. Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.

[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração do Power Apps](https://admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

O modelo e as tarefas subjacentes a seguir são usados para sincronizar produtos do Supply Chain Management para o Sales.

- **Nome do modelo na Integração de dados:** Produtos (Supply Chain Management para Sales) — Direto
- **Nome da tarefa no projeto de Integração de dados:** Produtos

Nenhuma tarefa de sincronização é necessária para que a sincronização de produtos ocorra.

## <a name="entity-set"></a>Conjunto de entidades

| Gerenciamento da Cadeia de Fornecedores    | Vendas    |
|----------------------------|----------|
| Produtos liberados comercializáveis | Produtos |

## <a name="entity-flow"></a>Fluxo de entidades

Os produtos são gerenciados no Supply Chain Management e sincronizados para o Sales. A entidade de dados **Produtos liberados comercializáveis** no Supply Chain Management só exporta produtos *comercializáveis*. Os produtos comercializáveis são produtos contendo as informações necessárias para serem usados em uma ordem de venda. As mesmas regras se aplicam quando um produto é validado usando a função **Validar** na página **Produto liberado**.

O número do produto é usado como uma chave. Portanto, quando variantes do produto são sincronizadas para o Sales, cada variante do produto tem uma ID de produto individual.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

No Sales, um novo campo **É Mantido Externamente** foi adicionado em produtos para indicar que determinado produto é mantido externamente. Por padrão, o valor é definido como **Sim** durante uma importação para o Sales. Os valores a seguir estão disponíveis:

- **Sim** — O produto foi originado do Supply Chain Management e não será editável no Sales.
- **Não** – O produto foi inserido diretamente no Sales.
- **(Em branco)** – O produto existia no Sales antes de a solução Prospect to cash ser habilitada.

O campo **É Mantido Externamente** ajuda a garantir que somente as cotações e ordens de venda com produtos mantidos externamente serão sincronizadas para o Supply Chain Management.

Os Produtos mantidos externamente são adicionados de forma automática à primeira lista de preços válida com a mesma moeda. Listas de preços são organizadas em ordem alfabética por nome. O preço de venda do produto do Supply Chain Management é usado como o preço na lista de preços. Portanto, é preciso existir uma lista de preços no Sales para cada moeda de venda de produto no Supply Chain Management. A moeda dos produtos liberados comercializáveis é definida como a moeda contábil da entidade legal da qual o produto é exportado.

> [!NOTE]
> - A sincronização de produto só terá êxito se houver uma lista de preços com uma moeda correspondente.
> - Você pode controlar a lista de preços usada com a integração mapeando o pricelevelid.name [Lista de Preços Padrão (Nome)] no projeto de Integração de Dados. A entrada deve ser toda em letras minúsculas. Por exemplo, o padrão de uma lista de preços no “Sales” chamada 'Padrão' seria: Campo de destino: pricelevelid.name [Lista de Preços Padrão (Nome]) e Tipo de mapa: [ { "transformType": "Padrão ", "defaultValue": "padrão" } ].

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

- Antes de executar a sincronização pela primeira vez, preencha a Tabela de produtos distintos para os produtos existentes no Supply Chain Management. Os produtos existentes não serão sincronizados até que o trabalho seja concluído.

    1. No Supply Chain Management, use Pesquisar para procurar **Preencher tabela de produtos distintos**.
    2. Selecione **Preencher tabela de produtos distintos** para executar o trabalho. Este trabalho deve ser executado apenas uma vez.

- Verifique se existe o mapa de valores obrigatório para a unidade de medida (UDM) de vendas entre o Supply Chain Management e o Sales no mapeamento de **SalesUnitSymbol** para **DefaultUnit (Name)**.
- Atualize o mapa de valores para **Grupo de unidades** (**defaultuomscheduleid.name**) para que corresponda a **Grupos de unidades** no Sales.

    O valor do modelo padrão é **Unidade padrão**.

- Verifique se as UDMs de venda para todos os produtos do Supply Chain Management existem no Sales.
- Verifique se existem listas de preços no Sales para cada moeda de venda de produto no Supply Chain Management.
- Quando os produtos são criados no Sales, eles podem ter um status **Rascunho** ou **Ativo**. O comportamento é controlado em **Configurações** > **Administração** > **Configurações do sistema** > **Vendas** no Sales.

    Produtos com o status **Rascunho** quando são criados devem ser ativados antes de serem adicionados às cotações ou ordens de venda.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra um exemplo de um mapeamento de modelo na Integração de dados. 

> [!NOTE]
> O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Supply Chain Management.

![Mapeamento de modelo no Integrador de dados](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Tópicos relacionados

[Cliente potencial ao pagamento à vista](prospect-to-cash.md)

[Sincronizar contas diretamente do Sales com clientes no Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management](contacts-template-mapping-direct.md)

[Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management com o Sales](sales-invoice-template-mapping-direct.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]