---
title: Planejamento mestre com previsões de fornecimento
description: Este artigo descreve como as previsões de fornecimento são consideradas durante o planejamento mestre.
author: t-benebo
ms.date: 09/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-21
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2bac9355bb1ac00f697ec459f494a64553e0eacc
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740132"
---
# <a name="master-planning-with-supply-forecasts"></a>Planejamento mestre com previsões de fornecimento

[!include [banner](../../includes/banner.md)]

As previsões de fornecimento permitem especificar o fornecimento que você espera ser necessário em um período futuro. Normalmente, você baseará a estimativa no histórico de vendas do ano anterior e usará a previsão para fins de orçamento. Também é possível configurar os planos mestre para considerar as previsões durante o planejamento.

## <a name="set-up-a-master-plan-to-consider-supply-forecasts"></a>Configurar um plano mestre para considerar previsões de fornecimento

Você pode especificar se cada plano mestre deve considerar previsões ao ser executado. Use o procedimento a seguir para definir as opções de previsão para cada plano.

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione um plano mestre existente no painel de lista, ou selecione **Novo** no Painel de Ações para criar um.
1. Na Guia Rápida **Geral**, defina os seguintes campos:

    - **Modelo de previsão** – selecione o modelo que contém as previsões de fornecimento e/ou demanda que devem ser consideradas pelo plano mestre.
    - **Incluir previsão de fornecimento** – defina esta opção como *Sim* se o plano mestre precisar considerar previsões de fornecimento.
    - **Incluir previsão de demanda** – defina esta opção como *Sim* se o plano mestre precisar considerar previsões de demanda. Embora essa configuração seja independente da configuração **Incluir previsão de fornecimento**, algumas das outras configurações na página se aplicam a previsões de fornecimento e a previsões de demanda. Para obter mais informações sobre o planejamento que considere previsões de demanda, consulte [Planejamento mestre com previsões de demanda](demand-forecast.md).
    - **Método usado para reduzir requisitos de previsão** – selecione o método a ser usado para reduzir requisitos de previsão durante o planejamento mestre:

        - *Nenhum* – os requisitos de previsão não serão reduzidos durante o planejamento mestre.
        - *Percentual - chave de redução* – os requisitos de previsão serão reduzidos de acordo com as porcentagens e os períodos de tempo definidos na chave de redução.
        - *Transações – chave de redução* – os requisitos de previsão serão reduzidos pelas transações que ocorrem durante os períodos de tempo definidos na chave de redução.
        - *Transações – período dinâmico* – os requisitos de previsão serão reduzidos pelas transações de ordem ocorridas durante o período dinâmico. O período dinâmico cobre as datas de previsão atuais, e termina quando a próxima previsão começa. O método *Transações – período dinâmico* não usa ou exige uma chave de redução e, ao usá-la, as seguintes condições se aplicam:

            - Se a previsão for completamente reduzida, os requisitos da previsão atual se tornam 0 (zero).
            - Se não houver previsão futura, os requisitos de previsão da última previsão que foi inserida serão reduzidos.
            - Os limites de tempo são incluídos no cálculo de redução de previsão.
            - Os dias positivos são incluídos no cálculo de redução de previsão.
            - Se as transações de ordens reais excederam os requisitos de previsão, as outras transações não serão encaminhadas para o próximo período de previsão.

        > [!NOTE]
        > A configuração de **Método usado para reduzir requisitos de previsão** também se aplicará a previsões de demanda se você habilitá-las para o plano mestre e isso afetá-los de forma semelhante. Para obter mais informações, consulte [Planejamento mestre com previsões de demanda​](demand-forecast.md).

## <a name="set-reduction-options-for-coverage-groups"></a>Definir opções de redução para grupos de cobertura

