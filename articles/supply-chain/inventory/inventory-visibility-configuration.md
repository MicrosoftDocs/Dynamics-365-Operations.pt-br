---
title: Configuração de Visibilidade de Estoque
description: Este tópico descreve como configurar o Visibilidade de Estoque.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 92e42b22d424ab80303d771f760cfcf0599b9f4c
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345024"
---
# <a name="inventory-visibility-configuration"></a>Configuração de Visibilidade de Estoque

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tópico descreve como configurar o Visibilidade de Estoque.

## <a name="introduction"></a><a name="introduction"></a>Introdução

Antes de começar a trabalhar com o Visibilidade de Estoque, você deve concluir a seguinte configuração, conforme descrito neste tópico:

- [Configuração de fonte de dados](#data-source-configuration)
- [Configuração de partição](#partition-configuration)
- [Configuração de hierarquia de índice de produtos](#index-configuration)
- [Configuração de reserva (opcional)](#reservation-configuration)
- [Exemplo de configuração padrão](#default-configuration-sample)

> [!NOTE]
> Você pode exibir e editar as configurações de Visibilidade de Estoque no [Microsoft Power Apps](./inventory-visibility-power-platform.md#configuration). Depois que a configuração for concluída, selecione **Atualizar Configuração** no aplicativo.

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Configuração de fonte de dados

A fonte de dados representa o sistema de onde vêm seus dados. Alguns exemplos são `fno` (que significa "aplicativos do Dynamics 365 Finance and Operations") e `pos` (que significa "ponto de venda").

A configuração da fonte de dados inclui as seguintes partes:

- Dimensão (mapeamento de dimensão)
- Medida física
- Medida calculada

> [!NOTE]
> A fonte de dados `fno` é reservada para o Dynamics 365 Supply Chain Management.

### <a name="dimension-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensão (mapeamento de dimensão)

O objetivo da configuração da dimensão é padronizar a integração de vários sistemas para postar eventos e consultas, com base nas combinações de dimensão.

O Visibilidade de Estoque dá suporte às dimensões básicas gerais a seguir.

| Tipo de dimensão | Dimensão base |
|---|---|
| Produto | `ColorId` |
| Produto | `SizeId` |
| Produto | `StyleId` |
| Produto | `ConfigId` |
| Rastreamento | `BatchId` |
| Rastreamento | `SerialId` |
| Localização | `LocationId` |
| Localização | `SiteId` |
| Status do estoque | `StatusId` |
| Específico de depósito | `WMSLocationId` |
| Específico de depósito | `WMSPalletId` |
| Específico de depósito | `LicensePlateId` |
| Diversos | `VersionId` |
| Estoque (personalizado) | `InventDimension1` a `InventDimension12` |
| Ramal | `ExtendedDimension1` a `ExtendedDimension8` |

> [!NOTE]
> Os tipos de dimensão listados na tabela anterior são apenas para referência. Você não precisa defini-los no Visibilidade de Estoque.
>
> As dimensões de estoque (personalizadas) podem ser reservadas para o Supply Chain Management. Nesse caso, você pode usar as dimensões estendidas.

Os sistemas externos podem acessar o Visibilidade de Estoque por meio de suas APIs RESTful. Para a integração, o Visibilidade de Estoque permite que você configure a _fonte de dados externa_ e o mapeamento das _dimensões externas_ para as _dimensões base_. Aqui está um exemplo de uma tabela de mapeamento de dimensão.

| Dimensão externa | Dimensão base |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

Configurando um mapeamento de dimensão, você pode enviar as dimensões externas diretamente para o Visibilidade de Estoque. O Visibilidade de Estoque converterá automaticamente as dimensões externas em dimensões base.

### <a name="physical-measures"></a>Medidas físicas

As medidas físicas modificam a quantidade e refletem o status do estoque. Você pode definir suas próprias medidas físicas, com base em seus requisitos.

O Visibilidade de Estoque fornece uma lista de medidas físicas padrão que estão vinculadas ao Supply Chain Management (a fonte de dados `fno`). A tabela a seguir fornece um exemplo de medidas físicas.

| Nome da medida física | descrição |
|---|---|
| `NotSpecified` | Não especificado |
| `Arrived` | Admitido |
| `AvailOrdered` | Disponível e solicitada |
| `AvailPhysical` | Quantidade física disponível |
| `Deducted` | Deduzido |
| `OnOrder` | OnOrder |
| `Ordered` | Encomenda feita |
| `PhysicalInvent` | Estoque físico |
| `Picked` | Separada |
| `PostedQty` | Quantidade lançada |
| `QuotationIssue` | Saída de cotação |
| `QuotationReceipt` | Recebimento de cotação |
| `Received` | Recebidos |
| `Registered` | Registrado |
| `ReservOrdered` | Ordem reservada |
| `ReservPhysical` | Reserva física |

### <a name="calculated-measures"></a><a name="data-source-configuration-calculated-measure"></a>Medidas calculadas

As medidas calculadas fornecem uma fórmula de cálculo personalizada que consiste em uma combinação de medidas físicas. Essa funcionalidade permite definir um conjunto de medidas físicas que serão adicionadas e/ou um conjunto de medidas físicas que serão subtraídas para formar a medida personalizada.

Por exemplo, você tem o resultado de consulta a seguir.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

Em seguida, você configura uma medida calculada chamada `MyCustomAvailableforReservation`, conforme mostrado na tabela a seguir. Essa medida calculada será consumida pelo sistema de consumo.

| Sistema de consumo | Medida calculada | Fonte de dados | Medida física | Tipo de cálculo |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

Quando essa fórmula de cálculo for usada, o novo resultado da consulta incluirá a medida personalizada.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
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

A saída `MyCustomAvailableforReservation`, com base na configuração de cálculo nas medidas personalizadas, é 100 + 50 + 80 + 90 + 30 – 10 – 20 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Configuração de partição

A configuração da partição consiste em uma combinação de dimensões básicas. Ela define o padrão de distribuição de dados. As operações de dados na mesma partição dão suporte a alto desempenho e não custam muito. Portanto, bons padrões de partição podem contribuir com benefícios significativos.

O Visibilidade de Estoque fornece a configuração de partição padrão a seguir.

| Dimensão base | Hierarquia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

> [!NOTE]
> A configuração da partição padrão é apenas para referência. Você não precisa defini-la no Visibilidade de Estoque. No momento, não há suporte para a atualização da configuração da partição.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Configuração de hierarquia de índice de produtos

Na maioria das vezes, a consulta de estoque disponível não será apenas no nível "total" mais alto. Em vez disso, talvez você também queira ver os resultados agregados com base nas dimensões do estoque.

O Visibilidade de Estoque fornece flexibilidade, permitindo que você configure _índices_. Esses índices são baseados em uma dimensão ou combinação de dimensões. Um índice consiste em um *número do conjunto*, uma *dimensão* e uma *hierarquia*, conforme definido na tabela a seguir.

| Organização | descrição |
|---|---|
| Número do conjunto | As dimensões que pertencerem ao mesmo conjunto (índice) serão agrupadas, e o mesmo número de conjunto será atribuído a elas. |
| Dimensão | Dimensões básicas nas quais o resultado da consulta é agregado. |
| Hierarquia | A hierarquia é usada para definir as combinações de dimensão com suporte que podem ser consultadas. Por exemplo, você configura um conjunto de dimensões que tem uma sequência de hierarquia de `(ColorId, SizeId, StyleId)`. Nesse caso, o sistema dá suporte a consultas em quatro combinações de dimensão. A primeira combinação está vazia, a segunda é `(ColorId)`, a terceira é `(ColorId, SizeId)` e a quarta é `(ColorId, SizeId, StyleId)`. Não há suporte para as outras combinações. Para obter mais informações, consulte o exemplo a seguir. |

### <a name="example"></a>Exemplo

Esta seção fornece um exemplo que mostra o funcionamento da hierarquia.

Você tem os itens a seguir em seu estoque.

| Item  | ColorId | SizeId | StyleId | Quantidade |
|---|---|---|---|---|
| Camiseta | Preto | Pequeno | Largo | 1 |
| Camiseta | Preto | Pequeno | Regular | 2 |
| Camiseta | Preto | Grande | Largo | 3 |
| Camiseta | Preto | Grande | Regular | 4 |
| Camiseta | Vermelho | Pequeno | Largo | 5 |
| Camiseta | Vermelho | Pequeno | Regular | 6 |
| Camiseta | Vermelho | Grande | Regular | 7 |

Aqui está o índice.

| Número do Conjunto | Dimensão | Hierarquia |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

O índice permite consultar o estoque disponível das seguintes maneiras:

- `()` – agrupado por todos

    - Camiseta, 28

- `(ColorId)` – agrupado por `ColorId`

    - Camiseta, Preta, 10
    - Camiseta, Vermelha, 18

- `(ColorId, SizeId)` – agrupado pela combinação de `ColorId` e `SizeId`

    - Camiseta, Preta, Pequena, 3
    - Camiseta, Preta, Grande, 7
    - Camiseta, Vermelha, Pequena, 11
    - Camiseta, Vermelha, Grande, 7

- `(ColorId, SizeId, StyleId)` – agrupado pela combinação de `ColorId`, `SizeId` e `StyleId`

    - Camiseta, Preta, Pequena, Larga, 1
    - Camiseta, Preta, Pequena, Regular, 2
    - Camiseta, Preta, Grande, Larga, 3
    - Camiseta, Preta, Grande, Regular, 4
    - Camiseta, Vermelha, Pequena, Larga, 5
    - Camiseta, Vermelha, Pequena, Regular, 6
    - Camiseta, Vermelha, Grande, Regular, 7

> [!NOTE]
> As dimensões base definidas na configuração da partição não devem ser definidas nas configurações de índice.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Configuração de reserva (opcional)

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

A configuração da reserva será necessária se você desejar usar o recurso de reserva flexível. A configuração consiste em duas partes fundamentais:

- Mapeamento de reserva flexível
- Hierarquia de reserva flexível

### <a name="soft-reservation-mapping"></a>Mapeamento de reserva flexível

Ao fazer uma reserva, você pode querer saber se o estoque em mãos está disponível para reserva. A validação está ligada a uma medida calculada que representa uma fórmula de cálculo de uma combinação de medidas físicas.

Por exemplo, uma medida de reserva é baseada na medida física `SoftReservOrdered` da fonte de dados `iv` (Visibilidade de Estoque). Nesse caso, você pode configurar a medida calculada `AvailableToReserve` da fonte de dados `iv` conforme mostrado aqui.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `AvailPhysical` |
| Adição | `pos` | `Inbound` |
| Subtração | `pos` | `Outbound` |
| Subtração | `iv` | `SoftReservOrdered` |

Em seguida, configure um mapeamento de reserva flexível para fornecer um mapeamento da medida de reserva `SoftReservOrdered` para a medida calculada `AvailableToReserve`.

| Fonte de dados de medida física | Medida física | Disponível para a fonte de dados de reserva | Disponível para medida calculada da reserva |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

Agora, quando você fizer a reserva em `SoftReservOrdered`, o Visibilidade de Estoque encontrará automaticamente `AvailableToReserve` e sua fórmula de cálculo relacionada para fazer a validação da reserva.

Por exemplo, você tem o estoque a seguir disponível no Visibilidade de Estoque.

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

Nesse caso, o seguinte cálculo se aplica:

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

Portanto, se você tentar fazer reservas em `iv.SoftReservOrdered` e a quantidade for menor ou igual a `AvailableToReserve` (10), você poderá fazer a reserva.

### <a name="soft-reservation-hierarchy"></a>Hierarquia de reserva flexível

A hierarquia de reservas descreve a sequência de dimensões que deve ser especificada quando as reservas são feitas. Ele funciona da mesma forma que a hierarquia de índice do produto funciona para consultas disponíveis.

A hierarquia de reserva é independente da hierarquia de índice de produto. Essa independência permite implementar o gerenciamento de categorias, no qual os usuários podem dividir as dimensões em detalhes para especificar os requisitos para fazer reservas mais precisas.

Aqui está um exemplo de uma hierarquia de reserva flexível.

| Dimensão base | Hierarquia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

Nesse exemplo, você pode fazer reserva nas seguintes sequências de dimensão:

- `()` – nenhuma dimensão é especificada.
- `(SiteId)`
- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Uma sequência de dimensão válida deve seguir estritamente a hierarquia de reserva, dimensão por dimensão. Por exemplo, a sequência de hierarquia `(SiteId, LocationId, SizeId)` não é válida porque `ColorId` está ausente.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Exemplo de configuração padrão

Durante seu estágio de inicialização, o Visibilidade de Estoque define uma configuração padrão. Você pode modificar a configuração conforme necessário.

### <a name="data-source-configuration"></a>Configuração de fonte de dados

#### <a name="configuration-of-the-iv-data-source"></a>Configuração da fonte de dados iv

Esta seção descreve como a fonte de dados `iv` é configurada.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Medidas físicas configuradas para a fonte de dados iv

As seguintes medidas físicas são configuradas para a fonte de dados `iv`:

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>Medida calculada de OrderedTotal

A medida calculada `OrderedTotal` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `Ordered` |
| Adição | `fno` | `Arrived` |
| Adição | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>Medida calculada OnHand

A medida calculada `OnHand` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `PhysicalInvent` |
| Adição | `iom` | `OnHand` |
| Adição | `erp` | `Unrestricted` |
| Adição | `erp` | `QualityInspection` |
| Adição | `pos` | `PosInbound` |
| Subtração | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>Medida calculada ReservedTotal

A medida calculada `ReservedTotal` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `ReservPhysical` |
| Adição | `fno` | `ReservOrdered` |
| Adição | `iv` | `SoftReservPhysical` |
| Adição | `iv` | `SoftReservOrdered` |
| Adição | `iv` | `ReservPhysical` |
| Adição | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>Medida calculada SoftReserved

A medida calculada `SoftReserved` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `iv` | `SoftReservPhysical` |
| Adição | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>Medida calculada HardReserved

A medida calculada `HardReserved` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `ReservPhysical` |
| Adição | `fno` | `ReservOrdered` |
| Adição | `iv` | `ReservPhysical` |
| Adição | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>Medida calculada OpenOrder

A medida calculada `OpenOrder` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `OnOrder` |
| Adição | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>Medida calculada OnHandAvailable

A medida calculada `OnHandAvailable` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `PhysicalInvent` |
| Adição | `iom` | `OnHand` |
| Adição | `erp` | `Unrestricted` |
| Adição | `erp` | `QualityInspection` |
| Adição | `pos` | `PosInbound` |
| Subtração | `fno` | `ReservPhysical` |
| Subtração | `iv` | `SoftReservPhysical` |
| Subtração | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>Medida calculada AvailableToReserve

A medida calculada `AvailableToReserve` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `PhysicalInvent` |
| Adição | `iom` | `OnHand` |
| Adição | `erp` | `Unrestricted` |
| Adição | `erp` | `QualityInspection` |
| Adição | `pos` | `PosInbound` |
| Adição | `fno` | `Ordered` |
| Adição | `fno` | `Arrived` |
| Adição | `iv` | `Ordered` |
| Subtração | `fno` | `ReservPhysical` |
| Subtração | `fno` | `ReservOrdered` |
| Subtração | `iv` | `SoftReservPhysical` |
| Subtração | `iv` | `SoftReservOrdered` |
| Subtração | `iv` | `ReservPhysical` |
| Subtração | `iv` | `ReservOrdered` |
| Subtração | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>Medida calculada InventorySupply

A medida calculada `InventorySupply` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `Ordered` |
| Adição | `fno` | `Arrived` |
| Adição | `iv` | `Ordered` |
| Adição | `fno` | `PhysicalInvent` |
| Adição | `iom` | `OnHand` |
| Adição | `erp` | `Unrestricted` |
| Adição | `erp` | `QualityInspection` |
| Adição | `pos` | `PosInbound` |
| Subtração | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>Medida calculada InventoryDemand

A medida calculada `InventoryDemand` é configurada para a fonte de dados `iv` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `OnOrder` |
| Adição | `iom` | `OnOrder` |
| Adição | `iv` | `SoftReservPhysical` |
| Adição | `iv` | `SoftReservOrdered` |
| Adição | `fno` | `ReservPhysical` |
| Adição | `fno` | `ReservOrdered` |
| Adição | `iv` | `ReservPhysical` |
| Adição | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>Configuração da fonte de dados fno

Esta seção descreve como a fonte de dados `fno` é configurada.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Mapeamentos de dimensão para a fonte de dados fno

Os mapeamentos de dimensão listados na tabela a seguir são configurados para a fonte de dados `fno`.

| Dimensão externa | Dimensão base |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Medidas físicas configuradas para a fonte de dados fno

As seguintes medidas físicas são configuradas para a fonte de dados `fno`:

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>Configuração da fonte de dados pos

Esta seção descreve como a fonte de dados `pos` é configurada.

##### <a name="physical-measures-for-the-pos-data-source"></a>Medidas físicas para a fonte de dados pos

As seguintes medidas físicas são configuradas para a fonte de dados `pos`:

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>Medida calculada AvailQuantity

A medida calculada `AvailQuantity` é configurada para a fonte de dados `pos` conforme mostrado na tabela a seguir.

| Tipo de cálculo | Fonte de dados | Medida física |
|---|---|---|
| Adição | `fno` | `AvailPhysical` |
| Adição | `pos` | `PosInbound` |
| Subtração | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>Configuração da fonte de dados iom

As seguintes medidas físicas são configuradas para a fonte de dados `iom` (Intelligent Order Management):

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Configuração da fonte de dados erp

As seguintes medidas físicas são configuradas para a fonte de dados `erp` (planejamento de recursos empresariais):

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>Configuração de partição

A tabela a seguir mostra a configuração da partição padrão.

| Dimensão base | Hierarquia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>Configuração de índice

A tabela a seguir mostra a configuração do índice padrão.

| Número do Conjunto | Dimensão | Hierarquia |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>Configuração de reserva

Esta seção descreve a configuração de reserva padrão.

#### <a name="reservation-mapping"></a>Mapeamento de reserva

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

A tabela a seguir mostra o mapeamento de reserva padrão.

| Fonte de dados de medida física | Medida física | Disponível para a fonte de dados de reserva | Disponível para medida calculada da reserva |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Hierarquia de reservas

A tabela a seguir mostra a hierarquia de reserva padrão.

| Dimensão base | Hierarquia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
