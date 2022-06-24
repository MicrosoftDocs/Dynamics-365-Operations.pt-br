---
title: Sincronizar informações de cliente intercompanhia
description: Este artigo explica a sincronização de informações do cliente para ordens intercompanhia
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
ms.openlocfilehash: a3a67c9bcf93f88375d2d4d78d87175200626d50
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897506"
---
# <a name="synchronize-intercompany-customer-information"></a>Sincronizar informações de cliente intercompanhia

[!include [banner](../../includes/banner.md)]

As informações sobre cliente são sincronizadas caso o campo **Informações do cliente** seja habilitado durante a criação da ordem de venda ou quando é feita uma alteração no cliente, referência do fornecedor ou número de requisição do cliente.

Você sempre poderá alterar o valor nos campos de sincronização. No entanto, você só poderá determinar se o valor será copiado para outras ordens intercompanhia selecionando esse parâmetro. Caso você tenha habilitado o campo **Informações do cliente** na ordem de venda intercompanhia, uma alteração na ordem de venda intercompanhia é sincronizada com a ordem de compra intercompanhia. Caso você também tenha habilitado o campo **Informações do cliente** na ordem de compra intercompanhia, ela é sincronizada novamente com a ordem de venda original.

> [!NOTE]
> Caso você tenha habilitado o campo **Informações do cliente** nas ordens de compra e de venda intercompanhia, as atualizações feitas por uma pessoa de uma empresa são anuladas pelas atualizações feitas por outra pessoa de outra empresa na mesma ordem.

A prática recomendada é habilitar o campo **Informações do cliente** na ordem de compra intercompanhia. Isso permite a sincronização entre a ordem de venda original e a ordem de compra intercompanhia, e da ordem de compra intercompanhia e a ordem de venda intercompanhia.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
