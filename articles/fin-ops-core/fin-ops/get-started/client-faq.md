---
title: Perguntas frequentes do cliente
description: Este artigo fornece respostas às perguntas frequentes sobre o cliente do Finance and Operations.
author: jasongre
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e64fb2453f17760b17ca2a7d3f593ac34cde0cc9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071024"
---
# <a name="client-faq"></a>Perguntas frequentes do cliente

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Este artigo fornece respostas às perguntas frequentes sobre o cliente do Finance and Operations.

## <a name="why-arent-symbols-loaded"></a>Por que os símbolos não são carregados?

As configurações de segurança em seu navegador podem impedir que os símbolos sejam carregados corretamente. Para resolver esse problema, siga as etapas a seguir:

- Se você tiver esse problema no Internet Explorer, clique em **Ferramentas** e **Opções de Internet**. Na caixa de diálogo Opções da Internet, na guia **Privacidade**, clique em **Nível de personalização**, e certifique-se de que a opção **Download de fonte** está selecionada.
- Caso contrário, talvez seja necessário adicionar o site do aplicativo à lista de sites confiáveis.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Não vejo a faixa de opções do Dynamics AX 2012. Posso manter as guias do Painel de Ação abertas a todo momento?

Planejamos implementar esse recurso em breve. Os usuários poderão optar por manter as guias do Painel de Ação abertas a todo momento. Caso contrário, as guias serão recolhidas quando não estiverem sendo usadas, para obter mais espaço de tela para a página.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a>Por que, às vezes, vejo menus de atalho diferentes quando clico com o botão direito?

Se você clicar com o botão direito do mouse em um campo editável (ou se o texto for selecionada), o menu de atalho do navegador será exibido. Esse menu fornece acesso aos comandos **Recortar**, **Copiar**, e **Colar**. Não podemos inserir esses comandos nos menus de atalho pois, por motivos de segurança, os navegadores não permitem que acessemos a área de transferência do sistema de forma programática.

Se você clicar com o botão direito do mouse em um rótulo de campo ou no valor de um controle somente leitura, você verá o menu de atalho.

Para facilitar o acesso do teclado, planejamos para implementar no futuro um atalho de teclado que abre o menu de atalho.

## <a name="where-is-the-view-details-functionality"></a>Onde está a funcionalidade Exibir detalhes?

A opção **Exibir detalhes** está disponível de algumas formas:

- Se um controle tiver os recursos de **Exibir detalhes**, e se o controle tiver um valor, esse valor será exibido como um hiperlink. Você pode clicar no hiperlink para abrir uma página que contém detalhes adicionais.
- **Exibir detalhes** também é uma opção nos menus de atalho. Para obter mais informações sobre quando os menus de atalho são exibidos ao clicar com o botão direito do mouse, consulte a seção anterior.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]