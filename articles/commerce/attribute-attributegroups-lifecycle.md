---
title: Gerenciar atributos e grupos de atributos
description: Este tópico descreve como usar atributos para fornecer uma forma de descrever um produto e suas características por meio de campos definidos pelo usuário.
author: ashishmsft
manager: AnnBe
ms.date: 04/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: EcoResCategoryAttribute, EcoResProductEntityAttributeTableFieldAssociation, EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResAttributeType, EcoResAttributeValue, EcoResCategoryAttributeGroup, EcoResCategoryFriendlyName
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application pdate 5, AX 8.0
ms.openlocfilehash: b5d0e92196f98fb707b1c424a6ae237f4dc9545c
ms.sourcegitcommit: 97d4a9bd442fe20f90605d8154c3a947c7645b37
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "3895344"
---
# <a name="manage-attributes-and-attribute-groups"></a>Gerenciar atributos e grupos de atributos

[!include [banner](includes/banner.md)]

Os *Atributos* fornecem uma maneira de descrever melhor um produto e suas características por meio de campos definidos pelo usuário (como **Tamanho da memória**, **Capacidade do disco rígido**, **Compatível com Energy Star** etc). Os atributos podem ser associados a várias entidades do Commerce, como categorias de produto e canais, e valores padrão podem ser definidos para eles. Os produtos então herdam os atributos e os valores padrão quando são associados às categorias de produto ou aos canais. Os valores padrão podem ser substituídos no nível de produto individual, de canal de varejo ou em um catálogo.


Por exemplo, uma televisão típica pode ter os seguintes atributos.

| Categoria   | Atributo                | Valores permitidos          | Valor padrão |
|------------|--------------------------|-----------------------------|---------------|
| TV e vídeo | Marca                    | Qualquer valor de marca válido       | Nenhum(a)          |
| TV         | Tamanho de Tela              | 20–80 polegadas                | Nenhum(a)          |
|            | Resolução Vertical      | 480i, 720p, 1080i ou 1080p | 1080p         |
|            | Taxa de Atualização da Tela      | 60hz, 120hz ou 240hz       | 60hz          |
|            | Entradas HDMI              | 0–10                        | 3             |
|            | Entradas DVI               | 0–10                        | 1             |
|            | Entradas Compostas         | 0–10                        | 2             |
|            | Entradas de Componentes         | 0–10                        | 1             |
| LCD        | Pronto para 3D                 | Sim ou Não                   | Sim           |
|            | Habilitado para 3D               | Sim ou Não                   | Não            |
| Plasma     | Operação Temporária de      | 32–110 graus              | 32            |
|            | Operação Temporária até        | 32–110 graus              | 100           |
| Projeção | Garantia de Tubo de Projeção | 6, 12 ou 18 meses         | 12            |
|            | \# de Tubos de Projeção   | 1–5                         | 3             |

## <a name="attributes-and-attribute-types"></a>Atributos e tipos de atributos

Os atributos são baseados nos *tipos de atributos*. O tipo de atributo identifica o tipo de dados que podem ser inseridos para um atributo específico. Os seguintes tipos de atributo têm suporte:

- **Moeda** – Este tipo dá suporte a um valor de moeda. Ele pode ser limitado (isto é, pode dar suporte a um intervalo de valores), ou pode ser deixado aberto.
- **Data/Hora** – Este tipo dá suporte a valores de data e hora. Pode ser limitado ou deixado aberto.
- **Decimal** – Este tipo dá suporte a um valor numérico que inclui casas decimais. Ele também dá suporte a uma unidade de medida. Pode ser limitado ou deixado aberto.
- **Inteiro** – Este tipo dá suporte a um valor numérico. Ele também dá suporte a uma unidade de medida. Pode ser limitado ou deixado aberto.
- **Texto** – Este tipo dá suporte a um valor de texto. Ele também dá suporte a um conjunto predefinido de valores possíveis (isto é, uma *enumeração*).
- **Booliano** – Este tipo dá suporte a um valor binário (**true** ou **false**).
- **Referência** – Este tipo faz referência a outros atributos.

### <a name="set-up-attribute-types"></a>Configurar tipos de atributos

1. Entre no cliente de back office como gerente de mercadorias.
2. Vá para **Gerenciamento de informações do produto** &gt; **Configuração** &gt; **Categorias e atributos** &gt; **Tipos de atributos**.
3. Crie dois tipos de atributos do tipo **Texto**, defina a opção **Lista fixa** como **Sim** e adicione uma lista de valores:

    - Nomeie um tipo de atributo **Formato de lente** e adicione os seguintes valores: **Oval**, **Quadrado** e **Retangular**.
    - Nomeie o outro tipo de atributo **Marca de óculos escuros** e adicione os seguintes valores: **Ray-Ban**, **Aviador** e **Oakley**.

