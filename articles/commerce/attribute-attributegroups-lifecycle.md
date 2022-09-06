---
title: Gerenciar atributos e grupos de atributos
description: Este artigo descreve como gerenciar atributos e grupos de atributos para descrever os produtos e suas características no Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.openlocfilehash: aad448ea733aabdff3dc4438dcb682d49e0665c0
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9386963"
---
# <a name="manage-attributes-and-attribute-groups"></a>Gerenciar atributos e grupos de atributos

[!include [banner](includes/banner.md)]

Este artigo descreve como gerenciar atributos e grupos de atributos para descrever os produtos e suas características no Microsoft Dynamics 365 Commerce.

Os *Atributos* fornecem uma maneira de descrever produtos e suas características em campos definidos pelo usuário. Os exemplos incluem tamanho da memória, capacidade do disco rígido e conformidade com o Energy Star.

Os atributos podem ser associados a várias entidades do Commerce, como categorias de produto e canais, e valores padrão podem ser definidos para eles. Quando os atributos são associados a categorias ou canais de produtos, os produtos herdam esses atributos e seus valores padrão. Os valores do atributo padrão podem ser substituídos no nível de produto individual, de canal de varejo ou em um catálogo.

Por exemplo, uma televisão típica pode ter os seguintes atributos.

| Categoria   | Atributo           | Valores permitidos                        | Valor padrão |
|------------|---------------------|-------------------------------------------|---------------|
| TV e vídeo | Marca               | Qualquer valor de marca válido                     | Nenhum          |
| TV         | Tamanho de Tela         | 20–85 polegadas                              | 55 polegadas     |
|            | Resolução Vertical | 4K (2160p), HD Total (1080p) ou HD (720p) | 4K (2160p)    |
|            | Taxa de Atualização da Tela | 60hz, 120hz ou 240hz                     | 60hz          |
|            | Entradas HDMI         | 0–10                                      | 3             |

## <a name="attributes-and-attribute-types"></a>Atributos e tipos de atributos

Os atributos são baseados nos *tipos de atributos*. Um tipo de atributo identifica o tipo de dados que pode ser inserido para um atributo específico. Os seguintes tipos de atributo têm suporte no Commerce:

- **Moeda** – Este tipo dá suporte a um valor de moeda. Ele pode ser limitado (isto é, pode dar suporte a um intervalo de valores), ou pode ser deixado aberto.
- **Data/Hora** – Este tipo dá suporte a valores de data e hora. Pode ser limitado ou deixado aberto.
- **Decimal** – Este tipo dá suporte a um valor numérico que inclui casas decimais. Ele também dá suporte a uma unidade de medida. Pode ser limitado ou deixado aberto.
- **Inteiro** – Este tipo dá suporte a um valor numérico. Ele também dá suporte a uma unidade de medida. Pode ser limitado ou deixado aberto.
- **Texto** – Este tipo dá suporte a um valor de texto. Ele também oferece suporte a um conjunto predefinido de valores possíveis quando a configuração de **Lista fixa** é habilitada.
- **Booliano** – Este tipo dá suporte a um valor binário (**true** ou **false**).
- **Referência** – Este tipo faz referência a outros atributos.

> [!NOTE]
> Devido às [limitações do índice de pesquisa do Azure](/rest/api/searchservice/data-type-map-for-indexers-in-azure-search), o tipo de atributo **Decimal** não é suportado para experiências de pesquisa habilitadas para nuvem. O Azure Cognitive Search não oferece suporte à conversão de tipos de atributos **Decimais** para tipos de campos de índice de destino **Edm.Double**, pois essa conversão diminuiria a precisão.

### <a name="set-up-attribute-types"></a>Configurar tipos de atributos

Para configurar tipos de atributos, siga as etapas deste procedimento de exemplo.

