---
title: Módulo de posicionamento de conteúdo
description: Este tópico aborda os módulos de posicionamento de conteúdo e item de posicionamento de conteúdo e descreve como adicioná-los às páginas do site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1b64e930628c969334ff6e643ba23b77445e6e4c
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785288"
---
# <a name="content-placement-module"></a>Módulo de posicionamento de conteúdo

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico aborda os módulos de posicionamento de conteúdo e item de posicionamento de conteúdo e descreve como adicioná-los às páginas do site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de posicionamento de conteúdo é um contêiner especial no qual outros módulos podem ser colocados em um layout específico. Os módulos de posicionamento de conteúdo são compatíveis com os seguintes tipos de módulos como módulos filhos: item de posicionamento de conteúdo, item de boas-vindas da conta, item de ordem da conta, item da lista de desejos da conta e item de perfil da conta.

Os módulos de posicionamento de conteúdo derivam dados dos módulos filhos com os quais são compatíveis. Portanto, os módulos de posicionamento de conteúdo podem ser usados de várias maneiras, dependendo dos módulos adicionados a ele.

Os módulos de item de posicionamento de conteúdo usam imagens e texto para exibir promoções, políticas e recursos do produto. Por exemplo, um módulo de item de posicionamento de conteúdo pode ser usado em uma home page para mostrar políticas de loja ou informações de remessa. Os módulos de item de posicionamento de conteúdo são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página. Contudo, eles podem ser usados apenas dentro de um módulo de posicionamento de conteúdo.

## <a name="examples-of-content-placement-modules-in-e-commerce"></a>Exemplos de módulos de posicionamento de conteúdo no comércio eletrônico

* Os módulos de posicionamento de conteúdo que contêm módulos de item de posicionamento de conteúdo podem ser usados em uma home page ou em páginas de marketing para mostrar recursos do produto, promoções, políticas de loja, informações de remessa e outras informações por meio de imagens e texto.
* Os módulos de posicionamento de conteúdo que contêm módulos de item de posicionamento de conteúdo podem ser usados nas páginas de detalhes do produto para mostrar os recursos do produto.
* Os módulos de posicionamento de conteúdo que contêm itens de boas-vindas da conta ou módulos de itens do ordens da conta podem ser usados nas páginas de gerenciamento de contas.

## <a name="content-placement-module-properties"></a>Propriedades do módulo de posicionamento de conteúdo

| Nome da propriedade | Alíquota | Descrição |
|---------------|-------|-------------|
| Largura         | **Ajustar contêiner** ou **Preencher tela** | Se o valor estiver definido como **Ajustar contêiner**, os itens dentro do módulo de posicionamento de conteúdo serão restritos à largura do módulo de posicionamento de conteúdo. Se o valor estiver definido como **Preencher tela**, os itens não se restringirão à largura do módulo de posicionamento de conteúdo, mas poderão entrar no modo de tela cheia. |

## <a name="content-placement-item-module-properties"></a>Propriedades do módulo de item de posicionamento de conteúdo

| Nome da propriedade | Alíquota | Descrição |
|---------------|-------|-------------|
| Cabeçalho       | Texto do cabeçalho e tags do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Todo módulo de item de posicionamento de conteúdo pode ter um cabeçalho. A propriedade **Título** é compatível com tags do cabeçalho. Por padrão, a tag de cabeçalho **H2** é usada, mas a tag do cabeçalho pode ser alterada para atender aos requisitos de acessibilidade. |
| Parágrafo     | Texto de parágrafo | Os módulos de item de posicionamento de conteúdo é compatível com texto de parágrafo em formato rich text. Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks. Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo. |
| Imagem         | Arquivo de imagem | Uma imagem pode ser associada ao texto. |
| Vincular          | URL do link e texto do link | Um link pode ser adicionado ao texto para redirecionar os usuários a uma página específica. |
| Tamanho do bloco     | Um número de **1** a **12** | Para cada item de canal de conteúdo, essa propriedade define o número de slots que o item deve preencher no módulo de posicionamento de conteúdo. O tamanho máximo do módulo de posicionamento de conteúdo é de 12 slots. Se o tamanho total do bloco dos primeiros itens *n* no módulo de posicionamento de conteúdo exceder 12 slots, os itens serão agrupados na próxima linha. |

## <a name="add-a-content-placement-module-that-contains-a-content-placement-item-module-to-a-page"></a>Adicionar um módulo de posicionamento de conteúdo que contém um módulo de item de posicionamento de conteúdo a uma página

Para adicionar um módulo de posicionamento de conteúdo que contém um módulo de item de posicionamento de conteúdo a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Crie um modelo chamado **modelo de posicionamento de conteúdo**.
1. No slot **Principal** da página padrão, adicione um módulo de posicionamento de conteúdo.
1. No módulo de posicionamento de conteúdo, adicione um módulo de item de posicionamento de conteúdo.
1. Faça check-in do modelo e publique-o.
1. Use o modelo de posicionamento de conteúdo que você acabou de criar para criar uma página chamada **Página de posicionamento de conteúdo**.
1. No slot **Principal** da nova página, adicione um módulo de posicionamento de conteúdo.
1. No módulo de posicionamento de conteúdo, adicione um módulo de item de posicionamento de conteúdo.
1. No painel de propriedades do módulo de item de posicionamento de conteúdo, selecione uma imagem, adicione um título, adicione um parágrafo, adicione um link, defina a URL do link e defina o tamanho do bloco como **6**.
1. Repita as etapas 7 e 8 para adicionar outro módulo de item de posicionamento de conteúdo que tenha o mesmo tamanho de bloco.
1. Salve e exiba a página. Você deve ver dois itens de posicionamento de conteúdo que aparecem lado a lado. Você pode ajustar a propriedade **Tamanho do bloco** de cada módulo de item de posicionamento de conteúdo ou adicionar mais módulos para obter o layout desejado.
1. Insira a página e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de carrossel](add-carousel.md)

[Módulo de bloco de conteúdo sofisticado](add-content-rich-block.md)

[Módulo de recurso](add-feature-module.md)

[Módulo de hero](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)
