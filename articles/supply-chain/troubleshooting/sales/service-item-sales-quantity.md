---
title: Não é possível definir a quantidade de item de serviço em uma linha de cotação de venda
description: Ao trabalhar com cotações de venda, não será possível definir uma quantidade de venda para produtos que sejam itens de serviço, porque não há itens físicos a serem contados.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea0f8f246e95f90b6ac5e78ee63950c9ca836a0e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475621"
---
# <a name="cant-change-the-sales-quantity-of-a-service-item-on-a-sales-quotation-line"></a>Não é possível alterar a quantidade de venda de um item de serviço em uma linha de cotação de venda

## <a name="symptoms"></a>Sintomas

Se você tentar definir uma quantidade de venda (campo **SalesQty**) para um item do tipo *Serviço* em uma linha da cotação de venda, você receberá a seguinte mensagem:

> Atualização não permitida para o campo Quantidade.

## <a name="cause"></a>Causa

Isso ocorre por design. Não é possível definir uma quantidade de venda para produtos que são itens de serviço. Por exemplo, se você oferece um serviço para instalar um item, não faz sentido registrar uma quantidade porque não há um item físico a ser contado. Há apenas um serviço.