1. Entre no Commerce Headquarters como um gerente de mercadorias.
1. Acesse **Gerenciamento de informações sobre o produto \> Configuração \> Categorias e atributos \> Tipos de atributos**.
1. No Painel de Ações, selecione **Novo**.
1. No campo **Nome do tipo de atributo**, insira **Tipo de sacola**.
1. No campo **Tipo**, selecione **Texto**.
1. Defina a opção **Lista fixa** como **Sim**.
1. Na Guia Rápida **Valores**, selecione **Adicionar**.
1. Na nova linha, no campo **Valor**, digite **Satchel**.
1. Adicione mais cinco linhas. No campo **Valor** de cada uma, informe um valor diferente: **Bolsa**, **Mala**, **Mochila**, **Mensageiro** ou **Carteira**.
1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ações, selecione **Novo**.
1. No campo **Nome do tipo de atributo**, insira **Marca de óculos escuros**.
1. No campo **Tipo**, selecione **Texto**.
1. Defina a opção **Lista fixa** como **Sim**.
1. Na Guia Rápida **Valores**, selecione **Adicionar**.
1. Na nova linha, no campo **Valor**, digite **Ray ban**.
1. Adicione mais duas linhas. No campo **Valor** de cada uma, informe um valor diferente: **Aviador** ou **Oakley**.
1. No Painel de ações, selecione **Salvar**.

![Página dos tipos de atributos.](media/AttributeType_2022Series.png)

### <a name="set-up-an-attribute"></a>Configurar um atributo

Para configurar um atributo, siga as etapas deste procedimento de exemplo.

1. Entre no Commerce Headquarters como um gerente de mercadorias.
1. Vá para **Gerenciamento de informações sobre o produto \> Configuração \> Categorias e atributos \> Atributos**.
1. No Painel de Ações, selecione **Novo**.
1. No campo **Nome**, digite **Tipo de sacola**.
1. No campo **Tipo de atributo**, selecione **Tipo de sacola**.
1. No Painel de ações, selecione **Salvar**.

![Página de atributos.](media/Attribute_2022Series.png)

## <a name="attribute-metadata"></a>Metadados de atributo

Os *Metadados de atributo* permitem selecionar opções para especificar como os atributos de cada produto devem se comportar. Por exemplo, você pode especificar se os atributos são obrigatórios, se podem ser usados para pesquisas e como filtro.

Para produtos, as configurações de metadados de atributo podem ser substituídas no nível do canal.

Uma página de **Atributos** tem várias opções que são relacionadas aos metadados do atributo. Por exemplo, se você definir a opção **Pode ser refinado** como **Sim** em **Atribuir metadados para canais do Commerce**, o atributo será mostrado para refinamento ou filtragem de produtos em resultados de pesquisa e páginas de pesquisa de categorias. Para configurar um atributo como refinável, primeiro você deve selecionar **Configurações do filtro** no Painel de Ações e confirmar as configurações do filtro do atributo.

## <a name="filter-settings-for-attributes"></a>Configurações de filtro para atributos

As configurações de filtro para atributos permitem definir como esses filtros do atributos são mostrados no ponto de venda (PDV). Para acessar as configurações de filtro de um atributo, na página **Atributos**, no Painel de Ação, selecione **Configurações do filtro**.

A página **Configurações do filtro** inclui os seguintes campos:

- **Nome** – Por padrão, este campo é definido como o nome do atributo. No entanto, você pode alterar o valor.
- **Opção de exibição** – As seguintes opções estão disponíveis:

    - **Valor único** – Esta opção está disponível para os seguintes tipos de atributos: **Booliano**, **Moeda**, **Decimal**, **Inteiro** e **Texto**. Ele permite que apenas um único valor seja selecionado para refinadores em páginas de lista de produtos, como pesquisa de categorias e páginas de resultados da pesquisa de produtos.
    - **Diversos valores** – Esta opção está disponível para os seguintes tipos de atributos: **Moeda**, **Decimal**, **Inteiro** e **Texto**. Ela permite a seleção de diversos valores para o atributo no cliente para refinamento.

- **Controle de exibição** – As seguintes opções estão disponíveis:

    - **Lista** – Esta opção está disponível para todos os tipos de atributos.
    - **Intervalo** – Esta opção está disponível para os seguintes tipos de atributos: **Moeda**, **Decimal** e **Inteiro**.
    - **Controle deslizante** – Esta opção está disponível para os seguintes tipos de atributos: **Moeda**, **Decimal** e **Inteiro**.
    - **Controle deslizante com barras** – Esta opção está disponível para os seguintes tipos de atributos: **Moeda**, **Decimal** e **Inteiro**.

