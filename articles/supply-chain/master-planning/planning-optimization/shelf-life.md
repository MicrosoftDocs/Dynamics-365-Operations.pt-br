---
title: Planejamento mestre para produtos com validade limitada
description: Este artigo descreve como configurar e usar recursos de planejamento que levam em conta a vida útil de produtos perecíveis.
author: t-benebo
ms.date: 08/10/2022
ms.topic: article
ms.search.form: ReqPlanSched, CustTable, EcoResProductDetailsExtended, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 95c905cbcc3c057dbccf2b7d6e894b1e99ddfba5
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337124"
---
# <a name="master-planning-for-products-with-limited-shelf-life"></a>Planejamento mestre para produtos com validade limitada

[!include [banner](../../includes/banner.md)]

A validade é o período de tempo que um produto pode ser armazenado até que não possa mais ser usado ou vendido. Para produtos com uma vida útil limitada, você provavelmente usará uma estratégia de depósito FEFO (primeiro a expirar, primeiro a sair), que prioriza o consumo e a venda de itens com base em sua vida útil restante. Essa estratégia de depósito é relevante para alimentos, remédios e outras mercadorias caracterizadas por um tempo de armazenamento curto. De acordo com o FEFO, os itens no depósito são armazenados como bens em uma prateleira de supermercado: os produtos com uma validade longa são colocados no fundo das prateleiras, de forma que os produtos com uma vida útil mais curta são remetidos primeiro.

## <a name="using-shelf-life-in-master-planning"></a>Uso da validade no planejamento mestre

Esta seção explica como o planejamento mestre sugere o fornecimento para itens de validade.

Quando você executa um planejamento mestre, ele gera ordens planejadas sugeridas (fornecimento) que atenderão à sua demanda e também minimizarão os atrasos. Se o plano incluir itens com validade limitada, os cálculos de planejamento serão mais complexos, pois o plano não só deve minimizar atrasos, mas também usar o suprimento existente antes de expirar. O plano deve tentar usar o suprimento que esteja mais próximo da data de vencimento antes do suprimento com expiração posterior. Portanto, o planejamento mestre busca atingir as seguintes metas, nesta ordem:

1. Minimizar a soma de atrasos.
1. Maximizar a soma do suprimento FEFO.
1. Minimizar o reabastecimento de estoque.

Em alguns casos, pode haver um conflito entre as duas primeiras metas, e uma opção deve ser feita: deseja atrasar uma remessa ou usar o suprimento que expira mais tarde em vez de fornecer o que expira mais cedo? Para resolver esse conflito durante o planejamento mestre, o sistema prioriza a minimização de atrasos em relação ao uso do suprimento com expiração iminente. Em geral, esse tipo de conflito ocorre quando é possível que haja atrasos e cobertura por período. Portanto, recomendamos que você use um período de cobertura menor do que a validade de um item. É improvável que outros tipos de cobertura (como a requisição) ocorram neste tipo de conflito.

## <a name="set-up-shelf-life"></a>Configurar a validade

### <a name="configure-each-master-plan-to-consider-shelf-life"></a>Configurar cada planejamento mestre para considerar a validade

Por padrão, os planos mestre não consideram a validade. Use o procedimento a seguir para habilitar os cálculos de validade para cada plano mestre que os exija.

1. Acesse **Planejamento mestre \> configuração \> planos \> Planos mestres**.
1. Selecione um plano existente no painel de lista ou crie um.
1. Na Guia Rápida **Geral**, defina a opção **Usar datas de validade** como *Sim*.

### <a name="configure-tracking-dimension-groups-to-track-the-batch-dimension"></a>Configurar grupos de dimensão de rastreamento para rastrear a dimensão de lote

A validade de um item só poderá ser rastreada se o item for rastreado na dimensão de lote. Em outras palavras, a referência do lote e as datas necessárias devem ser registradas no recebimento ou na fabricação, e por todas as transações de estoque do item. Para gerenciar essa opção, configure um ou mais grupos de dimensões de rastreamento para fazer o rastreamento necessário e, em seguida, atribua os itens relevantes a esses grupos, conforme necessário.

