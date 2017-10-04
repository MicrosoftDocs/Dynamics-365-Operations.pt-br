---
title: "Pesquisa de ação"
description: "Este artigo descreve a funcionalidade de pesquisa de ação no Microsoft Dynamics 365 for Finance and Operations. A pesquisa de ação ajudará a encontrar e executar ações em uma página."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: cd024f2bc06fca9c21ea41fbed44efbc519cee94
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017


---

# <a name="action-search"></a>Pesquisa de ação

[!include[banner](../includes/banner.md)]


Este artigo descreve a funcionalidade de pesquisa de ação no Microsoft Dynamics 365 for Finance and Operations. A pesquisa de ação ajudará a encontrar e executar ações em uma página.

<a name="introduction"></a>Introdução
------------

As páginas no Microsoft Dynamics 365 for Finance and Operations expõem principalmente comandos em Painéis de Ação: o Painel de Ação padrão que aparece na parte superior da página e as barras de ferramentas que aparecem em várias seções da página. Em versões anteriores, um recurso Dicas de Tecla permitia acessar rapidamente qualquer botão de um Painel de Ação pressionando a tecla Alt e depois uma série de letras. 

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png) Entretanto, na versão atual do Finance and Operations, as dicas de tecla não estarão mais disponíveis, mas foram substituídas por funcionalidade de pesquisa da ação. Esse novo recurso permite procurar e executar rapidamente um botão em qualquer Painel de Ação visível.

## <a name="using-action-search"></a>Usando a pesquisa de ação
Para usar o recurso de pesquisa de ação, siga estas etapas.

1.  No Painel de Ação, clique no campo **pesquisa de ação**. (O campo **pesquisa de ação** tem um ícone de lupa).
2.  Digite todo ou parte do nome do botão que deseja executar. Também é possível pesquisar usando palavras do "caminho" do botão. (Para obter mais informações, consulte a próxima seção deste artigo.) Normalmente, um botão aparecerá próximo ao topo da lista de resultados depois que você digitar dois a quatro caracteres.
3.  Localize e execute o botão na lista de resultados (usando o mouse ou o teclado).

Depois que o botão é executado, o foco retorna à sua última posição na página, para que você possa continuar trabalhando. 

[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)

Você também pode iniciar a pesquisa de ação pressionando Ctrl+/ ou Alt+Q. Pressione o atalho de teclado novamente para retornar o foco à sua última posição na página.

## <a name="understanding-the-results-list"></a>Noção básica da lista de resultados
Frequentemente, no Finance and Operations, você deve conhecer o local e o contexto de um botão para compreender totalmente a finalidade desse botão. Por isso, as informações adicionais são mostradas para cada item da lista de resultados, para ajudar a entender completamente os botões que aparecem na lista. Particularmente, o "caminho" do botão é exibido. Esse caminho pode incluir os rótulos dos seguintes elementos da interface do usuário, conforme relevantes:

-   Guia Painel de Ação
-   Grupo de botões
-   Botão de menu (se o botão estiver em um botão de menu)
-   Separador de menu (se o botão estiver em um grupo nomeado, dentro de um botão de menu)
-   Grupo ou guia na página (por exemplo, o nome de uma Guia Rápida)

Por exemplo, você digitou **tot** no campo de **pesquisa de ação** e agora está examinando a lista de resultados. A primeira ocorrência, referente ao botão **Totais**, é realçada. O caminho de botão **Ordem de venda** &gt; **Exibir** também é exibido. A parte **Ordem de venda** do caminho corresponde à guia **Ordem de venda** do Painel de Ação e a parte **Exibir** do caminho corresponde ao grupo **Exibir** dessa guia. Da mesma forma, o caminho do botão **Desconto total** (**Venda** &gt; **Calcular**) informa que esse botão está localizado no grupo **Calcular**, na guia **Venda** do Painel de Ação. Portanto, essas informações ajudam você a compreender exatamente qual botão será acionado pela pesquisa de ação (se você selecionar esse botão na lista de resultados). 

[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png) 

No exemplo anterior, a pesquisa de ação mostrou resultados do painel de ações padrão na parte superior da página. No entanto, a pesquisa de ação também exibe resultados de barras de ferramentas visíveis que estão localizadas em outros locais da página. Por exemplo, você está procurando o botão **Estoque disponível**, localizado na Guia Rápida **Linhas de ordem de venda**. Nesse caso, o caminho do botão na lista de resultados (**Linhas de ordem de venda** &gt; **Estoque** &gt; **Exibir**) informa que esse botão está localizado abaixo do cabeçalho **Exibir** no botão de menu **Estoque**, na Guia Rápida **Linhas de ordem de venda**. 

[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Pesquisa de ação x pesquisa de navegação
Enquanto a pesquisa de ação tem como objetivo localizar e executar ações em uma página, existe um mecanismo de pesquisa destinado especificamente à localização e navegação nas páginas do Finance and Operations. Para obter mais informações sobre esse recurso, consulte o artigo [Pesquisa de navegação](navigation-search.md).



