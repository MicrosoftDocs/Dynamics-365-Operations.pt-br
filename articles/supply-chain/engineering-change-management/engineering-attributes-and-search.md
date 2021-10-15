---
title: Atributos de engenharia e pesquisa de atributos de engenharia
description: Este tópico explica como você pode usar atributos de engenharia para especificar todas as características não padronizadas, a fim de garantir que todos os dados mestre do produto possam ser registrados no sistema. Ele também explica como você pode usar a pesquisa de atributos de engenharia para encontrar produtos com facilidade, com base nessas características registradas.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductAttributeSearch, EngChgMaintainAttributeInheritance, EngChgAttribute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2f8803e46ce6f104a5afee64faaf393a2df47a61
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568102"
---
# <a name="engineering-attributes-and-engineering-attribute-search"></a>Atributos de engenharia e pesquisa de atributos de engenharia

[!include [banner](../includes/banner.md)]

Para garantir que todos os dados mestre do produto possam ser registrados no sistema, você deve usar atributos de engenharia para especificar todas as características não padronizadas. Você pode usar a pesquisa de atributos de engenharia para encontrar produtos com facilidade, com base nessas características registradas.

## <a name="create-engineering-attributes-and-attribute-types"></a>Criar atributos de engenharia e tipos de atributo

Normalmente, os produtos de engenharia têm muitas características e propriedades que você deve capturar. Embora seja possível registrar algumas das propriedades usando os campos de produto padrão, você também pode criar novas propriedades de engenharia, conforme a necessidade. Você pode definir seus próprios *atributos de engenharia* e torná-los parte da definição do produto.

Cada atributo de engenharia deve pertencer a um *tipo de atributo*. Esse requisito existe porque cada atributo de engenharia deve ter um *tipo de dados* que defina os tipos de valores que ele pode manter. Um tipo de atributo de engenharia pode ser um tipo padrão (como texto livre, inteiro ou decimal) ou um tipo personalizado (como texto com um conjunto específico de valores para seleção). Você pode reutilizar cada tipo de atributo com qualquer quantidade de atributos de engenharia.

### <a name="set-up-engineering-attribute-types"></a>Configurar tipos de atributos de engenharia

Para exibir, criar ou editar um tipo de atributo de engenharia, siga estas etapas.

1. Acesse **Gerenciamento de alterações de engenharia \> Configuração \> Atributos \> Tipos de atributos**.
1. Selecione um tipo de atributo existente no painel de lista ou selecione **Novo** no Painel de Ações para criar um novo tipo de atributo.
1. Defina os seguintes campos:

    - **Nome do tipo de atributo** – insira um nome para o tipo de atributo.
    - **Tipo** – selecione um tipo de dados padrão (*Moeda*, *DateTime*, *Decimal*, *Inteiro*, *Texto*, *Booliano* ou *Referência*).
    - **Lista fixa** – esta opção só estará disponível se você definir o campo **Tipo** como *Texto*. Defina-o como *Sim* para definir valores específicos para atributos desse tipo. Nesse caso, uma lista suspensa será criada. Use a FastTab **Valor** para estabelecer os valores disponíveis para esse tipo de atributo. Defina esta opção como *Não* para permitir que usuários insiram qualquer valor. Nesse caso, um campo de entrada será criado.
    - **Intervalo de valores** – esta opção só estará disponível se você definir o campo **Tipo** como *Inteiro*, *Decimal* ou *Moeda*. Defina-o como *Sim* para estabelecer os valores mínimo e máximo que serão aceitos para atributos desse tipo. Use a FastTab **Intervalo** para estabelecer os valores mínimo e máximo e (para moeda) a moeda que se aplica aos limites inseridos. Defina esta opção como *Não* para aceitar qualquer valor. 
    - **Unidade de medida** – este campo só estará disponível se você definir o campo **Tipo** como *Inteiro* ou *Decimal*. Selecione a unidade de medida que se aplica a esse tipo de atributo. Se nenhuma unidade for necessária, deixe esse campo em branco.

### <a name="set-up-engineering-attributes"></a>Configurar atributos de engenharia

Para exibir, criar ou editar um atributo de engenharia, siga estas etapas.

1. Acesse **Gerenciamento de alterações de engenharia \> Configuração \> Atributos \> Atributos de engenharia**.
1. Selecione um atributo existente no painel de lista ou selecione **Novo** no Painel de Ações para criar um novo atributo.
1. Defina os seguintes campos:

    - **Nome** – insira um nome do atributo. Esse nome aparece somente na página **Atributos de engenharia**. Em qualquer outra parte do sistema, o valor do campo **Nome amigável** em geral é mostrado para identificar o atributo.
    - **Tipo de atributo** – selecione um tipo de atributo definido na seção anterior.
    - **Nome amigável** – insira um nome que identifique o atributo no sistema (exceto na página **Atributos de engenharia**). 
    - **Descrição** — insira uma descrição do atributo.
    - **Texto de ajuda** – insira texto de ajuda que informe a outros usuários a função do atributo.
    - **Valor padrão** – Insira um valor padrão para o atributo. As opções apresentadas dependem do tipo de atributo selecionado.
    - **Moeda** – se o tipo de atributo selecionado for uma moeda, selecione a moeda que o atributo aceitará e mostre os valores.

