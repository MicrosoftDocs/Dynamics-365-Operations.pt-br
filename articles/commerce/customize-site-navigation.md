---
title: Personalizar a navegação do site
description: Este tópico descreve como criar uma hierarquia online personalizada de navegação para organizar seus produtos para procurar no site do Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c2b6a7a3b35873e80be391c627d0397fd6398a99
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410174"
---
# <a name="customize-site-navigation"></a>Personalizar a navegação do site


[!include [banner](includes/banner.md)]

Este tópico descreve como criar uma hierarquia online personalizada de navegação para organizar seus produtos para procurar no site do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

As lojas online normalmente permitem que os clientes descubram e naveguem entre produtos por meio de categorias de produto. Este recurso é normalmente fornecido por guias na parte superior da página ou na barra de navegação à esquerda. No Dynamics 365 Commerce, você pode criar e gerenciar uma estrutura hierárquica de navegação da categoria e os produtos que estão incluídos nas várias categorias.

## <a name="create-a-channel-navigation-hierarchy"></a>Criar uma hierarquia de navegação de canal

Para criar uma hierarquia de navegação de canal, siga estas etapas.

1. Vá para **Varejo e Comércio \> Produtos e categorias \> Gerenciamento de categorias e produtos**.
1. Selecione **Hierarquias de categoria** e depois **Novo**.
1. Nomeie a hierarquia.

    > [!NOTE]
    > A categoria mais alta que você cria é o nó de categoria raiz. Não será exibido no site. Para criar uma hierarquia de categoria onde um único nó superior é mostrada no site, crie e nomeie a categoria como filho da categoria raiz.

1. Selecione **Novo nó da categoria**, e o nome da categoria.
1. Continue ao criar categorias irmão e filho como necessário.

Agora você pode atribuir produtos a cada categoria criada na categoria de nível superior.

## <a name="customize-the-order-of-categories"></a>Personalizar a ordem de categorias

Por padrão, as categorias que você define em ordem alfabética aparecerão no site. Entretanto, é possível personalizar a ordem de exibição de categorias.

## <a name="assign-a-category-hierarchy-type"></a>Atribuir um tipo de hierarquia de categoria

1. Vá para **Varejo e Comércio \> Produtos e categorias \> Gerenciamento de categorias e produtos**.
1. Selecione **Hierarquias de categoria**.
1. No Painel de Ação, na guia **Hierarquias de categoria**, no grupo **Configurar**, selecione **Associar tipo de hierarquia**.
1. Selecione **Novo**.
1. No campo **Tipo de hierarquia de categoria**, selecione **Hierarquia de navegação de canal**.
1. No campo **Hierarquia de categoria**, selecione a hierarquia de navegação de canal criadas anteriormente.

## <a name="publish-new-or-updated-navigation-hierarchies"></a>Publicar hierarquias de navegação novas ou atualizadas

Para tornar sua hierarquia de navegação disponível na loja online, siga essas etapas.

1. Vá para **Varejo e Comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. Na árvore a esquerda, selecione seu armazenamento online.
1. Selecione **Publicar atualizações de canal**.
1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. Na lista, localize e selecione **Trabalho 1040**.
1. Selecione **Executar agora**.
1. Repita as etapas 5 e 6 para a trabalhos 1070 e 1150.

## <a name="show-categories-on-your-site"></a>Exibir categorias no site

Para exibir sua hierarquia de categoria na loja online, você deve adicionar o módulo do menu de navegação no local apropriado em um modelo ou fragmento. O módulo de menu de navegação mostrará a hierarquia de navegação, desde que você a tenha publicado no canal ao qual o site está associado.

> [!NOTE]
> O módulo de menu de navegação incluído na biblioteca de módulos permite que os usuários naveguem somente até categorias que não tenham subcategorias. Se seus clientes podem navegar em categorias que têm subcategorias, você deve personalizar o módulo de menu de navegação.

## <a name="add-custom-navigation-options"></a>Adicionar opções de navegação personalizadas

No menu de navegação, você pode adicionar opções de navegação que não fazem parte da hierarquia da categoria de produto. Por exemplo, no final da lista de categorias de produtos, você pode adicionar um item **Fale conosco** que aponta para uma página de contato criada para o site.

Para adicionar opções personalizados de navegação no menu de navegação, siga essas etapas.

1. No modelo ou fragmento que deseja personalizar, selecione o módulo de menu de navegação.
1. No painel de propriedade, na guia **Dados**, selecione **Adicionar item** para criar um novo item de conteúdo de navegação (CMS) do sistema de gerenciamento.
1. Insira o texto do link e uma URL.
1. Repita as etapas 2 e 3 para adicionar mais uma opções personalizadas de navegação.
1. Quando terminar, selecione **Salvar** para salvar o modelo ou o fragmento e, em seguida, selecione **Concluir a edição** para fazer o respectivo check-in.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Trabalhar com modelos](work-with-templates.md)

[Trabalhar com layouts predefinidos](work-with-layouts.md)

[Trabalhar com fragmentos](work-with-fragments.md)

[Trabalhar com módulos](work-with-modules.md)

[Criar uma URL da página](create-page-url.md)

[Trabalhar com grupos de publicações](publish-groups.md)
