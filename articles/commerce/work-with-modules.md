---
title: Trabalhar com módulos
description: Este tópico descreve como e quando usar os módulos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6d872719d3b1aa27ccfdcf36d7739c883e7b4996
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801352"
---
# <a name="work-with-modules"></a>Trabalhar com módulos

[!include [banner](includes/banner.md)]

Este tópico descreve como e quando usar os módulos no Microsoft Dynamics 365 Commerce.

Módulos são blocos de construção lógicos que compõem a estrutura da sua página e têm vários objetivos e escopos. Alguns módulos são contêineres de alto nível e seu único objetivo é manter e organizar outros módulos (módulos filhos). Outros módulos, como um módulo simples de posicionamento de imagem, têm uma finalidade muito específica. Outros módulos, como um módulo de carrossel, estão em algum lugar entre essas duas categorias.

Por padrão, seu site do Dynamics 365 Commerce contém uma biblioteca de módulos que permite alcançar os cenários mais básicos de comércio eletrônico. Você poderá criar um site de comércio eletrônico completo apenas usando esses módulos. No entanto, você também pode querer personalizar esses módulos ou criar novos módulos personalizados para necessidades específicas. Se quiser construir módulos personalizados, um SDK (Kit de Desenvolvimento de Software para criação de módulo) está disponível para ajudá-lo a criar uma biblioteca de módulos personalizados.

## <a name="container-modules-and-slots"></a>Módulos e slots de contêiner

Como mencionado anteriormente, alguns módulos são projetados para conter módulos filhos. Esse módulos são conhecidos como *contêineres*, e permitem hierarquias de módulos aninhadas. Os módulos do contêiner contém *slots*. Os slots são usados para manipular o layout e a finalidade dos módulos filhos no contêiner. Um exemplo é um módulo básico de contêiner de página (um módulo de nível superior para qualquer página) que define vários slots importantes:

- Um slot de cabeçalho
- Um slot de subcabeçalho
- Um slot principal
- Um slot de rodapé
- Um slot de sub-rodapé

O desenvolvedor do módulo define esses slots e determina quais módulos filhos e quantos módulos filhos podem ser colocados diretamente dentro dele. Por exemplo, o slot do cabeçalho pode suportar apenas um módulo do tipo **Módulo do Cabeçalho**, enquanto o slot do corpo pode suportar um número ilimitado de módulos de qualquer tipo (exceto outros módulos de contêiner de página).

Nas ferramentas de criação, os autores de página não precisam saber com antecedência quais módulos podem e não podem ser colocados em cada slot. Quando os autores da página selecionam um slot e, em seguida, tentam selecionar um módulo para adicioná-lo, eles veem uma exibição filtrada dos tipos de módulos suportados por esse slot.

## <a name="content-modules"></a>Módulos de conteúdo

Os módulos de conteúdo contêm elementos de conteúdo e mídia, como texto (por exemplo, títulos, parágrafos e links) ou referências de ativos (por exemplo, imagens, vídeo e PDFs). Os tipos de módulos de conteúdo típicos incluem módulos de bloco de conteúdo, bloco de texto e faixa promocional. Os módulos desses três tipos podem conter texto ou mídia e não exigem módulos filhos para tornar algo visível em uma página.

A maioria das atividades típicas diárias de criação de página e conteúdo envolve módulos de conteúdo, principalmente porque esses módulos definem o conteúdo real que é renderizado em seus módulos de contêiner pai Muitos módulos de conteúdo estão disponíveis, e esses módulos geralmente são as últimas partes que você adicionará à hierarquia de módulos aninhados de uma página.

A ilustração a seguir mostra como os módulos são aninhados nos slots de módulo de contêiner pai.

