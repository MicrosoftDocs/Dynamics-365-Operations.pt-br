---
title: "Pesquisa de navegação"
description: "Este artigo explica como usar a funcionalidade de pesquisa para navegar para páginas no Microsoft Dynamics 365 para as operações."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 87fed576f8cf358520d94f5cd5b326ff9801913a
ms.lasthandoff: 03/31/2017


---

# <a name="navigation-search"></a>Pesquisa de navegação

Este artigo explica como usar a funcionalidade de pesquisa para navegar para páginas no Microsoft Dynamics 365 para as operações.

O dynamics 365 de operações fornece funcionalidade para uma vasto leque indústrias e medidores verticais. O aplicativo inclui várias áreas e de páginas para ajudá-lo a executar várias tarefas. Para localizar rapidamente páginas que você precisará concluir as tarefas, use a funcionalidade de pesquisa de navegação. Para usar esse recurso, clique no ícone **Pesquisa** para exibir a caixa **Pesquisa**. Você poderá então digitar uma ou mais palavras na caixa. O sistema pesquisa instantaneamente as páginas relevantes no aplicativo que correspondem à palavra que você inseriu. Por exemplo, você pode digitar a “fatura de fornecedor” como entrada e, em seguida, o sistema exibe os resultados que correspondem a essa entrada. **Observação:** A caixa **Pesquisa** ajuda você a encontrar e navegar para páginas. Ela não ajuda você a encontrar dados ou ações específicos. 

[Pesquisar- caixa![(]. /media/search-box.png)](. /media/search-box.png) Que a funcionalidade de pesquisa de navegação também serve como uma grande de forma que você navegue em rapidamente para uma página específica. Por exemplo, se você for um funcionário de contas a pagar que usa frequentemente ** diário de pagamentos ** a página, insira “diário” o pagamento na caixa de pesquisa. Como é uma entrada - correspondência exata do título da página, a página está listado na parte superior de resultados da pesquisa, e pode rapidamente para que seja possível navegar até ele. 

[pesquisar-para-pagamento- diário do![(]. /media/searching-for-payment-journal.png)](. /media/searching-for-payment-journal.png) 

A lista de resultados de busca exibe o título da página para o caminho de navegação. Isso ajuda a torná-lo ciente do local da página no aplicativo. Ele também ajuda você a diferenciar entre duas ou mais páginas semelhantes nos resultados. Ao pesquisar por uma página, sua entrada é feita em relação ao título da página, bem como seu diretório de navegação. Por exemplo, se você inserir “receber” em ** ** pesquisar a caixa, serão exibidos os resultados para as páginas disponíveis para você na área de contas a receber--mesmo que títulos de página não inclua a palavra “receber.” 

[Pesquisar-para --![Word- receber (]. /media/search-for-the-word-receivable.png)](. /media/search-for-the-word-receivable.png) 

De uma perspectiva de administração e segurança, das superfícies funcionalidade de pesquisa de navegação somente:

-   Páginas que estão habilitadas na configuração atual (usando chaves de configuração).
-   Pagina às quais o usuário tem acesso com base na função de usuário

A lista de resultados de pesquisa é limitada a 10 itens. Se você não encontrar o que está procurando nos resultados, você deve tentar refinar ou atualizar a entrada. De uma perspectiva de desenvolvimento, é muito fácil tirar proveito do recurso de pesquisa de navegação, pois não há praticamente nenhum atraso entre a implantação dos itens de menu e a capacidade aparecer nos resultados da pesquisa. À medida que os itens de menu são vinculados ao painel de navegação ou painel de controle, eles se tornam automaticamente pesquisáveis. O recurso de pesquisa de navegação também inclui um recurso muito solicitado para usuários avançados: a capacidade de navegar rapidamente até uma página com base no nome do formulário técnico. Muitos usuários estão familiarizados de tal forma com o sistema que sabem os nomes exatos dos formulários com os quais trabalham. Se você for um desses usuários, você pode inserir **formulário:** seguido do nome do formulário que você está procurando. Por exemplo, se você inserir **formulário: vendinvoice**, os resultados da pesquisa mostrarão todas as páginas onde o nome do formulário começa com **vendinvoice**. 

[Pesquisar-para- formulário -vendinvoice - vendinvoice![(]. /media/search-for-form-vendinvoice.png)](. /media/search-for-form-vendinvoice.png)