Para definir opções que controlam como um grupo de cobertura reduzirá os requisitos de previsão para planos mestres que usam redução baseada na transação, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Grupos de cobertura**.
1. Selecione um grupo de cobertura existente no painel de lista ou selecione **Novo** no Painel de Ações para criar um novo.
1. Na FastTab **Outro**, no campo **Reduzir previsão por** especifique como requisitos de previsão de fornecimento devem ser reduzidos para itens no grupo de cobertura, para planos mestre em que o campo **Método usado para reduzir requisitos de previsão** está definido como *Transações - chave de redução* ou *Transações - período dinâmico*. Selecione um dos seguintes valores:

    - *Todas as transações* – todas as transações devem reduzir a previsão.
    - *Ordens* – somente ordens do mesmo tipo devem reduzir a previsão.

    Por exemplo, as configurações de ordem padrão para um item indicam que ele deve ser produzido. Há uma linha de previsão de fornecimento para uma quantidade de 50 e há uma ordem de compra existente para uma quantidade de 20. Se o campo **Reduzir previsão por** estiver definido como *Ordens*, uma ordem de produção planejada será criada para uma quantidade de 50. Se ele estiver definido como *Todas as transações*, a ordem de produção planejada será reduzida para uma quantidade de 30.

    Essa configuração também se aplica à redução de previsão de demanda. Para obter mais informações, consulte [Planejamento mestre com previsões de demanda​](demand-forecast.md).

## <a name="enter-a-supply-forecast-for-a-product"></a>Inserir uma previsão de fornecimento para um produto

Para inserir uma previsão de fornecimento para um produto, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione o produto ao qual deseja inserir uma previsão.
1. No Painel de Ações, na guia **Plano**, selecione **Previsão de fornecimento**.
1. Na página **Previsão de fornecimento**, no Painel de Ações, selecione **Novo** para adicionar uma previsão à grade.
1. Insira informações na nova linha, conforme necessário, para especificar sua previsão.

## <a name="plan-for-an-item-with-supply-forecast-lines"></a>Plano para um item com linhas de previsão de fornecimento

Quando você executar um plano mestre que inclui um item para o qual existir uma previsão de fornecimento, o sistema criará uma ordem de compra para as linhas de fornecimento que foram inseridas. As configurações de ordem padrão para o item são respeitadas. Se essas configurações de ordem padrão de especificarem um valor **Tipo de ordem padrão** de *Ordem de compra* e nenhuma conta de fornecedor for especificada na linha de previsão de fornecimento, o sistema usará o fornecedor padrão para o item.

## <a name="check-whether-a-planned-order-is-a-supply-forecast-order"></a>Verificar se uma ordem planejada é uma ordem de previsão de fornecimento

Use o procedimento a seguir para saber se uma ordem planejada foi criada como resultado de uma previsão de fornecimento.

1. Acesse **Planejamento mestre \> Planejamento mestre \> Ordens planejadas**.
1. Abra a ordem planejada a ser inspecionada.
1. Na FastTab **Geral**, procure o valor do campo **Previsão de fornecimento**. Se a ordem tiver sido criada para cobrir uma previsão de fornecimento, este campo será definido como *Sim*.

## <a name="examples-of-master-planning-with-supply-forecasts"></a>Exemplos de planejamento mestre com previsões de fornecimento

Esta seção fornece vários exemplos que mostram como a previsão de fornecimento afeta o planejamento mestre.

### <a name="example-1-supply-forecast-for-an-item"></a>Exemplo 1: Previsão de fornecimento de um item

Você tem um item em que o tipo de ordem padrão é *Ordem de compra* e o fornecedor padrão é *US-002*. Ele tem a linha de previsão de fornecimento a seguir.

| Modelo    | Data     | Conta de fornecedor | Grupo de Fornecedores | Quantidade | Unidade | Site | Depósito |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | cada   | 1    | 11        |

Quando você executar o planejamento mestre, uma ordem de compra planejada será criada para *35 ea* do fornecedor *US-002*.

### <a name="example-2-several-supply-forecast-lines-with-and-without-a-vendor"></a>Exemplo 2: várias linhas de previsão de fornecimento, com e sem um fornecedor

