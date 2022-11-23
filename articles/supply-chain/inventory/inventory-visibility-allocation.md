---
title: Alocação de estoque do Inventory Visibility
description: Este artigo explica como configurar e usar o recurso alocação de estoque, que permite separar o estoque dedicado para garantir que você possa atender a canais ou clientes mais rentáveis.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 449ca0616405ba589b92fba1ef078a4350d1e3b1
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762663"
---
# <a name="inventory-visibility-inventory-allocation"></a>Alocação de estoque do Inventory Visibility

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Plano de fundo e finalidade dos negócios

As organizações geralmente precisam pré-alocar seu estoque disponível para seus canais de vendas, grupos de clientes, regiões e eventos promocionais mais importantes para garantir que o estoque pré-alocado seja protegido contra qualquer outro uso e possa ser consumido apenas por meio de transações de vendas relevantes para o alocação. A alocação de estoque na Visibilidade de estoque é um componente do processo de planejamento operacional de vendas e é feita antes que qualquer atividade de venda real ocorra ou que um pedido de venda seja criado.

Por exemplo, uma empresa chamada Contoso produz uma bicicleta conhecida. Infelizmente, como uma interrupção recente na cadeia de suprimentos afetou todo o estoque em trânsito dessa bicicleta, a Contoso tem apenas um estoque disponível limitado e deve aproveitá-lo da melhor maneira possível. A Contoso faz vendas online e na loja. Em cada canal de vendas, a empresa tem alguns parceiros comerciais importantes (mercados e varejistas grandes) que exigem que uma parte específica do estoque disponível da bicicleta seja salva para eles. Portanto, a empresa de bicicleta deve ser capaz de equilibrar a distribuição de estoque em canais e também gerenciar as expectativas de parceiros VIP. A melhor maneira de atingir ambas as metas é usar a alocação de estoque, de forma que cada canal e varejista possa receber quantidades alocadas específicas que possam ser vendidas para os consumidores posteriormente.

A alocação de estoque tem duas finalidades comerciais básicas:

- **Proteção de estoque (ringfencing)** – As organizações desejam pré-alocar estoque restrito ou limitado para canais priorizados, regiões, clientes VIP e empresas subsidiárias. O recurso de alocação de visibilidade de estoque visa proteger o estoque alocado, de forma que as outras alocações, reservas ou outras demandas de venda não afetem o estoque previamente alocado.
- **Controle de venda excessiva** – o recurso de alocação de visibilidade de estoque visa colocar uma restrição nas quantidades alocadas anteriormente, de modo que a parte destinatária (por exemplo, um canal ou grupo de clientes) não as consuma em excesso quando a transação de vendas real baseada em uma reserva flexível entrar em vigor.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Definição de alocação no serviço de visibilidade de estoque

### <a name="allocation-virtual-pool"></a>Pool de alocação virtual

Embora o recurso de alocação na Visibilidade de estoque não reserve quantidades de estoque físico, ele se refere à quantidade de estoque físico disponível para definir a quantidade inicial de pool virtual *disponível para alocar*. A alocação de estoque na visibilidade de estoque é uma alocação flexível. Ela é realizada antes das transações reais de vendas e não depende de ordens de venda. Por exemplo, você pode alocar o estoque para os canais de vendas mais importantes ou grandes varejistas empresariais antes que os clientes finais visitem o canal de vendas ou a loja de varejo para comprá-lo.

### <a name="difference-between-inventory-allocation-and-soft-reservation"></a>Diferença entre a alocação de estoque e a reserva flexível

