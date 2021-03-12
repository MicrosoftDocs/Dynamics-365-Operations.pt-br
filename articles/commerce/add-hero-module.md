---
title: Módulo de bloco de conteúdo
description: Este tópico abrange os módulos de bloco de conteúdo e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6359c915d053bb00c969b166325f675c0003ead
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980348"
---
# <a name="content-block-module"></a>Módulo de bloco de conteúdo


[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de bloco de conteúdo e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de bloco de conteúdo é usado para divulgar produtos ou promoções por meio de uma combinação de imagens e texto. Por exemplo, um varejista pode adicionar um módulo de bloco de conteúdo à home page de um site de comércio eletrônico para promover um novo produto e atrair a atenção dos clientes.

Um módulo de bloco de conteúdo é direcionado por dados do sistema de gerenciamento de conteúdo (CMS). É um módulo autônomo que não depende de nenhum outro módulo na página. Um módulo de bloco de conteúdo pode ser colocado em qualquer página do site em que um varejista queira divulgar ou promover algo (por exemplo, produtos, vendas ou recursos).

## <a name="examples-of-content-block-module-in-e-commerce"></a>Exemplos de módulo de bloco de conteúdo no comércio eletrônico

- Um módulo de bloco de conteúdo pode ser usado na home page de um site de comércio eletrônico para destacar promoções e novos produtos.
- Um módulo de bloco de conteúdo pode ser usado em uma página de detalhes do produto para mostrar informações do produto.
- Vários módulos de bloco de conteúdo podem ser colocados dentro de um módulo de carrossel para destacar vários produtos ou promoções.

## <a name="content-block-modules-and-themes"></a>Temas e módulos de bloco de conteúdo

Os módulos de bloco de conteúdo podem dar suporte a vários layouts e estilos com base em um tema. Por exemplo, o tema Fabrikam oferece suporte a três variações de layout de um módulo de bloco de conteúdo: hero, recurso e bloco. O layout de hero mostra uma imagem no plano de fundo com sobreposição de texto. O layout de recurso mostra uma imagem e um texto lado a lado. O layout de bloco permite vários blocos de conteúdo em um formato de bloco.

Além disso, o tema pode expor diferentes propriedades de cada layout. Um desenvolvedor de temas pode criar mais layouts com mais estilos usando o módulo de bloco de conteúdo.

A imagem a seguir mostra um exemplo de módulo de bloco de conteúdo com layout de hero.

![Exemplo de um módulo de herói](./media/Hero.PNG)

A imagem a seguir mostra um exemplo de módulo de bloco de conteúdo com layout de recurso.

![Exemplos de módulos de recursos](./media/Feature.PNG)

## <a name="content-block-module-properties"></a>Propriedades do módulo de bloco de conteúdo

| Nome da propriedade  | Valores | Descrição |
|----------------|--------|-------------|
| Imagem          | Arquivo de imagem | Uma imagem pode ser usada para mostrar um produto ou uma promoção. Uma imagem pode ser carregada na galeria de imagens ou uma imagem existente pode ser usada. |
| Cabeçalho        | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Todo módulo de hero pode ter um cabeçalho. Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho. No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade. |
| Parágrafo      | Texto de parágrafo | Os módulos de hero é compatível com texto de parágrafo em formato rich text. Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks. Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo. |
| Vincular           | Texto do link, URL do link, etiqueta ARIA (Accessible Rich Internet Applications) e **Abrir link em uma nova guia** | Os módulos de hero oferecem suporte a um ou mais links de "chamada à ação". Se um link for adicionado, será necessário o texto do link, uma URL e uma etiqueta ARIA. As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade. Os links podem ser configurados para serem abertos em uma nova guia. |

## <a name="content-block-module-properties-exposed-by-the-fabrikam-theme"></a>Propriedades do módulo de bloco de conteúdo expostas pelo tema Fabrikam 

| Nome da propriedade  | Valores | Descrição |
|----------------|--------|-------------|
| Posicionamento do texto | **Esquerda**, **Direita**, **Centro** | Esta propriedade define a posição do texto na imagem. Ela só se aplica ao layout de hero. |
| Tema de texto     | **Claro** ou **Escuro** | Um esquema de cores pode ser definido para o texto, com base na imagem de plano de fundo. Por exemplo, se a imagem tiver um fundo escuro, um tema claro poderá ser aplicado para tornar o texto mais visível e atender às taxas de contraste de cores para fins de acessibilidade. Ela só se aplica ao layout de hero.|
| Posicionamento de Imagem       | **Esquerda**, **Direita** | Esta propriedade especifica se a imagem deve ficar à esquerda ou à direita do texto. Ela só se aplica ao layout de recurso.  |

## <a name="add-a-content-block-module-to-a-new-page"></a>Adicionar um módulo de bloco de conteúdo a uma nova página

Para adicionar um módulo de hero a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Modelos** e crie um modelo de página chamado **Modelo de bloco de conteúdo**.
1. No slot **Principal** da página padrão, adicione um módulo de hero.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Use o modelo de hero recém-criado para criar uma página chamada **Página de bloco de conteúdo**.
1. No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar módulo**, em **Selecionar módulos**, selecione um módulo de hero e depois selecione **OK**.
1. Na árvore de estrutura de tópicos à esquerda, selecione o módulo de bloco de conteúdo.
1. No painel de propriedades à direita, selecione **Adicionar uma imagem**. Em seguida, selecione uma imagem existente ou carregue uma nova imagem.
1. Selecione **Título**.
1. Na caixa de diálogo **Título**, adicione o texto do cabeçalho, selecione o nível do cabeçalho e selecione **OK**.
1. Em **Rich Text**, adicione o texto como necessário.
1. Selecione **Adicionar Link**.
1. Na caixa de diálogo **Link**, adicione o texto do link, uma URL do link e uma etiqueta ARIA para o link e selecione **OK**.
1. Selecione o layout **Hero**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo. 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de banner de promoção](add-alert.md)

[Módulo do carrossel](add-carousel.md)

[Módulo de bloco de texto](add-content-rich-block.md)

[Módulo de reprodutor de vídeo](add-video-player.md)
