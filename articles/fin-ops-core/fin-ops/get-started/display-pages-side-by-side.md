---
title: Mostrar páginas lado a lado usando o recurso Abrir em nova janela
description: Este artigo explica como exibir páginas lado a lado.
author: aneesmsft
manager: AnnBe
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35ade352edf31fe895a9b9118a8ad7d5fe6c0bde
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798394"
---
# <a name="show-pages-side-by-side-using-the-open-in-new-window-feature"></a>Mostrar páginas lado a lado usando o recurso Abrir em nova janela

[!include [banner](../includes/banner.md)]

Este artigo explica como exibir páginas lado a lado.

Você pode optar por exibir várias páginas lado a lado para concluir tarefas rapidamente. Como um exemplo, você pode desejar validar ou inserir linhas em mais de um diário. Normalmente, para validar ou inserir linhas em mais de um diário, você precisaria voltar e avançar entre a página que exige uma lista de diários, e a página que exige as linhas para um determinado diário. No entanto, o recurso **Abrir em nova janela**, permite exibir essas páginas lado a lado de forma que você possa executar suas tarefas rapidamente.

Continuando com o exemplo acima, ao exibir as linhas, você pode clicar no ícone **Abrir em nova janela**.

[![Clique no ícone Abrir em nova janela.](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)

Clique no ícone **Abrir em nova janela** para abrir a página de linhas em um novo navegador pop-up e, em seguida, navegue no histórico do navegador original até a página que exibiu a lista de diários. Em seguida, você pode exibir ambas as páginas lado a lado. Depois de exibir um diário, você pode alterar o diário selecionado na página de listagem de diário, e a página de linhas na janela pop-up exibirá automaticamente as linhas do diário recentemente selecionado.

[![Você pode exibir ambas as páginas lado a lado.](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)

A vinculação dinâmica e a atualização acontecem devido às relações que existem entre os dados que são subjacentes a essas páginas. Se o sistema não estiver ciente da relação entre os dados, a janela pop-up não atualizará automaticamente em resposta a uma alteração na janela da qual ela se originou.

Algumas páginas possuem várias exibições como, por exemplo, exibição de grade, exibição de cabeçalho, e exibição de detalhes. O ícone **Abrir em nova janela** faz com que toda a página seja aberta na nova janela do navegador. Sendo assim, não é possível manter duas exibições da mesma página lado a lado usando o recurso **Abrir em nova janela**. Quase todas essas páginas têm uma lista de navegação que você pode usar para alternar entre os registros e obter uma experiência semelhante.

Antes de usar o recurso **Abrir em nova janela**, é necessário configurar o bloqueador de pop-ups do navegador para permitir pop-ups da URL do site. Como um exemplo, você poderia permitir pop-ups de "\*.dynamics.com".

O recurso **Abrir em nova janela** estará disponível apenas quando houver mais de uma página aberta na janela. Além disso, a janela pop-up será fechada automaticamente quando não houver mais páginas abertas (ou seja, quando você fecha a última página nessa janela). O sistema também fecha as páginas abertas quando você navega para uma área diferente no aplicativo. Portanto, se você tem janelas pop-up abertas e navega para uma área diferente no aplicativo, as janelas pop-up são fechadas automaticamente porque o sistema fechou as páginas nessas janelas.

A barra superior nas janelas pop-up exibe informações sobre a empresa na qual a página foi aberta e é somente leitura. As janelas pop-up também dependem da janela principal do navegador. Se a janela principal for fechada ou atualizada, todos janela pop-up em aberto se tornarão somente leitura. Se isso acontecer, você ainda poderá exibir as informações nas janelas, mas você não poderá interagir com elas.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]