1. Se o tipo de atributo selecionado for um inteiro ou decimal, a FastTab **Intervalo** será mostrada. Nessa FastTab, defina os seguintes campos, conforme necessário:

    - **Ação de tolerância** – selecione como o sistema deverá responder se um usuário inserir um valor fora do intervalo especificado. Se você selecionar *Aviso*, um aviso será exibido, mas o usuário poderá salvar o valor. Se você selecionar *Não permitido*, um aviso será exibido e o valor não poderá ser salvo até que o usuário o corrija.
    - **Mínimo** – insira o valor mínimo recomendado ou aceito.
    - **Máximo** – insira o valor máximo recomendado ou aceito.

### <a name="engineering-attribute-inheritance"></a>Herança de atributo de engenharia

Para estruturas de produtos, como listas de materiais (BOMs) ou fórmulas, os atributos selecionados podem ser passados dos itens filhos até os itens pai. Você pode pensar nesse processo como "herança reversa".

#### <a name="turn-on-this-feature-for-your-system"></a>Ative este recurso para o seu sistema

Se o sistema ainda não incluir os recursos que são descritos nesta seção, acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Herança de atributos aprimorada para Gerenciamento de Modificações de Engenharia*.

#### <a name="attribute-inheritance-example"></a>Exemplo de atribuição de herança

Para um produto alimentar, como um bolo de cenoura, o sistema precisa registrar todos os alergênicos que o produto contém. O bolo de cenoura pode ser modelado no sistema como um produto de engenharia que tem uma fórmula. Essa fórmula contém os ingredientes do bolo de cenoura, como farinha, leite, cenouras e nozes. Neste exemplo, a empresa fornece dois modelos de bolo de cenoura: um que contém lactose e outro que não contém.

O bolo que contém lactose tem os seguintes atributos no nível de ingrediente:

- Ingrediente "farinha": atributo "glúten" = sim
- Ingrediente "leite": atributo "lactose" = sim
- Ingrediente "nozes": atributo "nozes" = sim

O bolo que não contém lactose usa leite sem lactose e tem os seguintes atributos no nível de ingrediente:

- Ingrediente "farinha": atributo "glúten" = sim
- Ingrediente "leite": atributo "lactose" = não
- Ingrediente "nozes": atributo "nozes" = sim

Como esses produtos são muito parecidos, talvez seja conveniente passar esses atributos dos produtos filho (as duas variações) para o pai (o bolo de cenoura básico). Para implementar essa "herança reversa", você pode usar a funcionalidade *Herança de atributo*. Essa funcionalidade é definida para cada [versão de engenharia](engineering-versions-product-category.md).

## <a name="connect-engineering-attributes-to-an-engineering-product-category"></a>Conectar atributos de engenharia a uma categoria de produto de engenharia

Alguns atributos de engenharia se aplicam a todos os produtos, enquanto outros são específicos de produtos individuais ou categorias de produtos. Por exemplo, os atributos elétricos não são necessários para produtos mecânicos. Portanto, você pode configurar *categorias de produtos de engenharia*. Uma categoria de produto de engenharia estabelece a coleção de atributos de engenharia que devem fazer parte da definição dos produtos que pertencem a essa categoria. Você também pode especificar quais atributos de engenharia são obrigatórios e se há um valor padrão.

Para obter mais informações sobre como trabalhar com categorias de produtos de engenharia, incluindo informações sobre como conectar atributos a categorias, consulte [Versões de engenharia e categorias de produtos de engenharia](engineering-versions-product-category.md).

## <a name="set-attribute-values-for-engineering-attributes"></a>Definir valores para atributos de engenharia

Os atributos de engenharia conectados a uma categoria de produto de engenharia são apresentados quando você cria um novo produto de engenharia que é baseado nessa categoria. Nesse momento, você pode definir valores para os atributos. Posteriormente, esses valores podem ser alterados na página **Versão de engenharia** ou como parte do gerenciamento de alterações de engenharia em uma ordem de alteração de engenharia. Para obter mais informações, consulte [Gerenciar alterações de produtos de engenharia](engineering-change-management.md).

## <a name="create-an-engineering-product"></a>Criar um produto de engenharia

Para criar um produto de engenharia, abra a página **Produtos liberados**. Em seguida, no Painel de Ações, na guia **Produto**, no grupo **Novo**, selecione **Produto de engenharia**.

Você deve especificar a categoria de engenharia à qual o produto pertence. A categoria definirá todos os valores e as características padrão do produto. Ela também definirá os atributos aplicáveis ao produto. Depois que a categoria for selecionada, os valores serão definidos para os atributos. Você pode modificar esses valores.

## <a name="search-for-products-by-using-engineering-attribute-values"></a>Procurar produtos usando valores de atributo de engenharia

Você pode usar a pesquisa de atributos de engenharia para encontrar produtos pesquisando valores de atributos de engenharia. Portanto, você pode encontrar facilmente produtos de engenharia com base nas características deles. Você pode pesquisar nos produtos que pertencem a uma categoria de produto de engenharia ou pode pesquisar em todos os produtos de engenharia.

A pesquisa está disponível nas páginas de dados do produto mestre e em itens transacionais no sistema, como ordens de venda. Para um item transacional, você pode usar a página **Pesquisa de atributo de engenharia** para procurar um produto. Em seguida, você poderá usar o botão **Adicionar como nova linha** para adicionar o produto às linhas da ordem de venda. Os produtos nos resultados da pesquisa também podem ser adicionados diretamente à ordem.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
