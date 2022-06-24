---
title: Módulo de lista de blocos
description: Este artigo abrange os módulos de lista de blocos e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 44eb9b82ef9625734c7fe5ccba85207d9f210a00
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905389"
---
# <a name="tile-list-module"></a>Módulo de lista de blocos

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de lista de blocos e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Um módulo de lista de blocos é uma coleção de peças em um carrossel. Ele é usado para comercializar categorias de produtos ou marcas de produto por meio de imagens e texto. Por exemplo, um varejista pode adicionar um módulo de lista de blocos à página inicial de um site de comércio eletrônico para promover todas as principais categorias de vendas.

O módulo de lista de blocos é baseado em dados do sistema de gerenciamento de conteúdo (CMS). Ele não depende de outros módulos ou dados do Commerce headquarters. O módulo de lista de blocos pode ser colocado a qualquer página do site em que um varejista queira divulgar ou promover algo (por exemplo, produtos, categorias ou marcas).

A ilustração a seguir mostra um exemplo de um módulo de lista de blocos e módulos de blocos na página inicial do Adventure Works.

![Exemplo de um módulo de lista de blocos e módulos de blocos na página inicial do Adventure Works](./media/Tile_list.PNG)

> [!IMPORTANT]
> O módulo de lista de blocos está disponível a partir da versão 10.0.20 do Dynamics 365 Commerce.
> O módulo de lista de blocos é apresentado no tema Adventure Works.

## <a name="tile-list-modules-and-themes"></a>Temas e módulos de lista de blocos

O módulo de lista de blocos pode oferecer suporte a vários layouts e estilos com base em um tema. Por exemplo, no tema Adventure Works, os blocos mostram um efeito de animação quando os usuários do site movem o cursor sobre eles. Cada tema pode conter propriedades adicionais para a lista de blocos e os módulos de blocos. Os desenvolvedores de temas também podem criar layouts adicionais para a lista de blocos e os módulos de blocos.

## <a name="tile-list-module-properties"></a>Propriedades do módulo de lista de blocos

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Título       | Texto do cabeçalho e tag do cabeçalho | Um cabeçalho de texto para o módulo de lista de blocos. |

## <a name="tile-module-properties"></a>Propriedades do módulo de blocos

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Imagem         | Arquivo de imagem | Uma imagem pode ser usada para mostrar um produto ou uma categoria. A imagem pode ser carregada na Biblioteca de mídia do criador de sites do Commerce ou uma imagem existente pode ser usada. |
| Título       | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Por padrão, a tag de cabeçalho **H2** é usada, mas a tag do cabeçalho pode ser alterada para atender aos requisitos de acessibilidade. |
| Parágrafo     | Texto de parágrafo | O módulo oferece suporte a texto de parágrafo em formato rich text. Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks. Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo. |
| Vincular          | Texto do link, URL do link, etiqueta ARIA (Accessible Rich Internet Applications) e **Abrir link em uma nova guia** | Os módulos oferecem suporte a um ou mais links de "chamada à ação". Se um link for adicionado, será necessário o texto do link, uma URL e uma etiqueta ARIA. As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade. Os links podem ser configurados para serem abertos em uma nova guia. |
| Link do bloco     | Texto do link, URL do link, etiqueta ARIA e seletor **Abrir link em uma nova guia** | Esta propriedade é usada para definir um link de "chamada à ação". Se um link for adicionado, será necessário o texto do link, uma URL e uma etiqueta ARIA. As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade. Os links podem ser configurados para serem abertos em uma nova guia.|
| Ícone          | Imagem | Além de uma imagem de produto ou categoria, um símbolo de ícone pode ser adicionado. A imagem do ícone será exibida acima da imagem do produto ou da categoria. |

## <a name="add-a-tile-list-module-to-a-new-page"></a>Adicionar um módulo de lista de blocos a uma nova página

Para adicionar um módulo de lista de blocos uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Acesse **Modelos** e abra o modelo de marketing para a página inicial do seu site (ou crie um novo modelo de marketing).
1. No slot **Principal** da página padrão, selecione as reticências (**...**) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Lista de blocos** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e abra a página inicial do site (ou crie uma nova página inicial usando o modelo de marketing).
1. No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Lista de blocos** e, depois, **OK**.
1. No painel de propriedades do módulo de lista de blocos, adicione um cabeçalho.
1. No slot **Lista de blocos**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Módulo de blocos** e, depois, **OK**.
1. No painel de propriedades do módulo de blocos, adicione uma imagem, um título e uma imagem de símbolo de ícone.
1. Adicione e configure módulos de blocos adicionais conforme necessário.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Visão geral do tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
