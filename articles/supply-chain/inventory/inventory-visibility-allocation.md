---
title: Alocação de estoque de visibilidade de estoque
description: Este tópico explica como configurar e usar o recurso alocação de estoque, que permite separar o estoque dedicado para garantir que você possa atender a canais ou clientes mais rentáveis.
author: yufeihuang
ms.date: 05/20/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 4293ead4ccfc9ba04e8b9da437134b4e97569026
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786940"
---
# <a name="inventory-visibility-inventory-allocation"></a>Alocação de estoque de visibilidade de estoque

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Plano de fundo e finalidade dos negócios

Em muitos casos, os fabricantes, varejistas e outros proprietários de empresas da cadeia de suprimento devem pré-alocar estoque para canais de vendas importantes, locais ou clientes, ou para eventos de vendas específicos. A alocação de estoque é uma prática típica no processo de planejamento operacional de vendas e é realizada antes que as atividades reais de vendas ocorram e uma ordem de venda seja criada.

Por exemplo, uma empresa de bicicleta tem estoque limitado disponível para uma bicicleta muito popular. Esta empresa faz vendas online e na loja. Em cada canal de vendas, a empresa tem alguns parceiros comerciais importantes (mercados e varejistas grandes) que exigem que uma parte específica do estoque disponível da bicicleta seja salva para eles. Portanto, a empresa de bicicleta deve ser capaz de equilibrar a distribuição de estoque em canais e também gerenciar as expectativas de parceiros VIP. A melhor maneira de atingir ambas as metas é usar a alocação de estoque, de forma que cada canal e varejista possa receber quantidades alocadas específicas que possam ser vendidas para os consumidores posteriormente.

A alocação de estoque tem duas finalidades comerciais básicas:

- **Proteção de estoque (ringfencing)** – as organizações desejam pré-alocar estoque restrito ou limitado para canais priorizados, regiões, clientes VIP e empresas subsidiárias. O recurso de alocação de visibilidade de estoque visa proteger o estoque alocado, de forma que as outras alocações, reservas ou outras demandas de venda não afetem o estoque previamente alocado.
- **Controle de venda excessiva** – o recurso de alocação de visibilidade de estoque visa colocar uma restrição nas quantidades alocadas anteriormente, de modo que a parte destinatária (por exemplo, um canal ou grupo de clientes) não as consuma em excesso quando a transação de vendas real baseada em uma reserva flexível entrar em vigor.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Definição de alocação no serviço de visibilidade de estoque

Embora o recurso de alocação no serviço de visibilidade de estoque não reserve quantidades de estoque físico, ele se refere à quantidade de estoque físico disponível para definir a quantidade inicial de pool virtual *disponível para alocar*. A alocação de estoque na visibilidade de estoque é uma alocação flexível. Ela é realizada antes das transações reais de vendas e não depende de ordens de venda. Por exemplo, você pode alocar o estoque para os canais de vendas mais importantes ou grandes varejistas empresariais antes que os clientes finais visitem o canal de vendas ou a loja de varejo para comprá-lo.

