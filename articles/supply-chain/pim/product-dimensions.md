---
title: Dimensões do produto
description: Existem cinco dimensões do produto - cor, configuração, tamanho, estilo e versão. Você combina dimensões de produto em grupos de dimensões e atribui grupos de dimensões a produtos mestres. As combinações de dimensões de produto determinam como as variantes de produto serão definidas.
author: t-benebo
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle, EcoResVersionNameLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 46079daafc744421abcbdf0a3539428f2a39f13c
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920514"
---
# <a name="product-dimensions"></a>Dimensões do produto

[!include [banner](../includes/banner.md)]

Existem cinco dimensões do produto: cor, configuração, tamanho, estilo e versão. Você combina dimensões de produto em grupos de dimensões e atribui grupos de dimensões a produtos mestres. As combinações de dimensões de produto determinam como as variantes de produto serão definidas.

As dimensões de produto são as características que servem para identificar uma variante do produto. Você pode usar combinações de dimensões do produto para definir variantes de produto. Você deve definir pelo menos uma dimensão de produto para um produto mestre para criar uma variante do produto.

## <a name="product-variants"></a>Grades de produtos

As variantes dos produtos também são chamadas de itens. Um item é um produto tangível, que não é o mesmo que um serviço. Também é possível definir um produto mestre com o tipo de serviço. Usando o tipo de serviço, você poderá especificar as variantes de produtos que incluem serviços. Por exemplo, você pode especificar um produto mestre do trabalho de consultoria e variantes de produtos para trabalhos que são realizados por consultores seniores e por consultores júnior.

## <a name="product-dimensions"></a>Dimensões do produto

Uma grade de produto pode ser gerada com base nos valores de dimensão de produto.

Os valores de dimensão do produto para as dimensões de tamanho, cor e estilo podem ser criados nos seguintes locais:

- Página **Tamanho** (**Gerenciamento de informações do produto \> Configuração \> Dimensão e grupos de grades \> Tamanhos**)
- Página **Cor** (**Gerenciamento de informações do produto \> Configuração \> Dimensão e grupos de grades \> Cores**)
- Página **Estilo** (**Gerenciamento de informações do produto \> Configuração \> Dimensão e grupos de grades \> Estilos**)

Os valores de dimensão do produto para a dimensão de configuração, geralmente, são criados usando o Configurador de produtos ou o Configurador baseado em dimensão. 

Geralmente, as versões do produto são criadas para versões específicas à medida que o produto evolui durante seu ciclo de vida. As versões do produto são abordadas em detalhes mais adiante neste tópico.

As dimensões do produto também podem ser criadas e mantidas na página **Dimensões do produto**, que podem ser acessadas dos seguintes locais:

- Acesse **Gerenciamento de informações sobre produtos \> Produtos \> Produtos mestre**. No Painel de Ações, selecione **Dimensões do produto**.
- Acesse **Gerenciamento de informações do produto \> Produtos \> Todos os produtos e produtos mestres**. Selecione um produto mestre. No Painel de Ações, selecione **Dimensões do produto**.
- Acesse **Gerenciamento de informações do produto \> Produtos liberados**. Selecione um produto mestre. No Painel de Ações, na guia **Produto**, no grupo **Produto mestre**, selecione **Dimensões do produto**.

O número de variantes que você pode criar para um item é limitado pelo número de possíveis combinações de dimensão do produto.

> [!TIP]
> Quando você usa um produto em uma linha de ordem, por exemplo, seleciona as dimensões do produto para identificar a grade de produto com a qual deseja trabalhar.

## <a name="example"></a>Exemplo

Uma empresa vende jeans denim. O item *Jeans* usa as dimensões cor e tamanho do produto. Os jeans são vendidos em três cores diferentes e seis tamanhos diferentes. As cores são azul, preto e marrom. Os tamanhos são XS, S, M, L, XL e XXL. Nem todos os tamanhos estão disponíveis nas três cores. Se todas as combinações estivessem disponíveis, existiriam 18 tipos diferentes de jeans. Mas, neste exemplo, somente as nove combinações de grade de produto a seguir são produzidas.

