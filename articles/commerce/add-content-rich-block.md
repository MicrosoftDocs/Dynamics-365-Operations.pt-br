---
title: Módulo de bloco de texto
description: Este tópico abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025588"
---
# <a name="text-block-module"></a>Módulo de bloco de texto


[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de bloco de texto é um módulo usado para adicionar conteúdo textual. Esse conteúdo pode ser informativo ou promocional.

Os módulos de bloco de texto são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página. São módulos autônomos que não dependem do contexto da página ou de outros módulos.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Exemplos de módulos de bloco de texto no comércio eletrônico

Os módulos de bloco de texto podem ser usados das seguintes formas:

* Para exibir os recursos do produto em uma página de detalhes do produto.
* Para fins informativos em qualquer página. Por exemplo, eles podem explicar os benefícios dos programas de fidelidade, descrever as políticas de remessa e devolução, responder a perguntas frequentes ou fornecer conteúdo "sobre nós".
* Para adicionar mensagens personalizadas em uma página de detalhes do produto. (por exemplo, "Frete grátis para pedidos acima de US$ 50").
* Para avisos de isenção de responsabilidade e detalhes de contato nas páginas de detalhes do produto, páginas de carrinho, páginas de finalização de compra e outras páginas (por exemplo, "Remessas e devoluções estão sujeitas às políticas da loja").

## <a name="text-block-module-properties"></a>Propriedades do módulo de bloco de texto

| Nome da propriedade     | Value                                            | Descrição |
|-------------------|--------------------------------------------------|-------------|
| Rich text         | Rich text                                        | Texto do parágrafo. Há suporte para alguns recursos básicos de rich text, como negrito, sublinhado e itálico. |
| Nome da classe personalizada | Um nome de classe de folhas de estilo em cascata (CSS)        | O nome de uma classe CSS personalizada que um desenvolvedor fornece para formatar esse módulo. O nome da classe deve ser definido no pacote de tema. |
| Tamanho da fonte         | **Pequeno**, **Médio**, **Grande** ou **Extra-grande** | O tamanho da fonte do conteúdo. |

## <a name="add-a-text-block-module-to-a-page"></a>Adicionar um módulo de bloco de texto a uma página

Para adicionar um módulo de bloco de texto a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Criar um modelo da página chamado **Modelo de conteúdo**. 
1. No slot **Corpo**, adicione um módulo **Página padrão**.
1. Termine de editar o modelo e publique-o.
1. Use o modelo de conteúdo que criou para criar uma página nomeada **Página do conteúdo**.
1. No slot **Principal** da nova página, adicione um módulo de contêiner.
1. No painel de propriedades do módulo de contêiner, defina a propriedade **Largura** como **Preencher contêiner**.
1. Adicione um módulo de bloco de texto ao módulo de contêiner. 
1. No painel de propriedades do módulo de bloco de texto, adicione um texto ao campo **Texto rico**.
1. Termine de editar a página e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de faixa promocional](add-alert.md)

[Módulo do carrossel](add-carousel.md)

[Módulo de bloco de conteúdo](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)

