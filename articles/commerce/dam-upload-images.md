---
title: Carregar imagens
description: Este tópico descreve como carregar imagens no assistente para criação de sites do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f562d3376fde6a24e6a1e1a3f7f4192cf290ae90
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594275"
---
# <a name="upload-images"></a>Carregar imagens

[!include [banner](includes/banner.md)]

Este tópico descreve como carregar imagens no assistente para criação de sites do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

A Biblioteca de Mídia do assistente para criação de sites do Commerce permite carregar imagens, individualmente ou em massa, usando pastas. Você sempre deve carregar a versão da imagem com a resolução e a qualidade mais altas, porque o componente redimensionador de imagem otimizará automaticamente a imagem em diferentes portas de exibição e seus pontos de interrupção.

### <a name="image-information-specified-during-upload"></a>Informações de imagem especificadas durante o carregamento

Ao carregar uma imagem, as informações a seguir podem ser especificadas.

- **Título, texto alt, descrição, palavras-chave**: metadados da imagem ou imagens. Título e texto alt são valores obrigatórios.
- **Selecionar categoria**:
    - **Nenhum(a)**: usado em imagem(ns) para contar histórias de comércio eletrônico.
    - **Produto, categoria, cliente, funcionário, catálogo**: usados em imagem(ns) de omnicanal do Dynamics 365 Commerce.
- **Publicar ativos após upload**: quando esta caixa de seleção está marcada, a imagem ou as imagens são publicadas imediatamente após o carregamento.

> [!NOTE]
> Os ativos de imagem com uma categoria atribuída também são marcados automaticamente com a categoria como uma palavra-chave para ajudar na pesquisa de ativos de uma categoria específica.

### <a name="naming-conventions-for-omni-channel-images"></a>Convenções de nomenclatura para imagens de omnicanal 

Se você configurou a Biblioteca de Mídia como o back-end da imagem de omnicanal, poderá usar categorias de imagens para indicar a qual categoria a imagem carregada pertence. Também existe uma convenção de nomenclatura que deve ser seguida para garantir que as imagens sejam recuperadas corretamente por outros canais, como ponto de venda (PDV).

A convenção de nomenclatura padrão varia de acordo com a categoria:
- As imagens do catálogo devem ser nomeadas como "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"
- As imagens da categoria devem ser nomeadas como "**/Categories/\{CategoryName\}.png**"
- As imagens do cliente devem ser nomeadas como "**/Customers/\{CustomerNumber\}.jpg**"
- As imagens dos funcionários devem ser nomeadas como "**/Workers/\{WorkerNumber\}.jpg**"
- As imagens do produto devem ser nomeadas como "**/Products/\{ProductNumber\}_000_001.png**"
    - 001 é a sequência da imagem e pode ser 001, 002, 003, 004 ou 005
- As imagens da grade de produto devem ser nomeadas como "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"

## <a name="upload-an-image"></a>Carregar uma imagem

Para carregar uma imagem no assistente para criação de sites, siga as etapas a seguir.

1. No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.
1. Na barra de comandos, selecione **Carregar \> Carregar Itens de Mídia**.
1. Na janela do explorador de arquivos, explore e selecione um ou mais arquivos de imagem a serem carregados e, em seguida, selecione **Abrir**.
1. Na caixa de diálogo **Carregar Item de Mídia**, digite o título e o texto alt necessários.
1. Digite uma descrição opcional e palavras-chave e selecione uma categoria, se desejar. 
1. Se você deseja publicar as imagens imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**.
1. Selecione **OK**.

## <a name="upload-a-folder-of-images"></a>Carregar uma pasta de imagens

Para carregar uma pasta de imagens em massa no assistente para criação de sites, siga as etapas a seguir.

1. No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.
1. Na barra de comandos, selecione **Carregar \> Carregar Pasta**.
1. Na janela do explorador de arquivos, explore e selecione uma pasta a ser carregada e, em seguida, selecione **Abrir**.
1. Na caixa de diálogo **Carregar Itens de Mídia**, insira palavras-chave opcionais e selecione uma categoria, se desejar. 
1. Se você deseja publicar as imagens na pasta imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**.
1. Selecione **OK**.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do gerenciamento de ativos digitais](dam-overview.md)

[Carregar vídeos](dam-upload-video.md)

[Carregue arquivos](dam-upload-files.md)

[Cortar imagens](dam-crop-images.md)

[Personalizar pontos focais da imagem](dam-custom-focal-point.md)

[Carregar e atender arquivos estáticos](upload-serve-static-files.md)
