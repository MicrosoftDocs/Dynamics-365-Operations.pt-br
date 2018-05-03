---
title: Sincronizar ordens de trabalho no Field Service com ordens de venda no Finance and Operations
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho no Field Service com ordens de venda no Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08cfd2cfa24bef0f0c92126f5d1052a12ceba37a
ms.openlocfilehash: 854240bef9d6193c8f0f608687b68e6842fe272c
ms.contentlocale: pt-br
ms.lasthandoff: 04/11/2018

---

# <a name="synchronize-work-orders-in-field-service-to-sales-orders-in-finance-and-operations"></a>Sincronizar ordens de trabalho no Field Service com ordens de venda no Finance and Operations

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho no Microsoft Dynamics 365 for Field Service com ordens de venda no Microsoft Dynamics 365 for Finance and Operations.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar ordens de trabalho no Field Service com ordens de venda no Finance and Operations.

## <a name="templates-and-tasks"></a>Modelos e tarefas

Os modelos e as tarefas subjacentes a seguir são usadas para executar a sincronização de ordens de trabalho no Field Service com ordens de venda no Finance and Operations.

### <a name="names-of-the-templates-in-data-integration"></a>Nomes dos modelos na Integração de dados

O modelo **Ordens de trabalho para ordens de venda (Field Service para Fin and Ops)** é usado para executar a sincronização.

### <a name="names-of-the-tasks-in-the-data-integration-project"></a>Nomes das tarefas no projeto de Integração de dados

- WorkOrderHeader
- WorkOrderServiceLineEstimate
- WorkOrderServiceLineUsed
- WorkOrderProductLineEstimate
- WorkOrderProductLineUsed

As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de ordem de venda possa ocorrer:

- Produtos do Field Service (Fin and Ops com o Field Service)
- Contas (Sales com o Fin and Ops) – Direto

## <a name="entity-set"></a>Conjunto de entidades

| **Field Service** | **Finance and Operations** |
|-------------------------|-------------------------|
| msdyn_workorders        | Cabeçalhos de ordens de venda CDS |
| msdyn_workorderservices | Linhas de ordem de venda do CDS   |
| msdyn_workorderproducts | Linhas de ordem de venda do CDS   |

## <a name="entity-flow"></a>Fluxo de entidades

As ordens de serviço são criadas no Field Service. Se as ordens de trabalho incluem somente produtos mantidos externamente e se o valor do **Status da ordem de trabalho** for diferente de **Aberto - Não Agendado** e **Fechado - Cancelado**, as ordens de trabalho podem ser sincronizadas como Finance and Operations por um projeto de integração de Dados de CDS. Aa stualizações nas ordens de trabalho serão sincronizadas como ordens de venda no Finance and Operations. Essas atualizações incluem as informações sobre o tipo e status de origem.

## <a name="estimated-versus-used"></a>Previsto versus usado

No Field Service, os produtos e serviços nas ordens de trabalho têm os valores **Previsto** e **Usado** para quantidades e valores. No entanto, no Finance and Operations, as ordens de venda não têm o mesmo conceito de valores **Previsto** e **Usado** . Para oferecer suporte à alocação de produtos que usa a quantidade prevista na ordem de venda no Finance and Operations, mas mantém a quantidade usada que deve ser consumida e faturada, dois conjuntos de tarefas sincronizam os produtos e serviços na ordem de trabalho. Um conjunto de tarefas é para os valores **Previsto** e outro conjunto de tarefas é para os valores **Usado**.

Esse comportamento permite cenários em que os valores previstos são usados para a alocação ou a reserva no Finance and Operations, enquanto os valores usados são usados para o consumo e o faturamento.

### <a name="estimated"></a>Previsto

Para a sincronização das linhas do produto, os valores **Previsto** serão usados quando o **Status da Linha** for **Previsto**, a opção **Alocado** estiver definida como **Sim** e o valor **Status do Sistema** não for **Fechado - Lançado**.

Para a sincronização das linhas do serviço, os valores **Previsto** serão usados quando o valor **Status da Linha** for **Previsto** e o valor **Status do Sistema** não for **Fechado - Lançado**.

### <a name="used"></a>Usado

Os valores **Usado** serão usados para consumo e o faturamento. Nesses casos, os valores **Usado** serão sincronizados.

A tabela a seguir fornece uma visão geral das várias combinações para linhas de produto.

