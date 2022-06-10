---
title: Módulo de recurso interativo
description: Este tópico abrange os módulos de recurso interativos e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 3ab325189812289390740e31fd673ee9892f9759
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780730"
---
# <a name="interactive-feature-module"></a>Módulo de recurso interativo

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de recurso interativos e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Os módulos de recursos interativos são módulos do tipo mosaico que podem ser usados para comercializar várias categorias de produtos ou marcas de produto usando uma combinação de imagens e texto. Por exemplo, um varejista pode adicionar um módulo de recurso interativo à página inicial de um site de comércio eletrônico para promover as principais categorias de vendas. O módulo de recurso interativo é semelhante ao módulo de lista de blocos, mas tem um layout diferente e uma funcionalidade de interação diferente.

Cada módulo de recurso interativo é um conjunto de módulos de itens de recursos interativos. Cada item de módulo de recurso é baseado em dados do sistema de gerenciamento de conteúdo (CMS). Ele não depende de outros módulos ou dados da matriz do Commerce. O módulo de recurso interativo pode ser colocado a qualquer página do site em que um varejista queira divulgar ou promover algo (por exemplo, produtos, categorias ou marcas).

> [!IMPORTANT]
> - O módulo de recurso interativo está disponível a partir da versão 10.0.20 do Dynamics 365 Commerce.
> - O módulo de recurso interativo é apresentado no tema Adventure Works.

A ilustração a seguir mostra um exemplo de um módulo de recurso interativo na página inicial do Adventure Works.

![Exemplo de um módulo de recurso interativo na página inicial do Adventure Works](./media/Feature.PNG)

## <a name="interactive-feature-module-and-themes"></a>Módulo de recurso interativo e temas

O módulo de recurso interativo pode oferecer suporte a vários layouts e estilos com base em um tema. Por exemplo, no tema Adventure Works, o módulo de recurso interativo tem um layout de duas colunas que mostra os efeitos de animação quando um usuário do site move o cursor sobre cada item. O módulo de recurso interativo é otimizado para um número par de imagens que são organizadas em um layout de duas colunas.

## <a name="interactive-feature-module-properties"></a>Propriedades do módulo de recurso interativo

| Nome da propriedade | Valores | Descrição |
|---------------|--------|-------------|
| Título       | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Um cabeçalho de texto para o módulo de recurso interativo. |

## <a name="interactive-feature-item-module-properties"></a>Propriedades do módulo de item de recurso interativo

| Nome da propriedade | Valores | Descrição |
|---------------|--------|-------------|
| Imagem         | Arquivo de imagem | Uma imagem que representa um produto ou uma categoria. A imagem pode ser carregada na Biblioteca de mídia do criador de sites do Commerce ou uma imagem existente pode ser usada. |
| Título       | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Por padrão, a tag de cabeçalho **H2** é usada, mas a tag do cabeçalho pode ser alterada para atender aos requisitos de acessibilidade. |
| Parágrafo     | Texto de parágrafo | O módulo oferece suporte a texto de parágrafo em formato rich text. Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks. Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo. |
| Vincular          | Texto do link, URL do link, rótulo ARIA (Accessible Rich Internet Applications) e seletor **Abrir link em uma nova guia** | O módulo oferece suporte a um ou mais links de "chamada à ação". Se um link for adicionado, será necessário o texto do link, uma URL e uma etiqueta ARIA. As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade. Os links podem ser configurados para serem abertos em uma nova guia. |

## <a name="add-an-interactive-feature-module-to-a-new-page"></a>Adicionar um módulo de recurso interativo a uma nova página

Para adicionar um módulo de recurso interativo a uma nova página e definir as propriedades necessárias criador de sites do Commerce, siga as etapas a seguir.

1. Acesse **Modelos** e abra o modelo de marketing para a página inicial do seu site (ou crie um novo modelo de marketing).
1. No slot **Principal** da página padrão, selecione as reticências (**...**) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Recurso interativo** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e abra a página inicial do site (ou crie uma nova página inicial usando o modelo de marketing).
1. No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, em **Selecionar Módulos**, selecione um **Recurso interativo** e, depois, **OK**.
1. No painel de propriedades do módulo de recurso interativo, adicione um cabeçalho.
1. No slot **Recurso interativo**, selecione o botão de reticências (**...**) e, depois, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Item de recurso interativo** e, depois, **OK**.
1. No painel de propriedades do módulo do item de recurso interativo, adicione uma imagem, texto de título, texto de parágrafo e uma URL.
1. Adicione e configure módulos de recurso interativo adicionais conforme necessário.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Visão geral do tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
