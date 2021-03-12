---
title: Carregar vídeos
description: Este tópico descreve como carregar vídeos no assistente para criação de sites do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a8cabcd3528308919697a9f2ecb2a81ad5acbe31
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000916"
---
# <a name="upload-videos"></a>Carregar vídeos

[!include [banner](includes/banner.md)]

Este tópico descreve como carregar vídeos no assistente para criação de sites do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

A Biblioteca de Mídia do assistente para criação de sites do Commerce permite carregar vídeos. Você sempre deve carregar a versão de um vídeo com a taxa de bits e a resolução mais altas, porque o vídeo será convertido automaticamente para se adequar a diferentes portas de exibição e seus pontos de interrupção.

### <a name="video-information-specified-during-upload"></a>Informações de vídeo especificadas durante o carregamento

Ao carregar um vídeo, as informações a seguir podem ser especificadas.

- **Título, descrição, palavras-chave**: metadados do vídeo.
- **Gerar automaticamente legendas ocultas**: especifica se as legendas ocultas devem ser geradas automaticamente para o vídeo.
- **Legenda Oculta**: especifica as legendas ocultas a serem usadas.
- **Áudio Regular**: especifica a trilha de áudio comum a ser usada.
- **Miniatura**: especifica a miniatura do vídeo. Se não especificada, será gerada automaticamente.
- **Áudio Descritivo**: especifica a trilha de áudio descritiva a ser usada.

## <a name="upload-a-video"></a>Carregar um vídeo

Para carregar um vídeo no assistente para criação de sites, siga as etapas a seguir.

1. No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.
1. Na barra de comandos, selecione **Carregar \> Carregar Itens de Mídia**.
1. Na janela do explorador de arquivos, explore e selecione um ou mais arquivos de vídeo a serem carregados e, em seguida, selecione **Abrir**.
1. Na caixa de diálogo **Carregar Item de Mídia**, digite o título e o texto alt necessários.
1. Digite uma descrição opcional e palavras-chave e selecione uma categoria, se desejar. 
1. Se você deseja publicar as imagens imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**
1. Selecione **OK**.

Se você estiver carregando vários tipos de ativos simultaneamente (por exemplo, imagens e vídeos), na caixa de diálogo **Carregar Item de Mídia**, você poderá especificar apenas palavras-chave, se os arquivos devem ser publicados imediatamente após o carregamento e se legendas ocultas devem ser geradas automaticamente para arquivos de vídeo. Todos os ativos compartilharão as mesmas palavras-chave.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do gerenciamento de ativos digitais](dam-overview.md)

[Carregar imagens](dam-upload-images.md)

[Carregue arquivos](dam-upload-files.md)

[Cortar imagens](dam-crop-images.md)

[Personalizar pontos focais da imagem](dam-custom-focal-point.md)

[Carregar e atender arquivos estáticos](upload-serve-static-files.md)