- **Valor de limite** – Esta configuração será necessária se você tiver selecionado **Intervalo** como tipo de controle de exibição. Você pode definir valores usando um ponto-e-vírgula (;) como delimitador.

    Por exemplo, para um atributo **Volume do Malote** que tem um tipo de **Inteiro**, o valor limite pode ser **10; 20; 50; 100; 200; 500; 1000; 5000**. Nesse caso, o PDV mostrará os intervalos a seguir. Os intervalos que não tiverem nenhum produto no conjunto de resultados aparecerão esmaecidos.

    - Menos de 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - 500 ou mais

As configurações de filtro para atributos são aplicáveis somente a atributos de produtos e podem ser usadas para refinar os resultados de pesquisa de categorias e de produtos. Elas não se aplicam à pesquisa de clientes ou a pesquisas de ordens, embora os mesmos atributos possam ser usados para enriquecer as informações sobre clientes ou ordens.

Nos módulos padrão do Commerce, nenhum suporte pronto para uso está disponível para configurações de filtro do **Controle de exibição**, como **Intervalo**, **Controle Deslizante** e **Controle deslizante com barras**. As configurações de **Intervalo** e **Controle Deslizante** continuam sendo suportadas para soluções PDV, enquanto que a configuração do **Controle deslizante com barras** é aplicável a lojas online legadas do SharePoint e continua disponível para cenários de integração e personalizados de terceiros.

Recomendamos que os atributos refináveis tenham um atributo do tipo **Texto** no qual a **Lista fixa** é habilitada e que você mantenha a lista gerenciável (até 100 – 200 valores exclusivos). Se um refinador tiver 1.000 ou mais valores exclusivos, é mais apropriado usar um atributo do tipo de **Texto** no qual a opção de **Lista fixa** está desativada.

As traduções são críticas para nomes de atributos e seus valores. Para atributos do tipo de **Texto** em que a opção de **Lista fixa** está habilitada, você pode definir traduções para os valores de atributo em **Tipo de atributo**. Para cada outro tipo de atributo, você pode definir traduções na página onde você define os valores de atributo. Por exemplo, para um atributo do tipo de **Texto**, você pode definir traduções para o valor padrão na página **Atributos** do atributo. No entanto, se você substituir o valor padrão no nível de produto, poderá definir traduções para o atributo na página **Atributos do produto**.

Depois que um atributo for marcado como refinável para um canal, você não deverá atualizar o tipo de atributo. Caso contrário, você afetará a publicação de dados de produtos para o índice de pesquisa. Em vez disso, recomendamos que você crie um novo atributo para um novo tipo de refinador e remova o atributo anterior, removendo-o de outros grupos de atributos.

A pesquisa por atributos é suportada, mas busca resultados somente para correspondências exatas de palavras de pesquisa. Por exemplo, um atributo **Tecido** tem um valor de **Algodão cashmere**. Se um cliente procurar por "Cash", nenhum produto que tenha **Algodão cashmere** como tecido será recuperado. No entanto, se um cliente pesquisar por "Cashmere," "Algodão" ou "Algodão Cashmere", os produtos que têm **Algodão cashmere** como tecido serão recuperados.

### <a name="additional-attribute-metadata-options"></a>Opções de metadados de atributos adicionais

> [!NOTE]
> Essas opções de metadados de atributos são aplicáveis somente à loja online herdada e às integrações externas do SharePoint. Para obter mais informações sobre essas opções de metadados de atributo, consulte [Visão geral do esquema de pesquisa no SharePoint Server 2013](/SharePoint/search/search-schema-overview).

As seguintes opções de metadados de atributos adicionais também estão disponíveis na página **Atributos**:

- Pesquisável
- Recuperável
- Pode ser consultado
- Classificável
- Ignorar maiúsculas/minúsculas e formato
- Correspondência concluída

