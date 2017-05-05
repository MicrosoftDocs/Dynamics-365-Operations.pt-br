---
title: Contagem de etiqueta de estoque
description: "Este artigo fornece informações sobre a contagem de etiquetas, que pode ser usado para comparar o conteúdo real de um depósito com o estoque disponível."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 896b91647b65843bf67211cab68b4dd08e379b18
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-tag-counting"></a>Contagem de etiqueta de estoque

[!include[banner](../includes/banner.md)]


Este artigo fornece informações sobre a contagem de etiquetas, que pode ser usado para comparar o conteúdo real de um depósito com o estoque disponível. 

Ao criar linhas na página **Contagem de etiquetas**, você coloca um número de etiqueta em cada item de estoque, como um número de 1 a 500. Durante a contagem, você digita o número e a quantidade do item na respectiva etiqueta. Esta etiqueta pode ser usada como base para entrada no diário de contagem de etiquetas. Após você lançar o diário de contagem de etiquetas, um novo diário de contagem é criado na página **Contagem**. O novo diário se baseia nas linhas do diário de contagem de etiquetas que você criou. Para contar as etiquetas de itens por uma dimensão de estoque específica, selecione a dimensão na página **Dimensão de exibição** exibida quando você cria o diário de contagem de etiquetas. Por exemplo, para contar itens em um depósito específico, marque a caixa de seleção **Depósito**. Se o controle deslizante **Bloquear itens durante a contagem** na página **Parâmetros de gerenciamento de depósito e estoque** estiver selecionado, os itens não poderão ser atualizados fisicamente durante a contagem. No entanto, os itens em diários de contagem de etiquetas não são bloqueados durante a contagem. As transações de estoque não são criadas até que as linhas de contagem sejam lançadas e transferidas para um diário de contagem. Se as etiquetas forem inseridas aleatoriamente e você quiser identificar etiquetas ausentes, clique no cabeçalho da coluna **Etiqueta** para classificar as linhas por etiqueta.

<a name="see-also"></a>Consulte também
--------

[Contagem cíclica](../warehousing/cycle-counting.md)