Use o procedimento a seguir para configurar um grupo de dimensões de rastreamento para rastrear a dimensão de lote.

1. Acesse **Gerenciamento de informações do produto \> Configuração \> Grupos de dimensões e grades \> Grupos de dimensões de rastreamento**.
1. Siga uma destas etapas:

    - No Painel de Ações, selecione **Novo** para criar um grupo de dimensões de rastreamento. Insira um nome e uma descrição e selecione **Salvar** no Painel de Ações.
    - No painel de lista, selecione o grupo de dimensões de rastreamento existente que você deseja configurar para rastrear a dimensão de lote.

1. Na Guia Rápida **Dimensão de rastreamento**, na linha **Número do lote**, marque as caixas de seleção nas colunas **Ativo** e **Estoque físico**.

### <a name="set-up-shelf-life-for-a-product"></a>Configurar a validade para um produto

Use o procedimento a seguir para configurar a validade para um produto.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Crie ou abra o produto que você desejar configurar.
1. Para usar as configurações de validade, na Guia Rápida **Geral**, defina o campo **Grupo de dimensões de rastreamento** como um grupo de dimensões de rastreamento configurado para rastrear a dimensão de lote. Você só poderá definir esse campo quando estiver criando um produto pela primeira vez. Não é possível alterar o valor de produtos existentes.
1. Na Guia Rápida **Gerenciar estoque**, defina os seguintes campos:

    - **Período de aviso de tempo de prateleira em dias** – especifique o período (em dias) para verificar um lote deste produto a fim de garantir que ele seja adequado para consumo ou revenda. O valor desse campo é adicionado à *data de fabricação* de um lote para determinar sua *data de aviso de tempo de prateleira*. Você pode configurar o sistema para gerar ordens de qualidade quando um lote se aproximar da data de aviso de validade.
    - **Período de tempo de prateleira em dias** – especifique o número de dias antes do vencimento de um lote deste produto. Esse valor é adicionado à *data de fabricação* para determinar a *data de vencimento*. O lote será considerado inutilizável após essa data.
    - **Período de validade em dias** – especifique o período (em dias) após o qual um lote deste produto será considerado ainda comercializável mas não poderá mais manter algumas de suas propriedades originais. Esse valor é adicionado à *data de fabricação* para determinar a *data de validade*. Você pode executar relatórios para identificar o estoque que esteja além da data de validade. 

### <a name="set-a-sellable-days-rule-for-each-customer"></a>Definir uma regra de dias comercializáveis para cada cliente

A funcionalidade *Dias comercializáveis* garante que os produtos de um lote que irão expirar em breve não sejam enviados aos clientes. Além disso, ele garante que, quando produtos forem enviados a um cliente, ainda restará um número adequado de dias comercializáveis após a entrega.

Para usar a funcionalidade de dias comercializáveis, você deverá definir o número de dias comercializáveis que se aplica para cada produto (ou grupo de produtos) de cada cliente. Você deve concluir manualmente esse processo, pois não há uma entidade de dados para ele.

Use o procedimento a seguir para configurar os dias comercializáveis para cada produto para cada cliente.