Essas opções foram originalmente destinadas a melhorar a funcionalidade de pesquisa das lojas online herdadas do SharePoint. Elas não se aplicam necessariamente a sites de comércio eletrônico do Commerce ou terminais de PDV. Como a integração sem periféricos continua sendo suportada, essas opções estão disponíveis para exportar metadados de atributo usando o Kit de desenvolvimento de software (SDK) do Commerce. Você pode usar o SDK do Commerce para colocar produtos em um índice de pesquisa externo personalizado e otimizado. Dessa forma, você pode garantir que apenas os atributos que devem ser indexados sejam indexados.

## <a name="attribute-groups"></a>Grupos de atributos

Um *grupo de atributos* é usado para agrupar os atributos individuais para um componente ou um subcomponente em um modelo de configuração do produto. Um atributo pode ser incluído em mais de um grupo de atributos. Os grupos de atributos podem ajudar os usuários a configurar produtos porque as várias seleções são organizadas em um contexto específico. Os grupos de atributo podem ser atribuídos a categorias ou canais. Você também pode definir valores padrão para atributos em um grupo de atributos.

![Página Grupos de atributos.](media/AttributeGroup_2022Series.png)

### <a name="create-an-attribute-group"></a>Criar um grupo de atributos

Para criar um grupo de atributos, siga as etapas deste procedimento de exemplo.

1. Entre no Commerce Headquarters como um gerente de mercadorias.
1. Vá para **Gerenciamento de informações do produto \> Configuração \> Categorias e atributos \> Grupos de atributos**.
1. Crie um grupo de atributos chamado **Camisas Sociais**.
1. Adicione os seguintes atributos: **Método de Lavagem**, **Tipo de Colarinho**, **Coleção** e **Design**.

> [!NOTE]
> Os valores da ordem de exibição dos atributos no grupo de atributos não influenciam nem se aplicam à ordem dos refinadores nos resultados da pesquisa de navegação e de categoria. Elas são aplicáveis somente ao cenário "atributos da ordem".

### <a name="assign-attribute-groups-to-categories"></a>Atribuir grupos de atributo a categorias

Um ou mais grupos de atributos podem ser associados a nós de categoria nos seguintes tipos de hierarquias de categoria:

- Hierarquia de produtos de comércio
- Hierarquia da categoria de navegação do canal
- Hierarquia da categoria de produto complementar

Quando os produtos são classificados em categorias associadas a grupos de atributos, eles herdam os atributos incluídos nesses grupos de atributos.

![Guia Rápida de grupos de atributos do produto na página hierarquia de produtos do Commerce.](media/AGRetailProdHierarchy_2022Series.png)

Para atribuir grupos de atributo a categorias na Hierarquia de produtos do Commerce, siga as etapas neste procedimento de exemplo.

1. Entre no Commerce Headquarters como um gerente de mercadorias.
1. Acesse **Varejo e Comércio \> Produtos e categorias \> Hierarquia de produtos de comércio**.
1. Selecione a hierarquia de navegação **Moda**.
1. Em **Roupa Masculina**, selecione a categoria **Calças** e na Guia Rápida **Grupos de atributos do produto**, adicione um grupo de atributo chamado **Cintos masculinos**.
1. Selecione a categoria **Óculos escuros** e verifique os novos atributos no grupo de atributos **Óculos escuros** selecionando **Exibir atributos**. O grupo de atributos deve mostrar os novos atributos **Formato de lente** e **Marca de óculos escuros**.
1. Selecione a categoria **Calças** e verifique os atributos do grupo de atributos **Cintos masculinos** selecionando **Exibir atributos**. O grupo de atributos deve mostrar os atributos **Marca de cintos masculinos**, **Tecido do cinto** e **Tamanho do cinto**.

O mesmo procedimento básico pode ser usado para atribuir grupos de atributos a categorias na hierarquia de categoria de navegação de canal e na hierarquia de categoria de produtos complementares. No entanto, na etapa 2, use um dos seguintes caminhos, dependendo da hierarquia à qual você deseja atribuir grupos de atributos:

- **Hierarquia de categoria de navegação de canal:** Vá para **Varejo e Comércio \> Gerenciamento de categorias e produtos \> Categorias de navegação de canal**.
- **Hierarquia de categoria de produtos complementares:** Vá para **Varejo e Comércio \> Gerenciamento de categorias e produtos \> Categorias de produtos complementares**.

