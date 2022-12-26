---
title: Configurar a visibilidade de estoque
description: Este artigo descreve como configurar a visibilidade de estoque.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 2a368535c9644e174d1a2460ac0891c9dc1b1b3f
ms.sourcegitcommit: 44f0b4ef8d74c86b5c5040be37981e32eb43e1a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2022
ms.locfileid: "9850014"
---
# <a name="configure-inventory-visibility"></a>Configurar a visibilidade de estoque

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar a Visibilidade de Estoque usando o aplicativo Visibilidade de Estoque para Power Apps.

## <a name="introduction"></a><a name="introduction"></a>Introdução

Antes de começar a trabalhar com o Visibilidade de Estoque, você deve concluir a seguinte configuração, conforme descrito neste artigo:

- [Configuração de fonte de dados](#data-source-configuration)
- [Configuração de partição](#partition-configuration)
- [Configuração de hierarquia de índice de produtos](#index-configuration)
- [Configuração de reserva (opcional)](#reservation-configuration)
- [Configuração de pré-carga de consulta (opcional)](#query-preload-configuration)
- [Exemplo de configuração padrão](#default-configuration-sample)

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, instale e configure o Suplemento Visibilidade de Estoque conforme descrito em [Instalar e configurar Visibilidade do Estoque](inventory-visibility-setup.md).

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>A página Configuração do aplicativo Visibilidade de Estoque

No Power Apps, a página **Configuração** do [aplicativo Visibilidade de Estoque](inventory-visibility-power-platform.md) ajuda você a definir a configuração disponível e a configuração de reserva flexível. Após a instalação do suplemento, a configuração padrão incluirá o valor do Microsoft Dynamics 365 Supply Chain Management (a fonte de dados `fno`). Você pode analisar as configurações padrão. Além disso, com base nos requisitos comerciais e nos requisitos de lançamento de estoque do sistema externo, você poderá modificar a configuração para padronizar a forma como as alterações de estoque podem ser lançadas, organizadas e consultadas em vários sistemas. As seções restantes do artigo explicam como usar cada parte da página **Configuração**.

Depois que a configuração for concluída, selecione **Atualizar Configuração** no aplicativo.

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>Habilitar recursos de Visibilidade de Estoque no gerenciamento de recursos do Power Apps

O Suplemento de Visibilidade de Estoque adiciona vários recursos novos à sua instalação do Power Apps. Por padrão, esses recursos estão desativados. Para usá-los, abra a página **Configuração** e na guia **Gerenciamento de Recursos** ative os recursos a seguir, conforme necessário.

| Nome do Gerenciamento de Recursos | Descrição |
|---|---|
| *OnHandReservation* | Este tópico permite criar reservas, consumir reservas e/ou cancelar a reserva de quantidades de estoque especificadas usando a Visibilidade de Estoque. Para obter mais informações, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md). |
| *OnHandMostSpecificBackgroundService* | Este recurso fornece um resumo de estoque para produtos juntamente com todas as dimensões. Os dados do resumo de estoque serão sincronizados periodicamente de Visibilidade de Estoque. A frequência de sincronização padrão é uma vez a cada 15 minutos e pode ser definida como uma vez a cada 5 minutos. Para obter mais informações, consulte [Resumo de estoque](inventory-visibility-power-platform.md#inventory-summary). |
| *OnHandIndexQueryPreloadBackgroundService* | Esse recurso busca e armazena periodicamente um conjunto de dados de resumo de estoque disponível com base nas dimensões pré-configuradas. Ele fornece um resumo de estoque que inclui somente as dimensões que são relevantes para seus negócios diários e que é compatível com itens habilitados para processos de gerenciamento de depósito (WMS). Para obter mais informações, consulte [Ativar e configurar consultas disponíveis pré-carregadas](#query-preload-configuration) e [Pré-carregar uma consulta disponível simplificada](inventory-visibility-power-platform.md#preload-streamlined-onhand-query). |
| *OnhandChangeSchedule* | Esse recurso habilita o plano de alterações disponível e os recursos disponíveis para promessa (ATP). Para obter mais informações, consulte [Agenda de alterações disponíveis e disponível para promessa de Visibilidade de Estoque](inventory-visibility-available-to-promise.md). |
| *Alocação* | Esse recurso opcional permite que a Visibilidade de Estoque tenha a capacidade de proteção de inventário (ringfencing) e controle de venda excessiva. Para obter mais informações, consulte [Alocação de estoque de visibilidade do estoque](inventory-visibility-allocation.md). |
| *Habilitar itens de depósito em Visibilidade de Estoque* | Esse recurso opcional permite que a Visibilidade do Estoque dê suporte a itens habilitados para processos de gerenciamento de depósito (WMS). Para obter mais informações, consulte [Suporte do Visibilidade de Estoque para itens WMS](inventory-visibility-whs-support.md). |

> [!IMPORTANT]
> Recomendamos que você use o recurso *OnHandIndexQueryPreloadBackgroundService* ou o recurso *OnHandMostSpecificBackgroundService*, mas não ambos. Habilitar os dois recursos afetará o desempenho.

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Localizar o ponto de extremidade de serviço

Se você não souber o ponto de extremidade de serviço de Visibilidade de Estoque correto, abra a página **Configuração** no Power Apps e selecione **Mostrar Detalhes do Serviço** no canto superior direito. A página mostrará o ponto de extremidade de serviço correto. Você também pode encontrar o ponto de extremidade no Microsoft Dynamics Lifecycle Services, conforme descrito em [Encontre o ponto de extremidade de acordo com seu ambiente de serviços de ciclo de vida](inventory-visibility-api.md#endpoint-lcs).

> [!NOTE]
> O uso de um ponto de extremidade incorreto pode causar falha na instalação do Visibilidade de estoque erros quando o Supply Chain Management é sincronizado com o Visibilidade de estoque. Se você não tiver certeza de qual é o seu ponto de extremidade, entre em contato com o administrador do sistema. Os URLs de ponto de extremidade usam o seguinte formato:
>
> `https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Configuração de fonte de dados

Cada fonte de dados representa um sistema de onde vêm seus dados. Exemplos de nomes de fontes de dados incluem `fno` (que corresponde a Supply Chain Management) e `pos` (que significa "ponto de venda"). Por padrão, o Supply Chain Management é configurado como uma fonte de dados padrão (`fno`) no Visibilidade de Estoque.

> [!NOTE]
> A fonte de dados `fno` é reservada para o Supply Chain Management. Se o suplemento Visibilidade de Estoque estiver integrado a um ambiente do Supply Chain Management, recomendamos que você não exclua as configurações relacionadas a `fno` na fonte de dados.

Para adicionar uma fonte de dados, siga estas etapas.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Fonte de dados**, selecione **Nova fonte de dados** para adicionar uma fonte de dados (por exemplo, `ecommerce` ou outra ID de fonte de dados significativa).

> [!NOTE]
> Ao adicionar uma fonte de dados, valide o nome da fonte de dados, as medidas físicas e os mapeamentos de dimensão antes de atualizar a configuração para o serviço Visibilidade de Estoque. Não será possível modificar essas configurações depois de selecionar **Atualizar Configuração**.

A configuração da fonte de dados inclui as seguintes partes:

- Dimensões (mapeamento de dimensão)
- Medidas físicas
- Medidas calculadas

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Dimensões (mapeamento de dimensão)

O objetivo da configuração da dimensão é padronizar a integração de vários sistemas para postar eventos e consultas, com base nas combinações de dimensão. Visibilidade de Estoque fornece uma lista de dimensões básicas que podem ser mapeadas desde as dimensões da sua fonte de dados. Trinta e três dimensões disponíveis para mapeamento.

- Por padrão, se você estiver usando o Supply Chain Management como uma de suas fontes de dados, 13 dimensões já são mapeadas para as dimensões padrão do Supply Chain Management. As outras 12 dimensões (`inventDimension1` a `inventDimension12`) também são mapeadas para dimensões personalizadas no Supply Chain Management. As oito dimensões restantes (`ExtendedDimension1` a `ExtendedDimension8`) são dimensões estendidas que podem ser mapeadas para fontes de dados externas.
- Se não usar o Supply Chain Management como uma de suas fontes de dados, você poderá mapear as dimensões livremente. A tabela a seguir mostra a lista completa de dimensões disponíveis.

> [!NOTE]
> Se você usar o Supply Chain Management e alterar os mapeamentos de dimensão padrão entre o Supply Chain Management e o Visibilidade de estoque, a dimensão alterada não sincronizará os dados. Portanto, se a dimensão não estiver na lista de dimensões padrão e se você estiver usando uma fonte de dados externa, recomendamos o uso de `ExtendedDimension1` a `ExtendedDimension8` para fazer o mapeamento.

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
| Extensão | `ExtendedDimension1` a `ExtendedDimension8` |
| Sistema | `Empty` |

> [!NOTE]
> Os tipos de dimensão listados na tabela anterior são apenas para sua referência. Você não precisa defini-los no Visibilidade de Estoque.
>
> As dimensões (personalizadas) de estoque podem ser reservadas para o Supply Chain Management. Nesse caso, use as dimensões estendidas.

Os sistemas externos podem acessar o Visibilidade de Estoque por meio de suas APIs RESTful. Para a integração, o Visibilidade de Estoque permite que você configure a *fonte de dados externa* e o mapeamento das *dimensões externas* para as *dimensões base*. Aqui está um exemplo de uma tabela de mapeamento de dimensão.

| Dimensão externa | Dimensão base |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

Configurando um mapeamento de dimensão, você pode enviar as dimensões externas diretamente para o Visibilidade de Estoque. O Visibilidade de Estoque converterá automaticamente as dimensões externas em dimensões base.

Para adicionar mapeamentos de dimensão, siga estas etapas.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Data Source**, selecione a fonte de dados onde deseja fazer o mapeamento de dimensão. Em seguida, na seção **Mapeamentos de Dimensão**, selecione **Adicionar** para adicionar mapeamentos de dimensão.

    ![Adição de mapeamentos de dimensão](media/inventory-visibility-dimension-mapping.png "Adição de mapeamentos de dimensão")

1. No campo **Nome da Dimensão**, especifique a dimensão de origem.
1. No campo **Para Dimensão Base**, selecione a dimensão no Visibilidade de Estoque que você deseja mapear.
1. Selecione **Salvar**.

Por exemplo, você já criou uma fonte de dados chamada `ecommerce` que inclui uma dimensão de cor do produto. Neste caso, para fazer o mapeamento, você pode primeiro adicionar `ProductColor` ao campo **Nome da dimensão** na fonte de dados `ecommerce` e então selecionar `ColorId` no campo **Para dimensão base**.

### <a name="physical-measures"></a><a name="data-source-configuration-physical-measures"></a>Medidas físicas

Quando uma fonte de dados lança uma alteração de estoque em Visibilidade de Estoque, ela lança essa alteração usando *medidas físicas*. As medidas físicas modificam a quantidade e refletem o status do estoque. Você pode definir suas próprias medidas físicas, com base em seus requisitos. As consultas podem ser baseadas nas medidas físicas.

O Visibilidade de Estoque fornece uma lista de medidas físicas padrão que estão mapeadas ao Supply Chain Management (a fonte de dados `fno`). Essas medidas físicas padrão são tiradas dos status da transação de estoque na página **Lista de disponíveis** no Supply Chain Management (**Gerenciamento de Estoque \> Consultas e Relatório \> Lista de disponíveis**). A tabela a seguir fornece um exemplo de medidas físicas.

| Nome da medida física | Descrição |
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
| `Received` | Recebido |
| `Registered` | Registrado |
| `ReservOrdered` | Ordem reservada |
| `ReservPhysical` | Reserva física |

Se a sua fonte de dados for o Supply Chain Management, você não precisará recriar as medidas físicas padrão. No entanto, para fontes de dados externas, você poderá criar novas medidas físicas seguindo estas etapas.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Fonte de dados**, selecione a fonte de dados para adicionar medidas físicas (por exemplo, a fonte de dados `ecommerce`). Em seguida, na seção **Medidas físicas**, selecione **Adicionar** e especifique o nome da medida (por exemplo, `Returned` se desejar registrar as quantidades devolvidas nesta fonte de dados como Visibilidade do inventário). Salve as alterações.

### <a name="extended-dimensions"></a>Dimensões estendidas

Os clientes que desejam usar fontes de dados externas na fonte de dados podem ter vantagens da extensibilidade que o Dynamics 365 oferece por meio da criação de [Extensões de Classe](../../fin-ops-core/dev-itpro/extensibility/class-extensions.md) para as classes `InventOnHandChangeEventDimensionSet` e `InventInventoryDataServiceBatchJobTask`.

Sincronize com o banco de dados depois de criar as extensões na ordem para que os campos personalizados sejam adicionados à tabela `InventSum`. Em seguida, você pode consultar a seção Dimensões anteriormente neste artigo para mapear as dimensões personalizadas para qualquer uma das oito dimensões estendidas em `BaseDimensions`, em Estoque.

> [!NOTE] 
> Para obter outros detalhes sobre como criar extensões, consulte [Home page de Extensibilidade](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md).

### <a name="calculated-measures"></a>Medidas calculadas

Você pode usar Visibilidade de Estoque para consultar tanto as medidas físicas de estoque como as *medidas calculadas personalizadas*. As medidas calculadas fornecem uma fórmula de cálculo personalizada que consiste em uma combinação de medidas físicas. Essa funcionalidade permite definir um conjunto de medidas físicas que serão adicionadas e/ou um conjunto de medidas físicas que serão subtraídas para formar a medida personalizada.

> [!IMPORTANT]
> Uma medida calculada é uma composição de medidas físicas. Sua fórmula pode incluir somente medidas físicas sem duplicatas, não medidas calculadas.

A configuração permite definir um conjunto de fórmulas de medida calculadas que incluem modificadores de adição ou subtração para obter a quantidade total de saída agregada.

Para configurar uma medida calculada personalizada, siga estas etapas.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Medida Calculada**, selecione **Nova Medida de Cálculo** para adicionar uma medida calculada.
1. Defina os seguintes campos para a nova medida calculada:

    - **Nome da nova medida calculada** – Insira o nome da medida calculada.
    - **Fonte de dados** – Selecione a fonte de dados na qual a nova medida calculada será incluída. O sistema de consulta é uma fonte de dados.

1. Selecione **Adicionar** para adicionar um modificador à nova medida calculada.
1. Defina os seguintes campos para o novo modificador:

    - **Modificador** – Selecione o tipo de modificador (*Adição* ou *Subtração*).
    - **Fonte de dados** – selecione a fonte de dados em que a medida que fornece o valor do modificador deve ser encontrada.
    - **Medida** – Selecione o nome da medida (da fonte de dados selecionada) que fornece o valor para o modificador.

1. Repita as etapas 5 a 6 até adicionar todos os modificadores necessários e concluir a fórmula da medida calculada.
1. Selecione **Salvar**.

Por exemplo, uma empresa de moda opera em três fontes de dados:

- `pos` - Corresponde ao canal da loja.
- `fno` - Corresponde ao Supply Chain Management.
- `ecommerce` - Corresponde ao seu canal web.

Sem medidas calculadas, ao consultar o produto D0002 (Armário) no local 1, depósito 11 e um valor de dimensão `ColorID` de `Red`, você pode obter o seguinte resultado de consulta, que mostra as quantidades de estoque em cada físico pré-configurado a medida. No entanto, você não tem visibilidade do total disponível para quantidades de reserva em suas fontes de dados.

```json
[
    {
        "productId": "D0002",
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
            "ecommerce": {
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
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `received` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `scheduled` | `Addition` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `issued` | `Subtraction` |
| `CrossChannel` | `MyCustomAvailableforReservation` | `ecommerce` | `reserved` | `Subtraction` |

Quando essa fórmula de cálculo for usada, o novo resultado da consulta incluirá a medida personalizada.

```json
[
    {
        "productId": "D0002",
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
            "ecommerce": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CrossChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

A saída `MyCustomAvailableforReservation` com base na configuração de cálculo nas medidas personalizadas, é 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Configuração de partição

No momento, a configuração da partição consiste em duas dimensões base (`SiteId` e `LocationId`) que indicam como os dados são distribuídos. As operações na mesma partição podem oferecer melhor desempenho a um custo menor. A tabela a seguir mostra a configuração de partição padrão fornecida pelo Suplemento de Visibilidade de Estoque.

| Dimensão base | Hierarquia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

A solução inclui essa configuração de partição por padrão. Portanto, *você não precisa defini-la*.

> [!IMPORTANT]
> Não personalize a configuração de partição padrão. Se você excluí-la ou alterá-la, provavelmente causará um erro inesperado.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Configuração de hierarquia de índice de produtos

Na maioria das vezes, a consulta de estoque disponível não será apenas no nível "total" mais alto. Em vez disso, talvez você deseje ver os resultados agregados com base nas dimensões do estoque.

A Visibilidade de Estoque fornece flexibilidade, permitindo que você configure *índices* para aprimorar o desempenho de consultas. Esses índices são baseados em uma dimensão ou combinação de dimensões. Um índice consiste em um *número do conjunto*, uma *dimensão* e uma *hierarquia*, conforme definido na tabela a seguir.

| Organização | Descrição |
|---|---|
| Número do conjunto | As dimensões que pertencerem ao mesmo conjunto (índice) serão agrupadas, e o mesmo número de conjunto será atribuído a elas. |
| Dimensão | Dimensões básicas nas quais o resultado da consulta é agregado. |
| Hierarquia | A hierarquia permite aumentar o desempenho de combinações específicas de dimensão quando usadas em parâmetros de filtro e de grupo por consulta. Por exemplo, se você configurar um conjunto de dimensões com uma sequência de hierarquias `(ColorId, SizeId, StyleId)`, o sistema poderá processar consultas relacionadas a quatro combinações de dimensões mais rapidamente. A primeira combinação está vazia, a segunda é `(ColorId)`, a terceira é `(ColorId, SizeId)` e a quarta é `(ColorId, SizeId, StyleId)`. Outras combinações não serão aceleradas. Os filtros não são restritos por ordem, mas devem estar nessas dimensões, caso você queira melhorar o desempenho. Para obter mais informações, consulte o exemplo a seguir. |

Para configurar seu índice de hierarquia de produtos, siga estas etapas.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Índice de Hierarquia de Produtos**, na seção **Mapeamentos de Dimensão**, selecione **Adicionar** para adicionar mapeamentos de dimensão.
1. Por padrão, uma lista de índices é fornecida. Para modificar um índice existente, selecione **Editar** ou **Adicionar** na seção do índice relevante. Para criar um novo conjunto de índices, selecione **Novo conjunto de índices**. Para cada linha em cada conjunto de índices, no campo **Dimensão**, selecione na lista de dimensões base. Os valores para os campos a seguir são gerados automaticamente:

    - **Número do conjunto** – as dimensões que pertencem ao mesmo grupo (índice) serão agrupadas, e o mesmo número do conjunto será alocado para elas.
    - **Hierarquia** – a hierarquia aumenta o desempenho de combinações específicas de dimensão quando usadas em parâmetros de filtro e de grupo por consulta.

> [!TIP]
> Conheça algumas dicas para ter em mente ao configurar sua hierarquia de índice:
>
> - As dimensões base definidas na configuração da partição não devem ser definidas nas configurações de índice. Se uma dimensão base for definida novamente na configuração do índice, você não poderá consultar por esse índice.
> - Se você só precisar consultar o estoque agregado por todas as combinações de dimensão, configure um único índice que contenha a dimensão base `Empty`.

### <a name="example"></a>Exemplo

Esta seção fornece um exemplo que mostra o funcionamento da hierarquia.

A tabela a seguir fornece uma lista de estoque disponível para este exemplo.

| Item | ColorId | SizeId | StyleId | Quantidade |
|---|---|---|---|---|
| D0002 | Preto | Pequeno | Largo | 1 |
| D0002 | Preto | Pequeno | Regular | 2 |
| D0002 | Preto | Grande | Largo | 3 |
| D0002 | Preto | Grande | Regular | 4 |
| D0002 | Vermelho | Pequeno | Largo | 5 |
| D0002 | Vermelho | Pequeno | Regular | 6 |
| D0002 | Vermelho | Grande | Regular | 7 |

A tabela a seguir mostra como a hierarquia de índice é configurada.

| Número do Conjunto | Dimensão | Hierarquia |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

O índice permite consultar o estoque disponível das seguintes maneiras:

- `()` – agrupado por todos

    - D0002, 28

- `(ColorId)` – agrupado por `ColorId`

    - D0002, Preto, 10
    - D0002, Vermelho, 18

- `(ColorId, SizeId)` – agrupado pela combinação de `ColorId` e `SizeId`

    - D0002, Preto, Pequeno, 3
    - D0002, Preto, Grande, 7
    - D0002, Vermelho, Pequeno, 11
    - D0002, Vermelho, Grande, 7

- `(ColorId, SizeId, StyleId)` – agrupado pela combinação de `ColorId`, `SizeId` e `StyleId`

    - D0002, Preto, Pequeno, Largo, 1
    - D0002, Preto, Pequeno, Regular, 2
    - D0002, Preto, Grande, Largo, 3
    - D0002, Preto, Grande, Regular, 4
    - D0002, Vermelho, Pequeno, Largo, 5
    - D0002, Vermelho, Pequeno, Regular, 6
    - D0002, Vermelho, Grande, Regular, 7

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Configuração de reserva (opcional)

A configuração da reserva será necessária se você desejar usar o recurso de reserva flexível. A configuração consiste em duas partes fundamentais:

- Mapeamento de reserva flexível
- Hierarquia de reserva flexível

### <a name="soft-reservation-mapping"></a>Mapeamento de reserva flexível

Ao fazer uma reserva, você pode querer saber se o estoque em mãos está disponível para reserva. A validação está ligada a uma medida calculada que representa uma fórmula de cálculo de uma combinação de medidas físicas.

Ao configurar o mapeamento da medida física para a medida calculada, você permitirá que o serviço Visibilidade de Estoque valide automaticamente a disponibilidade da reserva, com base na medida física.

Antes de configurar esse mapeamento, as medidas físicas, as medidas calculadas e suas fontes de dados deverão ser definidas nas guias **Fonte de dados** e **Medida calculada** da página de **Configuração** no Power Apps (conforme descrito anteriormente neste artigo).

Para definir o mapeamento de reserva flexível, siga estas etapas.

1. Defina a medida física que serve como medida da reserva flexível (por exemplo, `SoftReservPhysical`).
1. Na guia **Medida calculada** da página **Configuração**, defina a medida calculada AFR (*disponível para reserva*) que contém a fórmula de computação AFR que você deseja mapear para a medida física. Por exemplo, você pode configurar `AvailableToReserve` (disponível para reserva) para que ele seja mapeado para a medida física `SoftReservPhysical` definida anteriormente. Dessa forma, você poderá descobrir quais quantidades têm o status de estoque `SoftReservPhysical` estarão disponíveis para reserva. A tabela a seguir mostra a fórmula de computação AFR.

    | Tipo de cálculo | Fonte de dados | Medida física |
    |---|---|---|
    | Adição | `fno` | `AvailPhysical` |
    | Adição | `pos` | `Inbound` |
    | Subtração | `pos` | `Outbound` |
    | Subtração | `iv` | `SoftReservPhysical` |

    É recomendável configurar a medida calculada para que contenha a medida física na qual a medida da reserva se baseia. Dessa forma, a quantidade da medida calculada será afetada pela quantidade da medida da reserva. Portanto, neste exemplo, a medida calculada `AvailableToReserve` da fonte de dados `iv` deve conter a medida física `SoftReservPhysical` de `iv` como componente.

1. Abra a página **Configuração**.
1. Na guia **Mapeamento de Reserva Flexível**, configure o mapeamento da medida física para a medida calculada. No exemplo anterior, você poderia usar as configurações a seguir para mapear `AvailableToReserve` para a medida física `SoftReservPhysical` definida anteriormente.

    | Fonte de dados de medida física | Medida física | Disponível para a fonte de dados de reserva | Disponível para medida calculada da reserva |
    |---|---|---|---|
    | `iv` | `SoftReservPhysical` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Se não puder editar a guia **Mapeamento de Reserva Flexível**, você poderá precisar ativar o recurso *OnHandReservation* na guia **Gerenciamento de Recursos**.

Agora, quando você fizer a reserva em `SoftReservPhysical`, o Visibilidade de Estoque encontrará automaticamente `AvailableToReserve` e sua fórmula de cálculo relacionada para fazer a validação da reserva.

Por exemplo, você tem o estoque a seguir disponível no Visibilidade de Estoque.

```json
{
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservPhysical": 90
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

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservPhysical`  
= 70 + 50 – 20 – 90  
= 10

Portanto, se você tentar fazer reservas em `iv.SoftReservPhysical` e a quantidade for menor ou igual a `AvailableToReserve` (10), a reserva flexível será bem-sucedida.

> [!NOTE]
> Ao chamar a API de reserva, você pode controlar a validação da reserva especificando o parâmetro booliano `ifCheckAvailForReserv` no corpo da solicitação. Um valor de `True` significa que a validação é necessária, enquanto um valor de `False` significa que a validação não é necessária (embora você possa acabar com uma quantidade negativa de `AvailableToReserve`, o sistema ainda permitirá você para reserva flexível). O valor padrão é `True`.

### <a name="soft-reservation-hierarchy"></a>Hierarquia de reserva flexível

A hierarquia de reservas descreve a sequência de dimensões que deve ser especificada quando as reservas são feitas. Ele funciona da mesma forma que a hierarquia de índice do produto funciona para consultas disponíveis.

A hierarquia de reserva é independente da hierarquia de índice de produto. Essa independência permite implementar o gerenciamento de categorias, no qual os usuários podem dividir as dimensões em detalhes para especificar os requisitos para fazer reservas mais precisas. A hierarquia de reserva reversível deve conter `SiteId` e `LocationId` como componentes, pois eles constroem a configuração da partição. Ao fazer a reserva, você deve especificar uma partição para o produto.

Aqui está um exemplo de uma hierarquia de reserva flexível.

| Dimensão base | Hierarquia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

Nesse exemplo, você pode fazer reserva nas seguintes sequências de dimensão. Você deve especificar uma partição para o produto ao fazer a reserva. Portanto, a hierarquia básica que você pode usar é `(SiteId, LocationId)`.

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Uma sequência de dimensão válida deve seguir estritamente a hierarquia de reserva, dimensão por dimensão. Por exemplo, a sequência de hierarquia `(SiteId, LocationId, SizeId)` não é válida porque `ColorId` está ausente.

## <a name="available-to-promise-configuration-optional"></a>Configuração disponível para promessa (opcional)

Você pode configurar a visibilidade do inventário para permitir que você programe futuras alterações disponíveis e calcule as quantidades disponíveis para promessa (ATP). ATP é a quantidade de um item que está disponível e pode ser prometida a um cliente no próximo período. O uso deste cálculo pode aumentar bastante o recurso de atendimento da ordem. Para usar esse recurso, você deve habilitá-lo na guia **Gerenciamento de Recursos** e configurá-lo na guia **Definição de ATP**. Para obter mais informações, consulte [Agenda de alterações disponíveis e disponível para promessa de Visibilidade de Estoque](inventory-visibility-available-to-promise.md).

## <a name="turn-on-and-configure-preloaded-on-hand-queries-optional"></a><a name="query-preload-configuration"></a>Ativar e configurar consultas disponíveis pré-carregadas (opcional)

A Visibilidade de Estoque pode buscar e armazenar periodicamente um conjunto de dados de resumo de estoque disponível com base nas dimensões pré-configuradas. Isso proporciona os seguintes benefícios:

- Uma exibição mais limpa que armazena um resumo de estoque que inclui somente as dimensões que são relevantes para o seu negócio diário.
- Um resumo de estoque compatível com itens habilitados para processos de gerenciamento de depósito (WMS).

Consulte [Pré-carregar uma consulta disponível simplificada](inventory-visibility-power-platform.md#preload-streamlined-onhand-query) para obter mais informações sobre como trabalhar com esse recurso após configurá-lo.

> [!IMPORTANT]
> Recomendamos que você use o recurso *OnHandIndexQueryPreloadBackgroundService* ou o recurso *OnHandMostSpecificBackgroundService*, mas não ambos. Habilitar os dois recursos afetará o desempenho.

Siga estas etapas para configurar o recurso:

1. Entre no Power App Visibilidade de Estoque.
1. Acesse **Configuração \> Gerenciamento e Configurações de Recursos**.
1. Se o recurso *OnHandIndexQueryPreloadBackgroundService* já estiver habilitado, recomendamos que você o desative por enquanto, já que o processo de limpeza pode levar muito tempo para ser concluído. Você o ativará outra vez posteriormente neste procedimento.
1. Abra a guia **Configuração de Pré-carregamento**.
1. Na seção **Etapa 1: Limpar Armazenamento de Pré-carregamento**, selecione **Limpar** para limpar o banco de dados e prepará-lo para aceitar suas novas configurações de agrupar por.
1. Na seção **Etapa 2: Configurar Agrupar por Valores**, no campo **Agrupar Resultado por**, insira uma lista de nomes de campos separados por vírgulas para agrupar os resultados da consulta. Assim que houver dados no banco de dados de armazenamento de pré-carregamento, não será possível alterar essa configuração até que você limpe o banco de dados, conforme descrito na etapa anterior.
1. Acesse **Configuração \> Gerenciamento e Configurações de Recursos**.
1. Ative o recurso *OnHandIndexQueryPreloadBackgroundService*.
1. Selecione **Atualizar Configuração** no canto superior direito da página **Configuração** para configurar suas alterações.

## <a name="complete-and-update-the-configuration"></a>Concluir e atualizar a configuração

Depois de concluir a configuração, você deverá confirmar todas as alterações em Visibilidade de Estoque. Siga estas etapas para confirmar suas alterações.

1. No Power Apps, na página **Configuração**, selecione **Atualizar configuração** no canto superior direito. 
1. O sistema solicita credenciais de login. Insira os seguintes valores:

    - **ID do Cliente** – a ID do aplicativo do Azure criada para Visibilidade de Estoque.
    - **ID de Locatário** – sua ID de locatário do Azure.
    - **Segredo do Cliente** – o segredo do aplicativo do Azure criado para Visibilidade de Estoque.

    Para obter mais informações sobre essas credenciais como encontrá-las, consulte [Instalar e configurar o Visibilidade de Estoque](inventory-visibility-setup.md).

    > [!IMPORTANT]
    > Valide o nome da fonte de dados, as medidas físicas e os mapeamentos de dimensão antes de atualizar a configuração. Não será possível modificar essas configurações depois de atualizar.

1. Após entrar, selecione **Atualizar configuração** novamente. O sistema aplica suas configurações e mostra o que mudou.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Exemplo de configuração padrão

Durante seu estágio de inicialização, Visibilidade de Estoque define uma configuração padrão, que é detalhada aqui. Você pode modificar essa configuração conforme necessário.

### <a name="data-source-configuration"></a>Configuração de fonte de dados

#### <a name="configuration-of-the-iv-data-source"></a>Configuração da fonte de dados iv

Esta seção descreve como a fonte de dados `iv` é configurada.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Medidas físicas configuradas para a fonte de dados "iv"

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

#### <a name="configuration-of-the-fno-data-source"></a>Configuração da fonte de dados "fno"

Esta seção descreve como a fonte de dados `fno` é configurada.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Mapeamentos de dimensão para a fonte de dados "fno"

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

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Medidas físicas configuradas para a fonte de dados "fno"

As seguintes medidas físicas são configuradas para a fonte de dados `fno`:

- `Arrived`
- `PhysicalInvent`
- `ReservPhysical`
- `onorder`
- `notspecified`
- `availordered`
- `availphysical`
- `picked`
- `postedqty`
- `quotationreceipt`
- `received`
- `ordered`
- `ReservOrdered`

#### <a name="configuration-of-the-pos-data-source"></a>Configuração da fonte de dados "pos"

Esta seção descreve como a fonte de dados `pos` é configurada.

##### <a name="physical-measures-for-the-pos-data-source"></a>Medidas físicas para a fonte de dados "pos"

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

#### <a name="configuration-of-the-iom-data-source"></a>Configuração da fonte de dados "iom"

As seguintes medidas físicas são configuradas para a fonte de dados `iom` (Intelligent Order Management):

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Configuração da fonte de dados "erp"

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

A tabela a seguir mostra o mapeamento de reserva padrão.

| Fonte de dados de medida física | Medida física | Disponível para a fonte de dados de reserva | Disponível para medida calculada da reserva |
|---|---|---|---|
| `iv` | `SoftReservPhysical` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Hierarquia de reservas

A tabela a seguir mostra a hierarquia de reserva padrão.

| Dimensão base | Hierarquia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
