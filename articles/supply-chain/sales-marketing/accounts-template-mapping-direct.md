---
title: Sincronizar contas diretamente do Sales com clientes no Supply Chain Management
description: Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar contas do Dynamics 365 Sales com o Supply Chain Management.
author: ChristianRytt
ms.date: 10/25/2018
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
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: fff9171966045e9dad5f2c70087a568cfa075e43
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908123"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a>Sincronizar contas diretamente do Sales com clientes no Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Microsoft Dataverse para Aplicativos](/powerapps/administrator/data-integrator).

Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar contas diretamente do Dynamics 365 Sales com o Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales.  Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.

[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração do Power Apps](https://preview.admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

O modelo e as tarefas subjacentes a seguir são usados para sincronizar contas do Sales com o Supply Chain Management:

- **Nome do modelo na Integração de dados:** Contas (Sales para Fin and Ops) – Direto
- **Nome da tarefa no projeto:** Contas – Clientes

Nenhuma tarefa de sincronização é necessária para que a sincronização de conta/cliente ocorra.

## <a name="entity-set"></a>Conjunto de entidades

| Vendas    | Gerenciamento da Cadeia de Fornecedores |
|----------|------------------------|
| Contas | Clientes V2           |

## <a name="entity-flow"></a>Fluxo de entidades

As contas são gerenciadas no Sales e sincronizadas com o Supply Chain Management como clientes. A propriedade **É Mantido Externamente** nesses clientes é definida como **Sim** para rastrear clientes originários do Sales. Durante o faturamento, essas informações são usadas para filtrar faturas sincronizadas com o Sales.

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

A coluna **Número da Conta** está disponível na página **Conta**. Criou-se uma chave natural e exclusiva para oferecer suporte à integração. O recurso de chave natural da solução Gerenciamento de Relacionamento com o Cliente (CRM) pode afetar clientes que já usam a coluna **Número da conta**, mas que não utilizam os valores exclusivos **Número da conta** por conta. Atualmente, a solução de integração não é compatível nesse caso.

Quando uma nova conta é criada, se um valor **Número da Conta** ainda não existe, ele é automaticamente gerado com uma sequência numérica. O valor consiste em **ACC** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres. Veja um exemplo: **ACC-01000-BVRCPS**

Quando a solução de integração para o Sales é aplicada, um script de atualização define a coluna **Número da Conta** para as contas existentes no Sales. Se não houver valores de **Número da Conta**, a sequência numérica mencionada anteriormente será usada.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

- O mapeamento de **CustomerGroupId** deve ser atualizado para um valor válido no Supply Chain Management. É possível especificar um valor padrão ou definir o valor usando um mapa de valores.

    O valor do modelo padrão é **10**.

- Ao adicionar os mapeamentos a seguir, você poderá ajudar a reduzir o número de atualizações manuais necessárias no Supply Chain Management. Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.

    - **SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Supply Chain Management. Um site padrão pode ser obtido do produto ou cliente no cabeçalho da ordem.

        O valor do modelo padrão é **1**.

    - **WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Supply Chain Management. Um depósito padrão pode ser obtido do produto ou do cliente no cabeçalho da ordem do Supply Chain Management.

        O valor do modelo padrão é **13**.

    - **LanguageId** – Um idioma é necessário pra gerar cotações e pedidos de venda no Supply Chain Management. Por padrão, o idioma no cabeçalho da ordem do cliente é usado.

        O valor padrão do modelo é **en-us**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

> [!NOTE]
> As colunas **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídas no mapeamento padrão. Para mapear essas colunas, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a tabela está sincronizada.

As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados. 

> [!NOTE]
> O mapeamento mostra quais informações de coluna serão sincronizadas do Sales com o Supply Chain Management.

![Mapeamento de modelo na Integração de dados](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a>Tópicos relacionados


[Cliente potencial ao pagamento à vista](prospect-to-cash.md)

[Sincronizar contas diretamente do Sales com clientes no Supply Chain Management](accounts-template-mapping-direct.md)

[Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management](contacts-template-mapping-direct.md)

[Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management com o Sales](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]