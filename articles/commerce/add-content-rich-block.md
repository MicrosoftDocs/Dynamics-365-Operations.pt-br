---
title: Módulo de bloco de texto
description: Este artigo abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 9e422c203d719b2e46620ce50b9d029e7ebd8d4c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270473"
---
# <a name="text-block-module"></a>Módulo de bloco de texto

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Um módulo de bloco de texto é um módulo usado para adicionar conteúdo textual. Esse conteúdo pode ser informativo ou promocional.

Os módulos de bloco de texto são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página. São módulos autônomos que não dependem do contexto da página ou de outros módulos.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Exemplos de módulos de bloco de texto no comércio eletrônico

Os módulos de bloco de texto podem ser usados das seguintes formas:

* Para exibir os recursos do produto em uma página de detalhes do produto.
* Para fins informativos em qualquer página. Por exemplo, eles podem explicar os benefícios dos programas de fidelidade, descrever as políticas de remessa e devolução, responder a perguntas frequentes ou fornecer conteúdo "sobre nós".
* Para adicionar mensagens personalizadas em uma página de detalhes do produto. (por exemplo, "Frete grátis para pedidos acima de US$ 50").
* Para avisos de isenção de responsabilidade e detalhes de contato nas páginas de detalhes do produto, páginas de carrinho, páginas de finalização de compra e outras páginas (por exemplo, "Remessas e devoluções estão sujeitas às políticas da loja").

A imagem a seguir mostra um exemplo de um módulo de bloco de texto que é usado em uma home page.

![Exemplo de um módulo de bloco de texto.](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a>Propriedades do módulo de bloco de texto

| Nome da propriedade     | Alíquota                                            | Descrição |
|-------------------|--------------------------------------------------|-------------|
| Rich text         | Rich text                                        | Texto do parágrafo. Há suporte para alguns recursos básicos de rich text, como negrito, sublinhado e itálico. |
| Nome da classe personalizada | Um nome de classe de folhas de estilo em cascata (CSS)        | O nome de uma classe CSS personalizada que um desenvolvedor fornece para formatar esse módulo. O nome da classe deve ser definido no pacote de tema. |
| Tamanho da fonte         | **Pequeno**, **Médio**, **Grande** ou **Extra-grande** | O tamanho da fonte do conteúdo. |

## <a name="add-a-text-block-module-to-a-page"></a>Adicionar um módulo de bloco de texto a uma página

Para adicionar um módulo de bloco de texto a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Acesse **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo modelo**, em **Nome do modelo**, insira um **Modelo de conteúdo**.
1. No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Página padrão** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma nova página**, em **Nome da página**, insira uma **Página de conteúdo** e, depois, selecione **Avançar**.
1. Em **Escolha um modelo**, selecione **Modelo de conteúdo** e, depois, **Avançar**.
1. Em **Escolher um layout**, selecione um layout de página (por exemplo, **Layout flexível**) e selecione **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**. 
1. No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No painel de propriedades do módulo de contêiner, defina a propriedade **Largura** como **Preencher contêiner**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Bloco de texto** e, depois, **OK**. 
1. No painel de propriedades do módulo de bloco de texto, adicione um texto ao campo **Texto rico**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de banner de promoção](add-alert.md)

[Módulo do carrossel](add-carousel.md)

[Módulo de bloco de conteúdo](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