1. Acesse **Vendas e marketing \> Clientes \> Todos os clientes**.
1. Encontre e selecione o cliente que você deseja configurar.
1. No Painel de Ações, na guia **Vender**, no grupo **Configurar**, selecione **Vender \> Dias comercializáveis**.
1. Na página **Dias comercializáveis para o cliente**, a grade lista as regras de dias comercializáveis existentes para cada produto ou grupo de produtos. Use os botões do Painel de Ações para adicionar ou editar linhas na grade conforme necessário. Um **Filtro** é fornecido para ajudar na localização de linhas existentes.
1. Para cada linha, defina os seguintes campos:

    - **Código do item** – selecione um dos valores a seguir para especificar o escopo dos itens que serão afetados:

        - *Tabela* – a linha se aplica a um item específico.
        - *Grupo* – a linha se aplica a um grupo de itens específico.
        - *Todos* – a linha se aplica a todos os itens.

    - **Relação de itens** – se você tiver definido o campo **Código do item** como *Tabela*, selecione um item específico. Se você tiver definido o campo **Código do item** como *Grupo*, selecione um grupo de itens. Se você tiver definido o campo **Código do item** como *Todos*, esse campo não estará disponível.
    - **Dias comercializáveis** – insira o número mínimo de dias que o cliente deve ter para vender produtos correspondentes antes que o lote expire. O valor de dias comercializáveis se baseia na data de recebimento solicitada (ou na data de recebimento confirmada, se estiver definida) para os produtos correspondentes na ordem de venda.
    - *(Outras dimensões de produto)* – para limitar ainda mais o escopo de uma linha, especifique outros valores de dimensão (como **Tamanho** e **Cor**) conforme necessário. Para controlar quais dimensões serão mostradas na grade, selecione **Exibir dimensões** no Painel de Ações.

### <a name="set-up-all-relevant-products-so-that-they-are-fefo-date-controlled"></a>Configurar todos os produtos relevantes para que eles sejam controlados por data FEFO

Para que os dias comercializáveis funcionem, cada item relevante deve pertencer a um grupo de modelos de item em que a caixa de seleção **Controlado por data FEFO** esteja marcada.

Use o procedimento a seguir para configurar um grupo de modelos de item para que ele dê suporte à funcionalidade de dias comercializáveis.

1. Acesse **Gerenciamento de estoque \> Configuração \> Estoque \> Grupos de modelos de item**.
1. Selecione um grupo existente no painel de lista ou crie um novo ao selecionar **Novo** no Painel de Ações.
1. Na Guia Rápida **Políticas de estoque**, marque a caixa de seleção **Controlado por data FEFO**.
1. Configure outros campos para o grupo conforme necessário.

Use o procedimento a seguir para exibir ou definir o grupo de modelos de item ao qual um produto pertence.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Abra o produto a ser inspecionado ou editado.
1. Na Guia Rápida **Geral**, defina o campo **Grupo de modelos de item** como um grupo no qual a caixa de seleção **Controlado por data FEFO** esteja marcada.

## <a name="example-1-simple-fefo-10-day-period-zero-days-of-lead-time"></a>Exemplo 1: FEFO simples, período de 10 dias, zero dias de prazo de entrega

Este exemplo mostra um exemplo básico de validade, no qual a vinculação entre as ordens de fornecimento e a demanda é feita para atender às seguintes metas do sistema:

- Minimizar a soma de atrasos.
- Maximizar a soma do suprimento FEFO.
- Minimizar o reabastecimento de estoque.

O sistema tem as seguintes configurações de item e plano mestre:

- **Código de cobertura (estratégia de reabastecimento):** período 
- **Período de cobertura:** 10 dias (igual à validade)
- **Validade:** 10 days
- **Dias comercializáveis:** 0 dia
- **Prazo de entrega:** 0 dia
- **Dias negativos:** 0 dia
- **Tipo de ordem planejada (configurações de ordem padrão do item):** ordem de compra

As seguintes ordens de venda do item existem no sistema:

- **SO1:** quantidade (qtd.) = 2, data de entrega solicitada = hoje + 1 dia
- **SO2:** qtd. = 1, data de entrega solicitada = hoje + 4 dias
- **SO3:** qtd. = 1, data de entrega solicitada = hoje + 5 dias

Todas essas ordens de venda criam demanda para o item.

Existe o seguinte suprimento para o item:

- **Estoque disponível:** Qtd. = 1, data de vencimento = hoje + 5 dias
- **Ordem de compra 1 (PO1):** data de recebimento = hoje + 2 dias, qtd. = 1, data de vencimento = hoje + 4 dias

