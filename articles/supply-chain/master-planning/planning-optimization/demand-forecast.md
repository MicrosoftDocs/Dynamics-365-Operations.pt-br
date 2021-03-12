---
title: Planejamento mestre com previsões de demanda
description: Este tópico explica como incluir previsões de demanda durante planejamento mestre com Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: cb696c365e02ab3e3b28da19b8b33f1975c142f8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983535"
---
# <a name="master-planning-with-demand-forecasts"></a>Planejamento mestre com previsões de demanda

[!include [banner](../../includes/banner.md)]

Você pode usar uma previsão de demanda junto com a Otimização de Planejamento para contabilizar a demanda esperada no planejamento mestre. Você pode criar manualmente uma previsão de demanda, importá-la ou gerá-la usando a funcionalidade de previsão de demanda no Microsoft Dynamics 365 Supply Chain Management. Para obter mais informações sobre a previsão de demanda, consulte [Visão geral de previsão de demanda](../introduction-demand-forecasting.md).

> [!NOTE]
> Não há suporte para planejamento de previsão separado com a Otimização de Planejamento. Portanto, a configuração **Plano de previsão atual** na página **Parâmetros de planejamento mestre** não tem efeito ao usar a Otimização de Planejamento.

## <a name="set-up-a-master-plan-to-include-a-demand-forecast"></a>Configurar um plano mestre para incluir uma previsão de demanda

Para configurar um plano mestre de forma que inclua uma previsão de demanda, siga estas etapas.

