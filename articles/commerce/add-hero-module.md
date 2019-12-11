---
title: Módulo de hero
description: Este tópico abrange os módulos de hero e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785372"
---
# <a name="hero-module"></a>Módulo de hero

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de hero e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de hero é usado para comercializar produtos ou promoções por meio de uma combinação de imagens e texto. Por exemplo, um varejista pode adicionar um módulo de hero à home page de um site de comércio eletrônico para promover um novo produto e atrair a atenção dos clientes.

Um módulo de hero é direcionado por dados do sistema de gerenciamento de conteúdo (CMS). É um módulo autônomo que não depende de nenhum outro módulo na página. Um módulo de hero pode ser colocado em qualquer página do site em que um varejista queira comercializar ou promover algo (por exemplo, produtos, vendas ou recursos).

## <a name="examples-of-hero-module-in-e-commerce"></a>Exemplos de módulo de hero no comércio online

- Um módulo de hero pode ser usado na home page de um site de comércio eletrônico para destacar promoções e novos produtos.
- Um módulo de hero pode ser usado em uma página de detalhes do produto para mostrar informações do produto.
- Vários módulos de hero podem ser colocados dentro de um módulo de carrossel para destacar vários produtos ou promoções.

## <a name="hero-module-properties"></a>Propriedades de módulo de hero

| Nome da propriedade  | Valores | Descrição |
|----------------|--------|-------------|
| Imagem          | Arquivo de imagem | Uma imagem pode ser usada para mostrar um produto ou uma promoção. Uma imagem pode ser carregada na galeria de imagens ou uma imagem existente pode ser usada. |
| Cabeçalho        | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Todo módulo de hero pode ter um cabeçalho. Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho. No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade. |
| Parágrafo      | Texto de parágrafo | Os módulos de hero é compatível com texto de parágrafo em formato rich text. Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks. Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo. |
| Vincular           | Texto do link, URL do link, etiqueta ARIA (Accessible Rich Internet Applications) e **Abrir link em uma nova guia** | Os módulos de hero oferecem suporte a um ou mais links de "chamada à ação". Se um link for adicionado, será necessário o texto do link, um URL e uma etiqueta ARIA. As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade. Os links podem ser configurados para serem abertos em uma nova guia. |
| Posicionamento do texto | **Esquerdo superior**, **Direito superior**, **Superior central**, **Esquerdo inferior**, **Direito inferior**, **Centro inferior**, **Centro esquerdo**, **Centro direito** ou **Centro central** | Esta propriedade define a posição da imagem em relação ao texto. Por exemplo, se **Direito** estiver selecionado, a imagem aparecerá à direita do texto. |
| Tema de texto     | **Claro** ou **Escuro** | Um esquema de cores pode ser definido para o texto, com base na imagem de plano de fundo. Por exemplo, se a imagem tiver um fundo escuro, um tema claro poderá ser aplicado para tornar o texto mais visível e atender às taxas de contraste de cores para fins de acessibilidade. |
| Gradiente       | **Verdadeiro** ou **Falso** | Um gradiente pode ser aplicado à imagem para atender às taxas de contraste de cores para fins de acessibilidade. |

## <a name="add-a-hero-module-to-a-new-page"></a>Adicionar um módulo de hero a uma nova página

Para adicionar um módulo de hero a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Modelos** e crie um modelo de página chamado **modelo de hero**.
1. No slot **Principal** da página padrão, adicione um módulo de hero.
1. Faça check-in do modelo e publique-o.
1. Use o modelo de hero que criou para criar uma página nomeada **página de hero**.
1. No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar módulo**, em **Selecionar módulos**, selecione um módulo de hero e depois selecione **OK**.
1. Na árvore de estrutura de tópicos à esquerda, selecione o módulo de hero.
1. No painel de propriedades à direita, selecione **Adicionar uma imagem**. Em seguida, selecione uma imagem existente ou carregue uma nova imagem.
1. Selecione **Título**.
1. Na caixa de diálogo **Título**, adicione o texto do cabeçalho, selecione o nível do cabeçalho e selecione **OK**.
1. Em **Rich Text**, adicione o texto como necessário.
1. Selecione **Adicionar link de ação**.
1. Na caixa de diálogo **Action Link**, adicione o texto do link, uma URL do link e uma etiqueta ARIA para o link e selecione **OK**.
1. Salve a página e visualize suas alterações.
1. Insira a página e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de carrossel](add-carousel.md)

[Módulo de bloco de conteúdo sofisticado](add-content-rich-block.md)

[Módulo de posicionamento de conteúdo](add-content-placement-modules.md)

[Módulo de recurso](add-feature-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)
