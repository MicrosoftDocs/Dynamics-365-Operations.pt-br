---
title: Pesquisa de ação
description: Este artigo descreve a funcionalidade de pesquisa de ação no Microsoft Dynamics 365 for Finance and Operations. A pesquisa de ação ajudará a encontrar e executar ações em uma página.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 960c715c487fbda5d93630327f07380e6d8fbd3c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547022"
---
# <a name="action-search"></a>Pesquisa de ação

[!include [banner](../includes/banner.md)]

Este artigo descreve a funcionalidade de pesquisa de ação no Microsoft Dynamics 365 for Finance and Operations. A pesquisa de ação ajudará a encontrar e executar ações em uma página.

## <a name="introduction"></a>Introdução

As páginas no Microsoft Dynamics 365 for Finance and Operations expõem principalmente comandos em Painéis de Ação: o Painel de Ação padrão que aparece na parte superior de uma página e as barras de ferramentas que aparecem em várias seções da página. Em versões anteriores, um recurso Dicas de Tecla permitia acessar rapidamente qualquer botão de um Painel de Ação pressionando a tecla Alt e depois uma série de letras.

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)

Entretanto, na versão atual de Finance and Operations, Dicas de Tecla não estão mais disponíveis, mas foram substituídas pelo recurso de pesquisa de ação. Esse novo recurso permite procurar e executar rapidamente um botão em qualquer Painel de Ação visível.

## <a name="using-action-search"></a>Usando a pesquisa de ação

Para usar o recurso de pesquisa de ação, siga estas etapas.

1. No Painel de Ação, clique no campo **pesquisa de ação**. (O campo **pesquisa de ação** tem um ícone de lupa).
2. Digite todo ou parte do nome do botão que deseja executar. Também é possível pesquisar usando palavras do "caminho" do botão. (Para obter mais informações, consulte a próxima seção deste artigo.) Normalmente, um botão aparecerá próximo ao topo da lista de resultados depois que você digitar dois a quatro caracteres.
3. Localize e execute o botão na lista de resultados (usando o mouse ou o teclado).

Depois que o botão é executado, o foco retorna à sua última posição na página, para que você possa continuar trabalhando.

[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)

Você também pode iniciar a pesquisa de ação pressionando Ctrl+/ ou Alt+Q. Pressione o atalho de teclado novamente para retornar o foco à sua última posição na página.

## <a name="understanding-the-results-list"></a>Noção básica da lista de resultados

Frequentemente, no Finance and Operations, você deve conhecer o local e o contexto de um botão para compreender totalmente a finalidade desse botão. Por isso, as informações adicionais são mostradas para cada item da lista de resultados, para ajudar a entender completamente os botões que aparecem na lista. Particularmente, o "caminho" do botão é exibido. Esse caminho pode incluir os rótulos dos seguintes elementos da interface do usuário, conforme relevantes:

- Guia Painel de Ação
- Grupo de botões
- Botão de menu (se o botão estiver em um botão de menu)
- Separador de menu (se o botão estiver em um grupo nomeado, dentro de um botão de menu)
- Grupo ou guia na página (por exemplo, o nome de uma Guia Rápida)

Por exemplo, você digitou **tot** no campo de **pesquisa de ação** e agora está examinando a lista de resultados. A primeira ocorrência, referente ao botão **Totais**, é realçada. O caminho de botão **Ordem de venda** &gt; **Exibir** também é exibido. A parte da **Ordem de venda** do caminho corresponde à guia **Ordem de venda** no Painel Ação e a parte **Exibir** do caminho corresponde ao grupo **Exibir** daquela guia. Da mesma forma, a parte do botão **Desconto total** (**Vender** &gt; **Calcular**) informa que este botão está localizado no grupo **Calcular** na guia **Vender** do Painel Ação. Portanto, essas informações ajudam você a compreender exatamente qual botão será acionado pela pesquisa de ação (se você selecionar esse botão na lista de resultados).

[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)

No exemplo anterior, a pesquisa de ação mostrou resultados do painel de ações padrão na parte superior da página. No entanto, a pesquisa de ação também exibe resultados de barras de ferramentas visíveis que estão localizadas em outros locais da página. Por exemplo, você está procurando o botão **Estoque disponível**, localizado na Guia Rápida **Linhas de ordem de venda**. Nesse caso, o caminho do botão na lista de resultados (**Linhas de ordem de venda** &gt; **Estoque** &gt; **Exibir**) informa que esse botão está localizado abaixo do cabeçalho **Exibir** no botão de menu **Estoque**, na Guia Rápida **Linhas de ordem de venda**.

[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Pesquisa de ação x pesquisa de navegação

Enquanto a pesquisa de ação tem como objetivo localizar e executar ações em uma página, existe um mecanismo de pesquisa destinado especificamente à localização e navegação nas páginas do Finance and Operations. Para obter mais informações sobre esse recurso, consulte o artigo [Pesquisa de navegação](navigation-search.md).