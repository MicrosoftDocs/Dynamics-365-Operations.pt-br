---
title: Adicionar um favicon
description: Este tópico explica como adicionar um favicon ao seu site.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 18e12cbe46650fcf024a56b6de9a8cb2903d2bf8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914555"
---
# <a name="add-a-favicon"></a>Adicionar um favicon

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico explica como adicionar um favicon ao seu site.

## <a name="overview"></a>Visão geral

Um favicon é um pequeno arquivo gráfico que é mostrado em uma guia do navegador da Web, na barra de endereços, no histórico de navegação e em indicadores ou favoritos, entre outros lugares. Recomendamos que você adicione um favicon ao seu site, porque ele representa e reforça sua marca e ajuda a distinguir seu site de outros sites visitados por seus clientes.

Embora você possa adicionar vários favoritos de vários tamanhos e tipos de arquivo ao seu site, este tópico mostra como adicionar um único favorito. No entanto, o mesmo processo e local são usados para adicionar mais favicons.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Carregar um favicon na coleção de ativos do seu site

Para carregar um favicon na coleção de ativos do seu site, siga as etapas a seguir.

1. Vá para **Ativos \> Carregar \> Carregar ativos**.
1. Localize e selecione o favicon no seu sistema de arquivos local.
1. Insira um título e depois selecione **OK**. 
1. No painel de propriedades à direita, copie a URL pública do favicon.

> [!NOTE]
> Se você não selecionar a opção **Publicar ativos após upload**, será preciso retornar à página **Ativos** e publicar manualmente o favicon depois.

## <a name="create-the-html-for-the-favicon"></a>Criar o HTML do favicon

Para criar o HTML do favicon, use o seguinte trecho de código de HTML. No atributo **href**, substitua **"URL\_pública\_para\_seu\_favicon"** pela URL pública que você copiou anteriormente.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a>Adicione o HTML do favicon ao elemento \<head\> das suas páginas

Para adicionar um favicon ao seu site, use o mesmo procedimento usado para adicionar qualquer tipo de HTML ou script ao elemento **\<head\>** das páginas do site.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Trabalhar com arquivos de substituição CSS](css-override-files.md)

[Adicionar uma mensagem de boas-vindas](add-welcome-message.md)

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)