![Tipos de atributos](media/AttributeType.png)

### <a name="set-up-an-attribute"></a>Configurar um atributo

1. Entre no cliente de back office como gerente de mercadorias.
2. Vá para **Gerenciamento de informações do produto** &gt; **Configuração** &gt; **Categorias e atributos** &gt; **Atributos**.
3. Crie um atributo chamado **Lente**.
4. Defina o campo **Tipo de atributo** como **Formato de lente**.

![Atributos](media/Attribute.png)

## <a name="attribute-metadata"></a>Metadados de atributo

Os *Metadados de atributo* permitem selecionar opções para especificar como os atributos de cada produto devem se comportar. Por exemplo, você pode especificar se os atributos são obrigatórios, se podem ser usados para pesquisas e como filtro.

Para produtos, as configurações de metadados de atributo podem ser substituídas no nível do canal. Esse recurso será discutido posteriormente neste tópico.

Como você pode observar, a página **Atributos** inclui as opções relacionadas a metadados de atributo. Em **Atribuir metadados para PDV**, uma opção chamada **Pode ser refinado** afeta o comportamento dos valores de atributo no ponto de venda (PDV) ou a forma como o sistema trata esses valores de atributo. Somente atributos para os quais você define a opção **Pode ser refinado** como **Sim** aparecerão para refinamento ou filtragem de produtos no PDV.

Estas são as outras opções de metadados de atributo na página **Atributos**:

- Pesquisável
- Recuperável
- Pode ser consultado
- Classificável
- Permitir valores múltiplos
- Ignorar maiúsculas/minúsculas e formato
- Correspondência concluída

Essas opções foram originalmente destinadas a melhorar a funcionalidade de pesquisa da vitrine online. Embora o Commerce não inclua a vitrine online pronta para uso, ele vem com o Software Development Kit (SDK) para publicação de comércio eletrônico. Os clientes podem usar esse SDK para colocar produtos em um índice de pesquisa de sua escolha. Embora os dados do produto sejam importados, os clientes ainda poderão distinguir dados pesquisáveis, dados que podem ser consultados e assim por diante. Dessa forma, eles podem construir um índice ideal para garantir que indexem somente os atributos que, *em sua opinião*, devem ser indexados.