O sistema cria uma lista de suprimentos que podem cobrir essa demanda e classifica a lista por data de vencimento (usando FEFO).

O planejamento mestre cria a vinculação necessária entre o fornecimento e a demanda. Ele também cria qualquer demanda necessária com base na lista de suprimentos (usando FEFO) e considera a data de disponibilidade.

- SO1 pode ser atendida pela quantidade disponível, mas não pode ser atendida por PO1, porque a data de disponibilidade para PO1 é um dia depois do que SO1 requer. Portanto, SO1 gera demanda para uma unidade de bens.
- SO2 podem ser coberta por PO1, pois PO1 chegará no tempo solicitado e a data de vencimento ainda será válida. Portanto, o requisito de SO2 é totalmente coberto por PO1.
- SO3 não está coberta, pois os recursos não estão disponíveis. Portanto, SO3 gera demanda para uma unidade de bens.

Para cobrir todos os requisitos restantes, o sistema deverá criar a seguinte ordem de compra planejada:

- **PPO1:** data de recebimento = hoje, qtd. = 2, data de vencimento = hoje + 10 dias

A tabela a seguir resume o resultado.

| Demanda | Vinculação |
|---|---|
| **SO1:** data de entrega = hoje + 1 dia, qtd. = 2 | <p>**Disponível:** qtd. = 1, data de vencimento = hoje + 5 dias</p><p>**PPO1:** data de recebimento = hoje, qtd. = 1, data de vencimento = hoje + 10 dias</p> |
| **SO2:** data de entrega = hoje + 4 dias, qtd. = 1 | **PO1:** data de recebimento = hoje + 2 dias, 1 qtd., data de vencimento = hoje + 4 dias |
| **SO3:** data de entrega = hoje + 5 dias, qtd. = 1 | **PPO1:** data de recebimento = hoje, qtd. = 2, data de vencimento = hoje + 10 dias |

A ilustração a seguir mostra a linha do tempo para este exemplo.

![Exemplo 1: FEFO simples, período de 10 dias, zero dia de prazo de entrega.](media/fefo-example-1.png "Exemplo 1: FEFO simples, período de 10 dias, zero dias de prazo de entrega")

## <a name="example-2-simple-fefo-requirement-three-days-of-lead-time"></a>Exemplo 2: FEFO simples, requisito, três dias de prazo de entrega

Este exemplo mostra como a tentativa do sistema de minimizar atrasos pode, às vezes, acarretar em uma ordem excedente.

O sistema tem as seguintes configurações de item e plano mestre:

- **Código de cobertura (estratégia de reabastecimento):** requisito
- **Validade:** 10 days
- **Dias comercializáveis:** 0 dia
- **Prazo de entrega:** estabelecido pelos seguintes contratos comerciais de fornecedor:

    - **Contrato comercial 1:** se qtd. = 1, prazo de entrega = 4
    - **Contrato comercial 2:** se qtd. = 2, prazo de entrega = 3

- **Dias negativos:** 0 dia
- **Tipo de ordem planejada (configurações de ordem padrão do item):** ordem de compra

Existe a seguinte ordem de venda no sistema:

- **SO1:** qtd. = 2, data de entrega solicitada = hoje + 3 dias

Essa demanda é coberta pelo suprimento existente e uma ordem de compra confirmada:

- **Estoque disponível:** disponível = hoje, qtd. = 1, data de vencimento = hoje + 2 dias
- **PO1:** data de recebimento = hoje + 3 dias, qtd. = 1, data de vencimento = hoje + 4 dias

SO1 não pode ser atendida pelo estoque disponível porque a data de vencimento do estoque é anterior à data de remessa. PO1 pode cobrir o requisito de SO1 com uma quantidade de apenas 1. Portanto, SO1 gera demanda para uma unidade de bens. Para cobrir esse requisito, o sistema cria uma ordem de compra planejada (PPO1).

