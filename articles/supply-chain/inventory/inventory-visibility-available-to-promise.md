---
title: Programações de alterações disponíveis e disponível para promessa da Visibilidade de Estoque
description: Este artigo descreve como programar as alterações disponíveis futuras e calcular as quantidades de (ATP) disponível-para-promessa.
author: yufeihuang
ms.date: 05/11/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-04
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: f831c5d5719bbbd72c7cff37b8b35826f48ce6e4
ms.sourcegitcommit: ce58bb883cd1b54026cbb9928f86cb2fee89f43d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/25/2022
ms.locfileid: "9719282"
---
# <a name="inventory-visibility-on-hand-change-schedules-and-available-to-promise"></a>Programações de alterações disponíveis e disponível para promessa da Visibilidade de Estoque

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar o recurso *programação de alteração disponível* para programar alterações futuras disponíveis e calcular quantidades disponíveis para promessa (ATP). ATP é a quantidade de um item que está disponível e pode ser prometida a um cliente no próximo período. O uso deste cálculo pode aumentar bastante o recurso de atendimento da ordem.

Para muitos fabricantes, varejistas ou vendedores, não basta saber o que está disponível no momento. Eles devem ter visibilidade total da disponibilidade futura. Essa disponibilidade futura deve considerar o futuro, a demanda futura e ATP.

## <a name="enable-and-set-up-the-features"></a><a name="setup"></a>Habilitar e configurar os recursos

Para usar a ATP, você deve configurar uma ou mais medidas calculadas para calcular as quantidades de ATP. Você também deve ativar o recurso e configurar as definições de ATP no Microsoft Power Apps.

### <a name="set-up-calculated-measures-for-atp-quantities"></a>Configurar medidas calculadas para quantidades de ATP

A *medida calculada de ATP* é aquela calculada predefinida que normalmente é usada para localizar a quantidade disponível que está atualmente em andamento. A *quantidade de suprimentos* é a soma das quantidades das medidas físicas com um tipo de modificador de *adição* e a *quantidade de demanda* é a soma de quantidades das medidas físicas com um tipo de modificador de *subtração*.

Você pode adicionar várias medidas calculadas para calcular várias quantidades de ATP. Mas, o número total de medidas físicas distintas em todas as medidas calculadas de ATP deve ser menor do que nove.

> [!IMPORTANT]
> Uma medida calculada é uma composição de medidas físicas. Sua fórmula pode incluir somente medidas físicas sem duplicatas, não medidas calculadas.

Por exemplo, é possível configurar a seguinte medida calculada:

**Disponível em estoque** = (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) – (*ReservPhysical* + *SoftReservePhysical* + *Outbound*)

A soma (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) representa o suprimento e a soma (*ReservPhysical* + *SoftReservePhysical* + *Outbound*) representa a demanda. Portanto, a medida calculada pode ser compreendida da seguinte maneira:

**Disponível em estoque** = *Suprimento* – *Demanda*

Você pode adicionar outra medida calculada para calcular a quantidade de ATP **física disponível**.

**Física disponível** = (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) – (*Outbound*)

Há oito medidas físicas distintas entre essas duas medidas calculadas de ATP: *PhysicalInvent*, *OnHand*, *Unrestricted*, *QualityInspection*, *Inbound*, *ReservPhysical*, *SoftReservePhysical*, e *Outbound*.

