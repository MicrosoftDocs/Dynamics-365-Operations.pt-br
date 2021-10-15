---
title: Sincronizar encargos intercompanhia
description: Este tópico explica a sincronização de encargos intercompanhia
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c4854b698c8046fc603454c4d9d7059c938c70b3
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548105"
---
# <a name="synchronize-intercompany-charges"></a>Sincronizar encargos intercompanhia

[!include [banner](../../includes/banner.md)]

Os encargos são sincronizados somente entre a ordem de venda intercompanhia e a ordem de compra intercompanhia, e a sincronização sempre acontece.

Se o campo **Permitir edição de preço** estiver selecionado na ordem de compra ou na ordem de venda intercompanhia, você poderá adicionar manualmente um encargo na ordem de compra ou de venda intercompanhia. Caso contrário, não será possível.

Se o campo **Permitir edição de preço** não estiver selecionado na ordem de venda intercompanhia, você não poderá adicionar um encargo diverso manualmente a uma ordem de venda intercompanhia.

Se o campo **Permitir edição de preço** não estiver selecionado na ordem de compra intercompanhia, você não poderá adicionar um encargo manualmente a uma ordem de compra intercompanhia.

Se o campo **Permitir edição de preço** estiver habilitado na ordem de compra intercompanhia e na ordem de venda intercompanhia, você poderá adicionar manualmente encargos nas duas ordens. No entanto, isso poderá resultar em muitos encargos adicionados incorretamente.

Para evitar esses tipos de conflitos, a melhor prática é permitir que os encargos sejam adicionados à ordem de compra intercompanhia ou à ordem de compra intercompanhia, mas não às duas.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
