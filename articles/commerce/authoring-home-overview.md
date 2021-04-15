---
title: Visão geral da página Criação
description: Este tópico fornece uma visão geral da criação de páginas no Microsoft Dynamics 365 Commerce.
author: brendans
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application USer
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brendans
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b5e1e7dd669a9608d385086cf24d388b065c9ca6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799868"
---
# <a name="authoring-page-overview"></a>Visão geral da página Criação

  
 [!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral da criação de páginas no Microsoft Dynamics 365 Commerce.

Sites podem ser criados para oferecer suporte a várias necessidades empresariais. Eles podem representar uma empresa por completo, oferecer um único canal de negócios ou ter como alvo um público ou segmento específico de audiência. Por exemplo, um fabricante de vestuário pode ter um site que apresente todos os tipos de marca que ele possui. O mesmo de fabricante vestuário pode ter um site em separado para cada uma dessas marcas, e também um conjunto de sites que tenha roupas de luxo, roupa casual e roupas de criança.

Dynamics 365 Commerce oferece suporte à criação e gerenciamento de vários sites, e cada site pode ter sua própria aparência e conteúdo. A página de criação funciona como um ponto de acesso comum para esses sites. Você pode usá-lo para entrar e sair do sistema e para criar novos sites.

Atualmente, a página de criação consiste nas seguintes seções.

- **Barra superior** – A barra superior aparece na parte superior da página de criação. Fornece acesso fácil às ferramentas de comércio eletrônico, notificações, links de suporte e entrada de usuário.
- **Barra de comandos** – A barra de comandos aparece na barra superior. Pode ser usada para criar novos sites.
- **Lista de sites** – A lista de sites preenche qualquer espaço na barra de comandos. Fornece uma lista completa dos sites e dos domínios que são associados com eles.

A ilustração a seguir mostra a página de criação.

![Página de criação do Dynamics 365 Commerce](../commerce/media/authoring_tools_01.png)

## <a name="use-the-home-button-to-select-a-tool"></a>Use o botão Início para selecionar uma ferramenta

O botão **Início** no canto superior esquerdo da página de criação. Fornece acesso fácil a outras ferramentas de comércio eletrônico. Quando selecionar este botão, um menu de ferramentas que você pode usar é aberto. Quando você seleciona uma ferramenta, o menu está fechado, e a ferramenta selecionada é carregada no navegador.

## <a name="view-and-clear-notifications"></a>Exibir e excluir notificações

O botão **Notificações** é um dos botões no canto superior direito da página de criação. Se parece com um sino. Selecionando esse botão, você pode exibir todas as notificações que foram enviadas para você.

Notificações serão usadas na ferramenta de criação para informar você quando ações foram concluídas. Por exemplo, uma notificação pode indicar, “Sua página foi publicada" para informar você que uma ação foi publicada com sucesso.

Notificações também pode informar sobre os erros que foram encontrados quando uma ação foi executada. Selecione a identificação de erro para abrir a mensagem. As informações nessa mensagem podem ajudá-lo a solucionar o erro.

Você pode desmarcar as notificações do menu de notificações selecionando **Remover** na parte inferior de notificação. Para desmarcar as notificações em massa, selecione **Remover todos** na parte inferior do menu de notificação.

## <a name="get-help-with-the-authoring-tool"></a>Obter ajuda com a ferramenta de criação

O botão **Ajuda** é outro botão no canto superior direito da página de criação. É como um ponto de interrogação. Quando selecionar este botão, um menu das opções predefinidas a seguir é aberto:

- **Ajuda no desenvolvimento do site** – Se você selecionar esta opção, a documentação para criar um novo site será aberta em uma nova guia do navegador.
- **Comentários e suporte** – Selecione esta opção para abrir um canal do Microsoft Yammer no qual é possível deixar comentários sobre a criação ou solicitação de suporte.
- **Privacidade e cookies** – Se você selecionar esta opção, a política de privacidade da Microsoft é aberta em uma nova guia do navegador.
- **Sobre** – Selecione esta opção para abrir uma caixa de mensagem que contém informações sobre a ferramenta de criação e a versão que você está usando atualmente.

## <a name="sign-in-to-and-out-of-the-authoring-tool"></a>Entrar e sair da ferramenta de criação

O botão **Minha conta** é outro botão no canto superior direito da página de criação. É como um círculo colorido. Ao selecionar este botão, você pode ver qual conta foi usada para entrar, e também poderá sair dessa conta se precisar.

Para entrar e sair da ferramenta de criação, siga uma dessas etapas.

- Se você não estiver conectado a uma ferramenta de criação, selecione **Minha conta** \> **Entrar** para entrar.
- Se já estiver conectado e quiser sair, selecione **Minha conta** \> **Sair**.

## <a name="change-the-display-language-of-the-authoring-tool"></a>Altere o idioma de exibição da ferramenta de criação

Você também pode usar o botão **Minha conta** para alterar o idioma dos caracteres de texto que aparecem na ferramenta de criação.

Para alterar o idioma de exibição, siga estas etapas.

1. Selecione **Minha conta** \> **Alterar idioma**. Uma caixa de diálogo será exibida.
1. Selecione um dos idiomas de usuário e depois selecione **Salvar**.

## <a name="create-a-new-website"></a>Criar um novo site

Dynamics 365 Commerce oferece suporte à criação e gerenciamento de vários sites, e cada site pode ter sua própria aparência e conteúdo.

Para criar um novo site, siga estas etapas.

1. Na barra de comandos, selecione **Novo site**. Uma caixa de diálogo será exibida.
2. Insira as seguintes informações necessárias para o novo site:

    - **Nome do site** – Insira o nome do site. Esse nome não é exibido para os clientes do site. Em vez disso, é usado na lista do site e em outros locais na ferramenta de criação.
    - **Site administra o grupo de segurança** – Insira o nome completo do grupo de segurança do Microsoft Azure Active Directory (Azure AD) que contém os usuários que devem ter acesso administrativo ao site. O nome de grupo admin, junto com outras permissões de site, pode ser alterado depois que o site for criado.
    - **Canal padrão** – Insira o canal de venda padrão que deverá ser associado ao site. O canal padrão determina os produtos que podem ser vendidos no site.
    - **Idioma padrão** – Após especificar o canal padrão, selecione o idioma padrão para o canal. O canal padrão define o idioma no qual os produtos são exibidos se o cliente não especificar um idioma preferido.
    - **Mercado padrão** – Insira o mercado padrão de site. O marketing padrão define o marketing que é mostrado se o cliente não especificar um mercado preferido.
    - **Domínio** – Selecione o domínio da Web a ser associado ao site. Esse domínio é o domínio que os clientes o site acessarão em seu navegador.

1. Selecione **OK**. O novo site foi criado.

> [!NOTE]
> A criação de um novo site pode levar até 60 segundos. Depois que o processo é concluído, uma notificação aparece na área de notificação. Além disso, o site será exibido na lista de sites e possui o nome do site que você inseriu.

## <a name="select-a-website-to-author"></a>Selecione um site para criar

Essa lista de sites fornece uma lista abrangente de sites que estão associados ao sistema de comércio online. Os sites aparecem em ordem alfabética. O domínio que está associado a cada site também é conhecido. Para exibir o conteúdo de um site e um início para criar páginas, selecione o nome do site. A ferramenta de criação e o conteúdo do site são carregados.

Depois que a ferramenta de criação é carregada, você pode selecionar **Início** para retornar à página de criação.

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciar usuários e funções de comércio online](manage-ecommerce-users-roles.md)

[Considerações de otimização do mecanismo de pesquisa (SEO) para seu site](search-engine-optimization-considerations.md)

[Gerenciar a política de segurança de conteúdo (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
