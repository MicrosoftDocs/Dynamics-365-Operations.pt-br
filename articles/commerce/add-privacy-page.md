---
title: Adicionar página de política de privacidade
description: Este tópico descreve como adicionar uma página de política de privacidade ao seu site no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/08/2020
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ee9a68f46c91299065732e5f65479906f9e06079
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001314"
---
# <a name="add-a-privacy-policy-page"></a>Adicionar página de política de privacidade


[!include [banner](includes/banner.md)]

Este tópico descreve como adicionar uma página de política de privacidade ao seu site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

A conformidade com privacidade inclui medidas organizacionais que informam os usuários do site sobre como os dados são coletados e manipulados. Os usuários podem então decidir como querem que seus dados pessoais sejam manuseados e podem tomar a ação apropriada.

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a>Rever a declaração de privacidade da Microsoft em Dynamics 365 Commerce

Para revisar a declaração de privacidade da Microsoft enquanto você está nas ferramentas de criação Dynamics 365 Commerce, selecione o botão **Ajuda** (**?**) no canto superior direito, e depois selecione **Privacidade e cookies**. Uma nova guia é aberta e tem um link para a [Declaração de privacidade da Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="build-a-privacy-policy-page-for-your-site"></a>Criar uma página de política de privacidade para o seu site

No Dynamics 365 Commerce, há várias maneiras de fornecer aos usuários do site acesso à sua política de privacidade. Esta seção mostra como criar uma página de política de privacidade e, depois, faz referência à página usando um fragmento de rodapé.

A diretriz a seguir é um exemplo que mostra como criar uma página de diretiva de privacidade genérica para um site de comércio. Você é responsável por criar e implementar uma solução de página de diretiva de privacidade que atende melhor aos requisitos legais da sua empresa.

Para iniciar, nas ferramentas de criação, vá para o site para o qual você deseja criar uma página de política de privacidade.

### <a name="create-a-template"></a>Criar um modelo

> [!NOTE]
> Se um modelo que pode ser usado para a página política de privacidade já foi criado, pule para a seção de página [Criar uma política de privacidade](#build-a-privacy-policy-page).

Para criar um modelo, siga estas etapas.

1. Vá para **Modelos \> Novo modelo**.
1. Insira o nome do modelo e depois selecione **OK**.
1. No modelo, adicione os módulos necessários aos slots de página necessários. Para obter orientação, passe o mouse sobre os pontos de exclamação vermelhos.

    Por exemplo, o slot **Head do HTML** pode precisar de um módulo **Script externo padrão**.

1. No slot **Corpo**, adicione um módulo **Página padrão**.
1. No módulo **Página padrão**, no slot **Principal**, adicione um módulo **Bloco de conteúdo sofisticado**.
1. No módulo **Bloco de conteúdo sofisticado**, adicione um módulo **Item de bloco de conteúdo sofisticado**.
1. Faça check-in do modelo e publique-o.

### <a name="build-a-privacy-policy-page"></a>Criar uma página de política de privacidade

Para criar uma página de política de privacidade, siga estas etapas.

1. Vá para **Páginas \> Nova página**.
1. Selecione o modelo para a página política de privacidade.
1. Insira um nome de página e URL e depois selecione **OK**. 
1. No slot **Principal** da página, adicione um módulo **Bloco de conteúdo sofisticado**.
1. No módulo **Bloco de conteúdo sofisticado**, adicione um módulo **Item de bloco de conteúdo sofisticado**.
1. No painel de propriedades do módulo **Bloco de conteúdo sofisticado**, selecione **Adicionar Fonte de Dados**, e depois selecione **Conteúdo de Rich Text**.
1. No editor de Rich Text, insira o conteúdo da página de política de privacidade. Expanda o editor de Rich Text para o modo de tela inteira, conforme necessário.
1. Ao concluir a inserção de conteúdo, selecione **Visualização** para visualizar a página no navegador da Web.
1. Preencha as adições restantes nas propriedades de página e módulo.
1. Verifique a página de política de privacidade e publique-a.

Para publicar a URL para a página de política de privacidade, siga estas etapas.

1. Vá para **URLs** e selecione a URL para a página de política de privacidade.
1. Publique a URL selecionada.

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a>Crie um link para a página de política de privacidade em um rodapé

Você pode adicionar um link à página de política de privacidade a um fragmento. Dessa forma, você pode compartilhar o link e atualizá-lo em várias páginas do site referenciando o fragmento. Este exemplo mostra como adicionar um link à página de política de privacidade a um fragmento de rodapé.

Para adicionar um link a um fragmento de rodapé, siga estas etapas.

1. Vá para **Fragmentos de página \> Novo fragmento de página**.
1. Selecione o módulo do **Cabeçalho** e insira um nome no campo nome **Nome do Fragmento de Página**.
1. No slot **Categoria de rodapé**, adicione um módulo de **Item de cabeçalho**.
1. No painel de propriedades à direita, selecione **Vincular texto**.
1. Na caixa de diálogo **Vincular texto**, insira o texto de link e destino do link da página de política de privacidade, e depois clique em **OK**.

    Para obter a URL da página de política de privacidade, vá para **Páginas**, vá para a página de política de privacidade e copie a URL do painel Propriedades.

1. Salve o fragmento, insira-o e publique-o.
1. Visualize o fragmento e teste o link da página de política de privacidade.

Agora, o fragmento pode ser referenciado no modelo para outras páginas do site. Quando este fragmento é referenciado no módulo **rodapé** de um modelo, a referência de link aparece em todas as páginas criadas com o uso desse modelo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de conformidade](compliance-overview.md)

[Recursos e funcionalidades de acessibilidade](accessibility.md)

[Compatível com cookies](cookie-compliance.md)