| Status do Sistema <br>(Field Service) | Status da Linha <br>(Field Service) | Alocado <br>(Field Service) |Valor sincronizado <br>(Finance and Operations) |
|--------------------|-------------|-----------|---------------------------------|
| Aberto - Agendado   | Previsto   | Sim       | Previsto                       |
| Aberto - Agendado   | Previsto   | Não        | Usado                            |
| Aberto - Agendado   | Usado        | Sim       | Usado                            |
| Aberto - Agendado   | Usado        | Não        | Usado                            |
| Aberto - Em Andamento | Previsto   | Sim       | Previsto                       |
| Aberto - Em Andamento | Previsto   | Não        | Usado                            |
| Aberto - Em Andamento | Usado        | Sim       | Usado                            |
| Aberto - Em Andamento | Usado        | Não        | Usado                            |
| Aberto - Concluído   | Previsto   | Sim       | Previsto                       |
| Aberto - Concluído   | Previsto   | Não        | Usado                            |
| Aberto - Concluído   | Usado        | Sim       | Usado                            |
| Aberto - Concluído   | Usado        | Não        | Usado                            |
| Fechado - Lançado    | Previsto   | Sim       | Usado                            |
| Fechado - Lançado    | Previsto   | Não        | Usado                            |
| Fechado - Lançado    | Usado        | Sim       | Usado                            |
| Fechado - Lançado    | Usado        | Não        | Usado                            |

A tabela a seguir fornece uma visão geral das várias combinações para linhas de serviço.

| Status do Sistema <br>(Field Service) | Status da Linha <br>(Field Service) | Valor sincronizado <br>(Finance and Operations) |
|--------------------|-------------|-----------|
| Aberto - Agendado   | Previsto   | Previsto |
| Aberto - Agendado   | Usado        | Usado      |
| Aberto - Em Andamento | Previsto   | Previsto |
| Aberto - Em Andamento | Usado        | Usado      |
| Aberto - Concluído   | Previsto   | Previsto |
| Aberto - Concluído   | Usado        | Usado      |
| Fechado - Lançado    | Previsto   | Usado      |
| Fechado - Lançado    | Usado        | Usado      |

A sincronização dos valores **Previsto** versus **Usado** é gerenciada por meio de dois conjuntos de tarefas para as linhas de produto e as linhas de serviço. Os filtros predefinidos disparam a tarefa correta, e o mapeamento subjacente ajuda a garantir que os valores corretos de **Esperado** versus **Usado** sejam sincronizados.

### <a name="example"></a>Exemplo

1. Uma ordem de trabalho é criada e agendada no Field Service.

    O valor **Status do Sistema** é **Aberto - Agendado**.

    - **Linha de produtos:** Qtd. Prevista = 5ea, Qtd. Usada = 0ea, Status da Linha = Previsto, Alocado = Não
    - **Linha de serviço:** Qtd. Prevista = 2h, Qtd. Usada = 0h, Status da Linha = Previsto

    Neste exemplo, o valor **Qtd Usada** do produto de **0** (zero) e o valor **Qtd Prevista** do serviço de **2h** são sincronizados com o Finance and Operations.

2. Os produtos são alocados no Field Service.

    O valor **Status do Sistema** é **Aberto - Agendado**.

    - **Linha de produtos:** Qtd. Prevista = 5ea, Qtd. Usada = 0ea, Status da Linha = Previsto, Alocado = Sim
    - **Linha de serviço:** Qtd. Prevista = 2h, Qtd. Usada = 0h, Status da Linha = Previsto

    Neste exemplo, o valor **Qtd Prevista** do produto de **5ea** e o valor **Qtd Prevista** do serviço de **2h** são sincronizados com o Finance and Operations.

3. O técnico de serviço comeã a trabalhar na ordem de trabalho e registra o uso de material de 6.

    O valor **Status do Sistema** é **Aberto - Em Andamento**.

    - **Linha de produtos:** Qtd. Prevista = 5ea, Qtd. Usada = 6ea, Status da Linha = Usado, Alocado = Sim
    - **Linha de serviço:** Qtd. Prevista = 2h, Qtd. Usada = 0h, Status da Linha = Previsto

    Neste exemplo, o valor **Qtd Usada** do produto de **6** e o valor **Qtd Prevista** do serviço de **2h** são sincronizados com o Finance and Operations.

4. O técnico de serviço conclui a ordem de trabalho e registra o tempo usado de 1,5 horas.

    O valor **Status do Sistema** é **Aberto - Concluído**.

    - **Linha de produtos:** Qtd. Prevista = 5ea, Qtd. Usada = 6ea, Status da Linha = Usado, Alocado = Sim
    - **Linha de serviço:** Qtd. Prevista = 2h, Qtd. Usada = 1,5h, Status da Linha = Usado

    Neste exemplo, o valor **Qtd Usada** do produto de **6** e o valor **Qtd Prevista** do serviço de **1,5h** são sincronizados com o Finance and Operations.

## <a name="sales-order-origin-and-status"></a>Origem e status da ordem de venda

### <a name="sales-origin"></a>Origem de venda

