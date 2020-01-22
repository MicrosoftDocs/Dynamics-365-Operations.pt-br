---
title: Trabalhar com módulos
description: Este tópico descreve como e quando usar os módulos no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3c4161e7a40cdbbb40292a6ce9acab58347460bd
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914785"
---
# <a name="work-with-modules"></a>Trabalhar com módulos

Este tópico descreve como e quando usar os módulos no Microsoft Dynamics 365 Commerce.

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a>Visão geral

Módulos são blocos de construção lógicos que compõem a estrutura da sua página e têm vários objetivos e escopos. Alguns módulos são contêineres de alto nível e seu único objetivo é manter e organizar outros módulos (módulos filhos). Outros módulos, como um módulo simples de posicionamento de imagem, têm uma finalidade muito específica. Outros módulos, como um módulo de carrossel, estão em algum lugar entre essas duas categorias.

Por padrão, seu site do Dynamics 365 Commerce contém uma biblioteca de módulos do kit de início que permite alcançar os cenários mais básicos de comércio eletrônico. Você poderá criar um site de comércio eletrônico completo apenas usando esses módulos. No entanto, você também pode querer personalizar esses módulos ou criar novos módulos personalizados para necessidades específicas. Se quiser construir módulos personalizados, um SDK (Kit de Desenvolvimento de Software para criação de módulo) está disponível para ajudá-lo a criar uma biblioteca de módulos personalizados.

## <a name="container-modules-and-slots"></a>Módulos e slots de contêiner

Como mencionado anteriormente, alguns módulos são projetados para conter módulos filhos. Esse módulos são conhecidos como *contêineres*, e permitem hierarquias de módulos aninhadas. Os módulos do contêiner contém *slots*. Os slots são usados para manipular o layout e a finalidade dos módulos filhos no contêiner. Um exemplo é um módulo básico de contêiner de página (um módulo de nível superior para qualquer página) que define vários slots importantes:

- Um slot de cabeçalho
- Um slot de corpo
- Um slot de rodapé

O desenvolvedor do módulo define esses slots e determina quais módulos filhos e quantos módulos filhos podem ser colocados diretamente dentro dele. Por exemplo, o slot do cabeçalho pode suportar apenas um módulo do tipo **Módulo do Cabeçalho**, enquanto o slot do corpo pode suportar um número ilimitado de módulos de qualquer tipo (exceto outros módulos de contêiner de página).

Nas ferramentas de criação, os autores de página não precisam saber com antecedência quais módulos podem e não podem ser colocados em cada slot. Quando os autores da página selecionam um slot e, em seguida, tentam selecionar um módulo para adicioná-lo, eles veem uma exibição filtrada dos tipos de módulos suportados por esse slot.

## <a name="content-modules"></a>Módulos de conteúdo

Os módulos de conteúdo contêm elementos de conteúdo e mídia, como texto (por exemplo, títulos, parágrafos e links) ou referências de ativos (por exemplo, imagens, vídeo e PDFs). Exemplos de tipos típicos de módulos de conteúdo são **Herói**, **Recurso** e **Banner**. Os módulos desses três tipos podem conter texto ou mídia e não exigem módulos filhos para tornar algo visível em uma página.

A maioria das atividades típicas diárias de criação de página e conteúdo envolve módulos de conteúdo, principalmente porque esses módulos definem o conteúdo real que é renderizado em seus módulos de contêiner pai Muitos módulos de conteúdo estão disponíveis, e esses módulos geralmente são as últimas partes que você adicionará à hierarquia de módulos aninhados de uma página.

A ilustração a seguir mostra como os módulos são aninhados nos slots de módulo de contêiner pai.

