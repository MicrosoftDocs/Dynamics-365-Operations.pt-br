---
title: Adicionar o código de script a páginas do site para oferecer suporte à telemetria
description: Este artigo descreve como adicionar código de script do cliente às páginas do site para dar suporte à coleção de telemetria do cliente.
author: bicyclingfool
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: a0a5103d239c7f93ad6888a2eaf56d1cac32bd58
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282263"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Adicionar o código de script a páginas do site para oferecer suporte à telemetria

[!include [banner](includes/banner.md)]

Este artigo descreve como adicionar código de script do cliente às páginas do site para dar suporte à coleção de telemetria do cliente.

A análise da Web é uma ferramenta essencial quando você deseja entender como seus clientes interagem com seu site e tomar decisões que ajudarão a otimizar a experiência para obter a conversão máxima. Muitos pacotes de análise da Web estão disponíveis para ajudar você a atingir esses objetivos, como Google Analytics, Clicky, Moz Analytics e KISSMetrics. A maioria dos pacotes de análise da Web exige que você adicione o código de script do cliente no elemento **\<head\>** do HTML para todas as páginas do seu site.

> [!NOTE]
> As instruções neste artigo também se aplicam a outras funcionalidades personalizadas do cliente que o Microsoft Dynamics 365 Commerce não oferece nativamente.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Criar um fragmento reutilizável para o seu código de script

Um fragmento permite reutilizar o código de script embutido ou externo em todas as páginas do site, independentemente do modelo usado.

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a>Criar um fragmento reutilizável para o seu código de script embutido

Para criar um fragmento reutilizável para o código de script embutido no construtor de sites, siga estas etapas.

1. Acesse **Fragmentos** e selecione **Novo**.
1. Na caixa de diálogo **Novo fragmento**, selecione **Script embutido**.
1. Em **Nome do fragmento**, digite um nome para o fragmento e, em seguida, selecione **OK**.
1. No fragmento criado, selecione o módulo **Script embutido padrão**.
1. No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente. Em seguida, configure outras opções conforme necessário.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar**.

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a>Criar um fragmento reutilizável para o seu código de script externo

Para criar um fragmento reutilizável para o código de script externo no construtor de sites, siga estas etapas.

1. Acesse **Fragmentos** e selecione **Novo**.
1. Na caixa de diálogo **Novo fragmento**, selecione **Script externo**.
1. Em **Nome do fragmento**, digite um nome para o fragmento e, em seguida, selecione **OK**.
1. No fragmento criado, selecione o módulo **Script externo padrão**.
1. No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa. Em seguida, configure outras opções conforme necessário.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar**.

> [!NOTE]
> Se a política de segurança de conteúdo (CSP) estiver habilitada para seu site, verifique se todas as URLs externas são adicionadas à diretiva **script-src** da CSP no construtor de sites do Commerce. Para obter mais informações, consulte [Gerenciar a Política de Segurança de Conteúdo (CSP)](manage-csp.md).

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a>Adicionar um fragmento que inclua código de script a um modelo

Para adicionar um fragmento que inclua código de script a um modelo no construtor de sites, siga estas etapas.

1. Acesse **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.
1. No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.
1. No slot **Head do HTML**, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar fragmento**.
1. Selecione o fragmento que você criou para o seu código de script.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar**.

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a>Adicionar um script externo ou script embutido diretamente a um modelo

Se você deseja inserir um script embutido ou externo diretamente em um conjunto de páginas controlado por um único modelo, não é necessário criar um fragmento primeiro.

### <a name="add-an-inline-script-directly-to-a-template"></a>Adicionar um script embutido diretamente a um modelo

Para adicionar um script embutido diretamente a um modelo no site Builder, siga estas etapas.

1. Acesse **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.
1. No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.
1. No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar módulo**, selecione **Script embutido**.
1. No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente. Em seguida, configure outras opções conforme necessário.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar**.

### <a name="add-an-external-script-directly-to-a-template"></a>Adicionar um script externo diretamente a um modelo

Para adicionar um script externo diretamente a um modelo no site Builder, siga estas etapas.

1. Acesse **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.
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

[Adicionar um aviso de direitos autorais](add-copyright-notice.md)

[Adicionar idiomas ao seu site](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