> [!NOTE]
> Certifique-se de associar somente os grupos de atributos em uma hierarquia de categoria na Guia Rápida **Grupos de atributo de produto**, não na Guia Rápida **Valores de atributos da categoria**. Se os atributos aparecerem na Guia Rápida **Valores de atributos da categoria**, selecione **Editar hierarquia de categoria** no Painel de Ações. Em seguida, na Guia Rápida **Grupos de atributos da categoria**, selecione os nós de categoria e depois **Remover**. Não há suporte para a busca de atributos por categoria por meio do Commerce Scale Unit.

## <a name="identify-viewable-and-refinable-attributes-for-commerce-channels-for-the-default-product-collection"></a>Identificar atributos visíveis e refináveis para canais do Commerce para a coleção de produtos padrão

Depois de associar vários grupos de atributos a categorias em várias hierarquias (hierarquia de produtos do Commerce ou categorias de navegação de canais) e valores de atributo definidos para cada produto, com base na associação de categoria, você deve habilitar o sinalizador **Mostrar atributo no Canal** para tornar esses atributos visíveis em um canal específico.

1. Acesse **Varejo e Comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. Selecione **Definir metadados de atributo** e selecione um atributo no painel de navegação esquerdo.
1. Na Guia Rápida **Atributos de produto do canal** (não na Guia Rápida **Atributos da Categoria**), defina a opção **Mostrar atributo no canal** como **Sim** para tornar o atributo visível.
1. Se você deseja que o atributo seja refinável também, defina a opção **Pode ser refinado** como **Sim**.

### <a name="control-visibility-of-dimension-based-refiners-such-as-size-style-and-color"></a>Controlar a visibilidade de refinadores baseados em dimensão, como tamanho, estilo e cor

As dimensões do produto, como tamanho, estilo e cor, são os refinadores mais usados. Para disponibilizar essas dimensões de produto como refinadores, você deve associar um grupo de atributos ao nível do canal que contém uma referência a um tipo de atributo que herda automaticamente valores dos valores de dimensão do produto.

Você pode especificar que as dimensões do produto são visíveis e refináveis atualizando os sinalizadores na página **Categorias do canal e atributos de produto**. Selecione o nó raiz no painel de navegação e, em seguida, na Guia Rápida **Atributos de produto do canal**, defina a opção **Mostrar atributo no canal** como **Sim** para os atributos **Tamanho**, **Estilo** e **Cor**. Se quiser que esses atributos sejam refináveis também, defina a opção **Pode ser refinado** como **Sim** para cada um.

![Configurando metadados de atributo para refinadores de dimensão.](./media/ProductDimensionRefinersMetadataSetup_2022Series.png)

Para habilitar os atributos de forma que estejam disponíveis no canal Houston baseado em dados de demonstração, siga as etapas neste procedimento de exemplo.

1. Acesse **Varejo e Comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. Selecione o canal **Houston**.
1. No Painel de Ação, selecione **Definir metadados de atributo**.
1. Selecione o nó de categoria **Moda** e, em seguida, na Guia Rápida **Atributos de produto do canal**, selecione **Incluir atributo** para cada atributo.
1. Selecione o nó de categoria **Acessórios de moda**, a categoria **Óculos escuros** e, em seguida, na Guia Rápida **Atributos de produto do canal**, selecione **Incluir atributo** para cada atributo.
1. Selecione o nó de categoria **Menswear**, a categoria **Calças** e, em seguida, na Guia Rápida **Atributos de produto do canal**, selecione **Incluir atributo** para cada atributo.
1. Depois de atualizar os metadados de atributo para os atributos e refinadores pretendidos, certifique-se de salvar as alterações e executar o trabalho **Publicar atualizações de canal**. Em seguida, depois que as atualizações forem publicadas, você deverá executar os seguintes trabalhos: **1070** (**Configuração do canal**), **1040** (**Produtos**) e **1150** (**Catálogo**).

