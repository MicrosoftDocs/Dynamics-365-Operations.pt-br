---
title: Suplemento Visibilidade de Estoque
description: Este tópico descreve como instalar e configurar o Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management.
author: sherry-zheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e6f7e0a3978bbf7e520f8cbcfd27c4cfe507777
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114661"
---
# <a name="inventory-visibility-add-in"></a>Suplemento Visibilidade de Estoque

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

O Suplemento Visibilidade de Estoque é um microsserviço independente e altamente escalonável que permite o rastreamento de estoque disponível em tempo real, oferecendo, assim, uma visão global da visibilidade de estoque.

Todas as informações relacionadas ao estoque disponível são exportadas para o serviço quase em tempo real por meio de uma integração SQL de nível baixo. Os sistemas externos acessam o serviço por meio de APIs RESTful para consultar informações disponíveis sobre determinados conjuntos de dimensões, recuperando, dessa forma, uma lista de posições disponíveis.

A Visibilidade de Estoque é um microsserviço criado no Microsoft Dataverse, o que significa que você pode estendê-lo criando Power Apps e aplicando o Power BI para fornecer funcionalidade personalizada para atender aos seus requisitos de negócios. Também é possível atualizar o índice para fazer consultas de estoque.

A Visibilidade de Estoque fornece opções de configuração que permitem a integração com vários sistemas de terceiros. Ela oferece suporte à dimensão de estoque padronizada, à extensibilidade personalizada e a quantidades calculadas padronizadas e configuráveis.

Este tópico descreve como instalar e configurar o Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management e como usar sua interface de programação de aplicativo (API).

## <a name="install-the-inventory-visibility-add-in"></a>Instalar o Suplemento Visibilidade de Estoque

É necessário instalar o Suplemento Visibilidade de Estoque usando o Microsoft Dynamics Lifecycle Services (LCS). O LCS é um portal de colaboração que fornece um ambiente e um conjunto de serviços regularmente atualizados que ajudam a gerenciar o ciclo de vida dos seus aplicativos do Dynamics 365 Finance and Operations.

Para obter mais informações, consulte [Recursos do Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).

### <a name="prerequisites"></a>Pré-requisitos

Antes de instalar o Suplemento Visibilidade de Estoque, você deve fazer o seguinte:

- Obter um projeto de implementação do LCS com, pelo menos, um ambiente implantado.
- Gerar as chaves beta da sua oferta no LCS.
- Habilitar as chaves beta da sua oferta para seu usuário no LCS.
- Entrar em contato com a equipe do produto Visibilidade de Estoque da Microsoft e fornecer uma ID de ambiente onde você deseja implantar o Suplemento Visibilidade de Estoque.

Caso tenha alguma dúvida sobre esses pré-requisitos, entre em contato com a equipe do produto Visibilidade de Estoque.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Instalar o suplemento

Para instalar o Suplemento Visibilidade de Estoque, faça o seguinte:

