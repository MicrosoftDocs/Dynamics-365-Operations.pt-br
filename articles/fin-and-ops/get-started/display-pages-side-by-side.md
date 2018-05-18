---
title: "Exibir páginas lado a lado usando o ícone Abrir em Nova Janela"
description: "Este artigo explica como exibir página lado a lado no Microsoft Dynamics 365 for Finance and Operations."
author: aneesmsft
manager: AnnBe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4a575665a2b893745a2f2044cd97177917ee1a33
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="display-pages-side-by-side-using-the-open-in-new-window-icon"></a>Exibir páginas lado a lado usando o ícone Abrir em Nova Janela

[!include [banner](../includes/banner.md)]

Este artigo explica como exibir página lado a lado no Microsoft Dynamics 365 for Finance and Operations.

O Microsoft Dynamics 365 for Finance and Operations ajuda você a executar tarefas de forma eficiente. Em alguns casos, você pode optar por exibir várias páginas lado a lado para concluir tarefas rapidamente. Como um exemplo, você pode desejar validar ou inserir linhas em mais de um diário. Normalmente, para fazer isso você precisaria voltar e avançar entre a página que exige uma lista de diários, e a página que exige as linhas para um determinado diário. No entanto, o recurso **Abrir em nova janela**, permite exibir essas páginas lado a lado de forma que você possa executar suas tarefas rapidamente. 

Continuando com o exemplo acima, ao exibir as linhas, você pode clicar no ícone **Abrir em nova janela**. 

[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png) 

Clique no ícone **Abrir em nova janela** para abrir a página de linhas em um novo navegador pop-up e, em seguida, navegue no histórico do navegador original até a página que exibiu a lista de diários. Em seguida, você pode exibir ambas as páginas lado a lado. Ao terminar de exibir um diário, você pode alterar o diário selecionado na página de listagem de diário, e a página de linhas na janela pop-up exibirá automaticamente as linhas do diário recentemente selecionado. 

[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png) 

A vinculação dinâmica e a atualização acontecem devido às relações que existem entre os dados que são subjacentes a essas páginas. Se o sistema não estiver ciente da relação entre os dados, a janela pop-up não atualizará automaticamente em resposta a uma alteração na janela da qual ela se originou. 

Algumas páginas possuem várias exibições como, por exemplo, exibição de grade, exibição de cabeçalho, e exibição de detalhes. O ícone **Abrir em nova janela** faz com que toda a página seja aberta na nova janela do navegador. Sendo assim, não é possível manter duas exibições da mesma página lado a lado usando o recurso **Abrir em nova janela**. No entanto, quase todas essas páginas têm uma lista de navegação que você pode usar para alternar entre os registros e obter uma experiência semelhante. 

Antes de usar o recurso **Abrir em nova janela**, é necessário configurar o bloqueador de pop-ups do navegador para permitir pop-ups do URL do site do Finance and Operations. Como um exemplo, você poderia permitir pop-ups de "\*.dynamics.com". 

O recurso **Abrir em nova janela** estará disponível apenas quando houver mais de uma página aberta na janela. Além disso, a janela pop-up será fechada automaticamente quando não houver mais páginas abertas (ou seja, quando a última página nessa janela estiver fechada.) O Finance and Operations também fecha as páginas em aberto quando você navega para uma área diferente no aplicativo. Portanto, se você tem janelas pop-up abertas e navega para uma área diferente no aplicativo, as janelas pop-up são fechadas automaticamente porque as páginas nas janelas foram fechadas pelo sistema. 

A barra superior nas janelas pop-up exibe informações sobre a empresa na qual a página foi aberta e é somente leitura. As janelas pop-up também dependem da janela principal do navegador do Finance and Operations. Se a janela principal for fechada ou atualizada, todos janela pop-up em aberto se tornarão somente leitura. Isso significa que você ainda pode exibir as informações nas janelas, mas você não poderá interagir com elas.