Para obter informações sobre a finalidade dessas outras opções, consulte [Visão geral do esquema de pesquisa no SharePoint Server 2013](https://technet.microsoft.com/library/jj219669.aspx).

## <a name="filter-settings-for-attributes"></a>Configurações de filtro para atributos

As configurações de filtro para atributos permitem definir como esses filtros são mostrados no PDV. Para acessar as configurações de filtro de um atributo, na página **Atributos**, selecione o atributo e, no Painel de Ação, selecione **Configurações do filtro**.

A página **Preferências de exibição do filtro** inclui os seguintes campos:

- **Nome** – Por padrão, este campo é definido como o nome do atributo. No entanto, você pode alterar o valor.
- **Opção de exibição** – As seguintes opções estão disponíveis:

    - **Valor único** – Esta opção está disponível para os seguintes tipos de atributos: **Booliano**, **Moeda**, **Decimal**, **Inteiro** e **Texto**. Essa opção permite a seleção de um valor único para esses atributos no cliente para refinamento.
    - **Diversos valores** – Esta opção está disponível para os seguintes tipos de atributos: **Moeda**, **Decimal**, **Inteiro** e **Texto**. Essa opção permite a seleção de diversos valores para esse atributo no cliente para refinamento.

- **Controle de exibição** – As seguintes opções estão disponíveis:

    - **Lista** – Esta opção está disponível para todos os tipos de atributos.
    - **Intervalo** – Esta opção está disponível para os seguintes tipos de atributos: **Moeda**, **Decimal** e **Inteiro**.
    - **Controle deslizante** – Esta opção está disponível para os seguintes tipos de atributos: **Moeda**, **Decimal** e **Inteiro**.
    - **Controle deslizante com barras** – Esta opção está disponível para os seguintes tipos de atributos: **Moeda**, **Decimal** e **Inteiro**.

- **Valor de limite** – Esta configuração será necessária se você tiver selecionado **Intervalo** como tipo de controle de exibição. Você pode definir valores usando um ponto-e-vírgula (;) como delimitador.

    Por exemplo, para um filtro como **Volume do malote**, um valor de limite pode ser **10; 20; 50; 100; 200; 500; 1000; 5000**. Nesse caso, o PDV mostrará os intervalos a seguir. Os intervalos que não tiverem nenhum produto no conjunto de resultados aparecerão esmaecidos.

    - Menos de 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - 500 ou mais

![Configurações de filtro do atributo](media/AttributeFilterSettings.PNG)

## <a name="attribute-groups"></a>Grupos de atributos

Depois que os atributos forem definidos, poderão ser atribuídos a grupos de atributos. Um *grupo de atributos* é usado para agrupar os atributos individuais para um componente ou um subcomponente em um modelo de configuração do produto. Um atributo pode ser incluído em mais de um grupo de atributos. Os grupos de atributos podem ajudar os usuários a configurar produtos porque as várias seleções são organizadas em um contexto específico. Os grupos de atributo podem ser atribuídos a categorias ou canais.

Você também pode definir valores padrão para atributos que estejam incluídos em um grupo de atributos. Por exemplo, você adiciona um atributo para cor a um grupo de atributos e seleciona **Azul** como o valor do atributo padrão. Nesse caso, quando o grupo de atributos for adicionado a um produto que inclua cor como um de seus atributos, **Azul** aparecerá como a cor padrão desse produto.

![Grupos de atributos](media/AttributeGroup.png)

### <a name="create-an-attribute-group"></a>Criar um grupo de atributos

1. Entre no cliente de back office como gerente de mercadorias.
2. Vá para **Gerenciamento de informações do produto** &gt; **Configuração** &gt; **Categorias e atributos** &gt; **Grupos de atributos**.
3. Crie um grupo de atributos chamado **Óculos escuros**.
4. Adicione os seguintes atributos: **Formato de lente** e **Marca de óculos escuros**.

### <a name="assign-attribute-groups-to-categories"></a>Atribuir grupos de atributo a categorias

Um ou mais grupos de atributo podem ser associados a nós de categoria nos seguintes tipos de hierarquias de categorias: Hierarquia de produtos de comércio, Hierarquia de categoria de navegação de canal e Hierarquia de categoria de produtos complementares. Então, quando os produtos são categorizados, eles herdam os atributos incluídos nos grupos de atributos.

![Hierarquia de produtos – Grupos de atributo de produto](media/AGRetailProdHierarchy.PNG)

Siga estas etapas para atribuir grupos de atributo a categorias na Hierarquia de produtos de comércio.

1. Entre no cliente de back office como gerente de mercadorias.
2. Vá para **Varejo e Comércio** &gt; **Gerenciamento de categorias e produtos** &gt; **Hierarquia de produtos de comércio**.
3. Selecione **Hierarquia de navegação de moda**.
4. Em **Menswear**, selecione a categoria **Calças** e, em seguida, na Guia Rápida **Grupos de atributo de produto**, adicione um grupo de atributos chamado **Cintos masculinos**.
5. Selecione a categoria **Óculos escuros** e verifique os novos atributos no grupo de atributos **Óculos escuros** selecionando **Exibir atributos**.

    O grupo de atributos deve mostrar os novos atributos **Formato de lente** e **Marca de óculos escuros**.

6. Em **Menswear**, selecione a categoria **Calças** e verifique os atributos do grupo de atributos **Cintos masculinos** selecionando **Exibir atributos**.

    O grupo de atributos deve mostrar os atributos **Marca de cintos masculinos**, **Tecido do cinto** e **Tamanho do cinto**.

> [!NOTE]
> Esse procedimento também pode ser usado para atribuir grupos de atributos a categorias na Hierarquia de categoria de navegação de canal e na Hierarquia de categoria de produtos complementares. Na etapa 2, use os seguintes caminhos de navegação:
>
> - Varejo e Comércio &gt; Gerenciamento de categorias e produtos &gt; Categorias de navegação de canal
> - Varejo e Comércio &gt; Gerenciamento de categorias e produtos &gt; Categorias de produtos complementares

### <a name="assign-attribute-groups-to-stores"></a>Atribuir grupos de atributo a lojas

Um ou mais grupos de atributo podem ser associados a uma ou mais lojas na hierarquia de lojas. Assim, quando os produtos são enriquecidos para lojas específicas, eles herdam os atributos incluídos nos grupos de atributo.

1. Entre no cliente de back office como gerente de mercadorias.
2. Vá para **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Categorias do canal e atributos de produto**.
3. Atribuir grupos de atributos ao canal Houston:

    1. Selecione o canal **Houston**.
    2. Na Guia Rápida **Grupo de atributos**, selecione **Adicionar** e, em seguida, no campo **Nome**, selecione **SharePointProvisionedProductAttributeGroup**.
    3. Selecione **Adicionar** novamente e, em seguida, no campo **Nome**, selecione **Cintos masculinos**.
    4. Selecione **Adicionar** novamente e, em seguida, no campo **Nome**, selecione **Óculos escuros**.

        > [!NOTE]
        > Uma opção permite especificar que esse canal deve herdar os grupos de atributos de seu canal principal na hierarquia. Se você definir a opção **Herdar** como **Sim**, o nó do canal secundário herdará todos os grupos de atributos e todos os atributos nesses grupos.

4. Habilitar os atributos para que fiquem disponíveis no canal Houston:

    1. No Painel de Ação, selecione **Definir metadados de atributo**.
    2. Selecione o nó de categoria **Moda** e, em seguida, na Guia Rápida **Atributos de produto do canal**, selecione **Incluir atributo** para cada atributo.
    3. Selecione o nó de categoria **Acessórios de moda**, a categoria **Óculos escuros** e, em seguida, na Guia Rápida **Atributos de produto do canal**, selecione **Incluir atributo** para cada atributo.
    4. Selecione o nó de categoria **Menswear**, a categoria **Calças** e, em seguida, na Guia Rápida **Atributos de produto do canal**, selecione **Incluir atributo** para cada atributo.

![Categorias do canal e atributos de produto – Grupos de atributos](media/CCPAttrGrp.png)

## <a name="overriding-attribute-values"></a>Substituição de valores de atributo

Os valores padrão de atributos podem ser substituídos para produtos individuais no nível do produto. Os valores padrão também podem ser substituídos para produtos individuais em catálogos específicos destinados a canais específicos.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Substituir os valores de atributo de um produto individual

1. Entre no cliente de back office como gerente de mercadorias.
2. Vá para **Varejo e Comércio** &gt; **Gerenciamento de categorias e produtos** &gt; **Produtos liberados por categoria**.
3. Selecione o nó de categoria **Moda** &gt; **Acessórios de moda** &gt; **Óculos escuros**.
4. Selecione o produto obrigatório na grade. Em seguida, no Painel de Ação, na guia **Produto**, no grupo **Configurar**, selecione **Atributos de produto**.
5. Selecione um atributo no painel esquerdo e atualize seu valor no painel direito.

![Página de detalhes do produto – Grupos de atributos do produto](media/ProdDetailsProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-catalog"></a>Substituir os valores de atributo de produtos em um catálogo

1. Entre no cliente de back office como gerente de mercadorias.
2. Vá para **Varejo e Comércio** &gt; **Gerenciamento de catálogo** &gt; **Todos os catálogos**.
3. Selecione o catálogo **Fabrikam Base Catalog**.
4. Selecione o nó de categoria **Moda** &gt; **Acessórios de moda** &gt; **Óculos escuros**.
5. Na Guia Rápida **Produtos**, selecione o produto obrigatório e, em seguida, selecione **Atributos** acima da grade do produto.
6. Nas seguintes Guias Rápidas, atualize os valores dos atributos obrigatórios:

    - Mídia do produto compartilhado
    - Atributos do produto compartilhado
    - Mídia do canal
    - Atributos de produto do canal

    > [!NOTE]
    > Se mídia de produto e atributos de produto compartilhados forem criados, eles se aplicarão a todos os produtos.

![Grupos de atributos de produto do catálogo](media/CatalogProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-channel"></a>Substituir os valores de atributo de produtos em um canal

1. Entre no cliente de back office como gerente de mercadorias.
2. Vá para **Varejo e Comércio** &gt; **Configuração de canal** &gt; **Categorias do canal e atributos de produto**.
3. Selecione o canal **Houston**.
4. Na Guia Rápida **Produtos**, selecione o produto obrigatório e, em seguida, selecione **Atributos** acima da grade do produto.

    > [!NOTE]
    > Se nenhum produto estiver disponível, adicione produtos selecionando **Adicionar** na Guia Rápida **Produtos** e, em seguida, selecionando os produtos obrigatórios na caixa de diálogo **Adicionar produtos**.

5. Nas seguintes Guias Rápidas, atualize os valores dos atributos obrigatórios:

    - Mídia do produto compartilhado
    - Atributos do produto compartilhado
    - Mídia do canal
    - Atributos de produto do canal

    > [!NOTE]
    > Se mídia de produto e atributos de produto compartilhados forem criados, eles se aplicarão a todos os produtos.
