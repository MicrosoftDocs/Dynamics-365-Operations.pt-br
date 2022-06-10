---
title: Registrar pagamentos automaticamente para faturas de clientes intercompanhia
description: Este tópico explica como registrar pagamentos automaticamente para faturas de clientes intercompanhia
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
ms.openlocfilehash: dbd06b21d736d1e247cd087e5bb86fbe641352e6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8669422"
---
# <a name="register-payments-automatically-for-intercompany-customer-invoices"></a>Registrar pagamentos automaticamente para faturas de clientes intercompanhia

[!include [banner](../../includes/banner.md)]

O Microsoft Dynamics 365 Supply Chain Management cria uma transação de cliente quando uma fatura de cliente intercompanhia é lançada. Essa transação de cliente permanece aberta até que seja liquidada, o que significa que foi paga. Quando a fatura da ordem de compra intercompanhia correspondente é atualizada, uma transação de fornecedor correspondente à transação de cliente é criada. Essa transação de fornecedor também permanece aberta até ser liquidada. Para reduzir o risco de diferenças, um diário de pagamento de contas a receber poderá ser criado e lançado automaticamente quando o diário de pagamento de contas a pagar for lançado.

1. Acesse **Vendas e marketing \> Clientes \> Todos os clientes**.
1. No Painel de Ações, na guia **Geral**, selecione **Intercompanhia**.
1. Para configurar os pagamentos de contas a receber intercompanhia na página **Intercompanhia** para ordens de venda, selecione o link **Políticas de ordem de venda**.
1. No campo **Diário de pagamentos**, selecione o diário de pagamentos de contas a receber em que você deseja registrar pagamentos de fornecedor intercompanhia. Você define isso na página **Parâmetros de contas a receber**.
1. Se você quiser lançar neste diário automaticamente, marque a caixa de seleção **Lançar diário automaticamente**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]