A diferença entre alocação de estoque e [reserva flexível de estoque](inventory-visibility-reservations.md) é que a reserva flexível geralmente é vinculada a transações de vendas reais (linhas da ordem de venda). Portanto, se você desejar usar os recursos de alocação e reserva flexível juntos, é recomendável fazer a alocação de estoque primeiro e, depois, fazer a reserva flexível para as quantidades alocadas. Para obter mais informações, consulte [Consumir como reserva flexível](#consume-to-soft-reserved).

O recurso de alocação de estoque permite que os planejadores de vendas ou os principais gerentes de contas gerenciem e pré-aloquem estoque importante entre grupos de alocação (como canais, regiões e grupos de clientes). Ele também oferece suporte a rastreamento, ajuste e análise de consumo em tempo real em relação a quantidades alocadas, de forma que o reabastecimento ou a realocação possa ser feita no prazo. Essa capacidade de ter visibilidade em tempo real sobre alocação, consumo e saldo de alocação é especialmente importante em eventos de promoção e venda rápida.

## <a name="terminology"></a>Terminologia

Os seguintes termos e conceitos são úteis em discussões de alocação de estoque:

- **Grupo de alocação** – o grupo que possui a alocação, como um canal de vendas, um grupo de clientes ou um tipo de ordem.
- **Valor do grupo de alocação** – o valor de cada grupo de alocação. Por exemplo, *web* ou *loja* pode ser o valor do grupo de alocação de canais de vendas, enquanto *VIP* ou *normal* pode ser o valor do grupo de alocação do cliente.
- **Hierarquia de alocação** – um meio de combinar grupos de alocação de forma hierárquica. Por exemplo, você pode definir *canal* como nível hierárquico 1, *região* como nível 2 e *grupo de clientes* como nível 3. Durante a alocação de estoque, você deve seguir a sequência da hierarquia de alocação ao especificar o valor do grupo de alocação. Por exemplo, você pode alocar 200 bicicletas vermelhas para o canal da *Web*, a região de *Londres* e o grupo de clientes *VIP*.
- **Disponível para alocar** – o *pool comum virtual* que indica a quantidade disponível para alocação adicional. Esta é uma medida calculada que você pode definir livremente usando sua própria fórmula. Se você também estiver usando o recurso de reserva reversível, é recomendável usar a mesma fórmula para calcular disponível para alocar e disponível para reservar.
- **Alocado** – uma medida física que mostra a cota alocada que pode ser consumida pelos grupos de alocação.
- **Consumido** – uma medida física que indica as quantidades consumidas com relação à quantidade alocada original. À medida que os números são adicionados a essa medida física, a medida física alocada é reduzida automaticamente.

A ilustração a seguir mostra o fluxo de trabalho comercial para alocação de estoque.

![Fluxo de trabalho comercial de alocação da visibilidade de estoque.](media/inventory-visibility-allocation-flow.png "Fluxo de trabalho comercial de alocação da visibilidade de estoque.")

## <a name="set-up-inventory-allocation"></a>Configurar alocação de estoque

O recurso de alocação de estoque consiste nos seguintes componentes:

- A fonte de dados predefinida, relacionada à alocação, medidas físicas e medidas calculadas.
- Grupos de alocação personalizáveis com, no máximo, oito níveis.
- Um conjunto de interfaces de programação de aplicação (APIs) de alocação:

    - alocar
    - realocar
    - desalocar
    - consumir
    - consulta

O processo de configuração do recurso de alocação tem duas etapas:

- Configure a [fonte de dados](inventory-visibility-configuration.md#data-source-configuration) e suas [medidas](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Configure o nome e a hierarquia do grupo de alocação.

### <a name="predefined-data-source"></a>Fonte de dados predefinida

Ao habilitar o recurso de alocação e chamar a API de atualização de configuração, a visibilidade de estoque cria uma fonte de dados predefinida e várias medidas iniciais.

A fonte de dados é chamada de `@iv`.

Estas são as medidas físicas iniciais:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Estas são as medidas calculadas iniciais:

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Adicionar outras medidas físicas à medida calculada disponível para alocar

Para usar a alocação, você deve configurar a medida calculada de disponível para alocar (`@iv`.`@available_to_allocate`). Por exemplo, você tem a fonte de dados `fno` e a medida `onordered`, a fonte de dados `pos` e a medida `inbound`, e deseja fazer a alocação no que há disponível para a soma de `fno.onordered` e `pos.inbound`. Nesse caso, `@iv.@available_to_allocate` deve conter `pos.inbound` e `fno.onordered` na fórmula. Este é um exemplo:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

### <a name="change-the-allocation-group-name"></a>Alterar o nome do grupo de alocação

É possível definir no máximo oito nomes de grupos de alocação. Os grupos têm uma hierarquia.

Defina os nomes de grupos na página **Configuração do Power App de Visibilidade de Estoque**. Para abrir esta página, no ambiente do Microsoft Dataverse, abra a aplicação de Visibilidade de Estoque e selecione **Configuração \> Alocação**.

Por exemplo, se você usar quatro nomes de grupos e defini-los como \[`channel`, `customerGroup`, `region`, `orderType`\], os nomes serão válidos para solicitações relativas à alocação quando você chamar a API de atualização de configuração.

### <a name="allcoation-using-tips"></a>Alocação usando dicas

- Para cada produto, a função de alocação deve ser usada no mesmo nível de dimensão, de acordo com a hierarquia de índice do produto definida na [configuração da hierarquia do índice do produto](inventory-visibility-configuration.md#index-configuration). Por exemplo, a hierarquia de índice é Site, Local, Cor, Tamanho. Se você alocar uma quantidade para um produto em nível de Site, Local, Cor. Na próxima vez em que você alocar, também faça em nível de Site, Local, Cor. Se você usar o nível Site, Local, Cor, Tamanho ou o nível Site, Local, os dados não serão consistentes.
- A alteração do nome do grupo de alocação não afetará os dados salvos no serviço.
- A alocação deverá ocorrer depois que o produto tiver a quantidade disponível positiva.

### <a name="using-the-allocation-api"></a><a name="using-allocation-api"></a>Usar a API de alocação

No momento, cinco APIs de alocação estão abertas:

- POST /api/environment/{environmentId}/allocation/allocate
- POST /api/environment/{environmentId}/allocation/unallocate
- POST /api/environment/{environmentId}/allocation/reallocate
- POST /api/environment/{environmentId}/allocation/consume
- POST /api/environment/{environmentId}/allocation/query

#### <a name="allocate"></a>Alocar

Chame a API `Allocate` para alocar um produto com dimensões específicas. Este é o esquema do corpo da solicitação.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Por exemplo, você deseja alocar 10 unidades do produto *Bicicleta*, site *1*, local *11*, cor *vermelho*, canal *Online*, grupo de clientes *VIP* e região *EUA*. Para fazer essa alocação, você pode fazer uma chamada com o seguinte conteúdo de corpo.

```json
{
    "id": "???",
    "productId": "Bike",
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 10,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

A quantidade deve ser sempre maior que 0 (zero).

#### <a name="unallocate"></a>Desalocar

Use a API `Unallocate` para reverter a operação `Allocate`. A quantidade negativa não é permitida em uma operação `Allocate`. O corpo de `Unallocate` é idêntico ao corpo de `Allocate`.

#### <a name="reallocate"></a>Realocar

Use a API `Reallocate` para mover uma quantidade alocada para outra combinação de grupos. Este é o esquema do corpo da solicitação.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "sourceGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "targetGroups": {
        "groupD": "string",
        "groupE": "string",
        "groupF": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Por exemplo, você pode mover duas bicicletas com as dimensões \[site=1, local=11, cor=vermelho\] do grupo de alocação \[Online, VIP, EUA\] para o grupo de alocação \[Online, VIP, UE\] chamando a API `Reallocate` e fornecendo o corpo de texto a seguir.

```json
{
    "id": "???",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "EU"
    },
    "quantity": 2,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

#### <a name="consume"></a>Consumir

Use a API `Consume` para lançar a quantidade de consumo em relação à alocação. Por exemplo, você pode usar esta API para mover a quantidade alocada para algumas medidas reais. Este é o esquema do corpo da solicitação.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "physicalMeasures": {
        "datasource1": {
            "measure": "string" // Addition or Subtraction
        }
    }
}
```

Por exemplo, há oito bicicletas alocadas com as dimensões \[site=1, local=11, cor=vermelho\] para o grupo de alocação \[Online, VIP, EUA\]. A seguinte fórmula disponível para alocar é usada:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

As oito bicicletas são alocadas a partir da medida `pos.inbound`.

Agora, três bicicletas são vendidas e são retiradas do pool de alocação. Para registrar esta mudança, você pode fazer uma chamada com o corpo da solicitação a seguir.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "pos": {
            "inbound": "Subtraction"
        }
    }
}
```

Depois dessa chamada, a quantidade alocada para o produto será reduzida em 3. Além disso, a visibilidade do estoque gerará um evento de alteração disponível em que `pos.inbound` = *-3*. Outra opção é manter o valor `pos.inbound` como está e apenas consumir a quantidade alocada. Mas, nesse caso, você deve criar outra medida física para manter as quantidades consumidas ou usar a medida predefinida `@iv.@consumed`.

Nesta solicitação, observe que a medida física usada no corpo da solicitação de consumo deve usar o tipo de modificador oposto (adição ou subtração), em comparação com o tipo de modificador usado na medida calculada. Portanto, neste corpo de consumo, `iv.inbound` tem o valor `Subtraction`, e não `Addition`.

A fonte de dados `fno` não pode ser usada no corpo de consumo porque sempre reivindicamos que a visibilidade de estoque não pode alterar dados da fonte de dados `fno`. O fluxo de dados é unidirecional, o que significa que todas as alterações de quantidade da fonte de dados `fno` devem ser obtidas do ambiente do Supply Chain Management.

#### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Consumir como uma reserva flexível

A API `Consume` também pode consumir a quantidade alocada como uma reserva flexível. Nesse caso, a operação `Consume` reduzirá a quantidade alocada e, depois, fará uma reserva flexível para essa quantidade. Para usar essa abordagem, você também deve usar o recurso [reserva flexível](inventory-visibility-reservations.md) de visibilidade de estoque.

Por exemplo, você definiu um modificador de reserva flexível (medida) como `iv.softreserved`. A seguinte fórmula é usada para a medida calculada de disponível para reservar:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved`

Para usar essa configuração com o recurso de alocação, adicione `@iv.@allocated` a `iv.available_to_reserve` para produzir a seguinte fórmula:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved` – `@iv.@allocated`

Atualize `@iv.@available_to_allocate` para o mesmo valor.

Quando desejar consumir uma quantidade de 3 e reservá-la diretamente, você poderá fazer uma chamada com o corpo da solicitação a seguir.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "iv": {
            "softreserved": "Addition"
        }
    }
}
```

Nesta solicitação, note que `iv.softreserved` tem o valor `Addition`, e não `Subtraction`.

#### <a name="query"></a>Consulta

Use a API `Query` para recuperar informações relativas à alocação de alguns produtos. É possível usar filtros de dimensão e filtros de grupos de alocação para restringir os resultados. As dimensões devem coincidir exatamente com a que você deseja recuperar; por exemplo, \[site=1, local=11\] terão resultados não relacionados comparados a \[site=1, local=11, cor=vermelho\].

```json
{
    "productId": "string",
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "groups": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
    },
}
```

Por exemplo, use \[site=1, local=11, cor=vermelho\] e o campo grupos vazios para obter todos os registros de alocação:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

Use \[site=1, local=11, cor=vermelho\] e grupos \[canal=Online, customerGroup=VIP, região=EUA\] para obter registros de alocação para este grupo:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```