Para manter o controle das ordens de venda no Finance and Operations que são originárias de ordens de trabalho, você pode criar uma origem de venda em que a opção **Atribuição do tipo de origem** é definida como **Sim** e o campo **Tipo de origem de venda** é definido como **Integração de ordem de trabalho**.

Por padrão, o mapeamento seleciona a origem de venda para o tipo de origem de vendas **Integração de ordem de trabalho** para todas as ordens de venda criadas da partir de ordens de trabalho. Esse comportamento pode ser útil quando você trabalha com a ordem de venda no Finance and Operations. Você deve certificar-se de que as ordens de venda que são originárias das ordens de trabalho não sejam sincronizadas de volta com o Field Service como ordens de trabalho.

Para obter detalhes sobre como criar a configuração correta para a origem de venda no Finance and Operations, consulte a seção "Pré-condições e configuração de mapeamento" deste tópico.

### <a name="status"></a>Status

Quando a ordem de venda for originária de uma ordem de trabalho, o campo **Status de ordens de trabalho externas** será exibido na guia **Configuração** no cabeçalho da ordem de venda. Esse campo mostra o status do sistema da ordem de trabalho no Field Service para ajudar a rastrear o status da ordem de trabalho de ordens de venda no Finance and Operations. Esse campo também pode ajudar o usuário do Finance and Operations a determinar quando a ordem de venda deverá ser enviada ou faturada.

O campo **Status de ordens de trabalho externas** pode ter os seguintes valores:

- Aberto - Agendado
- Aberto - Em Andamento
- Aberto - Concluído
- Fechado - Lançado

## <a name="field-service-crm-solution"></a>Solução Field Service CRM

Para oferecer suporte à integração entre o Field Service e o Finance and Operations, a funcionalidade adicional da solução Field Service do CRM é necessária. A solução inclui as alterações a seguir.

### <a name="work-order-entity"></a>Entidade de ordem de trabalho

O campo **Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade **Ordem de trabalho** e é exibido na página. Ele é usado para controlar consistententemente se uma ordem de trabalho consiste inteiramente em produtos mantidos externamente. Uma ordem de trabalho consiste inteiramente em produtos mantidos externamente quando todos os produtos relacionados são mantidos no Finance and Operations. Esse campo ajuda a garantir que os usuários não sincronizem ordens de trabalho que tenham produtos que sejam desconhecidos para o Finance and Operations.

### <a name="work-order-product-entity"></a>Entidade do produto da ordem de trabalho

- O campo **A Ordem Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade **Produto da Ordem de trabalho** e é exibido na página. Ele é usado para controlar consistententemente se o produto da ordem de trabalho é mantido no Finance and Operations. Esse campo ajuda a garantir que os usuários não sincronizem produtos da ordem de trabalho que que sejam desconhecidos para o Finance and Operations.
- O campo **Status do Sistema do Cabeçalho** foi adicionado à entidade **Produto da Ordem de trabalho** e é exibido na página. Ele é usado para controlar consistententemente o status do sistema da ordem de trabalho e ajuda a garantir a filtragem correta quando os produtos da ordem de trabalho são sincronizadas com o Finance and Operations. Quando os filtros são definidos nas tarefas de integração, as informações **Status do Sistema do Cabeçalho** também serão usadas para determinar se os valores previstos ou usados devem ser sincronizados.
- O campo **Valor da Unidade Faturada** mostra o valor que foi faturado por unidade real usada. O valor é calculado como o valor **Valor Total** dividido pelo valor **Quantidade real** . O campo é usado para a integração a sistemas que não oferecem suporte a valores diferentes para a quantidade usada e a quantidade faturada. Esse campo não é exibido na interface de usuário (IU). 
- O campo **Valor do Desconto Faturado** é calculado como o valor **Valor de desconto** mais arredondamento do cálculo do valor **Valor da Unidade Faturada** . Esse campo é usado para a integração e não é exibido na interface do usuário.
- O campo **Quantidade Decimal** armazena do campo **Quantidade** como um número decimal. Esse campo é usado para a integração e não é exibido na interface do usuário. 
- O valor nos campos **Usado** será redefinido como **0** (zero) se o valor **Status da Linha** do produto da ordem de trabalho for alterado de **Usado** para **Previsto**. Essa alteração ajuda a evitar situações em que uma quantidade usada inserida incorretamente é usada pela sincronização quando o valor **Status da Linha** é **Previsto** e a opção **Alocado** está definida como **Não**.

### <a name="work-order-service-entity"></a>Entidade do serviço da ordem de trabalho