1. Vá para **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione um plano existente ou crie um novo plano.
1. Na Guia Rápida **Geral**, defina os seguintes campos:

    - **Modelo de previsão** – selecione o modelo de previsão a ser aplicado. Esse modelo será considerado quando uma sugestão de fornecimento for gerada para o plano mestre atual.
    - **Incluir previsão de demanda** – defina esta opção como *Sim* para incluir a previsão de demanda no plano mestre atual. Se você defini-la como *Não*, as transações de previsão de demanda não serão incluídas no plano mestre.
    - **Método usado para reduzir requisitos de previsão** – selecione o método que deve ser usado para reduzir requisitos de previsão. Para obter mais informações, consulte a seção [Chaves de redução da previsão](#reduction-keys) mais adiante neste tópico.

1. Na FastTab **Limite de tempo em dias**, você pode definir os seguintes campos para especificar o período de inclusão da previsão de demanda durante:

    - **Plano de previsão** – defina esta opção como *Sim* para substituir o limite de tempo do plano de previsão originado dos grupos de cobertura individuais. Defina como *Não* para usar os valores dos grupos de cobertura individuais para o plano mestre atual.
    - **Período de tempo de previsão** – se você definir a opção **Plano de previsão** como *Sim*, especifique o número de dias (a partir da data de hoje) em que a previsão de demanda deve ser aplicada.

    > [!IMPORTANT]
    > A configuração de **Plano de previsão** ainda não tem suporte com a Otimização de Planejamento.

## <a name="set-up-a-coverage-group-to-include-a-demand-forecast"></a>Configurar um grupo de cobertura para incluir uma previsão de demanda

Para configurar um grupo de cobertura para que inclua uma previsão de demanda, siga estas etapas.

1. Vá para **Planejamento mestre \> Configuração \> Planos \> Grupos de cobertura**.
1. Selecione um grupo de cobertura existente ou crie um novo grupo.
1. Na FastTab **Outro**, defina os seguintes campos:

    - **Limite de tempo do plano de previsão** – insira o número de dias (a partir da data de hoje) para o qual a previsão de demanda deve ser aplicada. Esse valor pode ser substituído usando a opção **Plano de previsão** no plano mestre, conforme descrito na seção anterior.
    - **Chave de redução** – selecione a chave de redução a ser aplicada. Para obter mais informações, consulte as seções [Criar e configurar uma chave de redução de previsão](#create-reduction-key) e [Usar uma chave de redução](#use-reduction-key) mais adiante neste tópico.
    - **Reduzir previsão por** – para planos mestre em que o campo **Método usado para reduzir requisitos de previsão** está definido como *Transações - chave de redução* ou *Transações - período dinâmico*, especifique quais transações devem reduzir a previsão. Selecione um dos seguintes valores:

        - **Todas as transações** – todas as transações devem reduzir a previsão.
        - **Ordens** – somente ordens de venda devem reduzir a previsão.

        > [!NOTE]
        > Se você selecionar *Todas as transações*, as transações com demanda e fornecimento nas mesmas dimensões de estoque serão consideradas neutras e serão ignoradas durante a redução da previsão. Por exemplo, se a dimensão de planejamento for definida como somente site, não depósito, uma ordem de transferência entre o site 1, o depósito 11 e o site 1, depósito 13, será ignorada e não reduzirá a previsão de demanda pendente.

    - **Incluir ordens intercompanhia** – defina esta opção como *Sim* se precisar incluir ordens intercompanhia quando a previsão for reduzida. Caso contrário, defina-a como *Não*.
    - **Incluir previsão de cliente na previsão de demanda** – especifique se uma previsão de cliente deve ser incluída na previsão geral. Essa opção determina como a demanda real reduz a demanda prevista. Você pode usá-la para garantir que o planejamento mestre cubra o fornecimento de itens comprados por clientes específicos.

        - Defina esta opção como *Sim* para incluir uma previsão de cliente na previsão geral. Nesse caso, a demanda do cliente real reduz a previsão do cliente e a previsão geral. O planejamento mestre gera ordens planejadas para cobrir somente a quantidade de previsão geral.
        - Defina esta opção como *Não* se não desejar incluir uma previsão de cliente na previsão geral. Nesse caso, a demanda do cliente real reduz somente a previsão do cliente. O planejamento mestre gera ordens planejadas para cobrir a quantidade de previsão geral e a previsão para a quantidade de cada cliente.

## <a name="forecast-reduction-keys"></a><a name="reduction-keys"></a>Chaves de redução da previsão

Esta seção fornece informações sobre os diferentes métodos usados para reduzir requisitos de previsão. Ele inclui exemplos dos resultados de cada método. Também explica como criar, configurar e usar uma chave de redução da previsão. Alguns métodos usam uma chave de redução da previsão para diminuir os requisitos de previsão.

### <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>Métodos usados para reduzir os requisitos de previsão

Quando você inclui uma previsão sobre um plano mestre, pode selecionar como os requisitos de previsão são reduzidos quando a demanda real é incluída. Observe que o planejamento mestre exclui os requisitos de previsão do passado, o que significa todos os requisitos de previsão antes da data atual.

Para incluir uma previsão em um plano mestre e selecionar o método usado para reduzir os requisitos de previsão, vá para **Planejamento mestre \> Configuração \> Planos \> Planos mestres**. No campo **Modelo de previsão**, selecione um modelo de previsão. No campo **Método usado para reduzir requisitos de previsão**, selecione um método. As opções a seguir estão disponíveis:

- Nenhuma
- Percentual – chave de redução
- Transações – chave de redução (ainda não há suporte com Otimização de Planejamento)
- Transações – período dinâmico

As próximas seções fornecem mais informações sobre cada opção.

#### <a name="none"></a>Nenhuma

Se você seleciona **Nenhum**, os requisitos de previsão não são reduzidos durante o agendamento do planejamento mestre. Nesse caso, o planejamento mestre cria ordens planejadas para suprir a demanda prevista (requisitos de previsão). Essas ordens planejadas mantêm a quantidade sugerida, independentemente de outros tipos de demanda. Por exemplo, se são feitas ordens de venda, o planejamento mestre cria ordens planejadas adicionais para suprir as ordens de venda. A quantidade dos requisitos de previsão não é reduzida.

#### <a name="percent--reduction-key"></a>Percentual – chave de redução

Se você seleciona **Percentual - chave de redução**, os requisitos de previsão são reduzidos de acordo com as porcentagens e os períodos definidos pela chave de redução. Nesse caso, o planejamento mestre cria ordens planejadas nos casos em que a quantidade é calculada como quantidade prevista × chave de redução em cada período. Se há outros tipos demanda, o planejamento mestre também cria ordens planejadas para suprir essa demanda.

##### <a name="example-percent--reduction-key"></a>Exemplo: Percentual – chave de redução

Este exemplo mostra como uma chave de redução reduz requisitos de previsão de demanda de acordo com as porcentagens e os períodos que são definidos pela chave de redução.

Neste exemplo, você inclui a previsão de demanda a seguir em um plano mestre.

| Mês    | Previsão de demanda |
|----------|-----------------|
| Janeiro  | 1.000           |
| Fevereiro | 1.000           |
| Março    | 1.000           |
| Abril    | 1.000           |

Na página **Chaves de redução**, você configura as seguintes linhas.

| Troco | Unidade  | Porcentagem |
|--------|-------|---------|
| 1      | Mês | 100     |
| 2      | Mês | 75      |
| 3      | Mês | 50      |
| 4      | Mês | 25      |

Você atribui a chave de redução ao grupo de cobertura do item. Em seguida, na página **Planos mestres**, no campo **Método usado para reduzir requisitos de previsão**, selecione **Percentual - chave de redução**.

Nesse caso, se você executar o plano de previsão em 1º de janeiro, os requisitos de previsão de demanda serão consumidos de acordo com as porcentagens configuradas na página **Chaves de redução**. As quantidades da requisição a seguir são transferidas para o plano mestre.

| Mês                | Quantidade de ordens planejadas | Cálculo    |
|----------------------|------------------------|----------------|
| Janeiro              | 0                      | = 0% × 1.000   |
| Fevereiro             | 250                    | = 25% × 1.000  |
| Março                | 500                    | = 50% × 1.000  |
| Abril                | 750                    | = 75% × 1.000  |
| Maio até dezembro | 1.000                  | = 100% × 1.000 |

#### <a name="transactions--reduction-key"></a>Transações – chave de redução

Se você seleciona **Transações - chave de redução**, os requisitos de previsão são reduzidos pelas transações que ocorrem durante os períodos definidos pela chave de redução.

##### <a name="example-transactions--reduction-key"></a>Exemplo: Transações – chave de redução

Este exemplo mostra como as ordens reais que ocorrem durante os períodos definidos pela chave de redução reduzem requisitos de previsão de demanda.

Para este exemplo, você seleciona **Transações - chave de redução** no campo **Método usado para reduzir requisitos de previsão** da página **Planos mestre**.

As ordens de venda a seguir existem em 1º de janeiro.

| Mês    | Número de peças pedidas |
|----------|--------------------------|
| Janeiro  | 956                      |
| Fevereiro | 1.176                    |
| Março    | 451                      |
| Abril    | 119                      |

Se você usar a mesma previsão de demanda de 1.000 peças por mês que foi usada no exemplo anterior, as quantidades da requisição a seguir serão transferidas para o plano mestre.

| Mês                | Número de peças necessárias |
|----------------------|---------------------------|
| Janeiro              | 44                        |
| Fevereiro             | 0                         |
| Março                | 549                       |
| Abril                | 881                       |
| Maio até dezembro | 1.000                     |

#### <a name="transactions--dynamic-period"></a>Transações – período dinâmico

Se você seleciona **Transações - dinâmico período**, os requisitos de previsão são reduzidos pelas transações de ordem reais ocorridas durante o período dinâmico. O período dinâmico cobre as datas de previsão atuais e termina no início da próxima previsão. Nesse caso, o planejamento mestre cria ordens planejadas para suprir a demanda prevista (requisitos de previsão). Entretanto, quando as transações de ordem reais são feitas, os requisitos de previsão são reduzidos. As transações reais consomem parte dos requisitos de previsão.

Quando esta opção é usada, o seguinte comportamento ocorre:

- As chaves de redução não são obrigatórias nem são usadas. 
- Se a previsão for completamente reduzida, os requisitos da previsão atual se tornam 0 (zero).
- Se não houver previsão futura, os requisitos de previsão da última previsão que foi inserida serão reduzidos.
- Os limites de tempo são incluídos no cálculo de redução de previsão.
- Os dias positivos são incluídos no cálculo de redução de previsão.
- Se as transações de ordens reais excederam os requisitos de previsão, as outras transações não serão encaminhadas para o próximo período de previsão.

##### <a name="example-1-transactions--dynamic-period"></a>Exemplo 1: Transações – período dinâmico

Veja um exemplo simples que mostra como funciona o método **Transações - período dinâmico**.

Neste exemplo, você inclui a previsão de demanda a seguir em um plano mestre.

| Data        | Previsão de demanda |
|------------|-----------------|
| 1º de janeiro  | 1.000           |
| 1 de fevereiro | 1.000             |

Você também criará as ordens de venda a seguir.

| Data         | Quantidade da ordem de venda |
|-------------|----------------------|
| 15 de janeiro  | 200                  |
| 15 de fevereiro | 400                  |

Nesse caso, as ordens planejadas a seguir são criadas.

| Data da previsão de demanda | Quantidade | Explicação                           |
|--------------------- |----------|---------------------------------------|
| 1º de janeiro            | 800      | Requisitos de previsão (= 1.000 – 200) |
| 15 de janeiro           | 200      | Requisitos de ordens de venda             |
| 1 de fevereiro           | 600      | Requisitos de previsão (= 1.000 – 400) |
| 15 de fevereiro          | 400      | Requisitos de ordens de venda             |

##### <a name="example-2-transactions--dynamic-period"></a>Exemplo 2: Transações – período dinâmico

Na maioria dos casos, os sistemas são configurados de forma que as transações reduzam a previsão de demanda em períodos de previsão específicos: semanas, meses e assim por diante. Os períodos são definidos na chave de redução. No entanto, o tempo entre duas linhas de previsão de demanda também pode *implicar* em um período.

Neste exemplo, você cria uma previsão de demanda para as datas e quantidades a seguir.

| Data       | Previsão de demanda |
|------------|-----------------|
| 1º de janeiro  | 1.000           |
| 5 de janeiro  | 500             |
| 12 de janeiro | 1.000           |

Observe que, na previsão, não há um período claro entre as datas. Entre a primeira e a segunda datas há um período de quatro dias, e entre a segunda e a terceira datas há um período de sete dias. Esses períodos são os períodos dinâmicos.

Você também criará as linhas de ordem de venda a seguir.

| Data                             | Quantidade da ordem de venda |
|----------------------------------|----------------------|
| 15 de dezembro do ano anterior | 500                  |
| 3 de janeiro                        | 100                  |
| 10 de janeiro                       | 200                  |

Nesse caso, a previsão será reduzida da seguinte maneira:

- Como a primeira ordem de venda não está em nenhum período, ela não reduz nenhuma previsão.
- Como a segunda ordem de venda está entre 1º e 5 de janeiro, isso reduz em 100 a previsão para 1º de janeiro.
- Como a terceira ordem de venda está entre 5 e 12 de janeiro, isso reduz em 200 a previsão para 5 de janeiro.

Por isso, as ordens planejadas a seguir são criadas.

| Data da previsão de demanda             | Quantidade | Explicação                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| 15 de dezembro do ano anterior | 500      | Requisitos de ordem de venda                                            |
| 1º de janeiro                        | 900      | Período dos requisitos de previsão de 1º a 5 de janeiro (= 1.000 – 100) |
| 3 de janeiro                        | 100      | Requisitos de ordem de venda                                            |
| 5 de janeiro                        | 300      | Período dos requisitos de previsão de 5 a 10 de janeiro (= 500 – 200)  |
| 12 de janeiro                       | 1.000    | Período dos requisitos de previsão de 12 até o final de janeiro                      |

### <a name="create-and-set-up-a-forecast-reduction-key"></a><a name="create-reduction-key"></a>Criar e configurar uma chave de redução da previsão

Uma chave de redução da previsão é usada nos métodos **Transações - chave de redução** e **Percentual - chave de redução** para diminuir os requisitos de previsão. Siga estas etapas para criar e configurar uma chave de redução.

1. Vá para **Planejamento mestre \> Configuração \> Cobertura \> Chaves de redução**.
2. Selecione **Nova** pressione **CTRL+N** para criar uma chave de redução.
3. No campo **Chave de redução**, insira um identificador exclusivo para a chave de redução da previsão. Em seguida, no campo **Nome**, insira um nome. 
4. Defina os períodos e o percentual da chave de redução em cada período:

    - O campo **Data de efetivação** indica a data de início da criação dos períodos. Quando a opção **Usar a data de efetivação** é definida como **Sim**, os períodos iniciam na data de efetivação. Quando ela é definida como **Não**, os períodos iniciam na data em que o planejamento mestre é executado.
    - Defina os períodos durante os quais a redução da previsão deve ocorrer.
    - Para um período específico, defina as porcentagens de redução dos requisitos de previsão. Você pode inserir valores positivos para diminuir os requisitos ou valores negativos para aumentá-los.

### <a name="use-a-reduction-key"></a><a name="use-reduction-key"></a>Use uma chave de redução

Uma chave de redução da previsão deve ser atribuída ao grupo de cobertura do item. Siga estas etapas para atribuir uma chave de redução ao grupo de cobertura de um item.

1. Vá para **Planejamento mestre \> Configuração \> Cobertura \> Grupos de cobertura**.
2. Na Guia Rápida **Outro**, no campo **Chave de redução**, selecione a chave de redução para atribuir ao grupo de cobertura. A chave de redução é aplicada a todos os itens que pertencem ao grupo de cobertura.
3. Para usar uma chave de redução para calcular a redução da previsão durante o agendamento do planejamento mestre, você deve definir esse parâmetro na configuração do plano de previsão ou do plano mestre. Vá para um dos seguintes locais:

    - Planejamento mestre \> Configuração \> Planos \> Planos de previsão
    - Planejamento mestre \> Configuração \> Planos \> Planos mestres

4. Na página **Planos de previsão** ou **Planos mestres**, na Guia Rápida **Geral**, no campo **Método usado para reduzir os requisitos de previsão**, selecione **Percentual - chave de redução** ou **Transações - chave de redução**.

### <a name="reduce-a-forecast-by-transactions"></a>Reduzir uma previsão por transações

Quando você seleciona **Transações - chave de redução** ou **Transações - período dinâmico** como método para reduzir os requisitos de previsão, pode especificar quais transações reduzem a previsão. Na página **Grupos de cobertura**, na Guia Rápida **Outro**, no campo **Reduzir a previsão por**, selecione **Todas as transações**, se todas as transações tiverem que reduzir a previsão, ou **Ordens**, se somente as ordens de venda devem reduzir a previsão.
