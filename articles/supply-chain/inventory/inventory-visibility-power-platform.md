---
title: Aplicativo Visibilidade de Estoque
description: Este tópico descreve como usar o aplicativo Visibilidade de Estoque.
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
ms.openlocfilehash: cc09dd82547ec42041889e9a96662cd17549a3ea
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344993"
---
# <a name="inventory-visibility-app"></a>Aplicativo Visibilidade de Estoque

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tópico descreve como usar o aplicativo Visibilidade de Estoque.

A Visibilidade de Estoque fornece um aplicativo baseado em modelo para visualização. O aplicativo contém três páginas: **Configuração**, **Visibilidade operacional** e **Resumo de estoque**. Ele tem os seguintes recursos:

- Ele fornece uma IU (interface do usuário) para configuração disponível e configuração de reserva flexível.
- Ele oferece suporte a consultas de estoque disponível em tempo real em várias combinações de dimensões.
- Ele fornece uma interface do usuário para o lançamento de solicitações de reserva.
- Ele fornece uma exibição personalizada do estoque disponível para produtos juntamente com todas as dimensões

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, instale e configure o Suplemento Visibilidade de Estoque conforme descrito em [Configurar Visibilidade do Estoque](inventory-visibility-setup.md).

## <a name="configuration"></a><a name="configuration"></a>Configuração

A página **Configuração** ajuda você a definir a configuração disponível e a configuração de reserva flexível. Após a instalação do suplemento, a configuração padrão incluirá o valor do Microsoft Dynamics 365 Supply Chain Management (a fonte de dados `fno`). Você pode analisar a configuração padrão. Além disso, com base nos requisitos comerciais e nos requisitos de lançamento de estoque do sistema externo, você poderá modificar a configuração no [Dataverse](/powerapps/maker/common-data-service/data-platform-intro) para padronizar a forma como as alterações de estoque podem ser lançadas, organizadas e consultadas em vários sistemas.

### <a name="define-data-sources"></a>Definir fontes de dados

Você define cada *fonte de dados* que deseja integrar com Visibilidade de Estoque. Visibilidade de Estoque oferece suporte à integração com várias fontes de dados, como o seu sistema de PDV (ponto de venda), o Supply Chain Management e outros sistemas externos. Por padrão, o Supply Chain Management é configurado como uma fonte de dados padrão (`fno`) no Visibilidade de Estoque.

Para adicionar uma fonte de dados, siga estas etapas.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Fonte de Dados**, selecione **Nova Fonte de Dados** para adicionar uma fonte de dados.

> [!NOTE]
> Ao adicionar uma fonte de dados, valide o nome da fonte de dados, as medidas físicas e os mapeamentos de dimensão antes de atualizar a configuração para o serviço Visibilidade de Estoque. Não será possível modificar essas configurações depois de selecionar **Atualizar Configuração**.

### <a name="set-up-dimension-mappings"></a>Configurar mapeamentos de dimensão

Visibilidade de Estoque fornece uma lista de dimensões básicas que podem ser mapeadas desde as dimensões da sua fonte de dados. Trinta e três dimensões disponíveis para mapeamento.

- Por padrão, se você estiver usando o Supply Chain Management como uma de suas fontes de dados, 13 dimensões serão mapeadas para as dimensões padrão do Supply Chain Management. Doze outras dimensões (`inventDimension1` a `inventDimension12`) são mapeadas para dimensões personalizadas no Supply Chain Management. As oito dimensões restantes são dimensões estendidas que podem ser mapeadas para fontes de dados externas.
- Se não usar o Supply Chain Management como uma de suas fontes de dados, você poderá mapear as dimensões livremente. A tabela a seguir mostra a lista completa de dimensões disponíveis.

> [!NOTE]
> Se a dimensão não estiver na lista de dimensões padrão e se você estiver usando uma fonte de dados externa, recomendamos o uso de `ExtendedDimension1` a `ExtendedDimension8` para fazer o mapeamento.

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
| Outros(as) | `VersionId` |
| Estoque (Personalizado) | `InventDimension1` a `InventDimension12` |
| Outros(as) | `ExtendedDimension1` a `ExtendedDimension8` |

Para adicionar mapeamentos de dimensão, siga estas etapas.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Fonte de Dados**, na seção **Mapeamentos de Dimensão**, selecione **Adicionar** para adicionar mapeamentos de dimensão.
1. No campo **Nome da Dimensão**, especifique a dimensão de origem.
1. No campo **Para Dimensão Base**, selecione a dimensão no Visibilidade de Estoque que você deseja mapear.
1. Selecione **Salvar**.