| Cor | Tamanho |
|-------|------|
| Azul  | PP   |
| Azul  | S    |
| Azul  | S    |
| Preto | S    |
| Preto | L    |
| Preto | GG   |
| Marrom | L    |
| Marrom | GG   |
| Marrom | GGG  |

## <a name="the-version-product-dimension"></a>A dimensão do produto de versão

A versão é uma dimensão de produto pretendida para ajudar a manter e rastrear várias versões de um produto em toda a cadeia de suprimentos. O controle de versão é essencial para o sucesso dos fabricantes que operam em um mundo com ciclos de vida de produtos cada vez menores, requisitos de qualidade e confiabilidade maiores e um foco maior na segurança dos produtos.

Como uma dimensão de produto padrão, a versão terá comportamento semelhante às dimensões do produto existentes (tamanho, estilo, cor e configuração). Portanto, você pode usá-lo para outras finalidades além de rastrear versões de produtos.

### <a name="turn-on-the-version-dimension"></a><a name="enable-version-dim"></a>Ativar a dimensão de versão

#### <a name="before-you-turn-on-the-version-dimension"></a>Antes de ativar a dimensão de versão

Quando você ativa a dimensão de versão, algumas funcionalidades poderão ser interrompidas ou parar de funcionar como esperado se você tiver instalado outras soluções que adicionam personalizações às dimensões de estoque. Para que a dimensão da versão seja totalmente funcional, talvez seja necessário atualizar essas soluções para que incluam a dimensão de versão em referências às dimensões do estoque.

Quando estiver testando soluções para a compatibilidade com a dimensão de versão, procure os seguintes elementos:

1. **Funcionalidade:** mais importante, quaisquer personalização que envolva as dimensões de estoque deve ser avaliada para garantir que funcione em conjunto com a dimensão de versão.
1. **Referências às dimensões de estoque:** verifique se há referências às dimensões de estoque (isto é, locais onde as dimensões são referenciadas explicitamente). As referências a `InventDimId` devem estar prontas para uso, mas procure referências ao estilo ou à cor. Por exemplo, verifique os seguintes elementos:

    - Chamadas de API em classes estendidas
    - Todas as referências a dimensões de estoque específicas no código de extensão (esse código deve flutuar a dimensão de versão junto com as dimensões de estilo, cor e tamanho).

1. **Referências a chamadas de API obsoletas:** na introdução da dimensão da versão, a Microsoft tentou tornar o mínimo de APIs obsoletas. As poucas APIs que se tornaram obsoletas emitirão um aviso quando você ativar a chave de configuração **Dimensão de produto - versão**. As chamadas para essa API devem ser corrigidas em soluções estendidas antes de você ativar a dimensão de versão em um sistema de produção. Estas são as APIs obsoletas específicas da versão:

    - RetailTransactionServiceInventory::getProductRecordId
    - EcoResProductNumberIdentifiedProductVariantEntity::find
    - EGAISAlcoholProduction_RU::findByItemDim
    - PCVariantConfiguration::findByProductMasterAndDimensions

1. **Mapas:** se algum mapa usar as dimensões de estoque, o mapeamento de relações correspondente a esses mapas deverá ser atualizado para incluir a dimensão de versão. No modelo estendido ou nas extensões de tabela, procure nas tabelas nas quais os campos incluam as dimensões de estoque.
1. **Funcionalidade do Microsoft Dynamics 365 Commerce:** depois de ativada, a dimensão de versão aparecerá durante todo o código específico do Commerce no Dynamics 365 Supply Chain Management. No entanto, a dimensão de versão ainda não tem suporte do banco de dados de canal do Commerce ou nos aplicativos de ponto de venda (PDV) e comércio eletrônico. Esses aplicativos específicos do Commerce não oferecem suporte a usuários que vendem/enviam ou devolvem/recebem estoque por dimensão de versão. As funções de pesquisa de disponibilidade de estoque não distinguem estoque por dimensão de versão em aplicativos do Commerce. Esse comportamento é semelhante ao comportamento atual da dimensão de configuração no Commerce.

