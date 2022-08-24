---
title: Módulo de imagem ativa
description: Este artigo abrange os módulos de imagem ativa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: fdcd54adc98c7bc52ab6ff1ef7d5d03616aadfc3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267608"
---
# <a name="active-image-module"></a>Módulo de imagem ativa

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de imagem ativa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Um módulo de imagem ativa pode ser usado para incorporar marcas de produto em uma imagem. Os usuários do site de comércio eletrônico podem passar o mouse sobre as marcas para visualizar os produtos que são mostrados na imagem. As versão preliminares são mostradas em janelas pop-up. Ao selecionar uma janela pop-up de versão preliminar, os usuários podem ir diretamente para a página de detalhes do produto (PDP) do produto correspondente.

As marcas são definidas usando coordenadas X e Y na imagem. Cada ponto marcado deve ser configurado com o ID do produto que é mostrado na imagem.

A ilustração a seguir mostra um exemplo de uma janela pop-up de versão preliminar em uma imagem hero na página inicial da Adventure Works.

![Exemplo de uma janela pop-up de versão preliminar em um módulo de imagem ativa](./media/Active_image.PNG)

> [!IMPORTANT]
> - O módulo de imagem ativa está disponível a partir da versão 10.0.20 do Dynamics 365 Commerce.
> - O módulo de imagem ativa é apresentado no tema Adventure Works.

## <a name="active-image-module-properties"></a>Propriedades do Módulo de imagem ativa

| Nome da propriedade      | Valores | Descrição |
|--------------------|--------|-------------|
| Imagem              | Arquivo de imagem | Uma imagem pode ser usada para mostrar um ou mais produtos. A imagem pode ser carregada na Biblioteca de mídia do criador de sites do Commerce ou uma imagem existente pode ser usada. |
| Largura              | Número de pixels | Esta propriedade define a largura da imagem. As coordenadas ativas são calculadas com base na largura da imagem.|
| Coordenadas ativas | Coordenadas X e Y e um número de ID do produto | Cada matriz de imagem ativa consiste em coordenadas X e Y e um número de ID de produto.|
| Título            | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Por padrão, a tag de cabeçalho **H2** é usada, mas a tag do cabeçalho pode ser alterada para atender aos requisitos de acessibilidade. |
| Parágrafo          | Texto de parágrafo | O módulo oferece suporte a texto de parágrafo em formato rich text. Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks. Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo. |
| Vincular               | Texto do link, URL do link, rótulo ARIA (Accessible Rich Internet Applications) e seletor **Abrir link em uma nova guia** | O módulo oferece suporte a um ou mais links de "chamada à ação". Se um link for adicionado, será necessário o texto do link, uma URL e uma etiqueta ARIA. As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade. Os links podem ser configurados para serem abertos em uma nova guia. |
| Subtexto           | Título, texto e links | É possível adicionar um contexto adicional para a imagem, como um autor ou nome de designer, ou links para Blogs pessoais.|
| Tema de texto         | **Claro** ou **Escuro** | Esta propriedade permite que um usuário defina o texto como claro ou escuro, com base na imagem de plano de fundo. Ele está disponível como uma extensão de tema no tema Adventure Works. |

## <a name="add-an-active-image-module-to-a-new-page"></a>Adicionar um módulo de imagem ativo a uma nova página

Para adicionar um módulo de imagem ativa a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Acesse **Modelos** e abra o modelo de marketing para a página inicial do seu site (ou crie um novo modelo de marketing).
1. No slot **Principal** da página padrão, selecione as reticências (**...**) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Imagem ativa** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e abra a página inicial do site (ou crie uma nova página inicial usando o modelo de marketing).
1. No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Imagem ativa** e, depois, **OK**.
1. No painel de propriedades do módulo de imagem ativa, adicione uma imagem e defina a largura da tela como o tamanho da imagem.
1. Defina as coordenadas X e Y e adicione o número de ID do produto apropriado.
1. Adicione e configure módulos de imagem ativa adicionais conforme necessário.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Visão geral do tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