> [!NOTE]
> - Se a sua empresa exigir que você adicione ou remova os produtos com frequência na hierarquia de navegação, ou que você faça alterações, como atualizar valores de ordem de exibição, adicionar novas categorias e adicionar novos grupos de atributos a categorias, recomendamos que você configure o trabalho **Publicar atualizações de canal** para ser executado como um trabalho em lotes frequente. Como alternativa, acione manualmente o trabalho **Publicar atualizações de canal** e, em seguida, os seguintes trabalhos do Commerce Data Exchange (CDX): **1070** (**Configuração do canal**), **1040** (**Produtos**) e **1150** (**Catálogo**).
> - Uma opção **Herdar** permite especificar que esse canal deve herdar os grupos de atributos de seu canal principal na hierarquia. Se você definir a opção **Herdar** como **Sim**, o nó do canal secundário herdará todos os grupos de atributos e todos os atributos nesses grupos.
> - Se o botão **Definir metadados do atributo** no Painel de Ações não estiver disponível, certifique-se de que a **Hierarquia de navegação** está associada ao canal na Guia Rápida **Geral**.
> - Você não deve associar nenhum grupo de atributos, exceto grupos de atributos baseados em dimensão em um nível de canal (por exemplo, em **Grupos de atributos** na página **Categorias do canal e atributos de produto**).
> - Depois da introdução do suporte a catálogos B2B (business-to-business) específicos do cliente na versão 10.0.27 do Commerce, você deve identificar as configurações do refinador e atributo para cada catálogo B2B da mesma maneira descrita neste artigo.

## <a name="override-attribute-values"></a>Substituir de valores de atributo

Os valores padrão de atributos podem ser substituídos para produtos individuais no nível do produto. Eles também podem ser substituídos para produtos individuais em catálogos específicos destinados a canais específicos.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Substituir os valores de atributo de um produto individual

Para substituir os valores de atributo de um produto individual, siga as etapas deste procedimento de exemplo.

1. Entre no Commerce Headquarters como um gerente de mercadorias.
1. Vá para **Varejo e Comércio \> Gerenciamento de categorias e produtos \> Produtos lançados por categoria**.
1. Selecione **Moda \> Acessórios de Moda \> Óculos Escuros**.
1. Selecione o produto obrigatório na grade. Em seguida, no Painel de Ação, na guia **Produto**, no grupo **Configurar**, selecione **Atributos de produto**.
1. Selecione um atributo no painel esquerdo e atualize seu valor no painel direito.

![Página valores de atributos de produto.](media/ProdDetailsProdAttrValues_2022Series.png)

### <a name="override-the-attribute-values-of-all-products-in-a-catalog"></a>Substituir os valores de atributo de todos os produtos em um catálogo

Para substituir os valores de atributo de todos os produtos em um catálogo, siga as etapas deste procedimento de exemplo.

1. Entre no Commerce Headquarters como um gerente de mercadorias.
1. Vá para **Varejo e Comércio \> Gerenciamento de catálogo \> Todos os catálogos**.
1. Selecione o catálogo **Fabrikam Base Catalog**.
1. Selecione **Moda \> Acessórios de Moda \> Óculos Escuros**.
1. Na Guia Rápida **Produtos**, selecione o produto obrigatório e, em seguida, selecione **Atributos** acima da grade do produto.
1. Nas seguintes Guias Rápidas, atualize os valores dos atributos obrigatórios:

    - Mídia do produto compartilhado
    - Atributos do produto compartilhado
    - Mídia do canal
    - Atributos de produto do canal

### <a name="override-the-attribute-values-of-all-products-in-a-channel"></a>Substituir os valores de atributo de todos os produtos de um canal

Para substituir os valores de atributo de todos os produtos em um canal, siga as etapas deste procedimento de exemplo.

1. Entre no Commerce Headquarters como um gerente de mercadorias.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. Selecione o canal **Houston**.
1. Na Guia Rápida **Produtos**, selecione o produto obrigatório e, em seguida, selecione **Atributos** acima da grade do produto.
1. Se nenhum produto estiver disponível, selecione **Adicionar** na Guia Rápida **Produtos** e, em seguida, selecione os produtos obrigatórios na caixa de diálogo **Adicionar produtos**.
1. Nas seguintes Guias Rápidas, atualize os valores dos atributos obrigatórios:

    - Mídia do produto compartilhado
    - Atributos do produto compartilhado
    - Mídia do canal
    - Atributos de produto do canal

