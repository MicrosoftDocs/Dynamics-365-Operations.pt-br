---
title: Adicionar o código de script a páginas do site para oferecer suporte à telemetria
description: Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.
author: bicyclingfool
manager: annbe
ms.date: 03/20/2020
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
ms.openlocfilehash: 4f26ed5b6674566f579e801f4b7be63c2d0dc38d
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686805"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Adicionar o código de script a páginas do site para oferecer suporte à telemetria

[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.

## <a name="overview"></a>Visão geral

A análise da Web é uma ferramenta essencial quando você deseja entender como seus clientes interagem com seu site e tomar decisões que ajudarão a otimizar a experiência para obter a conversão máxima. Muitos pacotes de análise da Web estão disponíveis para ajudar você a atingir esses objetivos, como Google Analytics, Clicky, Moz Analytics e KISSMetrics. A maioria dos pacotes de análise da Web exige que você adicione o código de script do cliente no elemento **\<head\>** do HTML para todas as páginas do seu site.

> [!NOTE]
> As instruções neste tópico também se aplicam a outras funcionalidades personalizadas do cliente que o Microsoft Dynamics 365 Commerce não oferece nativamente.

## <a name="create-a-reusable-page-fragment-for-your-script-code"></a>Criar um fragmento de página reutilizável para o seu código de script

Um fragmento de página permite reutilizar o código de script interno ou externo em todas as páginas do site, independentemente do modelo usado.

### <a name="create-a-reusable-page-fragment-for-your-inline-script-code"></a>Criar um fragmento de página reutilizável para o seu código de script embutido

Para criar um fragmento de página reutilizável para o código de script embutido no site Builder, siga estas etapas.

1. Vá para **Fragmentos** e selecione **Novo**.
1. Na caixa de diálogo **Novo fragmento de página**, selecione **Script embutido**.
1. Em **Nome do fragmento de página**, digite um nome para o fragmento e, em seguida, selecione **OK**.
1. No fragmento de página criado, selecione o módulo de **Script embutido padrão**.
1. No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente. Em seguida, configure outras opções conforme necessário.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar**.

### <a name="create-a-reusable-page-fragment-for-your-external-script-code"></a>Criar um fragmento de página reutilizável para o seu código de script externo

Para criar um fragmento de página reutilizável para o código de script externo no site Builder, siga estas etapas.

1. Vá para **Fragmentos** e selecione **Novo**.
1. Na caixa de diálogo **Novo fragmento de página**, selecione **Script externo**.
1. Em **Nome do fragmento de página**, digite um nome para o fragmento e, em seguida, selecione **OK**.
1. No fragmento de página criado, selecione o módulo de **Script externo padrão**.
1. No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa. Em seguida, configure outras opções conforme necessário.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar**.

## <a name="add-a-page-fragment-that-includes-script-code-to-a-template"></a>Adicionar um fragmento de página que inclua código de script a um modelo

Para adicionar um fragmento de página que inclua código de script a um modelo no site builder, siga estas etapas.

1. Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.
1. No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.
1. No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar fragmento de página**.
1. Selecione o fragmento que você criou para o seu código de script.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar**.

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a>Adicionar um script externo ou script embutido diretamente a um modelo

Se você deseja inserir um script embutido ou externo diretamente a um conjunto de páginas controlado por um único modelo, não é necessário criar um fragmento de página primeiro.

### <a name="add-an-inline-script-directly-to-a-template"></a>Adicionar um script embutido diretamente a um modelo

Para adicionar um script embutido diretamente a um modelo no site Builder, siga estas etapas.

1. Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.
1. No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.
1. No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar módulo**, selecione **Script embutido**.
1. No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente. Em seguida, configure outras opções conforme necessário.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar**.

### <a name="add-an-external-script-directly-to-a-template"></a>Adicionar um script externo diretamente a um modelo

Para adicionar um script externo diretamente a um modelo no site Builder, siga estas etapas.

1. Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.
1. No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.
1. No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar módulo**, selecione **Script externo**.
1. No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa. Em seguida, configure outras opções conforme necessário.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionais

[Adicionar um logotipo](add-logo.md)

[Selecionar um tema de site](select-site-theme.md)

[Trabalhar com arquivos de substituição CSS](css-override-files.md)

[Adicionar um favicon](add-favicon.md)

[Adicionar uma mensagem de boas-vindas](add-welcome-message.md)

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)
