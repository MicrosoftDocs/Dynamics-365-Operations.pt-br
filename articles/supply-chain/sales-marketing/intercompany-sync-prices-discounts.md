---
title: Sincronizar preços e descontos intercompanhia
description: Este artigo explica a sincronização de preços e descontos para ordens de venda intercompanhia e ordens de compra
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
ms.openlocfilehash: 64130c400212a819f931cc36459667e4d7c83f32
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905679"
---
# <a name="synchronize-intercompany-prices-and-discounts"></a>Sincronizar preços e descontos intercompanhia

[!include [banner](../../includes/banner.md)]

Os descontos e preços são sempre sincronizados entre a ordem de venda intercompanhia e a ordem de compra intercompanhia. Também é possível sincronizar o preço e os descontos de/para a ordem de venda original, de modo que todas as ordens tenham os mesmos preços e descontos. Isso é feito na página **Intercompanhia**, que é acessada da guia **Geral** da página de listagem **Todos os clientes** – seja de **Vendas e marketing** ou de **Compras**.

O campo **Preço e desconto** é sincronizado com a linha da ordem de venda intercompanhia. Isso significa que selecionando o campo **Permitir edição de preços** e o campo **Permitir edição de descontos**, você permitiu uma alteração entre a ordem de venda intercompanhia e a ordem de compra intercompanhia. Uma alteração no preço unitário, na unidade de preço ou em encargos de vendas na ordem de venda intercompanhia determina o preço na linha da ordem de compra intercompanhia.

Se os campos **Permitir edição de preços** e **Permitir edição de descontos** estiverem habilitados na ordem de venda intercompanhia ou na ordem de compra intercompanhia, será possível alterar o preço ou descontá-lo manualmente em ambas as ordens. Caso contrário, não será possível.

Se os campos **Permitir edição de preços** e **Permitir edição de descontos** não estiverem habilitados na ordem de venda intercompanhia, não será possível alterar o preço (ou encargos) ou descontá-lo manualmente em uma ordem de venda intercompanhia.

Se os campos **Permitir edição de preços** e **Permitir edição de descontos** não estiverem habilitados na ordem de compra intercompanhia, não será possível alterar o preço (ou encargos) ou descontá-lo manualmente em uma ordem de compra intercompanhia.

Se os campos **Permitir edição de preços** e **Permitir edição de descontos** estiverem habilitados na ordem de venda intercompanhia e na ordem de compra intercompanhia, será possível fazer alterações manuais em ambas as ordens. No entanto, isso poderá resultar em atualizações feitas por uma pessoa substituídas pelas atualizações feitas por outra pessoa em outra empresa na mesma ordem.

> [!NOTE]
> Se o campo **Preço e desconto** nas ordens de compra e de venda intercompanhia foi habilitado, você não controlará os preços.

Para evitar esses tipos de conflito, a melhor prática será permitir que os preços e descontos sejam alterados somente na ordem de venda intercompanhia ou na ordem de compra intercompanhia. Isso é realizado por meio da habilitação dos campos **Permitir edição de preços** e **Permitir edição de descontos** em qualquer uma dessas ordens.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