[Reservas flexíveis](inventory-visibility-reservations.md) geralmente são vinculadas a transações de vendas reais (linhas de ordem de venda). Tanto as alocações quanto a reserva flexível podem ser usadas de maneira independente, mas se você quiser usá-las juntas, a reserva flexível deve ser feita após a alocação. Recomendamos que você primeiro faça a alocação de estoque e, em seguida, faça uma reserva flexível em relação às quantidades alocadas para atingir o consumo quase em tempo real em relação à alocação. Para obter mais informações, consulte [Consumir como reserva flexível](#consume-to-soft-reserved).

O recurso de alocação de estoque permite que os planejadores de vendas ou os principais gerentes de contas gerenciem e pré-aloquem estoque importante entre grupos de alocação (como canais, regiões e grupos de clientes). Ele também oferece suporte a rastreamento, ajuste e análise de consumo em tempo real em relação a quantidades alocadas, garantindo que o reabastecimento ou a realocação possa ser feita no prazo. Essa capacidade de ter visibilidade em tempo real sobre alocação, consumo e saldo de alocação é especialmente importante em eventos de promoção e venda rápida.

## <a name="terminology"></a>Terminologia

Os seguintes termos e conceitos são úteis em discussões de alocação de estoque:

- **Grupo de alocação** – o grupo que possui a alocação, como um canal de vendas, um grupo de clientes ou um tipo de ordem.
- **Valor do grupo de alocação** – o valor de cada grupo de alocação. Por exemplo, *web* ou *loja* pode ser o valor do grupo de alocação de canais de vendas, enquanto *VIP* ou *normal* pode ser o valor do grupo de alocação do cliente.
- **Hierarquia de alocação** – um meio de combinar grupos de alocação de forma hierárquica. Por exemplo, você pode definir *canal* como nível hierárquico 1, *região* como nível 2 e *grupo de clientes* como nível 3. Durante a alocação de estoque, você deve seguir a sequência da hierarquia de alocação ao especificar o valor do grupo de alocação. Por exemplo, você pode alocar 200 bicicletas vermelhas para o canal da *Web*, a região de *Londres* e o grupo de clientes *VIP*.
- **Disponível para alocar** – o *pool comum virtual* que indica a quantidade disponível para alocação adicional. Esta é uma medida calculada que você pode definir livremente usando sua própria fórmula. Se você também estiver usando o recurso de reserva reversível, é recomendável usar a mesma fórmula para calcular disponível para alocar e disponível para reservar.
- **Alocado** – uma medida física que mostra a cota alocada que pode ser consumida pelos grupos de alocação. Ele é deduzido ao mesmo tempo que se soma a quantidade consumida.
- **Consumido** – uma medida física que indica as quantidades consumidas com relação à quantidade alocada original. À medida que os números são adicionados a essa medida física, a medida física alocada é reduzida automaticamente.

A ilustração a seguir mostra o fluxo de trabalho comercial para alocação de estoque.

![Fluxo de trabalho comercial de alocação da visibilidade de estoque.](media/inventory-visibility-allocation-flow.png "Fluxo de trabalho comercial de alocação da visibilidade de estoque.")

A ilustração a seguir mostra a hierarquia de alocação e os grupos de alocação. O *pool comum virtual* mostrado aqui é a quantidade disponível para alocação.

[<img src="media/inventory-visibility-allocation-hierarchy.png" alt="Inventory Visibility allocation hierarchy." title="Hierarquia de alocação do Visibilidade de estoque" width="720" />](media/inventory-visibility-allocation-hierarchy.png)

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

O processo de configuração do recurso de alocação tem três etapas:

- Ative o recurso no aplicativo Visibilidade de estoque acessando **Configuração \> Gerenciamento de recursos e configurações \> Alocação**.
- Configure a [fonte de dados](inventory-visibility-configuration.md#data-source-configuration) e suas [medidas](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Configure o nome e a hierarquia do grupo de alocação.

### <a name="predefined-data-source"></a>Fonte de dados predefinida

Ao habilitar o recurso de alocação e chamar a API de atualização de configuração, a visibilidade de estoque cria uma fonte de dados predefinida e várias medidas iniciais.

A fonte de dados é chamada de `@iv`. Isso inclui um conjunto de medidas físicas padrão. Você pode visualizá-los no aplicativo Visibilidade de estoque acessando **Configuração \> Fonte de dados**. Você deverá ver **Datasource - @IV**. Expanda a fonte de dados `@iv` para visualizar a lista de medidas físicas iniciais:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Selecione a guia **Medidas calculadas** para visualizar a medida inicial calculada, chamada `@iv.@available_to_allocate`

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Adicionar outras medidas físicas à medida calculada disponível para alocar

Para usar a alocação, você deve configurar corretamente a fórmula para a medida calculada disponível para alocar (`@iv.@available_to_allocate`). Por exemplo, você tem a fonte de dados `fno` e a medida `onordered`, a fonte de dados `pos` e a medida `inbound` e deseja fazer a alocação no estoque disponível para a soma de `fno.onordered` e `pos.inbound`. Nesse caso, `@iv.@available_to_allocate` deve conter `pos.inbound` e `fno.onordered` na fórmula. Este é um exemplo:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

> [!NOTE]
> A fonte de dados `@iv` é uma fonte de dados predefinida e as medidas físicas definidas em `@iv` com o prefixo `@` são medidas predefinidas. Essas medidas são uma configuração predefinida para o recurso de alocação e, portanto, não são alteradas nem excluídas, ou você provavelmente encontrará erros inesperados ao usar o recurso de alocação.
>
> Você pode adicionar novas medidas físicas à medida calculada predefinida `@iv.@available_to_allocate`, mas não deve alterar seu nome.

### <a name="manage-allocation-groups"></a>Gerenciar grupos de alocação

É possível definir no máximo oito nomes de grupos de alocação. Os grupos têm uma hierarquia. Siga estas etapas para exibir e atualizar grupos de alocação.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração** e, na guia **Alocação**, selecione **Editar configuração**. Por padrão, há uma hierarquia de alocação que possui quatro camadas: `Channel` (camada superior), `customerGroup` (segunda camada),`Region` (terceira camada) e `OrderType` (quarta camada).
1. Você pode remover um grupo de alocação existente selecionando **X** ao lado dele. Você também pode adicionar novos grupos de alocação à hierarquia inserindo o nome de cada novo grupo diretamente no campo.

    > [!IMPORTANT]
    > Tenha cuidado ao excluir ou alterar o mapeamento da hierarquia de alocação. Para obter orientação, consulte [Dicas para usar a alocação](#allocation-tips).

1. Quando terminar de configurar o grupo de alocação e as configurações de hierarquia, salve suas alterações e selecione **Atualizar configuração** no canto superior direito. Os valores dos grupos de alocação configurados serão atualizados quando você criar uma alocação usando a interface do usuário ou API POST (/api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate). Detalhes sobre ambas as abordagens são fornecidos posteriormente neste artigo.

Se você usar quatro nomes de grupo e defini-los como \[`channel`, `customerGroup`, `region`, `orderType`\], esses nomes serão válidos para solicitações relacionadas à alocação quando você chamar o API de atualização de configuração.

### <a name="tips-for-using-allocation"></a><a name="allocation-tips"></a>Dicas para usar alocação

- Para cada produto, a função de alocação deve ser usada no mesmo *nível de dimensão*, de acordo com a hierarquia de índice do produto definida na [configuração da hierarquia do índice do produto](inventory-visibility-configuration.md#index-configuration). Por exemplo, suponha que sua hierarquia de índice seja \[`Site`, `Location`, `Color`, `Size`\]. Se você alocar alguma quantidade para um produto no nível de dimensão \[`Site`, `Location`, `Color`\], na próxima vez que você quiser alocar este produto, você também deve alocar no mesmo nível, \[`Site`, `Location`, `Color`\]. Se você usar o nível \[`Site`, `Location`, `Color`, `Size`\] or \[`Site`, `Location`\], os dados serão inconsistentes.
- **Modificando grupos de alocação e a hierarquia:** se os dados de alocação já existirem no sistema, a exclusão de grupos de alocação existentes ou uma mudança na hierarquia do grupo de alocação corromperá o mapeamento existente entre os grupos de alocação. Portanto, certifique-se de limpar manualmente todos os dados antigos antes de atualizar sua nova configuração. No entanto, como a adição de novos grupos de alocação à hierarquia mais baixa não afeta os mapeamentos existentes, você não precisará limpar os dados.
- A alocação terá sucesso somente se o produto tiver uma quantidade `available_to_allocate` positiva.
- Para alocar produtos de um grupo de *nível de alocação* alto para um subgrupo, use a API `Reallocate`. Por exemplo, você tem uma hierarquia de grupos de alocação \[`channel`, `customerGroup`, `region`, `orderType`\] e deseja alocar algum produto do grupo de alocação \[Online, VIP\] para o subgrupo de alocação \[Online, VIP, EU\], use a API `Reallocate` para mover a quantidade. Se você usar a API `Allocate`, ela alocará a quantidade do pool comum virtual.
- Para visualizar a disponibilidade geral do produto (o pool comum), use a API [consulta disponível](inventory-visibility-api.md#query-on-hand) para solicitar a quantidade de estoque *disponível para alocação*. Você pode então tomar decisões de alocação com base nessas informações.

## <a name="use-the-allocation-api"></a><a name="using-allocation-api"></a>Usar a API de alocação

No momento, cinco APIs de alocação estão abertas:

- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate** – Essa API é usada para criar a alocação inicial.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/unallocate** – Essa API é usada para reverter ou remover as quantidades alocadas.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/reallocate** – Essa API é usada para mover a quantidade alocada de uma alocação existente para outros grupos de alocação.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/consume** – Essa API é usada para deduzir (usar) a quantidade alocada.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/query** – Essa API é usada para verificar os registros de alocação existentes em relação aos grupos de alocação e hierarquia.

### <a name="allocate"></a>Alocar

Chame a API `Allocate` para alocar um produto com dimensões específicas. Este é o esquema do corpo da solicitação.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test101",
    "productId": "Bike",
    "groups": {
        "channel": "Web",
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

### <a name="unallocate"></a>Desalocar

Use a API `Unallocate` para reverter a operação `Allocate`. A quantidade negativa não é permitida em uma operação `Allocate`. O corpo de `Unallocate` é idêntico ao corpo de `Allocate`.

### <a name="reallocate"></a>Realocar

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
    "groups": {
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
    "id": "test102",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "groups": {
        "channel": "Web",
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

### <a name="consume"></a>Consumir

Use a API `Consume` para lançar a quantidade de consumo em relação à alocação. Por exemplo, você pode usar esta API para mover a quantidade alocada para algumas medidas reais. Este é o esquema do corpo da solicitação.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test103",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
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

### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Consumir como uma reserva flexível

A API `Consume` também pode consumir a quantidade alocada como uma reserva flexível. Nesse caso, a operação `Consume` reduzirá a quantidade alocada e, depois, fará uma reserva flexível para essa quantidade. Para usar essa abordagem, você também deve usar o recurso [reserva flexível](inventory-visibility-reservations.md) de visibilidade de estoque.

Por exemplo, você definiu uma medida de reserva flexível como `iv.softreserved`. A seguinte fórmula é usada para a medida calculada de disponível para reservar:

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
    "groups": {
        "channel": "Web",
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

### <a name="query"></a>Consulta

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
        "channel": "Web",
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
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

## <a name="use-the-allocation-user-interface"></a>Usar a interface do usuário de alocação

Você pode gerenciar manualmente as alocações por meio da interface do usuário abrindo o aplicativo Visibilidade de estoque e acessando **Visibilidade operacional \> Alocação**. Lá, você pode executar qualquer uma das ações descritas nas subseções a seguir.

### <a name="create-an-allocation"></a>Criar uma alocação

Siga estas etapas para criar uma alocação na página **Alocação** do aplicativo Visibilidade de estoque.

1. Selecione **Alocar**.
1. Defina os campos base, as dimensões e os valores dos grupos de alocação de destino. (Ao selecionar a fonte de dados coletada na seção **Dimensões**, primeiro use a lista suspensa para especificar as dimensões (por exemplo, `siteId`). Em seguida, insira os valores de dimensão nos campos exibidos.)
1. Selecione **enviar**.

### <a name="consume-an-allocation"></a>Consumir uma alocação

Selecione **Consumir** para consumir uma alocação. Para garantir que você consuma dentro do grupo de alocação e da hierarquia corretos, insira os mesmos conjuntos de organização e detalhes de dimensão inseridos ao criar a alocação.

### <a name="reallocate-an-allocation"></a>Realocar uma alocação

Selecione **Realocar** para mover a quantidade alocada existente de um conjunto de grupos de alocação para outro.

### <a name="query-existing-allocations"></a>Consultar alocações existentes

Selecione **Consultar** e insira os valores de produto, organização, dimensão e grupo de alocação para obter os resultados da consulta de alocações existentes.
