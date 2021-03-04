---
title: Auditar faturas e dados-chave em contas a pagar
description: Este tópico mostra como auditar faturas e dados-chave em contas a pagar.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5bb89f0adce41b045b1f573c4c0e841f78b2248c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440234"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>Auditar faturas e dados-chave em contas a pagar

[!include [banner](../../includes/banner.md)]

Ao receber uma fatura de um fornecedor para bens em uma ordem de compra, seus processos de negócios podem necessitar que os bens ou serviços sejam recebidos antes que a nota fiscal possa ser aprovada para pagamento. Antes de começar, verifique se a configuração conciliação de faturas está marcada. 

Na página **Parâmetros de contas a pagar**, verifique se a opção Habilitar validação da conciliação de faturas está selecionada, o campo **Lançar fatura com discrepâncias** está definido como **Exigir aprovação** e o campo **Política de conciliação de linha** está definido como **Conciliação tripla**.

Este procedimento usa a empresa de dados de demonstração USMF. A função gerente de contas a pagar ou gerente de contabilidade executaria estas etapas.


## <a name="create-a-purchase-order"></a>Crie uma ordem de compra
1. Ir para **Todas as ordens de compra**.
2. Clique em **Novo**.
3. No campo **Conta de fornecedor**, insira um valor.
4. Clique em **OK**.
5. Clique em **Adicionar linha**.
6. No campo **Número de item**, digite um valor.
7. No Painel de Ação, clique em **Compra**.
8. Clique em **Confirmar**.

## <a name="post-a-product-receipt"></a>Lançar um recebimento de produto
1. No Painel de Ação, clique em **Receber**.
2. Clique em **Recebimento de produtos**.
3. No campo **Recebimento de produtos**, digite um valor.
4. Clique em **OK**.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registre e a concilie uma fatura de fornecedor com um recebimento de produto
1. No Painel de Ação, clique em **Fatura > Fatura**.
2. No campo **Número**, digite um valor.
3. Clique no **padrão de: Quantidade encomendada** para abrir a caixa de diálogo de descarte.
4. No campo **Quantidade padrão para linhas**, selecione uma opção.
5. Clique em **OK**.
6. Clique em **Sim**.
7. Clique em **Conciliar recebimentos de produtos**.
8. Clique em **OK**.
9. No Painel de Ação, clique em **Revisar**.
10. Clique em **Detalhes da conciliação**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]