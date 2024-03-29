---
title: Pesquisa de navegação
description: Este artigo explica como usar a funcionalidade de pesquisa para navegar até páginas.
author: jasongre
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.openlocfilehash: 4c362e4cd83f926e7e21d775abd24ae6ddfcbbed
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292327"
---
# <a name="navigation-search"></a>Pesquisa de navegação

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Este artigo explica como usar a funcionalidade de pesquisa para navegar até páginas.

O aplicativo inclui várias áreas e páginas para ajudá-lo a executar várias tarefas. Para localizar rapidamente páginas que você precisa para concluir as tarefas, use a funcionalidade de pesquisa de navegação.

Para usar esse recurso, clique no ícone **Pesquisa** para exibir a caixa **Pesquisa**. Você poderá então digitar uma ou mais palavras na caixa. O sistema pesquisa instantaneamente as páginas relevantes no aplicativo que correspondem à palavra que você inseriu. Por exemplo, você pode digitar a "fatura de fornecedor" como a entrada e, em seguida, o sistema exibe os resultados que correspondem a essa entrada.

> [!NOTE]
> A caixa **Pesquisa** ajuda você a encontrar e navegar para páginas. Ela não ajuda você a encontrar dados ou ações específicos.

![search-box.](media/navigation-search.png "Caixa Pesquisar")

## <a name="quickly-navigate-to-a-particular-page"></a>Navegar rapidamente até uma página específica

O recurso de pesquisa de navegação também serve como uma ótima forma de navegar rapidamente até uma determinada página. Por exemplo, se você for um funcionário de contas a pagar que usa frequentemente a página **Diário de pagamentos**, você pode inserir "diário de pagamentos" na caixa **Pesquisar**. Como a entrada é uma correspondência exata do título da página, a página é listada no topo dos resultados de pesquisa e você pode navegar rapidamente para ela.

A lista de resultados de pesquisa exibe o título da página, bem como o diretório de navegação. Isso mostra o local da página no aplicativo. Ele também ajuda você a diferenciar entre duas ou mais páginas semelhantes nos resultados.

Ao pesquisar por uma página, sua entrada é feita em relação ao título da página, bem como seu diretório de navegação. Por exemplo, se você digitar "a receber" na caixa **Pesquisar**, verá os resultados das páginas disponíveis para você na área de Contas a receber, mesmo que os títulos de página não incluam a palavra "a receber".

## <a name="quickly-navigate-to-a-page-based-on-the-technical-form-name"></a>Navegar rapidamente para uma página com base no nome do formulário técnico

O recurso de pesquisa de navegação também inclui um recurso muito solicitado para usuários avançados: a capacidade de navegar rapidamente até uma página com base no nome do formulário técnico. Muitos usuários estão familiarizados de tal forma com o sistema que sabem os nomes exatos dos formulários com os quais trabalham. Se você for um desses usuários, você pode inserir **formulário:** seguido do nome do formulário que você está procurando. Por exemplo, se você inserir **formulário: vendinvoice**, os resultados da pesquisa mostrarão todas as páginas onde o nome do formulário começa com **vendinvoice**.

## <a name="administration-and-security"></a>Administração e segurança

De uma perspectiva de administração e segurança, a funcionalidade de pesquisa de navegação somente navega em dois tipos de resultados:

- Páginas que estão habilitadas na configuração atual (usando chaves de configuração).
- Pagina às quais o usuário tem acesso com base na função de usuário.

A lista de resultados de pesquisa é limitada a 10 itens. Se você não encontrar o que está procurando nos resultados, você deve tentar refinar ou atualizar a entrada.

## <a name="development"></a>Desenvolvimento

De uma perspectiva de desenvolvimento, é muito fácil tirar proveito do recurso de pesquisa de navegação, porque não há praticamente nenhum atraso entre a implantação dos itens de menu e a capacidade aparecer nos resultados da pesquisa. À medida que os itens de menu são vinculados ao painel de navegação ou painel de controle, eles se tornam automaticamente pesquisáveis.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
