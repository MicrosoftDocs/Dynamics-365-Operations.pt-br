---
title: Lotes intercompanhia e números de série
description: Este artigo explica o que acontecerá quando você registrar números de lotes e números de série para ordens intercompanhia
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 5c743c8eee8d27a2c2357523a11236eb247ec5be
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851497"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Lotes intercompanhia e números de série

[!include [banner](../../includes/banner.md)]

As empresas que usam números de série ou de lote no rastreamento dos itens também devem controlar os números de série e de lote dos itens separados. A funcionalidade intercompanhia automatiza o envio por push/pull dos números de série e de lote de uma empresa para outra. Quando você registra os números de série e de lote dos itens em uma ordem de venda intercompanhia, é possível definir o programa para encaminhar esses números automaticamente para a ordem de compra intercompanhia e para a ordem de venda original. É preciso configurar os parâmetros relevantes na página **Intercompanhia** para a ordem de venda:

- Caso você selecione o campo **Número do lote** na página **Políticas de ordem de venda**, o número de lote será sincronizado com as transações de estoque nas linhas da ordem de compra intercompanhia quando a guia de remessa da ordem de venda intercompanhia for lançada.
- Caso você selecione o campo **Número de série**, os números de série serão sincronizados com as transações de estoque nas linhas da ordem de compra intercompanhia quando guia de remessa da ordem de venda intercompanhia for lançada.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