- O campo **A Ordem Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade **Serviço da Ordem de trabalho** e é exibido na página. Ele é usado para controlar consistententemente se o serviço da ordem de trabalho é mantido no Finance and Operations. Esse campo ajuda a garantir que os usuários não sincronizem serviços da ordem de trabalho que que sejam desconhecidos para o Finance and Operations.
- O campo **Status do Sistema do Cabeçalho** foi adicionado à entidade **Serviço da Ordem de trabalho** e é exibido na página. Ele é usado para controlar consistententemente o status do sistema da ordem de trabalho e ajuda a garantir a filtragem correta quando os serviços da ordem de trabalho são sincronizadas com o Finance and Operations. Quando os filtros são definidos nas tarefas de integração, as informações **Status do Sistema do Cabeçalho** também serão usadas para determinar se os valores previstos ou usados devem ser sincronizados.
- O campo **Duração em Horas** armazena o valor do campo **Duração** depois que o valor é convertido de minutos em horas. Esse campo é usado para a integração e não é exibido na interface do usuário.
- O campo **Duração Prevista em Horas** armazena o valor do campo **Duração Prevista** depois que o valor é convertido de minutos em horas. Esse campo é usado para a integração e não é exibido na interface do usuário.
- O campo **Valor da Unidade Faturada** armazena o valor que foi faturado por unidade real usada. O valor é calculado como o valor **Valor Total** dividido pelo valor **Quantidade real** . Esse campo é usado para a integração a sistemas que não oferecem suporte a valores diferentes para a quantidade usada e a quantidade faturada. O campo não é exibido na interface de usuário.
- O campo **Valor do Desconto Faturado** é calculado como o valor **Valor de desconto** mais arredondamento do cálculo do valor **Valor da Unidade Faturada** . Esse campo é usado para a integração e não é exibido na interface do usuário.
- O campo **Ordem de Linha Externa** é um número negativo calculado da ordem de linha que pode ser usado nos sistemas externos em que as linhas de produtos e serviços da ordem de trabalho sejam combinadas. Esse campo permite que produtos da ordem de trabalho que são inseridos tenham os números de linha positivos e os serviços da ordem de trabalho tenham números de linha negativos. O valor desse campo é calculado como o valor **Ordem de Linha** multiplicado por -1. Esse campo não é exibido na interface de usuário.
- O valor nos campos **Usado** será redefinido como **0** (zero) se o valor **Status da Linha** do serviço da ordem de trabalho for alterado de **Usado** para **Previsto** por algum motivo. Essa alteração ajuda a evitar situações em que uma quantidade usada inserida incorretamente é usada pela sincronização quando o valor **Status da Linha** é **Previsto** e o valor **Status do Sistema do Cabeçalho** é **Fechado - Lançado**.

## <a name="preconditions-and-mapping-setup"></a>Precondições e configuração de mapeamento

Antes de sincronizar ordens de trabalho, é importante atualizar as configurações a seguir nos sistemas.

### <a name="setup-in-field-service"></a>Configuração no Field Service

- Verifique se a série de números usada para as ordens de trabalho no Field Service não se sobrepõe à sequência numérica usada para as ordens de venda no Finance and Operations. Caso contrário, as ordens de venda existentes podem ser atualizadas incorretamente no Field Service ou no Finance and Operations.
- O campo **Criação de Fatura de Ordem de Trabalho** deve ser definido como **Nunca**, porque a fatura será gerada no Finance and Operations. Acesse **Field Service** \> **Configurações** \> **Administração** \> **Configurações do Field Service** e verifique se o campo **Criação de Fatura de Ordem de Trabalho** está definido como **Nunca**.

### <a name="setup-in-finance-and-operations"></a>Configuração no Finance and Operations

A integração da ordem de trabalho exige que você configure a origem de venda. A origem de venda é usada para diferenciar as ordens de venda no Finance and Operations criadas a a partir de ordens de trabalho no Field Service. Quando uma ordem de venda tiver uma origem de venda do tipo **Integração de ordem de trabalho**, o campo **Status de ordens de trabalho externas** será exibido no cabeçalho da ordem de venda. Além disso, a origem de venda ajuda a garantir que as ordens de venda criadas a partir de ordens de trabalho no Field Service sejam filtradas durante a sincronização da ordem de venda do Finance and Operations com o Field Service.

1. Acesse **Vendas e marketing** \> **Configurar** \> **Ordens de venda** \> **Origem de venda**.
2. Selecione **Nova** para criar uma nova origem de venda.
3. No campo **Origem de venda** , insira um nome para a origem de venda, como **WorkOrder**.
4. No campo **Descrição** insira uma descrição, como **Ordem de Trabalho do Field Service**.
5. Marque a caixa de seleção **Atribuição do tipo de origem** .
6. Defina o campo **Tipo de origem de vendas** como **Integração de ordem de trabalho**.
7. Selecione **Salvar**.

### <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

(Em breve)