#### <a name="turn-on-the-version-dimension"></a>Ativar a dimensão de versão

Para que você possa usar a dimensão de versão, ela deve estar ativada no sistema. Esta tarefa requer permissões de administrador.

1. Acesse **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.
1. Ative o recurso que é denominado *Versão da dimensão do produto*. (Para obter mais informações, consulte [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Coloque o sistema em [modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Acesse **Administração de sistema \> Configurar \> Configuração de licença**.
1. Na guia **Chaves de configuração**, expanda **Comércio** e marque a caixa de seleção **Dimensão do produto - versão**.
1. Desative o [Modo de manutenção](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="areas-where-the-version-dimension-isnt-supported"></a>Áreas em que não há suporte para a dimensão da versão

As áreas a seguir não oferecem suporte à dimensão de versão (ainda é possível usar essas áreas, mas você não poderá adicionar produtos com versão (produtos em que a dimensão de versão é usada) a elas). Por exemplo, não é possível adicionar um item com versão a um catálogo de fornecedor. Isso porque a adição de produtos com a dimensão de versão a essas áreas causaria alterações na falha.

- Demonstrativo de objeto de custo mensal
- Cache de demonstrativos de objeto de custo
- Estatísticas de vendas de MCR por item
- Catálogos do fornecedor
- EcoResProductDimensionGroupEntity

Além disso, os recursos de criação de ordens e processamento de ordens no Commerce (por exemplo, para PDV, call center e ordens de comércio eletrônico) não dão suporte à dimensão da versão. Não há uma linha do tempo confirmada quanto ao momento em que as ordens do Commerce serão aprimoradas para suporte.

### <a name="functional-characteristics-of-the-version-dimension"></a>Características funcionais da dimensão de versão

A dimensão da versão funciona como as outras dimensões do produto. No entanto, devido à natureza específica e como ela se destina a manter e rastrear várias versões de um produto, ela se comporta de maneira um pouco diferente. Estas são algumas das diferenças e semelhanças:

- **Não há grupo de versões.**

    Embora o conceito de grupos exista para tamanho, cor e estilo (grupo de cores, grupo de tamanhos e grupo de estilos), não existe conceito de grupo de versões. Os grupos permitem que você predefina valores aplicáveis para que quando, por exemplo, você atribua um grupo de cores a um produto, o produto possa usar todas as cores desse grupo de cores. Esse conceito não se aplica à dimensão de versão porque as versões de um produto não são predefinidas quando o produto é criado. Em vez disso, as versões são criadas durante o ciclo de vida do produto, conforme elas sejam necessárias. Em geral, se o formulário, a adequação e a função do produto permanecerem iguais, crie uma nova versão em vez de um novo produto.

- **As sugestões de grade de produto funcionam como de costume.**

    As sugestões de grade de produto criarão sugestões para todos os valores de dimensão de versão, como ocorre com outras dimensões. O processo de criação e liberação de produtos com versão é o mesmo utilizado para os produtos que usam outras dimensões. Quando você criar um produto com versão, a primeira versão (V1) será criada como uma dimensão de produto e as grades serão liberadas. À medida que o produto for alterado e uma nova versão for necessária, o valor da nova versão (V2) será adicionado e as grades necessárias serão liberadas. Não há expectativa de que todas as versões (V1, V2 e V3) serão criadas antecipadamente para o produto.

> [!IMPORTANT]
> Se você ativar e usar a dimensão de versão, algumas soluções que fazem referência a dimensões de estoque poderão parar de funcionar conforme esperado. Para confirmar e corrigir esses problemas, fale com o fornecedor de software independente (ISV) para obter as soluções afetadas. Para obter mais informações, consulte [Habilitar a dimensão da versão](#enable-version-dim).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]