O sistema tem dois contratos comerciais (um para qtd. = 1, prazo de entrega = 4 dias e outro para qtd. = 2, prazo de entrega = 3 dias). Portanto, o sistema tenta minimizar os atrasos criando uma ordem de compra planejada (PPO1) que atenda ao segundo contrato comercial. O resultado é uma entrega excedente (qtd. = 2, data de vencimento = hoje + 10 dias).

A tabela a seguir resume o resultado.

| Demanda | Vinculação |
|---|---|
| **SO1:** data de entrega = hoje + 3 dias, qtd. = 2 | <p>**PO1:** data de recebimento = hoje + 3 dias, qtd. = 1, data de vencimento = hoje + 4 dias</p><p>**PPO1:** data de recebimento = hoje + 3 dias, qtd. = 1, data de vencimento = hoje + 10 dias</p> |

A ilustração a seguir mostra a linha do tempo para este exemplo.

![Exemplo 2: FEFO simples, requisito, três dias de prazo de entrega.](media/fefo-example-2.png "Exemplo 2: FEFO simples, requisito, três dias de prazo de entrega")

## <a name="example-3-simple-fefo-requirement-three-days-of-lead-time-five-sellable-days"></a>Exemplo 3: FEFO simples, requisito, três dias de prazo de entrega, cinco dias comercializáveis

Este exemplo mostra como a validade funciona quando dias comercializáveis são adicionados a um item.

O sistema tem as seguintes configurações de item e plano mestre:

- **Código de cobertura (estratégia de reabastecimento):** requisito
- **Validade:** 10 days
- **Dias comercializáveis:** 5 dia
- **Prazo de entrega:** 5 dia
- **Dias negativos:** 0 dia
- **Tipo de ordem planejada (configurações de ordem padrão do item):** ordem de compra

Existem as seguintes ordens de venda no sistema:

- **SO1:** qtd. = 2, data de entrega solicitada = hoje + 2 dias
- **SO2:** qtd. = 1, data de entrega solicitada = hoje + 3 dias
- **SO3:** qtd. = 1, data de entrega solicitada = hoje + 5 dias

Essa demanda pode ser coberta pelo suprimento existente e uma ordem de compra confirmada:

- **Estoque disponível:** disponível = hoje, qtd. = 1, data de vencimento = hoje + 6 dias
- **PO1:** data de recebimento = hoje + 2 dias, qtd. = 3, data de vencimento = hoje + 10 dias

O sistema cria uma lista de candidatos de vinculação, com base na lista de fornecimento (FEFO) e nas datas de disponibilidade. Portanto, SO1 não pode ser atendida pelo estoque disponível, pois esse estoque expira antes do final dos dias comercializáveis que o cliente exige (data de recebimento solicitada + 5 dias). PO1 pode cobrir o requisito de SO1 com duas unidades e o requisito de SO2 com uma unidade. Portanto, apenas SO3 ainda tem uma demanda inconsistente para uma unidade de bens. Para cobrir esse requisito, o sistema cria a seguinte ordem de compra planejada:

- **PP01:** data de recebimento = hoje + 5 dias, qtd. = 1, data de vencimento = hoje + 10 dias

A tabela a seguir resume o resultado.

| Demanda | Vinculação |
|---|---|
| **SO1:** data de entrega = hoje + 2 dias, qtd. = 2 | **PO1:** data de recebimento = hoje + 2 dias, qtd. = 2, data de vencimento = hoje + 10 dias |
| **SO2:** data de entrega = hoje + 3 dias, qtd. = 1 | **PO1:** data de recebimento = hoje + 2 dias, qtd. = 1, data de vencimento = hoje + 10 dias |
| **SO3:** data de entrega = hoje + 5 dias, qtd. = 1 | **PPO1:** data de recebimento = hoje + 5 dias, qtd. = 1, data de vencimento = hoje + 10 dias |

A ilustração a seguir mostra a linha do tempo para este exemplo.

