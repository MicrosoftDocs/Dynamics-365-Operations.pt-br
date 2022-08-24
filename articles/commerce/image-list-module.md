---
title: Módulo de lista de imagens
description: Este artigo abrange os módulos de lista de imagens e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: e89624a98d3cbdd861391e994386ae57d2c38aa0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269826"
---
# <a name="image-list-module"></a>Módulo de lista de imagens

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de lista de imagens e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

O módulo lista de imagens pode ser usado para adicionar facilmente um conjunto (matriz) de imagens a páginas do site. Cada imagem da matriz pode ser configurada com texto de parágrafo e URLs de link. O módulo de lista de imagens é mais adequado para exibir logotipos de marcas ou uma lista que inclua logotipos.

> [!IMPORTANT]
> - O módulo de lista de imagens está disponível na biblioteca de módulos do Commerce a partir da versão 10.0.20 do Dynamics 365 Commerce.
> - O módulo de lista de imagens é apresentado no tema Adventure Works.

A ilustração a seguir mostra um exemplo em que um módulo de lista de imagens exibe uma lista de texto que inclui logotipos em uma página do site empresa-para-consumidor (B2C) da Adventure Works.

![Exemplo de um módulo de lista de imagens que exibe uma lista de texto que inclui logotipos](./media/Image_list.PNG)

A ilustração a seguir mostra um exemplo em que um módulo de lista de imagens exibe logotipos de marca em uma página do site empresa-para-empresa (B2B) da Adventure Works.

![Exemplo de um módulo de lista de imagens que exibe logotipos de marca](./media/Image_list_B2B.PNG)

## <a name="image-list-module-properties"></a>Propriedades do módulo de lista de imagens

| Nome da propriedade | Valores | Descrição |
|---------------|--------|-------------|
| Título       | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Um cabeçalho de texto para o módulo de lista de imagens. |
| Lista de imagens    | Imagens, texto e URLs | Cada item na matriz é uma imagem acompanhada por texto de parágrafo e uma URL. |

## <a name="add-an-image-list-module-to-a-new-page"></a>Adicionar um módulo de lista de imagens a uma nova página

Para adicionar um módulo de lista de imagens a uma nova página e definir as propriedades necessárias criador de sites do Commerce, siga as etapas a seguir.

1. Acesse **Modelos** e abra o modelo de marketing para a página inicial do seu site (ou crie um novo modelo de marketing).
1. No slot **Principal** da página padrão, selecione as reticências (**...**) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Lista de imagens** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e abra a página inicial do site (ou crie uma nova página inicial usando o modelo de marketing).
1. No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione a **Lista de imagens** e, depois, **OK**.
1. No painel de propriedades do módulo de lista de imagens, adicione um título (por exemplo, **Nossas marcas**).
1. Adicione um item da lista de imagens e especifique uma imagem, alguns textos de parágrafo e uma URL de redirecionamento.
1. Adicione e configure módulos de lista de imagens adicionais conforme necessário.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Visão geral do tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
