---
title: Adicionar o código de script a páginas do site para oferecer suporte à telemetria
description: Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a5f82426d87cd2e0faa0195a841899bb03f9df08
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697327"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Adicionar o código de script a páginas do site para oferecer suporte à telemetria

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.

## <a name="overview"></a>Visão geral

A análise da Web é uma ferramenta essencial quando você deseja entender como seus clientes interagem com seu site e tomar decisões que ajudarão a otimizar a experiência para obter a conversão máxima. Muitos pacotes de análise da Web estão disponíveis para ajudar você a atingir esses objetivos, como Google Analytics, Clicky, Moz Analytics e KISSMetrics. A maioria dos pacotes de análise da Web exige que você adicione o código de script do cliente no elemento **\<head\>** do HTML para todas as páginas do seu site.

> [!NOTE]
> As instruções neste tópico também se aplicam a outras funcionalidades personalizadas do cliente que o Microsoft Dynamics 365 Commerce não oferece nativamente.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Criar um fragmento reutilizável para o seu código de script

Depois de criar um fragmento para o seu código de script, ele pode ser reutilizado em todas as páginas do seu site.

1. Vá para **Fragmentos \> Novo fragmento de página**.
2. Selecione **Script externo**, insira um nome para o fragmento e selecione **OK**.
3. Na hierarquia de fragmentos, selecione o filho do módulo **injetor de script** do fragmento que você acabou de criar.
4. No painel de propriedades à direita, adicione seu script do cliente e defina outras opções de configuração conforme necessário.

## <a name="add-the-fragment-to-templates"></a>Adicionar o fragmento aos modelos

1. Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.
2. No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.
3. Selecione o botão de reticências (**...**) para o slot **Head do HTML** e depois selecione **Adicionar fragmento**.
4. Selecione o fragmento que você criou para o seu código de script.
5. Salve o modelo e faça check-in dele.

> [!NOTE]
> Depois de terminar, você deve publicar o fragmento e o modelo mestre. 

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Adicionar um favicon](add-favicon.md)

[Adicionar uma mensagem de boas-vindas](add-welcome-message.md)

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)

