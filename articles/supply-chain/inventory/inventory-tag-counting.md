---
title: Contagem de etiqueta de estoque
description: Este artigo fornece informações sobre a contagem de etiquetas, que pode ser usado para comparar o conteúdo real de um depósito com o estoque disponível.
author: yufeihuang
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ceccfce98a71f7396358de9369af61c9eb96dce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856154"
---
# <a name="inventory-tag-counting"></a>Contagem de etiqueta de estoque

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre a contagem de etiquetas, que pode ser usado para comparar o conteúdo real de um depósito com o estoque disponível.

Ao criar linhas na página **Contagem de etiquetas**, você coloca um número de etiqueta em cada item de estoque, como um número de 1 a 500. Durante a contagem, você digita o número e a quantidade do item na respectiva etiqueta. Esta etiqueta pode ser usada como base para entrada no diário de contagem de etiquetas. Após você lançar o diário de contagem de etiquetas, um novo diário de contagem é criado na página **Contagem**. O novo diário se baseia nas linhas do diário de contagem de etiquetas que você criou. Para contar as etiquetas de itens por uma dimensão de estoque específica, selecione a dimensão na página **Dimensão de exibição** exibida quando você cria o diário de contagem de etiquetas. Por exemplo, para contar itens em um depósito específico, marque a caixa de seleção **Depósito**. Se o controle deslizante **Bloquear itens durante a contagem** na página **Parâmetros de gerenciamento de depósito e estoque** estiver selecionado, os itens não poderão ser atualizados fisicamente durante a contagem. No entanto, os itens em diários de contagem de etiquetas não são bloqueados durante a contagem. As transações de estoque não são criadas até que as linhas de contagem sejam lançadas e transferidas para um diário de contagem. Se as etiquetas forem inseridas aleatoriamente e você quiser identificar etiquetas ausentes, clique no cabeçalho da coluna **Etiqueta** para classificar as linhas por etiqueta.

## <a name="additional-resources"></a>Recursos adicionais

[Contagem cíclica](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]