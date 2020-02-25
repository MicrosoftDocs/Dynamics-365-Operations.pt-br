---
title: Adicionar um logotipo
description: Este tópico descreve como adicionar um logotipo ao seu site no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5fc0673dcdcc8b761089be2c2d201c8488128865
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025668"
---
# <a name="add-a-logo"></a>Adicionar um logotipo


[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar um logotipo ao seu site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Quando você cria seu site, uma das primeiras coisas que você provavelmente fará é adicionar o logotipo da empresa ou da marca ao cabeçalho do site. O kit de início do Dynamics 365 Commerce online fornece um módulo que facilita essa tarefa.

Você pode adicionar um logotipo diretamente a um modelo, layout ou página. Dessa forma, você pode alterar facilmente o logotipo que aparece em páginas ou grupos de páginas específicos. No entanto, este tópico cobre o cenário mais frequente, no qual você adiciona seu logotipo a um fragmento de cabeçalho que pode ser reutilizado em todas as páginas do seu site.

## <a name="prerequisites"></a>Pré-requisitos

Para poder adicionar um logotipo a todas as páginas do site, você deve executar estas tarefas.

1. Carregue o logotipo na Biblioteca de Mídia.
1. Criar um fragmento de cabeçalho. Para obter mais informações sobre como criar e usar fragmentos, consulte [Trabalhar com fragmentos](work-with-fragments.md).
1. Inclua o fragmento de cabeçalho no modelo usado pelas páginas do site para as opções de módulo e layout. Para obter mais informações sobre como modelos, consulte [Trabalhar com modelos](work-with-templates.md).

## <a name="add-a-logo-to-a-header-fragment"></a>Adicionar um logotipo a um fragmento de cabeçalho

Para adicionar um logotipo ao fragmento do cabeçalho ao site, siga estas etapas.

1. No painel de navegação à esquerda, selecione **Fragmentos de Página**.
1. Selecione o fragmento de cabeçalho que você criou antes e selecione **Editar**.
1. Expanda o módulo de cabeçalho.
1. No painel de propriedades do módulo de cabeçalho, forneça uma imagem e um link para o logotipo. 
1. Salve o fragmento de cabeçalho, termine de editá-lo e publique-o.

Depois de publicar o fragmento de cabeçalho atualizado, todas as páginas do site que usam o modelo que contém o fragmento do cabeçalho mostrarão seu logotipo.

## <a name="additional-resources"></a>Recursos adicionais

[Selecionar um tema de site](select-site-theme.md)

[Trabalhar com arquivos de substituição CSS](css-override-files.md)

[Adicionar um favicon](add-favicon.md)

[Adicionar uma mensagem de boas-vindas](add-welcome-message.md)

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)