Você tem um item em que o tipo de ordem padrão é *Ordem de compra* e o fornecedor padrão é *US-002*. Ele tem as linhas de previsão de fornecimento a seguir.

| Modelo    | Data     | Conta de fornecedor | Grupo de Fornecedores | Quantidade | Unidade | Site | Depósito |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                |              | 35       | cada   | 1    | 11        |
| CurrentF | 10/10/22 | US-101         |              | 25       | cada   | 1    | 11        |

Nesse caso, o sistema trata a linha que não especifica um fornecedor como uma previsão genérica e supõe que a linha que especifica um fornecedor deve ser subtraída da previsão genérica. Dessa forma, o planejamento mestre criará as seguintes ordens de compra planejadas para o item:

- Uma ordem de compra planejada para uma quantidade de *25 ea* do fornecedor *US-101* (o fornecedor e a quantidade que estão especificados na linha de previsão são usados).
- Uma ordem de compra planejada para uma quantidade de *10 ea* do fornecedor *US-002* (como nenhum fornecedor foi especificado na outra linha de previsão, o fornecedor padrão é usado e a quantidade dessa linha de previsão é reduzida pela quantidade da linha de previsão específica do fornecedor.)

### <a name="example-3-plans-that-use-the-transactions---dynamic-period-reduction-method-in-a-single-forecast-period"></a>Exemplo 3: planos que usam o método Transações - redução de período dinâmico em um único período de previsão

Para planos mestres que usam *Transações - período dinâmico* como o método de redução de previsão, o planejamento mestre reduzirá as quantidades de previsão se houver transações existentes que correspondam a essas características de fornecimento.

Por exemplo, você tem um item em que o tipo de ordem padrão é *Ordem de compra*. Ele tem a linha de previsão de fornecimento a seguir.

| Modelo    | Data     | Conta de fornecedor | Grupo de Fornecedores | Quantidade | Unidade | Site | Depósito |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | cada   | 1    | 11        |

Como há apenas uma linha de previsão de fornecimento, só há um período de previsão.

Quando você executa um plano mestre configurado para usar *Transações – período dinâmico* como o método de redução, um dos seguintes resultados pode ocorrer:

- Se houver uma ordem de compra para o fornecedor *US-101* e uma quantidade de *10 ea*, e o campo **Previsão de fornecimento** estiver definido como *Sim*, o planejamento mestre criará uma nova ordem de compra planejada para a quantidade pendente de *10 ea*. A linha de previsão é reduzida, pois o fornecedor corresponde à ordem de compra existente.
- Se houver uma ordem de compra para o fornecedor *US-102*, site *1*, depósito *11*, e uma quantidade de *10 ea*, e o campo **Previsão de fornecimento** estiver definido como *Sim*, o planejamento mestre criará uma nova ordem de compra planejada para a quantidade total de *25 ea*. A linha de previsão não pode ser reduzida, pois tem um fornecedor diferente do que a ordem de compra existente.

> [!NOTE]
> Essa situação pode ocorrer para ordens de compra planejadas, pois um fornecedor está associado a elas. No entanto, para ordens de transferência e ordens de produção, os valores de previsão de fornecimento sempre serão reduzidos por ordens existentes, porque nenhum fornecedor é especificado para esses tipos de ordens.

### <a name="example-4-plans-that-use-the-transactions---dynamic-period-reduction-method-over-several-forecast-periods"></a>Exemplo 4: planos que usam o método Transações - redução de período dinâmico em vários períodos de previsão

Você tem um item em que o tipo de ordem padrão é *Ordem de compra*. Ele tem as linhas de previsão de fornecimento a seguir.

| Modelo    | Data     | Conta de fornecedor | Grupo de Fornecedores | Quantidade | Unidade | Site | Depósito |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | cada   | 1    | 11        |
| CurrentF | 10/15/22 | US-101         |              | 25       | cada   | 1    | 11        |

Neste exemplo, há duas linhas de previsão, cada uma com uma data diferente. Portanto, as datas estabelecem os limites dos períodos de previsão. O primeiro período é de 10 a 14 de outubro de 2022 (10/10/22 – 10/14/22). A segunda é de 15 de outubro de 2022 (10/15/22) em diante.