![Exemplo 3: FEFO simples, requisito, três dias de prazo de entrega, cinco dias comercializáveis.](media/fefo-example-3.png "Exemplo 3: FEFO simples, requisito, três dias de prazo de entrega, cinco dias comercializáveis")

## <a name="example-4-simple-fefo-period-lead-time-depends-on-the-quantity"></a>Exemplo 4: FEFO simples, período, prazo de entrega depende da quantidade

Este exemplo mostra como a tentativa do sistema de minimizar atrasos pode, às vezes, acarretar em uma ordem excedente.

O sistema tem as seguintes configurações de item e plano mestre:

- **Código de cobertura (estratégia de reabastecimento):** período
- **Período de cobertura:** 10 dias (igual à validade)
- **Validade:** 10 days
- **Dias comercializáveis:** 0 dia
- **Prazo de entrega:** estabelecido pelos seguintes contratos comerciais de fornecedor:

    - **Contrato comercial 1:** se qtd. = 1, prazo de entrega = 5
    - **Contrato comercial 2:** se qtd. = 2, prazo de entrega = 0

- **Dias negativos:** 0 dia
- **Tipo de ordem planejada (configurações de ordem padrão do item):** ordem de compra

Existem as seguintes ordens de venda no sistema:

- **SO1:** qtd. = 1, data de entrega solicitada = hoje
- **SO2:** qtd. = 1, data de entrega solicitada = hoje + 6 dias

Essa demanda pode ser parcialmente coberta pelo suprimento existente das seguintes ordens de compra confirmadas:

- **PO1:** data de recebimento = hoje + 1 dias, qtd. = 1, data de vencimento = hoje + 2 dias
- **PO2:** data de recebimento = hoje + 3 dias, qtd. = 1, data de vencimento = hoje + 7 dias

O sistema tem dois contratos comerciais (um para qtd. = 1, prazo de entrega = 5 dias e outro para qtd. = 2, prazo de entrega = 0 dia). Portanto, o sistema tenta minimizar o atraso criando a ordem de compra planejada a seguir que atenda ao segundo contrato comercial.

- **PP01:** data de recebimento = hoje, qtd. = 2, data de vencimento = hoje + 10 dias

SO1 será coberta por uma unidade de PPO1. SO2 será coberta por PO2 porque PO2 expirará antes de PPO1.

A tabela a seguir resume o resultado.

| Demanda | Vinculação |
|---|---|
| **SO1:** data de entrega = hoje, qtd. = 1 | **PPO1:** data de recebimento = hoje, qtd. = 1, data de vencimento = hoje + 10 dias |
| **SO2:** data de entrega = hoje + 6 dias, qtd. = 1 | **PO2:** data de recebimento = hoje + 3 dias, qtd. = 1, data de vencimento = hoje + 7 dias |

> [!NOTE]
> PO1 não será usada, pois chegará muito atrasada para S01 e expirará antes que S02 seja entregue. PPO1 foi expedida por uma unidade para permitir que o prazo de entrega seja 0 (zero), por contrato comercial 2.

A ilustração a seguir mostra a linha do tempo para este exemplo.

![Exemplo 4: FEFO simples, período, prazo de entrega depende da quantidade.](media/fefo-example-4.png "Exemplo 4: FEFO simples, período, prazo de entrega depende da quantidade")

## <a name="example-5-simple-fefo-requirement-10-negative-days"></a>Exemplo 5: FEFO simples, requisito, 10 dias negativos

<!-- KFM: This is more of a negative days example than a shelf life example. We should point out more explicitly how shelf life affects this situation (or maybe otherwise remove this example). -->

Este exemplo mostra como a validade funciona quando um grande número de dias negativos é adicionado a um item. Os dias negativos são o número de dias que você está disposto a esperar antes de solicitar um reabastecimento de um item com estoque negativo. O sistema não cria o suprimento a menos que o número de dias negativos seja excedido.

O sistema tem as seguintes configurações de item e plano mestre:

