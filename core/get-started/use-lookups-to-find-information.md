---
title: "Use pesquisas para encontrar informações"
description: "No Microsoft Dynamics 365 para operações, vários campos tenham as pesquisas que podem ajudar a encontrar facilmente o valor correto ou desejado. Aprimoramentos diversos foram adicionados a pesquisas que tornam esses controles mais úteis e fazer produtivos mais usuários. Neste tópico, você saberá sobre os novos recursos de pesquisa e receberá alguns dicas úteis para obter melhor uso das pesquisas no sistema."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269934
ms.assetid: f20cbd2c-14e0-47e7-b351-8e60d3537f96
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 6a25593632575dcd71fa4a3c9cf5b83c9f8ecd39
ms.lasthandoff: 03/31/2017


---

# <a name="use-lookups-to-find-information"></a>Use pesquisas para encontrar informações

No Microsoft Dynamics 365 para operações, vários campos tenham as pesquisas que podem ajudar a encontrar facilmente o valor correto ou desejado. Aprimoramentos diversos foram adicionados a pesquisas que tornam esses controles mais úteis e fazer produtivos mais usuários. Neste tópico, você saberá sobre os novos recursos de pesquisa e receberá alguns dicas úteis para obter melhor uso das pesquisas no sistema.  

<a name="responsive-lookups"></a>Pesquisas responsivas
------------------

Em versões anteriores do 365 para operações, para interagir com um controle de pesquisa, um usuário que teria executar uma ação explícita abra o menu suspenso. Isso pode ter sido digitando um asterisco (\*) no controle para filtrar a consulta com o valor atual de controle, clicando no botão suspenso, ou usando ** Alt **+** seta para baixo ** atalho do teclado. Controla de pesquisa foram alterados destas maneiras para alinhar melhor com as práticas atuais de Web:

-   Os menus suspensos de pesquisa abrirão agora automaticamente após uma pausa ligeiramente em digitar, com o conteúdo do menu suspenso filtrados com base no valor do controle de pesquisa.
    -   Observe que o comportamento antigo de abertura automática de suspenso após digitado um asterisco (\*) foi substituído.
-   Depois do menu suspenso de pesquisa abriu, ocorrerá o seguinte:
    -   O cursor ficará em controle de pesquisa (em vez de foco que é movido no menu suspenso) para que você possa continuar a alterar o valor do controle. Entretanto, o usuário ainda poderá usar ** seta para cima ** ** e seta para baixo ** modificar linhas no menu suspenso, e inserir para selecionar a linha atual no menu suspenso.
    -   O conteúdo do menu suspenso ajustarão após alterações são feitas no valor do controle de pesquisa.

Por exemplo, considere um campo de pesquisa chamado ** ** cidade. 

Quando o foco está em ** cidade ** campo, comece a demanda da cidade que você deseja, digitando algumas letras como “colo”.  Depois que você interrompeu de digitar, a consulta aberto automaticamente filtrado 2, essas cidades que começam com “colo”. 

[typeaheadLookupExample![(]. /media/typeaheadlookupexample.png)](. /media/typeaheadlookupexample.png) 

Nesse ponto, o cursor ainda está no campo de pesquisa. Se você então continua a digite o valor é colum “”, o conteúdo de pesquisa ajusta automaticamente para refletir o valor mais recente do controle. 

![updateFilterLookupExample](./media/updatefilterlookupexample.png) 

Mesmo que o foco seja no controle de pesquisa, é possível usar ** seta para cima ** ** ou seta para baixo ** chaves para realçar a linha que deseja selecionar. Quando você pressiona ** ** entre a linha realçada será de pesquisa selecionada e o valor de controle será atualizado. 

![changingSelectionLookup](./media/changingselectionlookup.png)

## <a name="typing-in-more-than-ids"></a>Digite em mais de IDs
Ao inserir dados, é natural de usuários tentar identificar uma entidade, como um cliente ou fornecedor, em termos do nome em vez de um identificador que representará a entidade. Na versão atual do 365 para operações, muitas (mas não todas as pesquisas agora) permite a entrada de dados contextual. Este recurso avançado permite que o usuário digite a ID ou nome correspondente em controle de pesquisa. 

Por exemplo, considere ** conta de cliente ** campo ao criar uma ordem de venda. Este campo mostra ** ** ID da conta do cliente, mas um usuário preferiria normalmente ** inserir o nome da conta ** ** em vez da ID da conta ** para este campo ao criar uma ordem de venda, como “floresta vende atacado “em vez de “US-003”.

Se o usuário iniciado para informar o ** ** ID da conta no controle da pesquisa, o menu suspenso abriria automaticamente como descrito na seção e o usuário anterior ana veria a pesquisa como mostrado a seguir.

[contextual![pesquisa a um ID da conta de cliente é inserido. (]/media/howtocontextuallookups-1.png)](. /media/howtocontextuallookups-1.png)

Entretanto, o usuário também pode inserir a data de início ** ** nome de conta. Se isso for detectado, o usuário verá à pesquisa. ** Aviso como nome ** a coluna é movida para serem a primeira coluna na pesquisa, e como a pesquisa é classificada e filtrada baseada ** ** nome na coluna.

[contextual![pesquisa a um nome do cliente é inserido com (]. /media/howtocontextuallookups-2.png)](. /media/howtocontextuallookups-2.png)

## <a name="using-grid-column-headers-for-more-advanced-filtering-and-sorting"></a>Usando cabeçalhos de coluna de grade para a filtragem mais avançada e a classificação
Os aprimoramentos de pesquisa discutidos em duas seções anteriores melhoram bastante a capacidade de um usuário de até em linhas em uma pesquisa com o “começam com” a pesquisa ** ID ** ou ** nome ** campo de pesquisa. Contudo, há situações em que uma filtragem mais avançada (ou classificação) é necessário para encontrar a linha correta. Nessas situações, o usuário precisará usar as opções de filtragem e classificação em cabeçalhos de coluna de grade na pesquisa. Por exemplo, considere que um funcionário insere uma linha de ordem de venda que precisam atender “cabo direito” como os produtos. Digite “cabo **” número ** o controle não é útil, pois nenhum nome do produto que começa com “cabo.” 

![emptyitemlookup](./media/emptyitemlookup.png) 

Em vez disso, o usuário precisará desmarque o valor do controle da pesquisa, abra o menu suspenso de pesquisa e filtragem, do menu suspenso usando o cabeçalho de coluna de grade, como mostrado a seguir. Um usuário (ou do mouse o toque) possível simplesmente (ou clique toque) qualquer cabeçalho de coluna para acessar as opções de filtragem e classificação para a coluna. Para um usuário do teclado, o usuário precisará apenas de ** pressione Alt **+** abaixo ** ** seta ** as segundas vezes mover o foco no menu suspenso, após o qual o usuário podem catalogar correta a coluna, e em seguida pressione CTRL ** **+** G ** para abrir o menu suspenso de cabeçalho de coluna de grade. 

[gridfilteritemlookup![(]. /media/gridfilteritemlookup.png)](. /media/gridfilteritemlookup.png) 

Após o filtro que foi aplicado (consulte a figura abaixo), o usuário pode encontrar e selecionar a linha como de costume. 

![filtereditemlookup](./media/filtereditemlookup.png)


