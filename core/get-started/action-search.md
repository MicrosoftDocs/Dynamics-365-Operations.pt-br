---
title: "Pesquisa de ação"
description: "Este artigo descreve a funcionalidade de pesquisa da ação no Microsoft Dynamics 365 para as operações. A pesquisa de ação o ajudará a encontrar e executar ações em uma página."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 689d8f9fb0501c5007db21d41f126737af77b89e
ms.lasthandoff: 03/31/2017


---

# <a name="action-search"></a>Pesquisa de ação

Este artigo descreve a funcionalidade de pesquisa da ação no Microsoft Dynamics 365 para as operações. A pesquisa de ação o ajudará a encontrar e executar ações em uma página.

<a name="introduction"></a>Introdução
------------

As páginas no Microsoft Dynamics 365 para operações expõem primeiro comandos os painéis de ações, o painel de ações padrão que aparece na parte superior da página e as barras de ferramentas que se publiquem em mais seções de página. Em versões anteriores, um recurso-chave de dicas deixou-o rapidamente acessar qualquer botão de um painel de ações pressionando a tecla de Alt e depois uma série de letras. 

[![(keyTipsAX6]. /media/keytipsax6.png)](. /media/keytipsax6.png) Entretanto, na versão atual do 365 para operações, dicas não estarão mais disponíveis mas foram substituídos por funcionalidade de pesquisa da ação. Esse novo recurso permite procurar e executar rapidamente um botão em qualquer Painel de Ação visível.

## <a name="using-action-search"></a>Usando a pesquisa de ação
Para usar o recurso de pesquisa de ação, siga estas etapas.

1.  No Painel de Ação, clique no campo **pesquisa de ação**. (O campo **pesquisa de ação** tem um ícone de lupa).
2.  Digite o toda ou parte do nome do botão que deseja executar. Também é possível pesquisar usando word caminho de botões “.” (Para obter mais informações, consulte a seção a este item.) Normalmente, um botão aparecerá na parte superior lista os resultados depois de digitar dois a quatro caracteres.
3.  Localize e execute o botão na lista de resultados (usando o mouse ou o teclado).

Depois que o botão é executado, o foco retorna à sua última posição na página, para que você possa continuar trabalhando. 

[ação-Pesquisar- campo] (![. /media/action-search-field.png)](. /media/action-search-field.png)

Você também pode iniciar a pesquisa de ação pressionando Ctrl+/ ou Alt+Q. Pressione o atalho de teclado novamente para retornar o foco à sua última posição na página.

## <a name="understanding-the-results-list"></a>Noção básica da lista de resultados
Frequentemente, em dynamics 365 para as operações, você deve saber o local e o contexto de um botão para compreender totalmente a finalidade desse botão. Portanto, as informações adicionais é mostrado para cada item da lista de resultados, para ajudar a entender os botões que aparecem na lista. Particularmente, o "caminho" do botão é exibido. Esse caminho pode incluir os rótulos dos seguintes elementos da interface do usuário, conforme relevantes:

-   Guia Painel de Ação
-   Grupo de botões
-   Botão de menu (se o botão estiver em um botão de menu)
-   Separador de menu (se o botão estiver em um grupo nomeado, dentro de um botão de menu)
-   Grupo ou guia na página (por exemplo, o nome de uma Guia Rápida)

Por exemplo, você digitou **tot** no campo de **pesquisa de ação** e agora está examinando a lista de resultados. A primeira entrada, para um botão que é chamado ** totais **, está realçada. Um caminho de botões ** ordem de venda ** &gt; ** de exibição ** também será mostrado. ** ** Ordem de venda a parte do caminho corresponde ** ** ordem de venda para a guia do painel de ações, e exibição ** ** a parte do caminho corresponde ** exibição ** o grupo neste guia. De forma similar, o caminho ** ** desconto total de venda (botão ** ** &gt; ** calcule **) informa que este botão será posicionado em ** calcula ** ** grupo na venda ** guia do painel de ações. Portanto, essa informação o ajudará a entender exatamente o botão será disparado por busca de ação (caso selecione o botão da lista de resultados.) 

[ação-Pesquisar-campo-com- dados do![(]. /media/action-search-field-with-data.png)](. /media/action-search-field-with-data.png) 

No exemplo anterior, a pesquisa de ação mostrou resultados do painel de ações padrão na parte superior da página. No entanto, a pesquisa de ação também exibe resultados de barras de ferramentas visíveis que estão localizadas em outros locais da página. Por exemplo, você estará pesquisando para ** ** botão estoque disponível que está localizado ** linhas de ordem de venda em FastTab **. Nesse caso, o caminho de botões na lista de resultados (** linhas de ordem de venda ** &gt; ** estoque ** &gt; ** exibição **) informa que este botão será posicionado em exibição ** ** o título ** ** estoque no botão de menu ** linhas de ordem de venda em FastTab **. 

[![estoque disponível (-]. disponível em /media/on ARA - inventory.png])(. disponível em /media/on ARA - inventory.png)

## <a name="action-search-vs-navigation-search"></a>Pesquisa de ação x pesquisa de navegação
Considerando a pesquisa da ação está direcionada localizar e ações de execução em uma página, há um mecanismo separado de pesquisa para encontrar e navegar para páginas em dynamics 365 para as operações. Para obter mais informações sobre esse recurso, consulte [] busca de navegação (navigation-search.md) item.


