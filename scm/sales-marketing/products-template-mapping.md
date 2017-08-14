---
title: Sincronizar produtos do Finance and Operations com os produtos no Sales
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise para o Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2f14b06b57930256f9211f2085512aa589df083e
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a>Sincronizar produtos do Finance and Operations com os produtos no Sales

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, familiarize-se com a [Integração de dados do Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration). 

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise para o Microsoft Dynamics 365 for Sales.

## <a name="template-and-task"></a>Modelo e tarefa

Os modelos e as tarefas subjacentes a seguir são usados para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (Finance and Operations) para o Microsoft Dynamics 365 for Sales (Sales).

-   Nome do modelo: Produtos (Fin and Ops para Sales)

-   Nome de tarefa no projeto: Produtos

Tarefas de sincronização necessárias antes da sincronização de Produtos: nenhuma

## <a name="entity-set"></a>Conjunto de entidades

| **Finance and Operations** | **CDS** | **Vendas**  |
|----------------------------|---------|------------|
| Produtos liberados comercializáveis | Produto | Produtos   |

## <a name="entity-flow"></a>Fluxo de entidades

Os produtos são gerenciados no Finance and Operations e sincronizados para o Sales. A entidade de dados **Produtos liberados comercializáveis** do Finance and Operations só exporta produtos comercializáveis, o que significa que os produtos têm as informações que devem ser usadas em uma ordem de venda. As mesmas regras se aplicam quando um produto é validado com a função **Validar** na página **Produto liberado**.

O **Número de produto** é usado como chave, o que significa que as grades de produto são sincronizadas para o CDS e o Sales com **IDs de produto** individuais por **Grade de produto**.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

No Sales, um novo campo sobre os produtos, **É Mantido Externamente**, é adicionado para indicar que um determinado produto é mantido externamente. O valor é definido como **Sim** por padrão durante a importação para o Sales.

-   **É Mantido Externamente = Sim**: o produto tem origem no Finance and Operations e não será editável no Sales.

-   **É Mantido Externamente = Não**: o produto é inserido diretamente no Sales.

-   **É Mantido Externamente = em branco**: o produto existia no Sales antes da habilitação da solução Prospect to cash.

A informação de **É Mantido Externamente** é usada para garantir que somente **Cotações** e **Ordens de venda** com **Produtos mantidos externamente** sejam sincronizados para o Finance and Operations.

Os **Produtos mantidos externamente** são adicionados de forma automática à primeira **Lista de preços** válida com a mesma moeda. Observe que a lista é organizada alfabeticamente por **Nome**. O preço de venda do produto do Finance and Operations é usado como o preço na **Lista de preços**. Isso significa que é necessário ter uma **Lista de preços** no Sales para cada **Moeda de vendas de produto** no Finance and Operations. A moeda dos produtos liberados comercializáveis é definida como a moeda contábil da entidade legal da qual o produto é exportado.

> [!NOTE]
> A sincronização de produtos não obterá êxito sem uma **Lista de preços** com a moeda correspondente.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

-   Antes de executar a primeira sincronização, preencha a **Tabela de produtos distintos** para produtos existentes no Finance and Operations. Os produtos existentes não serão sincronizados até que o trabalho seja concluído.

    -   No Finance and Operations, use Pesquisar para procurar **Preencher tabela de produtos distintos**.

    -   Clique na **Preencher tabela de produtos distintos** para executar o trabalho. Este trabalho só precisa ser executado uma vez.

-   Verifique se o **ValueMap** necessário para a **Unidade de Medida** (UDM) de vendas do Finance and Operations existe em **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.

-   Verifique se **Oferece suporte a decimais** para o UDM corresponde aos seus requisitos em **CDS -\> Destination**. Se você exigir valores diferentes por UDM, isso poderá ser feito com **ValueMap** da Unidade, por exemplo, [Each : 0] & [Pound : 2].

    -   O padrão do valor do modelo é 0.

-   Atualize **CDS Organization ID Organization_OrganizationId** em **Source -\> CDS**.

    -   O padrão do valor do modelo é ORG001.

-   Atualize **ValueMap** para **Grupo de unidades** (**defaultuomscheduleid.name**) **CDS -\> Destination** para corresponder a **Grupos de unidades** no Sales.

    -   O padrão do valor do modelo é **Unidade padrão**.

-   Verifique se todas as UDMs de venda de produtos do Finance and Operations existem no Sales com o valor **Listas de separação do CDS**.

-   Verifique se existem **Tabelas de preços** no Sales para cada moeda de venda de produto no Finance and Operations

-   Os produtos podem ser no Sales com o status **Rascunho** ou **Ativo**. Isso é controlado em **Configurações do sistema** em **Vendas** no Sales.

    -   Os produtos criados com o status de rascunho precisam ser ativados antes que possam ser adicionados a **Cotação** ou **Ordem de venda**.

## <a name="template-mapping-in-data-integrator"></a>Mapeamento de modelos no integrador de dados

As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.

![mapeamento de modelos no integrador de dados](./media/products-template-mapping-data-integrator-1.png)

![mapeamento de modelos para produtos no integrador de dados](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Tópicos relacionados

[Sincronizar contas do Sales para clientes no Finance and Operations](accounts-template-mapping.md)

[Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations](contacts-template-mapping.md)

[Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations](sales-quotation-template-mapping.md)