Há uma ordem de compra existente para o fornecedor *US-101*, uma quantidade de *10 ea* e a data *10/12/22* (12 de outubro de 2022). Quando você executar um plano mestre configurado para usar *Transações – período dinâmico* como o método de redução, ele criará as seguintes ordens:

- Uma ordem planejada para uma quantidade de *15 ea* e a data *10/10/22* (a quantidade é reduzida pela ordem de compra existente que é datada durante o mesmo período de previsão).
- Uma ordem planejada para uma quantidade de *25 ea* e a data *10/15/22* (a quantidade é a quantidade total da previsão).

### <a name="example-5-plans-that-use-no-reduction"></a>Exemplo 5: planos que não usam redução

Quando você executar um plano no qual o método de redução de previsão é *Nenhum*, o planejamento mestre sempre criará o fornecimento planejado para todas as linhas de previsão de fornecimento. Após a aprovação do suprimento planejado, ele reduzirá ordens planejadas futuras. Mas, as ordens de compra não reduzirão as linhas de previsão de fornecimento.

Por exemplo, você tem um item em que o tipo de ordem padrão é *Ordem de compra*. Ele tem a linha de previsão de fornecimento a seguir.

| Modelo    | Data     | Conta de fornecedor | Grupo de Fornecedores | Quantidade | Unidade | Site | Depósito |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 | US-101         |              | 25       | cada   | 1    | 11        |

Há uma ordem de compra existente para o fornecedor *US-101*, site *1*, depósito *11*, uma quantidade de *25 ea* e a data *10/10/22*. 

Quando você executar um plano mestre configurado para usar *Nenhum* como o método de redução, ele criará uma ordem de compra planejada para o fornecedor *US-101*, site *1*, depósito *11*, uma quantidade de *25 ea* e a data *10/10/22*. Ou seja, a ordem de compra existente não será reduzida, pois o método de redução de previsão é *Nenhum*.

Agora, você edita a ordem de compra planejada que foi criada após o último planejamento executado, e altera a quantidade para *15 ea*. Depois, você aprova a ordem. Da próxima vez que você executar o plano mestre, ele criará uma ordem de compra planejada para o fornecedor *US-101*, site *1*, depósito *11*, uma quantidade de *10* ea e a data *10/10/22*. Desta vez, a quantidade será reduzida para refletir a quantidade da ordem aprovada existente do planejamento anterior executado.

## <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>Diferenças entre Otimização de Planejamento e mecanismo de planejamento mestre preterido

As previsões de fornecimento operam de forma um pouco distinta, dependendo do mecanismo de planejamento utilizado (otimização de planejamento ou o mecanismo de planejamento mestre preterido). Esta seção descreve as diferenças.

### <a name="vendor-groups"></a>Grupos de fornecedores

Ao adicionar uma linha prevista, você pode especificar um fornecedor e um grupo de fornecedores. No mecanismo de planejamento mestre preterido, as ordens planejadas criadas são agrupadas pela combinação dos valores do fornecedor e do grupo de fornecedores. Na Otimização de Planejamento, as ordens planejadas são agrupadas por fornecedor.

A tabela a seguir fornece alguns exemplos de linhas de previsão de fornecimento para um item.

| Modelo    | Data     | Conta de fornecedor | Grupo de Fornecedores | Quantidade | Unidade | Site | Depósito |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10/10/22 |                | VendorGroupA | 5        | ea   | 1    | 11        |
| CurrentF | 10/10/22 |                | VendorGroupA | 6        | ea   | 1    | 11        |
| CurrentF | 10/10/22 |                |              | 7        | ea   | 1    | 11        |

O fornecedor *VendorA* é o fornecedor padrão do grupo de fornecedores *VendorGroupA*. Ele também é o fornecedor padrão do item.

O mecanismo de planejamento mestre preterido criará as seguintes ordens:

