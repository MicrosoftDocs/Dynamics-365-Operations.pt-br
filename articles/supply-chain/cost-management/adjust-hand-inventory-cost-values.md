---
title: "Ajustar valores de custo de estoque disponível"
description: "Use a página Ajuste de estoque disponível para ajustar o valor de custo das quantidades de estoque disponível após a execução de um processo de fechamento de estoque."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7f7c1008eea83bbda96ace92cd4aedf09c8febdc
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="adjust-on-hand-inventory-cost-values"></a>Ajustar valores de custo de estoque disponível

[!include[banner](../includes/banner.md)]

Use a página Ajuste de estoque disponível para ajustar o valor de custo das quantidades de estoque disponível após a execução de um processo de fechamento de estoque.

Você pode usar a página **Ajuste de estoque disponível** para ajustar o valor de custo das quantidades de estoque disponível após a execução de um processo de fechamento de estoque. **Observação:** para abrir a página **Ajuste de estoque disponível**, na página **Fechamento e ajuste**, selecione o registro de um processo de fechamento de estoque e clique em **Ajuste** &gt; **Disponível**. **Exemplo:** você tem estas transações em fevereiro:

-   1º de fevereiro: um recebimento financeiro de estoque para uma quantidade de 2 a um custo de BRL 10,00
-   5 de fevereiro: um recebimento financeiro de estoque para uma quantidade de 1 a um custo de BRL 13,00
-   19 fevereiro: uma saída financeira de estoque para uma quantidade igual a 1 a um custo médio em execução de R$ 11,00

Esse item foi configurado com o modelo de estoque PEPS (primeiro a entrar, primeiro a sair), e o fechamento do estoque foi feito em 28 de fevereiro. A transação de saída financeira de US$ 11,00 será liquidada no recebimento financeiro datado de 1º de fevereiro e será feito um ajuste de US$ 1,00. Os seguintes recebimentos de estoque conterão, assim, quantidades de estoque em aberto:

-   1º de fevereiro: uma quantidade igual a 1 a um custo de R$ 10,00
-   5 de fevereiro: uma quantidade igual a 1 a um custo de R$ 13,00

Para definir o custo desses dois itens como BRL 15,00, use a opção de ajuste disponível para ajustar as quantidades disponíveis em aberto no último período de fechamento de estoque. **Observação:** a data de lançamento da transação de ajuste disponível será a data do último fechamento de estoque. Essa data não pode ser modificada.