### <a name="define-variant-specific-attribute-values-and-define-multiple-values-for-product-attributes"></a>Definir valores de atributos específicos da variante e definir vários valores para atributos de produto

Para definir valores de atributos específicos da variante e definir vários valores para atributos de produto, siga as etapas neste procedimento de exemplo.

1. Entre no Commerce Headquarters como um gerente de mercadorias.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. Selecione o canal **Houston**.
1. Na Guia Rápida **Produtos**, selecione a variante do produto obrigatória e, em seguida, selecione **Atributos** acima da grade do produto.
1. Se nenhum produto estiver disponível, selecione **Adicionar** na Guia Rápida **Produtos** e, em seguida, selecione as variantes do produtos obrigatórias na caixa de diálogo **Adicionar produtos**.
1. Nas seguintes Guias Rápidas, atualize os valores dos atributos obrigatórios:

    - Mídia do produto compartilhado
    - Atributos do produto compartilhado
    - Mídia do canal
    - Atributos de produto do canal

#### <a name="example-of-variant-specific-attribute-configuration"></a>Exemplo de configuração de atributo específica da variante
        
Neste exemplo, o produto **P001-Mestre** é um sapato para várias atividades que tem três variantes: **Corrida**, **Caminhada** e **Trilha**. Para cada variante, você deseja definir de forma exclusiva o valor do atributo da **Atividade**. Na Guia Rápida **Produtos** da página **Categorias do canal e atributos de produto** de seu canal, você define o valor do atributo **Atividade** para as variantes, como mostrado na seguinte tabela.

| Grade     | Valor do atributo da atividade |
|-------------|--------------------------|
| P001-Mestre | Esportes                   |
| P001-1      | Em Execução                  |
| P001-2      | Caminhar                  |
| P001-3      | Trilha                 |

Se um usuário procurar "sapato" o produto **P001-Mestre** será exibido nos resultados da pesquisa. Se você configurou o atributo **Atividade** como refinável, o refinador **Atividade** listará somente **Esportes** como valor refinável porque esse valor foi definido para o atributo **Atividade** em nível de produto **P001-Mestre**.

Por padrão, os atributos de nível de grade devem ser usados somente em páginas de detalhes do produto (PDPs). Quando você seleciona uma variante de produto específica em um PDP, as especificações do produto no PDP são atualizadas para essa variante específica.

Para que os refinadores selecionem valores de atributos definidos no nível de variante do produto, você deve definir um atributo no nível do produto mestre, marcar a caixa de seleção **Permitir vários valores** e definir o tipo de atributo como **Texto**.

Em seguida, você deve determinar todos os valores possíveis para as variantes do produto. Para o atributo **Atividade** usado neste exemplo, os valores possíveis podem incluir **Corrida**, **Caminhada**, **Montanhismo**, **Trilha**, **Acampamento**, **Esportes Aquáticos** e **Esportes de Neve**.

Depois de determinar quais devem ser os valores do atributo da variante, você pode defini-los no nível do produto mestre usando os valores separados por barra. Para o atributo **Atividade** você pode definir o valor do atributo no produto mestre como **Corrida|Caminhada|Montanhismo|Trilha|Acampamento|Esportes Aquáticos|Esportes de Neve**.

Em seguida, para cada variante, você pode definir valores de atributos inserindo valores separados por barra ou valores únicos. Para o atributo **Atividade**, você pode configurar uma variante de produto individual como **Corrida|Caminhada|Montanhismo**, **Corrida**, **Corrida|Montanhismo|Esportes Aquáticos** e assim por diante.

Depois de definir os valores do atributo da variante, na página **Categorias do canal e atributos de produto**, no Painel de Ação, selecione **Publicar atualizações de canal** e execute os trabalhos **1150**, **1040** e **1070**.

Depois que os trabalhos são concluídos e o índice de pesquisa é atualizado, todos os valores esperados devem aparecer nos resultados de pesquisa e na pesquisa de categorias.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