- **Código de cobertura (estratégia de reabastecimento):** requisito
- **Prazo de entrega:** 0 dia
- **Dias negativos:** 10 dia
- **Tipo de ordem planejada (configurações de ordem padrão do item):** ordem de compra

Existe a seguinte ordem de venda no sistema:

- **SO1:** qtd. = 1, data de entrega solicitada = hoje

Essa demanda pode ser parcialmente coberta pelo suprimento existente da seguinte ordem de compra confirmada:

- **PO1:** data de recebimento = hoje + 3 dias, qtd. = 1, data de vencimento = hoje + 5 dias

Como o sistema está configurado para permitir 10 dias negativos, ele cobre a demanda de SO1 usando PO1, mesmo que o resultado seja um atraso de três dias porque SO1 cria um estoque negativo até PO1 chegar. Nenhuma ordem de compra planejada é criada, mesmo que o prazo de entrega seja 0 (zero) e a criação de uma ordem de compra planejada reduza os atrasos.

A tabela a seguir resume o resultado.

| Demanda | Vinculação |
|---|---|
| **SO1:** data de entrega = hoje, qtd. = 1 | **PO1:** data de recebimento = hoje + 3 dias, qtd. = 1, data de vencimento = hoje + 5 dias |

A ilustração a seguir mostra a linha do tempo para este exemplo.

![Exemplo 5: FEFO simples, requisito, 10 dias negativos.](media/fefo-example-5.png "Exemplo 5: FEFO simples, requisito, 10 dias negativos")

## <a name="example-6-simple-fefo-requirement-five-negative-days"></a>Exemplo 6: FEFO simples, requisito, cinco dias negativos

Este exemplo mostra como a validade funciona quando o número de dias negativos para um item é inferior ao seu período de validade.

O sistema tem as seguintes configurações de item e plano mestre:

- **Código de cobertura (estratégia de reabastecimento):** requisito
- **Dias comercializáveis:** 0 dia
- **Prazo de entrega:** 0 dia
- **Dias negativos:** 5 dia
- **Tipo de ordem planejada (configurações de ordem padrão do item):** ordem de compra

Existe a seguinte ordem de venda no sistema:

- **SO1:** qtd. = 2, data de entrega solicitada = hoje

Essa demanda pode ser parcialmente coberta pelo suprimento existente das ordens de compra confirmadas:

- **PO1:** data de recebimento = hoje, qtd. = 1, data de vencimento = hoje + 1 dia
- **PO2:** data de recebimento = hoje + 2 dias, qtd. = 1, data de vencimento = hoje + 3 dias

No entanto, o sistema deve respeitar a restrição de que os itens enviados não podem estar expirados no momento da remessa. Portanto, PO2 e PO1 não podem ser usadas para SO1, porque PO1 expira antes da chegada de PO2. O sistema cria a ordem de compra planejada a seguir para finalizar a cobertura da demanda para SO1:

- **PPO1:** data de recebimento = hoje, qtd. = 1, data de vencimento = hoje + 10 dias

O sistema pode aproveitar os cinco dias negativos e usar PO2 e PPO1 para cobrir SO1. No entanto, essa abordagem causará o atraso da entrega até que PO2 chegue, e PO1 expirará enquanto isso. Portanto, o sistema cobre SO1 usando PPO1 e PO1.

A tabela a seguir resume o resultado.

| Demanda | Vinculação |
|---|---|
| **SO1:** data de entrega = hoje, qtd. = 2 | <p>**PO1:** data de recebimento = hoje, qtd. = 1, data de vencimento = hoje + 1 dia</p><p>**PPO1:** data de recebimento = hoje, qtd. = 1, data de vencimento = hoje + 10 dias</p> |

A ilustração a seguir mostra a linha do tempo para este exemplo.

![Exemplo 6: FEFO simples, requisito, cinco dias negativos.](media/fefo-example-6.png "Exemplo 6: FEFO simples, requisito, cinco dias negativos")
