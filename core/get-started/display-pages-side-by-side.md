---
title: "Exibir páginas lado a lado usando o ícone Abrir em Nova Janela"
description: "Este artigo explica como exibir página lado a lado no Microsoft Dynamics 365 for Operations."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 940d086f9c99af54bfcc7911ee7272f9eccba464
ms.lasthandoff: 03/31/2017


---

# <a name="display-pages-side-by-side-using-the-open-in-new-window-icon"></a>Exibir páginas lado a lado usando o ícone Abrir em Nova Janela

Este artigo explica como exibir página lado a lado no Microsoft Dynamics 365 for Operations.

O Microsoft Dynamics 365 for Operations ajuda você a executar tarefas de forma eficiente. Em alguns casos, você pode optar por exibir várias páginas lado a lado para concluir tarefas rapidamente. Como um exemplo, você pode desejar validar ou inserir linhas em mais de um diário. Normalmente, para fazer isso você precisaria voltar e avançar entre a página que exige uma lista de diários, e a página que exige as linhas para um determinado diário. No entanto, o recurso **Abrir em nova janela**, permite exibir essas páginas lado a lado de forma que você possa executar suas tarefas rapidamente. Continuando com o exemplo acima, ao exibir as linhas, você pode clicar no ícone **Abrir em nova janela**. [aberto-em-novo-janela- ícone![(]. /media/open-in-new-window-icon.png)](. /media/open-in-new-window-icon.png) Que clicar ** aberto na nova janela ** o ícone abrir linhas em uma nova página, navegador pop-up, e navega na parte traseira original de navegador histórico na página que exibida a lista de diários. Em seguida, você pode exibir ambas as páginas lado a lado. Ao terminar de exibir um diário, você pode alterar o diário selecionado na página de listagem de diário, e a página de linhas na janela pop-up exibirá automaticamente as linhas do diário recentemente selecionado. [page-apresentação-lado-por- lado do![(]. /media/pages-show-side-by-side.png)](. /media/pages-show-side-by-side.png) A fixação dinâmico e atualizar ocorre devido que existem as relações entre os dados que estão voltando essas páginas. Se o sistema não estiver ciente da relação entre os dados, a janela pop-up não atualizará automaticamente em resposta a uma alteração na janela da qual ela se originou. Algumas páginas possuem várias exibições como, por exemplo, exibição de grade, exibição de cabeçalho, e exibição de detalhes. O ícone **Abrir em nova janela** faz com que toda a página seja aberta na nova janela do navegador. Sendo assim, não é possível manter duas exibições da mesma página lado a lado usando o recurso **Abrir em nova janela**. No entanto, quase todas essas páginas têm uma lista de navegação que você pode usar para alternar entre os registros e obter uma experiência semelhante. Antes de usar o recurso **Abrir em nova janela**, é necessário configurar o bloqueador de pop-ups do navegador para permitir pop-ups do URL do site do Dynamics 365 for Operations. Como exemplo, você poderia permitir pop-ups\*“.dynamics.com”. O recurso **Abrir em nova janela** estará disponível apenas quando houver mais de uma página aberta na janela. Além disso, a janela pop-up será fechada automaticamente quando não houver mais páginas abertas (ou seja, quando a última página nessa janela estiver fechada.) O Dynamics 365 for Operations também fecha as páginas em aberto quando você navega para uma área diferente no aplicativo. Portanto, se você tem janelas pop-up abertas e navega para uma área diferente no aplicativo, as janelas pop-up são fechadas automaticamente porque as páginas nas janelas foram fechadas pelo sistema. A barra superior nas janelas pop-up exibe informações sobre a empresa na qual a página foi aberta e é somente leitura. As janelas pop-up também dependem da janela principal do navegador do Dynamics 365 for Operations. Se a janela principal for fechada ou atualizada, todos janela pop-up em aberto se tornarão somente leitura. Isso significa que você ainda pode exibir as informações nas janelas, mas você não poderá interagir com elas.


