---
title: Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management
description: O tópico discute os modelos e as tarefas subjacentes que são usados para executar a sincronização de ordens de venda diretamente entre o Dynamics 365 Sales e o Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 05/09/2019
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
ms.openlocfilehash: f0e26c63635179dc4c145f8d08e85fd110d9caac
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817764"
---
# <a name="synchronization-of-sales-orders-directly-between-sales-and-supply-chain-management"></a>Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

O tópico discute os modelos e as tarefas subjacentes que são usados para executar a sincronização de ordens de venda diretamente entre o Dynamics 365 Sales e o Dynamics 365 Supply Chain Management.

## <a name="data-flow-in-prospect-to-cash"></a>Fluxo de dados no Prospect to cash

A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales. Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados para contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales. A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.

[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração do Power Apps](https://preview.admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

Os seguintes modelos e as tarefas subjacentes são usados para executar sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management.

- **Nomes dos modelos na Integração de dados:** 

    - Ordens de Venda (Sales para Supply Chain Management) – Direto
    - Ordens de Venda (Supply Chain Management para Sales) – Direto

- **Nomes das tarefas no projeto de Integração de dados:**

    - OrderHeader
    - OrderLine

As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de fatura de venda possa ocorrer:

- Produtos (Supply Chain Management para Sales) – Direto
- Contas (Sales para Supply Chain Management) – Direto (se usado)
- Contatos para Clientes (Sales para Supply Chain Management) – Direto (se usado)

## <a name="entity-set"></a>Conjunto de entidades

| Gerenciamento da Cadeia de Fornecedores  | Vendas             |
|-------------------------|-------------------|
| Cabeçalhos de ordens de venda do Dataverse | SalesOrders       |
| Linhas de ordens de venda do Dataverse   | SalesOrderDetails |

## <a name="entity-flow"></a>Fluxo de entidades

As ordens de venda são criadas no Sales e sincronizadas para o Supply Chain Management quando **Executar projeto** é disparado para um projeto com base no modelo de **Ordens de Venda (Sales para Supply Chain Management) – Direto**. Você só pode ativar e sincronizar ordens do Sales se todos os **Produtos do Pedido** consistem em produtos que são mantidos externamente. Portanto, não pode haver nenhum produto inserido. Depois que a ordem é ativada, a ordem de venda se torna somente leitura na interface de usuário (IU). Nesse ponto, as atualizações são feitas no Supply Chain Management. Depois que a ordem de venda tem um status **Confirmado**, um projeto baseado no modelo **Ordens de Venda (Supply Chain Management para Sales) – Direto** pode ser usado para sincronizar atualizações ou o status de atendimento do Supply Chain Management para Sales.

Você não precisa criar ordens no Sales. É possível criar novas ordens de venda no Supply Chain Management. Depois que uma ordem de venda tem um status **Confirmado**, ela é sincronizada com o Sales conforme descrito no parágrafo anterior.

No Supply Chain Management, os filtros no modelo ajudam a garantir que somente as ordens de venda relevantes sejam incluídas na sincronização:

- Na ordem de venda, a solicitação e o faturamento do cliente precisam ter origem no Sales para serem incluídos na sincronização. No Supply Chain Management, as colunas **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** são usadas para filtrar ordens de venda das tabelas de dados.
- A ordem de venda no Supply Chain Management deve ser confirmada. Somente ordens de venda confirmadas ou ordens de venda com status de processamento superior, como **Enviado** ou **Faturado** são sincronizadas com o Sales.
- Depois que uma ordem de venda é criada ou modificada, o trabalho em lotes **Calcular totais de vendas** no Supply Chain Management deve ser executado. Somente as ordens de venda em que os totais de vendas são calculados serão sincronizadas para o Sales.

## <a name="freight-tax"></a>Taxa de frete

O Sales não dá suporte a impostos em nível de cabeçalho, pois os impostos são armazenados em nível de linha. Para permitir impostos no nível de cabeçalho no Supply Chain Management, como imposto sobre frete, o sistema sincroniza impostos com o Sales como um produto fora do catálogo que é chamado de **Taxa de Imposto sobre Frete** e que tem o valor de imposto do Supply Chain Management. Dessa forma, o cálculo de preços padrão no Sales pode ser usado para totais, mesmo quando há um imposto no nível de cabeçalho do Supply Chain Management.

## <a name="discount-calculation-and-rounding"></a>Cálculo de desconto e arredondamento

O modelo de cálculo de desconto no Sales difere do modelo de cálculo de desconto no Supply Chain Management. No Supply Chain Management, o valor final de descontos em uma linha de venda pode ser o resultado de uma combinação de valores de desconto e porcentagens de desconto. Se este valor final de descontos for dividido pela quantidade na linha, poderá haver um arredondamento. No entanto, esse arredondamento não é considerado se um valor de desconto por unidade arredondado é sincronizado para o Sales. Para ajudar a garantir que o valor total do desconto da linha de venda no Supply Chain Management seja sincronizado corretamente para o Sales, o valor total deve ser sincronizado sem ser dividido pela quantidade da linha. Portanto, você deve definir o **Método de cálculo de desconto** como **Item de linha** no Sales.

Quando uma linha da ordem de venda for sincronizada do Sales para o Supply Chain Management, o valor de desconto de linha total será usado. Como o Supply Chain Management não tem campos que possam armazenar o valor total de desconto para uma linha, o valor é dividido pela quantidade e armazenado no campo **Desconto de linha**. Qualquer arredondamento que ocorrer nesta divisão será armazenado no campo **Encargos de venda** na linha de venda.

### <a name="example"></a>Exemplo

**Sincronização do Sales para o Supply Chain Management**

- **Vendas:** Quantidade = 3, desconto por linha = $ 10,00
- **Supply Chain Management:** Quantidade = 3, valor do desconto de linha = US$ 3,33, encargo de venda = -US$ 0,01 

**Sincronização do Supply Chain Management para Sales**

- **Supply Chain Management:** Quantidade = 3, valor do desconto de linha = US$ 3,33, encargo de venda = -US$ 0,01
- **Vendas:** Quantidade = 3, desconto por linha = (3 × $ 3,33) + $ 0,01 = $ 10,00

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

Novas colunas foram adicionadas à tabela **Ordem** e são exibidas na página:

- **É mantido externamente** – Defina essa opção como **Sim** quando a origem da ordem for o Supply Chain Management.
- **Status de processamento** – Esta coluna mostra o status de processamento da ordem no Supply Chain Management. Os valores a seguir estão disponíveis:

    - **Rascunho** – O status inicial quando uma ordem é criada no Sales. No Sales, só podem ser editadas ordens com este status de processamento.
    - **Ativo** – O status depois que a ordem é ativada no Sales usando o botão **Ativar**.
    - **Confirmado**
    - **Guia de remessa**
    - **Faturado**
    - **Separado**
    - **Parcialmente separada**
    - **Parcialmente embalada**
    - **Remetido**
    - **Parcialmente remetida**
    - **Parcialmente faturada**
    - **Cancelado**

A configuração **Tem Somente Produtos Mantidos Externamente** é usada durante a ativação da ordem para rastrear, de forma consistente, se a ordem de venda consiste inteiramente em produtos mantidos externamente. Se uma ordem de venda consistir inteiramente em produtos mantidos externamente, os produtos serão mantidos no Supply Chain Management. Essa configuração ajuda a garantir que você não ative nem tente sincronizar linhas da ordem de venda que tenham produtos que sejam desconhecidos para o Supply Chain Management.

Os botões **Criar fatura**, **Cancelar Ordem**, **Recalcular**, **Obter Produtos** e **Procurar Endereço** na página **Ordem de venda** são ocultados para ordens mantidas externamente, pois as faturas serão criadas no Supply Chain Management e sincronizadas para o Sales. Essas ordens não podem ser editadas, pois as informações da ordem de venda serão sincronizadas do Supply Chain Management após a ativação.

O status da ordem de venda permanecerá **Ativo** para ajudar a garantir que as alterações no Supply Chain Management possam fluir para a ordem de venda no Sales. Para controlar este comportamento, defina o padrão do valor **Statecode \[Status\]** para **Ativo** no Projeto de integração de dados.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

Antes de sincronizar ordens de venda, é importante atualizar as configurações a seguir nos sistemas.

### <a name="setup-in-sales"></a>Configuração no Sales

- Verifique se as permissões estão definidas para a equipe à qual foi atribuído o usuário da conexão do Sales definida. Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas a equipe não tem acesso admin. Se a equipe não tiver acesso de administrador, quando você executar o projeto na Integração de dados, você receberá uma mensagem de erro indicando que a Equipe principal está ausente.

    Vá para **Configurações** &gt; **Segurança** &gt; **Equipes**, selecione a equipe relevante, selecione **Gerenciar Funções** e selecione a função que tem as permissões desejadas, como **Administrador do Sistema**.

- Para assegurar o cálculo correto de descontos no Sales e no Supply Chain Management, o **Método de cálculo de desconto** deve ser definido como **Item de linha**.
- Vá para **Configurações** &gt; **Administração** &gt; **Configurações do sistema** &gt; **Vendas** e certifique-se de que as seguintes configurações sejam usadas:

    - A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.
    - A coluna **Método de cálculo de desconto** está definida como **Item de linha**.

### <a name="setup-in-supply-chain-management"></a>Configuração no Supply Chain Management

- Vá para **Vendas e marketing** &gt; **Tarefas periódicas** &gt; **Calcular totais de vendas**, e configure o trabalho para ser executado como um trabalho em lotes. Defina a opção **Calcular totais de ordens de venda** como **Sim**. Esta etapa é importante, pois somente as ordens de venda em que os totais de vendas são calculados serão sincronizadas para o Sales. A frequência do trabalho em lotes deve ser alinhada à frequência de sincronização da ordem de venda.

Se você também usa a integração da ordem de trabalho, você precisa configurar a origem de venda. A origem de venda é usada para diferenciar as ordens de venda no Supply Chain Management criadas com base em ordens de serviço no Field Service. Quando uma ordem de venda tiver uma origem de venda do tipo **Integração de ordem de trabalho**, o campo **Status de ordens de trabalho externas** será exibido no cabeçalho da ordem de venda. Além disso, a origem de venda garante que as ordens de venda criadas com base em ordens de serviço no Field Service sejam filtradas durante a sincronização da ordem de venda do Supply Chain Management para o Field Service.

1. Acesse **Vendas e marketing** \> **Configurar** \> **Ordens de venda** \> **Origem de venda**.
2. Selecione **Nova** para criar uma nova origem de venda.
3. Na coluna **Origem de venda**, insira um nome para a origem de venda, como **SalesOrder**.
4. Na coluna **Descrição**, insira uma descrição, como **Ordem de venda do Sales**.
5. Marque a caixa de seleção **Atribuição do tipo de origem** .
6. Defina a coluna **Tipo de origem de venda** como **Integração da ordem de venda**.
7. Selecione **Salvar**.

### <a name="setup-in-the-sales-orders-sales-to-supply-chain-management---direct-data-integration-project"></a>Configuração nas Ordens de Venda (Sales para Supply Chain Management) - Projeto de integração de dados direta

- Verifique se o mapeamento exigido existe para **Shipto\_country** para **DeliveryAddressCountryRegionISOCode**. Você pode tornar em branco um padrão no mapa de valores para não precisar digitar o país de ordens nacionais. Defina o lado esquerdo como 'Embranco', e o lado direito com o país ou a região desejada.

    O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados, e onde 'Em branco' = EUA.

### <a name="setup-in-the-sales-orders-supply-chain-management-to-sales---direct-data-integration-project"></a>Configuração nas Ordens de Venda (Supply Chain Management para Sales) - Projeto de integração de dados direta

#### <a name="salesheader-task"></a>Tarefa de SalesHeader

- Uma lista de preços é necessária para criar ordens no Sales. Atualize o mapa de valores para **pricelevelid.name \[Price List Name\]** para a lista de preços que é usada no Sales por moeda. Você pode usar a lista de preços padrão para uma única moeda. Caso existam listas de preços em várias moedas, você poderá usar um mapa de valores.

    O valor do modelo padrão para **pricelevelid.name \[Price List Name\]** é **CRM Service USA (sample)**.

#### <a name="salesline-task"></a>Tarefa de SalesLine

- Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Supply Chain Management.
- Verifique se as unidades necessários estão definidas no Sales.

    Um valor do modelo que tem um mapa de valores é definido para o **SalesUnitSymbol** para **oumid.name**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

> [!NOTE]
> As colunas **Condições de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não fazem parte dos mapeamentos padrão. Para mapear essas colunas, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a tabela está sincronizada.

As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados.

> [!NOTE]
> O mapeamento mostra quais informações de coluna serão sincronizadas do Sales para o Supply Chain Management ou do Supply Chain Management para o Sales.

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderheader"></a>Ordens de Venda (Supply Chain Management para Sales) – Direto: OrderHeader

[![Mapeamento de modelo na Integração de dados](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-supply-chain-management-to-sales---direct-orderline"></a>Ordens de Venda (Supply Chain Management para Sales) – Direto: OrderLine

[![Mapeamento de modelo na integração de dados](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderheader"></a>Ordens de Venda (Sales para Supply Chain Management) – Direto: OrderHeader

[![Mapeamento de modelo na integração de dados](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-supply-chain-management---direct-orderline"></a>Ordens de Venda (Sales para Supply Chain Management) – Direto: OrderLine

[![Mapeamento de modelo na integração de dados](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Tópicos relacionados

[Cliente potencial ao pagamento à vista](prospect-to-cash.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]