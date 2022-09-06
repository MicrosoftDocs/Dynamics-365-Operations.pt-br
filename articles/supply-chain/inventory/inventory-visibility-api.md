---
title: APIs públicas do Inventory Visibility
description: Este artigo descreve as APIs públicas fornecidas pela visibilidade do Estoque.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 23f4c52b6d1d8c1af927a2c21455d6e24b24408a
ms.sourcegitcommit: 7bcaf00a3ae7e7794d55356085e46f65a6109176
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2022
ms.locfileid: "9357632"
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
| /api/environment/{environmentId}/onhand | Lançar | [Criar um evento de alteração disponível](#create-one-onhand-change-event) |
| /api/environment/{environmentId}/onhand/bulk | Lançar | [Criar vários eventos de alteração](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Lançar | [Definir/substituir quantidades disponíveis](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Lançar | [Criar um evento de reserva](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Lançar | [Criar vários eventos de reserva](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/changeschedule | Lançar | [Criar um alteração disponível programada](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/changeschedule/bulk | Lançar | [Criar várias alterações disponíveis programadas](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/indexquery | Lançar | [Consultar usando o método post](#query-with-post-method) |
| /api/environment/{environmentId}/onhand | Obter | [Consultar usando o método get](#query-with-get-method) |
| /api/environment/{environmentId}/allocation/allocate | Lançar | [Criar um evento alocar](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/unallocate | Lançar | [Criar um evento desalocar](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/reallocate | Lançar | [Criar um evento realocar](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/consume | Lançar | [Criar um evento consumir](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/query | Lançar | [Resultado da alocação da consulta](inventory-visibility-allocation.md#using-allocation-api) |

> [!NOTE]
> A parte {environmentId} do caminho é a ID do ambiente em Microsoft Dynamics Lifecycle Services (LCS).
> 
> A API em massa pode retornar um máximo de 512 registros para cada solicitação.

A Microsoft forneceu uma coleção de solicitações do *Postman* pronta para uso. Você pode importar essa coleção para o seu software *Postman* usando o seguinte link compartilhado: <https://www.getpostman.com/collections/ad8a1322f953f88d9a55>.

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>Localizar o ponto de extremidade de acordo com o seu ambiente do Lifecycle Services

O microsserviço da Visibilidade de Estoque é implantado no Microsoft Azure Service Fabric, em várias geografias e regiões. No momento, não há um ponto de extremidade central que possa redirecionar automaticamente sua solicitação para a geografia e a região correspondentes. Portanto, você deve compor as partes das informações em uma URL usando o seguinte padrão:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

O nome curto da região pode ser encontrado no ambiente do LCS (Microsoft Dynamics Lifecycle Services). A tabela a seguir lista as regiões disponíveis no momento.

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
| Sul do Brasil        | sbr               |
| Central Sul dos EUA    | scus              |

O número da ilha é onde seu ambiente do LCS é implantado no Service Fabric. No momento, não há como obter essas informações do lado do usuário.

A Microsoft criou uma IU (interface do usuário) no Power Apps para que você possa obter o ponto de extremidade completo do microsserviço. Para obter mais informações, consulte [Localizar o ponto de extremidade de serviço](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Autenticação

O token de segurança da plataforma é usado para chamar a API pública da Visibilidade de Estoque. Portanto, você deve gerar um token do _Azure Active Directory (Azure AD)_ usando a aplicação Azure AD. Você deve usar o token Azure AD para obter o _token de acesso_ do serviço de segurança.

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
   - O valor `context` deve ser a ID do ambiente LCS em que deseja implantar o suplemento.
   - Defina todos os demais valores conforme mostrado no exemplo.

1. Busque um token de acesso (`access_token`) ao enviar uma solicitação HTTP com as seguintes propriedades:

   - **URL:** `https://securityservice.operations365.dynamics.com/token`
   - **Método:** `POST`
   - **Cabeçalho HTTP:** inclua a versão da API. (A chave é `Api-Version`, e o valor é `1.0`.)
   - **Conteúdo do corpo:** inclua a solicitação JSON criada na etapa anterior.

   Você deverá receber um token de acesso (`access_token`) em resposta. Você deverá usar esse token como um token de portador para chamar a API da Visibilidade de Estoque. Veja aqui um exemplo.

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

| ID do campo | descrição |
|---|---|
| `id` | Uma ID exclusiva para o evento de alteração específico. Essa ID é usada para garantir que, se a comunicação com o serviço falhar durante o lançamento, o mesmo evento não será contado duas vezes no sistema caso seja enviado novamente. |
| `organizationId` | O identificador da organização vinculado ao evento. Esse valor é mapeado para uma ID da organização ou da área de dados no Supply Chain Management. |
| `productId` | O identificador do produto. |
| `quantities` | A quantidade pela qual a quantidade disponível deve ser alterada. Por exemplo, se 10 novos livros forem adicionados a uma prateleira, esse valor será `quantities:{ shelf:{ received: 10 }}`. Se três livros forem removidos da prateleira ou se forem vendidos, esse valor será `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | A fonte de dados das dimensões usadas no evento e na consulta de alteração de lançamento. Se você especificar a fonte de dados, poderá usar as dimensões personalizadas da fonte de dados especificada. A Visibilidade de Estoque pode usar a configuração da dimensão para mapear as dimensões personalizadas para as dimensões padrão gerais. Se nenhum valor de `dimensionDataSource` for especificado, você só poderá usar as [dimensões base](inventory-visibility-configuration.md#data-source-configuration-dimension) gerais em suas consultas. |
| `dimensions` | Um par de chave-valor dinâmico. Os valores são mapeados para algumas das dimensões no Supply Chain Management. No entanto, você também pode adicionar dimensões personalizadas (por exemplo, _Origem_) para indicar se o evento provém do Supply Chain Management ou de um sistema externo. |

> [!NOTE]
> Os parâmetros `SiteId` e `LocationId` e constroem a [configuração da partição](inventory-visibility-configuration.md#partition-configuration). Portanto, você deve especificá-los nas dimensões ao criar eventos de alteração disponível, definir ou substituir quantidades disponíveis ou criar eventos de reserva.

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

O exemplo a seguir mostra o conteúdo do corpo de exemplo. Neste exemplo, você lança um evento de alteração para o produto *Camiseta*. Esse evento é do sistema de PDV (ponto de venda) e o cliente devolveu uma camiseta vermelha para sua loja. Esse evento aumentará a quantidade do produto *Camiseta* em 1.

```json
{
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "PosMachineId": "0001",
        "ColorId": "Red"
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
    "id": "123456",
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Criar vários eventos de alteração

Essa API pode criar vários registros ao mesmo tempo. As únicas diferenças entre essa API e a [API de evento único ](#create-one-onhand-change-event) são os valores de `Path` e `Body`. Para essa API, `Body` fornece uma matriz de registros. O número máximo de registros é 512, o que significa que a API em massa de alteração disponível pode oferecer suporte a até 512 eventos de alteração de cada vez.

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
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "Pants",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Definir/substituir quantidades disponíveis

A API _Definir disponível_ substitui os dados atuais do produto especificado.

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
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
             "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId": "0001"
        },
        "quantities": {
            "pos": {
                "inbound": 1
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Criar eventos de reserva

Para usar a API *Reservar*, você deverá abrir o recurso de reserva e concluir a configuração da reserva. Para obter mais informações, consulte [Configuração da reserva (opcional)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Criar um evento de reserva

Uma reserva pode ser feita com diferentes configurações da fonte de dados. Para configurar esse tipo de reserva, especifique primeiro a fonte de dados no parâmetro `dimensionDataSource`. Depois disso, no parâmetro `dimensions`, especifique as dimensões de acordo com as configurações de dimensão na fonte de dados de destino.

Ao chamar a API de reserva, você pode controlar a validação da reserva especificando o parâmetro booliano `ifCheckAvailForReserv` no corpo da solicitação. Um valor `True` significa que a validação é necessária, enquanto um valor `False` significa que a validação não é necessária. O valor padrão é `True`.

Se você deseja cancelar uma reserva ou cancelar a reserva de quantidades de estoque especificadas, defina a quantidade como um valor negativo e defina o parâmetro `ifCheckAvailForReserv` como `False` para ignorar a validação.

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
    "organizationId": "usmf",
    "productId": "T-shirt",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softreservordered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    }
}
```

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Criar vários eventos de reserva

Essa API é uma versão em massa da [API de evento único](#create-one-reservation-event).

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

## <a name="query-on-hand"></a>Consultar disponíveis

Use a API _Consultar disponíveis_ para buscar dados de estoque disponível atuais para seus produtos. No momento, a API oferece suporte à consulta de até 100 itens individuais por valor de `ProductID`. Diversos valores `SiteID` e `LocationID` também podem ser especificados em cada consulta. O limite máximo é definido como `NumOf(SiteID) * NumOf(LocationID) <= 100`.

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

O parâmetro `groupByValues` deve seguir a configuração para indexação. Para obter mais informações, consulte [Configuração de hierarquia de índice de produto](./inventory-visibility-configuration.md#index-configuration).

O parâmetro `returnNegative` controla se os resultados contêm entradas negativas.

> [!NOTE]
> Se você tiver habilitado o plano de alteração disponível e os recursos disponíveis para a promessa (ATP), a consulta também poderá incluir o parâmetro `QueryATP` booliano, que controla se os resultados da consulta incluirão informações de ATP. Para obter mais informações e exemplos, consulte [Agenda de alterações disponíveis e disponível para promessa de Visibilidade de Estoque](inventory-visibility-available-to-promise.md).

O exemplo a seguir mostra o conteúdo do corpo de exemplo.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "LocationId": ["11"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
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
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
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
/api/environment/{environmentId}/onhand?organizationId=usmf&productId=T-shirt&SiteId=1&LocationId=11&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

## <a name="available-to-promise"></a>Disponível para promessa

É possível configurar a Visibilidade do Estoque para permitir que você agende alterações futuras disponíveis e calcule as quantidades do ATP. ATP é a quantidade de um item que está disponível e pode ser prometida a um cliente no próximo período. O uso do cálculo do ATP pode aumentar bastante o recurso de preenchimento de seu pedido. Para obter informações sobre como habilitar esse recurso e como interagir com a Visibilidade do Estoque por meio de sua API após a habilitação do recurso, consulte [Agenda de alterações disponíveis e disponível para promessa de Visibilidade de Estoque](inventory-visibility-available-to-promise.md#api-urls).

## <a name="allocation"></a>Alocação

As APIs relacionadas à alocação estão localizadas em [Alocação da Visibilidade de estoque](inventory-visibility-allocation.md#using-allocation-api).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