Para obter mais informações sobre medidas calculadas, consulte [Medidas calculadas](inventory-visibility-configuration.md#calculated-measures).

### <a name="turn-on-the-on-hand-change-schedule-feature-and-configure-atp-settings"></a>Ativar o recurso de programação de alterações disponível e configurar as definições de ATP

Siga estas etapas para ativar o recurso *Programação de alteração disponível* no Power Apps e configure as definições de ATP.

1. Entre no Power Apps e abra a Visibilidade de Estoque.
1. Abra a página **Configuração**.
1. Na guia **Gerenciamento de Recursos**, ative o recurso *OnhandChangeSchedule*.
1. Selecione a guia **Definição de ATP**.
1. Quando você consultar a Visibilidade de Estoque, ela fornecerá um resultado que incluirá cada medida calculada de ATP que você adicionar aqui. Selecione **Adicionar** para adicionar uma medida calculada de ATP.
1. Defina os seguintes campos:

    - **Fonte de Dados** – selecione a fonte de dados associada à medida calculada.
    - **Medida Calculada** – selecione a medida calculada que está associada à fonte de dados selecionada e que você deseja usar para localizar a quantidade disponível no momento.
    - **Período da Programação** – Insira o número de dias que os usuários podem exibir e enviar alterações disponíveis programadas quando a medida calculada selecionada é usada. Os usuários que consultam informações sobre ações receberão a quantidade disponível, as alterações disponíveis programadas e ATP para cada dia neste período, começando com a data atual. Selecione um inteiro entre 1 e 7.

    > [!IMPORTANT]
    > O período da programação inclui a data atual. Portanto, os usuários podem programar alterações disponíveis para ocorrer a qualquer hora a partir da data atual (o dia em que a alteração é enviada) até (período programado – 1) dias no futuro.

1. Selecione **Salvar**.
1. Repita as etapas 5 a 7 até adicionar todas as medidas calculadas necessárias para ATP.
1. Ao concluir a definição de todas as configurações necessárias, selecione **Atualizar Configuração**.

Para obter mais informações, consulte [Concluir e atualizar a configuração](inventory-visibility-configuration.md).

## <a name="how-the-on-hand-change-schedule-and-atp-calculations-work"></a>Como a programação de alterações disponível e os cálculos de ATP funcionam

Uma *programação de alteração disponível* estabelece as datas e quantidades esperadas de alterações disponíveis programadas. Você pode enviar uma programação de alteração disponível para a Visibilidade de Estoque desde que as datas estejam dentro do período definido pela configuração do **Período programado** (consulte a seção [Habilitar e configurar os recursos](#setup)). Os usuários que consultam informações sobre estoque receberão a quantidade disponível, as alterações disponíveis programadas e ATP para cada dia neste período.

As alterações programadas não são inicialmente confirmadas e, portanto, não afetam as quantidades disponíveis reais no sistema. Para confirmar as alterações, você deve enviar um *evento de alteração disponível*, que atualiza a quantidade disponível real. Em seguida, você deve reverter a alteração programada, enviando uma programação de alteração disponível para uma quantidade negativa correspondente.

Por exemplo, é necessário fazer um pedido de 10 bicicletas e esperar que ele chegue amanhã. Portanto, você envia uma programação de alteração disponível que tem uma quantidade de entrada de 10 e é atualizada para amanhã. Quando o pedido chegar no dia seguinte, você adicionará as bicicletas ao estoque físico disponível. Em seguida, você deve confirmar a alteração no sistema para atualizar a quantidade disponível real. Para confirmar a alteração, você envia um evento de alteração disponível que tem uma quantidade de entrada de 10. Em seguida, você deve reverter a alteração programada, enviando uma programação de alteração disponível que tem uma quantidade de entrada de -10.

Quando você consulta a Visibilidade de Estoque para quantidades disponíveis e de ATP, ela retorna as informações a seguir para cada dia no período programado:

- **Data** – a data à qual o resultado se aplica. O fuso horário é Tempo Universal Coordenado (UTC).
- **Quantidade disponível** – a quantidade disponível real da data especificada. Esse cálculo é feito de acordo com a medida calculada de ATP que está configurada para a Visibilidade de Estoque.
- **Fornecimento programado** – a soma de todas as quantidades de entrada programadas que não se tornaram fisicamente disponíveis para consumo imediato ou remessa a partir da data especificada.
- **Demanda programada** – a soma de todas as quantidades de saída programadas que não foram consumidas ou remetidas a partir da data especificada.
- **Quantidade ATP** – a quantidade disponível mínima projetada que é disponibilizada a partir da data especificada até o final do período programado. Essa quantidade inclui todos os ajustes de quantidade programados. É a quantidade máxima que pode ser prometida na data atual para entrega ou consumo nesse dia.

Por exemplo, se a data atual for 1º de fevereiro de 2022 e o período da programação for 7, os usuários poderão enviar as alterações disponíveis programadas que deverão ocorrer a partir de 1º de fevereiro a 7 de fevereiro de 2022. Neste caso, a quantidade ATP para 3 de fevereiro, por exemplo, é calculada com base na quantidade disponível desse dia e nas quantidades programadas de 3 de fevereiro a 7 de fevereiro.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como uma série de alterações de quantidade programada afeta as quantidades disponíveis e ATP que a Visibilidade de Estoque relata. Também mostra como confirmar uma alteração programada, como uma alteração de programação confirmada afeta os resultados e o que pode ocorrer se você não confirmar uma alteração programada.

Os resultados neste exemplo mostram um valor *disponível projetado*. Esse valor incorpora todas as atualizações programadas para fins de ilustração, mas não é realmente informado quando você consulta a Visibilidade de Estoque.

1. As configurações a seguir são definidas para seu sistema na página **Definição de ATP** no Power Apps:

    - **Medida calculada de ATP** – você tem uma medida calculada que é chamada *Disponível*. É calculado como *Disponível = Fornecimento – Demanda*. Você seleciona essa medida aqui.
    - **Período da programação** – você seleciona *7*.

1. As seguintes condições também se aplicam:

    - A data atual é 1º de fevereiro de 2022.
    - A quantidade disponível atual é 20.

1. Para a data atual (1º de fevereiro de 2022), você envia uma quantidade solicitada programada de 3 para a Visibilidade de Estoque. Portanto, a quantidade disponível projetada é 17. A tabela a seguir mostra o resultado.

    | Data | Disponível | Fornecimento programado | Demanda programada | Disponível projetado | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 17 |
    | 2022-02-02 | 20 | | | 17 | 17 |
    | 2022-02-03 | 20 | | | 17 | 17 |
    | 2022-02-04 | 20 | | | 17 | 17 |
    | 2022-02-05 | 20 | | | 17 | 17 |
    | 2022-02-06 | 20 | | | 17 | 17 |
    | 2022-02-07 | 20 | | | 17 | 17 |

1. Na data atual (1º de fevereiro de 2022), você envia uma quantidade de fornecimento programada de 10 para 3 de fevereiro de 2022. A tabela a seguir mostra o resultado.

    | Data | Disponível | Fornecimento programado | Demanda programada | Disponível projetado | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 17 |
    | 2022-02-02 | 20 | | | 17 | 17 |
    | 2022-02-03 | 20 | 10 | | 27 | 27 |
    | 2022-02-04 | 20 | | | 27 | 27 |
    | 2022-02-05 | 20 | | | 27 | 27 |
    | 2022-02-06 | 20 | | | 27 | 27 |
    | 2022-02-07 | 20 | | | 27 | 27 |

1. Na data atual (1º de fevereiro de 2022), você envia as seguintes alterações de quantidade programadas:

    - Quantidade de demanda 15 para 4 de fevereiro de 2022
    - Quantidade de suprimento 1 para 5 de fevereiro de 2022
    - Quantidade de suprimento 3 para 6 de fevereiro de 2022

    A tabela a seguir mostra o resultado.

    | Data | Disponível | Fornecimento programado | Demanda programada | Disponível projetado | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 12 |
    | 2022-02-02 | 20 | | | 17 | 12 |
    | 2022-02-03 | 20 | 10 | | 27 | 12 |
    | 2022-02-04 | 20 | | 15 | 12 | 12 |
    | 2022-02-05 | 20 | 1 | | 13 | 13 |
    | 2022-02-06 | 20 | 3 | | 16 | 16 |
    | 2022-02-07 | 20 | | | 16 | 16 |

1. Na data atual (1º de fevereiro de 2022), você remete a quantidade de demanda programada de 3. Portanto, você deve confirmar a alteração para que ela seja refletida na sua quantidade disponível real. Para confirmar a alteração, você envia um evento de alteração disponível que tem uma quantidade de saída de 3. Em seguida, você deve reverter a alteração programada, enviando uma programação de alteração disponível que tem uma quantidade de saída de -3. A tabela a seguir mostra o resultado.

    | Data | Disponível | Fornecimento programado | Demanda programada | Disponível projetado | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 17 | | 0 | 17 | 12 |
    | 2022-02-02 | 17 | | | 17 | 12 |
    | 2022-02-03 | 17 | 10 | | 27 | 12 |
    | 2022-02-04 | 17 | | 15 | 12 | 12 |
    | 2022-02-05 | 17 | 1 | | 13 | 13 |
    | 2022-02-06 | 17 | 3 | | 16 | 16 |
    | 2022-02-07 | 17 | | | 16 | 16 |

1. No dia seguinte (2 de fevereiro de 2022), o período da programação passa para frente em um dia. A tabela a seguir mostra o resultado.

    | Data | Disponível | Fornecimento programado | Demanda programada | Disponível projetado | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-02 | 17 | | | 17 | 12 |
    | 2022-02-03 | 17 | 10 | | 27 | 12 |
    | 2022-02-04 | 17 | | 15 | 12 | 12 |
    | 2022-02-05 | 17 | 1 | | 13 | 13 |
    | 2022-02-06 | 17 | 3 | | 16 | 16 |
    | 2022-02-07 | 17 | | | 16 | 16 |
    | 2022-02-08 | 17 | | | 16 | 16 |

1. No entanto, dois dias depois (4 de fevereiro de 2022), a quantidade de fornecimento de 10 programada para 3 de fevereiro ainda não foi recebida. A tabela a seguir mostra o resultado.

    | Data | Disponível | Fornecimento programado | Demanda programada | Disponível projetado | ATP |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-04 | 17 | | 15 | 2 | 2 |
    | 2022-02-05 | 17 | 1 | | 3 | 3 |
    | 2022-02-06 | 17 | 3 | | 6 | 6 |
    | 2022-02-07 | 17 | | | 6 | 6 |
    | 2022-02-08 | 17 | | | 6 | 6 |
    | 2022-02-09 | 17 | | | 6 | 6 |
    | 2022-02-10 | 17 | | | 6 | 6 |

    Como você pode ver, as alterações disponíveis (mas não confirmadas) programadas não afetam a quantidade disponível real.

## <a name="submit-change-schedules-change-events-and-atp-queries-through-the-api"></a><a name="api-urls"></a>Enviar programações de alteração, eventos de alteração e consultas ATP por meio da API

Você pode usar as seguintes URLs da API (interface de programação de aplicativos) para enviar programações de alteração disponíveis, eventos de alteração e consultas.

| Caminho | Método | Descrição |
| --- | --- | --- |
| `/api/environment/{environmentId}/onhand/changeschedule` | `POST` | Criar um alteração disponível programada. |
| `/api/environment/{environmentId}/onhand/changeschedule/bulk` | `POST` | Criar várias alterações disponíveis programadas. |
| `/api/environment/{environmentId}/onhand` | `POST` | Criar um evento de alteração disponível. |
| `/api/environment/{environmentId}/onhand/bulk` | `POST` | Criar vários eventos de alteração. |
| `/api/environment/{environmentId}/onhand/indexquery` | `POST` | Consultar usando o método `POST`. |
| `/api/environment/{environmentId}/onhand` | `GET` | Consultar usando o método `GET`. |
| `/api/environment/{environmentId}/onhand/exactquery` | `POST` | Fazer uma consulta exata usando o método `POST`. |

Para obter mais informações, consulte [APIs públicas de Visibilidade de Estoque](inventory-visibility-api.md).

### <a name="create-one-on-hand-change-schedule"></a>Criar uma agenda de alterações disponíveis

Uma agenda de alterações disponíveis é criada, enviando uma solicitação `POST` para a URL de serviço de Visibilidade de Estoque relevante (consulte a seção [Enviar agendas de alterações, eventos de alterações e consultas ATP por meio da API](#api-urls)). Você também pode enviar solicitações em massa.

Uma agenda de alterações disponíveis poderá ser criada apenas se a data agendada estiver entre a data atual e o final do período de programação atual. O formato de data/hora deve ser *ano-mês-dia* (por exemplo, **2022-02-01**). O formato de hora deve ser exato somente no dia.

Esta API cria uma única agenda de alterações disponíveis.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # optional
        dimensions: {
            [key:string]: string,
        },
        quantitiesByDate: {
            [datetime:datetime]: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
    }
```

O exemplo a seguir mostra o conteúdo do corpo de exemplo sem `dimensionDataSource`.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    },
    "quantitiesByDate":
    {
        "2022-02-01": // today
        {
            "pos":{
                "inbound": 10
            }
        }
    }
}
```

### <a name="create-multiple-on-hand-change-schedules"></a>Criar várias agendas de alterações disponíveis

Essa API pode criar vários registros ao mesmo tempo. As únicas diferenças entre esta API e a API de evento único são os valores `Path` e `Body`. Para essa API, `Body` fornece uma matriz de registros. O número máximo de registros é 512. Portanto, a API em massa de alterações disponíveis agendada pode dar suporte a até 512 alterações agendadas ao mesmo tempo.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantitiesByDate: {
                [datetime:datetime]: {
                    [dataSourceName:string]: {
                        [key:string]: number,
                    },
                },
            },
        },
        ...
    ]
```

O exemplo a seguir mostra o conteúdo do corpo de exemplo.

```json
[
    {
        "id": "id-bike-0001",
        "organizationId": "usmf",
        "productId": "Bike",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-01": // today
            {
                "pos":{
                    "inbound": 10
                }
            }
        }
    },
    {
        "id": "id-car-0002",
        "organizationId": "usmf",
        "productId": "Car",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-05":
            {
                "pos":{
                    "outbound": 10
                }
            }
        }
    }
]
```

### <a name="create-on-hand-change-events"></a>Criar eventos de alteração disponíveis

Os eventos de alteração disponíveis são feitos pelo envio de uma solicitação `POST` para a URL de serviço de Visibilidade de Estoque relevante (consulte a seção [Enviar programações de alteração, eventos de alteração e consultas ATP por meio da API](#api-urls)). Você também pode enviar solicitações em massa.

> [!NOTE]
> Os eventos de alteração disponíveis não são exclusivos da funcionalidade ATP, mas fazem parte da API de Visibilidade de Estoque padrão. Este exemplo foi incluído porque os eventos são relevantes ao trabalhar com ATP. Os eventos de alteração disponíveis se assemelham a reservas de alteração disponíveis, mas as mensagens de evento devem ser enviadas para uma URL de API diferente e os eventos usam `quantities`, em vez de `quantityByDate` no corpo da mensagem. Para obter mais informações sobre os eventos de alteração disponíveis e outros recursos da API de Visibilidade de Estoque, consulte [APIs públicas de Visibilidade de Estoque](inventory-visibility-api.md#create-one-onhand-change-event).

O exemplo a seguir mostra um corpo de solicitação que contém um evento de alteração disponível único.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "SizeId": "Big",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 10.0
        }
    }
}
```

## <a name="query-the-scheduled-on-hand-changes-and-atp-results"></a>Consultar as alterações disponíveis programadas e os resultados de ATP

Você pode consultar as alterações disponíveis e os resultados de ATP programados, enviando uma solicitação `POST` ou uma solicitação `GET` para a URL da API apropriada (consulte a seção [Enviar programações de alteração, eventos de alteração e consultas ATP por meio da API](#api-urls)).

Na sua solicitação, defina `QueryATP` como *verdadeiro* se quiser consultar alterações disponíveis e resultados de ATP.

- Se você estiver enviando a solicitação usando o método `GET`, defina este parâmetro na URL.
- Se você estiver enviando a solicitação usando o método `POST`, defina este parâmetro no corpo da solicitação.

> [!NOTE]
> Independentemente de o parâmetro `returnNegative` ser definido como *verdadeiro* ou *falso* no corpo da solicitação, o resultado incluirá valores negativos quando você consultar as alterações disponíveis e os resultados de ATP programados. Esses valores negativos serão incluídos porque, se somente as ordens de demanda forem planejadas ou se as quantidades de fornecimento forem menores do que as quantidades de demanda, as quantidades de alterações disponíveis planejadas serão negativas. Se valores negativos não foram incluídos, os resultados ficarão confusos. Para obter mais informações sobre essa opção e como ela funciona para outros tipos de consultas, consulte [APIs públicas de Visibilidade de Estoque](inventory-visibility-api.md#query-with-post-method).

### <a name="query-by-using-the-post-method"></a>Fazer uma consulta usando o método POST

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

O exemplo a seguir mostra como criar um corpo de solicitação de consulta de índice que possa ser enviado para a Visibilidade de Estoque usando o método `POST`.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "SiteId": ["1"],
        "LocationId": ["11"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true
}
```

### <a name="query-by-using-the-get-method"></a>Fazer uma consulta usando o método GET

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

O exemplo a seguir mostra como criar uma URL de solicitação de consulta de índice como uma solicitação `GET`.

```txt
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand?organizationId=usmf&productId=Bike&SiteId=1&LocationId=11&groupBy=ColorId,SizeId&returnNegative=true&QueryATP=true
```

O resultado desta solicitação `GET` é exatamente igual ao resultado da solicitação `POST` no exemplo anterior.

### <a name="exact-query-by-using-the-post-method"></a>Fazer uma consulta exata usando o método POST

```txt
Path:
    /api/environment/{environmentId}/onhand/exactquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            dimensions: string[],
            values: string[][],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

O exemplo a seguir mostra como criar um corpo de solicitação de consulta exata que possa ser enviado para a Visibilidade de Estoque usando o método `POST`.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "dimensions": ["SiteId", "LocationId"],
        "values": [
            ["1", "11"]
        ]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true
}
```

### <a name="query-result-example"></a>Exemplo de resultado da consulta

Qualquer um dos exemplos de consulta anteriores podem produzir a resposta a seguir. Para esse exemplo, o sistema é configurado com as seguintes configurações:

- **Medida ATP calculada:** *iv.onhand = pos.inbound – pos.outbound*
- **Período da programação:** *7*

Veja aqui um exemplo do corpo da resposta.

```json
[
    {
        "quantitiesByDate": {
            "2022-02-02T00:00:00": {
                "pos": {
                    "outbound": 5,
                    "inbound": 0,
                },
                "iv": {
                    "onhand": -5,
                },
            },
            "2022-02-06T00:00:00": {
                "pos": {
                    "inbound": 7,
                    "outbound": 0,
                },
                "iv": {
                    "onhand": 7,
                },
            }
        },
        "atpQuantities": {
            "2022-02-01T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-02T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-03T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-04T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-05T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-06T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            },
            "2022-02-07T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            }
        },
        "productId": "Bike ",
        "dimensions": {
            "ColorId": "Red",
            "SizeId": "Big",
            "siteid": "1",
            "locationid": "11"
        },
        "quantities": {
            "pos": {
                "inbound": 10.0,
                "outbound": 0,
            },
            "iv": {
                "onhand": 10.0,
            }
        }
    }
]
```
