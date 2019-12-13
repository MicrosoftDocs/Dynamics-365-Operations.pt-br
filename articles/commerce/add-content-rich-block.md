---
title: Módulo de bloco de conteúdo sofisticado
description: Este tópico abrange os módulos de bloco de conteúdo sofisticado e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785412"
---
# <a name="content-rich-block-module"></a>Módulo de bloco de conteúdo sofisticado

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de bloco de conteúdo sofisticado e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de bloco de conteúdo sofisticado é um contêiner especial dentro do qual um ou mais itens de bloco de conteúdo sofisticado podem ser colocados. Os módulos de bloco de conteúdo sofisticado são usados para o conteúdo de texto em uma página. Esse conteúdo pode ser informativo ou promocional.

Os módulos de bloco de conteúdo sofisticado são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página. São módulos autônomos que não dependem do contexto da página ou de outros módulos.

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a>Exemplos de módulos de bloco de conteúdo sofisticado no comércio eletrônico

Os módulos de bloco de conteúdo sofisticado podem ser usados das seguintes formas:

* Para exibir os recursos do produto em uma página de detalhes do produto.
* Para fins informativos em qualquer página. Por exemplo, eles podem explicar os benefícios dos programas de fidelidade, descrever as políticas de remessa e devolução, responder a perguntas frequentes ou fornecer conteúdo "sobre nós".
* Para adicionar mensagens personalizadas em uma página de detalhes do produto. (por exemplo, "Frete grátis para pedidos acima de US$ 50").
* Para avisos de isenção de responsabilidade e detalhes de contato nas páginas de detalhes do produto, páginas de carrinho, páginas de finalização de compra e outras páginas (por exemplo, "Remessas e devoluções estão sujeitas às políticas da loja").

## <a name="content-rich-block-module-properties"></a>Propriedades do módulo de bloco de conteúdo sofisticado

| Nome da propriedade     | Alíquota                                 | Propriedade |
|-------------------|---------------------------------------|----------|
| Número de colunas | Um número de **1** a **4**     | O número de colunas no bloco de conteúdo sofisticado. Pode haver até quatro colunas. |
| Largura             | **Preencher contêiner** ou **Preencher tela** | Se o valor estiver definido como **Preencher contêiner**, os itens dentro do contêiner serão restritos à largura do contêiner. Se o valor estiver definido como **Preencher tela**, os itens não serão restritos à largura do contêiner, mas poderão entrar no modo de tela cheia. É possível alterar o valor para obter o layout desejado. |

## <a name="content-rich-block-item-module-properties"></a>Propriedades do módulo do item de bloco de conteúdo sofisticado

| Nome da propriedade | Alíquota          | Descrição |
|---------------|----------------|-------------|
| Parágrafo     | Texto de parágrafo | O texto que acompanha cada item de bloco de conteúdo sofisticado. Há suporte para alguns recursos básicos de rich text, como negrito, sublinhado e itálico. |

## <a name="add-a-content-rich-block-module-to-a-page"></a>Adicionar um módulo de bloco de conteúdo sofisticado a uma página

Para adicionar um módulo de bloco de conteúdo sofisticado a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Criar um modelo da página chamado **Modelo de conteúdo**.
1. No slot **Principal** da página padrão, adicione um módulo de bloco de conteúdo sofisticado.
1. Faça check-in do modelo e publique-o.
1. Use o modelo de conteúdo que criou para criar uma página nomeada **Página do conteúdo**.
1. No slot **Principal** da nova página, adicione um módulo de bloco de conteúdo sofisticado.
1. Nas propriedades do módulo de bloco de conteúdo sofisticado, defina o número de colunas como **2**.
1. No módulo de bloco de conteúdo sofisticado, selecione **Adicionar um módulo** e adicione um item de bloco de conteúdo sofisticado (por exemplo, **item1**).
1. No novo item de bloco de conteúdo sofisticado, adicione o texto do parágrafo.
1. No módulo de bloco de conteúdo sofisticado, selecione **Adicionar um módulo** e adicione um item de bloco de conteúdo sofisticado (por exemplo, **item2**).
1. No novo item de bloco de conteúdo sofisticado, adicione o texto do parágrafo.
1. Salve a página e visualize as alterações. Você verá dois blocos de rich text em uma exibição de duas colunas.
1. Insira a página e publique-a.

> [!NOTE]
> Se você adicionar um terceiro item de bloco de conteúdo sofisticado, ele será empilhado abaixo dos dois itens que você adicionou anteriormente. Alterando o número de colunas e itens no contêiner, você poderá obter layouts diferentes para o conteúdo textual.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de carrossel](add-carousel.md)

[Módulo de posicionamento de conteúdo](add-content-placement-modules.md)

[Módulo de recurso](add-feature-module.md)

[Módulo de hero](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)

