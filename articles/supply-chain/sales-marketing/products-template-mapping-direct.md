---
title: Sincronizar produtos diretamente do Finance and Operations com produtos no Sales
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b4a6fab3a4831bc3d18313b351e453c615788843
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742415"
---
# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a>Sincronizar produtos diretamente do Finance and Operations com produtos do Sales

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Common Data Service para Aplicativos](https://docs.microsoft.com/powerapps/administrator/data-integrator).

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos diretamente do Microsoft Dynamics 365 for Finance and Operations para o Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales. Os modelos Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.

[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração de PowerApps](https://admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

O modelo e as tarefas subjacentes a seguir são usados para sincronizar produtos do Finance and Operations para o Sales.

- **Nome do modelo na Integração de dados:** Produtos (Fin and Ops para Sales) – Direto
- **Nome da tarefa no projeto de Integração de dados:** Produtos

Nenhuma tarefa de sincronização é necessária para que a sincronização de produtos ocorra.

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations     | Vendas    |
|----------------------------|----------|
| Produtos liberados comercializáveis | Produtos |

## <a name="entity-flow"></a>Fluxo de entidades

Os produtos são gerenciados no Finance and Operations e sincronizados para o Sales. A entidade de dados **Produtos lançados comercializáveis** no Finance and Operations só exporta produtos *comercializáveis*. Os produtos comercializáveis são produtos contendo as informações necessárias para serem usados em uma ordem de venda. As mesmas regras se aplicam quando um produto é validado usando a função **Validar** na página **Produto liberado**.

O número do produto é usado como uma chave. Portanto, quando variantes do produto são sincronizadas para o Sales, cada variante do produto tem uma ID de produto individual.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

No Sales, um novo campo **É Mantido Externamente** foi adicionado em produtos para indicar que determinado produto é mantido externamente. Por padrão, o valor é definido como **Sim** durante uma importação para o Sales. Os valores a seguir estão disponíveis:

- **Sim** – Produto originado do Finance and Operations e não será editável no Sales.
- **Não** – O produto foi inserido diretamente no Sales.
- **(Em branco)** – O produto existia no Sales antes de a solução Prospect to cash ser habilitada.

O campo **É Mantido Externamente** ajuda a garantir que somente cotações e ordens de venda com produtos mantidos externamente sejam sincronizadas para o Finance and Operations.

Os Produtos mantidos externamente são adicionados de forma automática à primeira lista de preços válida com a mesma moeda. Listas de preços são organizadas em ordem alfabética por nome. O preço de venda do produto do Finance and Operations é usado como o preço na lista de preços. Então, é preciso existir uma lista de preços no Sales para cada moeda de venda de produto no Finance and Operations A moeda dos produtos liberados comercializáveis é definida como a moeda contábil da entidade legal da qual o produto é exportado.

> [!NOTE]
> - A sincronização de produto só terá êxito se houver uma lista de preços com uma moeda correspondente.
> - Você pode controlar a lista de preços usada com a integração mapeando o pricelevelid.name [Lista de Preços Padrão (Nome)] no projeto de Integração de Dados. A entrada deve ser toda em letras minúsculas. Por exemplo, o padrão de uma lista de preços no “Sales” chamada 'Padrão' seria: Campo de destino: pricelevelid.name [Lista de Preços Padrão (Nome]) e Tipo de mapa: [ { "transformType": "Padrão ", "defaultValue": "padrão" } ].

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

- Antes de executar a sincronização pela primeira vez, preencha a Tabela de produtos distintos para produtos existentes no Finance and Operations. Os produtos existentes não serão sincronizados até que o trabalho seja concluído.

    1. No Finance and Operations, use Pesquisar para procurar **Preencher tabela de produtos distintos**.
    2. Selecione **Preencher tabela de produtos distintos** para executar o trabalho. Este trabalho deve ser executado apenas uma vez.

- Verifique se existe o mapa de valores obrigatório para a unidade de medida (UDM) de vendas entre o Finance and Operations e o Sales no mapeamento de **SalesUnitSymbol** para **DefaultUnit (Name)**.
- Atualize o mapa de valores para **Grupo de unidades** (**defaultuomscheduleid.name**) para que corresponda a **Grupos de unidades** no Sales.

    O valor do modelo padrão é **Unidade padrão**.

- Verifique se as UDMs de venda para todos os produtos do Finance and Operations existem no Sales.
- Verifique se existem listas de preços no Sales para cada moeda de venda de produto no Finance and Operations
- Quando os produtos são criados no Sales, eles podem ter um status **Rascunho** ou **Ativo**. O comportamento é controlado em **Configurações** > **Administração** > **Configurações do sistema** > **Vendas** no Sales.

    Produtos com o status **Rascunho** quando são criados devem ser ativados antes de serem adicionados às cotações ou ordens de venda.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

A ilustração a seguir mostra um exemplo de um mapeamento de modelo na Integração de dados. 

> [!NOTE]
> O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Finance and Operations..

![Mapeamento de modelo no Integrador de dados](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Tópicos relacionados

[Prospect to cash](prospect-to-cash.md)

[Sincronizar contas diretamente do Sales com clientes do Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations](contacts-template-mapping-direct.md)

[Sincronizar cabeçalhos e linhas de ordem de venda diretamente do Finance and Operations com o Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar cabeçalhos e linhas de fatura diretamente do Finance and Operations com o Sales](sales-invoice-template-mapping-direct.md)



