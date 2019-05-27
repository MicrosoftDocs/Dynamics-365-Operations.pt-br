---
title: Sincronizar contas diretamente do Sales com clientes do Finance and Operations
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar contas do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
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
ms.openlocfilehash: a0cabdab63d4d44010e52303d6f487db1e910059
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561239"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a>Sincronizar contas diretamente do Sales com clientes no Finance and Operations

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Common Data Service para Aplicativos](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar contas diretamente do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations.

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales.  Os modelos Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.

[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração de PowerApps](https://preview.admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

O modelo e a tarefa subjacente a seguir são usados para sincronizar contas do Sales com o Finance and Operations:

- **Nome do modelo na Integração de dados:** Contas (Sales para Fin and Ops) – Direto
- **Nome da tarefa no projeto:** Contas – Clientes

Nenhuma tarefa de sincronização é necessária para que a sincronização de conta/cliente ocorra.

## <a name="entity-set"></a>Conjunto de entidades

| Vendas    | Finance and Operations |
|----------|------------------------|
| Contas | Clientes V2           |

## <a name="entity-flow"></a>Fluxo de entidades

As contas são gerenciadas no Sales e sincronizadas com o Finance and Operations como clientes. A propriedade **É Mantido Externamente** nesses clientes é definida como **Sim** para rastrear clientes originários do Sales. Durante o faturamento, essas informações são usadas para filtrar faturas sincronizadas com o Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

O campo **Número da Conta** está disponível na página **Conta**. Criou-se uma chave natural e exclusiva para oferecer suporte à integração. O recurso de chave natural da solução Gerenciamento de Relacionamento com o Cliente (CRM) pode afetar clientes que já usam o campo **Número da Conta**, mas que não utilizam os valores exclusivos **Número da Conta** por conta. Atualmente, a solução de integração não é compatível nesse caso.

Quando uma nova conta é criada, se um valor **Número da Conta** ainda não existe, ele é automaticamente gerado com uma sequência numérica. O valor consiste em **ACC** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres. Veja um exemplo: **ACC-01000-BVRCPS**

Quando a solução de integração para o Sales é aplicada, um script de atualização define o campo **Número da Conta** para as contas existentes no Sales. Se não houver valores de **Número da Conta**, a sequência numérica mencionada anteriormente será usada.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

- O mapeamento **CustomerGroupId** deve ser atualizado para um valor válido no Finance and Operations. É possível especificar um valor padrão ou definir o valor usando um mapa de valores.

    O valor do modelo padrão é **10**.

- Ao adicionar os mapeamentos a seguir, você poderá ajudar a reduzir o número de atualizações manuais necessárias no Finance and Operations. Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.

    - **SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Finance and Operations. Um site padrão pode ser obtido do produto ou cliente no cabeçalho da ordem.

        O valor do modelo padrão é **1**.

    - **WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Finance and Operations. Um depósito padrão pode ser obtido do produto ou cliente no cabeçalho da ordem do Finance and Operations.

        O valor do modelo padrão é **13**.

    - **LanguageId** – Um idioma é necessário para gerar cotações e ordens de venda no Finance and Operations. Por padrão, o idioma no cabeçalho da ordem do cliente é usado.

        O valor padrão do modelo é **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

> [!NOTE]
> Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados. 

> [!NOTE]
> O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Finance and Operations..

![Mapeamento de modelo na Integração de dados](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Tópicos relacionados


[Prospect to cash](prospect-to-cash.md)

[Sincronizar contas diretamente do Sales com clientes do Finance and Operations](accounts-template-mapping-direct.md)

[Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations](contacts-template-mapping-direct.md)

[Sincronizar cabeçalhos e linhas de ordem de venda diretamente do Finance and Operations com o Sales](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar cabeçalhos e linhas de fatura diretamente do Finance and Operations com o Sales](sales-invoice-template-mapping-direct.md)