![Aninhando módulos](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Adicionar ou remover módulos

Os procedimentos a seguir descrevem como adicionar e remover módulos.

### <a name="add-a-module"></a>Adicionar um módulo

Para adicionar um módulo a um slot ou contêiner em uma página, siga estas etapas.

1. No painel de estrutura de tópicos à esquerda ou diretamente na tela principal, selecione um contêiner ou slot ao qual um módulo filho possa ser adicionado.

    > [!NOTE]
    > O designer do módulo define a lista de tipos de módulos que podem ser adicionados a um slot de módulo específico. Os autores de modelos podem refinar as opções de módulo permitidas para ajudar a garantir otimização consistente do mecanismo de pesquisa (SEO) e eficiência de autoria para todas as páginas criadas com base em um modelo específico. Ao adicionar um módulo a um slot, a caixa de diálogo **Adicionar Módulo** é filtrada automaticamente para mostrar apenas os módulos com suporte no contêiner ou slot selecionado. Esta lista de módulos permitidos é determinada pelo modelo da página ou pela definição do módulo do contêiner.

1. Se estiver usando o painel de estrutura de tópicos, selecione as reticências (**...**) ao lado do nome do módulo e selecione **Adicionar Módulo**. Se estiver usando os controles diretamente na tela, selecione o símbolo de adição (**+**) em um slot vazio ou adjacente ao módulo selecionado no momento e selecione **Adicionar Módulo**.

    > [!NOTE]
    > Se um contêiner ou slot não suportar novos módulos filhos, a opção **Adicionar Módulo** não ficará disponível.

1. Na caixa de diálogo **Adicionar Módulo**, selecione um módulo para adicionar à página.

    > [!TIP]
    > O **bloco de conteúdo** é um bom tipo de módulo para iniciantes.

1. Selecione **OK** para adicionar o módulo selecionado ao contêiner ou slot selecionado em sua página.

### <a name="remove-a-module"></a>Remover um módulo

Para remover um módulo de um slot ou contêiner de uma página, siga estas etapas.

1. No painel de estrutura de tópicos à esquerda, selecione as reticências (**...**) ao lado do nome do módulo a ser removido e, depois, selecione o símbolo de lixeira. Como alternativa, na tela principal, você pode selecionar o símbolo da lixeira na barra de ferramentas de um módulo selecionado.
1. Quando for solicitado a confirmar que você deseja remover o módulo, selecione **OK**.

## <a name="move-a-module-to-a-new-position"></a>Mover um módulo para uma nova posição

Para mover um módulo para uma nova posição na página, use um dos métodos a seguir.

### <a name="move-a-module-using-the-outline-pane"></a>Mover um módulo usando o painel de estrutura de tópicos

Para mover um módulo usando o painel de estrutura de tópicos, siga estas etapas.

1. Selecione e mantenha pressionado o módulo que deseja mover no painel de estrutura de tópicos e, em seguida, arraste o módulo para uma nova posição na estrutura de tópicos. A linha azul na estrutura de tópicos e na tela indica onde o módulo pode ser colocado.
1. Libere o módulo para soltá-lo na nova posição.

### <a name="move-a-module-directly-within-the-canvas"></a>Mover um módulo diretamente na tela

Para mover um módulo diretamente na tela, siga estas etapas.

1. Selecione o módulo a ser movido na tela. 
1. Selecione um símbolo de seta apontando para cima ou para baixo na barra de ferramentas do módulo e arraste a seta para uma nova posição na página. A linha azul na tela e na estrutura de tópicos indica onde o módulo pode ser colocado. Se um módulo não puder ser movido para cima ou para baixo, esse símbolo de seta ficará esmaecido. 
1. Libere o módulo para soltá-lo na nova posição.

### <a name="move-a-module-using-the-ellipsis-menu"></a>Mover um módulo usando o menu de reticências

Para mover um módulo usando o menu de reticências, siga estas etapas.

1. Selecione um módulo na estrutura de tópicos ou na tela.
1. Selecione as reticências (**...**) ao lado do nome do módulo no painel de estrutura de tópicos ou na barra de ferramentas do módulo selecionado na tela.
1. Se o módulo puder ser movido para cima ou para baixo no contêiner ou slot, você verá as opções para **Mover para cima** ou **Mover para baixo**. Selecione a opção de movimentação desejada para mover o módulo para cima ou para baixo em relação aos irmãos.

## <a name="configure-modules"></a>Configurar módulos

Os procedimentos a seguir descrevem como configurar os módulos de conteúdo e contêiner.

### <a name="configure-a-content-module"></a>Configurar um módulo de conteúdo

Para configurar um módulo de conteúdo em uma página, siga estas etapas.

1. No painel da estrutura de tópicos à esquerda, expanda a árvore e selecione qualquer módulo de conteúdo (por exemplo, **Bloco de conteúdo**). Como alternativa, você pode selecionar o módulo na tela principal.
1. No painel de propriedades do módulo, à direita, insira propriedades para os controles de módulo desejados.
1. Na barra de comandos, selecione **Salvar**. Isso também atualizará a tela de exibição.

### <a name="edit-module-text-properties"></a>Editar propriedades de texto do módulo

As propriedades de texto do módulo que não são somente leitura podem ser editadas diretamente na tela.

Para editar as propriedades de texto do módulo, siga estas etapas.

1. Selecione o controle de texto na tela e coloque o cursor no local onde deseja editar o texto.
1. Insira o conteúdo do seu texto.
1. Selecione qualquer local fora do conteúdo do texto para continuar editando outro conteúdo.

### <a name="inline-image-selection"></a>Seleção de imagem embutida

As imagens do módulo que não são somente leitura podem ser alteradas diretamente na tela.

Para escolher uma nova imagem para um módulo de conteúdo, siga estas etapas.

1. Na tela, clique duas vezes na imagem. Isso exibirá a janela do seletor de mídia.
1. Localize e selecione uma nova imagem a ser usada e selecione **OK**. A nova imagem agora é renderizada na tela.

### <a name="configure-a-container-module"></a>Configurar um módulo de contêiner

Para configurar um módulo de contêiner em uma página, siga estas etapas.

1. Selecione um módulo de contêiner em sua página (por exemplo, um carrossel ou um módulo fluido do contêiner).
1. No painel de propriedades à direita, expanda os controles aninhados selecionando os cabeçalhos e defina quaisquer valores de controle necessários.
1. No painel de estrutura de tópicos à esquerda, selecione o botão de reticências ao lado do nome do contêiner ou de quaisquer slots dentro do contêiner e, em seguida, selecione **Adicionar Módulo**. Em seguida, adicione os módulos filho ao contêiner selecionado. Para obter mais informações, consulte a seção [Trabalhar com módulos](#add-a-module) anterior nesse tópico.
1. Se vários módulos filho existirem como irmãos um contêiner pai, poderá alterar a ordem de exibição no contêiner pai. Selecione o botão de reticências para um módulo, e use os botões de seta para cima e a seta para baixo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Trabalhar com modelos](work-with-templates.md)

[Trabalhar com layouts predefinidos](work-with-layouts.md)

[Trabalhar com fragmentos](work-with-fragments.md)

[Adicionar um módulo de contêiner a uma página](add-container-module.md)

[Trabalhar com grupos de publicações](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