![Adição de mapeamentos de dimensão](media/inventory-visibility-dimension-mapping.png "Adição de mapeamentos de dimensão")

Por exemplo, se a sua fonte de dados incluir uma dimensão de cor do produto, você poderá mapeá-la para a dimensão base `ColorId` a fim de adicionar uma dimensão personalizada `ProductColor` à fonte de dados `exterchannel`. Em seguida, ela será mapeada para a dimensão base `ColorId`.

## <a name="create-a-physical-measure"></a>Criar uma medida física

Quando uma fonte de dados lança uma alteração de estoque em Visibilidade de Estoque, ela lança essa alteração usando *medidas físicas*. As medidas físicas são modificadores que refletem os status de transação de estoque resumidos. As consultas podem ser baseadas nas medidas físicas.

Visibilidade de Estoque tem uma lista de medidas físicas padrão. Essas medidas físicas padrão são tiradas dos status da transação de estoque na página **Lista de disponíveis** no Supply Chain Management (**Gerenciamento de Estoque \> Consultas e Relatório \> Lista de disponíveis**).

| Modificador | Organização |
|---|---|
| `PhysicalInvent` | Estoque Físico |
| `ReservPhysical` | Físico Reservado |
| `AvailPhysical` | Físico disponível |
| `ReservOrdered` | Encomendado Reservado |
| `PostedQty` | Quantidade Lançada |
| `Deducted` | Deduzido |
| `Picked` | Separada |
| `Received` | Recebidos |
| `Registered` | Registrado |
| `Arrived` | Admitido |
| `Ordered` | Encomenda feita |
| `OnOrder` | Em Ordem |
| `QuotationReceipt` | Recebimento de Cotação |
| `QuotationIssue` | Saída de Cotação |

Se a fonte de dados for o Supply Chain Management, você não precisará recriar as medidas físicas padrão. No entanto, para fontes de dados externas, você poderá criar novas medidas físicas seguindo estas etapas.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Fonte de Dados**, na seção **Medidas Físicas**, selecione **Adicionar**, especifique um nome de medida de origem e salve as alterações.

## <a name="define-the-product-hierarchy-index"></a>Definir o índice da hierarquia de produtos

Ao configurar grupos de dimensões agregados, você poderá usar Visibilidade de Estoque para consultar o status do estoque disponível. Em Visibilidade de Estoque, cada grupo de dimensões é conhecido como um *índice*. Cada índice corresponde a um número definido. Você pode decidir quais dimensões serão usadas para configurar a indexação, de acordo com a forma como será consultada em Visibilidade de Estoque.

Para configurar seu índice de hierarquia de produtos, siga estas etapas.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Índice de Hierarquia de Produtos**, na seção **Mapeamentos de Dimensão**, selecione **Adicionar** para adicionar mapeamentos de dimensão.
1. Por padrão, uma lista de índices é fornecida. Para modificar um índice existente, selecione **Editar** ou **Adicionar** na seção do índice relevante. Para criar um novo conjunto de índices, selecione **Novo conjunto de índices**. Para cada linha em cada conjunto de índices, no campo **Dimensão**, selecione na lista de dimensões base. Os valores para os campos a seguir são gerados automaticamente:

    - **Número do conjunto** – as dimensões que pertencem ao mesmo grupo (índice) serão agrupadas, e o mesmo número do conjunto será alocado para elas.
    - **Hierarquia** – a hierarquia é usada para definir as combinações de dimensões com suporte que podem ser consultadas em um grupo de dimensões (índice). Por exemplo, se você configurar um grupo de dimensões com uma sequência de hierarquias de *Estilo*, *Cor* e *Tamanho*, o sistema dará suporte ao resultado de três grupos de consulta. O primeiro grupo é somente estilo. O segundo grupo é uma combinação de estilo e cor. E o terceiro grupo é uma combinação de estilo, cor e tamanho. Não há suporte para as outras combinações.

