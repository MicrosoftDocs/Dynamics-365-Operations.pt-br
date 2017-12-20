---
title: "Sincronização de ordens de venda diretamente entre o Sales e o Finance and Operations"
description: "O tópico discute os modelos e as tarefas subjacentes que são usados para executar a sincronização de ordens de venda diretamente entre o Microsoft Dynamics 365 for Sales e o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: ChristianRytt
manager: AnnBe
ms.date: 10/31/2017
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
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 7a828090fa34eb96d2b557eb06e48ad05b421ae8
ms.openlocfilehash: 9aa8c78f5aea5a818d517c2baa9051750b132fc6
ms.contentlocale: pt-br
ms.lasthandoff: 11/20/2017

---

# <a name="synchronization-of-sales-orders-directly-between-sales-and-finance-and-operations"></a>Sincronização de ordens de venda diretamente entre o Sales e o Finance and Operations

[!include[banner](../includes/banner.md)]

O tópico discute os modelos e as tarefas subjacentes que são usados para executar a sincronização de ordens de venda diretamente entre o Microsoft Dynamics 365 for Sales e o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, abra o [Centro de administração de PowerApps](https://preview.admin.powerapps.com/dataintegration). Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.

Os seguintes modelos e as tarefas subjacentes são usados para executar sincronização de ordens de venda diretamente entre o Sales e o Finance and Operations

- **Nomes dos modelos na Integração de dados:** 

    - Ordens de venda (Sales para Fin and Ops) – Direto
    - Ordens de venda (Fin and Ops para Sales) – Direto

- **Nomes das tarefas no projeto de Integração de dados:**

    - OrderHeader
    - OrderLine

As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de fatura de venda possa ocorrer:

- Produtos (Fin and Ops para Sales) – Direto
- Contas (Sales para Fin and Ops) - Direto (se usado)
- Contatos para Clientes (Sales para Fin and Ops) – Direto (se usados)

## <a name="entity-set"></a>Conjunto de entidades

| Finance and Operations  | Vendas             |
|-------------------------|-------------------|
| Cabeçalhos de ordens de venda CDS | SalesOrders       |
| Linhas de ordem de venda do CDS   | SalesOrderDetails |

## <a name="entity-flow"></a>Fluxo de entidades

As ordens de venda são criadas no Sales e sincronizadas para o Finance and Operations quando **Executar projeto** é disparado para um projeto com base no modelo de **Ordens de venda (Sales para Fin and Ops) – Direto**. Você só pode ativar e sincronizar ordens do Sales se todos os **Produtos do Pedido** consistem em produtos que são mantidos externamente. Portanto, não pode haver nenhum produto inserido. Depois que a ordem é ativada, a ordem de venda se torna somente leitura na interface de usuário (IU). Nesse ponto, as atualizações são feitas no Finance and Operations. Depois que a ordem de venda tem um status **Confirmado**, um projeto baseado no modelo **Ordens de Venda (Fin and Ops para Sales) - Direto** pode ser usado para sincronizar atualizações ou o status de atendimento do Finance and Operations para o Sales.

Você não precisa criar ordens no Sales. Você pode criar novas ordens de venda no Finance and Operations. Depois que uma ordem de venda tem um status **Confirmado**, ela é sincronizada com o Sales conforme descrito no parágrafo anterior.

No Finance and Operations, os filtros no modelo ajudam a garantir que somente as ordens de venda relevantes sejam incluídas na sincronização:

- Na ordem de venda, a solicitação e o faturamento do cliente precisam ter origem no Sales para serem incluídos na sincronização. No Finance and Operations, os campos **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** são usados para filtrar ordens de venda das entidades de dados.
- A ordem de venda no Finance and Operations deve ser confirmada. Somente ordens de venda confirmadas ou ordens de venda com status de processamento superior, como **Enviado** ou **Faturado** são sincronizadas com o Sales.
- Após uma ordem de venda ser criada ou modificada, o trabalho em lotes **Calcular totais de vendas** no Finance and Operations deve ser executado. Somente as ordens de venda em que os totais de vendas são calculados serão sincronizadas para o Sales.

## <a name="freight-tax"></a>Taxa de frete

O Sales não dá suporte a impostos em nível de cabeçalho, pois os impostos são armazenados em nível de linha. Para dar suporte a impostos em nível de cabeçalho no Finance and Operations, como imposto sobre frete, o sistema sincroniza impostos para o Sales como um produto inserido que é chamado de **Taxa de Imposto sobre Frete**, e que tem o valor de imposto do Finance and Operations. Dessa forma, o cálculo de preços padrão no Sales pode ser usado para totais, mesmo quando há um imposto em nível de cabeçalho do Finance and Operations.

## <a name="discount-calculation-and-rounding"></a>Cálculo de desconto e arredondamento

O modelo de cálculo de desconto no Sales difere do modelo de cálculo de desconto no Finance and Operations. No Finance and Operations, o valor final de descontos em uma linha de venda pode ser o resultado de uma combinação de valores de desconto e porcentagens de desconto. Se este valor final de descontos for dividido pela quantidade na linha, poderá haver um arredondamento. No entanto, esse arredondamento não é considerado se um valor de desconto por unidade arredondado é sincronizado para o Sales. Para ajudar a garantir que o valor total do desconto da linha de venda no Finance and Operations seja sincronizado corretamente para o Sales, o valor total deve ser sincronizado sem ser dividido pela quantidade da linha. Portanto, você deve definir o **Método de cálculo de desconto** como **Item de linha** no Sales.

Quando uma linha de ordem de venda for sincronizada do Sales para o Finance and Operations, o valor de desconto de linha total será usado. Como o Finance and Operations não tem campos que possam armazenar o valor total de desconto para uma linha, o valor é dividido pela quantidade e armazenado no campo **Desconto de linha**. Qualquer arredondamento que ocorrer nesta divisão será armazenado no campo **Encargos de venda** na linha de venda.

### <a name="example"></a>Exemplo

**Sincronização do Sales para o Finance and Operations**

- **Vendas:** Quantidade = 3, desconto por linha = $ 10,00
- **Finance and Operations:** Quantidade = 3, valor de desconto de linha = $ 3,33, encargos de vendas = -$ 0,01 

**Sincronização do Finance and Operations para o Sales**

- **Finance and Operations:** Quantidade = 3, valor de desconto de linha = $ 3,33, encargos de vendas = -$ 0,01
- **Vendas:** Quantidade = 3, desconto por linha = (3 × $ 3,33) + $ 0,01 = $ 10,00

## <a name="prospect-to-cash-solution-for-sales"></a>Solução Prospect to cash para o Sales

Novos campos foram adicionados à entidade **Ordem** e são exibidos na página:

- **É mantido externamente** – Defina esta opção como **Sim** quando a ordem for proveniente do Finance and Operations.
- **Status de processamento** – Este campo mostra o status de processamento da ordem no Finance and Operations. Os valores a seguir estão disponíveis:

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

A configuração **Tem Somente Produtos Mantidos Externamente** é usada durante a ativação da ordem para rastrear, de forma consistente, se a ordem de venda consiste inteiramente em produtos mantidos externamente. Se uma ordem de venda consiste inteiramente em produtos mantidos externamente, os produtos são mantidos no Finance and Operations. Esta configuração ajuda a garantir que você não ative e tente sincronizar linhas de ordem de venda com produtos que sejam desconhecidos para o Finance and Operations.

Os botões **Criar fatura**, **Cancelar Ordem**, **Recalcular**, **Obter Produtos** e **Procurar Endereço** na página **Ordem de venda** são ocultos para ordens mantidas externamente, pois as faturas serão criadas no Finance and Operations e sincronizadas para o Sales. Essas ordens não podem ser editadas, pois as informações da ordem de venda serão sincronizadas do Finance and Operations após a ativação.

O status da ordem de venda permanecerá **Ativo** para ajudar a garantir que as alterações do Finance and Operations possam fluir para a ordem de venda do Sales. Para controlar este comportamento, defina o padrão do valor **Statecode \[Status\]** para **Ativo** no Projeto de integração de dados.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

Antes de sincronizar ordens de venda, é importante atualizar as configurações a seguir nos sistemas.

### <a name="setup-in-sales"></a>Configuração no Sales

- Verifique se as permissões estão definidas para a equipe à qual foi atribuído o usuário da conexão do Sales definida. Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas a equipe não tem acesso admin. Se a equipe não tiver acesso de administrador, quando você executar o projeto na Integração de dados, você receberá uma mensagem de erro indicando que a Equipe principal está ausente.

    Vá para **Configurações** &gt; **Segurança** &gt; **Equipes**, selecione a equipe relevante, selecione **Gerenciar Funções** e selecione a função que tem as permissões desejadas, como **Administrador do Sistema**.

- Vá para **Configurações** &gt; **Administração** &gt; **Configurações do sistema** &gt; **Vendas** e certifique-se de que as seguintes configurações sejam usadas:

    - A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.
    - O campo **Método de cálculo de desconto** está definido como **Item de linha**.

### <a name="setup-in-finance-and-operations"></a>Configuração no Finance and Operations

- Vá para **Vendas e marketing** &gt; **Tarefas periódicas** &gt; **Calcular totais de vendas**, e configure o trabalho para ser executado como um trabalho em lotes. Defina a opção **Calcular totais de ordens de venda** como **Sim**. Esta etapa é importante, pois somente as ordens de venda em que os totais de vendas são calculados serão sincronizadas para o Sales. A frequência do trabalho em lotes deve ser alinhada à frequência de sincronização da ordem de venda.

### <a name="setup-in-the-sales-orders-sales-to-fin-and-ops---direct-data-integration-project"></a>Configuração de Ordens de venda (Sales para Fin and Ops) - Projeto de integração de dados diretos

- Verifique se o mapeamento exigido existe para **Shipto\_country** para **DeliveryAddressCountryRegionISOCode**. Você pode tornar em branco um padrão no mapa de valores para não precisar digitar o país de ordens nacionais. Defina o lado esquerdo como 'Embranco', e o lado direito com o país ou a região desejada.

    O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados, e onde 'Em branco' = EUA.

### <a name="setup-in-the-sales-orders-fin-and-ops-to-sales---direct-data-integration-project"></a>Configuração de Ordens de venda (Fin and Ops para Sales) – Projeto de integração de dados diretos

#### <a name="salesheader-task"></a>Tarefa de SalesHeader

- Uma lista de preços é necessária para criar ordens no Sales. Atualize o mapa de valores para **pricelevelid.name \[Price List Name\]** para a lista de preços que é usada no Sales por moeda. Você pode usar a lista de preços padrão para uma única moeda. Caso existam listas de preços em várias moedas, você poderá usar um mapa de valores.

    O valor do modelo padrão para **pricelevelid.name \[Price List Name\]** é **CRM Service USA (sample)**.

#### <a name="salesline-task"></a>Tarefa de SalesLine

- Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Finance and Operations.
- Verifique se as unidades necessários estão definidas no Sales.

    Um valor do modelo que tem um mapa de valores é definido para o **SalesUnitSymbol** para **oumid.name**.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

> [!NOTE]
> Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados.

> [!NOTE]
> O mapeamento mostra quais informações de campo serão sincronizadas do Sales para o Finance and Operations, ou vice-versa..

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderheader"></a>Ordens de venda (Fin and Ops para Sales) – Direto: OrderHeader

[![Mapeamento de modelo na Integração de dados](./media/sales-order-direct-template-mapping-data-integrator-1.png)](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="sales-orders-fin-and-ops-to-sales---direct-orderline"></a>Ordens de venda (Fin and Ops para Sales) – Direto: OrderLine

[![Mapeamento de modelo na integração de dados](./media/sales-order-direct-template-mapping-data-integrator-2.png)](./media/sales-order-direct-template-mapping-data-integrator-2.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderheader"></a>Ordens de venda (Sales para Fin and Ops) – Direto: OrderHeader

[![Mapeamento de modelo na integração de dados](./media/sales-order-direct-template-mapping-data-integrator-3.png)](./media/sales-order-direct-template-mapping-data-integrator-3.png)

### <a name="sales-orders-sales-to-fin-and-ops---direct-orderline"></a>Ordens de venda (Sales para Fin and Ops) – Direto: OrderLine

[![Mapeamento de modelo na integração de dados](./media/sales-order-direct-template-mapping-data-integrator-4.png)](./media/sales-order-direct-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a>Tópicos relacionados

[Prospect to cash](prospect-to-cash.md)

