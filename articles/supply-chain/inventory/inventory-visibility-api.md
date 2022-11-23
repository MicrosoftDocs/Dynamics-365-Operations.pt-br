---
title: APIs públicas do Inventory Visibility
description: Este artigo descreve as APIs públicas fornecidas pela visibilidade do Estoque.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 8b0b8ca261237fbb2190f2a94cc11b816ae05af5
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762825"
---
# <a name="inventory-visibility-public-apis"></a>APIs públicas do Inventory Visibility

[!include [banner](../includes/banner.md)]

Este artigo descreve as APIs públicas fornecidas pela visibilidade do Estoque.

A API REST pública do Suplemento Visibilidade de Estoque apresenta vários pontos de extremidade específicos para integração. Ela oferece suporte a quatro tipos de interação principais:

- Lançar alterações de estoque disponíveis no suplemento a partir de um sistema externo
- Configuração ou substituição de quantidades de estoque disponível no suplemento de um sistema externo
- Lançamento de eventos de reserva no no suplemento desde um sistema externo
- Consultar as quantidades disponíveis no momento a partir de um sistema externo

A tabela a seguir lista as APIs disponíveis no momento:

| Caminho | Método | Descrição |
|---|---|---|
| /api/environment/{environmentId}/onhand | Lançar | [Criar um evento de alteração disponível](#create-one-onhand-change-event)|
| /api/environment/{environmentId}/onhand/bulk | Lançar | [Criar vários eventos de alteração](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Lançar | [Definir/substituir quantidades disponíveis](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Lançar | [Criar um evento de reserva flexível](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Lançar | [Criar vários eventos de reserva flexível](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/unreserve | Lançar | [Reverter um evento de reserva flexível](#reverse-one-reservation-event) |
| /api/environment/{environmentId}/onhand/unreserve/bulk | Lançar | [Reverter vários eventos de reserva flexível](#reverse-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/changeschedule | Lançar | [Criar um alteração disponível programada](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/changeschedule/bulk | Lançar | [Criar várias alterações disponíveis com datas](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/indexquery | Lançar | [Fazer uma consulta usando o método POST](#query-with-post-method) (recomendado) |
| /api/environment/{environmentId}/onhand | Obter | [Consultar usando o método get](#query-with-get-method) |
| /api/environment/{environmentId}/onhand/exactquery | Lançar | [Fazer uma consulta exata usando o método POST](#exact-query-with-post-method) |
| /api/environment/{environmentId}/allocation<wbr>/allocate | Lançar | [Criar um evento alocar](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/unallocate | Lançar | [Criar um evento desalocar](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/reallocate | Lançar | [Criar um evento realocar](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/consume | Lançar | [Criar um evento consumir](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation<wbr>/query | Lançar | [Resultado da alocação da consulta](inventory-visibility-allocation.md#using-allocation-api) |

> [!NOTE]
> A parte {environmentId} do caminho é a ID do ambiente em Microsoft Dynamics Lifecycle Services.
> 
> A API em massa pode retornar um máximo de 512 registros para cada solicitação.

A Microsoft forneceu uma coleção de solicitações do *Postman* pronta para uso. Você pode importar essa coleção para o seu software *Postman* usando o seguinte link compartilhado: <https://www.getpostman.com/collections/95a57891aff1c5f2a7c2>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a><a name = "endpoint-lcs"></a>Localizar o ponto de extremidade de acordo com o seu ambiente do Lifecycle Services

O microsserviço da Visibilidade de Estoque é implantado no Microsoft Azure Service Fabric, em várias geografias e regiões. No momento, não há um ponto de extremidade central que possa redirecionar automaticamente sua solicitação para a geografia e a região correspondentes. Portanto, você deve compor as partes das informações em uma URL usando o seguinte padrão:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

O nome curto da região pode ser encontrado no ambiente do Lifecycle Services. A tabela a seguir lista as regiões disponíveis no momento.

| Região do Azure        | Nome curto da região |
| ------------------- | ----------------- |
| Leste da Austrália      | eau               |
| Sudeste da Austrália | seau              |
| Canadá Central      | cca               |
| Leste do Canadá         | eca               |
| Norte da Europa        | neu               |
| Oeste da Europa         | weu               |
| Leste dos EUA             | eus               |
| Oeste dos EUA             | wus               |
| Sul do Reino Unido            | suk               |
| Oeste do Reino Unido             | wuk               |
| Leste do Japão          | ejp               |
| Oeste do Japão          | wjp               |
| Índia Central       | cin               |
| Sul da Índia         | sin               |
| Norte da Suíça   | nch               |
| Oeste da Suíça    | wch               |
| Sul da França        | sfr               |
| Leste da Ásia           | eas               |
| Sudeste da Ásia     | seas              |
| Norte dos EAU           | nae               |
| Leste da Noruega         | eno               |
| Oeste da Noruega         | wno               |
| Oeste da África do Sul   | wza               |
| Norte da África do Sul  | nza               |

O número da ilha é onde seu ambiente do Lifecycle Services é implantado no Service Fabric. No momento, não há como obter essas informações do lado do usuário.

A Microsoft criou uma IU (interface do usuário) no Power Apps para que você possa obter o ponto de extremidade completo do microsserviço. Para obter mais informações, consulte [Localizar o ponto de extremidade de serviço](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Autenticação

O token de segurança da plataforma é usado para chamar a API pública da Visibilidade de Estoque. Portanto, você deve gerar um token *Azure Active Directory (Azure AD)* usando o aplicativo Azure AD. Você deve usar o token Azure AD para obter o *token de acesso* do serviço de segurança.

A Microsoft fornece uma coleção de obtenção de token do *Postman* pronta para uso. Você pode importar essa coleção para o seu software *Postman* usando o seguinte link compartilhado: <https://www.getpostman.com/collections/496645018f96b3f0455e>.

Para obter um token de serviço de segurança, siga estas etapas.

1. Entre no portal do Azure e use-o para localizar os valores de `clientId` e `clientSecret` para seu aplicativo Dynamics 365 Supply Chain Management.
1. Busque um token do Azure AD (`aadToken`) ao enviar uma solicitação HTTP com as seguintes propriedades:

    - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/v2.0/token`
    - **Método:** `GET`
    - **Conteúdo do corpo (dados de formulário):**

        | Chave           | Alíquota                                            |
        | ------------- | -------------------------------------------------|
        | client_id     | ${aadAppId}                                      |
        | client_secret | ${aadAppSecret}                                  |
        | grant_type    | client_credentials                               |
        | escopo         | 0cdb527f-a8d1-4bf8-9436-b352c68682b2/.padrão    |

    Você deverá receber um token do Azure AD (`aadToken`) em resposta. Ela deve se assemelhar ao seguinte exemplo.

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Formula uma solicitação JSON (JavaScript Object Notation) semelhante ao exemplo a seguir.

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type": "aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope": "https://inventoryservice.operations365.dynamics.com/.default",
        "context": "{$LCS_environment_id}",
        "context_type": "finops-env"
    }
    ```

    Observe os seguintes pontos:

    - O valor de `client_assertion` deverá ser o token do Azure AD (`aadToken`) que você recebeu na etapa anterior.
    - O valor de `context` deve ser a ID do ambiente do Lifecycle Services em que você deseja implantar o suplemento.
    - Defina todos os demais valores conforme mostrado no exemplo.

1. Busque um token de acesso (`access_token`) ao enviar uma solicitação HTTP com as seguintes propriedades:

    - **URL:** `https://securityservice.operations365.dynamics.com/token`
    - **Método:** `POST`
    - **Cabeçalho HTTP:** inclua a versão da API. (A chave é `Api-Version`, e o valor é `1.0`.)
    - **Conteúdo do corpo:** inclua a solicitação JSON criada na etapa anterior.

    Você deverá receber um token de acesso (`access_token`) em resposta. Você deverá usar esse token como um token de portador para chamar a API da Visibilidade de Estoque. Este é um exemplo.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 3600
    }
    ```

> [!IMPORTANT]
> Ao usar a coleção de solicitações *Postman* para chamar APIs públicas de Visibilidade de Estoque, você deverá adicionar um token de portador a cada solicitação. Para localizar o token de portador, selecione a guia **Autorização** na URL da solicitação, selecione o tipo **Token de Portador** e copie o token de acesso obtido na última etapa. Nas seções posteriores deste artigo, `$access_token` será usado para representar o token buscado na última etapa.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Criar eventos de alteração disponíveis

Há duas APIs para a criação de eventos de alteração disponíveis:

- Criar um registro: `/api/environment/{environmentId}/onhand`
- Criar vários registros: `/api/environment/{environmentId}/onhand/bulk`

A tabela a seguir resume o significado de cada campo no corpo do JSON.

| ID do campo | Descrição |
|---|---|
| `id` | Uma ID exclusiva para o evento de alteração específico. Se ocorrer um reenvio devido a uma falha de serviço, essa ID será usada para garantir que o mesmo evento não seja contado duas vezes no sistema. |
| `organizationId` | O identificador da organização vinculado ao evento. Esse valor é mapeado para uma ID da organização ou da área de dados no Supply Chain Management. |
| `productId` | O identificador do produto. |
| `quantities` | A quantidade pela qual a quantidade disponível deve ser alterada. Por exemplo, se 10 novos livros forem adicionados a uma prateleira, esse valor será `quantities:{ shelf:{ received: 10 }}`. Se três livros forem removidos da prateleira ou se forem vendidos, esse valor será `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | A fonte de dados das dimensões usadas no evento e na consulta de alteração de lançamento. Se você especificar a fonte de dados, poderá usar as dimensões personalizadas da fonte de dados especificada. A Visibilidade de Estoque pode usar a configuração da dimensão para mapear as dimensões personalizadas para as dimensões padrão gerais. Se nenhum valor de `dimensionDataSource` for especificado, você só poderá usar as [dimensões base](inventory-visibility-configuration.md#data-source-configuration-dimension) gerais em suas consultas. |
| `dimensions` | Um par de chave-valor dinâmico. Os valores são mapeados para algumas das dimensões no Supply Chain Management. No entanto, você também pode adicionar dimensões personalizadas (por exemplo, *Origem*) para indicar se o evento provém do Supply Chain Management ou de um sistema externo. |

> [!NOTE]
> Os parâmetros `siteId` e `locationId` e constroem a [configuração da partição](inventory-visibility-configuration.md#partition-configuration). Portanto, você deve especificá-los nas dimensões ao criar eventos de alteração disponível, definir ou substituir quantidades disponíveis ou criar eventos de reserva.

As subseções a seguir fornecem exemplos que mostram como usar essas APIs.

### <a name="create-one-on-hand-change-event"></a><a name="create-one-onhand-change-event"></a>Criar um evento de alteração disponível

Essa API cria um único evento de alteração disponível.

```txt
Path:
    /api/environment/{environmentId}/onhand
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
        dimensionDataSource: string, # Optional
        dimensions: {
            [key:string]: string,
        },
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
    }
```

O exemplo a seguir mostra o conteúdo do corpo de exemplo. Neste exemplo, a empresa possui um sistema de ponto de venda (POS) que processa as transações na loja e, portanto, as alterações de estoque. O cliente devolveu uma camiseta vermelha à sua loja. Para refletir a alteração, você publica um único evento de alteração para o produto *Camiseta*. Esse evento aumentará a quantidade do produto *Camiseta* em 1.

```json
{
    "id": "Test201",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "posMachineId": "0001",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

O exemplo a seguir mostra o conteúdo do corpo de exemplo sem `dimensionDataSource`. Nesse caso, `dimensions` será as [dimensões básicas](inventory-visibility-configuration.md#data-source-configuration-dimension). Se `dimensionDataSource` for definido, `dimensions` poderá ser as dimensões da fonte de dados ou as dimensões básicas.

```json
{
    "id": "Test202",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Criar vários eventos de alteração

Essa API pode criar eventos de alteração, assim como a [API de evento único](#create-one-onhand-change-event). A única diferença é que esta API pode criar vários registros ao mesmo tempo. Portanto, os valores `Path` e `Body` diferem. Para essa API, `Body` fornece uma matriz de registros. O número máximo de registros é 512. Portanto, a API em massa de alteração disponível pode suportar até 512 eventos de alteração por vez. 

Por exemplo, uma máquina PDV de uma loja de varejo processou as duas transações a seguir:

- Um pedido de devolução de uma camiseta vermelha
- Uma transação de venda de três camisetas pretas

Nesse caso, você pode incluir ambas as atualizações de estoque em uma chamada de API.

```txt
Path:
    /api/environment/{environmentId}/onhand/bulk
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
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
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
        "id": "Test203",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "Site1",
            "LocationId": "11",
            "posMachineId&quot;: &quot;0001"
            "colorId&quot;: &quot;red"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensions": {
            "siteId": "1",
            "locationId": "11",
            "colorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Definir/substituir quantidades disponíveis

A API *Definir disponível* substitui os dados atuais do produto especificado. Essa funcionalidade é normalmente usada para fazer atualizações de contagem de estoque. Por exemplo, durante sua contagem diária de estoque, uma loja pode descobrir que o estoque disponível real de uma camiseta vermelha é 100. Portanto, a quantidade de entrada do PDV deve ser atualizada para 100, independentemente de qual era a quantidade anterior. Você pode usar esta API para substituir o valor existente.

```txt
Path:
    /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk
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
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifiedDateTimeUTC: datetime,
        },
        ...
    ]
```

O exemplo a seguir mostra o conteúdo do corpo de exemplo. O comportamento dessa API difere do comportamento das APIs descritas na seção [Criar eventos de alteração disponíveis](#create-onhand-change-event), anteriormente neste artigo. Neste exemplo, a quantidade do produto *Camiseta* será definida como 1.

```json
[
    {
        "id": "Test204",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "posMachineId": "0001"
            "colorId": "red"
        },
        "quantities": {
            "pos": {
                "inbound": 100
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Criar eventos de reserva

Para usar a API *Reservar*, você deverá ativar o recurso de reserva e concluir a configuração da reserva. Para obter mais informações (incluindo um fluxo de dados e um cenário de amostra), consulte [Configuração de reserva (opcional)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Criar um evento de reserva

Uma reserva pode ser feita com diferentes configurações da fonte de dados. Para configurar esse tipo de reserva, especifique primeiro a fonte de dados no parâmetro `dimensionDataSource`. Depois disso, no parâmetro `dimensions`, especifique as dimensões de acordo com as configurações de dimensão na fonte de dados de destino.

Ao chamar a API de reserva, você pode controlar a validação da reserva especificando o parâmetro booliano `ifCheckAvailForReserv` no corpo da solicitação. Um valor `True` significa que a validação é necessária, enquanto um valor `False` significa que a validação não é necessária. O valor padrão é `True`.

Se você desejar reverter uma reserva ou cancelar a reserva de quantidades de estoque especificadas, defina a quantidade como um valor negativo e o parâmetro `ifCheckAvailForReserv` como `False` para ignorar a validação. Há também uma API de cancelamento de reserva dedicada para fazer o mesmo. A diferença só ocorre no modo como as duas APIs são chamadas. É mais fácil reverter um evento de reserva específico usando `reservationId` com a API *cancelar reserva*. Para obter mais informações, consulte a seção [Cancelar a reserva de um evento de reserva](#reverse-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve
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
        dimensionDataSource: string,
        dimensions: {
            [key:string]: string,
        },
        quantityDataSource: string, # optional
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
        modifier: string,
        quantity: number,
        ifCheckAvailForReserv: boolean,
    }
```

O exemplo a seguir mostra o conteúdo do corpo de exemplo.

```json
{
    "id": "reserve-0",
    "organizationId": "SCM_IV",
    "productId": "iv_postman_product",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softReservOrdered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "colorId": "red",
        "sizeId&quot;: &quot;small"
    }
}
```

O exemplo a seguir mostra uma resposta bem-sucedida.

```json
{
    "reservationId": "RESERVATION_ID",
    "id": "ohre~id-822-232959-524",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
``` 

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Criar vários eventos de reserva

Essa API é uma versão em massa da [API de evento único](#create-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve/bulk
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
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifier: string,
            quantity: number,
            ifCheckAvailForReserv: boolean,
        },
        ...
    ]
```

## <a name="reverse-reservation-events"></a>Reverter eventos de reserva

A API *Cancelar reserva* funciona como a operação reversa para eventos de [*Reserva*](#create-reservation-events). Ela oferece uma forma de reverter um evento de reserva especificado por `reservationId` ou de diminuir a quantidade de reserva.

### <a name="reverse-one-reservation-event"></a><a name="reverse-one-reservation-event"></a>Reverter um evento de reserva

Quando uma reserva for criada, uma `reservationId` será incluída no corpo da resposta. Você deve fornecer o mesmo `reservationId` para cancelar a reserva e incluir os mesmos `organizationId` e `dimensions` usados na chamada à API de reserva. Finalmente, especifique um valor `OffsetQty` que represente o número de itens a serem liberados da reserva anterior. Uma reserva pode ser total ou parcialmente revertida dependendo do `OffsetQty` especificado. Por exemplo, se *100* unidades de itens foram reservadas, você poderá especificar `OffsetQty: 10` para cancelar a reserva *10* do valor inicial reservado.

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve
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
        reservationId: string,
        dimensions: {
            [key:string]: string,
        },
        OffsetQty: number
    }
```

O código a seguir mostra um exemplo do conteúdo do corpo.

```json
{
    "id": "unreserve-0",
    "organizationId": "SCM_IV",
    "reservationId": "RESERVATION_ID",
    "dimensions": {
        "siteid":"iv_postman_site",
        "locationid":"iv_postman_location",
        "ColorId": "red",
        "SizeId&quot;: &quot;small"
    },
    "OffsetQty": 1
}
```

O código a seguir mostra um exemplo do corpo de uma resposta bem-sucedida.

```json
{
    "reservationId": "RESERVATION_ID",
    "totalInvalidOffsetQtyByReservId": 0,
    "id": "ohoe~id-823-11744-883",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
```

> [!NOTE]
> No corpo da resposta, quando `OffsetQty` for menor ou igual à quantidade de reserva, `processingStatus` será "*êxito*" e `totalInvalidOffsetQtyByReservId` será *0*.
>
> Se `OffsetQty` for maior que o valor reservado, `processingStatus` será "*partialSuccess*" e `totalInvalidOffsetQtyByReservId` será a diferença entre `OffsetQty` e o valor reservado.
>
>Por exemplo, se a reserva tiver uma quantidade de *10* e `OffsetQty` tiver um valor de *12*, `totalInvalidOffsetQtyByReservId` será *2*.

### <a name="reverse-multiple-reservation-events"></a><a name="reverse-multiple-reservation-events"></a>Reverter vários eventos de reserva

Essa API é uma versão em massa da [API de evento único](#reverse-one-reservation-event).

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve/bulk
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
            reservationId: string,
            dimensions: {
                [key:string]: string,
            },
            OffsetQty: number
        }
        ...
    ]
```

## <a name="query-on-hand"></a>Consultar disponíveis

Use a API *Consultar disponíveis* para buscar dados de estoque disponível atuais para seus produtos. Você pode usar essa API sempre que precisar saber o estoque, por exemplo, quando quiser revisar os níveis de estoque do produto em seu site de comércio eletrônico ou quando quiser verificar a disponibilidade do produto em várias regiões ou em lojas e armazéns próximos. No momento, a API oferece suporte à consulta de até 5000 itens individuais por valor de `productID`. Diversos valores `siteID` e `locationID` também podem ser especificados em cada consulta. O limite máximo é definido pela seguinte equação:

*NumOf(SiteID) \* NumOf(LocationID) <= 100*.

### <a name="query-by-using-the-post-method"></a><a name="query-with-post-method"></a>Consultar usando o método post

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

Na parte do corpo desta solicitação, `dimensionDataSource` ainda é um parâmetro opcional. Se não estiver definido, `filters` será tratado como *dimensões básicas*. Há quatro campos obrigatórios para `filters`: `organizationId`, `productId`, `siteId` e `locationId`.

- `organizationId` deve conter apenas um valor, mas ainda é uma matriz.
- `productId` pode conter um ou mais valores. Se for uma matriz vazia, todos os produtos serão retornados.
- `siteId` e `locationId` são usados para particionamento em Visibilidade de Estoque. Você pode especificar mais de um valor `siteId` e `locationId` em uma solicitação *Consulta disponível*. Na versão atual, você deve especificar os dois valores `siteId` e `locationId`.

Sugerimos que você use o parâmetro `groupByValues` para seguir a configuração para indexação. Para obter mais informações, consulte [Configuração de hierarquia de índice de produto](./inventory-visibility-configuration.md#index-configuration).

O parâmetro `returnNegative` controla se os resultados contêm entradas negativas.

> [!NOTE]
> Se você tiver habilitado o plano de alteração disponível e os recursos disponíveis para a promessa (ATP), a consulta também poderá incluir o parâmetro `QueryATP` booliano, que controla se os resultados da consulta incluirão informações de ATP. Para obter mais informações e exemplos, consulte [Agenda de alterações disponíveis e disponível para promessa de Visibilidade de Estoque](inventory-visibility-available-to-promise.md).

O exemplo a seguir mostra o conteúdo do corpo de exemplo. Isso mostra que você pode consultar o estoque disponível de vários locais (armazéns).

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "locationId": ["11","12","13"],
        "colorId": ["red"]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

O exemplo a seguir mostra como consultar todos os produtos em um site e local específicos.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "locationId": ["11"],
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Consultar usando o método get

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

Este é um exemplo de obtenção de URL. Essa solicitação get é exatamente igual ao exemplo de lançamento fornecido anteriormente.

```txt
/api/environment/{environmentId}/onhand?organizationId=SCM_IV&productId=iv_postman_product&siteId=iv_postman_site&locationId=iv_postman_location&colorId=red&groupBy=colorId,sizeId&returnNegative=true
```

## <a name="on-hand-exact-query"></a><a name="exact-query-with-post-method"></a>Consulta exata de estoque disponível

As consultas exatas sobre disponibilidade se assemelham às consultas sobre disponibilidade regulares, mas permitem especificar uma hierarquia de mapeamento entre um site e um local. Por exemplo, se você tiver os seguintes dois sites:

- Site 1, que é mapeado para o local A
- Site 2, que é mapeado para o local B

Para uma consulta disponível regular, se você especificar `"siteId": ["1","2"]` e `"locationId": ["A","B"]`, o Visibilidade de estoque consultará automaticamente o resultado para os seguintes sites e locais:

- Site 1, local A
- Site 1, local B
- Site 2, local A
- Site 2, local B

Como você pode ver, a consulta disponível regular não reconhece que o local A existe apenas no site 1 e o local B existe apenas no site 2. Portanto, ela faz consultas redundantes. Para acomodar esse mapeamento hierárquico, você pode usar uma consulta exata disponível e especificar os mapeamentos de localização no corpo da consulta. Nesse caso, você consultará e receberá resultados apenas para o site 1, local A, e para o site 2, local B.

### <a name="exact-query-by-using-the-post-method"></a><a name="exact-query-with-post-method"></a>Fazer uma consulta exata usando o método POST

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

Na parte do corpo desta solicitação, `dimensionDataSource` é um parâmetro opcional. Se não estiver definido, `dimensions` em `filters` será tratado como *dimensões básicas*. Há quatro campos obrigatórios para `filters`: `organizationId`, `productId`, `dimensions` e `values`.

- `organizationId` deve conter apenas um valor, mas ainda é uma matriz.
- `productId` pode conter um ou mais valores. Se for uma matriz vazia, todos os produtos serão retornados.
- Na matriz `dimensions`, os campos `siteId` e `locationId` são necessários, mas podem aparecer com outros elementos em qualquer ordem.
- O campo `values` pode conter uma ou mais tuplas de valores correspondendo a `dimensions`.

O campo `dimensions` em `filters` será adicionado automaticamente a `groupByValues`.

O parâmetro `returnNegative` controla se os resultados contêm entradas negativas.

O exemplo a seguir mostra o conteúdo do corpo de exemplo.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": ["iv_postman_product"],
        "dimensions": ["siteId", "locationId", "colorId"],
        "values" : [
            ["iv_postman_site", "iv_postman_location", "red"],
            ["iv_postman_site", "iv_postman_location", "blue"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

O exemplo a seguir mostra como consultar todos os produtos em vários sites e locais.

```json
{
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": [],
        "dimensions": ["siteId", "locationId"],
        "values" : [
            ["iv_postman_site_1", "iv_postman_location_1"],
            ["iv_postman_site_2", "iv_postman_location_2"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

## <a name="available-to-promise"></a>Disponível para promessa

É possível configurar a Visibilidade do Estoque para permitir que você agende alterações futuras disponíveis e calcule as quantidades do ATP. ATP é a quantidade de um item que está disponível e pode ser prometida a um cliente no próximo período. O uso do cálculo do ATP pode aumentar bastante o recurso de preenchimento de seu pedido. Para obter informações sobre como habilitar esse recurso e como interagir com a Visibilidade do Estoque por meio de sua API após a habilitação do recurso, consulte [Agenda de alterações disponíveis e disponível para promessa de Visibilidade de Estoque](inventory-visibility-available-to-promise.md#api-urls).

## <a name="allocation"></a>Alocação

As APIs relacionadas à alocação estão localizadas em [Alocação da Visibilidade de estoque](inventory-visibility-allocation.md#using-allocation-api).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