![Aninhando módulos](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Adicionar ou remover módulos

Os procedimentos a seguir descrevem como adicionar e remover módulos.

### <a name="add-a-module"></a>Adicionar um módulo

Para adicionar um módulo a um slot ou contêiner em uma página, siga estas etapas.

1. No painel de estrutura de tópicos à esquerda, selecione um contêiner ou slot ao qual um módulo filho possa ser adicionado.

    > [!NOTE]
    > O designer do módulo define a lista de tipos de módulos que podem ser adicionados a um slot de módulo específico. Os autores de modelos podem refinar as opções permitidas do módulo para ajudar a garantir otimização consistente do mecanismo de pesquisa (SEO) e eficiência de autoria para todas as páginas das páginas criadas a partir de um modelo específico.

1. Selecione o botão de reticências (**...**) para o módulo e selecione **Adicionar Módulo**. A caixa de diálogo **Adicionar Módulo** será exibida. Essa caixa de diálogo é filtrada automaticamente para mostrar apenas os módulos suportados no contêiner ou no slot selecionado. A lista de módulos é determinada pelo modelo da página ou pela definição do módulo do contêiner.

    > [!NOTE]
    > Se um contêiner ou slot não suportar novos módulos filhos, a opção **Adicionar Módulo** não ficará disponível.

1. Na caixa de diálogo, procure e selecione um módulo para adicionar à sua página.

    > [!TIP]
    > **Recurso** e **Herói** são bons tipos de módulo para os iniciantes trabalharem.

1. Selecione **OK** para adicionar o módulo selecionado ao contêiner ou slot selecionado em sua página.

### <a name="remove-a-module"></a>Remover um módulo

Para remover um módulo de um slot ou contêiner de uma página, siga estas etapas.

1. No painel de estrutura de tópicos à esquerda, selecione o botão de reticências ao lado do nome do módulo a ser removido e, em seguida, selecione o botão da lixeira.
1. Quando for solicitado para confirmar se você deseja remover o módulo, selecione **OK**.

## <a name="configure-modules"></a>Configurar módulos

Os procedimentos a seguir descrevem como configurar os módulos de conteúdo e contêiner.

### <a name="configure-a-content-module"></a>Configurar um módulo de conteúdo

Para configurar um módulo de conteúdo em uma página, siga estas etapas.

1. No painel da estrutura de tópicos à esquerda, selecione um tipo de módulo de conteúdo (por exemplo, **Recurso**, **Herói** ou **Banner**).
1. No painel de propriedades à direita, expanda os controles aninhados selecionando os cabeçalhos e defina quaisquer valores de controle necessários.
1. Se o painel de propriedades tiver uma seção de **Configuração de Dados**, selecione-a para expandi-la. Caso contrário, vá para a etapa 5.
1. Se houver um botão **Adicionar Fonte de Dados** selecione-o e escolha os itens de conteúdo a serem adicionados.
1. Insira as configurações para quaisquer controles de módulo necessários ou desejados.
1. Selecione **Salvar**.

### <a name="configure-a-container-module"></a>Configurar um módulo de contêiner

Para configurar um módulo de contêiner em uma página, siga estas etapas.

1. Selecione um módulo de contêiner em sua página (por exemplo, um carrossel ou um módulo fluido do contêiner).
1. No painel de propriedades à direita, expanda os controles aninhados selecionando os cabeçalhos e defina quaisquer valores de controle necessários.
1. No painel de estrutura de tópicos à esquerda, selecione o botão de reticências ao lado do nome do contêiner ou de quaisquer slots dentro do contêiner e, em seguida, selecione **Adicionar Módulo**. Em seguida, adicione os módulos filho ao contêiner selecionado. Para obter mais informações, consulte o procedimento [Adicionar um módulo](#add-a-module) anterior neste tópico.
1. Se vários módulos filho existirem como irmãos um contêiner pai, poderá alterar a ordem de exibição no contêiner pai. Selecione o botão de reticências para um módulo, e use os botões de seta para cima e a seta para baixo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Trabalhar com modelos](work-with-templates.md)

[Trabalhar com layouts predefinidos](work-with-layouts.md)

[Trabalhar com fragmentos](work-with-fragments.md)

[Adicionar um módulo de contêiner a uma página](add-container-module.md)

[Adicionar módulos de posicionamento de conteúdo a uma página](add-content-placement-modules.md)

[Trabalhar com grupos de publicações](publish-groups.md)

