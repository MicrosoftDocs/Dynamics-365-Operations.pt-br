---
title: Módulo de recurso
description: Este tópico abrange os módulos de recurso e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785274"
---
# <a name="feature-module"></a>Módulo de recurso 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de recurso e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de recurso é usado para comercializar produtos ou promoções por meio de uma combinação de imagens e texto. Por exemplo, um revendedor pode adicionar um módulo de recurso a uma página de detalhes do produto para destacar os recursos do produto.

Um módulo de recurso é direcionado por dados do sistema de gerenciamento de conteúdo (CMS). É um módulo autônomo que não depende de nenhum outro módulo na página. Um módulo de recurso pode ser colocado em qualquer página do site em que um varejista queira comercializar ou promover algo (por exemplo, produtos, vendas ou recursos).

## <a name="examples-of-feature-modules-in-e-commerce"></a>Exemplos de módulos de recurso no comércio online

Um módulo de recurso pode ser usado nas seguintes páginas:

- Uma página de detalhes do produto, para mostrar os recursos do produto
- A home page, para promover produtos
- Uma página de categoria, para destacar uma categoria de produtos

## <a name="feature-module-properties"></a>Propriedades do módulo de recurso

| Nome da propriedade     | Valores | Descrição |
|-------------------|--------|-------------|
| Imagem             | Arquivo de imagem | Uma imagem pode ser usada para comercializar o produto ou promoção. Uma imagem pode ser carregada na galeria de imagens ou uma imagem existente pode ser usada. |
| Cabeçalho           | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Todo módulo de recurso pode ter um cabeçalho. Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho. No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade. |
| Parágrafo         | Texto de parágrafo | Os módulos de recurso é compatível com texto de parágrafo em formato rich text. Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks. Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo. |
| Vincular              | Texto do link, URL do link, etiqueta ARIA (Accessible Rich Internet Applications) e **Abrir link em uma nova guia** | Os módulos de recurso oferecem suporte a um ou mais links de "chamada à ação". Se um link for adicionado, será necessário o texto do link, um URL e uma etiqueta ARIA. As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade. Os links podem ser configurados para serem abertos em uma nova guia. |
| Posicionamento de Imagem   | **Direito**, **Esquerdo**, **Superior** ou **Inferior** | Esta propriedade define a posição da imagem em relação ao texto. Por exemplo, se **Direito** estiver selecionado, a imagem aparecerá à direita do texto. |
| Tamanho da coluna de imagem | Um valor de **1** a **12** | Esta propriedade define o tamanho da imagem em relação ao texto. O tamanho é expresso como um número de colunas na página. Existem 12 colunas em uma página. Por padrão, a imagem e o texto têm o mesmo tamanho (seis colunas cada). Contudo, o tamanho pode ser ajustado conforme necessário. |

## <a name="add-a-feature-module-to-a-new-page"></a>Adicionar um módulo de recurso a uma nova página 

Para adicionar um módulo de recurso a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Modelos** e crie um modelo de página chamado **modelo de recurso**.
1. No slot **Principal** da página padrão, adicione um módulo de recurso.
1. Faça check-in do modelo e publique-o.
1. Use o modelo de recurso que criou para criar uma página nomeada **página do recurso**.
1. No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar módulo**, em **Selecionar módulos**, selecione um módulo de recurso e depois selecione **OK**.
1. Na árvore de estrutura de tópicos à esquerda, selecione o módulo de recurso.
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

[Módulo de hero](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)
