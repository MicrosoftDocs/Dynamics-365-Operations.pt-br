---
title: FAQ de cliente do Dynamics 365 for Operations
description: "Este artigo dá respostas às perguntas frequentes sobre o cliente do Microsoft Dynamics 365 for Operations."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 2c99b2e1f7ddecb61be62832ca1a8d3ac1fd21a8
ms.lasthandoff: 03/31/2017


---

# <a name="dynamics-365-for-operations-client-faq"></a>FAQ de cliente do Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]


Este artigo dá respostas às perguntas frequentes sobre o cliente do Microsoft Dynamics 365 for Operations.

<a name="why-arent-symbols-loaded-when-i-use-dynamics-365-for-operations"></a>Por que os símbolos não são carregados quando uso o Dynamics 365 for Operations?
-----------------------------------------------------------------

As configurações de segurança em seu navegador podem impedir que os símbolos sejam carregados corretamente. Para resolver esse problema, siga as etapas a seguir:

-   Se você estiver passando por esse problema no Internet Explorer, clique em **Ferramentas** e depois clique em **Opções de Internet**.  Na caixa de diálogo Opções da Internet, na guia **Privacidade**, clique em **Nível de personalização**, e certifique-se de que a opção **Download de fonte** está selecionada.
-   Caso contrário, talvez seja necessário adicionar o site do Dynamics 365 for Operations à lista de sites confiáveis.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Não vejo a barra do Dynamics AX 2012. Posso manter as guias do Painel de Ação abertas a todo momento?
Planejamos implementar esse recurso em breve. Os usuários poderão optar por manter as guias do Painel de Ação abertas a todo momento. Caso contrário, as guias serão recolhidas quando não estiverem sendo usadas, para obter mais espaço de tela para a página.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-rightclick"></a>Por que às vezes vejo menus de atalho diferentes quando clico com o botão direito?
Se você clicar com o botão direito do mouse em um campo editável (ou se o texto for selecionada), o menu de atalho do navegador será exibido. Esse menu fornece acesso aos comandos **Recortar**, **Copiar**, e **Colar**. Não podemos inserir esses comandos no Dynamics 365 for Operations nos menus de atalho, pois, por motivo de segurança, os navegadores não permitem que acessemos a área de transferência do sistema de forma programática.

Se você clicar com o botão direito do mouse em um rótulo de campo ou no valor de um controle somente leitura, você verá o menu de atalho do Dynamics 365 for Operations.

Para facilitar o acesso do teclado, planejamos para implementar no futuro um atalho de teclado que abre o menu de atalho do Dynamics 365 for Operations.

## <a name="where-is-the-view-details-functionality-in-dynamics-365-for-operations"></a>Onde está o recurso de exibição de detalhes no Dynamics 365 for Operations?
A opção **Exibir detalhes** está disponível de algumas formas:

-   Se um controle tiver os recursos de **Exibir detalhes **, e se o controle tiver um valor, esse valor será exibido como um hiperlink. Você pode clicar no hiperlink para abrir uma página que contém detalhes adicionais.
-   **Exibir detalhes** também é uma opção nos menus de atalho do Dynamics 365 for Operations. Para obter mais informações sobre quando os menus de atalho do Dynamics 365 for Operations são exibidos quando você clica com o botão direito do mouse, consulte a seção anterior.