Para obter mais informações, consulte [Configuração de hierarquia de índice de produto](inventory-visibility-configuration.md#index-configuration).

### <a name="example"></a>Exemplo

Esta seção fornece um exemplo que mostra o funcionamento da hierarquia. A tabela a seguir fornece uma lista de estoque disponível para este exemplo.

| Item  | Estilo | Cor | Tamanho | Quantidade |
|---|---|---|---|---|
| I0001 | Largo | Preto | Pequeno | 1 |
| I0001 | Largo | Preto | Grande | 2 |
| I0001 | Largo | Vermelho | Pequeno | 3 |
| I0001 | Regular | Preto | Pequeno | 4 |
| I0001 | Regular | Preto | Grande | 5 |
| I0001 | Regular | Vermelho | Pequeno | 6 |
| I0001 | Regular | Vermelho | Grande | 7 |

A tabela a seguir mostra como a hierarquia de índice é configurada.

| Chave | Número do conjunto | Hierarquia |
|---|---|---|
| `StyleId` | 1 | 1 |
| `ColorId` | 1 | 2 |
| `SizeId` | 1 | 3 |

Com base nas configurações anteriores, a combinação de dimensões para a consulta de Visibilidade de Estoque é *Estilo*, *Cor* e *Tamanho*. A configuração de hierarquia permite que sistemas externos consultem o estoque disponível das seguintes maneiras:

- `()`– agrupado por todos. Esta é a saída:

    - I0001, 28

- `(StyleId)` - agrupar por estilo. Esta é a saída:

    - I0001, Largo, 6
    - I0001, Regular, 22

- `(StyleId, ColorId)` – agrupado pela combinação de estilo e cor. Esta é a saída:

    - I0001, Largo, Preto, 3
    - I0001, Largo, Vermelho, 3
    - I0001, Regular, Preto, 9
    - I0001, Regular, Vermelho, 13

- `(StyleId, ColorId, SizeId)` – agrupado pela combinação de estilo, cor e tamanho. Esta é a saída:

    - I0001, Largo, Preto, Pequeno, 1
    - I0001, Largo, Preto, Grande, 2
    - I0001, Largo, Vermelho, Pequeno, 3
    - I0001, Regular, Preto, Pequeno, 4
    - I0001, Regular, Preto, Grande, 5
    - I0001, Regular, Vermelho, Pequeno, 6
    - I0001, Regular, Vermelho, Grande, 7

## <a name="set-up-a-custom-calculated-measure"></a>Configurar uma medida calculada personalizada

Você pode usar Visibilidade de Estoque para consultar tanto as medidas físicas de estoque como as *medidas calculadas personalizadas*.

A configuração permite que você defina um conjunto de modificadores adicionados ou subtraídos para obter a quantidade de saída agregada total.

1. Entre no seu ambiente do Power Apps e abra **Visibilidade de Estoque**.
1. Abra a página **Configuração**.
1. Na guia **Medida Calculada**, selecione **Nova Medida de Cálculo** para adicionar uma medida calculada. Defina os campos conforme descrito na tabela a seguir.

    | Campo | Alíquota |
    |---|---|
    | Nome da nova medida calculada | Insira o nome da medida calculada. |
    | Fonte de dados | O sistema de consulta é uma fonte de dados. |
    | Fonte de dados modificadora | Insira a fonte de dados do modificador. |
    | Modificador | Insira o nome do modificador. |
    | Tipo de modificador | Selecione o tipo de modificador (*Adição* ou *Subtração*). |

A tabela a seguir mostra a um exemplo da medida calculada personalizada `MyCustomAvailableforReservation`. Para obter mais informações sobre este exemplo, consulte [Configuração da fonte de dados](inventory-visibility-configuration.md#data-source-configuration).

| Fonte de dados de medida calculada | Medida calculada | Fonte de dados modificadora | Modificador | Tipo de modificador |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `Exteexterchannelrchannel` | `reserved` | `Subtraction` |

### <a name="set-up-a-soft-reservation-mapping"></a><a name="setup-reservation-mapping"></a>Configurar um mapeamento de reserva flexível

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Antes de editar a guia **Mapeamento de Reserva Flexível**, você deverá ativar o recurso *OnHandReservation* na guia **Gerenciamento de Recursos**.

Ao configurar o mapeamento da medida física para a medida calculada, você permitirá que o serviço Visibilidade de Estoque valide automaticamente a disponibilidade da reserva, com base na medida física.

Antes de configurar esse mapeamento, as medidas físicas, as medidas calculadas e suas fontes de dados deverão ser definidas nas guias **Fonte de dados** e **Medida calculada** da página de **Configuração** no Power Apps (conforme descrito anteriormente neste tópico).

Para definir o mapeamento de reserva flexível, siga estas etapas.

1. Defina a medida física que serve como medida da reserva flexível (por exemplo, `softreservordered`).
1. Na guia **Medida calculada** da página **Configuração**, defina a medida calculada AFR (*disponível para reserva*) que contém a fórmula de computação AFR que você deseja mapear para a medida física. Por exemplo, você pode configurar `availforreserv` (disponível para reserva) para que ele seja mapeado para a medida física `softreservordered` definida anteriormente. Dessa forma, você poderá descobrir quais quantidades têm o status de estoque `softreservordered` estarão disponíveis para reserva. A tabela a seguir mostra a fórmula de computação AFR.

    | Modificador | Fonte de dados | Medição |
    |---|---|---|
    | `Addition` | `fno` | `availphysical` |
    | `Addition` | `pos` | `inbound` |
    | `Subtraction` | `pos` | `outbound` |
    | `Subtraction` | `iv` | `softreservordered` |

1. Abra a página **Configuração**.
1. Na guia **Mapeamento de Reserva Flexível**, configure o mapeamento da medida física para a medida calculada. No exemplo anterior, você poderia usar as configurações a seguir para mapear `availforreserv` para a medida física `softreservordered` definida anteriormente.

    | Fonte de dados de medida física | Medida física | Disponível para a fonte de dados de reserva | Disponível para medida calculada da reserva |
    |---|---|---|---|
    | `iv` | `softreservordered` | `iv` | `availforreserv` |

### <a name="set-up-a-soft-reservation-hierarchy"></a><a name="setup-reservation-hierarchy"></a>Configurar uma hierarquia de reservas flexível

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Antes de editar a guia **Hierarquia de Reservas Flexível**, você deverá ativar o recurso *OnHandReservation* na guia **Gerenciamento de Recursos**.

A hierarquia de reservas descreve a sequência de dimensões que deve ser especificada quando as reservas são feitas. Ele funciona da mesma forma que a hierarquia de índice do produto funciona para consultas disponíveis.

A hierarquia de reservas pode ser diferente da hierarquia de índices disponível. Essa independência permite implementar o gerenciamento de categorias, no qual os usuários podem dividir as dimensões em detalhes para especificar os requisitos para fazer reservas mais precisas.

#### <a name="example"></a>Exemplo

A hierarquia de reservas a seguir está configurada no seu sistema.

| Dimensão | Hierarquia |
|---|---|
| `ColorId` | 1 |
| `SizeId ` | 2 |
| `StyleId` | 3 |

Dada essa hierarquia de reserva, você poderá fazer reserva nas seguintes ordens de dimensão:

- `()` – nenhuma dimensão é fornecida.
- `(ColorId)`
- `(ColorId, SizeId)`
- `(ColorId, SizeId, StyleId)`

A ordem de dimensão deve seguir estritamente a sequência da hierarquia de reservas, dimensão por dimensão. Por exemplo, as reservas com `(ColorId, StyleId)` não serão permitidas neste exemplo, porque essa sequência não está definida na hierarquia de reservas.

### <a name="control-feature-management"></a><a name="feature-switch"></a>Controlar o gerenciamento de recursos

O Suplemento Visibilidade de Estoque fornece recursos como *OnHandReservation* e *OnHandMostSpecificBackgroundService*. Por padrão, esses recursos estão desativados. Para usá-los, abra a página **Configuração** no Power Apps e, em seguida, na guia **Gerenciamento de Recursos**, ative-os.

### <a name="complete-and-update-the-configuration"></a>Concluir e atualizar a configuração

Depois de concluir a configuração, você deverá confirmar todas as alterações em Visibilidade de Estoque. Para confirmar as alterações, selecione **Atualizar Configuração** no canto superior direito da página **Configuração** no Power Apps.

Na primeira vez que você seleciona **Atualizar Configuração**, o sistema solicita suas credenciais.

- **ID do Cliente** – a ID do aplicativo do Azure criada para Visibilidade de Estoque.
- **ID de Locatário** – sua ID de locatário do Azure.
- **Segredo do Cliente** – o segredo do aplicativo do Azure criado para Visibilidade de Estoque.

Depois de entrar, a configuração será atualizada no serviço Visibilidade de Estoque.

> [!NOTE]
> Valide o nome da fonte de dados, as medidas físicas e os mapeamentos de dimensão antes de atualizar a configuração para o serviço Visibilidade de Estoque. Não será possível modificar essas configurações depois de selecionar **Atualizar Configuração**.

### <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Localizar o ponto de extremidade de serviço

Se você não souber o ponto de extremidade de serviço de Visibilidade de Estoque correto, abra a página **Configuração** no Power Apps e selecione **Mostrar Ponto de Extremidade de Serviço** no canto superior direito. A página mostrará o ponto de extremidade de serviço correto.

## <a name="operational-visibility"></a>Visibilidade operacional

A página **Visibilidade Operacional** fornece os resultados de uma consulta de estoque disponível em tempo real, com base em várias combinações de dimensão. Quando o recurso *OnHandReservation* estiver ativado, você também poderá lançar solicitações de reserva na página **Visibilidade Operacional**.

### <a name="on-hand-query"></a>Consulta de disponíveis

A guia **Consulta de Disponíveis** mostra os resultados de uma consulta de estoque disponível em tempo real.

Quando você seleciona a guia **Consulta de Disponíveis**, o sistema solicita suas credenciais para obter o token de portador necessário para consultar o serviço Visibilidade de Estoque. Você pode simplesmente colar o token de portador no campo **BearerToken** e fechar a caixa de diálogo. Em seguida, você pode lançar uma solicitação de consulta de disponíveis.

Se o token de portador não for válido ou se tiver expirado, você deverá colar um novo no campo **BearerToken**. Insira os valores corretos de **ID do Cliente**, **ID do Locatário**, **Segredo do Cliente** e selecione **Atualizar**. O sistema receberá automaticamente um novo token de portador válido.

Para lançar uma consulta disponível, insira a consulta no corpo da solicitação. Use o padrão descrito em [Consultar usando o método post](inventory-visibility-api.md#query-with-post-method).

![Configurações de consulta de disponíveis](media/inventory-visibility-query-settings.png "Configurações de consulta de disponíveis")

### <a name="reservation-posting"></a>Lançamento de reserva

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Use a guia **Lançamento de reserva** para lançar uma solicitação de reserva. Para poder lançar uma solicitação de reserva, você deverá ativar o recurso *OnHandReservation*. Para obter mais informações sobre esse recurso, consulte [Reservas de Visibilidade de Estoque](inventory-visibility-reservations.md).

Para lançar uma solicitação de reserva, você deverá inserir um valor no corpo da solicitação. Use o padrão descrito em [Criar um evento de reserva](inventory-visibility-api.md#create-one-reservation-event). Em seguida, selecione **Lançar**. Para exibir os detalhes da resposta da solicitação, selecione **Mostrar Detalhes**. Você também pode obter o valor **reservationId** dos detalhes da resposta.

## <a name="inventory-summary"></a>Resumo de estoque

**Resumo de estoque** é uma exibição personalizada da *Entidade de Soma de Estoque Disponível*. Ela fornece um resumo de estoque para produtos juntamente com todas as dimensões. Usando o **Filtro Avançado** fornecido pelo Dataverse, será possível criar uma exibição pessoal que mostre as linhas importantes para você. As opções de filtro avançado permitem criar uma ampla variedade de exibições, das simples às complexas. Elas também permitem adicionar condições agrupadas e aninhadas aos filtros.

Para saber mais sobre como usar o **Filtro Avançado**, consulte [Editar ou criar exibições pessoais usando filtros de grade avançados](/powerapps/user/grid-filters-advanced)

A parte superior da exibição personalizada fornece três campos: **Dimensão Padrão**, **Dimensão Personalizada** e **Medida**. Você pode usar esses campos para controlar quais colunas são visíveis.

Você pode selecionar o cabeçalho da coluna para filtrar ou classificar o resultado atual.

A parte inferior da exibição personalizada mostra informações como "50 registros (29 selecionados)" ou "50 registros". Essas informações se referem aos registros atualmente carregados desde o resultado de **Filtro Avançado**. O texto "29 selecionados" se refere ao número de registros selecionados usando o filtro de cabeçalho de coluna para os registros carregados.

Na parte inferior da exibição, há um botão **Carregar mais** que pode ser usado para carregar mais registros do Dataverse. O número padrão de registros carregados é 50. Quando você selecionar **Carregar mais**, os próximos 1.000 registros disponíveis serão carregados na exibição. O número no botão **Carregar Mais** indica os registros carregados no momento e o número total de registros para o resultado de **Filtro Avançado**.

![Resumo de Estoque](media/inventory-visibility-onhand-list.png "Resumo de Estoque")
