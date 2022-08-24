---
title: Carregar imagens
description: Este artigo descreve como carregar imagens no construtor de sites do Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: d937e8c0e00ce28b0e4a4c2feab3ac1c8f075916
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283370"
---
# <a name="upload-images"></a>Carregar imagens

[!include [banner](includes/banner.md)]

Este artigo descreve como carregar imagens no construtor de sites do Microsoft Dynamics 365 Commerce.

A Biblioteca de Mídia do assistente para criação de sites do Commerce permite carregar imagens, individualmente ou em massa, usando pastas. Você sempre deve carregar a versão da imagem com a resolução e a qualidade mais altas, porque o componente redimensionador de imagem otimizará automaticamente a imagem em diferentes portas de exibição e seus pontos de interrupção.

### <a name="image-information-specified-during-upload"></a>Informações de imagem especificadas durante o carregamento

Ao carregar uma imagem, as informações a seguir podem ser especificadas.

- **Título, texto alt, descrição, palavras-chave**: metadados da imagem ou imagens. Título e texto alt são valores obrigatórios.
- **Selecionar categoria**:
    - **Nenhum(a)**: usado em imagem(ns) para contar histórias de comércio eletrônico.
    - **Produto, categoria, cliente, funcionário, catálogo**: usados em imagem(ns) de omnicanal do Dynamics 365 Commerce.
- **Publicar ativos após upload**: quando esta caixa de seleção está marcada, a imagem ou as imagens são publicadas imediatamente após o carregamento.

> [!NOTE]
> - Os ativos de imagem com uma categoria atribuída também são marcados automaticamente com a categoria como uma palavra-chave para ajudar na pesquisa de ativos de uma categoria específica.
> - Páginas de detalhes do produto geram de forma dinâmica o **Texto alt** usando o nome do produto, portanto, alterar o **Texto alt** para uma imagem do produto não afetará a imagem renderizada.

### <a name="naming-conventions-for-omni-channel-images"></a>Convenções de nomenclatura para imagens de omnicanal 

Se você configurou a Biblioteca de Mídia como o back-end da imagem de omnicanal, poderá usar categorias de imagens para indicar a qual categoria a imagem carregada pertence. Também existe uma convenção de nomenclatura que deve ser seguida para garantir que as imagens sejam recuperadas corretamente por outros canais, como ponto de venda (PDV).

A convenção de nomenclatura padrão varia de acordo com a categoria:
- As imagens do catálogo devem ser nomeadas como "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"
- As imagens da categoria devem ser nomeadas como "**/Categories/\{CategoryName\}.png**"
- As imagens do cliente devem ser nomeadas como "**/Customers/\{CustomerNumber\}.jpg**"
- As imagens dos funcionários devem ser nomeadas como "**/Workers/\{WorkerNumber\}.jpg**"
- As imagens do produto devem ser nomeadas como "**/Products/\{ProductNumber\}\_000_001.png**"
    - 001 é a sequência da imagem e pode ser 001, 002, 003, 004 ou 005
- As imagens da grade de produto devem ser nomeadas como "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"
    - Por exemplo: 93039 \^ &nbsp;\^ 2 \^ Black \^\_000_001.png
- As imagens de grade de produto com dimensões de configuração devem ser nomeadas "**/Products/\{ProductNumber\} \^ \{Configuration\}\_000_001.png**"
    - Por exemplo: 93039 \^ LB8017_000_001.png

> [!NOTE]
> Para imagens de grade de produto, se o valor de dimensão estiver vazio, deve haver dois espaços em branco entre os acentos no nome do arquivo.

Os exemplos acima usam a configuração padrão. O caractere separador e as dimensões são configuráveis e o nome exato necessário pode variar entre as implantações. Um método para identificar a convenção de nomenclatura exata necessária é usar o console do desenvolvedor do navegador para inspecionar as solicitações de imagem de grade do produto ao alterar as dimensões do produto na página detalhes do produto da vitrine (PDP).

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
