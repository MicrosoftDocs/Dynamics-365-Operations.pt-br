---
title: Atualizações físicas e financeiras
description: Este tópico fornece uma visão geral dos tipos de transação que aumentam ou diminuem quantidades em estoque.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c7b354a7524a6e96da8e2a9eeca0d4f21b9fb0a6d515620ab3fe446425af17c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734370"
---
# <a name="physical-and-financial-updates"></a>Atualizações físicas e financeiras

[!include [banner](../includes/banner.md)]

Este tópico fornece uma visão geral dos tipos de transação que aumentam ou diminuem quantidades em estoque. 

As transações de estoque podem ser atualizadas de forma física e financeira no Dynamics 365 Supply Chain Management. Alguns dos tipos de transações físicas e financeiras aumentam as quantidades em estoque, enquanto outras diminuem a quantidade.

## <a name="physical-increases"></a>Aumentos físicos
Quando uma transação física é lançada, o status do registro da transação é **Recebido**. As transações a seguir são consideradas aumentos físicos:

-   Recebimento de ordem de compra
-   Devolução de guia de remessa de ordem de venda
-   Relate uma ordem de produção como concluída.
-   Subproduto em uma lista de separação de ordem de produção

## <a name="financial-increases"></a>Aumentos físicos
Quando uma transação de recebimento financeiro é lançada, o status do registro da transação que aumenta a quantidade é **Comprado**. As transações a seguir são consideradas aumentos físicos:

-   Fatura de fornecedor
-   Fatura de ordem de venda para uma devolução
-   Custos de ordem de produção
-   Diários de estoque de quantidade positiva, como movimento, lucros e perdas, contagem, lista de materiais e transferência

## <a name="transactions-that-increase-quantity"></a>Transações que aumentam a quantidade
As transações que aumentam a quantidade são lançadas ao preço de custo médio. O preço de custo médio calculado é baseado no custo de cada uma dessas transações para cada dimensão de estoque rastreada financeiramente. Para obter informações sobre os preços de custo médio, consulte [Preço de custo médio](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Transações que diminuem a quantidade
O preço de custo médio calculado é usado quando uma transação que diminui a quantidade é lançada, independentemente do modelo de estoque associado a esse estoque. A transação que diminui a quantidade não deve ter sido marcada anteriormente para outra transação antes do lançamento. Se o estoque disponível físico ficar negativo, o custo de estoque definido para o item na página **Item** será usado. 

> [!NOTE]
> Se a funcionalidade multissite estiver habilitada, esse custo será o custo de estoque definido para um site na página **Configurações da ordem padrão**.

## <a name="physical-issues-vs-financial-issues"></a>Saídas físicas versus saídas financeiras
Quando uma transação física de saída é lançada, o status do registro da transação é **Deduzido**. As transações a seguir são consideradas saídas físicas:

-   Diário de lista de separação de ordem de produção
-   Guia de remessa de ordem de venda
-   Devolução de guia de remessa de ordem de compra

Quando uma transação financeira é lançada, o status do registro da transação é **Vendido**. As transações a seguir são consideradas saídas financeiras:

-   Terminar uma ordem de produção
-   Fatura de ordem de venda
-   Devolução de fatura de fornecedor
-   Diários de estoque de quantidade negativa, como movimento, lucros e perdas, contagem, lista de materiais e transferência

As transações que diminuem a quantidade são lançadas ao preço de custo médio. Portanto, o procedimento de fechamento de estoque é necessário para liquidar transações de saída para transações de recebimento com base no modelo de estoque atribuído a cada item.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]