- Uma ordem de compra planejada para o fornecedor *VendorA*, grupo de fornecedores *VendorGroupA* e uma quantidade de *11*
- Uma ordem de compra planejada para o fornecedor *VendorA* e uma quantidade de *7*

A Otimização de Planejamento criará apenas uma ordem:

- Uma ordem de compra planejada para o fornecedor *VendorA*, grupo de fornecedores *VendorGroupA* e uma quantidade de *18*

### <a name="reduction-of-general-forecasts-by-more-specific-forecasts"></a>Redução de previsões gerais por previsões mais específicas

No mecanismo de planejamento mestre preterido, o resultado será imprevisível se algumas previsões tiverem um fornecedor, mas outras não.

Na Otimização de Planejamento, as previsões gerais são sempre reduzidas por previsões mais específicas, como mostra o exemplo a seguir.

A tabela a seguir fornece alguns exemplos de linhas de previsão de fornecimento para um item.

| Data       | Quantidade | Fornecedor   | Grupo de Fornecedores  |
|------------|----------|----------|---------------|
| 02/11/2022 | 5,00     | Vendor-A | VendorGroup-A |
| 02/11/2022 | 6,00     | Vendor-A | VendorGroup-A |
| 02/11/2022 | 15,00    |          |               |

A previsão geral (para 15,0 peças) é reduzida pelas previsões mais específicas (para 5,0 + 6,0 = 11,0 peças). O restante é atribuído ao fornecedor padrão. A tabela a seguir mostra as ordens planejadas.

| Data       | Quantidade | Fornecedor   | Grupo de Fornecedores  |
|------------|----------|----------|---------------|
| 02/11/2022 | 11,00    | Vendor-A | VendorGroup-A |
| 02/11/2022 | 4,00     | Vendor-A | VendorGroup-A |

### <a name="respect-for-default-order-settings-when-planned-orders-are-generated"></a>Respeitar as configurações de ordem padrão quando as ordens planejadas são geradas

Cada item pode ter configurações de ordem padrão, como uma quantidade de ordem de compra mínima. O mecanismo de planejamento mestre preterido ignora essas configurações e, portanto, converte as previsões em ordens planejadas que têm a mesma quantidade. A otimização do planejamento respeita essas configurações quando as ordens planejadas são geradas a partir de previsões de fornecimento. 

### <a name="aggregation-of-planned-orders-as-a-result-of-reduction-by-approved-orders"></a>Agregação de ordens planejadas como resultado da redução por ordens aprovadas

O mecanismo de planejamento mestre preterido supõe que apenas uma ordem reduzirá a previsão de fornecimento existente. Portanto, se várias ordens corresponderem a uma linha de previsão de fornecimento, apenas a primeira ordem será reduzida. Na Otimização de Planejamento, todas as ordens que correspondem à linha de previsão de fornecimento a reduzirão.

### <a name="reduction-of-forecasts-by-matching-vendors-only"></a>Redução de previsões somente por fornecedores correspondentes

Quando o mecanismo de planejamento mestre preterido reduz uma previsão por ordens de compra lançadas existentes, isso não garante que o fornecedor na ordem de compra corresponda ao fornecedor da previsão. A Otimização do Planejamento reduz as previsões somente por ordens de compra com um valor correspondente no campo de fornecedor.

Para ordens de transferência e de produção, o campo de fornecedor é sempre ignorado, pois ele não é relevante para esses tipos de ordem.

### <a name="reduction-of-forecasts-by-transfer-orders"></a>Redução de previsões por ordens de transferência

Se o tipo de ordem padrão de um item for *Transferência*, as previsões só poderão ser reduzidas pelas ordens de transferência planejadas existentes. Mas, para ordens de produção e ordens de compra, somente ordens liberadas reduzem a previsão de fornecimento.

O mecanismo de planejamento mestre preterido reduz todos os estados de ordem de transferência, enquanto a Otimização de Planejamento reduz previsões somente por ordens de transferência no estado *Liberado*.
