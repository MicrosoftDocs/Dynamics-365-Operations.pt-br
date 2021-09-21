---
title: Perguntas frequentes sobre compras
description: Este tópico oferece respostas a perguntas frequentes (FAQs) sobre a funcionalidade de compras do Supply Chain Management
author: kamaybac
ms.date: 05/31/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 09c99b88bc47609158805cdba1291ae462cda178
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475529"
---
# <a name="procurement-faq"></a>Perguntas frequentes sobre compras

[!include [banner](../includes/banner.md)]

Este tópico oferece respostas a perguntas frequentes (FAQs) sobre a funcionalidade de compras do Supply Chain Management.

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>É possível mostrar somente as ordens de compra que criei?

Essa funcionalidade não está disponível no momento.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>Posso reservar estoque e criar transações em relação ao estoque registrado em uma ordem de compra?

### <a name="issue-description"></a>Descrição do problema

Mesmo quando os itens estão em um estado *Registrado* em uma ordem de compra, você ainda pode reservar o estoque. Em outras palavras, você pode criar transações no estoque registrado.

### <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Criar uma ordem de compra.
2. Registre a linha da ordem de compra.
3. Observe que você pode gerar reservas ou transações no estoque registrado.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é por design. A expectativa é de que os itens registrados tenham sido entregues fisicamente no depósito ou estoque e que, portanto, estejam disponíveis para reserva.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>É possível encontrar o usuário que cancelou uma ordem de compra?

Essas informações serão rastreadas somente se a ordem de compra estiver sujeita a gerenciamento de alterações. Se você usar o gerenciamento de alterações, poderá ver quem enviou a alteração (o cancelamento) e quem a aprovou.

## <a name="why-cant-i-link-a-purchase-agreement-to-an-existing-purchase-order"></a>Por que não consigo vincular um contrato de compra a uma ordem de compra existente?

Um contrato de compra deve ser associado a uma ordem de compra quando a ordem de compra for criada. Caso contrário, as linhas da ordem de compra não podem ser associadas a linhas do contrato de compra.

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a>Que verificação dispara a mensagem "Atualizar preços e descontos inseridos manualmente ou documento externo"?

Ao alterar a data de remessa, você pode receber uma mensagem que declara, "Atualizar preços e descontos inseridos manualmente ou documento externo." Você recebe esta mensagem porque, se a data de remessa for alterada, um contrato comercial ou de venda diferente poderá ser disparado e provocar uma alteração de preço. Uma alteração na data de remessa também pode afetar agendas de depósito e outras informações relacionadas.

A mensagem é disparada sempre que qualquer uma das datas ou outros parâmetros são alterados. A finalidade da mensagem é verificar se você está ciente de alterações de preço que podem ocorrer devido a essas alterações.

A mensagem é o prompt de avaliação do contrato comercial (TAE). Para obter uma descrição completa, consulte [Políticas de avaliação de contrato comercial](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).

## <a name="why-cant-i-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Por que não consigo lançar mais de uma fatura para uma linha da ordem de compra que tem itens baseados em categoria?

Uma quantidade será obrigatória se você quiser lançar faturas. Portanto, se a quantidade total de uma linha for faturada apenas por um valor parcial, não será possível faturar o valor restante em outra fatura.
