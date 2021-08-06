---
title: Módulo de lista de imagens
description: Este tópico abrange os módulos de lista de imagens e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b7e070bfe562bb1a28b10d4632725b53a090cda4
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638821"
---
# <a name="image-list-module"></a>Módulo de lista de imagens

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de lista de imagens e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

O módulo lista de imagens pode ser usado para adicionar facilmente um conjunto (matriz) de imagens a páginas do site. Cada imagem da matriz pode ser configurada com texto de parágrafo e URLs de link. O módulo de lista de imagens é mais adequado para exibir logotipos de marcas ou uma lista que inclua logotipos.

> [!IMPORTANT]
> - O módulo de lista de imagens está disponível na biblioteca de módulos do Commerce a partir da versão 10.0.20 do Dynamics 365 Commerce.
> - O módulo de lista de imagens é apresentado no tema Adventure Works.

A ilustração a seguir mostra um exemplo em que um módulo de lista de imagens exibe uma lista de texto que inclui logotipos em uma página do site empresa-para-consumidor (B2C) da Adventure Works.

![Exemplo de um módulo de lista de imagens que exibe uma lista de texto que inclui logotipos](./media/Image_list.PNG)

A ilustração a seguir mostra um exemplo em que um módulo de lista de imagens exibe logotipos de marca em uma página do site empresa-para-empresa (B2B) da Adventure Works.

![Exemplo de um módulo de lista de imagens que exibe logotipos de marca](./media/Image_list_B2B.PNG)

## <a name="image-list-module-properties"></a>Propriedades do módulo de lista de imagens

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Título       | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Um cabeçalho de texto para o módulo de lista de imagens. |
| Lista de imagens    | Imagens, texto e URLs | Cada item na matriz é uma imagem acompanhada por texto de parágrafo e uma URL. |

## <a name="add-an-image-list-module-to-a-new-page"></a>Adicionar um módulo de lista de imagens a uma nova página

Para adicionar um módulo de lista de imagens a uma nova página e definir as propriedades necessárias criador de sites do Commerce, siga as etapas a seguir.

1. Vá para **Modelos** e abra o modelo de marketing para a página inicial do seu site (ou crie um novo modelo de marketing).
1. No slot **Principal** da página padrão, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Lista de imagens** e depois **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Vá para **Páginas** e abra a página inicial do site (ou crie uma nova página inicial usando o modelo de marketing).
1. No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione **Lista de imagens** e depois **OK**.
1. No painel de propriedades do módulo de lista de imagens, adicione um título (por exemplo, **Nossas marcas**).
1. Adicione um item da lista de imagens e especifique uma imagem, alguns textos de parágrafo e uma URL de redirecionamento.
1. Adicione e configure módulos de lista de imagens adicionais conforme necessário.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Visão geral do tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
