---
title: "Encontrar informações usando pesquisas"
description: "No Microsoft Dynamics 365 for Finance and Operations, vários campos possuem pesquisas que podem ajudá-lo a encontrar facilmente o valor correto ou desejado. Vários aprimoramentos foram adicionados às pesquisas tornando esses controles mais úteis e os usuários mais produtivos. Neste tópico, você aprenderá sobre esses novos recursos das pesquisas e receberá algumas dicas úteis para fazer o melhor uso possível delas no sistema."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 9de957490b2ca87949a7cbcecc9acb4e8b98aaaf
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="find-information-by-using-lookups"></a>Encontrar informações usando pesquisas

[!include [banner](../includes/banner.md)]

No Microsoft Dynamics 365 for Finance and Operations, vários campos possuem pesquisas que podem ajudá-lo a encontrar facilmente o valor correto ou desejado. Vários aprimoramentos foram adicionados às pesquisas tornando esses controles mais úteis e os usuários mais produtivos. Neste tópico, você aprenderá sobre esses novos recursos das pesquisas e receberá algumas dicas úteis para fazer o melhor uso possível delas no sistema.

## <a name="responsive-lookups"></a>Pesquisas adequadas

Em versões anteriores do Dynamics 365 for Finance and Operations, ao interagir com um controle da pesquisa, um usuário precisava realizar uma ação explícita para abrir o menu suspenso. Isso poderia ser digitando um asterisco (\*) no controle para filtrar a pesquisa com base no valor atual do controle, clicando no botão suspenso ou utilizando o atalho **Alt**+**Seta para baixo**. Os controles da pesquisa foram modificados das seguintes maneiras para melhor se alinhar às práticas atuais da web:

- Os menus suspensos da pesquisa agora abrirão automaticamente após uma breve pausa na digitação, com o conteúdo do menu suspenso filtrado com base no valor do controle da pesquisa.

    Observe que o comportamento antigo de abertura automática do menu suspenso após digitar um asterisco (\*) foi substituído.

- Assim que o menu suspenso da pesquisa é aberto, ocorrerá o seguinte:

    - O cursor ficará no controle da pesquisa (em vez do foco se mover para o menu suspenso) para que você possa continuar fazendo modificações no valor do controle. No entanto, o usuário ainda pode utilizar as setas **Para cima** e **Para baixo** para mudar de linha no menu suspenso, e o enter para selecionar a linha atual no menu suspenso.
    - O conteúdo do menu suspenso irá se ajustar após qualquer modificação no valor do controle da pesquisa.

Por exemplo, considere um campo de pesquisa chamado **Cidade**.

Quando o foco estiver no campo **Cidade**, você pode começar a procurar a cidade desejada digitando algumas letras, como "col." Assim que você parar de digitar, a pesquisa abrirá automaticamente, filtrando apenas as cidades que começam com "col".

[![typeaheadLookupExample](./media/typeaheadlookupexample.png)](./media/typeaheadlookupexample.png)

Nesse momento, o cursor ainda está no campo de pesquisa. Se você continuar digitando o valor "colum", o conteúdo da pesquisa se ajusta automaticamente para refletir o valor mais atual no controle.

![updateFilterLookupExample](./media/updatefilterlookupexample.png)

Ainda que o foco continue no controle da pesquisa, você também pode utilizar as teclas **Para cima** ou **Para baixo** para realçar a linha que deseja selecionar. Se você apertar **Enter** a linha realçada será selecionada na pesquisa e o valor do controle será atualizado.

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Digitando mais que IDs

Ao inserir dados, é natural que os usuários tentem identificar uma entidade, como um cliente ou fornecedor, em termos do nome em vez de um identificador que represente a entidade. Na versão atual do Dynamics 365 for Finance and Operations, muitas (mas não todas) pesquisas permitem a entrada de dados contextuais. Este recurso poderoso permite que o usuário digite o ID ou o nome correspondente no controle da pesquisa.

Por exemplo, considere o campo **Conta do cliente** ao criar uma ordem de venda. Esse campo mostra o **ID da conta** do cliente, mas um usuário iria tipicamente preferir inserir um **Nome da conta** em vez do **ID da conta** para esse campo ao criar uma ordem de venda, como "Forest Wholesales" em vez de "US-003."

Se o usuário começou a inserir um **ID da conta** no controle da pesquisa, o menu suspenso abriria automaticamente como descrito na seção anterior e o usuário veria a pesquisa como mostrado abaixo.

[![Pesquisa contextual quando um ID da conta do cliente é inserido](./media/howtocontextuallookups-1.png)](./media/howtocontextuallookups-1.png)

No entanto, o usuário agora também pode inserir o início de um **Nome da conta**. Se isso for detectado, o usuário verá a seguinte pesquisa. Observe como a coluna **Nome** é movida para se tornar a primeira coluna na pesquisa, e como a pesquisa é classificada e filtrada com base na coluna **Nome**.

[![Pesquisa contextual quando um nome do cliente é inserido](./media/howtocontextuallookups-2.png)](./media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Usando cabeçalhos de coluna da tabela para filtragem e classificação mais avançada

Os aprimoramentos na pesquisa discutidos nas duas seções anteriores aumentam significativamente a habilidade do usuário navegar pelas linhas em uma pesquisa com base em uma busca do tipo "começa com" nos campos **ID** ou **Nome** na pesquisa. No entanto, existem situações em que filtros (ou classificações) mais avançados são necessários para encontrar a linha correta. Nessas situações, o usuário precisa usar as opções de filtragem e classificação nos cabeçalhos de coluna da tabela dentro da pesquisa. Por exemplo, considere um funcionário inserindo uma linha da ordem de venda que precisa localizar o "cabo" certo como produto. Digitar "cabo" no controle **Número do item** não é útil, já que não existem nomes de produtos que começam com "cabo".

![emptyitemlookup](./media/emptyitemlookup.png)

Em vez disso, o usuário precisa limpar o valor do controle da pesquisa, abrir o menu suspenso da pesquisa e filtrar o menu suspenso usando o cabeçalho de coluna da tabela, como mostrado abaixo. Um usuário de mouse (ou de toque) pode simplesmente clicar em qualquer cabeçalho de coluna para acessar as opções de filtragem e classificação para aquela coluna. Para um usuário de teclado, é necessário simplesmente pressionar **Alt**+**seta** **Para baixo** uma segunda vez para mover o foco para o menu suspenso, quando o usuário poderá selecionar a coluna correta utilizando o Tab, e pressionando **Ctrl**+**G** para abrir o menu suspenso do cabeçalho de coluna da tabela.

[![gridfilteritemlookup](./media/gridfilteritemlookup.png)](./media/gridfilteritemlookup.png)

Assim que o filtro for aplicado (veja a imagem abaixo), o usuário pode encontrar e selecionar a linha como de costume.

![filtereditemlookup](./media/filtereditemlookup.png)

