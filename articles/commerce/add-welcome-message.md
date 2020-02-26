---
title: Adicionar uma mensagem de boas-vindas
description: Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site Microsoft Dynamics 365 Commerce.
author: psimolin
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ca10b01268b5dcd4c6fe448d90cd0ebd65a2673b
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001245"
---
# <a name="add-a-welcome-message"></a>Adicionar uma mensagem de boas-vindas


[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Uma mensagem de boas-vindas em seu site de comércio online pode informar os visitantes sobre ofertas em andamento, atualizações do site ou disponibilidade de coleções sazonais. A mensagem de boas-vindas é configurada usando o módulo de alerta.

O módulo de alerta deverá ser adicionado ao slot **Mensagens de erro/informações** do fragmento do cabeçalho. O módulo de alerta permite que você especifique o texto exibido, a cor do texto e o alinhamento. Também permite especificar se os visitantes do site podem ignorar a mensagem.

Quando uma mensagem de boas-vindas é adicionada a um fragmento de cabeçalho compartilhado, ela será exibida em cada página que usa o modelo onde o fragmento de cabeçalho compartilhado é usado.

Para adicionar uma mensagem de boas-vindas ao site, siga essas etapas.

1. No Dynamics 365 Commerce, vá para o site.
1. Selecionar **Fragmentos**.
1. Selecione o fragmento do cabeçalho ao qual adicionar a mensagem.
1. Na árvore em destaque, abra **Mensagens de erro/informações**.
1. Selecione o módulo de alerta.

    Se um módulo de alerta não existir ainda, selecione o botão de reticências (**...**) ao lado de **Mensagens de erro/ informações** e depois selecione, **Adicionar o módulo**. Selecione o módulo de alerta e, em seguida, selecione **OK**.

1. No painel de propriedade à direita, na guia **Dados**, selecione **Adicionar fonte de dados** e **Conteúdo**.
1. No campo **Texto da entrada**, insira o texto da mensagem de boas-vindas.
1. Salve o fragmento do cabeçalho, insira-o e publique-o.

A mensagem de boas-vindas aparecerá na parte superior de cada página do site usando o fragmento do cabeçalho selecionado.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Trabalhar com arquivos de substituição CSS](css-override-files.md)

[Adicionar um favicon](add-favicon.md)

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)

