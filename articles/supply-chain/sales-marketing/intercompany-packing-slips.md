---
title: Guias de remessa intercompanhia
description: Este tópico descreve como gerar e imprimir guias de remessa para transações intercompanhia
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
ms.openlocfilehash: 72d052d2daba90d49ba372fb3fb480bdd0877398
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548109"
---
# <a name="intercompany-packing-slips"></a>Guias de remessa intercompanhia

## <a name="generate-intercompany-packing-slips"></a>Gerar guias de remessa intercompanhia

[!include [banner](../../includes/banner.md)]

Caso você trabalhe com entrega direta, a guia de remessa sempre será gerada automaticamente na ordem de compra intercompanhia e na ordem de venda original quando você gerar a guia de remessa na ordem de venda intercompanhia. A fatura da ordem de venda intercompanhia se baseia na guia de remessa da ordem de compra intercompanhia que foi gerada anteriormente.

Caso você faça alguma atualização na guia de remessa na ordem de venda intercompanhia, essas atualizações se refletirão na ordem de compra intercompanhia e na ordem de venda original.

Caso não trabalhe com entrega direta, você deverá gerar manualmente a guia de remessa na ordem de venda intercompanhia, na ordem de compra intercompanhia e na ordem de venda original.

## <a name="print-intercompany-packing-slips"></a>Imprimir guias de remessa intercompanhia

[!include [banner](../../includes/banner.md)]

Caso você trabalhe com entrega direta, uma guia de remessa poderá ser impressa automaticamente para a ordem de compra intercompanhia e para a ordem de venda original quando a guia de remessa for lançada na ordem de venda intercompanhia.

Para imprimir guias de remessa automaticamente, na página **Intercompanhia** para ordens de compra, selecione os campos **Imprimir guia de remessa automaticamente**.

Caso você atualize a guia de remessa na ordem de venda intercompanhia, as alterações serão refletidas automaticamente na ordem de compra intercompanhia e na ordem de venda original.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
