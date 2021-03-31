---
title: Adicionar uma mensagem de boas-vindas
description: Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d17ad7cfd6f11e84fdd1c8ebccca6f786b83c62d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209146"
---
# <a name="add-a-welcome-message"></a>Adicionar uma mensagem de boas-vindas


[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar uma mensagem de boas-vindas ao seu site do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Uma mensagem de boas-vindas em seu site de comércio online pode informar os visitantes sobre ofertas em andamento, atualizações do site ou disponibilidade de coleções sazonais. A mensagem de boas-vindas é configurada usando o módulo de alerta.

O módulo de alerta deverá ser adicionado ao slot **Mensagens de erro/informações** do fragmento do cabeçalho. O módulo de alerta permite que você especifique o texto exibido, a cor do texto e o alinhamento. Também permite especificar se os visitantes do site podem ignorar a mensagem.

Quando uma mensagem de boas-vindas é adicionada a um fragmento de cabeçalho compartilhado, ela será exibida em cada página que usa o modelo onde o fragmento de cabeçalho compartilhado é usado.

Para adicionar uma mensagem de boas-vindas ao site, siga essas etapas.

1. No construtor de sites do Commerce, navegue até o seu site.
1. Selecionar **Fragmentos**.
1. Selecione o fragmento do cabeçalho ao qual adicionar a mensagem.
1. Na árvore em destaque, abra **Mensagens de erro/informações**.
1. Selecione o módulo de alerta e, em seguida, selecione **OK**. Se um módulo de alerta não existir ainda, primeiro selecione o botão de reticências (**...**) ao lado de **Mensagens de erro/ informações** e depois selecione, **Adicionar o módulo**.
1. No painel de propriedade à direita, na guia **Dados**, selecione **Adicionar fonte de dados** e **Conteúdo**.
1. No campo **Texto da entrada**, insira o texto da mensagem de boas-vindas.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento do cabeçalho e depois selecione **Publicar** para publicá-lo. 

A mensagem de boas-vindas aparecerá na parte superior de cada página do site usando o fragmento do cabeçalho selecionado.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Trabalhar com arquivos de substituição CSS](css-override-files.md)

[Adicionar um favicon](add-favicon.md)

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]