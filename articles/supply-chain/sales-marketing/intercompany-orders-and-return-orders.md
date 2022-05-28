---
title: Ordens intercompanhia e ordens de devolução
description: Este tópico explica ordens intercompanhia e ordens de devolução
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
ms.openlocfilehash: 1c22c021adce5f892ccb6c2ff8735f9e647e8b81
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671832"
---
# <a name="intercompany-orders-and-return-orders"></a>Ordens intercompanhia e ordens de devolução

[!include [banner](../../includes/banner.md)]

Este tópico descreve como ordens de compra intercompanhia, ordens de venda, ordens de devolução, contratos de compra e contratos de venda são criados e atualizados.

## <a name="about-intercompany-orders"></a>Sobre ordens intercompanhia

Quando você cria uma ordem de venda intercompanhia, o Microsoft Dynamics 365 Supply Chain Management cria uma ordem de compra correspondente automaticamente. De maneira semelhante, a criação de uma ordem de compra intercompanhia leva à criação automática de uma ordem de venda intercompanhia correspondente.

Isso é verdadeiro para ordens de duas pernas (transações entre duas empresas relacionadas) e para a maioria das empresas de três pernas (quando uma transação intercompanhia se origina de uma ordem de venda para um cliente externo).

## <a name="intercompany-order-example"></a>Exemplo de ordem intercompanhia

Você tem duas empresas relacionadas. A Empresa A é uma subsidiária de vendas e a Empresa B é uma unidade de distribuição. As ordens de venda e de compra intercompanhia são criadas automaticamente nestes cenários:

- Quando a Empresa A cria uma ordem de compra e o fornecedor é a Empresa B, uma ordem de venda intercompanhia é criada automaticamente na Empresa B. A cadeia de ordem de duas pernas consiste em uma ordem de compra na Empresa A e uma ordem de venda intercompanhia na Empresa B.
- Quando a Empresa B cria uma ordem de venda e o cliente é a Empresa A, uma ordem de compra intercompanhia é criada automaticamente na Empresa A. A cadeia de ordem de duas pernas consiste em uma ordem de compra na Empresa B e uma ordem de compra intercompanhia na Empresa A.
- Quando a Empresa A cria uma ordem de venda para um cliente externo, uma ordem de compra pode ser criada automaticamente na Empresa A. Isso, por sua vez, leva à criação automática de uma ordem de venda intercompanhia na Empresa B. A cadeia de ordem de três pernas consiste em uma ordem de venda e uma ordem de compra na Empresa A e uma ordem de venda intercompanhia na Empresa B.

## <a name="about-intercompany-return-orders"></a>Sobre ordens de devolução intercompanhia

Você pode devolver itens intercompanhia como se fossem devoluções normais. No entanto, no caso de itens intercompanhia, a ordem de devolução de um cliente externo cria uma ordem de compra intercompanhia. Isso, por sua vez, leva à criação automática de uma ordem de devolução de venda intercompanhia. Você também pode devolver um item intercompanhia sem uma ordem de devolução de cliente externo.

As ordens de devolução intercompanhia, semelhantes a ordens de devolução normais, são iniciadas no formulário **Criar ordem de devolução**.

No Microsoft Dynamics 365 Supply Chain Management, as vendas intercompanhia e os contratos de compra são automaticamente atualizados para refletir um item devolvido. O compromisso de vendas ou do contrato de compra para esse item será ajustado automaticamente para refletir a alteração da quantidade ou o valor quando um item for devolvido.

## <a name="intercompany-return-order-example"></a>Exemplo de ordem de devolução intercompanhia

A Empresa A cria uma ordem de compra vinculada a um contrato de compra para um item intercompanhia. Uma ordem de venda intercompanhia é criada automaticamente na Empresa B e está vinculada ao contrato de venda correspondente. O contrato de compra e o contrato de venda estão relacionados como contratos intercompanhia.

A Empresa A devolve o item intercompanhia para a Empresa B. A Empresa B cria uma ordem de devolução para o item, e uma ordem de devolução de compra é automaticamente criada na Empresa A. Os compromissos no contrato de compra e no contrato de venda que estão vinculados às ordens originais são automaticamente ajustados para refletir a alteração na quantidade ou no valor.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