1. Entre no portal [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Na home page, selecione o projeto no qual seu ambiente foi implantado.
1. Na página do projeto, selecione o ambiente no qual você deseja instalar o suplemento.
1. Na página do ambiente, role para baixo até ver a seção **Suplementos de ambiente**. Se a seção não estiver visível, verifique se as chaves beta dos pré-requisitos foram totalmente processadas.
1. Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.
    ![A página do ambiente no LCS](media/inventory-visibility-environment.png "A página do ambiente no LCS")
1. Selecione o link **Instalar um novo suplemento**. Uma lista dos suplementos disponíveis será aberta.
1. Selecione **Serviço de estoque** na lista. (Observe que agora isso pode estar listado como **Suplemento Visibilidade de Estoque para Dynamics 365 Supply Chain Management**.)
1. Insira valores para os seguintes campos no seu ambiente:

    - **ID de aplicativo do AAD**
    - **ID de locatário do AAD**

    ![Página de configuração do suplemento](media/inventory-visibility-setup.png "Página de configuração do suplemento")

1. Concorde com os termos e condições, marcando a caixa de seleção **Termos e condições**.
1. Selecione **Instalar**. O status do suplemento será mostrado como **Instalando**. Após a conclusão, atualize a página para ver a alteração do status para **Instalado**.

### <a name="get-a-security-service-token"></a>Obter um token de serviço de segurança

Obtenha um token de serviço de segurança da seguinte forma:

1. Faça login no Portal do Azure e use-o para localizar `clientId` e `clientSecret` para o aplicativo Supply Chain Management.
1. Busque um token do Azure Active Directory (`aadToken`) enviando uma solicitação HTTP com as seguintes propriedades:
    - **URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Método** - `GET`
    - **Conteúdo do corpo (dados de formulário)**:

        | key | valor |
        | --- | --- |
        | client_id | ${aadAppId} |
        | client_secret | ${aadAppSecret} |
        | grant_type | client_credentials |
        | resource | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
1. Você receberá um `aadToken` em resposta, que se parece com o seguinte exemplo.

    ```json
    {
    "token_type": "Bearer",
    "expires_in": "3599",
    "ext_expires_in": "3599",
    "expires_on": "1610466645",
    "not_before": "1610462745",
    "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
    "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Formule uma solicitação JSON que se parece com a seguinte:

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Onde:
    - O valor `client_assertion` deve ser o `aadToken` que recebeu na etapa anterior.
    - O valor de `context` deve ser a ID do ambiente em que deseja implantar o suplemento.
    - Defina todos os demais valores conforme exibido no exemplo.

1. Envie uma solicitação HTTP com as seguintes propriedades:
    - **URL** - `https://securityservice.operations365.dynamics.com/token`
    - **Método** - `POST`
    - **Cabeçalho HTTP** – inclua a versão da API (a chave é `Api-Version` e o valor é `1.0`)
    - **Conteúdo do corpo** – inclua a solicitação JSON criada na etapa anterior.

1. Você receberá um `access_token` em resposta. É disso que você precisará como um token de portador para chamar a API da Visibilidade de Estoque. Veja aqui um exemplo.

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a>Desinstalar o suplemento

Para desinstalar o suplemento, selecione **Desinstalar**. Atualize o LCS e o Suplemento Visibilidade de Estoque será removido. O processo de desinstalação removerá o registro do suplemento e também iniciará um trabalho para limpar todos os dados comerciais armazenados no serviço.

## <a name="inventory-visibility-add-in-public-api"></a>API pública do Suplemento Visibilidade de Estoque

A API REST pública do Suplemento Visibilidade de Estoque apresenta vários pontos de extremidade de integração específicos. Ela oferece suporte a três tipos de interação principais:

- Lançar alterações de disponibilidade no suplemento a partir de um sistema externo.
- Consultar as quantidades disponíveis no momento a partir de um sistema externo.
- Sincronização automática com a disponibilidade do Supply Chain Management.

A sincronização automática não faz parte da API pública, mas é tratada em segundo plano para ambientes que habilitaram o Suplemento Visibilidade de Estoque.

### <a name="authentication"></a>Autenticação

O token de segurança da plataforma é usado para chamar o Suplemento Visibilidade de Estoque, portanto, você deve gerar um token do Azure Active Directory usando seu aplicativo do Azure Active Directory.

Para obter mais informações sobre como receber o token de segurança, consulte [Instalar o Suplemento Visibilidade de Estoque](#install-add-in).

### <a name="configure-the-inventory-visibility-api"></a>Configurar a API da Visibilidade de Estoque

Antes de usar o serviço, você deve concluir as configurações descritas nas subseções a seguir. A configuração pode variar com base nos detalhes do seu ambiente. Ela inclui principalmente quatro partes:

- [Particionamento](#partitioning)
- [Configurações de dimensões](#dimension-configurations)
- [Indexando](#indexing)
- [Medida personalizada](#custom-measurement)

#### <a name="partitioning"></a>Particionamento

O particionamento pode influenciar significativamente o desempenho da API da Visibilidade de Estoque. É uma boa ideia definir um esquema que permita pequenos agrupamentos de dados e, ao mesmo tempo, permita consultas de dados significativas.

A `organizationId` (`dataAreaId` no Supply Chain Management) sempre fará parte do particionamento e, por padrão, a Visibilidade de Estoque é configurada para particionar por dimensões como *Local + Localização*. Isso significa que o serviço sempre deve ser consultado com essas dimensões definidas nos filtros.

> [!NOTE]
> *Local* e *Localização* são duas dimensões padrão gerais na Visibilidade de Estoque. No Supply Chain Management, essas dimensões são chamadas de *Local* (`InventSiteId`) e *Depósito* (`InventLocationId`)

### <a name="dimension-configurations"></a>Configurações de dimensões

A Visibilidade de Estoque fornecerá uma lista de dimensões padrão gerais para habilitar a integração de sistemas de várias fontes.

A tabela a seguir lista as dimensões de estoque que serão os nomes de dimensão padrão na Visibilidade de Estoque.

| Tipo de dimensão | Nome da dimensão |
|---|---|
| Produto | `ColorId` |
| Produto | `SizeId` |
| Produto | `StyleId` |
| Produto | `ConfigId` |
| Rastreamento | `BatchId` |
| Rastreamento | `SerialId` |
| Localização | `LocationId` |
| Localização | `SiteId` |
| Status do Estoque | `StatusId` |
| Específico do Depósito | `WMSLocationId` |
| Específico do Depósito | `WMSPalletId` |
| Específico do Depósito | `LicensePlateId` |

> [!NOTE]
> O tipo de dimensão listado na tabela anterior é somente para referência. Não é necessário definir o tipo de dimensão na Visibilidade de Estoque.

Se uma dimensão personalizada existir e precisar fluir para um valor padrão quando consumida pela Visibilidade de Estoque, você poderá configurar o nome **Dimensão personalizada** na Visibilidade de Estoque.

Os sistemas externos acessam a Visibilidade de Estoque por meio de APIs RESTful que habilitam informações de disponibilidade sobre determinados conjuntos de dimensões a serem consultadas. Para a integração, a Visibilidade de Estoque permite configurar a *fonte de dados do canal externo* e a dimensão de origem para as *dimensões de destino* na Visibilidade de Estoque.

As dimensões de destino devem ser uma das seguintes opções:

- Dimensões padrão na Visibilidade de Estoque
- Dimensões personalizadas

A finalidade da configuração de dimensões é padronizar a integração de vários sistemas para a consulta em dimensões e o evento de lançamento com dimensões.

#### <a name="indexing"></a>Indexando

Na maioria das vezes, a consulta de estoque disponível não só estará no nível "total" mais alto, mas talvez você queira ver resultados agregados com base nas dimensões de estoque.

A Visibilidade de Estoque fornece flexibilidade, permitindo que você configure os índices, que se baseiam na dimensão ou na combinação das dimensões.

> [!NOTE]
> No momento, só é possível configurar índices para, no máximo, cinco. É necessário considerar cuidadosamente qual dimensão ou combinação de dimensões você usará antes da implementação para garantir que ela atenderá às suas necessidades comerciais. Por exemplo, se você quiser consultar produtos da seguinte maneira:

- Consultar o produto agregado disponível por meio das dimensões *Cor* e *Tamanho*.
- Em alguns casos, você só deseja consultar o produto no total.

Você teria dois índices definidos da seguinte forma:

- `["ColorId", "SizeId"]`
- `[]`

O colchete vazio agregará com base na ID do produto na partição.

A indexação define como você pode agrupar os resultados com base na configuração de consulta `groupBy`. Nesse caso, se você não definir nenhum valor `groupBy`, obterá totais por `productid`. Caso contrário, se você definir `groupBy` como `groupBy=ColorId&groupBy=SizeId`, receberá várias linhas retornadas, com base nas diferentes combinações de cor e tamanho no sistema.

Você pode colocar os critérios de consulta no corpo da solicitação.

Veja uma consulta de exemplo no produto com combinação de cor e tamanho.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a>Medida personalizada

As quantidades de medidas padrão estão vinculadas ao Supply Chain Management, mas talvez você queira ter uma quantidade que seja composta por uma combinação das medidas padrão. Para isso, você pode ter uma configuração de quantidades personalizadas, que será adicionada à saída das consultas de disponibilidade.

A funcionalidade simplesmente permite definir um conjunto de medidas que será adicionado e/ou um conjunto de medidas que será subtraído para formar a medida personalizada.

Por exemplo, com a seguinte condição de consulta, você configurará a quantidade de medidas personalizadas como `MyCustomAvailableforReservation` para ser consumida pelo sistema de consumo.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| Sistema de consumo | Medidas calculadas | Fonte de dados | Modificador | Tipo de cálculo do modificador |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Subtração |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Subtração |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Adição |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Subtração |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Subtração |

Com isso, a consulta na quantidade de medidas personalizadas retornará a seguinte saída.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

A saída `MyCustomAvailableforReservation` se baseia na configuração de cálculo nas medidas personalizadas como:  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Lançar alterações de disponibilidade

A URL exata na qual o evento será lançado dependerá da sua região geográfica. Ela terá a forma:

`https://{serviceURL}/api/environment/{environmentId}/onhand`

Quando autenticada, essa URL pode ser usada junto com o método HTTP `POST` para enviar eventos de alteração de disponibilidade para o serviço.

Um cabeçalho especial é usado para a comunicação com os serviços do Dynamics 365 por meio de solicitações HTTP, indicando a ID de ambiente da instância do Supply Chain Management à qual os dados estão vinculados. Por exemplo:

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Exemplo de consulta de lançamento de alterações de disponibilidade 1

Este exemplo mostra um cenário no qual você definirá a configuração de dimensões no Power Apps.

Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas. O sistema converterá automaticamente as dimensões personalizadas em dimensões base.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Exemplo de consulta de lançamento de alterações de disponibilidade 2

Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base. Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource` é nulo, vazio ou um espaço em branco.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>Propriedades de campo do documento JSON

Os campos dos exemplos de consulta JSON fornecidos anteriormente têm as propriedades listadas na tabela a seguir.

| ID do campo | descrição |
|---|---|
| `id` | Uma ID exclusiva para o evento de alteração específico. Essa ID é usada para garantir que, se a comunicação com o serviço falhar durante o lançamento, o reenvio do evento não resultará no mesmo evento sendo contado duas vezes no sistema. |
| `organizationId` | O identificador da organização vinculada ao evento. Isso é mapeado para as IDs de áreas de dados ou organizações do Supply Chain Management. |
| `productId` | O identificador do produto em questão. |
| `quantity` | A quantidade pela qual a disponibilidade precisa ser alterada. Se, por exemplo, 10 novos bagels forem adicionados a uma prateleira, esse valor será 10. Se 3 bagels forem removidos da prateleira ou vendidos, esse valor será -3. |
| `dimensionDataSource` | A fonte de dados das dimensões usadas no evento e na consulta de alteração de lançamento. Se você especificar a fonte de dados, poderá usar as dimensões personalizadas da fonte de dados especificada. Com a configuração de dimensões, a Visibilidade de Estoque pode mapear as dimensões personalizadas para as dimensões padrão gerais. Se a `dimensionDataSource` não estiver especificada, você só poderá usar as dimensões padrão gerais nas suas consultas.   |
| `dimensions` | Um recipiente dinâmico de pares de chave/valor. Eles serão mapeados para algumas das dimensões no Supply Chain Management, mas você também pode adicionar dimensões personalizadas (como *Origem*) que podem indicar se o evento é proveniente do Supply Chain Management ou de um sistema externo. |

### <a name="querying-current-on-hand"></a>Consultar a disponibilidade atual

O ponto de extremidade para consultar a disponibilidade atual terá uma URL semelhante:

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

Ela será consultada com o método HTTP `POST`.

#### <a name="current-on-hand-query-example-1"></a>Exemplo de consulta da disponibilidade atual 1

Este exemplo mostra um cenário no qual você já concluiu a configuração de dimensões no Power Apps.

Use a seguinte consulta para configurar o mapeamento de dimensões no Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Agora, você pode especificar a `dimensionDataSource` e usar dimensões personalizadas nas suas consultas. O sistema converterá automaticamente as dimensões personalizadas em dimensões base. Você pode especificar a `DimensionDataSource` em `filters` e especificar dimensões personalizadas em `filters` e `groupByValues`. O sistema converterá automaticamente as dimensões personalizadas em dimensões base.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Exemplo de consulta da disponibilidade atual 2

Este exemplo mostra um cenário em que não há mapeamentos definidos para a configuração de dimensões no Power Apps, portanto, o lançamento também deve usar as dimensões base. Todas as dimensões devem ser dimensões base quando o campo `dimensionDataSource`, em `filters`, é nulo, vazio ou um espaço em branco.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Exemplo de retorno de resultado

As consultas mostradas nos exemplos anteriores poderiam retornar um resultado como este.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Observe que os campos de quantidades estão estruturados como um dicionário de medidas e seus valores associados.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]